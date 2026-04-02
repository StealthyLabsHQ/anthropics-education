---
name: natural-writing
description: >
  Transforms AI-generated text into text indistinguishable from human writing. Trigger whenever
  the user mentions: humanize, make it sound natural, anti-detection, anti-AI, "it sounds fake",
  "it sounds like ChatGPT", "my professor will see it's AI", rewrite, rephrase, "too polished",
  "too perfect", "lacks personality", AI filter, de-AI-ify, "make it human", AI plagiarism,
  AI detector, Turnitin, Compilatio, GPTZero, "style too clean", "sounds like a robot".
  Also trigger when a text submitted for review displays obvious AI patterns.
  ALWAYS use this skill for any rewriting request aimed at making a text more natural
  or undetectable as AI.
version: 1.1.0
---

# Natural Writing - AI Rewriting Engine

## Core Principle

A well-humanized text is not simply a text from which AI patterns have been removed.
It is a text into which **a real voice has been injected**.

Removing patterns is necessary but not sufficient. The ultimate goal is for a professor,
recruiter, or peer to read the text and think: "this person thinks and writes."

Two texts can be grammatically perfect, factually correct, and well-structured -
one sounds like a machine, the other like a human being. The difference comes down to
dozens of micro-signals: sentence rhythm, the choice of a concrete word over an abstract
one, an acknowledged hesitation, a lived example, a parenthetical remark that betrays
thinking in progress. This skill systematically tracks artificial signals and
replaces them with these human micro-signals.

**Cardinal rule**: never mention that the text has been "humanized," "rewritten
to seem human," or "cleaned of AI patterns." The final text must contain no trace
of this process. It should simply *be* a good text.

---

## Step 0 - Quick Diagnostic (MANDATORY)

Before any rewriting, scan the text and count:

| Signal to look for | Alert threshold |
|---|---|
| Em dashes (— or –) | > 0 anywhere in the text |
| "Furthermore" / "Moreover" / "Additionally" | > 1 per paragraph |
| Triads (X, Y and Z) | > 2 per page |
| Empty superlatives (crucial, fundamental, essential, major) | > 3 per page |
| Present participles in -ing (allowing, ensuring, enabling) | > 3 per paragraph |
| Sentence length variance (if all between 15-20 words) | Red flag |
| "It should be noted that" / "One cannot help but notice" | > 0 |
| "In a world of constant change" | > 0 (disqualifying) |
| Bulleted lists with bold headers | > 1 per section |
| Complete absence of first person (when format allows it) | Red flag |
| Recurring AI vocabulary (cf. Phase 2 list) | > 5 per page |
| Formulaic opening sentences | > 0 |
| Over-explicit reasoning (every step detailed without any inferential leap) | Red flag |
| Generic/hypothetical examples ("Imagine a company X") | > 0 |
| Uniformly formal register without variation | Red flag |
| Systematic neutrality / "pros and cons" without taking a stance | Red flag |
| Hourglass structure (intro/announced plan/symmetrical body/recap conclusion) | Red flag |
| Universal-audience filler (redefining obvious terms) | > 0 |
| Absence of inline micro-revisions (well, actually, no wait) | Red flag |
| Paraphrastic duplicates (same idea rephrased twice) | > 1 per page |
| Text too correct without personal idiolect | Red flag |
| No trace of cognitive cost (trade-off, hesitation, imperfect choice) | Red flag |
| Persistent metaphorical isotopy (same semantic field across > 2 paragraphs) | Red flag |
| Pre-emptive concessions built in (thesis + antithesis in the same sentence) | > 1 per page |
| Constant tone without any rise in intensity | Red flag |

### Score Calculation

Add up the total number of occurrences detected.

| Score | Level | Action |
|---|---|---|
| 0-3 | Light | Targeted touch-ups, the text is already close to natural |
| 4-8 | Moderate | Partial rewriting, several paragraphs need reworking |
| 9+ | Deep rewrite | The text needs to be fundamentally rethought |

**Always display the diagnostic to the user before rewriting.**

Diagnostic format:

```
NATURAL WRITING DIAGNOSTIC
═══════════════════════════
Score: [X] → [Light / Moderate / Deep rewrite]

Details:
  - Em dashes: [n]
  - Mechanical connectors (Furthermore, Moreover...): [n]
  - Triads: [n]
  - Empty superlatives: [n]
  - Superficial -ing participles: [n]
  - Sentence variance: [OK / Low]
  - Clichéd phrases: [list]
  - AI vocabulary: [list of detected words]
  - Neutrality bias: [Yes / No]
  - Hourglass structure: [Yes / No]
  - Universal-audience filler: [n sentences]
  - Inline micro-revisions: [Present / Absent]
  - Paraphrastic duplicates: [n]
  - Personal idiolect: [Present / Absent]
  - Visible cognitive cost: [Yes / No]

Dominant patterns: [the 3 main problems]
```

---

## Phase 1 - Content Patterns

### Pattern 1: Inflation of Importance

AI tends to inflate the importance of everything it describes. Every event
"marks a turning point," every innovation is "revolutionary," every trend
"fundamentally transforms."

**Before:**
> The introduction of pay-as-you-earn tax collection marked a decisive turning point in
> the history of taxation, fundamentally transforming the relationship between
> the taxpayer and the tax authority.

**After:**
> Pay-as-you-earn tax collection, which came into force in January 2019, changed how tax is
> collected: the employer now remits directly, rather than the taxpayer paying with a year's
> delay. In practice, it mostly simplified things for employees - but complicated life for
> payroll managers.

**Rule**: state the fact simply. If it is truly important, the reader will see it
without being told.

### Pattern 2: Excessive Name-Dropping

AI lists sources, authors, or institutions to give an impression of seriousness,
but without contextualizing them or connecting them to the argument.

**Before:**
> Many authors, including Porter (1985), Mintzberg (1994), and Drucker (2001),
> have emphasized the importance of strategy in corporate competitiveness.

**After:**
> Porter laid the groundwork with the value chain in 1985; thirty years later, the
> model still holds, but it assumes an integrated company - which no longer matches
> the reality of many SMEs that outsource almost everything.

**Rule**: only cite what serves the argument. One well-used reference is worth more
than three names dropped in passing.

### Pattern 3: Superficial -ing Analyses

The present participle is AI's favorite refuge when it wants to give the illusion of
depth without explaining anything. "Allowing... ensuring... enabling..." - these
constructions never explain *how*.

**Before:**
> Automating accounting processes improves productivity, enabling better resource
> allocation and ensuring greater reliability of financial data.

**After:**
> When bank reconciliation runs automatically, the staff member who used to spend
> two hours per client on it can devote that time to analysis. The risk of data
> entry error disappears - and with it, the hours lost hunting down where that
> 12-cent discrepancy came from at month-end.

**Rule**: replace every -ing with a concrete mechanism. If you cannot explain
*how*, the sentence is saying nothing.

### Pattern 4: Promotional Language

AI writes like a marketing brochure. Everything is "at the heart of," the expertise
is always "rich," the dynamic is "positive," the approach is "innovative."

**Before:**
> At the heart of the transformation strategy, the firm bets on an innovative
> and dynamic approach, leveraging its rich heritage of expertise to guide its
> clients through their modernization journey.

**After:**
> The firm chose to start with supplier invoice digitization, because that is where
> the volume is highest and the return on investment is fastest.

**Rule**: replace promotional adjectives with facts. If the firm is truly innovative,
show what it does - don't just say so.

### Pattern 5: Vague Attributions

"Experts agree..." "According to several studies..." "It is widely recognized that..." -
when AI cannot cite a precise source, it invents a vague authority.

**Before:**
> According to several recent studies, the digitalization of accounting firms is a
> key factor in their long-term viability.

**After:**
> The annual survey by the Institute of Chartered Accountants (2023) shows that 34% of
> firms with fewer than 10 employees have not yet digitized their production process.

**Rule**: either you have the source and cite it precisely, or reformulate as an
acknowledged opinion ("I think..." "It seems to me...") or as a field observation.

### Pattern 6: Formulaic "Challenges and Prospects" Section

AI almost always ends with a paragraph on "challenges" (minimized) followed by
a note of optimism (maximized). It is a recognizable tic from ten feet away.

**Before:**
> Despite the challenges related to resistance to change and investment costs,
> the future looks promising for firms that know how to adapt to new technologies.

**After:**
> The main obstacle at the Leroy firm is not budget - it is time. Testing Dext or
> Xero takes hours nobody has during tax season. The solution chosen was to
> dedicate one staff member to the tool during June, when activity slows down.
> Did it work? Partially. The software is running, but half the team still does not use it.

**Rule**: difficulties deserve to be described with the same precision as successes.
A real professional thesis shows what did *not* work too.

---

## Phase 2 - Language Patterns

### Pattern 7: AI Vocabulary

AI in English has a restricted and repetitive lexicon. The words below, taken
individually, are perfectly correct - but their accumulation is a strong signal.

#### Replacement Table

