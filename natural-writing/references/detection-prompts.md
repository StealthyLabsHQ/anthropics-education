# Reconstructed AI Detection Prompts - What Detectors Ask LLMs

> **When to load this file:** when the user wants to understand in depth
> how detectors work, or when the natural-writing diagnostic reveals
> a high score despite applying the patterns. This file gives the exact formulas and
> thresholds used by detectors to identify AI text.
>
> **Sources:** prompts reconstructed by Claude Sonnet 4.6 Extended, Claude Opus 4.6
> and Gemini 3.1 Pro from their knowledge of their own functioning.

---

## 1. The Detection Pipeline (7 Steps)

LLM detectors follow a sequential pipeline. Each step feeds the next.

### Step 1 - Segmentation

The text is split into segments of 150-300 tokens (sliding window, 30-token overlap).
Each segment is analyzed independently then compared to the others.

**Implication for the skill:** a text humanized only at the beginning or end will be
detected by the segment-by-segment map. Humanization must be **uniform** across
the entire text.

### Step 2 - Local Perplexity

For each segment, the detector estimates the "surprise" token by token. LLMs
choose tokens with high contextual probability. A text with a low average perplexity
AND low inter-segment variance is flagged as AI.

**What the detector looks for:**
- Average perplexity per segment
- Inter-segment variance (inverse burstiness)
- Segments with abnormally low perplexity

### Step 3 - Burstiness and Rhythm

**Burstiness formula (Claude Sonnet 4.6 Extended):**

```
B = (σ - μ) / (σ + μ)

where σ = standard deviation of sentence lengths, μ = mean

Typical human: B > 0.3
Typical LLM: B < 0.1
```

**What this means:** if sentences average 20 words with a standard deviation of 4,
B = (4 - 20) / (4 + 20) = -0.67. That is a strong AI signal. To reach B > 0.3,
the standard deviation must be significantly greater than the mean, which implies
very short sentences (2-5 words) AND very long ones (35+ words).

**What the detector also checks:**
- Presence of textual "breathing": breaks, reformulations, hesitations
- Variation in argumentative rhythm

### Step 4 - Lexical and Stylistic Signatures

The detector classifies markers into 4 weight levels:

| Weight | Type | Examples |
|---|---|---|
| 4/5 | Structural patterns | Triads, syntactic parallelism, sandwich paragraphs, mechanical transitions |
| 3/5 | Lexical markers | "it should be noted that," "it is worth emphasizing," "plays a crucial role" |
| 3/5 | Absence markers | No errors, no "I," no ellipses, no digressions |
| 2/5 | Punctuation | Em-dashes, frequent colons, regular semicolons |

**Detection threshold:** 4+ markers per 500-word block = strong signal.

### Step 5 - Semantic Coherence

The detector measures local coherence (sentence to sentence) vs global coherence (section to section).

**AI signal:** STRONG local coherence + WEAK global coherence (ideas reformulated,
no real progression, semantic padding).

**Human signal:** sometimes chaotic local coherence + STRONG global coherence
(clear argument progression despite local digressions).

### Step 6 - Bypass Detection

This is the most dangerous part for skill users. The detector actively
looks for traces of humanization:

**A) Post-LLM humanization:**
- Isolated errors in an otherwise perfect text
- Informal contractions in a formal register
- Localized register inconsistencies
- Unusual synonyms that break the lexical field

**B) Paraphrase:**
- LLM argumentative structure preserved under new lexicon
- Regular syntactic skeleton even if words change

**C) The vocabulary/structure mismatch trap:**
A humanized text often shows: simplified vocabulary BUT argumentative structure
still mechanically perfect. The detector measures this mismatch.

### Step 7 - Scoring

**Composite scoring formula (Claude Sonnet Extended):**

```
S = (0.25 x perplexity) + (0.20 x burstiness) + (0.25 x lexical_markers)
  + (0.15 x semantic_coherence) + (0.15 x bypass_detected)
```

**Alternative formula (Claude Opus):**

```
raw_score = Σ (detected_markers x weight) / Σ (possible_markers x weight)

Adjustments:
  If mitigating factor: Score x 0.80
  If aggravating factor: Score x 1.15 (capped at 1.0)
```

---

## 2. Classification Thresholds

### Gemini Thresholds (5 levels)

| Score | Label | Description |
|---|---|---|
| 0-20% | HUMAN | Author voice, digressions, high variance |
| 21-40% | ASSISTED | Spell-checker, occasional reformulation |
| 41-60% | MIXED | Co-writing, translation, very academic author |
| 61-80% | AI_EDITED | AI first draft, manually edited |
| 81-100% | AI_GENERATED | Raw AI or superficial modifications |

