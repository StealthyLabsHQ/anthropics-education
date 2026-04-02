# Comprehensive Blacklist of AI Markers in English

> **When to load this file:** when the text to humanize does not belong to a specific discipline,
> or in addition to `patterns-by-discipline.md` for a full scan.
> This list groups the most frequent AI markers in English, across all disciplines.

---

## 1. Banned Words and Expressions (removal or replacement mandatory)

These words/expressions are near-certain AI signals when they appear in density.
One or two in a 5-page text is fine. Three or more, and the text gets flagged.

### Category A: Buzzwords and Filler Terms

| AI expression | Why it is a signal | Replacement |
|---|---|---|
| crucial | LLMs' favorite superlative, used 10x more than humans | important, key, decisive (if truly decisive), central |
| fundamental | Same issue, often unjustified | basic, foundational, core (if truly core) |
| essential (as opener) | AI opens 1 sentence in 5 with this word | Rephrase without this word |
| paramount | Variant of crucial/essential, same problem | necessary, indispensable |
| indispensable | AI treats everything as indispensable | necessary, that you cannot do without |
| undeniably | Strong modulator that humans rarely use | clearly, it is a fact, evidently |
| inherently | Philosophical vocabulary used out of context | in itself, by nature |
| catalyst | Overused chemistry metaphor | trigger, what launched it, driver |
| synergy | Pure consultant-speak | collaboration, complementarity, working together |
| paradigm (outside philosophy) | Academic jargon used incorrectly | model, framework, logic |
| holistic | All-purpose new-age term | overall, comprehensive, all-encompassing |
| ecosystem (outside ecology) | Empty metaphor | environment, network, setting |
| resilience (outside psychology) | Post-pandemic catch-all word | durability, robustness, ability to hold |
| disruptive / disruption | Tech anglicism used everywhere | that overturns, brutal change, break |

### Category B: Dead Metaphors and Worn-Out Images

| AI expression | Replacement |
|---|---|
| in a world of constant change | Delete entirely |
| landscape (in constant flux) | context, situation, environment |
| tapestry (figurative) | mix, mosaic |
| navigate (complexity) | manage, deal with, work through |
| orchestrate | organize, coordinate |
| dive into | examine, study, look closely at |
| weave connections | build relationships, work together |
| at the heart of | at the center of, in, (often deletable) |
| cornerstone | foundation, starting point |
| at the forefront | leading, at the front |
| backbone | main structure, core (if anatomy, otherwise "base") |
| at the dawn of | at the start of, at the moment of |
| in the era of | today, now that, since |
| lift the veil on | show, reveal, explain |
| pave the way | enable, make possible |

### Category C: Filler Formulas

| AI expression | Replacement |
|---|---|
| it should be noted that | (delete, just say it) |
| one cannot help but notice that | you can clearly see that, the fact is that |
| it is important to highlight that | (highlight it directly) |
| it is interesting to observe that | (observe it directly) |
| it goes without saying that | (just say it) |
| it is paramount to | you need to, it is necessary to |
| ultimately | in the end, in short |
| in the final analysis | in the end, to sum up |
| in this regard | on this point, (delete) |
| with this in mind | so, therefore, (delete) |
| given the above | given this, considering this |
| as far as X is concerned | for, on |
| it is worth noting that | (delete) |
| one can observe that | (delete) |
| this highlights the fact that | this shows that |

### Category D: Mechanical Connectors

| AI connector | When to replace | Alternative |
|---|---|---|
| Furthermore | When it opens a sentence | (delete), And, Also, Another thing: |
| Moreover | Always | (delete), On top of that (if register allows) |
| Additionally | When it serves just as a transition | (delete), On another note |
| Nevertheless | When there is more than one per page | But, Except that, Still |
| However | Same | Yet, Except that, The problem is that |
| On the other hand | Acceptable but no more than 1 per page | But, In contrast |
| Yet | AI signal when repeated | But, Still, Though |
| Thus | When mechanically opening a conclusion | So, As a result, The outcome: |
| Indeed | More than 1 per page = signal | Because, Since, The thing is |
| In this sense | Strong AI style signal | (delete), For this reason |

**Key rule:** a 4-sentence paragraph can contain no connectors at all.
The logic of the content makes the link. Connectors are not mandatory.

### Category E: "To Be" Substitution Verbs

AI avoids the verb "to be" and replaces it with more "elevated" verbs.

| AI verb | When it is a signal | Replacement |
|---|---|---|
| constitutes | "X constitutes a Y" = near-certain signal | is |
| represents | "X represents a Y" = same | is |
| embodies | Outside literary/theatrical context | is, shows, illustrates |
| proves to be | Redundant (proves = is revealed to be true) | is, turns out to be |
| fits within | "This approach fits within..." | is part of, falls under |