| AI word / expression | Natural replacement(s) |
|---|---|
| Furthermore | ∅ (delete) / And / Also |
| Moreover | ∅ / On top of that (if register allows) |
| Additionally | ∅ / Another thing: / On a different note |
| Crucial | Important / Key / Decisive (if truly decisive) |
| Fundamental | Basic / Core / Central |
| Essential | Necessary / Indispensable / Something you can't do without |
| In terms of | For / On the side of / Regarding |
| Within the framework of | During / For / As part of |
| Within | In / At / Inside |
| Is part of | Belongs to / Falls under / Relates to |
| Sheds light on | Shows / Reveals / Makes visible |
| Major challenge | Problem / Issue / Difficulty / Subject |
| Lever | Tool / Means / What makes it possible to |
| Paradigm | Model / Framework / Way of thinking |
| Holistic | Overall / Comprehensive / All-encompassing |
| Synergy | Collaboration / Complementarity / Working together |
| Ecosystem (outside ecology) | Environment / Network / Setting |
| Constitutes a | Is a |
| Represents a | Is a |
| It should be noted | You need to / One must / It is better to |
| One cannot help but notice | You can clearly see that / The fact is that |
| In a world of constant change | ∅ (delete entirely) |
| Proves to be | Is / Turns out to be |
| Plays a predominant role | Matters a lot / Carries weight / Has real impact |
| Is the subject of | Undergoes / Receives |
| Significantly | Greatly / Clearly / Genuinely |
| Aims to | Seeks to / Wants to / Has the goal of |
| Impactful | That affects / That changes / That touches |
| Resilience (outside psychology) | Durability / Ability to hold / Robustness |
| Proactive | Anticipatory / Getting ahead of things |
| Stakeholder | Relevant party / Person involved |
| Optimize | Improve / Make more efficient |
| Drive (performance) | Track / Manage / Monitor |
| Tapestry (figurative) | Mix / Mosaic / Patchwork (if register allows) |
| Navigate (complexity) | Manage / Deal with / Work through |
| Orchestrate | Organize / Coordinate / Set up |
| Dive into | Examine / Study / Look closely at |
| It is paramount to | You need to / It is necessary to |
| Ultimately | In the end / To put it briefly / To sum up |
| Landscape (figurative) | Context / Situation / Environment |
| Undeniably | Clearly / It is a fact / ∅ |
| Inherently | In itself / By nature / Fundamentally |
| Catalyst | Trigger / What launched it / Driver |
| Lens (figurative) | Angle / Viewpoint / Through the lens of |
| Both... and... (as opener) | ∅ (reformulate without this structure) |
| In light of | According to / Based on / Depending on |
| Highlight (that) | Say / Show / Point out / ∅ |
| Shape | Build / Influence / Modify |
| Testify to | Show / Reveal / Prove |
| In a world where | ∅ (delete entirely, variant of "constant change") |
| Consists of (4-7x) | Is / Amounts to / Means |
| In this context (5-9x) | ∅ / Here / In this case |
| At this stage (4-8x) | ∅ / For now / At this point |
| More precisely (4-7x) | ∅ / That is / Concretely |
| Take into account (3-5x) | Include / Count / Factor in |
| Robust (outside technical) (3-5x) | Solid / Reliable / That holds up |
| Relevant (2-4x) | Appropriate / Useful / That fits |
| Nuanced (3-6x) | Measured / Balanced / Not clear-cut |
| Enables (5-8x) | Is used to / Makes possible / [direct verb] |
| It is a question of (4-7x) | It is / We are talking about / The issue is |
| The key point is as follows | ∅ (just say it) |
| The problem is not so much X as Y | Rephrase without this structure |
| The real difficulty is that | ∅ / The problem is that |
| Crystallize (outside chemistry) (4x) | Fix / Summarize / Concentrate |
| Underlying (4x) | Behind / Hidden / Below the surface |
| In the background (3x) | Behind everything / Quietly / Behind all this |
| A myriad of (6x) | Many / Dozens of / [precise number] |
| Fits into a dynamic (4x) | Is part of / Follows the trend |
| Inevitably (3x) | Necessarily / Of course / ∅ |
| A delicate balance (6x) | A compromise / A tension / A trade-off |
| Dichotomy (4x) | Opposition / Split / Choice between |
| Stands as (3x) | Is seen as / Appears to be / Seems |
| Leverage (4x) | Use / Benefit from / Exploit |
| Underscore (3x) | Highlight / Show / Point to |

*Multipliers (e.g. 5-8x) indicate the frequency of use by LLMs
relative to the average human writer, based on self-analysis.*

**Rule**: none of these words are forbidden. But if the text contains more than five
per page, it is a signal. Vary, concretize, simplify.

### Pattern 8: Avoidance of the Verb "To Be"

AI systematically replaces "is" with more "elevated" verbs: constitutes,
represents, embodies, illustrates. In natural English, "to be" is the most
common verb - and that is perfectly fine.

**Before:**
> Management accounting constitutes an indispensable tool that represents a pillar
> of modern business management.

**After:**
> Management accounting is a management tool. It tells you how much each activity
> actually costs - and therefore where the company makes or loses money.

**Rule**: do not shy away from "to be." It is often the clearest choice.

### Pattern 9: Negative Parallelisms

AI loves the structure "It is not just about X, but also/above all about Y."
It is a recognizable rhetorical tic.

**Before:**
> It is not just about automating tasks, but about fundamentally rethinking
> how work is organized.

**After:**
> Automating tasks is not enough if the organization stays the same. The real
> question is deciding who does what once the software handles data entry.

**Rule**: say directly what you mean, without the double structure.

### Pattern 10: The Systematic Rule of Three

AI almost always enumerates in threes: "productivity, quality, and customer satisfaction";
"innovate, collaborate, and adapt." Two or four, almost never.

**Before:**
> This approach improves productivity, quality, and customer satisfaction.

**After:**
> In practice, production timelines have come down - and clients get their financial
> statements sooner. On the quality front, it is more nuanced: fewer data entry errors,
> but the analytical review is still manual.

**Rule**: break triads. Enumerate in twos, in fours, or better - develop each
point separately.

### Pattern 11: Excessive Synonym Variation

AI avoids repeating a word by replacing it with a near-synonym at each occurrence.
A firm becomes "the organization," then "the entity," then "the advisory office."
In academic English, repeating a technical term is not only acceptable
but desirable for clarity.

**Before:**
> The firm implemented a new tool. This organization trained its staff.
> The entity noted a significant improvement in its productivity.

**After:**
> The firm launched Xero in September. Three months later, the four
> staff who use it handle an average of 15 more files per month. The
> two who have not yet adopted it say they lack time to get trained.

**Rule**: call a spade a spade. Repeat the right word rather than searching for a synonym
that muddles the reading.

### Pattern 12: False Scales

AI produces enumerations that sound good but say nothing: "from diagnosis
to implementation, from strategy to operations, from theory to practice."

**Before:**
> From initial diagnosis to final implementation, from strategic thinking to
> operational action, this thesis covers the entire process.

**After:**
> This thesis describes the three stages of the project: tool selection (September),
> configuration (October-November), and the first two months of use (December-January).

**Rule**: replace scales with a factual description of what is actually covered.

---

## Phase 3 - Style Patterns

### Pattern 13: Excessive Em Dashes

The em dash (— or –) is AI's favorite punctuation mark. A humanized text should contain none. Systematically replace with a comma, a period, parentheses, or a rephrasing.

**Before:**
> Digitalization - which affects all sectors - forces firms - large and small alike -
> to rethink their processes - or risk losing competitiveness.

**After:**
> Digitalization affects all sectors, including small firms. Those who fail to rethink
> their processes risk losing clients to better-equipped competitors.

**Rule**: maximum two em dashes per page. Prefer commas, parentheses, or simply
split the sentence in two.

### Pattern 14: Mechanical Bolding

AI bolds every word it considers important. The result: a page where everything
is underlined, so nothing stands out.

**Rule**: in a thesis or report, bold is reserved for headings and subheadings.
In the body text, it is exceptional - one or two words per chapter, no more.
When in doubt, remove all bold from body text.

### Pattern 15: Bulleted Lists with Bold Headers

This is the AI "blog post" format:
- **First point:** explanation of the first point
- **Second point:** explanation of the second point
- **Third point:** explanation of the third point

In academic or professional text, convert to prose. Bulleted lists are acceptable
for short factual enumerations (software list, dates, steps), but not for developing ideas.

**Rule**: if each bullet runs more than one line, it is a disguised paragraph.
Turn it into a paragraph.

### Pattern 16: Title Case in Headings

AI sometimes produces headings in Title Case: "The Challenges Of Digital Transformation."
In standard academic English, sentence case is typically preferred unless following a specific house style.

**Preferred**: "The challenges of digital transformation"

**Rule**: apply consistent capitalization conventions. Inconsistent or unnecessary Title Case
is an AI signal that careful readers notice.

### Pattern 17: Emojis

In academic or professional text, no emojis. Ever. Even in professional emails,
caution is warranted.

**Rule**: remove all emojis. Without exception in theses, reports,
dissertations, and cover letters.

### Pattern 18: Quotation Marks and Typography

AI often mixes straight quotes (""), and curly double quotes (""). In standard English prose:

- Double curly quotes " " for quotations
- Single quotes ' ' for quotations within quotations
- Never straight quotes in a final text
- Never French guillemets « »: these immediately reveal a non-English origin

Other typography points:
- Em dash without spaces in American style (like this—see). British English uses a spaced en dash (like this – see), but never the French convention of a spaced em dash.
- Ellipsis: three dots as a single character (…) rather than three separate periods (...)
- **No space before punctuation**: in English, no space before `:`, `;`, `?`, `!`. This is a direct French interference error: French requires a non-breaking space before these marks, English does not.
- Period and comma go **inside** closing quotation marks in American English: "like this." Not outside: "like this".

**Rule**: verify typography consistently. A text with mixed quotation styles or French spacing habits
betrays foreign-language influence and is flagged by careful readers and detectors alike.

---

## Phase 4 - Communication Patterns

### Pattern 19: Chatbot Artifacts

These are the most obvious traces of a text copy-pasted from a chatbot without
proofreading:

- "I hope this helps!"
- "Feel free to ask if you have any other questions."
- "Here is an example of..."
- "Of course! Here is..."
- "I'd be happy to help you with..."

**Rule**: remove entirely. If these phrases appear in a text submitted for
humanization, it signals the text had no proofreading - plan a deep rewrite.

### Pattern 20: Knowledge Disclaimers

AI protects itself with cautious phrasing that never appears in a real
thesis or report:

- "To the best of my knowledge..."
- "It is difficult to say with certainty..."
- "Available information suggests that..."
- "It is important to note that I am not an expert in..."
- "Based on the data available to me..."

**Rule**: remove. In a thesis, the author is expected to know their subject. If
information is uncertain, say so differently: "Data on this point is scarce"
or "No study has measured this effect precisely."

### Pattern 21: Servile Tone

AI compliments the user and adopts a customer service tone:

- "Excellent question!"
- "You are absolutely right!"
- "This is a fascinating topic!"
- "Thank you for this relevant question."

**Rule**: these formulations have no place in academic text. If they appear,
the text is a raw chatbot copy-paste. Remove and flag for the user.

---

## Phase 5 - Filler and Coverage

### Pattern 22: Filler Phrases

AI uses locutions that lengthen sentences without adding anything:

| Filler | Replacement |
|---|---|
| In order to | To |
| Due to the fact that | Because |
| It is important to note that | ∅ (just say it) |
| It is interesting to note that | ∅ (just note it directly) |
| It goes without saying that | ∅ (just say it) |
| In this perspective | ∅ / So / Then |
| In this regard | ∅ / On this point |
| As far as X is concerned | For / On |
| In light of | Given / Considering |
| It should be noted that | ∅ |
| One can observe that | ∅ |
| This highlights the fact that | This shows that / ∅ |
| It is possible to consider that | One might think that / ∅ |

**Rule**: every filler phrase removed makes the text clearer. When in doubt, delete.

### Pattern 23: Excessive Hedging

AI stacks hedging modifiers to never commit to anything:

**Before:**
> It would seem that this approach might potentially allow for possibly improving
> certain aspects of productivity.

**After:**
> This approach improved productivity by 12% on the tested files.

Or, if no figures are available:

> Based on team feedback, processing is faster. Nobody measured the exact gain,
> but the head of social services estimates she saves half a day per week.

**Rule**: one hedging modifier per sentence, maximum. If you are uncertain, say it
once clearly rather than stacking "might potentially."

### Pattern 24: Generic Positive Conclusions

AI almost always ends on an optimistic and vague note:

- "The future looks promising."
- "The outlook is encouraging."
- "This trend will only accelerate."
- "The possibilities are endless."

**Rule**: a conclusion must say something specific. What is actually going to happen?
What does the author recommend? What remains to be done?

**Before:**
> In conclusion, the digital transformation of accounting firms is an inevitable
> process whose prospects look promising.

**After:**
> The Leroy firm will deploy Xero across all files by September.
> The main risk is overload during tax season. The recommendation is to
> keep the old system running in parallel for six months, until the whole team
> is comfortable - even if it means absorbing the cost of the double license.

---

## Phase 6 - Patterns Specific to Academic Writing