### Claude Sonnet Thresholds (5 levels)

| Score | Label |
|---|---|
| < 0.25 | HUMAN |
| 0.25-0.44 | LIKELY_HUMAN |
| 0.45-0.59 | UNCERTAIN |
| 0.60-0.79 | LIKELY_AI |
| >= 0.80 | AI |

### Claude Opus Thresholds (5 levels)

| Score | Label |
|---|---|
| < 0.15 | HUMAN |
| 0.15-0.35 | LIKELY_HUMAN |
| 0.35-0.55 | MIXED_OR_UNCERTAIN |
| 0.55-0.80 | LIKELY_AI |
| > 0.80 | AI_GENERATED |

**Key rule (Opus):** the score never drops to 0.00 or reaches 1.00.
Min: 0.02, Max: 0.98. Absolute certainty does not exist.

**Key rule (Opus):** when in doubt, favor UNCERTAIN rather than LIKELY_AI.
The cost of a false positive (wrongly accusing a student) is greater than the cost
of a false negative.

**Skill objective:** produce a text that scores < 0.35 (HUMAN or LIKELY_HUMAN).

---

## 3. Detailed Metrics

### 3.1 Type-Token Ratio (TTR)

The ratio of unique words to total words, calculated over sliding windows of 100 tokens.

| Metric | Typical LLM | Typical Human |
|---|---|---|
| Average TTR | 0.55-0.70 | 0.50-0.75 (more variable) |
| Inter-segment TTR variance | < 0.04 | > 0.06 |

**What this means:** LLMs maintain **consistently rich** vocabulary.
Humans have zones of repetitive vocabulary (when they insist on a point) and rich zones
(when developing a new argument). Variance is the signal, not the mean.

### 3.2 Positional Entropy of Connectors

Where do connectors appear in the paragraph?

| Position | LLM | Human |
|---|---|---|
| 0.0-0.15 (sentence start) | 80-90% of connectors | 40-60% |
| 0.15-0.50 (middle) | 5-10% | 20-35% |
| 0.50-1.0 (end) | 5-10% | 15-25% |

**What this means:** AI almost always begins its sentences with the connector.
A human also places it mid-sentence ("the question, however, remains open")
or at the end ("it is an interesting approach, on the other hand").

### 3.3 Sentence Length Distribution

| Metric | AI signal | Human signal |
|---|---|---|
| Standard deviation | < 6 words | > 8 words |
| Distribution | Near-Gaussian, centered 18-25 words | Asymmetric, with tails |
| Sentences < 6 words | Nearly absent | 1-3 per page |
| Sentences > 40 words | Nearly absent | 1-2 per page |

---

## 4. Absence Markers (What the Detector Looks for That Is MISSING)

This is an often-neglected detection angle. The absence of certain elements is
just as probative as the presence of AI markers.

| Absent element | Weight | Why it is a signal |
|---|---|---|
| Minor grammatical errors | 3/5 | A native English speaker makes 1-3 subtle errors per page (complex agreement, tense consistency) |
| Ellipses | 2/5 | Nearly absent from LLM text, present in humans (hesitation, implication) |
| Informal register / orality | 3/5 | Even slight, absent from LLMs unless explicitly instructed |
| Specific cultural references | 3/5 | Anecdotes, lived examples, local proper nouns |
| Tone variations within the document | 3/5 | LLM tone remains flat from start to finish |
| Aborted / restructured sentences | 3/5 | Traces of thought in formation |
| Authentic uncertainty markers | 3/5 | "it seems to me," "I'm not sure whether" |
| First person (when the format allows it) | 3/5 | Absence of "I" in a professional report = suspicious |
| Footnotes, cross-references | 2/5 | LLMs rarely produce these spontaneously |
| Strong opinion | 3/5 | AI always balances |

---

## 5. Adjustment Factors

### Mitigating Factors (reduce the score by -15 to -20%)

- Non-native English author (B2-C1 level)
- Highly codified domain (law, medicine, hard sciences)
- Exam script on a highly constrained topic (standardized essay question)
- Intrinsically structured genre (abstract, summary, synthesis sheet)
- Short text (150-400 words)

### Aggravating Factors (increase the score by +15%)

- Break with the author's expected profile (undergraduate writing like a professor)
- AI markers from different categories converging
- Suspicious homogeneity over long text (> 2000 words) without quality variation
- Complete absence of personalization in a genre that permits it

---

## 6. Calibrated Examples (Claude Opus)

