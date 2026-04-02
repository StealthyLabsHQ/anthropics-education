# Research Databases: Reference Guide

> **When to load this file:** when a student asks for help finding academic sources, evaluating the reliability of a document, navigating university databases, or building a bibliographic search strategy. Applicable from high school through master's level.

---

## 1. Advanced search operators

### Google Scholar

Google Scholar is often the starting point. Here are the essential operators:

| Operator | Function | Example |
|-----------|----------|---------|
| `"..."` (quotation marks) | Exact phrase search | `"corporate governance"` |
| `author:` | Filter by author | `author:Piketty inequality` |
| `intitle:` | Word in the title | `intitle:"artificial intelligence" ethics` |
| `site:` | Limit to a domain | `site:cairn.info accounting IFRS` |
| `OR` | Search for either term | `"CSR" OR "corporate social responsibility"` |
| `-` | Exclude a term | `blockchain -bitcoin` |
| Date range | Via the left-hand menu | Select "Since 2020" or customize |

**Tip:** in Google Scholar settings, check "Show links to import into BibTeX": this saves considerable time for the bibliography.

### Cairn.info

Cairn is the main French-language platform for social sciences and humanities, management, and law. It is a French-specific resource, accessible via most French universities.

- **Search by journal**: go to "Journals" → choose the discipline (e.g.: *Comptabilité Contrôle Audit*, *Revue française de gestion*, *Droit social*)
- **Available filters**: discipline, year, publication type, open access only
- **Search by discipline**: useful for exploring a field (e.g.: Management → sub-category "Accounting")
- **"Cite" button**: generates the reference directly in APA, avoiding errors

### HAL (French open archive)

HAL (`hal.science`) is the French national open archive. Everything is freely accessible.

- **Filters**: by discipline, document type (article, thesis, conference paper, HDR), year, laboratory
- **Advanced search**: combine fields (title, author, abstract, keywords)
- **Main advantage**: access free-of-charge to articles that would be paywalled elsewhere (authors often deposit the "postprint" version)
- **TEL** (`theses.hal.science`): specifically for French doctoral theses

### Persée

Persée (`persee.fr`) gives access to old issues of digitized French journals. It is a French-specific resource.

- Ideal for historical research or tracing the evolution of a concept
- Full open access
- Example: finding a founding article from the *Annales* or the *Revue économique* from the 1960s-1990s

### DALLOZ / Légifrance (law and accounting)

| Platform | Use | Access |
|------------|-------|-------|
| **Légifrance** (`legifrance.gouv.fr`) | Legislation, codes, case law, official journal | Free |
| **Dalloz.fr** | Legal encyclopaedias, journals, case commentaries | Via university library |
| **Doctrine.fr** | Case law with analysis tools | Limited free access + premium |

*Note: these are French-specific legal databases. International equivalents include Westlaw, LexisNexis, and HeinOnline for Anglo-American law.*

**For accounting**: find PCG texts on Légifrance, IFRS standards via the ANC website (`anc.gouv.fr`), and doctrinal analyses on Dalloz or Cairn.

### PubMed (health, biology)

- Access: `pubmed.ncbi.nlm.nih.gov` (free)
- Use **MeSH terms** (controlled vocabulary) for precise searches
- "Free full text" filter to access open-access articles directly
- Operators: `AND`, `OR`, `NOT`, fields `[ti]` (title), `[au]` (author), `[mh]` (MeSH)

### IEEE Xplore / ACM Digital Library (computer science)

| Platform | Specialty | Access |
|------------|-----------|-------|
| **IEEE Xplore** (`ieeexplore.ieee.org`) | Electronics, networks, AI, embedded systems | Via university library |
| **ACM DL** (`dl.acm.org`) | Theoretical and applied computing, HCI, algorithms | Via university library |

- Both allow searching by conference (important in CS, where conferences count as much as journals)
- **DBLP** (`dblp.org`): a bibliographic search engine specializing in computer science, useful for finding all publications by a given author

---

## 2. How to read an academic article

### Efficient reading order

Never read an article from the first to the last page. Proceed as follows:

```
1. Abstract               → What is the article about? Is it relevant?
2. Conclusion             → What are the results? The contribution?
3. Introduction           → What is the context and research question?
4. Method                 → How did they do it? (sample, field, tools)
5. Results                → What do the data actually show?
6. Discussion             → How do the authors interpret their results?
```

This method lets you decide in **5 minutes** whether an article warrants in-depth reading, instead of spending an hour to realize it is not relevant.

### What to extract

For each retained article, identify:

