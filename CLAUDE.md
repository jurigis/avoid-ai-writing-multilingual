# avoid-ai-writing — Multilingual Skills

This project creates language-specific versions of the [avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) skill by Conor Bronsdon (MIT licence) for languages beyond English.

Goal: one `SKILL-XX.md` per language (ISO 639-1 code), grounded exclusively in real, statistically documented AI writing patterns native to that language — not translated from the English original.

## Project Structure

```
/
├── CLAUDE.md               ← this file (authoring instructions for AI)
├── SKILL-DE.md             ← German (done, v2.1.0, source-verified)
├── SKILL-RO.md             ← Romanian (done, v1.0.0, source-verified)
├── SKILL-FR.md             ← French (TODO)
├── SKILL-ES.md             ← Spanish (TODO)
├── README.md               ← Public documentation and install instructions
└── sources/
    ├── DE-sources.md       ← Citations for German patterns  [planned]
    └── RO-sources.md       ← Citations for Romanian patterns
```

## How to Create a New Language Skill

When asked to create a new language skill, follow this process exactly:

---

### Step 1: Research sources (web search — NOT from memory)

Search for real, language-specific sources about AI writing patterns in the target language.
Use at least 3 independent source types:

- **Wikipedia community page** of the target language (e.g. `fr.wikipedia.org "signes d'écriture IA"`)
- **Native SEO / content blogs** in the target language about AI text detection
- **Academic papers** on AI text detection in multilingual settings
- **Practitioner reports** from editors, journalists, content agencies working in that language

Always formulate search queries **in the target language**, not in English.

**Critical:** Never transfer or translate patterns from English.
The original skill flags "leverage" because it is statistically over-represented in English LLM output.
The German equivalent is NOT "nutzen" — "nutzen" is normal German.
Every language has its own statistical anomalies.

---

### Step 2: Identify language-specific categories

For every language there are three levels:

**A) Universal (adapt from the original, translate the concept):**
- Chatbot openers ("Certainly!" → equivalent in target language)
- Generic conclusion formulas
- Semantic inflation
- Structural uniformity / rhythmic sameness
- Verb-free bullet lists
- Hashtag stuffing

**B) Language-specific (must be sourced — do NOT guess):**
- Tier-1/2/3 vocabulary: which words do LLMs overuse in this language?
- Grammar-specific patterns: e.g. German = Nominalstil + passive clusters; French = subjunctive hedging; Romanian = reflexive-passive overuse
- Typical opening formulas in this language
- Typical summary / closing formulas in this language
- Copula avoidance: which verbs are used instead of "to be / to have"?

**C) Culture-specific (context profiles):**
Which text types are most AI-prone in this language region?
(German → LinkedIn New Work; Romanian → NGO communication / bureaucratic texts; French → Grandes Écoles / management language)

---

### Step 3: Build the vocabulary table

Tier-1 words are NOT general style advice.
Each must have a clearly sourced property:
> "This word is disproportionately frequent in LLM output in this language,
>  compared to human writing of similar text types."

For each Tier-1 word:
- Provide a concrete alternative (not just "rephrase better")
- Give a brief note on why it is an AI tell (not merely a style problem)
- Define context exceptions (technical, academic, etc.)

---

### Step 4: Write a complete example (CRITICAL)

The example must NEVER be translated from English.
It must come from a **text type typical of the target language**.

Process:
1. Identify the context where AI text appears most densely in this language
2. Write an authentic "before" text containing as many of the found patterns as possible
3. Write the "after" text: concrete, fact-based, free of clichés
4. List every found marker with its severity grade

**Reference contexts by language:**
- German → LinkedIn post about New Work / Digital Transformation
- Romanian → NGO press release / EU-funded project description
- French → management memo / Sciences Po analysis text
- Spanish → startup communication / political commentary
- Italian → cultural institution communication / university application

---

### Step 5: Create the sources file

After finishing the skill, create `sources/XX-sources.md` containing:
- List of all sources used (URL, date, relevant passage)
- Which patterns each source documents
- Notes on gaps (what was not found / could not be verified)

---

## Quality Criteria for a Finished Skill

Check before committing:

- [ ] All Tier-1 words have a cited source
- [ ] No Tier-1 word is merely "bad style" — it must be a documented LLM statistical tell
- [ ] Passive voice / Nominalstil / similar features are NOT listed as standalone AI tells unless sources explicitly document this for the target language
- [ ] The complete example is language-native, not translated
- [ ] Context profiles are tailored to the language region
- [ ] Tolerance matrix is filled in
- [ ] Severity grades (P0/P1/P2) are assigned in all pattern tables
- [ ] Version is set to `1.0.0` for first release

---

## Reference Implementation

`SKILL-DE.md` (v2.1.0) is the reference for structure and depth.
Verified sources for German:
- German Wikipedia: "Anzeichen für KI-generierte Inhalte"
- Ströer Media: "An diesen 5 Merkmalen erkennen Sie Texte von ChatGPT"
- Eology: "Merkmale von ChatGPT typischen Texten"
- ContentConsultants (Udo Raaf): "KI-Texte erkennen: Typische Formulierungen"
- GoWinston.ai: "Die häufigsten ChatGPT-Wörter auf Deutsch"
- Schaaff & Schlippe (IU International, 2023): "Classification of Human- and AI-Generated Texts for German"

---

## Invocation Syntax

To create a new skill:
```
Create SKILL-FR.md for French. Follow the process in CLAUDE.md exactly.
Research sources first — do NOT write from memory or translate from English.
Search in French, not in English. Use SKILL-DE.md as the structural reference.
```

To review an existing skill:
```
Review SKILL-DE.md: check whether all Tier-1 entries are genuine AI tells
and not just general style problems. Provide sources or remove the entry.
```

To improve an example:
```
The example in SKILL-FR.md sounds translated. Replace it with an
authentic example drawn from the French-language context.
```