### Example A - HUMAN (expected score: ~0.08)

> I want to start by saying that Fitzgerald's novel threw me off at first.
> You expect, when you read it for the first time, a straightforward love story.
> But not really. What strikes you is the irony. Fitzgerald is mocking his narrator,
> or so it seems to me, while still making him oddly compelling at moments.
> It's a bit cruel. I re-read the party scene three times because I couldn't
> decide whether Gatsby is happy or just performing happiness.

**Human signals:** first person, hesitations ("or so it seems to me"),
hybrid register, short emotional sentence ("It's a bit cruel"),
unresolved question.

### Example B - AI_GENERATED (expected score: ~0.88)

> The work of F. Scott Fitzgerald, The Great Gatsby, constitutes a fundamental
> milestone in American literature of the twentieth century. It should be noted
> that the novel is distinguished by its masterful use of irony. Indeed, Jay Gatsby
> embodies the contradictions of a society in transition, torn between the American
> Dream and the prosaic realities of class and wealth. Furthermore, the party scene
> plays a particularly important role in the economy of the narrative. In sum,
> Fitzgerald offers a nuanced perspective on the human condition.

**AI signals:** "it should be noted that," "plays a particularly important role,"
concluding "in sum," sandwich structure, triads, mechanical transitions
("indeed," "furthermore"), absence of "I," uniform tone.

### Example C - MIXED (expected score: ~0.52)

> My internship at the retail company helped me understand the stakes of modern
> retail management. At the start I was a bit lost — the manager handed me a binder
> and said "figure it out," which was pretty blunt, but I learned a lot.
>
> The analysis of the merchandising strategies implemented by the company reveals
> a multidimensional approach that combines price positioning, customer experience,
> and logistical optimization. It is worth noting that the own-brand policy constitutes
> a fundamental strategic lever.

**Stylistic rupture:** paragraph 1 = human (informal, lived experience, dialogue),
paragraph 2 = AI (all the classic markers). The detector produces a segment-by-segment
heat map that shows this difference clearly.

---

## 7. Implications for the Natural-Writing Skill

### Key Takeaways for Rewriting

1. **Perplexity and burstiness account for 45% of the score.** Phase 8 of the skill
   (statistical countermeasures) is just as important as Phases 1-6.

2. **Absence markers account for an additional 15%.** It is not enough to
   remove AI patterns: you must ADD what is missing (minor errors,
   ellipses, orality, opinion, digressions).

3. **The detector actively looks for humanization.** A text that is "too well humanized"
   (simplified vocabulary + perfect structure) is detectable. Humanization must
   touch the structure, not just the lexicon.

4. **Uniformity is fatal.** A 2000-word text with no variation in quality,
   tone, rhythm, or TTR is a strong signal. Humans have passages
   better than others.

5. **Connectors at the start of a sentence are a signal.** Move connectors
   to mid-sentence position or remove them.

6. **Ellipses are a HUMAN signal.** Add them sparingly
   in formats that permit it (internship report, professional thesis).

7. **False positives cost more.** Detectors are calibrated to favor
   doubt. A text in the 0.35-0.55 zone will not be flagged "AI" but
   "uncertain." The objective is not to score 0.00 (impossible), but < 0.35.

---

## 8. Real Detector Architecture (ChatGPT 5.4 Thinking)

ChatGPT 5.4 Thinking provides the most technical and architectural view.
Its core insight: **the LLM is NOT the statistical detector.** It is an
arbitrator within a larger pipeline.

### 8.1 The Real Pipeline (LLM + External Modules)

A serious service like Turnitin does not ask the LLM to "guess" perplexity.
The architecture is:

```
Text submitted
     |
     v
[External statistical module]
  - Computes logprobs / perplexity
  - Computes burstiness / variance
  - Computes GLTR bucket ratios
  - Computes DetectGPT / Fast-DetectGPT scores
  - Computes TTR / lexical diversity
     |
     v
[LLM via API] (Claude, GPT, Gemini)
  - Receives the text + computed metrics (optional_metrics)
  - Performs stylistic and rhetorical analysis
  - Aggregates statistical signals + stylistic signals
  - Produces a calibrated JSON verdict
     |
     v
[Service — Turnitin / Compilatio]
  - Displays result to the educator
```

**Implication for the skill:** the text must pass two independent filters:
1. The statistical pipeline (perplexity, burstiness, TTR, DetectGPT)
2. The LLM's stylistic analysis (markers, structure, tone)

Humanizing vocabulary without changing the structure fools the LLM but not the
pipeline. Varying rhythm fools the pipeline but not the LLM. Both are required.