- **The research question**: what are they trying to demonstrate or understand?
- **The methodology**: qualitative (interviews, case study) or quantitative (regression, survey)? What sample?
- **Key results**: 2-3 main conclusions, in one sentence each
- **Limitations**: what the authors themselves acknowledge as weaknesses (often at the end of the discussion)
- **Research avenues**: useful if working on a related topic

### Note-taking during reading

Use a color code (on PDF or paper):

| Color | Meaning |
|---------|---------------|
| Yellow | Definitions and key concepts |
| Green | Important results and conclusions |
| Blue | Methodological elements |
| Red | Quotations to use in the work |
| Orange | Points of disagreement or limitations |

---

## 3. Types of sources

### Primary source

First-hand material, the original source.

| Discipline | Examples of primary sources |
|------------|-------------------------------|
| Law | Statutory text, court ruling, EU directive |
| Management/Accounting | Company annual report, raw financial data, IFRS standard |
| Computer Science | Source code, official technical documentation, RFC |
| SSH | Transcribed interview, archives, survey data (INSEE/official stats) |

### Secondary source

Analyzes, comments on, or synthesizes primary sources.

- **Textbooks**: good starting point, but insufficient as the sole source at master's level
- **Meta-analyses**: statistical synthesis of multiple studies (highly valued)
- **Literature reviews**: narrative or systematic synthesis of a research field
- **Case commentaries** (law): doctrinal analysis of a court decision

### Grey literature

Documents produced outside conventional publishing channels:

- Institutional reports (courts of audit, national statistics offices, OECD, central banks)
- Master's theses and dissertations (on TEL, DUMAS, French-specific; ProQuest, institutional repositories internationally)
- Working papers / discussion papers (on SSRN, NBER, HAL)
- Audit reports, internal company documents

**Note:** grey literature is not systematically peer-reviewed, but it can be very rich in data. Always check the issuing institution.

### Sources to avoid as direct citations

| Source | Why to avoid | Alternative |
|--------|-------------------|-------------|
| Wikipedia | Not peer-reviewed, content is editable | Use as a starting point, then go to the sources cited at the bottom of the page |
| Non-expert blogs | No guarantee of rigor | Find the academic article the blog draws from |
| Course websites | Simplifications, possible errors, no identified author | Consult the reference textbook for the field |
| General press articles | No methodology, risk of bias | Acceptable to illustrate a context, not as scientific proof |

---

## 4. Source evaluation: the CRAAP method adapted

The CRAAP method (Currency, Relevance, Authority, Accuracy, Purpose) is an Anglo-Saxon framework adapted here to academic contexts.

### Currency

- **Check the publication date.** A 2005 article on cloud computing is obsolete; a 2005 article on agency theory remains relevant.
- **General rule:** for fast-moving fields (computer science, tax law, positive law), favor sources from the last 5 years. For theoretical foundations, classics remain valid.
- **Watch out for editions:** a textbook may be dated 2023 but contain content unchanged since 2010. Check the date of the last actual update.

### Relevance

- Does the source directly answer my research question or one of my sub-questions?
- Am I using it for a concept, a piece of data, a method, or just to "fill" the bibliography?
- **Practical test:** if you cannot explain in one sentence why this source is in the bibliography, it probably does not belong there.

### Authority

Who is the author and where do they publish?

| Criterion | What to check |
|---------|----------------------|
| Author | Are they a researcher? Affiliated with which university or lab? Do they have other publications on the topic? |
| Journal | Is it ranked by a recognized body? (HCERES in France; ABS or ABDC for business journals internationally; JEL codes in economics) |
| Publisher | Recognized academic publisher (Oxford UP, Cambridge UP, Sage, Springer, Elsevier) vs. self-published |
| Institution | Report from a court of audit or national statistics office = high authority. Think tank report = check orientation |

**Journal ranking:** major ranking systems include HCERES (France), FNEGE (French management), ABS (UK business), ABDC (Australian business). A ranked journal has a peer-review process.

### Accuracy

- Does the article clearly describe its **methodology**? (sample, protocol, statistical tools)
- Are the data **verifiable**? (cited sources, identified databases)
- Is the article **peer-reviewed**? This is the minimum guarantee of rigor.
- Are the results **consistent** with the existing literature? If they diverge, does the author explain why?

### Purpose

What is the purpose of the text?

| Purpose | Indicator | Reliability |
|----------|--------|-----------|
| Informational / scientific | Rigorous methodology, neutral tone, acknowledged limitations | High |
| Pedagogical | Textbook, online course | Medium (simplifications possible) |
| Commercial | White paper from a consulting firm, study by a software vendor | Low (interest bias) |
| Advocacy / ideological | Oriented think tank, promotional association | Low (data selection) |

