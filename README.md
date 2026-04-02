# anthropics-education

Skills for Claude: academic support and tutoring.

## Overview

Open-source `.md` skill library to turn Claude into a pedagogical assistant, from high school to master's level.

## Structure

```
anthropics-education/
├── README.md
├── academic-support/
│   ├── SKILL.md                              ← Main skill (8 modules)
│   └── references/                           ← Resources loaded on demand
│       ├── citation-standards.md             ← APA 7, Harvard, Vancouver, Chicago, French standard
│       ├── natural-writing.md                ← Anti-AI detection filter (30+ before/after pairs)
│       ├── research-methodology.md           ← Qual, quant, mixed, grids, thematic analysis
│       ├── panel-questions.md                ← 50+ panel/jury questions + anti-AI trap questions
│       ├── level-structures.md               ← High school → Master's research expectations (comparison table)
│       ├── essay-commentary.md               ← Essay, commentary, ruling, document methods
│       ├── document-templates.md             ← Cover pages, tables of contents, bibliographies, typography
│       ├── exam-revision.md                  ← Active recall, schedules, subject cards, exam day
│       ├── research-databases.md             ← Google Scholar, Cairn, HAL, CRAAP evaluation, reading cards
│       ├── thesis-project-management.md      ← Timeline, supervisor meetings, blockers, versioning
│       ├── synthesis-notes.md                ← Document scanning method, synthesis plan, pitfalls
│       └── discipline-specifics.md           ← Standards by discipline (accounting, law, social sciences, IT, health)
├── cover-letter/
│   ├── SKILL.md                              ← Personalized cover letters
│   └── references/
│       ├── application-types.md              ← Specifics by application type
│       └── anti-generic.md                   ← 20 before/after anti-hollow-phrase pairs
└── natural-writing/
    ├── SKILL.md                              ← Anti-AI rewriting (48 patterns, 8 phases, self-evaluation)
    └── references/
        ├── patterns-by-discipline.md         ← Discipline-specific AI patterns (accounting, law, social sciences, IT, health, humanities)
        ├── ai-markers.md                     ← Cross-disciplinary blacklist of 80+ AI markers with multipliers
        ├── detection-prompts.md              ← Reconstructed detection prompts (formulas, thresholds, architecture)
        └── self-evaluation-formulas.md       ← Mathematical formulas for self-evaluating text before submission
```

## How it works

The system uses a **3-level progressive loading** architecture:

1. **Metadata** (always in context): The `name` + `description` in the SKILL.md YAML frontmatter. This is what Claude reads to decide whether to activate the skill. ~150 words.

2. **SKILL.md** (loaded when the skill triggers): The main body with modules, principles, and default responses. Contains rules and logic, not exhaustive details.

