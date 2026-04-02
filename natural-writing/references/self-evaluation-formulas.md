# Anti-Detection Self-Evaluation Formulas

> **When to load this file:** after the rewriting (Step 4), before delivery.
> Give the rewritten text + this file to an LLM with extended reasoning
> (Gemini 3.1 Pro Thinking High, ChatGPT 5.4 Thinking, Claude with Extended Thinking)
> to calculate scores and verify the text passes.
>
> **Objective:** estimate the score a detector would assign to the text,
> identify risk zones, and correct before delivery.

---

## 1. Burstiness Score (B)

### Formula

```
B = (σ - μ) / (σ + μ)

σ = standard deviation of sentence length (in words)
μ = mean sentence length (in words)
```

### Interpretation

| Score B | Interpretation | Action |
|---|---|---|
| B < -0.5 | Strongly AI: sentences very regular | Deep rhythm rewriting |
| -0.5 < B < 0.0 | Suspect: too little variation | Add sentences < 6 words and > 35 words |
| 0.0 < B < 0.3 | Grey zone: might pass | Check other metrics |
| B > 0.3 | Human zone: good variance | OK |

### Sample Calculation

Text: 10 sentences of lengths [18, 22, 19, 21, 20, 17, 23, 19, 21, 20]
- μ = 20.0
- σ = 1.7
- B = (1.7 - 20.0) / (1.7 + 20.0) = -0.84 → **Strongly AI**

Corrected text: [4, 32, 18, 7, 42, 12, 3, 28, 15, 39]
- μ = 20.0
- σ = 13.8
- B = (13.8 - 20.0) / (13.8 + 20.0) = -0.18 → **Upper grey zone, acceptable**

### How to Improve B

- Insert 2-3 sentences of 3-5 words per page ("Result: nothing." "It did not work.")
- Insert 1-2 sentences of 35+ words with nested subordinate clauses
- Aim for a range of 4 to 45 words, not 15 to 25

---

## 2. Type-Token Ratio Variance (TTR)

### Formula

```
For each sliding window of 100 tokens:
  TTR_i = number of unique words / 100

TTR_mean = mean of TTR_i
TTR_var = variance of TTR_i
```

### Interpretation

| TTR_var | Interpretation | Action |
|---|---|---|
| < 0.04 | AI: lexical richness too regular | Vary vocabulary (technical zones + simple zones) |
| 0.04 - 0.06 | Grey zone | Check other metrics |
| > 0.06 | Human: natural variation | OK |

### How to Improve TTR_var

- Create zones of repetitive vocabulary (when emphasizing a point, repeat
  the same word instead of searching for a synonym)
- Create zones of rich vocabulary (when developing a new argument,
  use field-specific technical vocabulary)
- Do not maintain a constant level of richness

---

## 3. Positional Connector Entropy (PCE)

### Formula

```
For each connector detected, calculate its relative position within the paragraph:
  pos_i = index_of_connector_word / paragraph_length_in_words

Distribute pos_i into 3 zones:
  Z1 = proportion of connectors at position 0.0 - 0.15 (beginning)
  Z2 = proportion of connectors at position 0.15 - 0.50 (middle)
  Z3 = proportion of connectors at position 0.50 - 1.00 (end)

PCE = -Σ(Zi × log2(Zi)) for Zi > 0
```

### Interpretation

| Pattern Z1/Z2/Z3 | Interpretation | Action |
|---|---|---|
| Z1 > 80% | AI: connectors always at the start | Move to middle or end |
| Z1 60-80% | Suspect | Rebalance |
| Z1 40-60% | Human: natural distribution | OK |
| PCE < 1.0 | AI: concentrated distribution | Disperse the connectors |
| PCE > 1.2 | Human: dispersed distribution | OK |

### How to Improve PCE

Instead of:
> **Furthermore**, digitalization raises challenges.

Write:
> Digitalization raises, **moreover**, specific challenges.

Or:
> Digitalization raises specific challenges, **incidentally**.

Or better: remove the connector entirely.

---

## 4. Semantic Density (SD)

### Formula

```
For each sentence, evaluate:
  info_i = 1 if the sentence brings a new factual piece of information
           (number, fact, name, date, concrete observation)
  info_i = 0.5 if the sentence develops/nuances previous information
  info_i = 0 if the sentence is filler (reformulation, empty transition,
           unnecessary contextualization)

SD = Σ(info_i) / number_of_sentences
```

### Interpretation

| SD | Interpretation | Action |
|---|---|---|
| < 0.3 | AI: too much filler | Remove empty sentences, add facts |
| 0.3 - 0.5 | Grey zone | Acceptable if burstiness is OK |
| 0.5 - 0.7 | Human: good info/prose ratio | OK |
| > 0.7 | Very dense (list of facts) | OK but check it reads smoothly |

### How to Improve SD

- Remove every sentence that says nothing new
- Replace generalizations with facts: "The company progressed" → "Revenue
  went from $1.2M to $1.5M between 2024 and 2025"
- Remove transition sentences that add nothing
  ("Having examined X, let us now look at Y")

---

## 5. Structural Regularity Score (SRS)

### Formula

```
For each pair of adjacent paragraphs:
  delta_len_i = |length_para_i - length_para_i+1| / max(length_para_i, length_para_i+1)

SRS = 1 - mean(delta_len_i)
```

### Interpretation

| SRS | Interpretation | Action |
|---|---|---|
| > 0.85 | AI: all paragraphs the same length | Radically unbalance |
| 0.70 - 0.85 | Suspect | Vary lengths |
| < 0.70 | Human: paragraphs of varied lengths | OK |

### How to Improve SRS

- A 2-sentence paragraph, followed by an 8-sentence one, followed by a 4-sentence one
- Never have 3 consecutive paragraphs of similar length (± 20%)
- Allow single-sentence paragraphs

---

## 6. Hapax Legomena Ratio (HLR)

Hapax legomena are words that appear only once in the text.
Humans produce significantly more than LLMs, because LLMs recycle
a restricted and predictable vocabulary.

### Formula

```
HLR = number of words appearing exactly 1 time / total number of unique words
```

### Interpretation

| HLR | Interpretation | Action |
|---|---|---|
| < 0.40 | AI: vocabulary too recycled | Introduce technical terms, proper nouns, trade jargon |
| 0.40 - 0.55 | Grey zone | Acceptable if other metrics are OK |
| > 0.55 | Human: rich and varied vocabulary | OK |

### How to Improve HLR

- Use real field technical vocabulary (reconciliation, trial balance, working papers, FX exposure)
- Cite proper nouns (software, people, places)
- Avoid AI synonym variation (the firm / the organization / the entity)
  and prefer repeating the right word + introducing new words elsewhere

---

## 7. Zipf Law Deviation (ZLD)

Zipf's law states that in natural text, the frequency of the n-th most
frequent word is inversely proportional to its rank: freq ~ 1/rank^α. Human
texts follow this law with α close to 1.0. AI texts deviate.