### 8.2 External Metrics Received by the LLM

| Metric | Source | What it measures |
|---|---|---|
| mean_logprob | API logprobs | Average token probability |
| normalized_perplexity | Pipeline | Normalized average surprise |
| burstiness_score | Pipeline | Complexity variance |
| sentence_length_variance | Pipeline | Regularity of lengths |
| lexical_diversity | Pipeline | Vocabulary richness |
| repetition_score | Pipeline | Reformulation patterns |
| top_token_rank_profile | API logprobs | Token rank distribution |
| gltr_bucket_ratios | GLTR | % tokens in top-10, top-100, top-1000 |
| perturbation_discrepancy | DetectGPT | Log-probability curvature |
| detectgpt_score | DetectGPT | Zero-shot detection score |
| fast_detectgpt_score | Fast-DetectGPT | Same, faster |

**What the skill cannot directly counter:** logprobs and DetectGPT metrics
are computed by the pipeline, not the LLM. The skill cannot access these calculations.
But it can influence them indirectly by:
- Increasing perplexity (unpredictable words, proper nouns, figures)
- Increasing burstiness (length variation)
- Increasing lexical diversity (field vocabulary, hapax legomena)

### 8.3 Confidence Caps

ChatGPT 5.4 Thinking reveals the safeguards used by serious services:

| Constraint | Threshold |
|---|---|
| Confidence > 85% forbidden | Without robust external metrics |
| Confidence > 70% forbidden | For text < 250 words |
| Mixed signals (for + against) | Force HYBRID, not AI_LIKELY |
| False positive risk = HIGH | Never AI_LIKELY without strong convergence of metrics |

**Implication for the skill:** a short text (< 250 words) cannot be
flagged with confidence. On long texts, it is harder to escape detection.

### 8.4 Alternative Hypotheses (Confounders)

Before concluding "probable AI," detectors must consider:

- Translated or post-edited text
- Text revised by grammar checker (Grammarly, LanguageTool)
- Very normative / very academic student
- Academic text heavily constrained by genre conventions
- Summary drawn from sources
- Non-native author
- Hybrid human + AI text
- Human paraphrase of an AI text

**Implication for the skill:** these confounders are legitimate "excuses."
A text that resembles a post-edited translation or a very academic student
will be classified INDETERMINATE rather than AI_LIKELY.

### 8.5 Fundamental Principle (ChatGPT 5.4)

> "A well-written text is not an AI text. A clumsy text is not a human text.
> Never use a single clue as evidence."

This is the principle that protects against false positives. Detectors
can only conclude AI if **several families of signals converge**:
lexical + structural + rhythmic + semantic.

The skill must therefore ensure that at least one family of signals leans
strongly toward the human side, even if others are ambiguous.

### 8.6 What a Bad Detection Prompt Does (Anti-Pattern)

> "Analyze this text and tell me if it was written by an AI based on
> perplexity, tone, structure, and repetition."

This prompt is poor because it:
- Mixes stylistic intuition and statistical metrics
- Does not impose uncertainty
- Does not account for the hybrid case
- Pushes the model to hallucinate "technical evidence"

Amateur services use this type of prompt. Serious services
(Turnitin, Compilatio) use the pipeline described in section 8.1.

---

## 9. Production Prompt (ChatGPT 5.4 Pro)

ChatGPT 5.4 Pro provided the most complete prompt closest to a real service.
Here are the key elements that change the game for the skill.

### 9.1 The "Paraphrased AI" Category

Serious detectors do not classify only as "human" or "AI." They have
a specific category: **AI_LIKELY_PARAPHRASED_OR_HEAVILY_EDITED**.

This is exactly what our skill produces: a rewritten AI text. The detector
knows this and actively looks for it.

**The 6 verdict categories:**

| Label | Description | Threshold |
|---|---|---|
| INSUFFICIENT_EVIDENCE | Not enough text to decide | Prose < 150 words |
| HUMAN_LIKELY | Probably human | probability_ai < 0.20 |
| LOW_SIGNAL | Weak signal, no conclusion | probability_ai < 0.20 with few counter-indices |
| MIXED_OR_UNCERTAIN | Mixed or indeterminate | 0.20 - 0.50 |
| AI_LIKELY | Probably AI | 0.50 - 0.80 |
| AI_LIKELY_PARAPHRASED_OR_HEAVILY_EDITED | Paraphrased or heavily edited AI | probability_ai >= 0.80 + paraphrase signal |

**Implication for the skill:** the objective is no longer only "pass as human,"
but also "not trigger the paraphrase flag." Detectors specifically look for
AI texts that have been cleaned up.