---

## 2. Syntactic Structures Flagged by Detectors

### 2.1 The Systematic Triad

AI almost always enumerates in threes. Two or four, almost never.

**Signal:** "productivity, quality, and client satisfaction"
**Fix:** develop each point, or enumerate in twos, or in fours.

### 2.2 The Negative Parallelism

**Signal:** "It is not just about X, but also/above all about Y"
**Fix:** say directly what you want to say.

### 2.3 The Universal Opening Sentence

**Signal:** "In a world of constant change...", "Nowadays...",
"Since time immemorial...", "In the age of globalization..."
**Fix:** start with the concrete, the field, the case.

### 2.4 The Accumulation of Present Participles

**Signal:** "...allowing... ensuring... enabling..."
**Fix:** replace each -ing participle with a concrete mechanism using subject-verb.

### 2.5 The Vague Optimistic Conclusion

**Signal:** "The prospects are promising", "The future looks..."
**Fix:** conclude with something concrete (what remains to be done? what did not work?).

---

## 3. Pronoun and Tone Markers

### 3.1 Overuse of "this" and "that"

LLMs use "this" and "that" 3 to 4 times more than the average human writer. This is a
strong statistical signal that detectors measure.

**Before:**
> This shows that digitalization has an impact. This confirms the conclusions of
> the previous study. This also raises questions.

**After:**
> Digitalization has a measurable impact. The previous study reached the same
> conclusion. One question remains open.

**Rule:** maximum 2 uses of "this/that" as subject per page. Replace with the real subject or rephrase.

### 3.2 Absence of "I" (when format allows it)

In a professional thesis, an internship report, a cover letter, the absence
of "I" is an AI signal. AI produces impersonal text by default.

### 3.3 Excessively Neutral Tone

A real author has a point of view. They show a slight preference, an acknowledged scepticism,
a surprise. AI remains neutral and equidistant. Detectors measure this constant
neutrality via sentiment analysis.

**Before (AI neutral):**
> The tool has advantages and disadvantages.

**After (human perspective):**
> Pennylane does invoice collection well, but its review module is frustrating.

---

## 4. Invisible Statistical Signals

These signals are not visible to the naked eye but LLM detectors measure them.

### 4.1 Low Perplexity

The text is composed of "obvious" words at every position. Every word is the one an
LLM would have predicted. Solution: precise words, proper nouns, numbers, non-standard phrasing.

### 4.2 Low Burstiness

All sentences are the same length and complexity. Solution: alternate
between 3-5 word sentences and 30+ word sentences. Aim for a standard deviation > 8 words.

### 4.3 Low Type/Token Ratio

The text recycles the same words. Solution: field technical vocabulary, trade
jargon, hapax (words that appear only once).

### 4.4 Constant Entropy

The text maintains uniform informational density. Solution: alternate dense
passages (quantified analysis) and lighter passages (anecdote, aside, question).

### 4.5 Predictable Token Distribution

At every position, the word is the one in the LLM's top-3. Solution: vary sentence
beginnings, place unexpected information in a strong position.

### 4.6 Calibrated Length (Claude Sonnet 4.6 signal)

AI texts have a length that always seems "just right": neither too short nor too
long. This is itself a signal. A human sometimes produces a paragraph that is too long,
a section that is too short, a rushed conclusion, or an introduction that drags.
AI calibrates everything perfectly, which is paradoxically suspicious.

---

## 5. Quick Checklist - 15 Signals to Scan

```
[ ] "Crucial" / "fundamental" / "essential" as opener: 0 occurrences
[ ] "Furthermore" / "Moreover" / "Additionally": max 2 in the entire text
[ ] "It should be noted" / "One cannot help but notice": 0
[ ] "In a world of constant change": 0 (disqualifying)
[ ] "This/That" (as subject): max 2 per page
[ ] Triads (X, Y, and Z): max 2 per page
[ ] Em dashes: 0 ideally, max 2 per page
[ ] All sentences between 15-20 words (no variation): NO
[ ] All paragraphs the same length (+-20%): NO
[ ] No example with a specific name/number/place: NO
[ ] No "I" in a format that allows it: NO
[ ] Uniformly formal register without variation: NO
[ ] Every step of reasoning explicitly connected: NO
[ ] Hypothetical examples ("Imagine..."): 0
[ ] Vague optimistic conclusion: NO
```

If more than 5 boxes are checked as "signal," the text needs a deep rewrite.

---

## 6. How to Use This File