### Formula

```
For each unique word, calculate:
  rank_i = ranking by descending frequency (1, 2, 3...)
  freq_i = number of occurrences

Log-log regression:
  log(freq_i) = -α × log(rank_i) + c

ZLD = |α - 1.0|
```

### Interpretation

| ZLD | Interpretation | Action |
|---|---|---|
| > 0.25 | AI: abnormal lexical distribution | Drastically vary vocabulary |
| 0.10 - 0.25 | Grey zone | Check other metrics |
| < 0.10 | Human: natural distribution | OK |

### Note

This formula is more complex to calculate. Ask the evaluating LLM to
run the log-log regression and report α. If α < 0.75 or α > 1.25,
it is an AI signal.

---

## 8. Sentence Start Diversity Index (SSDI)

LLMs begin their sentences repetitively (same type of word:
article, pronoun, connector). Humans vary more.

### Formula

```
For each sentence, classify the first word by category:
  ART = article (The, A, An)
  PRO = pronoun (It, She, We, I, They, He, That, This)
  CON = connector (Furthermore, Moreover, However, Nevertheless, Indeed)
  NOU = proper noun
  ADV = adverb (Concretely, Honestly, Unfortunately)
  VER = verb (Remains, Comes, Must)
  NUM = number (200 files, 3 staff)
  PRE = preposition/CC (In three months, Since September, During the placement)
  QUE = question (Why, How, Was)
  OTH = other

SSDI = number of categories used / 10

Then verify: no category exceeds 40% of sentence starts.
```

### Interpretation

| SSDI | Interpretation | Action |
|---|---|---|
| < 0.4 | AI: starts too repetitive | Vary openings (cf. Phase 8.3 of SKILL.md) |
| 0.4 - 0.6 | Grey zone | Verify no category dominates |
| > 0.6 | Human: good diversity | OK |

| Dominant category | Max threshold | If exceeded |
|---|---|---|
| ART (The, A...) | 30% | Start with verbs, adverbs, numbers |
| PRO (It, She...) | 25% | Vary with proper nouns, questions, circumstantials |
| CON (Furthermore...) | 15% | Remove the majority of connectors at the start |

---

## 9. Inter-Paragraph Cosine Similarity (IPCS)

AI paragraphs are semantically close to each other (they "circle around"
the same point). Human paragraphs progress: each paragraph
adds a new dimension.

### Formula

```
For each pair of adjacent paragraphs (P_i, P_{i+1}):
  Extract significant keywords (nouns, verbs, adjectives, excluding stop words)
  Build a frequency vector for each paragraph
  Calculate cosine similarity:
    cos_i = (V_i · V_{i+1}) / (||V_i|| × ||V_{i+1}||)

IPCS = mean of cos_i
```

### Interpretation

| IPCS | Interpretation | Action |
|---|---|---|
| > 0.60 | AI: paragraphs too similar (paraphrastic redundancy) | Remove duplicates, add new content |
| 0.35 - 0.60 | Grey zone | OK if thematic progression is visible |
| < 0.35 | Human: good progression | OK |

### Simplified Note

If vector calculation is too complex, ask the evaluating LLM:
"For each pair of adjacent paragraphs, estimate on a scale of 0 to 1
how much they say the same thing in different words."

---

## 10. Informational Entropy Variance by Segment (IEVS)

AI maintains constant informational density. A human alternates between
dense passages (technical analysis, numbers) and lighter passages
(anecdote, transition, aside).

### Formula

```
For each segment of ~100 words:
  E_i = number of informational elements (numbers, proper nouns, facts,
        references, technical terms) / number of words in segment

IEVS = variance of E_i
```

### Interpretation

| IEVS | Interpretation | Action |
|---|---|---|
| < 0.005 | AI: density too constant | Alternate dense and light passages |
| 0.005 - 0.015 | Grey zone | Acceptable |
| > 0.015 | Human: natural variation | OK |

### How to Improve IEVS

- After a dense paragraph (3+ numbers, technical terms), insert a
  light paragraph (anecdote, question, aside)
- Allow "informational dips" (transitions, personal reflections)
- Do not distribute facts uniformly throughout the text

---

## 11. Passive/Active Voice Ratio (PAVR)

LLMs overuse passive voice and impersonal constructions, especially
in academic writing. Humans use the active voice more.

### Formula

```
PAVR = number of passive constructions / total number of clauses

Passive constructions to count:
- "it was observed that"
- "it has been demonstrated that"
- "an improvement was noted"
- "[subject] was [past participle] by [agent]"
- Impersonal constructions: "it should be noted," "it is necessary to,"
  "it appears that," "it turns out that"
```

### Interpretation

| PAVR | Interpretation | Action |
|---|---|---|
| > 0.40 | AI: too much passive/impersonal | Rewrite in active voice with a human subject |
| 0.20 - 0.40 | Grey zone | Acceptable in a formal context |
| < 0.20 | Human: active voice dominant | OK |

### How to Improve PAVR

Instead of: "It was observed that productivity increased"
Write: "I observed that productivity increased" (if format allows)
Or: "Productivity increased by 15%" (active, factual)

---

## 12. Gini Coefficient of Paragraph Lengths (GCPL)

The Gini coefficient measures inequality. Applied to paragraph lengths,
it detects whether paragraphs are too uniform (AI) or naturally unequal (human).

### Formula

```
Sort paragraph lengths in ascending order: L_1, L_2, ..., L_n

GCPL = (2 × Σ(i × L_i) / (n × Σ(L_i))) - (n + 1) / n
```

### Interpretation

| GCPL | Interpretation | Action |
|---|---|---|
| < 0.15 | AI: paragraphs too equal | Radically unbalance |
| 0.15 - 0.30 | Grey zone | Acceptable |
| > 0.30 | Human: natural inequality | OK |

### How to Improve GCPL

- A 1-sentence paragraph, followed by a 12-line one, followed by a 4-line one
- Never have 3 consecutive paragraphs of the same length
- Allow very short (1-2 sentences) and very long (10+ sentences) paragraphs

---

## 13. Density of Self-Corrections and Thought Markers (DSTM)

Measures the presence of traces of thinking in progress: hesitations, corrections,
reframings, asides. This is the hardest signal to simulate, according to
ChatGPT 5.4 (Pattern 40 of SKILL.md).

### Formula

```
Count the following markers in the text:
  - Micro-revisions: "well," "actually," "no wait," "let's say,"
    "that is to say," "or rather"
  - Asides: parentheses containing a personal reflection
  - Rhetorical questions: "?" in the body text (excluding headings)
  - Uncertainty markers: "it seems to me," "I am not sure,"
    "probably," "in my view"
  - Cognitive cost markers: "the problem is that," "we hesitated,"
    "two options presented themselves," "it is not ideal but"

DSTM = total number of markers / (number of words / 500)
```

### Interpretation