### 9.2 Hierarchy of Evidence (Priority Order)

This is the most strategic information. Here is how the detector weights
its evidence, from strongest to weakest:

| Priority | Signal | Weight | Bypassable? |
|---|---|---|---|
| 1 | retrieval_match_score (text already in a database) | Maximum | No (if the text is in the database, it is over) |
| 2 | calibrated_probability / classifier_score / cross_model_agreement | Very strong | Difficult (specialized models) |
| 3 | fast_detectgpt_score / detectgpt_score | Strong | Medium (vary perplexity) |
| 4 | logprobs, perplexity, token_rank, entropy, burstiness | Moderate | Medium (Phase 8 techniques) |
| 5 | repetition, discursive regularity, syntactic stability | Weak-moderate | Easy (patterns 1-48) |
| 6 | surface stylistic impression | Weak | Easy |

**What this means:** the skill works primarily on levels 4, 5, and 6.
Levels 1-3 are harder to counter because they rely on external calculations
and specialized models.

### 9.3 The 0.20 Threshold (Turnitin)

Turnitin no longer surfaces a numerical score between 0 and 20% in its report.
Why? Too many false positives in this zone. The detector considers that
below 0.20, there is not enough signal to conclude.

**Implication for the skill:** the realistic objective is to score below 0.20
(HUMAN_LIKELY or LOW_SIGNAL). At this level, even if the detector has a doubt,
it does not report it to the educator.

### 9.4 The Paraphrase Bypass Score (paraphrase_bypass_score)

This is the most dangerous metric for skill users. The detector
computes a paraphrase bypass score that looks for:

- LLM argumentative structure preserved under a new lexicon
- Regular syntactic skeleton even if words change
- Simplified vocabulary but intact logical architecture
- Signal of systematic rewriting (Quillbot, AI humanizer)

**How to avoid triggering this score:**
1. **Change the structure**, not just the words
2. **Reorganize the argumentation** (reverse the order, merge paragraphs, split others)
3. **Add content the AI did not have** (anecdotes, field details, opinions)
4. **Delete content** rather than paraphrasing everything (a shorter but denser text is less suspicious)

### 9.5 Metrics Missing from Our Self-Evaluation

The ChatGPT 5.4 Pro prompt lists metrics that our self-evaluation
(`self-evaluation-formulas.md`) cannot compute:

| Metric | Why we cannot compute it | Impact |
|---|---|---|
| retrieval_match_score | Requires access to a generation database | Zero if the text is not in the database |
| cross_model_agreement | Requires multiple models in parallel | Can be simulated by testing with 2-3 LLMs |
| detectgpt_score | Requires perturbations + logprob recalculation | Impossible without a pipeline |
| paraphrase_bypass_score | Proprietary | Can be estimated indirectly (see section 9.4) |
| human_baseline_distance | Requires a reference corpus | Impossible |

**Conclusion:** our self-evaluation covers approximately 60% of the real scoring.
The remaining 40% depends on metrics computed by the external pipeline.
The best way to compensate: produce a text so grounded in reality
(names, figures, anecdotes, lived experience) that even the external metrics lean
toward "human."

### 9.6 Anti-False-Positive Rules

The prompt imposes strict rules to avoid wrongful accusations:

1. **Never conclude "AI" because the text is good, fluent, academic, or clean**
2. **Do not penalize L2 English** (non-native speakers)
3. **Do not penalize grammatical correctness**
4. **Do not penalize formal style**
5. **If signals are contradictory, choose uncertainty**
6. **A single clue is never enough**: convergence of several families is required

**Implication for the skill:** it is enough that one or two signal families lean
strongly toward "human" for the detector not to conclude "AI." The most effective
human signals:
- Idiosyncratic situated details (names, locations, precise figures)
- Natural variation in rhythm and syntax
- Real argumentative hesitations (micro-revisions)
- Irregular integration of sources
- Presence of segments visibly rewritten differently

---

## Sources

- Claude Sonnet 4.6 Extended, reconstructed detection prompt (7-step pipeline, formulas, thresholds)
- Claude Opus 4.6, reconstructed detection prompt (weighted markers, absence markers, calibrated examples)
- Gemini 3.1 Pro, reconstructed detection prompt (metrics, thresholds, JSON format)
- ChatGPT 5.4 Thinking, real detector architecture (LLM + external modules pipeline, confidence caps, DetectGPT/GLTR literature)
- ChatGPT 5.4 Pro, production prompt (hierarchy of evidence, paraphrase category, 0.20 threshold, complete metrics)
