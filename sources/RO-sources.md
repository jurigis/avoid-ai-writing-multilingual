# Sources for SKILL-RO.md (Romanian)

Created: 2026-05-25

---

## Sources Used

### 1. Academic Paper – Main Source

**Title:** Beyond Lexical Boundaries: LLM-Generated Text Detection for Romanian Digital Libraries  
**URL:** https://www.mdpi.com/1999-5903/16/2/41  
**Date:** 2024 (Future Internet, Vol. 16, No. 2, Article 41)  
**Relevance:**  
- Documents statistical differences between AI-generated and human-written Romanian texts
- Examines lexical diversity and text complexity across five domains (books, news, legal documents, medicine, science)
- Uses ReaderBench Textual Complexity Indices (RBI) for Romanian
- SHAP analysis identifies linguistic features most characteristic of AI-generated text
- **Note:** Full text was not directly accessible (HTTP 403); details drawn from the abstract and IDEAS summary

**Documented Patterns:** Lexical diversity, text complexity, sentence-length uniformity, "burstiness" metric

---

### 2. Anglicism Documentation – "face sens"

**Title:** De ce nu are sens să folosim expresia "face sens"  
**URL:** https://www.antena3.ro/actualitate/educatie/pe-cuvant-cu-ana-iorga-de-ce-nu-are-sens-sa-folosim-expresia-face-sens-431125.html  
**Date:** ca. 2020–2022  
**Relevance:** Documents "a face sens" as the most common anglicism (calque of "to make sense") in contemporary Romanian; used by ~15% of speakers; widely discussed in Romanian media

Additional sources for the same pattern:
- https://voxvalachorum.ro/a-avea-sens-vs-a-face-sens-care-e-forma-corecta/
- https://anidescoala.ro/educatie/gramatica/stii-sa-scrii/face-sens-sau-are-sens/
- https://www.digi24.ro/magazin/timp-liber/cultura/pastila-de-limba-calchierea-din-engleza-si-posesivul-fortat-793650
- https://destepti.ro/calcul-lingvistic-greseli-frecvente-in-limba-romana-actuala/