| DSTM | Interpretation | Action |
|---|---|---|
| 0 | AI: no trace of thinking | Inject 2-3 markers per page |
| 1 - 3 | Grey zone | Acceptable, check naturalness |
| > 3 | Human: visible traces of thinking | OK |

---

## 14. Mean Syntactic Dependency Distance (MSDD)

Measures the distance in words between the subject and the main verb. AI minimizes
this distance (left-to-right generation). Humans use insertions and
subordinate clauses that increase the distance between subject and verb.

### Formula

```
MSDD = (1/N) x Σ |position(verb_i) - position(subject_i)|

N = number of sentences
```

### Interpretation

| MSDD | Interpretation | Action |
|---|---|---|
| < 2.5 | AI: subject-verb always adjacent | Insert insets between subject and verb |
| 2.5 - 3.5 | Grey zone | Acceptable |
| 3.5 - 6.0 | Human: natural distance | OK |

### Example

"The researcher, exhausted by the long hours, fell asleep." → |10-2| = 8
"The algorithm generates text." → |2-1| = 1
MSDD = (8+1)/2 = 4.5 (human)

### How to Improve

Transform: "The tool allows optimizing processes."
Into: "The tool, despite its limits on complex cases, allows for optimization."

---

## 15. Lexical Contagion Index (LCI)

Measures the repetition of lexical lemmas within a 50-token window. AI
"contaminates" its context: once a word is generated, its embedding increases the
probability of its reappearance nearby.

### Formula

```
LCI = number of lexical words reappearing within a 50-token window
    / total number of lexical words (nouns, verbs, adjectives)
```

### Interpretation

| LCI | Interpretation | Action |
|---|---|---|
| > 0.28 | AI: strong lexical contagion | Use pronouns or synonyms to space them out |
| 0.12 - 0.28 | Grey zone | Acceptable |
| < 0.12 | Human: no contagion | OK |

### Mechanism

When an LLM generates "innovation," the embedding of that word saturates the local context
and increases the probability of generating "innovation" or "innovate" shortly after.
A human spontaneously uses pronouns ("it") or changes subject.

---

## 16. Punctuation Transition Entropy (PTE)

AI punctuation follows a predictable pattern (comma → period → comma).
Humans use punctuation in an expressive and erratic way.

### Formula

```
Extract the ordered sequence of all punctuation marks in the text.
For each pair (mark_i, mark_{i+1}), calculate the transition probability.

PTE = -Σ p(transition_ij) x log2(p(transition_ij))
```

### Interpretation

| PTE | Interpretation | Action |
|---|---|---|
| < 1.1 bits | AI: predictable punctuation | Vary punctuation (ellipses, parentheses, questions) |
| 1.1 - 1.8 bits | Grey zone | Acceptable |
| > 1.8 bits | Human: expressive punctuation | OK |

### How to Improve

Do not chain comma-period-semicolon-period in a loop. Insert
parentheses, ellipses, colons, questions.

---

## 17. Emotional Valence Volatility (EVV)

RLHF alignment forces AI to maintain a constant tone. Humans have
jagged emotional trajectories.

### Formula

```
For each sentence, assign a sentiment score v_i from -1 to +1:
  +1 = very positive, 0 = neutral, -1 = very negative

EVV = sqrt( (1/(N-1)) x Σ (v_{i+1} - v_i)^2 )
```

### Interpretation

| EVV | Interpretation | Action |
|---|---|---|
| < 0.20 | AI: flat tone, RLHF neutrality | Inject contrasts (enthusiasm then frustration) |
| 0.20 - 0.45 | Grey zone | Acceptable |
| > 0.45 | Human: contrasting emotions | OK |

### Example

"This result is excellent." (v=0.8) then "But the method is shaky." (v=-0.5)
Delta = (-0.5 - 0.8)^2 = 1.69 → high EVV (human)

---

## 18. Central Embedding Rate (CER)

AI generates left-to-right and favors right-branching.
Humans plan globally and use center-embedded structures.

### Formula

```
CER = number of subordinate clauses inserted IN THE MIDDLE of the main clause
    / total number of sentences

Center embedding = Subject + [subordinate clause] + Verb
Ex: "The car, which I bought yesterday, is broken."

Right-branching (NOT center-embedded):
Ex: "I bought a car that is broken."
```

### Interpretation

| CER | Interpretation | Action |
|---|---|---|
| < 0.05 | AI: no center embedding | Insert relative clauses and insets between subject and verb |
| 0.05 - 0.25 | Grey zone | Acceptable |
| > 0.25 | Human: natural embedding | OK |

---

## 19. Brunet's W Index

Lexical richness measure that remains stable (does not drop with text length,
unlike TTR). The lower W is, the richer the vocabulary.

### Formula

```
W = N ^ (V ^ -0.165)

N = total number of words
V = number of unique words
```

### Interpretation

| W | Interpretation | Action |
|---|---|---|
| > 13.5 | AI: poor and recycled vocabulary | Enrich with technical terms, proper nouns |
| 11.5 - 13.5 | Grey zone | Acceptable |
| < 11.5 | Human: rich vocabulary | OK |

---

## 20. Mean Anaphoric Distance (MAD)

Distance in words between a pronoun and its antecedent. AI keeps pronouns
very close to avoid ambiguity. Humans trust the reader.

### Formula

```
MAD = (1/N_p) x Σ (position(pronoun_k) - position(antecedent_k))

N_p = number of pronominal links
```

### Interpretation

| MAD | Interpretation | Action |
|---|---|---|
| < 10 words | AI: pronouns adjacent to antecedent | Increase distances for some pronouns, trust the context |
| 10 - 15 words | Grey zone | Acceptable |
| 15 - 30 words | Human: natural distances | OK |

---

## 21. Lexical Specificity Ratio (LSR)

Ratio between specific terms (hyponyms) and generic terms (hypernyms).
AI uses umbrella words ("tool," "problem," "approach").
Humans are specific ("wrench," "bottleneck," "CAR method").

### Formula

```
LSR = number of specific terms / number of generic terms

Generic terms: tool, problem, approach, process, initiative, aspect,
  element, thing, situation, phenomenon, domain, sector, structure, entity
Specific terms: names of real tools, precise methods, places,
  people, named concepts
```

### Interpretation

| LSR | Interpretation | Action |
|---|---|---|
| < 0.8 | AI: too many umbrella terms | Replace generics with precise names |
| 0.8 - 1.5 | Grey zone | Acceptable |
| > 1.5 | Human: specific vocabulary | OK |

---

## 22. Verb Tense Distribution Entropy (VTDE)

AI locks itself into a base tense (simple present or simple past). Humans
navigate between tenses to express anteriority, hypothesis, regret.

### Formula

```
Count each verb tense used:
  present, simple past, present perfect, past perfect,
  future, conditional, subjunctive, infinitive

VTDE = -Σ p(tense_t) x log2(p(tense_t))
```

### Interpretation

