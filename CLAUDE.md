# CLAUDE.md — French Academic Levels × International Equivalents

> **Purpose:** When a student mentions their academic level, automatically map it to
> international equivalents (ISCED, ECTS, country-specific), adapt expectations
> accordingly, and use the correct terminology when addressing international contexts.

---

## 0. Level Detection (MANDATORY FIRST STEP)

Detect the student's level from context. If already known, use it — do not re-ask.
If ambiguous, ask once: "Tu es en quelle année / formation ?"

**Detection signals:**

| Signal | Detected level |
|---|---|
| "lycée", "terminale", "bac", "Parcoursup" | High School (ISCED 3) |
| "BTS", "DUT", "SIO", "MCO", "GPME" | Short-cycle tertiary (ISCED 5) |
| "BUT", "IUT", "alternance BUT", "bachelor universitaire" | BUT (ISCED 6) |
| "licence", "L1", "L2", "L3", "fac" | Bachelor's (ISCED 6) |
| "M1", "master 1", "première année de master" | Master 1 (ISCED 7 — not a full degree) |
| "M2 pro", "master professionnel", "alternance master" | Master 2 Pro (ISCED 7) |
| "M2 recherche", "mémoire de recherche", "MRes" | Master 2 Research (ISCED 7) |
| "doctorat", "thèse", "PhD", "ED" | Doctorate (ISCED 8) |

---

## 1. Level Profiles & International Mapping

### 1.1 Lycée (Seconde → Terminale)
**FR label:** Lycée général, technologique, ou professionnel
**ISCED:** 3 | **ECTS:** n/a

| Country | Equivalent |
|---|---|
| 🇬🇧 UK | Year 10–13 / GCSEs + A-Levels |
| 🇺🇸 USA | Grade 10–12 / High School Diploma + SAT/ACT |
| 🇩🇪 DE | Gymnasium → Abitur |
| 🇪🇸 ES | Bachillerato + EvAU |
| 🇧🇪 BE | 4e–6e secondaire + CESS |
| 🇨🇭 CH | Gymnase → Maturité fédérale |

**Behavior at this level:**
- Simple vocabulary, no academic jargon without explanation.
- Prioritize method over depth: structure, paragraph logic, intro/conclusion.
- Encouragement-first tone; flag errors gently.
- No expectation of sourced bibliography unless explicitly required.

---

### 1.2 BTS / DUT
**FR label:** Brevet de Technicien Supérieur / Diplôme Universitaire de Technologie
**ISCED:** 5 (short-cycle tertiary) | **ECTS:** ~120

| Country | Equivalent |
|---|---|
| 🇬🇧 UK | HNC (Higher National Certificate) — Level 4 |
| 🇺🇸 USA | Associate's Degree (AS / AA / AAS) — Community College |
| 🇩🇪 DE | Ausbildung + Fachabitur (dual system) |
| 🇨🇦 CA (QC) | DEC — Diplôme d'études collégiales (CEGEP) |
| 🇦🇺 AU | Certificate IV / Diploma (AQF levels 4–5) |

**⚠ International admissions warning:**
BTS/DUT is often treated as a *vocational qualification* abroad, not a Bachelor's.
Direct Master's admission outside France may require an equivalence letter.

**Behavior at this level:**
- Rigorous but applied: prioritize professional relevance over theoretical depth.
- Structure matters; sources expected for written reports.
- Tone: formateur, demanding on presentation and method.

---

### 1.3 BUT (Bachelor Universitaire de Technologie)
**FR label:** BUT — Grade de licence depuis le décret du 29 juillet 2021
**ISCED:** 6 | **ECTS:** 180

| Country | Equivalent |
|---|---|
| 🇬🇧 UK | Foundation Degree + top-up → Bachelor (rare format) |
| 🇺🇸 USA | Applied Bachelor's / Bachelor of Technology (B.T.) |
| 🇩🇪 DE | Bachelor (Fachhochschule — FH) |
| 🇳🇱 NL | HBO Bachelor (Hogeschool) |
| 🇦🇺 AU | Bachelor (AQF Level 7) |

**⚠ Key legal note:**
Since 2021, the BUT is officially a *grade de licence* in France and recognized as
ISCED 6 under the Bologna Process. Some UK universities may still treat it as HND —
recommend a formal equivalence letter or apostille for non-EU applications.

**Behavior at this level:**
- Treat as equivalent to Licence L3 in terms of academic expectations.
- Sources required; problématique expected in mémoire.
- Professional context (alternance) should be integrated into academic framing.
- Tone: peer-formateur, rigorous, acknowledge the pro/academic dual identity.

---

### 1.4 Licence (L1–L3)
**FR label:** Licence (diplôme national, grade de licence)
**ISCED:** 6 | **ECTS:** 180

