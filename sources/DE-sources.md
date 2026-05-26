# Sources for SKILL-DE.md (German)

Created: 2026-05-26

---

## Sources Used

### 1. Academic Paper – Main Source

**Title:** Classification of Human- and AI-Generated Texts for English, French, German, and Spanish  
**Authors:** Kristina Schaaff, Tim Schlippe, Lorenz Mindner (IU International University of Applied Sciences, Germany)  
**URL:** https://arxiv.org/abs/2312.04882  
**Also published:** ACL Anthology https://aclanthology.org/2023.icnlsp-1.1/  
**Date:** 2023 (ICNLSP 2023 – 6th International Conference on Natural Language and Speech Processing)  
**Relevance:**  
- Analyses linguistic features that distinguish human-written from AI-generated text in German (and EN/FR/ES)
- Investigates two scenarios: AI text generated from scratch, and AI-rephrased human text
- Provides cross-language comparison — confirms that AI writing patterns are language-specific, not universal
- Basis for the principle that English patterns cannot be transferred directly to German

**Documented Patterns:** General foundation for statistical over-representation logic; sentence-length uniformity (#19/37); structural uniformity

---

### 2. German Wikipedia – AI Content Guidelines

**Title:** Wikipedia:Anzeichen für KI-generierte Inhalte  
**URL:** https://de.wikipedia.org/wiki/Wikipedia:Anzeichen_f%C3%BCr_KI-generierte_Inhalte  
**Date:** 2023–2024 (community maintained)  
**Relevance:**  
- Official German Wikipedia editor guide for identifying AI-generated content
- Documents specific German-language AI patterns: exaggerated emphasis on symbolism and significance
- Lists typical chatbot openers and phrases intended for direct conversation rather than prose
- Explicitly warns against relying on automated detection tools — supports human pattern recognition approach

**Documented Patterns:** Chatbot openers (#26), sycophantic tone (#34), significance inflation (#1), excessive structure (#36)

---

### 3. Ströer Media – "An diesen 5 Merkmalen erkennen Sie Texte von ChatGPT"

**Title:** So erkennen Sie Texte von ChatGPT  
**URL:** https://www.stroeer-direkt.de/blog/2023/an-diesen-5-merkmalen-erkennen-sie-texte-von-chatgpt/  
**Date:** 2023 (Ströer Media Deutschland GmbH)  
**Relevance:**  
- Documents five German-specific ChatGPT markers from a major German media company
- Explicitly identifies "eine Vielzahl an" and "eine breite Palette an" as formulaic enumeration openers
- Confirms "kann"-overuse as a typical ChatGPT hedging pattern in German
- Documents repeated closing formulas: "Es ist jedoch wichtig zu beachten, dass…", "Zusammenfassend lässt sich sagen…", "Insgesamt ist…"
- Also confirms "tauchen wir ein" as one of the clearest German AI markers

**Documented Patterns:** "eine Vielzahl an / eine breite Palette an" (Tier-2), "kann"-overuse (#15a), KI summary openers (#30), "tauchen wir ein" (#27)

---

### 4. Eology – "Merkmale von ChatGPT typischen Texten"

**Title:** Merkmale von ChatGPT typischen Texten – eology Roundtable  
**URL:** https://www.eology.de/news/merkmale-von-chatgpt-typischen-texten-beim-ai-roundtable  
**Date:** 2023 (eology GmbH – SEO agency)  
**Relevance:**  
- Documents "kann" as the single most over-used word in German ChatGPT texts — systematically weakens assertiveness
- Identifies typical ChatGPT introductory pattern: starting with "In der heutigen Zeit / In der modernen Welt"
- Notes that ChatGPT repeatedly echoes the headline topic in the first sentence of each paragraph
- Practical roundtable format from German SEO practitioners — not theoretical

**Documented Patterns:** "kann"-overuse (#15a), contextualization opener (#16 Tier-3), structural uniformity / paragraph rhythm (#19/37)

---

### 5. ContentConsultants (Udo Raaf) – "KI-Texte erkennen: Typische Formulierungen"

**Title:** KI-Texte erkennen: Typische Formulierungen und Muster  
**URL:** https://www.contentconsultants.de/ki-texte-erkennen-warum-man-texte-schreibt/  
**Date:** 2023–2024 (ContentConsultants – SEO consulting)  
**Relevance:**  
- Catalogues typical German AI phrases and fixed formulas that make text "non-specific and interchangeable"
- Confirms "tauchen wir ein" as a clear AI marker (alongside Ströer and mindtwo)
- Documents that AI writing style is "strangely stilted and inflated" with repeated rhetorical figures
- Notes that trained readers detect these patterns immediately even without AI detector tools

**Documented Patterns:** "tauchen wir ein" (#27), Tier-1 vocabulary inflation (#8), structural/rhetorical formulas (#36)

---

### 6. GoWinston.ai – "Die häufigsten ChatGPT-Wörter auf Deutsch"

**Title:** Die häufigsten ChatGPT-Wörter (und warum KI-Detektoren…)  
**URL:** https://gowinston.ai/most-common-chatgpt-words/  
**Date:** 2023–2024 (Winston AI – AI detection tool)  
**Relevance:**  
- Lists the most statistically over-represented words and phrases in German ChatGPT output
- Explains that AI scoring is triggered by word clusters and patterns, not individual words
- Documents ChatGPT's tendency to soften statements and avoid strong stances ("reduced decisiveness") — basis for Hedge-Stacking pattern
- Multilingual scope confirms German-specific over-representation differs from English

**Documented Patterns:** Tier-1 vocabulary list (statistical basis), hedge-stacking (#15), "kann"-overuse (#15a)

---

### 7. ki-im-marketing.at – "ChatGPT-Texte erkennen: Typische Merkmale"

**Title:** ChatGPT-Texte erkennen: Typische Merkmale von KI-generierten Texten  
**URL:** https://ki-im-marketing.at/blog/chatgpt-texte-erkennen-typische-merkmale-von-ki-generierten-texten  
**Date:** 2023–2024 (Austrian marketing / AI blog)  
**Relevance:**  
- Explicitly documents the "rule of three" as a ChatGPT default output pattern in German: always exactly 3 tips, 3 arguments, 3 steps regardless of content
- Confirms this as a structural AI tell specific to German marketing and blog content
- Practitioner perspective from Austrian content creators

**Documented Patterns:** Dreier-Listen-Muster / rule-of-three (#36a)

---

## Gaps and Undocumented Patterns

The following patterns are included in SKILL-DE.md based on general LLM behaviour observation and practitioner consensus, but no single German-language academic source was found that specifically documents them as statistically over-represented in German LLM output:

- **Kopula-Vermeidung** (Pattern #9 — "dient als", "fungiert als", "stellt dar"): Widely observed by German editors and practitioners, but not confirmed by a dedicated corpus study for German
- **Synonymketten** (Pattern #10): General LLM behaviour documented in English research; German-specific study not found
- **Tier-2 vocabulary** (most entries beyond "kann" and "eine Vielzahl"): Derived from practitioner consensus across sources 3–6; no single corpus study confirms statistical over-representation for German specifically
- **mindtwo** as third confirmation source for "tauchen wir ein" (#27): Referenced in the skill file but URL not independently verified in this session

## Recommendations for Future Improvements

1. German Wikipedia source deserves deeper analysis — the full list of documented patterns in that article may cover additional entries not yet in the skill
2. A corpus study specifically on German LinkedIn AI text would strengthen the Tier-1 vocabulary claims for the business/New Work context
3. The Schaaff & Schlippe (2023) paper full text should be reviewed for specific German linguistic features identified by their classifier — these could justify additional Tier-1 entries with academic backing