| VTDE | Interpretation | Action |
|---|---|---|
| < 0.9 bits | AI: stuck on 1-2 tenses | Vary tenses (conditional, past perfect, subjunctive) |
| 0.9 - 1.6 bits | Grey zone | Acceptable |
| > 1.6 bits | Human: rich temporal navigation | OK |

---

## 23. Rhythmic Periodicity Index (RPI)

Variance of the number of syllables between consecutive words. AI produces a
flat rhythm (words of 2-3 syllables). Humans alternate short and long words.

### Formula

```
RPI = (1/(N-1)) x Σ |syllables(word_{i+1}) - syllables(word_i)|

N = total number of words
```

### Interpretation

| RPI | Interpretation | Action |
|---|---|---|
| < 0.8 | AI: flat syllabic rhythm | Alternate short (1 syllable) and long (4+) words |
| 0.8 - 1.3 | Grey zone | Acceptable |
| > 1.3 | Human: saw-tooth rhythm | OK |

---

## 24. KL Divergence of Syntactic Bigrams (KLD-POS)

Compares the distribution of grammatical category pairs (DET-NOU, NOU-ADJ,
VERB-DET) in the text with the natural distribution in the language.

### Formula

```
KLD = Σ P_text(bigram_i) x log2( P_text(bigram_i) / P_language(bigram_i) )

Bigrams to verify: DET-NOU, NOU-ADJ, VERB-DET, ADJ-NOU, PREP-DET,
  NOU-VERB, ADV-VERB, VERB-PREP, PRO-VERB, etc.
```

### Interpretation

| KLD | Interpretation | Action |
|---|---|---|
| > 1.2 | AI: stereotyped syntactic structures | Vary (inversions, dislocations, ellipses) |
| 0.4 - 1.2 | Grey zone | Acceptable |
| < 0.4 | Human: natural syntactic distribution | OK |

### Note

The exact calculation requires a POS tagger. Ask the evaluating LLM:
"Tag each word (DET, NOU, ADJ, VERB, PREP, ADV, PRO, CONJ),
then count bigrams and identify over-represented ones."

---

## 25. Function Word Density Ratio (FWDR)

AI "pads" its sentences with grammatical words to guarantee fluency.
Humans are more direct and content-dense.

### Formula

```
FWDR = function words / lexical words

Function words: determiners, prepositions, conjunctions, pronouns,
  auxiliaries, conjunctive locutions
Lexical words: nouns, main verbs, adjectives, manner adverbs
```

### Interpretation

| FWDR | Interpretation | Action |
|---|---|---|
| > 1.3 | AI: too much grammatical padding | Cut locutions ("it is important to note that" → just say it) |
| 1.1 - 1.3 | Grey zone | Acceptable |
| 0.7 - 1.1 | Human: natural ratio | OK |

---

## 26. Fragment Autocorrelation (FA) - Second order

**Source: Gemini 3.1 Pro Thinking High**
**Target:** Detects an AI mechanically applying the fragmentation technique.

When an LLM receives "insert short sentences," it distributes them uniformly.
A human fragments in clusters (several fragments in a row) or in deserts
(long zones with no fragments).

### Formula

```
For each sentence, f_i = 1 if verbless fragment, 0 otherwise.

Calculate autocorrelation at lags k = 1, 2, 3:
  r(k) = Σ (f_i - f_mean)(f_{i+k} - f_mean) / Σ (f_i - f_mean)^2

FA = |r(1)| + |r(2)| + |r(3)|
```

### Interpretation

| FA | Interpretation | Action |
|---|---|---|
| > 0.40 | DETECTED: fragments too regular (AI simulating human) | Cluster the fragments, do not space them regularly |
| 0.15 - 0.40 | Grey zone | Acceptable |
| < 0.15 | Human: random fragments | OK |

### How to Avoid Detection

Do not space fragments mechanically (1 fragment every 3 sentences).
Cluster them: 3 fragments in a row then 8 normal sentences, then 2 fragments.
The irregularity must itself be irregular.

---

## 27. Epistemic Modality Positional Asymmetry (EMPA) - Second order

**Source: Gemini 3.1 Pro Thinking High**
**Target:** Detects an AI adding uncertainty at the end of sentences/paragraphs.

The AI first generates a confident assertion (its default mode), then
"remembers" the prompt and appends uncertainty at the end ("Maybe." "We'll see.").
A human integrates uncertainty from the beginning of their sentence.

### Formula

```
For each paragraph p:
  M_total(p) = number of uncertainty markers
    (maybe, perhaps, we'll see, ..., ?, probably, it seems to me)
  M_final(p) = number of these markers in the last 5 tokens of the paragraph

EMPA = Σ M_final(p) / (Σ M_total(p) + 0.01)
```

### Interpretation

| EMPA | Interpretation | Action |
|---|---|---|
| > 0.80 | DETECTED: uncertainty always postfixed | Distribute uncertainty UPSTREAM in the sentence |
| 0.35 - 0.80 | Grey zone | Acceptable |
| < 0.35 | Human: uncertainty distributed | OK |

### Example

AI: "The project is going well. The teams are on it. We'll see. Maybe."
→ EMPA = 2/2 = 1.0 (DETECTED)---

## 28. Perplexity Contrast Ratio (PCR) - Second order

**Source: Gemini 3.1 Pro Thinking High**
**Target:** Global detection of simulation effort.

---

## 28. Perplexity Contrast Ratio (PCR) - Second order

**Source: Gemini 3.1 Pro Thinking High**
**Target:** Global detection of simulation effort.

When an AI simulates a human, 90% of the text remains "pure LLM" (very predictable)
and 10% consists of injections of human style (very unpredictable). This large gap
betrays the simulation.

### Formula

```
For each sentence, estimate "rarity" (perplexity proxy):
  R_i = number of rare or unpredictable words / total number of words

PCR = max(R_i) / median(R_i)
```

### Interpretation

| PCR | Interpretation | Action |
|---|---|---|
| > 12.0 | DETECTED: isolated rarity spikes in a smooth text | Distribute rarity uniformly |
| 5.0 - 12.0 | Grey zone | Acceptable |
| 2.0 - 5.0 | Human: naturally fluctuating rarity | OK |

### How to Avoid Detection

Do not concentrate all concrete details and rare words in 2-3 "token" sentences.
Distribute proper nouns, numbers, and trade jargon across the entire text.
Each paragraph must contain at least 1 unpredictable element.

---

## 29. The Over-Humanization Paradox (ChatGPT 5.4 warning)

This is not a formula but a fundamental principle for the entire system.

> "These techniques do not prove that a text is human. They increase
>  the impression of presence, irregularity, and discursive friction. They
>  may fool certain weak stylistic detectors, without guaranteeing anything
>  against a more robust analysis."
>
> "If these techniques are applied mechanically, they become a detectable
>  pattern themselves. A signature. Almost a tic."
>
> -- ChatGPT 5.4

### Anti-over-humanization rules