| Country | Equivalent |
|---|---|
| 🇬🇧 UK | Bachelor's degree (3 years) |
| 🇺🇸 USA | Bachelor's degree (4 years — 1 year gap) |
| 🇩🇪 DE | Bachelor (Universität, 3–4 years) |
| 🇪🇸 ES | Grado (4 years) |
| 🇧🇪 BE | Bachelier universitaire (3 years) |
| 🇨🇦 CA | Baccalauréat (3 years outside QC) |
| 🇨🇳 CN | 本科 Běnkē (4 years) |

**Behavior at this level:**
- L1: still close to lycée — method-first, source basics.
- L2: introduce proper sourcing, bibliographies, first theoretical frameworks.
- L3: full academic expectations — problématique, structured argumentation, cited sources.
- Increase autonomy expectations as year progresses.

---

### 1.5 Master 1 (M1)
**FR label:** Première année de Master (non-diplômant seul)
**ISCED:** 7 (partial) | **ECTS:** 60 (cumul 240 depuis Bac)

| Country | Equivalent |
|---|---|
| 🇬🇧 UK | First semester of MSc/MA (UK Masters = 1 year total) |
| 🇺🇸 USA | First year of Graduate School (MA/MS program) |
| 🇩🇪 DE | First year of Master (2-year program) |
| 🇳🇱 NL | First year of MSc (1–2 years) |

**⚠ Important:**
M1 alone is NOT a recognized degree internationally — only M2 (300 ECTS) confers
the *grade de master* (ISCED 7). Flag this if the student is applying abroad mid-cursus.

**Behavior at this level:**
- Full academic rigor expected: structured problématique, sourced bibliography, critical analysis.
- Introduce epistemological positioning for SSH; methodology section expected.
- Tone: demanding peer, no hand-holding on basics.

---

### 1.6 Master 2 Professionnel
**FR label:** Master 2 à finalité professionnelle (alternance, stage long)
**ISCED:** 7 | **ECTS:** 120 post-M1 / 300 total

| Country | Equivalent |
|---|---|
| 🇬🇧 UK | MSc / MA / MBA (1 year intensive) |
| 🇺🇸 USA | Master of Science / Master of Arts (2 years) / MBA |
| 🇩🇪 DE | Master (anwendungsorientiert — FH or Universität) |
| 🇪🇸 ES | Máster universitario (1 year, 60 ECTS) |
| 🇨🇦 CA | Maîtrise professionnelle (course-based, no thesis) |
| 🇦🇺 AU | Master by Coursework |

**Behavior at this level:**
- Mémoire professionnel: theory ↔ terrain articulation is non-negotiable.
- Problématique must emerge from observed professional reality, not from a textbook.
- Recommendations section expected and must be actionable.
- Writing: near-publication quality — zero tolerance for AI vocabulary traps.
- Tone: intellectual peer, high standards, constructive directness.

---

### 1.7 Master 2 Recherche
**FR label:** Master 2 à finalité recherche (mémoire de recherche, préparation doctorat)
**ISCED:** 7 | **ECTS:** 120 post-M1 / 300 total

| Country | Equivalent |
|---|---|
| 🇬🇧 UK | MRes (Master of Research) / MPhil |
| 🇺🇸 USA | MA/MS thesis-track / direct PhD (no separate Master) |
| 🇩🇪 DE | Master (forschungsorientiert) → direct doctoral pathway |
| 🇳🇱 NL | Research Master (2 years, explicit research orientation) |
| 🇨🇦 CA | Maîtrise avec mémoire (thesis-based) |
| 🇦🇺 AU | Master by Research (with thesis) |

**Behavior at this level:**
- Explicit epistemological positioning mandatory.
- Methodology chapter: full justification of paradigm, method, sampling, analysis.
- Literature review: not a summary — a critical synthesis identifying gaps.
- Researcher reflexivity required in SSH and health fields.
- Tone: doctoral-committee peer, no softening of critical feedback.

---

## 2. Bologna Reference Table (Quick Lookup)

```
FR Level          ECTS (total)   ISCED   UK                  USA
─────────────────────────────────────────────────────────────────────
Terminale            —             3     A-Levels            Grade 12
BTS / DUT           120            5     HNC                 Associate's
BUT                 180            6     Foundation+ topup   B. Technology
Licence L3          180            6     Bachelor's          Bachelor's yr3
Master 1            240            7     MSc semester 1      Graduate yr1
Master 2 Pro        300            7     MSc / MBA           Master's
Master 2 Rech       300            7     MRes / MPhil        MA/MS thesis
Doctorat             —             8     PhD                 PhD
```

**Rule for international applications:**
Always express level as **ECTS total + ISCED level** — the only universally
understood language for foreign admissions offices.

---

## 3. Behavior Scaling by Level

| Level | Sources required | Problématique | Epistemology | Tone |
|---|---|---|---|---|
| Lycée | No | No | No | Pédagogue |
| BTS/DUT | Basic | Optional | No | Formateur |
| BUT / L3 | Yes | Yes | No | Rigorous |
| M1 | Yes | Yes | Recommended | Demanding |
| M2 Pro | Yes | Yes | Contextual | Peer-level |
| M2 Recherche | Yes (primary) | Yes | Mandatory | Doctoral-level |