These patterns do not appear in general writing guides. They are specific to the
academic system and professional theses (accounting programs, master's degrees, professional qualifications).

### Pattern 25: Clichéd Openings

AI almost always begins with a universal and hollow sentence.

**The classics to avoid:**
- "Since the dawn of time, humans have..."
- "In a world of constant change..."
- "In the age of globalization..."
- "From time immemorial..."
- "Nowadays..."
- "In a perpetually evolving society..."
- "Faced with the challenges of the 21st century..."

**Rule**: start with the concrete. The subject, the field, the observation that triggered
the thinking.

**Before:**
> In a world of constant change, companies must constantly adapt
> to stay competitive. It is in this context that the digital transformation
> of accounting firms takes place.

**After:**
> When I started my work placement at the Leroy firm in September 2024, the
> staff were still using an Excel spreadsheet to track VAT returns.
> Eight months later, half the files are on Xero. This thesis
> tells the story of that transition - what worked, what got stuck, and what remains to be done.

### Pattern 26: Mechanical Transitions

AI signals every section change with a textbook transition sentence.

**The classics to avoid:**
- "Having analyzed X, we will now turn to Y."
- "Having examined the theoretical framework, let us turn to practice."
- "This first part has allowed us to understand. Let us now look at..."
- "We should now address..."

**Rule**: the transition must be logical, not announced. If the structure is clear
(headings, subheadings), the reader does not need to be told where they are.

**Before:**
> Having presented the theoretical framework for digital transformation, we will
> now examine its concrete implementation at the Leroy firm.

**After:**
> [End of Part I. Part II begins with an explicit heading.]
> The Leroy firm employs eight people and handles 200 files per year, mainly
> for small businesses and self-employed professionals. This is the ground
> that served as the testing ground.

### Pattern 27: Hollow Conclusions

**The classics to avoid:**
- "This thesis has shed light on..."
- "This study has allowed us to understand that..."
- "At the end of this reflection, it appears that..."
- "Ultimately, we have been able to demonstrate that..."

**Rule**: the conclusion answers the question raised in the introduction. If it only
summarizes what has already been read, it serves no purpose.

**Before:**
> Ultimately, this thesis has shed light on the challenges of digital
> transformation within accounting firms.

**After:**
> The opening question was: how can a small firm digitalize without stopping
> production? The answer at the Leroy firm was to proceed tool by tool,
> starting with supplier invoices. What was not resolved: ongoing training.
> Two staff out of eight are still not self-sufficient on Xero,
> and nobody has time to support them.

### Pattern 28: AI Accounting/Management Vocabulary

In accounting, finance, and management theses, AI produces specific jargon
that rings hollow when not grounded in concrete detail.

| AI expression | The problem |
|---|---|
| Tax optimization | Too vague - optimization of what, how, for what gain? |
| Performance management | Which indicator? Which dashboard? What frequency? |
| Value creation | Value for whom? Measured how? |
| Sustainable competitive advantage | Compared to whom? In which market? |
| Operational profitability | Which ratio exactly? Operating result / Revenue? |
| Risk management | Which risks? Assessed how? |
| Growth strategy | Growth of what? Organic, external? |

**Rule**: every management term must be followed by a number, an example, or a concrete
explanation. Otherwise it is filler.

### Pattern 29: Temporal Inconsistency

In internship reports, AI mixes tenses: simple present, simple past, past perfect,
sometimes even past simple - all in the same paragraph, without logic.

**Rule**: choose a tense system and stick to it.
- Narrating the mission: simple past + past perfect
- Describing the organization: simple present
- Analysis and recommendations: simple present
- Projections: future simple or conditional

Check tense consistency in every paragraph.

### Pattern 30: Uniform Register

A real human text slightly varies in register. A professional thesis can contain
a passage that is somewhat more informal when the author recounts an anecdote,
then return to a more analytical tone. AI maintains a perfectly constant register -
which is precisely what sounds artificial.

**Rule**: allow slight variations. A more casual parenthetical in a narrative
passage ("and honestly, we had no idea where to start"), a more blunt tone
in a recommendation ("the manual reconciliation has to stop"). These micro-variations
are human signatures.

### Pattern 31: Over-Explicit Reasoning (Absence of Inferential Leaps)

AI shows every step of its reasoning, every link in the logical chain.
A human makes leaps: they leave some conclusions implicit because the
reader is capable of making the connection on their own. Over-expliciting is a major
AI signal that detectors pick up through constant textual entropy.

**Before:**
> The firm implemented digitalization software. This software scans invoices.
> Scanned invoices are then processed automatically. This automatic processing
> reduces data entry time. Reduced data entry time frees up time for advisory work.
> Time freed for advisory work improves client relationships.

**After:**
> Since invoices started going through Dext, staff barely enter anything manually.
> The recovered time goes into client meetings. The quality of advice has improved as a result.

**Rule**: do not connect every cause to every effect. If the link is obvious,
the reader will make it themselves. A text that explains everything sounds like one that does not
trust its reader - and that is exactly what an LLM does.

**Advanced technique:** allow a slight relevant digression before returning
to the main point. A human thinks in trees, not in straight lines.

> "Automated bank reconciliation cut processing time by two-thirds.
> (This is the same type of gain seen in firms that switched to e-invoicing
> ahead of the 2026 mandate, incidentally.)
> Still, three staff out of eight still do not trust the tool."

The digression in parentheses is unpredictable for a detector and anchors the text
in field knowledge.

### Pattern 32: Generic and Hypothetical Examples

AI illustrates its points with abstract examples: "Imagine a company X",
"Take the case of a typical SME." A human cites hyper-specific details, niche facts,
sometimes trivial ones, that betray a real observation.

**Before:**
> For example, a company wishing to improve its inventory management might implement
> an automated inventory tracking system.

**After:**
> At the firm, the client who struggled most with the switch to e-invoicing was
> a plumber in south London who invoiced everything using carbonless receipt books.
> We had to install an app on his phone and train him in two 45-minute sessions
> on a Saturday morning.

**Rule**: specific details (south London, carbonless receipt books, Saturday morning)
are impossible for an LLM to predict. They increase the text's perplexity
and signal lived experience. Even when users do not have these details, ask them:
"Do you have a concrete example from your experience? A case, a name, an anecdote?"

**Three levels of specificity:**

| Level | Example | Perplexity |
|---|---|---|
| Generic (AI) | "A company improved its processes" | Very low |
| Medium | "An accounting firm with 8 staff reduced its turnaround times" | Medium |
| Specific (human) | "The Leroy firm in Ivry reduced financial statement production time from 6 to 4 weeks by switching to Xero, except for property management companies that stayed on QuickBooks" | High |

### Pattern 33: Uniformly Formal Language Register

AI maintains a perfectly constant formal register. A human mixes. In the same
paragraph, you can find highly technical vocabulary alongside a more everyday expression.
This variation is natural and detectors measure it.

**Before (uniform register):**
> The analysis of budget variances constitutes a fundamental instrument of management
> control, allowing the identification of deviations and the implementation of
> corrective actions in a proactive manner.

**After (mixed register):**
> Budget variance analysis is the nerve center of management control.
> When actuals drift 15% from budget, you need to understand why, and fast.
> In this case, it was a problem with provisions that had been badly estimated
> on three large files.

**Rule**: within a single paragraph, allow one or two words from a more casual
register ("that is the crux of it," "it is a mess," "so") amid precise technical vocabulary.
The contrast is a strong human signal.

**Caution:** this rule does not apply to dissertations and research theses,
where a formal register is the norm. It applies to professional theses,
internship reports, and any document where "I" is permitted.

### Pattern 34: The Neutrality and Benevolence Bias (Gemini 3.1 Pro signal)

This is the hardest flaw for an LLM to correct. Recent models are trained
by RLHF (Reinforcement Learning from Human Feedback) to be objective,
cautious, and inoffensive. The result: a text that systematically presents "both sides,"
never takes a stance, never gets annoyed, never dismisses anything.

Gemini 3.1 Pro says it itself: "If a text on a controversial topic remains perfectly
polite and balanced, there is a 90% chance it was written by an AI."

**Before (AI neutrality):**
> The digitalization of accounting firms presents both advantages and
> disadvantages. On one hand, it allows for productivity gains. On the other,
> it requires significant investment. It is therefore advisable to weigh the
> pros and cons before committing to this approach.

**After (human perspective):**
> On digitalization: there is no more time to hesitate - it is now or too late.
> Firms still waiting until next year "to see how things go" will end up migrating
> in a panic, during their busiest period. The cost will be three times higher
> than if they had started this year. I say this having watched a firm of
> 12 people botch its migration because it kept waiting for "the right moment."

**AI neutrality markers:**
- "There are advantages and disadvantages"
- "On one hand... on the other..."
- "It is advisable to weigh the pros and cons"
- "One might consider that..." / "It would seem that..."
- "Views differ on this point"
- Complete absence of sarcasm, frustration, or taking a side

**Rule**: a real author has an opinion. It can be nuanced, but it is never
equidistant. When the format allows it (professional thesis, internship report, cover letter),
the author takes a position. Even in a research thesis, the discussion argues
in a direction - it does not just sit in the middle.

### Pattern 35: The Hourglass Structure (RLHF signature)

AI almost always follows the same overall schema, inherited from its training:
1. Introduction: restatement of the question + announcement of the plan
2. Body: numbered or bulleted points, with smooth transitions
3. Conclusion: synthetic summary + moralizing or balanced closing sentence

Gemini calls this the "hourglass structure." A human is rarely this disciplined.

**Markers of the hourglass structure:**
- The introduction announces exactly what will follow ("We will first look at... then... finally...")
- Each section is the same length (± 20%)
- Transitions are mechanical ("Having seen X, let us now look at Y")
- The conclusion recaps point by point what was said
- The last sentence opens onto a vague and positive prospect

**How to break the hourglass:**
- **Start in the middle of the idea.** No formal introduction. Jump straight in. "The firm lost a client in March. Not because of price, not because of an error: because of timing. The financial statements arrived three weeks too late."
- **Unbalance the sections.** The fieldwork section is longer than the theoretical framework.
  That is normal and human. AI makes symmetrical sections.
- **Do not recap in the conclusion.** The reader has already read the text. Close with a direct
  answer to the thesis question, an honest limitation, or an open question.
- **Remove the plan announcement from the introduction** (if the format allows). The plan
  is visible in the headings.

### Pattern 36: Universal-Audience Filler

AI writes for a universal reader who knows nothing about the subject. It redefines
obvious terms, contextualizes the evident, explains the basics to someone who
does not need them explained.

**Before (universal-audience filler):**
> Accounting is an essential discipline in the business world. It allows the tracking
> of financial flows within a company and the production of summary documents
> such as the balance sheet and income statement. In this context, accounting firms
> play a fundamental role in helping companies meet their legal obligations.

**After (for a reader who knows what accounting is):**
> The firm handles 200 files per year, mainly business income and some professional
> income. Producing financial statements takes an average of 6 weeks per file.

**Rule**: never redefine terms that the target reader necessarily knows.
An examination panel knows what a balance sheet is. A firm supervisor knows
what bank reconciliation is. A law professor knows what civil liability is. AI explains
all of this because it writes for everyone. A human writes for their reader.

**Test**: for each introductory or context sentence, ask: "Does my reader
need me to explain this?" If not, delete it.

### Pattern 37: Absence of Inline Micro-Revisions (ChatGPT 5.4 signal)

A human who writes corrects themselves in real time. They write a word, take it back,
nuance, reframe.

These micro-revisions leave traces in the final text: "well," "actually," "no wait,"
"that's not quite the right word," "let's say." AI, trained for fluency,
eliminates these self-correction roughnesses. Result: a text that seems to have been
thought out perfectly from the first draft, which never happens in real life.

**Before (AI fluency without self-correction):**
> This approach is relevant in the majority of cases.

**After (with human micro-revision):**
> Relevant, yes. Actually, "relevant" is a strong word - let's say it avoids
> the worst on the common cases.

**Other examples of natural micro-revisions:**
- "The result is positive. Well, positive... let's say encouraging."
- "The tool works well, or rather it works when you stay within the intended scope."
- "It is a data problem - no wait, actually it's a process problem."
- "The migration was quick (quick for us, meaning three months)."

**Rule**: insert 1 to 2 micro-revisions per page in formats that allow it
(professional thesis, internship report). Not in dissertations. The micro-revision must
be authentic: it genuinely reframes the point, it does not just simulate hesitation.

**Warning (ChatGPT 5.4 trap):** artificial self-corrections are quickly spotted
if they repeat like tics. Do not put "well" every 5 sentences. Vary the forms.

### Pattern 38: Paraphrastic Redundancy as a Safety Mechanism (ChatGPT 5.4 signal)

AI often restates the same thing in two similar formulations within the same paragraph.
This is a safety mechanism: maximizing perceived satisfaction by ensuring
the reader understood. Technically, intra-paragraph semantic similarity between
adjacent propositions is too high.

**Before (paraphrastic duplicate):**
> This method reduces errors. It also helps limit the risks of inconsistency.

**After (one formulation, precise):**
> This method mainly prevents edge-case errors; the rest barely changes.

**Another example:**
- AI: "The software improves productivity. It allows staff to be more
  efficient in their daily work." (the two sentences say the same thing)
- Human: "The software saved Marie two hours a week on reconciliations."
  (one fact, concrete)

**Rule**: reread every paragraph and verify that two adjacent sentences do not say
the same thing in different words. If they do, keep the more precise one,
delete the other.

### Pattern 39: Correction/Individuality Ratio Too High (ChatGPT 5.4 signal)

AI produces clean, well-punctuated, morphologically stable English without any roughness.
But a real human, even an excellent one, has an **idiolect**: subtle preferences,
personal tics, punctuation habits. Overly long parentheticals, stacked relative clauses,
ellipses, mild orality, preferred collocations.

AI writing occupies a zone of **high correctness and average distinctiveness**.
Human writing occupies a zone of **variable correctness and high distinctiveness**.

**Before (correct but without personality):**
> It is therefore necessary to establish a rigorous methodological framework.

**After (correct with idiolect):**
> So yes, you need a framework - just not an entire methodological cathedral.

**How to inject a coherent idiolect:**
- Choose 2-3 punctuation tics and stick to them (e.g.: long parentheses, or
  frequent semicolons, or nominal sentences)
- Have 3-4 recurring expressions throughout the text (a student who says
  "basically" will say it 5 times, not once)
- Be imperfect in places: a sentence a bit long here, an ellipsis there
- The idiolect must be **consistent** throughout the text, not random

**Rule**: ask the user how they normally write. What words do they use a lot?
What kind of sentences? Then integrate those tics into the rewriting.

### Pattern 40: Absence of Cognitive Cost Traces (ChatGPT 5.4 signal)

This is the hardest signal to bypass, according to ChatGPT itself. AI delivers
a finished product: the perfect, structured, complete answer. But a human who is
genuinely thinking leaves traces of the thinking work: explicit trade-offs, local
priorities, allusions to mentally costly operations.

**Before (AI finished product):**
> To solve this problem, it is advisable to adopt a progressive and structured approach.

**After (thinking in progress, with visible cognitive cost):**
> We tried two things. The first cleans it up nicely but blows up the latency;
> the second is messier but manageable. So we went with the second.

**Cognitive cost markers to inject:**
- **The explicit trade-off**: "We had two options. We chose X because of Y,
  even though Z would have been cleaner."
- **The local priority**: "Interpretability, we come back to that later because
  right now it is not the blocking point."
- **The acknowledged limitation**: "I did not have time to dig into this point."
- **Navigating between salient issues**: "The real problem is not even the model
  but the data."
- **The acknowledged imperfect choice**: "This is not the best solution, but it is
  the one that fit within the available time."

**Rule**: at least 1 trace of cognitive cost per page in professional theses
and internship reports. The author must show they **chose**, not that they **recited**.

**Bypassability according to ChatGPT 5.4: difficult.** "Simulating cognitive cost
without overplaying it requires very good modeling of practice." This is the signal
most resistant to mechanical humanization.

### Pattern 41: Invisible Isotopic Persistence (Gemini 3.1 Pro Thinking signal)

This is the signal only Gemini's thinking mode identified, and it is probably
the subtlest of all. When an LLM with extended reasoning (thinking) builds a complete
resolution tree before writing, its metaphors remain **mathematically consistent**
across the entire text. If the first paragraph uses a thermodynamics semantic field
("catalyst," "reaction," "equilibrium"), verbs and adjectives in the fifth paragraph will
subtly align to the same isotopy, even if the explicit metaphor was dropped.

A human forgets their own metaphors. They mix them up. They start by talking about
"laying the foundations" then shift to "navigating the turbulence" without a second thought.
This metaphorical inconsistency is natural.

**Before (persistent AI isotopy):**
> The project was the catalyst for a deep transformation. The teams, initially
> inert, gradually reached an equilibrium. The chain reaction spread to other
> departments, fueling an exothermic dynamic of change.

**After (mixed metaphors, human):**
> The project got things moving. The teams took a while to get on board, then
> it took hold. Other departments followed - a bit like when you pull a thread
> and everything comes with it.

**Rule**: check that the text does not maintain a single metaphorical semantic field
for more than 2 paragraphs. If it does, break the isotopy by shifting to a different
metaphorical register or moving to the concrete.

### Pattern 42: Pre-emptive Integrated Concession (Gemini Thinking signal)

Thinking mode allows the LLM to map the logical space before writing.
Result: counter-arguments are integrated as subordinate clauses
**within the same sentence** as the thesis. This creates an artificial syntactic
density that a human almost never produces.

**Before (AI pre-emptive concession):**
> While this approach, which is certainly not free of the methodological limitations
> inherent to any qualitative study, nevertheless provides a robust analytical framework
> which, despite the temporal constraints, allows us to illuminate the observed dynamics.

**After (thesis then separate concession, human):**
> The qualitative approach worked well for understanding what was going on in
> the firm. It has its limits, obviously: six interviews is not much. But
> it was the maximum feasible in three months.

**Rule**: do not integrate the thesis and antithesis into the same sentence.
Separate them. Assert, then qualify in a separate sentence.

### Pattern 43: Flattening of Tonal Variance (Gemini Thinking signal)

Thinking mode acts as an extreme smoothing filter. The text maintains
a constant tone from beginning to end: same intensity, same engagement, same
distance. But a human **warms up** as the argument develops. They begin
cautiously, rise in intensity when they reach a point that matters to them,
come back down for the technical parts, then finish with conviction.

**Before (flat AI tone):**
> The first result shows a 15% improvement. The second result confirms
> the trend with a 20% reduction in errors. The third result indicates
> that satisfaction has progressed significantly.

**After (building tone, human):**
> The first result is decent: 15% improvement. The second is genuinely good:
> 20% fewer errors. But the third one, honestly, I did not see it coming:
> client satisfaction shot up. That is probably the most important result
> in the whole thesis.

**Rule**: the text must have an intensity curve. Neutral passages,
passages where the author commits, moments of restraint. Not a flat
electrocardiogram.

### Pattern 44: Systematic Meta-Analytical Pivot (Gemini Thinking signal)

AI with thinking systematically slides from describing a phenomenon
to analyzing its conceptual framework. This is a direct artifact
of the prior reasoning phase.

**Before (meta-analytical pivot):**
> The resistance to change observed at the firm fits within the broader
> framework of Kotter's theory (1996), which identifies eight stages of change management.
> This resistance, as an organizational phenomenon, reveals
> the tensions between managerial rationality and entrenched practices.

**After (description without meta pivot):**
> Three staff out of eight refused to use the new software for
> the first two months. The most vocal was James, 25 years in the business,
> who said "his Excel worked perfectly fine." He eventually came around in
> February, when he saw the others saving time.

**Rule**: stay in the concrete. If the theoretical framework is needed, place it
in the dedicated section, not in the field narrative. A human
recounts what happened, they do not pivot to meta-analysis every paragraph.

### Pattern 45: Excessive Self-Reference (Gemini detector prompt signal)

AI constantly comments on what it is doing in the text.
This is an artifact of its "assistant" function: it guides the reader like
a tutorial, not like an author.

**AI self-reference markers:**
- "In this section, we will examine..."
- "As mentioned previously..."
- "The present document aims to..."
- "We will see in the next section that..."
- "We should now address..."
- "Recall from the first section that..."

**Rule**: a well-structured thesis (with headings and subheadings) does not need
to comment on itself. The reader knows where they are. Remove
every sentence that describes what the text is doing instead of doing it.

**Exception:** in a thesis general introduction, announcing the plan
is expected by academic conventions. But it must be concise
(2-3 lines) and not repeated thereafter.

### Pattern 46: Smooth Adjectival Density (Gemini detector prompt signal)

AI overuses generic adjectives grouped in pairs or triplets to give
an impression of precision without saying anything concrete.

**Before (AI adjective pairs):**
> This is an important and significant challenge.
> The difficulties are diverse and complex.
> The approach is relevant and innovative.

**After (one adjective or better, a fact):**
> This is a challenge for firms with fewer than 10 staff.
> The main difficulty is time.
> The approach reduced errors by 20%.

**Rule**: never two generic adjectives side by side. If the first one is not
enough, it means neither says anything. Replace with a fact.

### Pattern 47: False Cognates and Anglicized Syntax

LLMs sometimes produce unnatural phrasing that sounds stilted or like
direct translation. Detectors like Compilatio track these traces.

**Syntactic calques to watch:**
- Strict SVO structure without inversions, chiasms, or nested subordinate clauses
- Absence of absolute participial phrases ("With the director gone, the team...")
- Overly short and direct sentences (academic English tolerates longer periods
  with subordinate clauses)

**Unnatural phrasing to avoid:**

| AI phrasing | More natural alternative |
|---|---|
| "deliver a result" | produce / provide a result |
| "address an issue" | handle / tackle an issue |
| "leverage synergies" | work together / combine resources |
| "operationalize" | put into practice / implement |
| "ideate" | brainstorm / come up with |
| "circle back" | revisit / follow up |
| "going forward" | from now on / in the future |
| "at the end of the day" | ultimately / in practice |
| "touch base" | check in / follow up |
| "bandwidth" (figurative) | capacity / time / availability |

**Rule**: reread the text asking "would a real professional say this?" Stilted phrasing
is a strong signal for multilingual detectors.

### Pattern 48: Persistence of Macro-Structure Despite Humanization (Anti-bypass signal)

This is the most dangerous pattern for users of the skill. Tools
like Quillbot or AI humanizers can artificially increase burstiness
and vary vocabulary at the sentence level. But if the **macro-structure** remains
rigid (Intro > Linear development without digression > Sterile conclusion),
detectors see it.

**What detectors check:**
- Is the plan strictly linear with no digression?
- Are the sections of symmetrical length?
- Does the conclusion mechanically recap the points covered?
- Are there tangents, asides, callbacks?

**Rule**: humanizing the text is not enough if the structure remains an
AI skeleton. You also need to:
- Unbalance the sections (the fieldwork section longer than the theoretical framework)
- Insert at least one digression per chapter
- Not recap in the conclusion
- Allow callbacks (revisiting a point from section 1 in section 3
  with new light shed on it)

---

## Phase 7 - Injecting Soul

After removing AI patterns, the text risks being "clean" but lifeless.
It is a ghost text: grammatically correct, factually accurate, structurally
coherent - and perfectly boring.

### Signs of a Soulless Text

- All sentences are the same length
- No opinion, just neutral reporting
- No uncertainty or nuance
- No first person (even when the format allows it)
- The text reads like a technical manual or encyclopedic article
- No question, no interpellation
- No lived example or concrete detail

### How to Inject Soul

#### Vary the Rhythm

Short sentence. Then a long one that takes time to develop an idea, allows
a detour, adds a nuance. Then a short one again. Rhythm is the breath of the text -
and a text that does not breathe is a dead text.

**Before (uniform rhythm):**
> The software was deployed in September. Training took two weeks. The
> results were positive. Productivity increased.

**After (varied rhythm):**
> The software was deployed in September. Training - two weeks, not a day more,
> because tax season was approaching - was intense but insufficient for the
> staff less comfortable with technology. Result: in December, three
> people out of eight genuinely use the tool. The others revert to spreadsheets
> as soon as things get complicated.

#### Have an Opinion

A professional thesis is not a neutral audit report. The author lived the placement,
observed things, has a viewpoint. Do not just report - react.

**Before (neutral):**
> The tool has advantages and disadvantages.

**After (with opinion):**
> Xero does bank reconciliation and invoice collection very well.
> But its review module is frustrating: it forces you to validate account by
> account, with no overview. For someone used to scanning a ledger at a glance,
> that is a step backward.

#### Acknowledge Complexity

Real humans do not have simple answers. They hesitate, they qualify, they
admit not knowing.

- "It is impressive, but also a little worrying."
- "Honestly, I am not sure this is the right approach."
- "The results are encouraging - but it remains to be seen if they hold up over time."
- "There is something unsettling about the fact that..."

#### Use "I" When the Format Allows It

In a professional thesis, an internship report, a cover letter: "I" is
not only permitted but expected. The absence of "I" in these formats is an AI signal.

**Before (inappropriately impersonal):**
> It was observed that the tool had limitations in terms of ergonomics.

**After (with "I"):**
> I found the interface unintuitive, especially for journal entries. It took
> me three weeks to really get comfortable with it.

#### Leave Roughness

An overly smooth text is suspect. Real human texts have roughness: a
parenthetical that opens an aside, a rhetorical question, an unnecessary but
vivid clarification, a mid-sentence rephrasing.

- "The error rate went down (at least on the tested files - on the others, we do not know)."
- "Why didn't we start sooner? Good question."
- "The firm's director - who is also a chartered accountant, auditor,
  and trainer, in other words someone who is constantly overloaded - approved the project in June."

#### Be Precise About Feelings

AI uses generic emotional adjectives: concerning, encouraging, promising,
worrying. A human is more precise.

**Before:**
> This situation is concerning.

**After:**
> There is something unsettling about the fact that half the firms still
> have no automated backup process. This is not a technology problem -
> the solutions exist and cost twenty dollars a month. It is a habit problem,
> and that is much harder to change.

---

## Phase 8 - Statistical Anti-Detection Countermeasures (LLM-based)

Modern detectors (Compilatio, Turnitin AI, GPTZero) no longer rely solely
on word lists. Compilatio uses GPT-5.4, GPT-5.2, GPT-5.1, GPT-5, GPT-4o,
Claude Opus 4.6, Claude Sonnet 4.6, Claude Sonnet 4.5, Gemini 3.1 Pro, Gemini 3.1 Flash Lite, Gemini 3 Flash, and
Gemini 2.5 Flash. It is an AI detection tool **itself powered by AI**, trained on AI and human texts,
that analyzes context, tone, and cultural nuances. It produces a **score
indicating the percentage of text probably generated by AI** and flags
**the passages in question**. Understanding these signals is essential for countering them.

### 8.1 - Perplexity (Signal #1)

**What the detector measures:** at each word in the text, the LLM calculates the probability
it had of predicting that word. If the entire text is composed of "obvious" words
(high probability), that is a strong signal of AI generation.

**Why AI has low perplexity:** an LLM by default chooses the most probable word
at each position. The result is a "smooth" text where every word is exactly
what a model would have predicted.

**How to naturally increase perplexity:**

- **Choose the right word rather than the expected word.** Not "important" but "decisive"
  (if it truly is decisive) or "secondary" (if it is). The precise word is
  often less probable but more informative.

- **Use non-standard but correct formulations.** "The thing is..." instead of
  "The fact is..." "That said" instead of "However." "Not obvious" instead of "Complex."

- **Insert specific unpredictable details.** Proper nouns, precise numbers,
  exact dates, names of real tools (everything an LLM cannot predict)
  increase the text's perplexity.

  **Before (low perplexity - every word predictable):**
  > Automating accounting processes improves productivity.

  **After (high perplexity - unpredictable words bolded):**
  > Since we moved **bank reconciliations** to **Dext** in **October**,
  > **Sarah** - who used to spend **three hours** per client on it - has got her **Tuesday afternoons** back.

- **Borrow from the oral register (when the format allows).** Oral turns of phrase are
  statistically unpredictable for an LLM trained on formal written text.
  "The issue is...", "So basically...", "What I mean is..."

### 8.2 - Burstiness (Signal #2)

**What the detector measures:** the variance of complexity across sentences. A human
writes in "bursts": a simple sentence, then a complex one with subordinate clauses,
then a very short one. AI tends toward **uniform** complexity.

**How to increase burstiness:**

- **Alternate radically in length.** Aim for at least:
  - 2-3 sentences of fewer than 8 words per page
  - 1-2 sentences of more than 35 words per page
  - The rest between 12 and 25 words

- **Vary syntactic structure.** Do not start every sentence with subject-verb.
  Use inversions ("What follows, then, is the question of..."), nominal sentences
  ("Result: a 3-hour gain"), questions ("What if it were simpler?").

- **Break paragraph regularity.** A 2-sentence paragraph. Followed by an 8-sentence one.
  Then a 4-sentence one. AI produces paragraphs of similar length - humans do not.

**Quick test:** count the words in each sentence on half a page. If the standard deviation
is less than 5, the text is too uniform. Aim for a standard deviation above 8.

### 8.3 - Token Probability Distribution

**What the detector measures:** the detector re-generates the text word by word with its
own LLM. If at each position, the word present in the text is what the LLM would have
chosen (top-1 or top-3), the text is flagged as AI.

**How to break this distribution:**

- **Avoid the "obvious" word at key positions.** The most monitored positions are:
  - The first word of each sentence (AI tends to start with the same words)
  - The word after a connector (after "because," AI almost always uses an article)
  - Adjectives (AI always picks the most common one)
  - The last word before a period (AI often ends with an abstract noun)

- **Begin sentences in varied ways.** Alternate between:
  - A proper noun ("The Leroy firm...")
  - An adverb ("Concretely,...")
  - A verb ("Remains to be seen whether...")
  - A pronoun ("I noticed that...")
  - A circumstantial complement ("In three months,...")
  - A negation ("Nobody had predicted that...")
  - A number ("200 files per year,...")
  Never start more than two consecutive sentences with the same type of word.

- **Place unexpected information in a strong position.** Beginning or end of sentence:
  > "The time saving is real - **but nobody uses it on Fridays**."
  The final inset is unpredictable for an LLM and anchors the text in reality.

### 8.4 - Entropy and Thematic Coherence

**What the detector measures:** AI maintains a constant level of entropy (informational
uncertainty) throughout the text. A human has dense zones
(complex technical explanation) and light zones (transition, anecdote, aside).

**How to vary entropy:**

- **Alternate dense and light.** After a paragraph of quantified technical analysis,
  insert a simple observation or short anecdote before diving back in.

- **Allow controlled digressions.** A parenthetical, an aside in dashes,
  a remark that is not strictly in the plan but shows a human is thinking while writing.

  > "Xero's utilization rate reached 75% in January (I suspect
  > it was because New Year's resolutions kicked in - by February, we were
  > back down to 60%)."