1. **Never apply the 5 techniques in the same order** in every paragraph
2. **Vary the frequency**: not one short fragment every 3 sentences
3. **Vary the type**: not always sarcasm, not always ellipses
4. **Do not force it**: if a paragraph does not need a micro-revision, do not
   add one just to seem "human"
5. **Uncertainty must be integrated into the sentence**, not tacked onto the end
6. **Concrete details must be distributed** across the whole text, not concentrated
7. **The best humanization is invisible**: the reader should not notice
   the techniques, only the result

### The ultimate test

If you can predict where the next "humanization technique" will fall in the text,
it is mechanical. The goal is the unpredictability of unpredictability.

---

## 30. Local Referential Anchoring Density (LRAD) - Coverage of the 40%

**Source: Gemini 3.1 Pro Thinking High**
**Target:** Compensate for the retrieval_match_score and real-world grounding.

AI is probabilistic: it generates the most probable tokens, therefore the most
generic. It suffers from a "hallucination phobia" that prevents it from inventing
hyper-local details. Humans saturate their text with Level 3 references.

### Formula

```
For each named entity, date, place, or acronym in the text, assign a weight:
  w = 1 if global entity (UK, Internet, EU)
  w = 2 if domain entity (Xero, Python, CPA, Compilatio)
  w = 3 if hyper-local/personal entity (Mr. Johnson, March 14th at 10am, room B204)

LRAD = sum(w(e_i)) / number of paragraphs
```

### Interpretation

| LRAD | Interpretation | Action |
|---|---|---|
| < 1.5 | AI: generic text, no grounding | Add names, dates, places, precise acronyms |
| 1.5 - 4.5 | Grey zone | Enrich with Level 3 entities |
| > 4.5 | Human: strongly grounded in reality | OK |

### Why This Is Decisive

A high LRAD brings detector scores below 20% because Level 3 entities
(personal names, precise locations, exact dates) are impossible for an LLM
to predict, which destroys the perplexity and token-rank metrics of the external pipeline.

---

## 31. Collocational Distortion Index (CDI) - Coverage of the 40%

**Source: Gemini 3.1 Pro Thinking High**
**Target:** Detect the paraphrase_bypass_score (Quillbot, Wordtune).

Paraphrasing tools replace words with dictionary synonyms
without accounting for natural collocations in English.

### Formula

```
For each adjacent word pair (Noun-Adjective or Verb-Noun):
  Evaluate whether the combination is natural in English.
  If not (collocation break), count as atypical.

CDI = N_atypical / N_lexical x 100
```

### Interpretation

| CDI | Interpretation | Action |
|---|---|---|
| > 8.0 | DETECTED: text mechanically paraphrased | Rewrite the broken collocations |
| 2.0 - 8.0 | Grey zone | Check suspicious pairs |
| < 2.0 | Human (or non-paraphrased AI) | OK |

### Examples of Broken Collocations

| Original | Paraphrased (detectable) | Correct |
|---|---|---|
| important question | voluminous inquiry | key question |
| solve a problem | resolve a difficulty | address the problem |
| conduct a study | execute an investigation | carry out a study |

---

## 32. Enunciative Deictic Cohesion (EDC) - Coverage of the 40%

**Source: Gemini 3.1 Pro Thinking High**
**Target:** Measure whether the author has projected themselves into their text (viva preparation).

AI produces discourse that is "ungrounded." The student who has mastered their text leaves
traces of their thinking process and the materiality of their document.

### Formula

```
D_ego = number of first-person markers involved in a cognitive action
  (I think, my analysis, our choice, I observed, it seems to me)

D_spatio = markers linking the text to its production context
  (here, this thesis, in the previous section, as mentioned above, today)

EDC = (D_ego x D_spatio) / number of sentences
```

### Interpretation

| EDC | Interpretation | Action |
|---|---|---|
| < 0.3 | AI: ungrounded discourse, no projection | Add "I," "my," anchor within the document |
| 0.3 - 1.2 | Grey zone | Enrich based on format |
| > 1.2 | Human: author projected into their writing | OK |

### Why This Relates to the Viva

A high EDC indicates that the author is aware of their own text. It is the
best predictor of oral examination success: someone who writes "my analysis
shows that..." is someone who can defend "my analysis" before a panel.

---

## 33. Signal Dilution Ratio (SDR) - Coverage of the 40%

**Source: Gemini 3.1 Pro Thinking High**
**Target:** Aim for the Turnitin invisibility zone (< 0.20).

Turnitin does not classify a document in binary fashion. If the "human noise"
exceeds a certain percentage, the classifier prefers to return < 20%
to avoid false positives.

### Formula

```
V_AI = volume of text (words) with smooth characteristics
  (low variance, predictable syntax, no concrete details)

V_human = volume of text (words) with roughness
  (LRAD > 3, self-corrections, oral syntax, minor errors,
   anecdotes, precise numbers, proper nouns)

SDR = V_human / (V_AI + V_human)
```

### Interpretation

| SDR | Interpretation | Action |
|---|---|---|
| < 0.15 | Detected: not enough human noise | Add massive amounts of personal content |
| 0.15 - 0.35 | Borderline, moderate risk | Enrich smooth zones |
| > 0.35 | Invisible to Turnitin (< 20%) | OK |

### Concrete Example

800 AI words + 100 personal intro words + 3 anecdotes of 50 words = 250 human words.
SDR = 250 / 1050 = 0.24 (borderline).

To pass: add 2 more anecdotes (100 words) -> 350/1150 = 0.30.
Or better: rewrite 200 AI words adding concrete details -> 450/850 = 0.53.

### The One-Third Rule

To be invisible: **at least one third of the text** must contain elements
that only the author can know (field details, names, dates, anecdotes, opinions).

---

## 34. Extended Composite Estimated Score (SCE v3)

> **WARNING (ChatGPT 5.4)**: Humanization techniques applied
> mechanically become a detectable pattern themselves. Long sentence, short
> sentence, aside, "Right.", "Got it.", "Maybe." - repeated, it smells like a
> recipe, not spontaneity. Formulas 26-29 above detect
> precisely this mechanical over-humanization.

### Complete Formula (26 metrics)

The SCE v3 integrates the 13 base metrics + the 12 Gemini Thinking formulas.
Each metric is normalized to [0,1] then weighted.