**Documented Patterns:** Calchieri din engleză (Pattern #10), "face sens" as a typical AI tell

---

### 3. Romanian Wikipedia – AI Content Guidelines

**Title:** Wikipedia:Folosirea inteligenței artificiale  
**URL:** https://ro.wikipedia.org/wiki/Wikipedia:Folosirea_inteligen%C8%9Bei_artificiale  
**Date:** 2023–2024  
**Relevance:**  
- Documents "lungă, argumentații întortocheate" (long, convoluted arguments) as an AI pattern
- Describes "referire la politici inexistente sau vag legate de subiect" (references to non-existent or loosely related policies)
- Introduction of the {{Text generat de IA}} template as an official marker for suspected AI content

**Documented Patterns:** Excessive structure (#36), jargon substituting for content (#42), sentence-length uniformity (#19)

---

### 4. Practitioner Reports – Detecting AI Text in Romanian

**Title:** Cum recunoști un text scris de inteligența artificială  
**URL:** https://www.ikanos.ro/post/partea-a-ii-a-autenticitatea-comunic%C4%83rii-%C3%AEn-era-ai  
**Date:** ca. 2023–2024 (Ikanos.ro – communications agency)  
**Relevance:** Describes lack of authenticity, artificial empathy, and generic tone as recognizable AI patterns; recommends trusting instinct

**Title:** Cum să recunoști conținutul generat de AI: Ghid practic  
**URL:** https://www.iagency.ro/blog/cum-sa-recunosti-continutul-generat-de-ai-ghid-practic-pentru-utilizatori  
**Date:** ca. 2023–2024 (iAgency.ro – digital agency)  
**Relevance:** Documents "Repetiții neobișnuite" (unusual repetitions), "Formulări excesiv de generale" (excessively general phrasing), "Ton constant" (constant tone), "Fraze perfect corecte, dar puțin «reci»" (grammatically perfect but emotionally "cold" sentences)

**Documented Patterns:** Emotional flatness (#32), synonym chains (#11), structural uniformity (#19), over-polishing (#38)

---

### 5. SEO / Content Marketing – Romanian Context

**Title:** Inteligenta artificiala PRO si CONTRA in content marketing si SEO  
**URL:** https://adsem.ro/inteligenta-artificiala-pro-si-contra-in-marketing/  
**Date:** ca. 2023 (ADSEM.ro – SEO agency)  
**Relevance:** Describes AI content as "plictisitor sau lipsit de viață" (boring or lifeless), noting "limite în ceea ce privește înțelegerea semantică" (limits in semantic understanding)

**Documented Patterns:** Ton afectiv plat (#32), Inflație semantică (#1)

---

### 6. Linguistic Calques – General

**Title:** Calcul lingvistic – greșeli frecvente în limba română actuală  
**URL:** https://destepti.ro/calcul-lingvistic-greseli-frecvente-in-limba-romana-actuala/  
**Date:** ca. 2022  
**Relevance:** Documents systematic calque patterns from English in contemporary Romanian; explains why "face sens", "a naviga" (used abstractly) and similar calques are common in AI-generated text

**Documented Patterns:** Calchieri din engleză (#10)

---

### 7. Educational Context – ChatGPT Detection

**Title:** 5 sfaturi ChatGPT pentru a preveni frauda academică  
**URL:** https://panorama.ro/5-sfaturi-chatgpt-prevenire-plagiat-frauda-educatie/  
**Date:** ca. 2023 (Panorama.ro)  
**Relevance:** Describes identical structure, argumentation, and examples as a recognizable AI marker; documents its use in Romanian academic contexts

**Title:** Cum poți detecta un text „scris" de ChatGPT?  
**URL:** https://www.puterea.ro/cum-poti-detecta-un-text-scris-de-chatgpt/  
**Date:** ca. 2023 (Puterea.ro)  
**Relevance:** "aceeași construcție sau aceleași exemple sau raționament" (same structure, examples, or reasoning) as a recognizable AI pattern

**Documented Patterns:** Uniformitate structurală (#19), Triada artificială (#21)

---

### 8. "În lumea de astăzi" as an Explicit Marker

**Source:** CudekAI.com (AI detector documentation)  
**URL:** https://www.cudekai.com/ro/blogs/5-moduri-simple-de-a-detecta-con%C8%9Binutul-chatgpt-utilizeaz%C4%83-detectoare-ai  
**Relevance:** "În lumea de astăzi" is explicitly listed as a typical AI opening phrase in Romanian texts

**Documented Patterns:** Contextualizare inutilă (#6), Tier-3 phrases ("în lumea de astăzi")

---

## Gaps and Undocumented Patterns

The following patterns are based on structural inferences from linguistics and general LLM behavior observations, but have not been independently confirmed by Romanian-language sources:

- **Pasiv reflexiv excesiv** (Pattern #15): A well-known grammatical feature of Romanian administrative language, but no specific paper on LLM over-representation of this form in Romanian was found
- **Nominalizări în lanț** (Pattern #16): Documented as bureaucratic style, but not specifically confirmed as an LLM pattern for Romanian
- **Tier-1 words** other than "inovativ" and "esențial": Inferred from general LLM behavior observations (GPT-4 translation behavior on Romanian prompts), not confirmed by Romanian-language academic sources

## Recommendations for Future Improvements

1. Review the full text of the MDPI paper (2024) — the exact SHAP feature results would better justify Tier-1 vocabulary choices
2. A study of AI-generated text in Romanian NGO communications would be ideal (not yet found)
3. A corpus analysis of Romanian AI text vs. human text in journalism/NGO domains is still missing
4. Dictionary check: which Tier-1 words have acquired new or extended meanings in DOOM3 (Dicționar ortografic, ortoepic și morfologic) through calquing from English?
