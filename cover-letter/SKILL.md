---
name: cover-letter
description: >
  Writes and improves cover letters adapted to any type of application:
  school (Master's, bachelor's, Parcoursup, MIAGE, MSI, EFREI, grande école…), apprenticeship,
  internship, permanent/temporary employment, speculative application, career change.
  Use this skill whenever the user mentions a "cover letter", "application", "applying",
  "application file", "Parcoursup", "MonMaster", or asks to write, improve, correct,
  or rewrite a letter for a position or program.
  Also trigger when the user says "I need to sell myself", "I have an application to send",
  or provides a recruitment context without explicitly mentioning the letter.
version: 2
---

# Skill: Cover Letter (v2, Deep Personalization)

## Core Principle

A generic letter is an invisible letter. The goal is not to produce a "correct" letter:
it's to produce a letter that cannot be sent to anyone else.
Every sentence must either anchor the candidate's profile, or anchor the target. Ideally both.

---

## Step 0: Information Collection (MANDATORY before writing)

Never write without these elements. If the context is already known (profile, experience,
constraints), use it directly without re-asking.

### Candidate side
- Current program (exact title, institution, city)
- Key experience: apprenticeship, internships, jobs (with concrete details: specific tasks, figures, tools)
- Mastered technical skills (software, languages, methods)
- The trigger moment: what specifically crystallized the interest in this field? (see §Personal anchoring)
- Constraints: personal projects not to mention, sensitive elements to avoid
- Desired tone

### Target side
- Exact program / position title
- University / company name
- Specific elements gathered: program modules, research areas, business partnerships,
  recent projects, name of the academic director if known
- Application type (response to listing / speculative / MonMaster / Parcoursup)
- Specific constraints (format, maximum length)

> If information about the target is missing: ask the user for 2-3 concrete elements
> (a module, a project, a specific value). Without this, the letter will inevitably be generic.
> Never invent these elements.

---

## Step 1: Build the Angle BEFORE Writing

Before writing the first sentence, define these three points:

### 1a. The candidate's red thread
In one sentence: what is the central argument that connects the candidate's background to the target?

Examples:
- "Rare accounting/tech hybrid profile in the sector → naturally aligned with MIAGE"
- "Field experience in a firm → brings immediate operational maturity"
- "Atypical career change path → proof of determination and adaptability"

This red thread must show through in every paragraph. Never state it explicitly
("I'm a hybrid profile"): show it through examples.

### 1b. The differentiating angle
What does this candidate have that 95% of other candidates probably don't?
- Unusual experience for their level of study
- A rare combination of skills
- A proactive approach (self-learning, certification, concrete project)
- A strong turning point (career shift, field realization, encounter)

This angle should appear in §2 or §3, naturally, without being over-valued.

### 1c. The "central proof"
One single concrete, strong, memorable example that illustrates the profile on its own.
Quantified or dated if possible. This is the element the reader will remember.

Strong example: "developed a VBA tool that reduced bank reconciliation processing time by 40%"
rather than "I have automation skills."

---

## Step 2: Paragraph-by-paragraph personalization protocol

Test to apply to every sentence: "Could this sentence be pasted into someone else's letter?"
If yes → rewrite.

### §1: Opening (don't start with "I")
- Name the program/position with its exact title
- Include a specific element about the target in the opening (program axis, company's recent
  project, pedagogical specifics)
- Immediately connect to a concrete element of the candidate's background

❌ Generic:
"I wish to join your Master's program in order to deepen my knowledge."

✅ Personalized:
"The articulation between IS modeling and project management in [University]'s MIAGE Master's
directly matches the tension I encounter daily in a firm: understanding business processes
in order to better automate them."

---

### §2: Background and skills (show, don't tell)
- Prohibition on declaring qualities without proof ("I'm rigorous", "I'm motivated")
- Every cited skill must be illustrated by an example or a result
- Frame skills as past actions: "I set up X" not "I master X"
- Name the actual employer / school

❌ Generic:
"My experiences have allowed me to acquire skills in management and IT."

✅ Personalized:
"At ATF Firm, I automated bank reconciliation processing in VBA, reducing processing time
by several hours per client per week, which confronted me with the limits of a purely
accounting-based approach when dealing with growing data volumes."

---

### §3: Profile / target fit (reverse the perspective)
Most candidates write "this program will give me X."
The best write "here is what I bring to the program / team" first.

- Explain how the profile responds to an identified need of the target
- Name a module, axis, or project of the structure and create a bridge with a candidate experience
- Project into the future: what role in 3 years? Why is this program the only logical path?

❌ Generic:
"I am convinced that this program will provide me with the tools I need to succeed."