```
SCE_v3 =
  # --- Base metrics (60%) ---
  (0.08 x (1 - SD))                    # semantic density
  + (0.08 x (1 - norm_B))              # burstiness
  + (0.10 x marker_density)            # AI markers
  + (0.05 x SRS)                       # structural regularity
  + (0.04 x (1 - norm_HLR))            # hapax legomena
  + (0.04 x ZLD_norm)                  # Zipf deviation
  + (0.04 x (1 - SSDI))               # sentence start diversity
  + (0.04 x IPCS_norm)                 # inter-paragraph similarity
  + (0.04 x (1 - IEVS_norm))           # entropy variance
  + (0.03 x PAVR)                      # passive ratio
  + (0.03 x (1 - GCPL_norm))           # paragraph Gini
  + (0.03 x (1 - DSTM_norm))           # self-corrections

  # --- Gemini metrics (40%) ---
  + (0.04 x (1 - MSDD_norm))           # syntactic dependency distance
  + (0.04 x LCI_norm)                   # lexical contagion
  + (0.04 x (1 - PTE_norm))            # punctuation transition entropy
  + (0.04 x (1 - EVV_norm))            # emotional valence volatility
  + (0.04 x (1 - CER_norm))            # central embedding rate
  + (0.03 x W_norm)                     # Brunet index
  + (0.03 x (1 - MAD_norm))            # anaphoric distance
  + (0.03 x (1 - LSR_norm))            # lexical specificity
  + (0.03 x (1 - VTDE_norm))           # verb tense entropy
  + (0.02 x (1 - RPI_norm))            # rhythmic periodicity
  + (0.02 x KLD_norm)                   # KL syntactic divergence
  + (0.02 x FWDR_norm)                  # function word density
```

### Normalization of New Metrics

```
MSDD_norm = min(MSDD / 6.0, 1.0)
LCI_norm = min(LCI / 0.40, 1.0)
PTE_norm = min(PTE / 2.5, 1.0)
EVV_norm = min(EVV / 0.60, 1.0)
CER_norm = min(CER / 0.40, 1.0)
W_norm = max(min((W - 10) / 5.0, 1.0), 0)   # 10-15 -> 0-1
MAD_norm = min(MAD / 30.0, 1.0)
LSR_norm = min(LSR / 2.0, 1.0)
VTDE_norm = min(VTDE / 2.0, 1.0)
RPI_norm = min(RPI / 1.8, 1.0)
KLD_norm = min(KLD / 1.5, 1.0)
FWDR_norm = max(min((FWDR - 0.7) / 1.0, 1.0), 0)  # 0.7-1.7 -> 0-1
```

### Interpretation

| SCE_v3 | Label | Goal |
|---|---|---|
| < 0.20 | HUMAN | Ideal target (Turnitin flags nothing) |
| 0.20 - 0.35 | LIKELY_HUMAN | Acceptable |
| 0.35 - 0.50 | UNCERTAIN | Needs reworking |
| 0.50 - 0.75 | LIKELY_AI | Rewriting needed |
| > 0.75 | AI_GENERATED | Deep rewrite |

### Intermediate version (SCE v2, 14 base metrics)

If the 12 Gemini formulas are too complex, use only the first 13 metrics
with the original weightings (sections 1-13 of this file).

### Minimal version (SCE lite, 8 metrics)

```
SCE_lite = (0.20 x (1 - SD))          # semantic density
         + (0.15 x (1 - norm_B))       # burstiness
         + (0.20 x marker_density)     # AI markers
         + (0.10 x SRS)               # structural regularity
         + (0.10 x (1 - SSDI))        # sentence start diversity
         + (0.10 x PAVR)              # passive ratio
         + (0.08 x (1 - DSTM_norm))   # self-corrections
         + (0.07 x (1 - GCPL_norm))   # paragraph Gini
```

Same interpretation grid.

---

## Tier 2 & Tier 3 — Foundation Model Metrics

> **Architecture note (Gemini 3.1 Pro Thinking High):**
> Formulas 1–34 (stylometry, N-grams, POS-tagging) are excellent for rapid Tier 1
> filtering but are vulnerable to advanced prompt engineering. Formulas 35–38 operate
> at the level of **foundation model log-probabilities** and **syntactic graph topology**.
> They require an external inference pipeline and cannot be computed by the evaluating
> LLM itself — but understanding their logic informs exactly how to write text that
> defeats them.
>
> **Calibration warning:** thresholds below are calibrated on a reference architecture
> (LLaMA-3-70B / GPT-3.5 proxy). In a production system, adjust dynamically via a
> classifier (XGBoost or MLP) trained on your own corpus.

---

## 35. Parse Tree Depth Variance (PTDV) — Tier 1 (fast)

**Source: Gemini 3.1 Pro Thinking High**
**Tool: spaCy `en_core_web_trf` or Stanford CoreNLP**

LLMs produce syntactically balanced, regular dependency trees. Humans write
chaotically: a two-word sentence ("Result: nothing.") beside a sentence ten
levels deep with stacked subordinate clauses.

### Formula

```
For a document of S sentences, compute the dependency parse tree T_j for sentence j.
D(T_j) = maximum depth of T_j (longest path from root to leaf node).

μ_D  = (1/S) Σ D(T_j)
σ²_D = (1/S) Σ (D(T_j) − μ_D)²

Note: the branching factor variance (number of children per node) can be
      computed alongside σ²_D as a secondary signal.
```

### Detection Thresholds

| σ²_D | Interpretation | Action |
|---|---|---|
| < 2.5 | AI: all sentences structurally similar — depths like [5, 6, 5, 5, 7, 6] | Add fragments and embedded clauses |
| 2.5 – 4.5 | Grey zone | Check Burstiness Score (Formula 1) jointly |
| > 4.5 | Human: high heterogeneity — depths like [2, 8, 4, 11, 3] | OK |

### Attack Vector

**Technique:** Structural Burstiness Prompting — explicitly request alternation
between sentences of 1–4 words and sentences containing multiple embedded clauses.

**Why it works:** Forcing short (D ≈ 2) sentences next to complex (D ≈ 9–12)
sentences makes each D(T_j) diverge sharply from μ_D. The squared deviations
(D(T_j) − μ_D)² become large, driving σ²_D above the detection threshold.

---

## 36. Real Perplexity — PPL (Cross-Entropy Loss) — Tier 2

**Source: Gemini 3.1 Pro Thinking High**
**Tool: LLaMA-3-8B quantised or GPT-2 XL as proxy — requires a forward pass**

Perplexity measures how much a language model is "surprised" by a token sequence.
AI-generated text sits near the probability distribution's peak → very low perplexity.
Human text uses unexpected transitions → higher perplexity.

### Formula

```
Given token sequence X = (x₁, x₂, ..., xₙ) and language model p_θ:

CE(X)  = −(1/N) Σᵢ log p_θ(xᵢ | x₁, ..., xᵢ₋₁)

PPL(X) = exp(CE(X))
       = exp(−(1/N) Σᵢ log p_θ(xᵢ | x<ᵢ))
```

### Detection Thresholds (proxy model: LLaMA-3-8B or GPT-2 XL)

| PPL | Interpretation | Action |
|---|---|---|
| < 35 | AI: model predicts the sequence easily | Inject rare tokens, unexpected transitions |
| 35 – 65 | Grey zone: heavily edited AI or very academic human | Cross-check with GLTR (Formula 37) |
| > 65 | Human: unexpected transitions present | OK |

### Attack Vector

**Technique:** Replace common words with rare synonyms (thesaurus-based),
introduce deliberate archaisms, or use grammatical structures the model finds
statistically surprising.