1. **Scan the text** with the quick checklist (section 5).
2. **Identify the dominant categories** (A-E in section 1) and replace.
3. **Check syntactic structures** (section 2).
4. **Monitor tone and pronouns** (section 3).
5. **Cross-reference with statistical signals** (section 4) for difficult cases.
6. **If the text belongs to a specific discipline**, complement with `patterns-by-discipline.md`.

---

## 7. RLHF Signals (source: Gemini 3.1 Pro, self-analysis)

These signals come directly from Gemini 3.1 Pro's self-analysis of how
it detects its own texts. They are particularly relevant because they describe
the structural biases of RLHF training.

### 7.1 The Neutrality/Benevolence Bias

AI is trained to be objective, cautious, and harmless. Result:
- Always presents "both sides"
- Stacks modifiers ("It would seem that," "One might consider that")
- Never uses sarcasm, frustration, contempt, or marked slang
- On a controversial topic, stays perfectly polite and balanced

**Signal:** if the text takes no position, it is probably AI.

### 7.2 The Hourglass Structure

Rigid schema inherited from RLHF:
1. Restatement of the question + plan announcement
2. Numbered body with smooth transitions
3. Synthetic summary + moralizing or balanced opening

**Signal:** a human is rarely this disciplined in their structure.

### 7.3 Universal-Audience Filler

AI writes for everyone, so it redefines terms that the target reader
already knows. A human who knows their audience gets straight to the point.

**Signal:** unnecessary contextualization sentences at the start of sections.

### 7.4 Absence of "Perplexity Peaks"

AI is mathematically consistent in its quality. No strange word, no
clumsy phrasing, no sudden obscure cultural reference.

**Signal:** a text without any linguistic roughness.

---

## 8. ChatGPT 5.4 Signals (technical self-analysis)

ChatGPT 5.4 provided a self-analysis with precise frequency multipliers
and signals not covered by Gemini or Claude.

### 8.1 GPT Language Tics with Relative Frequencies

These words/expressions are used by GPT at N times the frequency of
an average English writer (ChatGPT 5.4 own estimates):

| Expression | Multiplier vs human | Category |
|---|---|---|
| "in this context" | 5-9x | Framing |
| "from this perspective" | 5-10x | Framing |
| "it is not about X but about Y" | 6-10x | Discriminating structure |
| "enables" | 5-8x | Catch-all verb |
| "on one hand... on the other hand" | 5-8x | Symmetric structure |
| "consists of" | 4-7x | "To be" substitution verb |
| "it is a question of" | 4-7x | Framing |
| "put in place" | 4-6x | Catch-all verb |
| "at this stage" | 4-8x | Transition |
| "more precisely" | 4-7x | Meta-discursive precision |
| "in practice" | 4-6x | Transition |
| "however" | 3-6x | Connector |
| "take into account" | 3-5x | Catch-all verb |
| "in other words" | 3-5x | Reformulation |
| "robust" | 3-5x | Technical adjective |
| "not only... but also" | 3-6x | Symmetric structure |
| "nuanced" | 3-6x | Meta-discursive |
| "on the other hand" | 3-5x | Connector |
| "relevant" | 2-4x | Meta-discursive |
| "that said" | 2-4x | Transition |

### 8.2 Deep Structural Signals

- **Absent micro-revisions**: AI does not self-correct while writing. No "well,"
  "actually," "no wait." Strong signal of AI text.
- **Paraphrastic redundancy**: two adjacent sentences that say the same thing
  in different words (LLM safety mechanism).
- **High correctness + low individuality**: grammatically perfect text but
  without any personal imprint (tics, preferences, distinctive punctuation).
- **Absence of cognitive cost**: the text presents a "finished product" with no trace
  of trade-offs, hesitations, or imperfect choices. The hardest signal to
  bypass, according to GPT itself.

### 8.3 Main Flaw (self-diagnosis)

GPT produces the most **false positives** on very clean human texts: consultants,
lawyers, high-level support, doctoral students who compress their voice, non-native speakers.
It produces the most **false negatives** on LLM texts post-edited by someone who
cuts transitions, adds situated details, breaks symmetry, and leaves some
roughness. That is exactly what the natural-writing skill does.

---

## 9. Gemini 3.1 Pro Thinking Signals (self-analysis with extended reasoning)

Thinking mode in Gemini radically modifies its textual topology compared
to standard generation. The self-analysis reveals signals that direct-generation models cannot identify.

### 9.1 Specific Gemini Thinking Tics