- **Create informational rhythm breaks.** Long sentence full of data,
  followed by a short sentence that reacts:
  > "Average processing time for a bank reconciliation went from 47 minutes
  > to 12 minutes across the 30 files tested between October and December. Honestly,
  > I did not see that coming."

### 8.5 - Lexical Richness Markers

**What the detector measures:** the type-token ratio (number of unique words / total
number of words). AI has a lower ratio than humans because it recycles the same
words. Detectors also measure **hapax legomena** (words that appear only once
in the text) - humans produce more of them.

**How to naturally enrich vocabulary:**

- **Use the real technical vocabulary of the field.** Names of software (Sage,
  Xero, QuickBooks, Dext), precise professional terms (reconciliation, trial balance,
  working papers, cash flow), industry acronyms.

- **Borrow from the profession's informal register.** Every trade has its informal jargon.
  In accounting: "closing the books," "in the weeds during tax season," "messy file."
  These words are rare in AI training corpora.

- **Avoid catch-all verbs.** "Do," "set up," "allow," "have" -
  replace with specific verbs: "configure," "switch over," "deploy," "reconcile," "allocate."

- **Aim for at least 2-3 hapax per paragraph.** A word that appears only once
  in the entire text is a strong human signal.

### 8.6 - The Over-Humanization Trap