✅ Personalized:
"The [module name] of the program, combined with my experience of operational constraints in
an accounting firm, would allow me to approach [axis] with both a technical and operational
perspective, the positioning I'm targeting to move toward MOA roles in financial environments."

---

### §4: Conclusion (no outdated formulas)
- Frame an invitation to discuss, not a plea
- Avoid archaic closing formulas unless explicitly required by a very formal context
- Option: conclude with a short conviction, then an invitation to interview

---

## Step 3: Personal anchoring: the "trigger moment"

The most powerful lever against the generic: the precise moment when the direction crystallized.
Optional but highly effective. Place in §1 or §2, 1-2 sentences max.

Questions to ask the candidate to draw it out:
- "What was the concrete situation that made you realize you wanted to go in this direction?"
- "Was there a task or problem during your internship/apprenticeship that made you want to go further?"
- "What conversation or reading convinced you this program was the right one?"

Framing in the letter:
"While handling [specific situation], I realized that [insight]. It is this conviction that led
me to apply for the [program] at [institution]."

---

## Step 4: Anti-generic filter (mandatory pass before delivery)

| Warning sign | Example to eliminate | Fix |
|---|---|---|
| Declaration without proof | "I am rigorous/dynamic/motivated" | Concrete example that shows it |
| Empty superlative | "The quality of your teaching" | Name the specific course |
| Industry generality | "The X field is rapidly evolving" | Remove or anchor on a precise, recent fact |
| Focused on what you receive | "This program will allow me to…" (in §3) | Rephrase as "what I bring" first |
| Cliché formula | "Please find enclosed my CV" | Remove |
| Weak verbs | "I participated in / I was involved in" | Strong action verb: I designed / led / implemented |
| Deliberate vagueness | "[relevant field]", "[relevant experience]" | Name precisely or don't write it |
| Universal sentence | Any sentence that could be copied into another letter | Rewrite with a candidate or target anchor |

Extended reference: `references/anti-generic.md` (20 commented before/after pairs).

---

## Structure and Format Rules

### Canonical structure

| Section | Role | Personalization test |
|---|---|---|
| §1 Opening | Red thread + anchor the target | Does it contain an element specific to the target? |
| §2 Background | Show, don't tell: the central proof | Does it contain a figure or a dated/named fact? |
| §3 Fit | What I bring + projection | Does it name a specific element of the program? |
| §4 Conclusion | Invitation to discuss | Does it avoid archaic closing formulas? |

### Length
- Employment / apprenticeship / internship: 300-400 words
- Master's / school (university application): 400-500 words
- Parcoursup (French university application platform): 1500 characters max

### Style
- Sentences: 20-25 words max, active voice, present and future tense
- Never start the very first sentence of the letter with "I"
- No bullet points in the body of the letter
- Font: Arial or Calibri 11-12, airy paragraphs

### Parcoursup / MonMaster: specific constraints (French platforms)
- No name/surname in the text
- No date or header
- Exact title: "BUT Informatique" not "IUT", "Master MIAGE" not "the master's"
- Show knowledge of the national program requirements
- Mention a concrete step proving genuine interest (open day, alumni exchange, fair)

---

## Formal Header (for letter as attachment)

```
[First name LAST NAME]                    [City, date]
[Address]
[Email] | [Phone]

Attention: [Ms./Mr. LAST NAME, Title]
[Institution / Company]
[Address]

Subject: Application for [exact title] | [Reference if applicable]
```

---

## Final checklist before delivery

- [ ] First sentence does not start with "I" and names the target with its exact title
- [ ] At least 1 ultra-specific element about the target (module, axis, project, named value)
- [ ] Presence of a concrete central proof (quantified or dated if possible)
- [ ] Zero quality declarations without proof
- [ ] §3 addresses "what the candidate brings" before "what they receive"
- [ ] No sentence could be copy-pasted into another letter without modification
- [ ] Anti-generic filter passed (Step 4 table)
- [ ] Conclusion adapted (no archaic closing unless required)
- [ ] Candidate constraints respected (personal projects, length, etc.)
- [ ] Zero spelling errors

---

## Additional References

### Skill resources

→ `references/application-types.md`: Specifics by type + template paragraphs
→ `references/anti-generic.md`: 20 before/after pairs to eliminate hollow phrases

### External skills (if available in the environment)

| Skill | When to consult |
|-------|----------------|
| `/mnt/skills/user/academic-support/SKILL.md` | The student mentions their thesis or internship report as an application argument: draw concrete elements from it |
| `/mnt/skills/user/natural-writing/SKILL.md` | The letter sounds too AI: apply the anti-detection filter with diagnosis and double pass |