| Expression | Multiplier | Specificity |
|---|---|---|
| "crystallize" (outside chemistry) | 4x | Abstraction closure |
| "inherently" | 5x | Depth simulation |
| "underlying" | 4x | Analytical crutch |
| "in the background" | 3x | Causality-free link |
| "a myriad of" | 6x | Quantification avoidance |
| "fits into a dynamic" | 4x | Illusion of temporal movement |
| "catalyst" | 5x | Substitute for "cause" |
| "a delicate balance" | 6x | Neutrality signature facing a dilemma |
| "in light of" | 5x | Comparative evaluation |
| "dichotomy" | 4x | Over-intellectualization |
| "inevitably" | 3x | Forced conclusion |
| "orchestrate" | 4x | Lexical triangle (with "shape" and "nuanced") |
| "leverage" | 4x | Smoothing of complex sentences |
| "stands as" | 3x | Smoothing |
| "underscore" | 3x | Substitute for "highlight" |

### 9.2 The 5 Structural Biases of Thinking Mode

1. **Pre-emptive concession**: counter-arguments integrated as subordinate clauses in
   the same sentence as the thesis. Artificial syntactic density.
2. **Symmetric exhaustiveness**: 3 advantages = exactly 3 disadvantages of the same
   lexical weight and grammatical complexity.
3. **Meta-analytical pivot**: systematic shift from describing a phenomenon to
   analyzing its conceptual framework. Artifact of the prior reasoning phase.
4. **Total absence of cognitive friction**: having already reasoned, the generation
   is a transcription of an already-resolved logical graph.
5. **Extreme tonal variance flattening**: extreme smoothing filter that prevents
   any rise in emotional intensity.

### 9.3 Isotopic Persistence (unique Gemini Thinking signal)

This is the subtlest signal identified by all the self-analyses.
Because thinking mode builds a complete resolution tree before writing,
metaphorical semantic fields remain mathematically aligned across the entire text.
A human forgets their own metaphors or mixes them up.

**Test:** if a text uses a coherent semantic field (e.g.: thermodynamics,
architecture, biology) for more than 2 paragraphs without a break, it is probably
a pre-calculated text.

### 9.4 False Positives / False Negatives

- **False positives**: researchers in social sciences (sociology, philosophy) with a
  naturally rigid thesis-antithesis-synthesis dialectic; institutional or SEO writers.
- **False negatives**: AI texts with deliberate register collisions, subtle
  typographic errors (omitted space), niche cultural references
  that short-circuit perplexity heuristics.

---

## 10. Reconstructed Detection Prompt (what detectors ask LLMs)

Gemini 3.1 Pro reconstructed the complete system prompt that a service like Compilatio
would send to an LLM to detect AI text. Key metrics:

| Metric | What it measures | How to counter it |
|---|---|---|
| Perplexity | Token predictability | Precise words, proper nouns, numbers, non-standard phrasing |
| Burstiness | Rhythmic variance | Alternate 3-5 word and 30+ word sentences |
| Semantic density | Factual info vs filler | Remove filler, add facts |
| Structural entropy | Plan predictability | Unbalance sections, insert digressions |

### Scoring Thresholds

- 0-20% = HUMAN (authorial voice, digressions, high variance)
- 21-40% = ASSISTED (spell checker, occasional rephrasing)
- 41-60% = MIXED (AI/human co-writing, post-edited translation, or very formulaic author)
- 61-80% = AI_EDITED (AI first draft, manually edited)
- 81-100% = AI_GENERATED (raw AI)

The goal of the skill is to produce a text that scores 0-40%.

### English AI Writing Patterns Detected by Gemini

| AI-sounding phrasing | A real writer would say |
|---|---|
| "deliver a result" | produce / provide a result |
| "leverage synergies" | work together / combine resources |
| "operationalize" | put into practice / implement |
| "circle back" | follow up / revisit |
| "going forward" | from now on / in the future |
| "ideate" | brainstorm / come up with ideas |
| "at the end of the day" | ultimately / in practice |
| "drill down into" | examine closely / dig into |
| "move the needle" | make a difference / improve things |
| "bandwidth" (figurative) | capacity / time / availability |

---

## Sources

- Internal analysis of LLM output patterns in English (Claude, GPT, Gemini)
- Gemini 3.1 Pro, self-analysis of AI detection signals (2026)
- Claude Opus 4.6, self-analysis of output patterns (2026)
- Claude Sonnet 4.6, self-analysis of detection signals (2026)
- ChatGPT 5.4, technical self-analysis with frequency multipliers (2026)
- Gemini 3.1 Pro Thinking, self-analysis with extended reasoning (2026)
- Turnitin, "Detecting ChatGPT / Generative AI text"
- Field feedback from teachers and evaluators (human detection signals)