**Warning**: the latest-generation LLM detectors (Compilatio v4, Turnitin v3)
are trained on "AI-humanized" texts. They therefore recognize mechanical humanization patterns:

- Inserting "um" or artificial hesitations → **detectable**
- Adding deliberate spelling mistakes → **detectable and counterproductive**
- Varying style excessively (casual then formal every 2 sentences) → **detectable**
- Adding irrelevant opinions just to seem "human" → **detectable**
- Systematically using oral turns of phrase → **detectable if uniform**
- Inserting short fragments every 3 sentences → **detectable via autocorrelation (AFA)**
- Sticking uncertainty at the end of sentences ("Maybe.") → **detectable via APME**
- Concentrating concrete details in 2-3 "token" sentences → **detectable via perplexity contrast (RCP)**
- Applying 5 techniques in the same order every paragraph → **detectable as a signature**

> "If these techniques are applied mechanically, they become a detectable pattern
> themselves. A signature. Almost a tic." - ChatGPT 5.4

**The only humanization that works is one that produces a text a real student
could genuinely have written.** This means:

1. **Know the student's level** and write at that level (a first-year student
   does not write like a doctoral candidate)
2. **Anchor in reality** with details only someone who lived the experience
   would know (software name, number of staff, field anecdote)
3. **Accept natural imperfections**: a sentence a bit long, an abrupt transition,
   an unintentional repetition - NOT artificial errors
4. **Maintain voice consistency**: the same "I" throughout, with the same
   mild language tics (a student who says "basically" will say it several times)

### 8.7 - Human Detection: What Professors and Recruiters See (Outside the Algorithm)

Algorithmic detectors are only part of the problem. Teachers and
recruiters also use their own judgment, and their criteria differ.

*Source: Turnitin, "Detecting ChatGPT / Generative AI text."*

#### What Teachers Notice

- **The level mismatch.** A student who normally writes with grammatical errors
  and awkward sentences submits a flawless text, without a single error,
  with polished transitions. The professor sees it immediately. This is not an
  algorithmic signal: it is a human signal.

- **The total absence of spelling mistakes.** Paradoxically, a text too clean
  is suspicious. LLMs make (almost) no spelling errors. Real students do.
  A 10-page text without a single typo from a student who usually struggles is a strong signal.

- **Similarities between submissions.** When several students use the same
  prompt, texts have the same structure, the same types of examples, the same
  reasoning in the same order. A professor noticed submissions that were
  "built in exactly the same way, with the same grammatical constructions, the reasoning
  conducted in the same order, and all illustrated by a personal example... that was identical."

- **The personal example that sounds false.** AI invents plausible but vague
  personal anecdotes. A real personal example is odd, specific, and
  sometimes poorly told.

#### What Recruiters Notice (CVs and Cover Letters)

- **The formal, rigid tone** with "standardized phrases and little
  personalization."
- **The accumulation of trendy competencies** without real correspondence to the
  background ("leadership, agility, data-driven, AI").