3. **references/** (loaded on demand): Detailed files that Claude consults only when the conversation covers a specific topic. For example, `citation-standards.md` is only read if the student asks for help with their bibliography.

This architecture avoids flooding the context with irrelevant information while keeping depth available when needed.

## Available Skills

| Skill | Modules covered | Target levels |
|-------|----------------|---------------|
| `academic-support` | Professional thesis, research thesis, internship report, academic tutoring, essay/commentary, thesis defense, group projects, discipline specifics | High school → Master's |
| `cover-letter` | Personalized cover letters for school, apprenticeship, internship, employment, speculative application, career change | All levels |
| `natural-writing` | Anti-AI rewriting: anchoring collection (9 questions), diagnosis, 48 patterns, 8 phases, 34 mathematical self-evaluation formulas, 8-step process, statistical countermeasures | All levels |

## Example Prompts

```
"I have an M1 accounting thesis due in 3 months and I don't know where to start"
"Help me find sources for my literature review on SME digitalization"
"I have a synthesis paper to prepare for the entrance exam, what's the method?"
"Proofread my cover letter for an accounting firm internship"
"I don't understand the lecture on depreciation, explain it simply"
"We have a group project due, how do we organize?"
"My intro sounds too ChatGPT, make it natural"
"Humanize this text, my professor will know it's AI-written"
```

## Skill Dependencies

Skills can complement each other depending on the need:

| Need | Main skill | Complementary skill |
|------|-----------|---------------------|
| Thesis + Word formatting | `academic-support` | `docx` (public) |
| Thesis + Master's application | `academic-support` | `cover-letter` |
| Text to make more natural / anti-AI | `natural-writing` | `academic-support` |
| Defense + slides | `academic-support` | `pptx` (public) |
| Printable revision card | `academic-support` | `pdf` (public) |
| Cover letter that sounds too AI | `natural-writing` | `cover-letter` |

## Installation

### On Claude.ai — Skills Marketplace

1. Go to [claude.ai/customize/skills](https://claude.ai/customize/skills)
2. Click **"Add skill"** (top right)
3. Paste the raw URL of the `SKILL.md` file you want to install, for example:
   ```
   https://raw.githubusercontent.com/StealthyLabsHQ/ai-edu-skills/main/academic-support/SKILL.md
   ```
4. Claude will automatically load the skill in all your future conversations

Available skill URLs:
| Skill | URL |
|-------|-----|
| `academic-support` | `https://raw.githubusercontent.com/StealthyLabsHQ/ai-edu-skills/main/academic-support/SKILL.md` |
| `cover-letter` | `https://raw.githubusercontent.com/StealthyLabsHQ/ai-edu-skills/main/cover-letter/SKILL.md` |
| `natural-writing` | `https://raw.githubusercontent.com/StealthyLabsHQ/ai-edu-skills/main/natural-writing/SKILL.md` |

### On ChatGPT — Skills Marketplace

1. Go to [chatgpt.com/skills](https://chatgpt.com/skills)
2. Click **"Add skill"**
3. Paste the raw URL of the `SKILL.md` file you want to install (same URLs as above)
4. The skill will be available in your ChatGPT conversations

### On Claude.ai (with Claude Code or Cowork)

```bash
git clone https://github.com/StealthyLabsHQ/anthropics-education.git

# Install the desired skills (with their references)
cp -r anthropics-education/academic-support /mnt/skills/user/
cp -r anthropics-education/cover-letter /mnt/skills/user/
cp -r anthropics-education/natural-writing /mnt/skills/user/
```

> **Important:** copy the entire folder (with `references/`) so progressive loading works. Without the `references/` folder, Claude won't have access to detailed resources.

### As Project Instructions (claude.ai)

1. Create a new Project on claude.ai
2. Copy the content of `SKILL.md` into the project instructions
3. Add the `references/` files as project files
4. Claude will consult them automatically based on context

### Direct use (no installation)

Copy-paste the content of `SKILL.md` into the conversation or into the system instructions of an API call.

## Natural Writing: the anti-detection engine

The `natural-writing` skill is the most advanced in this repo. It was built from
the self-analysis of **6 LLM models** describing their own generation biases:

| Model | Contribution |
|-------|-------------|
| Gemini 3.1 Pro | RLHF hourglass structure, neutrality bias, universal audience fluff |
| Gemini 3.1 Pro Thinking | Isotopic persistence (unique signal), preemptive concession, tonal variance |
| Claude Opus 4.6 | Syntactic regularity, parallel structures |
| Claude Sonnet 4.6 | Calibrated length, em dashes as Claude signature |
| ChatGPT 5.4 | Absent micro-revisions, paraphrastic redundancy, cognitive cost, 20 tics with multipliers |
| ChatGPT 5.4 Pro | Evidence hierarchy, paraphrase category, Turnitin 0.20 threshold |
| Gemini 3.1 Pro Thinking High | 12 formulas (Zipf, Brunet, Gini, lexical contagion, etc.) + 4 coverage formulas 40% + anchoring questionnaire |

**48 detection/humanization patterns**, **8 analysis phases**, **34 mathematical self-evaluation
formulas** (burstiness, TTR, Zipf, Brunet, Gini, connector/punctuation/tense entropy,
cosine similarity, lexical contagion, emotional volatility, referential anchoring,
collocational distortion, signal dilution, etc.), **5 reconstructed detection prompts**,
and an **anchoring questionnaire with 9 questions** (express version: 5 questions) that forces
the student to provide the real details without which no humanization works.

**8-step process:** mandatory anchoring collection, diagnosis, source model identification, rewriting,
self-audit, mathematical self-evaluation (SCE v3), final rewrite with output verification
(LRAD > 4.5, SDI > 0.5, RDS > 0.35, SCE < 0.35), modification summary.

**Estimate:** a raw AI text scores 85-99% on Compilatio. With the full skill
and student details, the target is 5-20% (invisible zone for Turnitin).

Compilatio uses: GPT-5.4, GPT-5.2, GPT-5.1, GPT-5, GPT-4o, Claude Opus 4.6,
Claude Sonnet 4.6, Claude Sonnet 4.5, Gemini 3.1 Pro, Gemini 3.1 Flash Lite,
Gemini 3 Flash, Gemini 2.5 Flash.

## Philosophy

1. **Guide, don't replace**: Skills guide the student's thinking instead of writing for them
2. **Academic rigor**: No invented sources, citation standards respected
3. **Anti-AI detection**: 48 patterns, 8 phases, 34 mathematical formulas, 5 reconstructed detection prompts, anchoring questionnaire, 8-step process
4. **Level adaptation**: Automatic depth adjustment based on profile (high school to Master's)
5. **Progressive loading**: Heavy references are only read when relevant

## Model Usage

Generating files (PDF, DOCX, PPTX) consumes more resources than text exchanges:
- **claude.ai**: consumes quota messages faster
- **API**: increases token count (and cost)

**Tip**: validate content as text before requesting file formatting.

## Contributing

Contributions are welcome. Open an issue or PR to:
- Propose new skills (e.g., dedicated skill for entrance exam prep, vocational training, PhD)
- Add references (e.g., discipline-specific standards)
- Improve existing methodologies
- Add document templates by discipline
- Fix errors or enrich before/after anti-AI pairs

## Roadmap

- [x] Skill `academic-support`: Theses, reports, revision, essay
- [x] Skill `cover-letter`: Personalized cover letters for all types
- [x] Skill `natural-writing`: Anti-AI rewriting: 48 patterns, 8 phases, 34 formulas, 5 reconstructed prompts, anchoring questionnaire, 8-step process
- [ ] Skill `exam-prep`: Entrance exam preparation (competitive prep, public service, health)
- [ ] Skill `vocational`: Vocational training specifics (exams, internship reports)
- [ ] Skill `phd`: PhD support (systematic review, publication, HDR)
- [ ] Additional references by discipline (law, health, sports science, IT...)
- [ ] Ready-to-use DOCX/PPTX templates

## License

MIT