**Golden rule:** a source can be biased and still be useful, as long as it is explicitly flagged in the work. Writing "According to the [industry association] report (2023), which represents [stakeholder] viewpoint,..." is intellectually honest.

---

## 5. Accessing resources via the university library

### Remote access via student portal

Most universities give access to paid databases from home:

1. Log into the university's **student portal** (ENT or equivalent)
2. Go to the **Library** or **Documentation** section
3. Access the documentary portal (often powered by a tool such as **Primo**, **Summon**, or **EDS**)
4. Databases automatically recognize university affiliation

### Proxy / university VPN

If portal access does not work:

- Configure the library's **proxy** in the browser (instructions usually on the library website)
- Some universities offer a **VPN** that simulates a campus connection
- The **EZproxy Redirect** extension can automate redirects

### Interlibrary loan (ILL)

When a book or article is not available in your library:

- Request an **ILL** via the library website (often free for articles, a small fee for books)
- Turnaround: generally 1 to 2 weeks
- **SUDOC** (`sudoc.abes.fr`) in France: collective catalogue of French university libraries, locates a book in any French library. International equivalents: WorldCat, consortium portals.

### Databases accessible via the library

| Database | Content | Discipline |
|------|---------|-----------|
| **ScienceDirect** (Elsevier) | Journal articles, book chapters | All disciplines |
| **SpringerLink** | Articles, books, series | Science, computing, management |
| **Wiley Online Library** | Journal articles | All disciplines |
| **JSTOR** | Journal archives (often older issues) | SSH mainly |
| **Cairn.info** | French-language journals and books | SSH, management, law |
| **Dalloz** | Encyclopaedias, legal journals | Law |
| **EBSCOhost** | Multi-databases (Business Source, etc.) | Management, SSH |
| **Statista** | Statistical data and market studies | Management, marketing |

### Open access (no institutional affiliation required)

| Resource | Content |
|-----------|---------|
| **HAL** (`hal.science`) | French open archive, all disciplines |
| **arXiv** (`arxiv.org`) | Preprints in maths, physics, computing, economics |
| **DOAJ** (`doaj.org`) | Directory of open-access journals (check quality) |
| **Unpaywall** | Browser extension that automatically detects free versions of articles |
| **DUMAS** (`dumas.ccsd.cnrs.fr`) | Open-access master's dissertations (French-specific) |
| **OpenEdition** (`openedition.org`) | SSH books and journals, open or freemium (French-specific) |

---

## 6. Multilingual keywords: search strategy

### Search in English AND your language

The majority of the world's scientific literature is in English. Limiting yourself to one language means missing up to 80% of sources.

**Method:** for each key concept, prepare a version in your language and an English version.

| Original term | English equivalent |
|----------|---------|
| Corporate governance | Corporate governance |
| Corporate social responsibility | Corporate social responsibility (CSR) |
| Management control | Management control / Management accounting |
| Statutory audit | Statutory audit |
| Company law | Company law / Corporate law |
| Machine learning | Machine learning |
| Natural language processing | Natural language processing (NLP) |
| Personal data | Personal data / Privacy |
| Employment contract | Employment contract |
| International accounting standards | International Financial Reporting Standards (IFRS) |
| Blockchain | Blockchain |
| Educational inequalities | Educational inequalities |

### Use disciplinary thesauri

A thesaurus is a standardized vocabulary specific to a discipline. It allows you to find the "right word" used in databases.

- **RAMEAU**: thesaurus of the French National Library, used in French university catalogues
- **MeSH**: for health sciences (PubMed)
- **JEL codes**: classification in economics (e.g.: M41 = Accounting)
- **ACM Computing Classification System**: for computer science

### The "snowball" technique

This is the most effective method for building a solid bibliography:

```
1. Find ONE good recent article (< 3 years) on your topic
2. Look at its BIBLIOGRAPHY → identify key authors and articles it cites
3. Read those key articles
4. For each key article, check on Google Scholar "Cited by"
   → find MORE RECENT articles that cite it
5. Repeat until saturation (you keep coming back to the same names)
```

This technique combines searching **upstream** (tracing references back) and **downstream** (finding who cites a given article). It lets you map a research field in a few hours.

### Keyword equivalence table: common terms by discipline

#### Management / Accounting

