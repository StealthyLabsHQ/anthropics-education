# Natural Writing: Before/After Pairs

> This file is consulted by Claude when producing long text (thesis, report, essay)
> to ensure the output does not trigger AI detectors. Load only if
> the produced content seems too "smooth" or if the student explicitly requests an undetectable text.

---

## Table of Contents

1. Mechanical connectors
2. Sentence structure
3. Typical AI vocabulary
4. Introductions and conclusions
5. Transitions between sections
6. Tone and register
7. Quick checklist

---

## 1. Mechanical connectors

AI chains connectors like a metronome. A human sometimes skips the connector
and lets the logic of the argument carry the link.

| BEFORE (AI) | AFTER (human) |
|------------|---------------|
| Furthermore, the company has implemented a monitoring system. Moreover, this system makes it possible to trace anomalies. In addition, it facilitates monthly reporting. | The company has implemented a monitoring system that tracks anomalies. Monthly reporting also runs more smoothly as a result. |
| First, we will define the concept. Then, we will analyze the field. Finally, we will propose recommendations. | The first section establishes the theoretical framework. Field analysis occupies the second. We close with the recommendations that follow from it. |
| Nevertheless, it should be noted that this approach has limitations. However, it remains relevant in the context studied. | The approach has its limits, but it fits the firm's context. |
| It is important to note that... | [Delete and state the fact directly] |
| It is clear that... | [Delete, if it's an observation the reader will see it] |
| First... second... lastly | [Vary: "To begin with...", then no connector, then "The question of... remains"] |

### Alternative: the varied connector toolbox

Instead of recycling the same ones, draw from here according to the logical relationship:

**Cause:** because, since, due to, given that, the reason is
**Consequence:** hence, so that, which explains, result:, consequently
**Opposition:** yet, except that, despite everything, the fact remains, the problem is that
**Addition:** add to this, another point, one also finds, not to mention
**Illustration:** concrete case:, this is what we observe at, take the example of

Above all: do not put a connector on every sentence. A paragraph of 4 sentences
may contain just one.

---

## 2. Sentence structure

AI produces sentences of regular length (15-20 words each). A human varies.

| BEFORE (AI) | AFTER (human) |
|------------|---------------|
| The automation of accounting processes represents a major challenge for accounting firms. It makes it possible to reduce repetitive tasks. It frees up time for advisory work. It improves data reliability. | Automating accounting processes changes the game for firms. Less data entry. More time for client advisory. And more reliable data (which matters when you're managing 200 files). |
| This approach is part of a continuous improvement logic. The company seeks to optimize its processes. The objective is to gain efficiency. | The idea is simple: do better with the same time. The company reworks its processes one by one, not a complete overhaul, but targeted adjustments that add up. |
| The concept of digital transformation has been defined by several authors. According to Westerman et al. (2014), it refers to the use of digital technologies to improve performance. According to Vial (2019), it is a process that generates disruption. | Westerman et al. (2014) describe digital transformation as using digital technologies to improve performance. Vial (2019) goes further: for him, it is not just an improvement, it is disruption. The distinction matters. |

### Concrete techniques

- **Short sentence after a long one.** The contrast effect draws attention.
- **Start a sentence with "And" or "But".** Grammatically correct and it breaks monotony.
- **Use rhetorical questions** (sparingly). "But is this really applicable in a five-person firm?"
- **Parentheses for asides.** "(which, in practice, never happens quite so smoothly)"
- **Nominal phrases.** "Result: a gain of 3 hours per week." Not always subject-verb-complement.

---

## 3. Typical AI vocabulary

Words and expressions that AI detectors flag. Replace them systematically.

| AI word/expression | Possible replacements |
|-------------------|------------------------|
| crucial | important, key, decisive, central |
| fundamental | basic, at the root of, primary |
| essential (at the start of a sentence) | [rewrite the sentence without this word] |
| it is necessary to | one must, we should, it is better to |
| it is important to note that | [delete, state directly] |
| in the context of | during, in, for, within |
| in terms of | on the side of, regarding, as for |
| enables / enabling | serves to, makes possible, [direct verb] |
| within | in, at, inside |
| is part of | belongs to, connects to, falls under |
| highlights / sheds light on | shows, reveals, brings out |
| a major challenge | a concrete problem, a difficulty, a sensitive point |
| a complex issue | a delicate subject, a question without easy answers |
| a fortiori, moreover, in this instance | all the more so, additionally, here / in this case |
| it is clear that | one can see that, the conclusion is clear |
| ultimately | in the end, to sum up, in short |
| landscape (figurative) | context, situation, environment |
| lever | tool, means, method |
| paradigm (outside philosophical context) | model, framework, logic |
| holistic | global, complete, overall |
| synergy | complementarity, combination, collaboration |
| ecosystem (outside biology) | environment, network, setting |

### General rule

If a word sounds like a McKinsey consulting report, replace it with its
concrete equivalent. "We identified synergies between the teams" → "The
two teams started working together on the same client file."

### AI vocabulary specific to accounting/management

Accounting and management dissertations have their own AI patterns. Detectors flag them
all the more because this vocabulary recurs in ChatGPT-trained material.

| AI word/expression (accounting/management) | Possible replacements |
|-------------------------------------|------------------------|
| tax optimization | reducing the tax burden, choosing a tax regime, filing strategy |
| performance management | tracking results, monthly dashboard, variance analysis |
| value creation | increase in net income, margin improvement, measured productivity gain |
| decision-support tool | dashboard, reporting, tracking file |
| competitive advantage lever | concrete advantage, measurable gain, differentiation on [specific point] |
| digitization of processes | moving from [old tool] to [new tool], automating [specific task] |
| in a context of globalization | [delete or replace with the actual context of the company] |
| supporting transformation | implementing [tool], training teams in [software] |
| optimal resource management | [describe what was actually done with numbers] |

### Tense consistency: work-study dissertations

Work-study dissertations often mix tenses inconsistently, which is a signal of automated writing. Clear rule:

| Section of the dissertation | Tense to use | Example |
|---|---|---|
| Description of the company | Present | "The firm employs 8 staff members" |
| Tasks completed | Simple past or past progressive | "I developed a macro" / "The process used to take 3 hours" |
| Theoretical framework | Timeless present | "According to Bouquin (2010), management control aims to..." |
| Analysis of results | Analytical present | "The results show that..." |
| Recommendations | Conditional or future | "The firm could consider..." |

**Common pitfall:** shifting from past to present in the middle of a task paragraph.
Reread each paragraph checking that the tense is consistent from start to finish.

---

## 3b. In-depth anti-AI filter: humanizer skill

> If the student needs a deeper filter than this checklist (for example to
> rewrite text that has already been produced), the **natural-writing** skill can be loaded as
> a complement: `/mnt/skills/user/natural-writing/SKILL.md` (if installed). It provides
> a full diagnostic, 48 detection patterns, and a two-pass rewrite.

---

## 4. Introductions and conclusions

### Introductions: the pitfalls

| BEFORE (AI) | AFTER (human) |
|------------|---------------|
| In a constantly evolving world, digitalization has become a major challenge for businesses. | ATF Firm handles 200 files a year with the same tools it used ten years ago. The question is no longer whether to digitize, but where to start. |
| Since the beginning of time, humans have sought to optimize their work processes. | [Delete. Never begin a thesis with "Since the dawn of time" or "Throughout history".] |
| Accounting is a field in full transformation. | Accounting is changing: software already does the data entry work that three people used to do five years ago. What remains is analysis, and that is where things get stuck. |

### Conclusions: the pitfalls

| BEFORE (AI) | AFTER (human) |
|------------|---------------|
| In conclusion, this thesis has highlighted the challenges of digital transformation. The prospects are promising and the avenues for improvement are numerous. | The VBA macro divided processing time by four. That is a first step. The next would be to integrate bank feeds directly via API, but that requires an investment the firm is not yet ready to make. The question remains open. |
| Thus, we have been able to demonstrate that... It would be interesting to deepen this reflection in future research. | [Answer the research question concretely, name an honest limitation, pose a question that genuinely extends the topic] |

---

## 5. Transitions between sections

AI pastes in formulaic transitions. A human transitions through meaning.

| BEFORE (AI) | AFTER (human) |
|------------|---------------|
| Having analyzed the theoretical framework, we will now turn our attention to the field. | The theoretical framework establishes the concepts. What remains is to see how they hold up in an eight-person firm in a mid-sized city. |
| This first section has allowed us to understand the foundations. The second section will be devoted to the case study. | [No explicit transition. End Part 1 with a question or tension, open Part 2 with a field-based fact.] |
| We have just seen that... We will now look at... | [Delete. If the outline is logical, the reader follows.] |

### Technique: the tension transition

End a section with an unresolved problem. Open the next with an attempted answer.

> End of Part 1: "...but these theoretical models presuppose large organizations.
> What about a firm with fewer than 10 employees?"
>
> Start of Part 2: "ATF Firm has 8 staff members. Three of them manage
> the bookkeeping for 200 client files on their own."

---

## 6. Tone and register

### Adapting to the document type

| Document | Register | "I" allowed | Humor/informality |
|----------|----------|---------------|-------------------|
| Research dissertation | Formal, impersonal | No ("we" of modesty) | No |
| Professional dissertation | Formal but accessible | Yes, in moderation | Very light, through concrete example |
| Internship report | Standard-formal | Yes, naturally | Possible in personal reflection |
| Essay | Formal | No (unless instructed) | No |
| Revision sheet | Direct, accessible | Not applicable | OK if pedagogical |

### The read-aloud test

Read the text aloud. If a sentence sounds wrong when spoken,
it is too artificial. Rewrite it as you would say it, then
raise the register slightly if needed.

---

## 7. Quick checklist (to run on any text > 300 words)

```
[ ] No more than 2 "Furthermore/Moreover/In addition" connectors in the entire text
[ ] At least 3 sentences of fewer than 10 words
[ ] At least 1 sentence of more than 30 words
[ ] No sentence beginning with "It is important to note that"
[ ] No opening with "In a constantly evolving world"
[ ] No conclusion with "The prospects are promising"
[ ] The word "crucial" does not appear (or maximum 1 time)
[ ] The word "enabling" appears no more than 2 times
[ ] At least 1 numbered or dated example
[ ] The text sounds natural when read aloud
[ ] Visible variation in sentence length
[ ] No mechanical structure (systematic three-part lists, forced parallelisms)
[ ] At least 1 inferential leap (implicit conclusion, not everything spelled out)
[ ] Specific examples with names/places/numbers (no hypothetical examples)
[ ] Slight register variation if the format allows (not uniformly formal)
[ ] "This" / "That": max 2 per page
```