**Why it works:** Rare tokens force log p_θ(xᵢ | x<ᵢ) toward a large negative
value (p_θ ≈ 0). This inflates the cross-entropy CE(X), pushing PPL above the
detection threshold.

---

## 37. GLTR Token Rank Ratios — Tier 2

**Source: Gehrmann et al. — Giant Language Model Test Room**
**Tool: any LLM forward pass to extract per-token probability ranks**

GLTR does not look at absolute probability — it looks at the **rank** of the
chosen token in the model's sorted distribution. LLMs sample almost exclusively
from the Top-10. Humans regularly reach into the long tail (Top-1000+).

### Formula

```
For each token xᵢ, let R(xᵢ) = rank of xᵢ sorted by descending probability p_θ(x | x<ᵢ).

Four buckets:
  B₁₀    = {xᵢ : R(xᵢ) ∈ [1, 10]}
  B₁₀₀   = {xᵢ : R(xᵢ) ∈ [11, 100]}
  B₁₀₀₀  = {xᵢ : R(xᵢ) ∈ [101, 1000]}
  B₁₀ₖ₊  = {xᵢ : R(xᵢ) > 1000}

Bucket ratio over sequence of size N:
  F(Bₖ) = (1/N) Σᵢ 𝟙(R(xᵢ) ∈ Bₖ)
  (where 𝟙 is the indicator function: 1 if condition true, 0 otherwise)
```

### Detection Thresholds

| Bucket | AI signal | Human signal |
|---|---|---|
| F(B₁₀)   | > 85% | 65–70% |
| F(B₁₀₀)  | ≈ 12% | 15–20% |
| F(B₁₀₀₀) | < 2%  | ≈ 10%  |
| F(B₁₀ₖ₊) | ≈ 0%  | > 2%   |

### Attack Vector

**Technique:** Generate with high temperature (T > 1.2) and high Top-P
(P > 0.95), or use the prompt: *"Use highly unpredictable vocabulary and
unusual associations of ideas."*

**Why it works:** High-temperature sampling flattens the softmax distribution,
forcing the model to select tokens with rank R > 100. This fills the B₁₀₀₀
and B₁₀ₖ₊ buckets artificially, mimicking human long-tail usage patterns.

---

## 38. DetectGPT Score (Perturbation Discrepancy) — Tier 3

**Source: Mitchell et al., Stanford (2023) — zero-shot detection**
**Tool: T5-large as perturbation model + LLM proxy for log-probability scoring**
**Cost: O(K × N × V) — trigger only when Tier 1+2 score is in the 40–60% zone**

The core hypothesis: AI-generated text sits at a **local maximum** of the
log-probability function. Perturbing it slightly causes a sharp probability drop.
Human text is not at a local maximum — perturbations leave probability stable
or even improve it.

### Formula

```
Given:
  x       = original text
  p_θ     = scoring model (LLM proxy)
  q(·|x)  = perturbation model (T5-large: mask and replace 15% of tokens)
  K       = number of perturbations (recommended: K = 100)

Generate K perturbations: x̃ₖ ~ q(·|x)

Discrepancy:
  d(x) = log p_θ(x) − (1/K) Σₖ log p_θ(x̃ₖ)

Z-score:
  Z(x) = d(x) / σ_x̃
  where σ_x̃ = standard deviation of {log p_θ(x̃ₖ)} over K perturbations
```

### Detection Thresholds

| Z(x) | Interpretation | Action |
|---|---|---|
| > 1.5 | AI: probability drop is statistically significant | Apply Paraphrasing Attack |
| ≈ 0 or < 0 | Human: perturbation does not degrade probability | OK |

### Attack Vector

**Technique:** Paraphrasing Attack. Generate with Claude or GPT-4, then
paraphrase with a radically different model (BART, Quillbot) or manually
rewrite 20% of sentences.

**Why it works:** Paraphrasing moves x off the local maximum of p_θ. Once
displaced, log p_θ(x) drops initially — but subsequent perturbations x̃ₖ no
longer trigger a sharp further drop. The numerator d(x) tends toward 0 and
Z(x) falls below the detection threshold.

---

## 6. Three-Tier Detection Pipeline (Architecture)

> Source: Gemini 3.1 Pro Thinking High

The 38 formulas above map onto a three-tier pipeline that enterprise detectors
implement (Turnitin AI Detection, GPTZero, Compilatio Magister):

| Tier | Complexity | Formulas | Trigger condition |
|---|---|---|---|
| **Tier 1** | O(N) — instant | Formulas 1–34 (surface) + Formula 35 (PTDV via spaCy) | Always |
| **Tier 2** | O(N × V) — 1 forward pass | Formulas 36 (PPL) + 37 (GLTR) — requires GPU proxy | Tier 1 score 30–70% |
| **Tier 3** | O(K × N × V) — 100 passes | Formula 38 (DetectGPT) | Tier 1+2 score 40–60% only |

### Practical implications for students

Tier 1 alone (Formulas 1–35) defeats most institutional detectors currently
deployed in French academia (Compilatio Magister, Unicheck). Turnitin AI
Detection (2023) uses a lightweight Tier 2 pass. GPTZero uses Tier 2 + partial
Tier 3. Defeating Tier 3 requires the Paraphrasing Attack (Formula 38) combined
with genuine student anchoring (Step 0 of the skill).

**The irreducible defence:** a text grounded in lived experience — named
people, specific dates, real version numbers, acknowledged failures — generates
naturally high PPL and healthy GLTR long-tail ratios. No prompt engineering
fully replicates authentic content.

---

## 7. Self-Evaluation Prompt (to give to the LLM)

Copy-paste this prompt with the text to evaluate:

```
You are a text evaluator. Calculate the following metrics on the text
below. Show your calculations step by step.

1. BURSTINESS (B)
   - List the length in words of each sentence
   - Calculate mu (mean) and sigma (standard deviation)
   - Calculate B = (sigma - mu) / (sigma + mu)
   - Verdict: B > 0.3 = human, B < 0 = suspect, B < -0.5 = AI

2. TTR VARIANCE
   - Divide the text into windows of 100 tokens
   - Calculate the TTR of each window
   - Calculate the inter-window variance
   - Verdict: var > 0.06 = human, var < 0.04 = AI

3. CONNECTORS
   - List all connectors and their relative position within the paragraph
   - Calculate Z1 (% at start), Z2 (% in middle), Z3 (% at end)
   - Verdict: Z1 > 80% = AI, Z1 < 60% = human

4. SEMANTIC DENSITY
   - For each sentence: new information (1), development (0.5), filler (0)
   - Calculate SD = sum / number of sentences
   - Verdict: SD < 0.3 = AI (too much filler), SD > 0.5 = human

5. STRUCTURAL REGULARITY
   - List the length of each paragraph
   - Calculate SRS = 1 - mean of relative deltas
   - Verdict: SRS > 0.85 = AI, SRS < 0.70 = human

6. AI MARKERS
   - Count the markers from the blacklist (see below)
   - Density = markers / (words / 500)
   - Verdict: > 4 per 500 words = strong signal

7. HAPAX LEGOMENA
   - Count words that appear exactly 1 time
   - HLR = hapax / total unique words
   - Verdict: HLR > 0.55 = human, HLR < 0.40 = AI

8. SENTENCE START DIVERSITY
   - Classify the 1st word of each sentence (article/pronoun/connector/noun/adverb/verb/number/question)
   - SSDI = categories used / 10, no category > 40%
   - Verdict: SSDI > 0.6 = human, SSDI < 0.4 = AI

9. INTER-PARAGRAPH SIMILARITY
   - For each adjacent pair, estimate semantic similarity (0-1)
   - IPCS = mean
   - Verdict: IPCS < 0.35 = human, IPCS > 0.60 = AI (redundancy)

10. INFORMATIONAL DENSITY VARIANCE
    - Per 100-word segment, count informational elements
    - IEVS = variance of densities
    - Verdict: IEVS > 0.015 = human, IEVS < 0.005 = AI

11. PASSIVE / ACTIVE RATIO
    - PAVR = passive constructions / total clauses
    - Verdict: PAVR < 0.20 = human, PAVR > 0.40 = AI

12. PARAGRAPH GINI
    - Gini coefficient of paragraph lengths
    - Verdict: GCPL > 0.30 = human, GCPL < 0.15 = AI

13. THOUGHT MARKERS
    - Count: well, actually, no wait, asides (), questions ?, uncertainties, trade-offs
    - DSTM = markers / (words / 500)
    - Verdict: DSTM > 3 = human, DSTM = 0 = AI

14. COMPOSITE SCORE v2
    Calculate SCE_v2 with the 14 metrics (or SCE_lite with 8)
    - Verdict: < 0.20 = HUMAN, 0.20-0.35 = LIKELY_HUMAN, > 0.35 = needs work

15. RISK ZONES
    - Identify the most suspicious sentences/paragraphs
    - Suggest concrete corrections for each zone

AI marker blacklist (non-exhaustive):
crucial, fundamental, essential, it should be noted, one cannot help but notice,
furthermore, moreover, additionally, sheds light on, constitutes a, represents a,
fits within, major challenge, leverage, paradigm, holistic, synergy,
ecosystem, in a world of constant change, it is important to note,
enables, consists of, in this context, at this stage, robust, relevant,
nuanced, crystallize, underlying, a myriad of, a delicate balance,
inevitably, orchestrate, tapestry, navigate, dive into.

TEXT TO EVALUATE:
[PASTE TEXT HERE]
```

---

## 8. Complete Self-Evaluation Workflow

```
1. Rewrite the text with natural-writing (48 patterns + Phase 7 + Phase 8)
                    |
                    v
2. Copy the rewritten text + the self-evaluation prompt (section 7)
   into an LLM with extended reasoning
                    |
                    v
3. Read the scores:
   - SCE_approx < 0.25? -> Deliver
   - SCE_approx 0.25-0.40? -> Check risk zones, correct if needed
   - SCE_approx > 0.40? -> Return to step 1 with focus on weak metrics
                    |
                    v
4. Check individual metrics:
   - B < 0? -> Break the rhythm (short + long sentences)
   - TTR_var < 0.04? -> Vary vocabulary (repetitive zones + rich zones)
   - Z1 > 80%? -> Move connectors to mid-sentence
   - SD < 0.3? -> Remove filler, add facts
   - SRS > 0.85? -> Unbalance the paragraphs
   - Markers > 4/500 words? -> Replace using the SKILL.md table
                    |
                    v
5. Re-score after corrections -> Loop until SCE_approx < 0.40
```

---

## 9. Paraphrase Risk Score (PRS)

Modern detectors have a specific category for paraphrased AI text
(AI_LIKELY_PARAPHRASED_OR_HEAVILY_EDITED). This self-evaluation checks whether the
text risks triggering this flag.

### Formula

```
For the rewritten text, verify:
  a) Has the argumentative structure changed compared to the original?
     (not just the words, but the ORDER of arguments, the LENGTH of sections)
     -> structure_changed = 1 if yes, 0 if no

  b) Has new content been added (anecdotes, details, opinions)?
     -> new_content_ratio = new_words / total_words

  c) Has content been removed (filler, redundancies)?
     -> deletion_ratio = 1 - (final_words / original_words)

  d) Has vocabulary been simplified without touching the structure?
     -> vocab_only_change = 1 if identical structure + different words, 0 otherwise

PRS = (0.3 x (1 - structure_changed))
    + (0.3 x (1 - new_content_ratio))
    + (0.2 x (1 - deletion_ratio))
    + (0.2 x vocab_only_change)
```

### Interpretation

| PRS | Risk | Action |
|---|---|---|
| > 0.70 | HIGH: text is just paraphrased, detectable | Restructure, add content, remove filler |
| 0.40 - 0.70 | MODERATE: some structural changes | Add more original content |
| < 0.40 | LOW: text has been substantially reworked | OK |

### What Triggers the Paraphrase Flag in Detectors

- AI argumentative structure preserved under new lexicon
- Regular syntactic skeleton even if words change
- Simplified vocabulary but intact logical architecture
- Same number of paragraphs, same length, same order

### What Avoids It

- Reorganizing the argumentation (inverting order, merging, splitting)
- Adding content the AI did not have
- Deleting content rather than paraphrasing everything
- A shorter but denser text is less suspect

---

## 10. Limits of Self-Evaluation

1. **The LLM does not calculate logprobs.** The perplexity and DetectGPT metrics
   are calculated by the detector's external pipeline. SCE_approx is an
   indirect estimate, not the real score.

2. **The evaluating LLM has its own biases.** Asking Claude to evaluate
   a text rewritten by Claude can introduce bias (too strict or too lenient).
   Use a different model for evaluation when possible.

3. **The thresholds are approximations.** The real thresholds of Compilatio or
   Turnitin are proprietary and calibrated on their own corpora.

4. **A low score does not guarantee undetectability.** Human judgment
   (level mismatch, similarities between submissions, viva questions)
   remains a risk independent of the score.

5. **Self-evaluation is only useful if the student masters their text.**
   A text that passes the metrics but that the student cannot defend
   at the oral examination remains a risk.

6. **Turnitin's real threshold is 0.20.** Below 20%, Turnitin does not
   even surface the score. That is the zone to target: not 0.00 (impossible),
   but < 0.20 (invisible to the teacher).

7. **Our self-evaluation now covers ~90% of the real scoring.** Formulas
   30-33 (LRAD, CDI, EDC, SDR) compensate for external pipeline metrics
   (retrieval, paraphrase_bypass, cross_model_agreement). Formulas 35-38
   document the Tier 2/3 pipeline architecture in full — but the LLM cannot
   compute real log-probabilities or run K perturbations itself. The remaining
   ~10% gap (real PPL, real DetectGPT Z-score) requires API access to a GPU
   proxy. The best compensator remains a text grounded in reality.