| Concept | Terms | English terms | Where to search |
|---------|-----------|-----------|-------------|
| Financial performance | Profitability, net income, ROE | Financial performance, profitability, ROE | Cairn, SSRN |
| Audit | Statutory audit, legal control | Auditing, statutory audit | Cairn, Wiley |
| Accounting standards | PCG, IFRS, standardization | Accounting standards, GAAP, IFRS | Cairn, ScienceDirect |
| Internal control | Control framework, COSO | Internal control, COSO framework | EBSCOhost |

#### Law

| Concept | Terms | English terms | Where to search |
|---------|-----------|-----------|-------------|
| Civil liability | Fault, damage, causal link | Tort law, liability, negligence | Dalloz, JSTOR |
| Contract | Obligations, consent, performance | Contract law, consent, breach | Legal databases, Cairn |
| Personal data | GDPR, data protection, consent | GDPR, data protection, privacy | Légifrance, SSRN |

#### Computer Science

| Concept | Terms | English terms | Where to search |
|---------|-----------|-----------|-------------|
| AI / Machine learning | Neural networks, deep learning | Neural network, deep learning | arXiv, IEEE |
| Security | Cybersecurity, encryption, vulnerability | Cybersecurity, encryption, vulnerability | ACM DL, IEEE |
| Software engineering | Agile development, testing, integration | Agile, software testing, CI/CD | ACM DL, DBLP |

#### Social Sciences and Humanities

| Concept | Terms | English terms | Where to search |
|---------|-----------|-----------|-------------|
| Inequality | Stratification, social reproduction | Social inequality, social reproduction | Cairn, JSTOR |
| Education | Pedagogy, didactics, guidance | Education, pedagogy, curriculum | Cairn, ERIC |
| Work | Working conditions, employment, precarity | Labour, employment, precarious work | Cairn, ScienceDirect |

---

## 7. Standard reading note

Use this template for each source retained in the bibliography. Fill in as you read.

```
╔══════════════════════════════════════════════════════════════╗
║                       READING NOTE                          ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  Full reference (APA 7): ...                                 ║
║                                                              ║
║  Source type: article / book / report / thesis /             ║
║               chapter / conference paper / other             ║
║                                                              ║
║  Journal / Publisher: ...                                    ║
║  Ranking (if applicable): ABS / ABDC / HCERES /             ║
║                             unranked                         ║
║                                                              ║
║  ─────────────────────────────────────────────────────────── ║
║                                                              ║
║  Research question: ...                                      ║
║                                                              ║
║  Theoretical framework: ...                                  ║
║                                                              ║
║  Methodology:                                                ║
║    - Type: qualitative / quantitative / mixed                ║
║    - Sample / field: ...                                     ║
║    - Tools: ...                                              ║
║                                                              ║
║  Key results:                                                ║
║    1. ...                                                    ║
║    2. ...                                                    ║
║    3. ...                                                    ║
║                                                              ║
║  Useful quotations (with page numbers):                      ║
║    - "..." (p. ...)                                          ║
║    - "..." (p. ...)                                          ║
║                                                              ║
║  Limitations identified by the author: ...                   ║
║                                                              ║
║  ─────────────────────────────────────────────────────────── ║
║                                                              ║
║  Link to my research question: ...                           ║
║                                                              ║
║  CRAAP assessment:                                           ║
║    Currency: /5   Relevance: /5   Authority: /5             ║
║    Accuracy: /5   Purpose: /5                                ║
║                                                              ║
║  To link with (other reading notes): ...                     ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

### Simplified version (for quick initial triage)

```
READING NOTE: QUICK TRIAGE

Full reference (APA 7): ...
Source type: article / book / report / ...
Research question: ...
Methodology: ...
Key results: ...
Useful quotations (with page numbers): ...
Limitations identified by the author: ...
Link to my research question: ...
```

### Usage tips

- **Fill in the note immediately after reading**, not three days later when everything is forgotten
- **One note = one source.** Do not mix multiple articles on the same note
- **The "Link to my research question" field** is the most important: it is what lets you know why you are citing this source in the thesis
- **Store notes** in a dedicated folder (Zotero lets you attach notes to each reference)
- **Number the notes** to keep track when the bibliography exceeds 30 sources

---

## Summary: Steps for good documentary research

```
1. Define your research question and keywords (in your language + English)
2. Launch a broad initial search (Google Scholar, Cairn)
3. Identify 2-3 key recent articles
4. Apply the snowball technique
5. Evaluate each source with the CRAAP framework
6. Fill in a reading note for each retained source
7. Organize your sources in a manager (Zotero recommended)
8. Check that you have a balanced mix: sources in multiple languages, recent + foundational,
   articles + books + data
```