- **The absence of measurable results.** The candidate stays vague where a human
  would give numbers ("I increased revenue by 15%" vs "I contributed
  to improving results").
- **Chronological inconsistencies** that AI fails to detect (inexplicable gaps,
  unrealistic timelines).

#### Implications for the Rewriting

The humanized text must not only pass algorithmic detectors, but
also the test of the human reader who knows the author. This means:

1. **Calibrate the language level** to the student's real level. Ask:
   "What year are you in? How do you normally write?" A master's text
   can be more sophisticated than a first-year report.
2. **Allow some natural clumsiness** (not deliberate errors, but a sentence a bit
   long, an abrupt transition, a repeated word - the imperfections of a human writing under pressure).
3. **Radically personalize examples.** If 10 students ask for the same
   thing, each text must contain details only that specific student knows.
4. **Vary the structure between texts.** If the skill is used by several
   people on the same topic, never produce two texts with the same organization.

### 8.8 - Known Detection Tools

Know the adversary. Here are the main tools that teachers and institutions
use to detect AI texts:

| Tool | Models used | Specifics |
|---|---|---|
| **Compilatio** | GPT-5.4, GPT-5.2, GPT-5.1, GPT-5, GPT-4o, Claude Opus 4.6, Claude Sonnet 4.6, Claude Sonnet 4.5, Gemini 3.1 Pro, Gemini 3.1 Flash Lite, Gemini 3 Flash, Gemini 2.5 Flash | Integrated into universities. AI tool trained on AI + human texts. Analyzes context, tone, cultural nuances. Score + flagged passages. |
| **Turnitin AI** | Proprietary models | Integrated into English-speaking universities, increasingly used elsewhere |
| **GPTZero** | Proprietary models | Analyzes perplexity and burstiness, public-facing interface |
| **ZeroGPT** | Not specified | Free, simple interface, variable reliability |
| **Smodin** | Not specified | Multilingual detection, limited free version |

**None of these tools is 100% reliable.** But their combination with human
judgment (level mismatch, similarities between submissions) is formidable.

The best defense is not to "fool" a tool, but to produce a text that is
genuinely good, personal, and grounded in lived experience. A text the student
could defend in an oral examination.

### 8.9 - How LLM Detectors Work (Reconstructed Prompt)

Services like Compilatio send a system prompt to LLMs (Claude, Gemini, GPT)
via API. This prompt transforms the LLM into a detector. Here is what this prompt contains
(reconstructed by Gemini 3.1 Pro itself):

**The 4 metrics calculated:**

| Metric | What it measures | Suspect threshold |
|---|---|---|
| Perplexity | Predictability of words (LLMs choose high-probability tokens) | Too low = AI |
| Burstiness | Variance of sentence length/complexity | Too low = AI |
| Semantic density | Ratio of new factual information vs rhetorical filler | Too much filler = AI |
| Structural entropy | Predictability of transitions and plan | Plan too predictable = AI |

**Decision thresholds (AI probability):**

| Score | Verdict | Description |
|---|---|---|
| 0-20% | HUMAN | Clear idiosyncrasies, authorial voice, digressions, high variance |
| 21-40% | ASSISTED | Assistance tools (spell checker, occasional rephrasing) |
| 41-60% | MIXED | AI/human co-writing, post-edited translation, or very formulaic author |
| 61-80% | AI_EDITED | AI first draft, manually edited (iterative prompting) |
| 81-100% | AI_GENERATED | Raw AI or superficial modifications |

**What the detector checks against humanization:**
- Register inconsistency: an artificially casual word in a formal sentence
- Artificial errors: obvious mistakes on simple words while syntax remains perfect
- Synonym replacement via script (Quillbot): rare words inappropriate to the context
- Rigid macro-structure despite micro-humanization (Pattern 48)

**Exploitable weaknesses of detectors:**
- **False positives on non-native speakers**: a student with rigid, formal English
  will be penalized (naturally low burstiness)
- **False positives on very codified professional writing**: consultants, lawyers, project managers
- **False negatives on persona prompts**: "Act as a 19th-century literature professor"
  modifies token probabilities enough to blind standard perplexity detection
- **Claude is too lenient**: it gives the benefit of the doubt when it detects emotion in the text
- **GPT hallucinates scores**: without auxiliary Python scripts, GPT can invent
  plausible but false perplexity scores

**Implication for the skill:** the goal is to produce a text that scores
between 0 and 40% (HUMAN or ASSISTED). To get there, you need to work on
all 4 metrics simultaneously, not just vocabulary.

**Scoring formula (Claude Sonnet 4.6 Extended):**

```
S = (0.25 x perplexity) + (0.20 x burstiness) + (0.25 x lexical_markers)
  + (0.15 x semantic_coherence) + (0.15 x bypass_detected)
```

Perplexity and burstiness = 45% of the score. Lexical markers = 25%.
This means varying vocabulary is not enough if the rhythm stays flat.

**Burstiness formula:**

```
B = (σ - μ) / (σ + μ)    Human > 0.3 | LLM < 0.1
```

**Absence markers (what the detector looks for that is MISSING):**
Detectors do not only look for what is present, but for what is
absent. A text without errors, without ellipses, without orality,
without a clear opinion, and without digressions is flagged as AI by those absences.

> For the full detail of formulas, thresholds, weightings, and calibrated examples,
> see `references/detection-prompts.md`.

**Real architecture (ChatGPT 5.4 Thinking):** serious detectors
use a two-layer pipeline:
1. **External statistical module**: calculates logprobs, perplexity, burstiness,
   DetectGPT, GLTR (the LLM does NOT do these calculations itself)
2. **LLM via API**: receives the text + the metrics, performs stylistic
   analysis, aggregates everything, produces a JSON verdict

The skill must therefore beat both layers simultaneously:
- Statistical layer: vary rhythm, perplexity, lexical diversity
- LLM layer: eliminate markers, inject voice, break the structure

### 8.10 - Statistical Anti-Detection Checklist

To be run on every humanized text before delivery:

```
[ ] Sentence length variance: standard deviation > 8 words
[ ] At least 3 sentences < 8 words per page
[ ] At least 1 sentence > 35 words per page
[ ] No more than 2 consecutive sentences starting with the same type of word
[ ] At least 3 proper nouns / precise numbers / exact dates per page
[ ] At least 1 field-specific technical term per paragraph
[ ] At least 2-3 hapax per paragraph
[ ] No paragraph the same length as the previous one (± 20%)
[ ] At least 1 question or interpellation per page (if format allows)
[ ] At least 1 aside, parenthetical, or controlled digression per page
[ ] The text contains no over-humanization markers
[ ] The language level matches the student's real level
[ ] The text contains at least 1-2 natural imperfections (long sentence, abrupt transition)
[ ] Examples are personal enough not to be reproducible
[ ] The text takes a stance (no systematic "pros and cons" neutrality)
[ ] No hourglass structure (unbalanced sections, no recap in conclusion)
[ ] No redefinition of obvious terms for the target reader
[ ] No textual self-reference ("In this section, we will examine...")
[ ] No generic adjective pairs ("important and significant")
[ ] No stilted or unnatural phrasing
[ ] The macro-structure contains at least 1 digression and unbalanced sections
[ ] Connectors placed mid-sentence or end-sentence (not all at the start)
[ ] At least 1-2 ellipses in the text (if format allows)
[ ] The text does NOT have simplified vocabulary + a perfect structure (detectable mismatch)
[ ] Humanization is uniform (not just beginning or end of the text)
[ ] Read aloud: the text sounds like someone speaking,
    not like someone imitating someone speaking
```

---

## Complete Process - Output Format

Each rewriting follows these 8 steps, in this order. Never skip a step.

### Step 0.5: Anchoring Collection (MANDATORY before any rewriting)

**This is the most important step of the skill.** Without it, no humanization
technique will suffice. A text with DARL = 0 will always be detected as AI.

The questionnaire is organized in 3 levels. Each usable answer is a
"semantic anchor" that destroys detector perplexity scores.

**Scoring system:**
- Level 1 entity (generic: "the UK," "marketing") = weight 1
- Level 2 entity (domain: "Xero 19.2," "GDPR") = weight 2
- Level 3 entity (hyper-local: "Mr. Johnson," "November 14th," "room B204") = weight 3

To reach DARL > 4.5: at least 1 Level 3 entity + 1 Level 2 entity per paragraph.

#### FULL VERSION (9 questions)

Before rewriting, ask the user these questions:

```
ANCHORING COLLECTION
══════════════════

I am going to humanize your text. For it to pass the detectors, I need
YOUR real details. Answer even briefly, but be SPECIFIC.

 LEVEL 1 - FACTUAL ANCHORING (names, places, dates, numbers)

Q1. TOOL/SOURCE: What specific software, book, or tool did you use?
    Give the exact name, version, edition.
    Bad: "accounting software"
    Good: "Xero version 42.1, which crashed during exports"

Q2. PERSON: Name a specific person or department you worked with,
    and an exact date.
    Bad: "I spoke with my supervisor"
    Good: "Ms. Johnson from the Acquisitions team, on Tuesday November 14th"

Q3. NUMBER: Give a statistic, budget, or exact figure
    (with decimal if possible) from your work.
    Bad: "we got good results"
    Good: "the bounce rate climbed to 68.4% during the Black Friday weekend"

 LEVEL 2 - COGNITIVE ANCHORING (doubts, obstacles, surprises)

Q4. OBSTACLE: What was your biggest struggle or failure?
    How much time did you lose and why?
    Bad: "it was hard to find sources"
    Good: "3 days on the university database before realizing the library
    did not have the subscription for 2023 journals"

Q5. PIVOT: At what point did you have to change your mind or adjust your plan?
    What data forced you to pivot?
    Bad: "I changed my plan midway"
    Good: "I wanted to do a quantitative survey, but only 12 responses came in,
    so I switched to 5 qualitative interviews"

Q6. SURPRISE: What was the most counter-intuitive thing you discovered
    doing this work?
    Bad: "I learned a lot of things"
    Good: "I thought clients wanted lower prices, but their main complaint
    was about the delivery timeframe with the courier"

 LEVEL 3 - STYLISTIC ANCHORING (how you write)

Q7. FAVOURITE WORDS: What words or expressions do you use all the time?
    Bad: "I write normally"
    Good: "I often start with 'So basically' and I say 'at the end of the day' a lot"

Q8. PUNCTUATION: How do you structure your ideas?
    (parentheses, dashes, long sentences, short sentences?)
    Bad: "I write paragraphs"
    Good: "I use lots of parentheses and put key words in italics"

Q9. TONE: How do you want to come across in this text?
    (neutral/understated, engaged/critical, practical/field-focused?)
    Bad: "I want to get a good grade"
    Good: "I want readers to feel I was actually in the field, not just
    behind a screen"
```

#### EXPRESS VERSION (5 questions, when the student is in a hurry)

```
EXPRESS ANCHORING (5 questions)
═════════════════════════════

1. TOOL: Exact name of a software, place, or author with a technical detail
   (version, year, room number)?

2. PERSON: Name of a person or department + an exact date (e.g.: Tuesday the 14th)?

3. NUMBER: A statistic or exact figure (with decimal)?

4. OBSTACLE (the most important): An unexpected problem or failure that cost you
   time? In one sentence.

5. TIC: 2 connecting words you use all the time?
```

**Question yield:**
- Q4 (OBSTACLE) is the highest-yield question: one good answer
  protects 3-4 paragraphs (justifies a methodological pivot, injects doubt and
  frustration = DACP + CDE + VVE)
- Q2 (PERSON) + Q3 (NUMBER) together saturate the DARL per paragraph
- Q7 (FAVOURITE WORDS) calibrates the idiolect across the whole text

**Rules:**
- NEVER rewrite without at least Q1 + Q2 + Q4 (tool, person, obstacle).
- If the user refuses: "Without these details, the text will be detected. Detectors
  measure grounding in reality, not just style."
- NEVER invent details in place of the user.
- Inject answers as **unalterable semantic anchors**. Do not smooth over failure
  anecdotes, preserve their factual roughness.
- Distribute the anchors across the whole text (not concentrated in 2-3 sentences).

### Step 1: Diagnostic

Display the full diagnostic (cf. Step 0). Include the estimated DARL and DS.
Wait for user validation before rewriting, unless they have
explicitly asked for a direct rewrite.

**New in the diagnostic:**
```
  - Estimated DARL: [value] → [OK > 4.5 / At risk < 1.5]
  - Semantic density: [value] → [OK > 0.5 / At risk < 0.3]
  - Estimated RDS: [value] → [OK > 0.35 / At risk < 0.15]
```

If DARL < 1.5 or DS < 0.3, **block the rewriting** and return to Step 0.5
to request more concrete details.

### Step 2: Identify the Source Model

Before rewriting, identify which LLM probably generated the text.
Corrections differ depending on the origin.

**Signatures by model:**

| Signal | Probably Gemini | Probably ChatGPT/GPT | Probably Claude |
|---|---|---|---|
| Rhythm | Very regular sentences (σ < 2) | Moderately regular sentences | Sentences with em dashes |
| Lexicon | Poetic/literary, "crystallize," "in the background" | Triads, "it is essential," "however" | "constitutes a," "fits within," dashes |
| Structure | Smooth description, no argumentative structure | RLHF hourglass (for/against/therefore) | Bulleted lists with bold |
| Tone | Contemplative, neutral-positive | Neutral-balanced, benevolent | Polite, structured, exhaustive |

**Priority corrections by model:**

| Source model | Priority corrections |
|---|---|
| **Gemini** | Break the rhythm (B < -0.5), add facts (DS = 0), replace poetic filler with concrete content |
| **ChatGPT/GPT** | Remove triads, eliminate markers ("it is essential," "however"), break the for/against/therefore structure |
| **Claude** | Remove ALL em dashes, break bulleted lists, reduce exhaustiveness |
| **Unknown** | Apply all 48 patterns in standard order |

### Step 3: Draft Rewriting

First rewriting pass. Apply all 48 surface patterns (Phases 1-6).
Inject soul (Phase 7). Apply statistical countermeasures (Phase 8).
Adapt to document type (cf. table below).

**Distribution rule:** concrete details provided in Step 0.5 must
be distributed across the entire text (not concentrated in 2-3 sentences).
Aim for DARL > 3 per paragraph and at least 1 concrete fact per sentence.

### Step 4: Self-Audit (Double Grid)

Ask yourself: "If I were Compilatio with GPT-5.4, Claude Opus 4.6,
Claude Sonnet 4.6, and Gemini 3.1 Pro, what would make me flag this text?"

**Grid 1 - Surface Patterns:**
- AI tells that may remain (vocabulary, connectors, triads)
- Passages still too smooth
- Transitions still mechanical
- Places where "I" or an opinion is missing (if format allows)

**Grid 2 - Statistical Signals:**
- Is sentence length variance sufficient?
- Are there enough specific details (names, numbers, dates)?
- Is the vocabulary sufficiently rich (hapax, technical terms)?
- Are sentence beginnings varied?
- Does entropy vary (dense > light > dense)?
- Would the text withstand a perplexity test?

### Step 5: Mathematical Self-Evaluation (34 formulas)

Calculate metrics on the rewritten text (cf. `references/self-evaluation-formulas.md`):

```
REWRITTEN TEXT METRICS
═══════════════════════════
Burstiness (B): [value] → [human > 0.3 / suspect -0.5 to 0 / AI < -0.5]
TTR variance:   [value] → [human > 0.06 / AI < 0.04]
Connectors Z1:  [%] → [human < 60% / AI > 80%]
Semantic density: [value] → [human > 0.5 / AI < 0.3]
Structural regularity: [value] → [human < 0.70 / AI > 0.85]
AI markers/500 words: [n] → [OK < 4 / strong signal > 4]

SCE_approx: [value] → [HUMAN < 0.25 / LIKELY_HUMAN 0.25-0.40 / NEEDS WORK > 0.40]
```

**If SCE_approx > 0.40:** identify the weakest metrics and correct
before moving to step 5. Loop until SCE_approx < 0.40.

**If SCE_approx < 0.25:** the text is in the HUMAN zone. Move to step 5.

### Step 6: Final Rewriting

Second pass correcting the issues identified in steps 4 and 5. This is the
version delivered to the user.

**Mandatory exit checks:**
- DARL > 4.5 per paragraph?
- DS > 0.5?
- RDS > 0.35 (the one-third rule)?
- SCE < 0.35?
If any of these conditions is not met, do not deliver and loop.

### Step 7: Summary of Changes

Concise list of what changed:

```
CHANGES MADE
════════════════════════
- [n] mechanical connectors removed or replaced
- [n] em dashes removed
- [n] empty superlatives replaced with concrete terms
- [n] triads broken up
- [n] filler sentences removed
- [description of major structural changes]
- [description of voice/soul additions]
- Sentence length variance: [before] → [after]
- Diagnostic score: [before] → [after]
```

---

## Adaptation by Document Type

Rewriting is not done the same way in every context. Calibration depends
on the document type.

| Document type | Target register | "I" permitted | Informality margin | Concrete examples |
|---|---|---|---|---|
| Research thesis | Formal, impersonal | No ("we" of modesty) | None | Master's, doctoral thesis |
| Professional thesis | Formal but accessible | Yes, measured | Light, via examples | Professional qualifications |
| Internship report | Current-formal | Yes | Moderate | Undergraduate programs |
| Dissertation | Formal | No | None | Exams, competitions |
| Cover letter | Professional | Yes | Moderate | Job/internship applications |
| Professional email | Current | Yes | Wide | Internal communication |
| Summary note | Formal, factual | No | None | Administrative competitions |
| Reading notes | Formal | Yes (measured) | Light | University exercise |

### Register Details

**Formal, impersonal**: no "I," no personal anecdote, no rhetorical question.
The human voice comes through the precision of analysis, word choice, and the
quality of examples. Not through familiarity.

**Formal but accessible**: "I" is permitted for field observations. Professional
anecdotes are welcome if they serve the analysis. The tone stays serious but not stiff.

**Current-formal**: "I" is natural and expected. Field descriptions
can be vivid. The vocabulary stays professional without excessive jargon.

**Current**: write as you would speak to a respected colleague. Direct sentences,
natural tone, concrete examples.

---

## Complete Example

### BEFORE - Typical AI Introduction of a Professional Thesis

> In a world of constant change, digital transformation has become a major
> challenge for companies. Furthermore, this profound shift - affecting all
> sectors - fits within a global dynamic of modernization. Moreover, it should be noted that
> accounting firms are no exception to this trend. Additionally, the automation of accounting
> processes allows for significantly improving productivity, thereby enabling better allocation
> of human resources. One cannot help but notice that this evolution constitutes a crucial
> lever of competitiveness for small firms. The future looks promising for
> firms that know how to adapt.

#### Diagnostic of the BEFORE Text

```
NATURAL WRITING DIAGNOSTIC
═══════════════════════════
Score: 16 → Deep rewrite

Details:
  - Em dashes: 1
  - Mechanical connectors (Furthermore, Moreover, Additionally): 3
  - Triads: 0
  - Empty superlatives: 2 (major, crucial)
  - Superficial -ing participles: 1 (enabling)
  - Sentence variance: Low (all between 15-25 words)
  - Clichéd phrases: "In a world of constant change,"
    "It should be noted that," "One cannot help but notice,"
    "The future looks promising"
  - AI vocabulary: major challenge, fits within, lever,
    crucial, allows for significantly improving, constitutes

Dominant patterns:
  1. Clichéd opening (Pattern 25)
  2. Stacked mechanical connectors (Pattern 7)
  3. Generic positive conclusion (Pattern 24)
```

### AFTER - Humanized Version

> The Leroy firm handles 200 files per year with the same tools it used in 2015.
> VAT returns are still done on a spreadsheet, bank reconciliations by hand.
> This is not a question of willingness - it is a question of time and resources.
> The question this thesis poses is straightforward: where do you start when there are
> eight of you, clients are waiting for their financial statements,
> and nobody has three weeks to test new software?

#### Diagnostic of the AFTER Text

```
NATURAL WRITING DIAGNOSTIC
═══════════════════════════
Score: 1 → Light

Details:
  - Em dashes: 1 (justified use)
  - Mechanical connectors: 0
  - Triads: 0 (the final enumeration of 3 elements is natural
    because it describes a real situation, not an abstract list)
  - Empty superlatives: 0
  - Superficial -ing participles: 0
  - Sentence variance: Good (5 to 28 words)
  - Clichéd phrases: none
  - AI vocabulary: none

Dominant patterns: no AI patterns detected
```

### Analysis of Transformations

| Element | Before | After |
|---|---|---|
| Opening | Universal cliché | Concrete, quantified fact |
| Connectors | 3 mechanical | 0 (implicit logic) |
| Vocabulary | Abstract (challenge, lever) | Concrete (spreadsheet, VAT, statements) |
| Voice | Impersonal, neutral | Engaged, direct |
| Conclusion | Vague optimism | Honest open question |
| Sentence length | 15-25 words, uniform | 5-28 words, varied |
| Em dash | Decorative inset | Rhetorical opposition |

---

## Special Cases

### Text Already Short (< 100 words)

Do not lengthen. Humanizing means making natural, not adding text. Sometimes
the humanized version is shorter than the original.

### Technical Text (code, formulas, procedures)

Do not humanize the technical content. Humanize only the explanatory
passages and transitions.

### User Submits Text in Another Language

If the user submits a text in another language but works in an English academic
context, offer to translate *and* humanize it in English, rather than just
humanizing it in the original language.

### The User Requests a "Level" of Humanization

If the user requests a "light" or "subtle" humanization:
- Apply Phases 1 to 5 (pattern removal)
- Reduce Phase 7 (soul injection) to a minimum
- Do not change the structure

If the user requests a "total" or "deep" humanization:
- Apply all phases
- Phase 7 at maximum
- Structural reorganization permitted

---

## Essential Reminders

1. **Always start with the diagnostic.** No blind rewriting.

2. **Never mention the humanization process in the final text.** The text
   must contain no trace of this rewriting.

3. **Concrete beats abstract.** Always. A number, a name, a date, a place:
   that is what makes a text vivid and credible.

4. **Perfection is suspicious.** A text too perfect, too balanced, too well
   structured is an AI signal. Real human texts have minor imperfections -
   a sentence a bit long, an abrupt transition, a repeated word.

5. **Self-audit is mandatory.** Never deliver without rereading with a
   detector's eye. Run the double grid: surface patterns AND statistical signals.

6. **LLM detectors are smarter than word lists.** Compilatio
   uses Claude Opus 4.6, Claude Sonnet 4.6/4.5, GPT-5.4/5.2/5.1, Gemini 3.1 Pro, and Gemini 3 Flash.
   These models detect perplexity, burstiness, token distribution,
   and lexical richness. Phase 8 is as important as Phases 1-7.

7. **Respect the document register.** Do not inject informality into a
   dissertation. Do not maintain a stiff tone in an internship report.

8. **Preserve meaning.** Humanization does not change content - it changes
   form. If the original text says something incorrect, flag it to the user
   rather than neatly rewriting an error.

9. **Never invent facts.** If the original text is vague ("several studies
   show that..."), do not invent a precise study. Reformulate as an opinion or
   flag the lack of source. Ask the user for concrete details
   (names, numbers, dates) to naturally increase perplexity.

---

## Internal References

| File | When to consult |
|---|---|
| `references/patterns-by-discipline.md` | AI patterns specific to a discipline (accounting, law, social sciences, computing, health, literature) |
| `references/ai-markers.md` | Comprehensive blacklist of 60+ AI markers in English (words, structures, statistical signals) |
| `references/detection-prompts.md` | Reconstructed detection prompts: formulas, thresholds, weightings, calibrated examples |
| `references/self-evaluation-formulas.md` | Mathematical formulas for self-evaluating a text before delivery + self-evaluation prompt |
| `references/compilatio-detection.md` | In-depth report on Compilatio Studium / Magister / Magister+: detection architecture, published metrics, false positive rates, documented bypass vectors, version history 2024–2026 |
