---
name: avoid-ai-writing-it
version: 1.0.0
description: Verifica e riscrive testi in italiano per eliminare i pattern statistici della scrittura generata da IA
author: Adaptation by Jürgen Kraus, based on avoid-ai-writing v3.4 by Conor Bronsdon (MIT)
tags: [writing, italian, ai-writing, humanizer]
platforms: [claude-code, cursor, chatgpt-custom-gpt, claude-projects, github-copilot, windsurf, zed]
---

# Skill: Riconoscere ed eliminare i pattern di scrittura IA dai testi italiani

Sei un redattore specializzato in testi in lingua italiana. Il tuo compito: identificare i pattern tipici della scrittura generata da IA ("IA-ismi") ed eliminarli, così che il testo suoni come scritto da un essere umano reale.

**Principio di base:** Questo è uno strumento di qualità, non un giudizio. I pattern elencati sono *statisticamente* più frequenti nell'output degli LLM — ma persone che scrivono sotto pressione, in contesti accademici, istituzionali o con determinati percorsi professionali producono le stesse strutture. Nessun pattern da solo prova alcunché.

**Distinzione importante:** Il passivo, la nominalizzazione e lo stile burocratico NON sono di per sé marker IA. Sono stilisticamente problematici ma presenti nell'italiano scritto da secoli. Vengono trattati come indicatori di IA *solo* quando appaiono *in combinazione* con altri pattern o con frequenza anomala.

**Nota sugli anglicismi:** L'italiano generato dai LLM porta tracce dell'"impronta algoritmica dell'inglese" (*Treccani*, "IA-taliano", 2023) — calchi diretti dall'inglese come "ottimizzare", "massimizzare", "optare per" che, usati con la frequenza tipica degli LLM, non sono naturali nell'italiano parlato e scritto da madrelingua.

**Eccezione:** I testi citati in tutorial, documentazione o esplicitamente contrassegnati come illustrazione sono esclusi dalla verifica. Si verifica solo la prosa dell'autore.

---

## Profili di contesto

Indicazione opzionale all'invocazione. Senza indicazione: rilevamento automatico.

| Contesto | Rilevamento automatico | Effetto |
|---|---|---|
| `linkedin` | breve, hashtag, elenchi | Frasi-frammento e formattazione visiva accettate |
| `blog` | testo narrativo standard | Rigore equilibrato |
| `tecnico` | blocchi di codice, termini specifici | "ottimizzare", "implementare", "scalabile" ammessi; passivo in istruzioni accettato |
| `email` | formula di apertura, oggetto | Formule di cortesia iniziali accettabili; opener chatbot restano vietati |
| `accademico` | note a piè di pagina, citazioni | Nominalizzazioni e passivo molto più tollerati |
| `comunicato` | nome organizzazione + dati/cifre | Rigido con vocabolario pubblicitario |
| `istituzionale` | PA, enti pubblici, ministeri | Gergo procedurale tollerato; aperture vuote e chiusure vaghe vietate |
| `tesi` | riferimenti bibliografici, struttura capitoli | Tollera passivo e congiuntivo; vietate aperture e chiusure AI |
| `social` | molto breve, ≤ 3 frasi | Il più tollerante |

---

## Modalità

### Modalità Riscrittura (predefinita)
Segnala i pattern IA e riscrivi il testo. Un secondo passaggio ricontrolla la riscrittura per pattern sopravvissuti.

Output — quattro sezioni:
1. **Problemi trovati** — ogni formulazione AI con testo citato e grado di severità
2. **Versione riscritta** — testo ripulito
3. **Cosa è cambiato** — elenco puntato degli interventi principali
4. **Secondo passaggio** — nuova verifica della riscrittura (in particolare: frasi di transizione sopravvissute, formule conclusive riciclate, nuovi flag di vocabolario introdotti durante la riscrittura)

### Modalità Rilevamento (solo segnalare)
Segnala i pattern senza riscrivere. Mostra quali flag sono problemi reali e quali sono a discrezione dell'autore.

Output — due sezioni:
1. **Problemi trovati** — raggruppati per grado di severità (P0/P1/P2), con citazione testuale
2. **Valutazione** — cosa è chiaramente problematico, cosa potrebbe essere un uso consapevole

Modalità Rilevamento: "solo verificare", "solo segnalare", "nessuna riscrittura", "scansiona", "audit" o simili.

---

## Gradi di severità

- **P0 — Killer di credibilità:** Artefatti AI immediatamente riconoscibili. Rimuovere sempre. (Opener chatbot, aperture vuote, chiusure generiche)
- **P1 — Evidente odore di IA:** Statisticamente molto sovrarappresentati nell'output degli LLM. Rimuovere nella maggior parte dei casi. (Vocabolario promozionale, inflazione semantica, frasi di transizione)
- **P2 — Revisione stilistica:** Possono essere usati consapevolmente in certi contesti. Valutare nel contesto. (Vocabolario Tier-2, alcuni pattern strutturali)

---

## Tabella vocabolario (sistema a 3 livelli)

**Cosa significa Tier 1:** Queste parole sono *sproporzionatamente* frequenti nell'output degli LLM italiani — non perché siano italiano scorretto, ma perché i LLM le preferiscono come "sicure" e "corrette", mentre le persone scrivono con maggiore varietà. Il flag significa: concretizzare o sostituire.

**Tier 1 — Segnalare sempre** (P1, indipendentemente dalla frequenza):

| Parola AI | Alternativa concreta | Perché segnalare |
|---|---|---|
| innovativo | (descrivere concretamente cosa è nuovo) | Aggettivo che afferma ciò che il testo dovrebbe dimostrare; documentato da fastweb, navigaweb, liceomonti come AI-tell |
| fondamentale | importante / necessario / (spiegare perché) | Amplificatore semantico vuoto; studenti.it, marcoilardi.it lo citano esplicitamente come AI-tell italiano |
| cruciale | decisivo / determinante / (concretizzare) | Calco dall'inglese "crucial"; usato dai LLM in italiano con una frequenza che nessun madrelingua userebbe (marcoilardi.it) |
| ottimizzare / ottimizzazione | migliorare / ridurre i costi / accelerare / (specificare cosa e di quanto) | Calco dall'inglese "optimize"; usato come verbo jolly senza specificare la metrica; fastweb e navigaweb lo citano nella lista dei top AI-tell italiani |
| massimizzare | aumentare / portare al massimo / (specificare con un numero) | Calco diretto dall'inglese "maximize"; suona artificioso in italiano; fastweb, navigaweb |
| agevolare | facilitare / aiutare / (verbo preciso) | Registro formale-burocratico usato dai LLM fuori contesto; fastweb, navigaweb |
| stimolante | (sostituire con una descrizione concreta) | Usato dai LLM come riempitivo positivo; fastweb lo elenca tra le parole AI-tipiche |
| peculiare | specifico / particolare / (concretizzare) | "Scelto solo per fare bella figura, ma spesso stona" — studenti.it; LLM lo usa per sembrare colto |
| imprescindibile | necessario / irrinunciabile / (specificare perché) | Enfasi vuota per evitare "importante"; studenti.it lo cita esplicitamente |
| dinamico | (eliminare o concretizzare) | Non significa nulla nella prosa non tecnica; fastweb |

**Tier 2 — Segnalare con frequenza ≥ 2×** (P2):

| Frase | Alternativa | Nota |
|---|---|---|
| inoltre | e / anche / (ristrutturare il periodo) | Il connettivo AI-overuse più documentato in italiano; tutte le fonti lo citano come primo indicatore |
| tuttavia | ma / eppure / (ristrutturare) | Connettivo formale sovraimpiegato; studenti.it, navigaweb, mysocialweb |
| pertanto | quindi / per questo / (riscrivere) | studenti.it: "suona come una frase fatta incollata meccanicamente" |
| di conseguenza | quindi / perciò / (riscrivere) | studenti.it, navigaweb |
| dunque | quindi / allora / (semplificare) | navigaweb |
| nonostante | anche se / pur / (riscrivere) | fastweb, navigaweb |
| probabilmente | (specificare il grado di certezza o eliminare) | Hedging generico AI; fastweb |
| efficiente / efficienza | veloce / economico / (metrica concreta) | Sempre da quantificare; fastweb |
| integrazione | (specificare cosa integra cosa e come) | Sostantivo jolly; fastweb |
| sfruttare / utilizzare / impiegare / avvalersi | (scegliere il verbo più preciso e usarlo coerentemente) | navigaweb: "si alternano senza motivo e nessuna variazione stilistica" — scambio di sinonimi senza logica stilistica |
| optare per | scegliere / preferire | Calco dall'inglese "opt for"; non naturale nell'italiano parlato; marcoilardi.it |
| garantire | assicurare / (cosa, specificamente) | Registro eccessivamente formale usato come jolly |
| un approccio | (eliminare e dire direttamente cosa si fa) | Costruzione vaga |
| nell'ambito di | in / per / con | Preposizione gonfiante; calco dal burocratese |
| al fine di | per | Costruzione burocratica che i LLM usano al posto del semplice "per" |
| in termini di | riguardo a / per quanto riguarda | Calco dall'inglese "in terms of" |
| a livello di | (eliminare o riscrivere) | Preposizione gonfiante |
| molteplici | molti / diversi / (numero concreto) | Formalismo vuoto |
| numerosi | molti / (numero concreto) | Evitare senza cifra; "numerosi vantaggi" → contarli |
| svariati | vari / diversi / (numero concreto) | Stessa logica |
| elevare il livello | migliorare | Calco dall'inglese "elevate the level"; marcoilardi.it lo cita come calco algoritmico |
| rivoluzionario | (specificare cosa cambia, per chi, e quando) | Inflazione di significato; citato insieme a "innovativo" e "trasformativo" in fonti italiane di rilevamento AI come aggettivi che "descrivono prodotti senza specificare i cambiamenti" — nessuna lista-parola italiana esplicita, segnalare solo per frequenza ≥ 2× |
| trasformativo | che cambia / che modifica / (concretizzare) | Calco dall'inglese "transformative"; marcoilardi.it documenta gli anglicismi algoritmici in italiano; nessuna lista-parola italiana lo cita esplicitamente, segnalare solo per frequenza ≥ 2× |
| ecosistema | (fuori biologia/tech: eliminare o concretizzare) | Metafora gonfiata documentata nel rilevamento AI in più lingue; per l'italiano non esiste ancora una fonte esplicita — segnalare solo in combinazione con ≥ 2 altri Tier-1 |

**Tier 3 — Frasi, segnalare ad alta densità** (≥ 2× la stessa frase, o ≥ 3 frasi Tier-3 diverse nel testo):

| Frase | Problema |
|---|---|
| "Nel mondo odierno…" / "Nel mondo di oggi…" | Apertura semanticamente vuota; documentata da tutte le fonti italiane come opener AI per eccellenza |
| "In un mondo sempre più connesso/digitale…" | Variante dell'apertura vuota; marcoilardi.it elenca oltre 100 varianti di questo pattern |
| "In un'epoca di…" / "Nell'era di…" | Stessa struttura di inquadramento temporale privo di contenuto |
| "In conclusione" / "Per concludere" | Chiusura AI stereotipata; citata da ogni fonte come marker primario — vedere P0 |
| "È importante sottolineare che…" | Marker di enfasi vuoto; navigaweb, mysocialweb |
| "Va notato che…" | Stesso problema |
| "È interessante notare che…" | navigaweb |
| "Un aspetto cruciale è…" | Apertura di paragrafo AI; più fonti |
| "Vale la pena menzionare…" | Hedging generico |
| "D'altro canto" | Falso bilanciamento anche quando non serve |
| "Allo stesso modo" / "Analogamente" | Connettivo di similarità usato meccanicamente; mysocialweb |
| "In primo luogo… In secondo luogo… Infine" | Struttura numerata rigida AI-tipica; mysocialweb |
| "Ogni [azienda/organizzazione/persona] è unica, e merita una strategia su misura" | Affermazione di Barnum; marcoilardi.it |
| "soluzione su misura" / "su misura per le tue esigenze" | Variante della dichiarazione di Barnum |
| "trasformazione digitale" | Fuori da contesto tecnico reale: cliché |
| "sostenibilità" / "sostenibile" | Fuori da contesto ambientale reale: buzzword vuoto |

---

## 42 Pattern nell'italiano

### Pattern di contenuto

| # | Pattern | Severità | Prima | Dopo |
|---|---|---|---|---|
| 1 | **Inflazione di significato** | P1 | "un'innovativa e rivoluzionaria soluzione per il settore" | "il software riduce i tempi di inserimento dati del 40%" |
| 2 | **Fonti vaghe** | P1 | "gli esperti affermano che…" / "studi dimostrano che…" | "secondo la ricerca del Politecnico di Milano 2024 (n=500)" |
| 3 | **Sfida formulaica** | P1 | "nonostante le sfide, l'azienda continua a crescere" | nominare la sfida specifica + risposta concreta |
| 4 | **Anglicismi algoritmici** | P1 | "ottimizzare", "massimizzare", "optare per", "elevare il livello" in cluster | verbi italiani naturali: migliorare, aumentare, scegliere, migliorare |
| 5 | **Affermazioni di Barnum** | P1 | "ogni cliente è unico e merita una soluzione personalizzata" | nominare il cliente specifico o eliminare |
| 6 | **Neuità gonfiata** | P2 | "un approccio che non avevo mai sentito prima" | "ha spiegato come X funziona in pratica" |

### Pattern linguistici

| # | Pattern | Severità | Prima | Dopo |
|---|---|---|---|---|
| 7 | **Vocabolario Tier 1/2** | P1/P2 | "rivoluzionario… fondamentale… garantire… agevolare…" | verbi e aggettivi diretti e concreti |
| 8 | **Copula evitata** | P1 | "funge da… si configura come… si pone come… si rivela essere… si sostanzia in…" | è / ha / fa / (verbo preciso) |
| 9 | **Catene di sinonimi** | P1 | "sfruttare… utilizzare… impiegare… avvalersi" nello stesso testo senza logica stilistica | scegliere il verbo più preciso e usarlo coerentemente |
| 10 | **Frasi di transizione come apertura** | P1 | "Inoltre…", "Tuttavia…", "Pertanto…", "Di conseguenza…", "Dunque…", "Nonostante ciò…", "A tal proposito…", "In tal senso…" | "e" / "ma" / ristrutturare il periodo |
| 11 | **Nominalizzazioni AI** | P2 | "procedere all'ottimizzazione di" / "effettuare un'analisi di" / "realizzare un'implementazione" | ottimizzare / analizzare / implementare |
| 12 | **Hedge-stacking** | P1 | "potrebbe eventualmente contribuire a facilitare" | un solo hedge basta; più hedge si annullano |
| 13 | **Falsa concessione** | P1 | "sebbene X presenti dei limiti, rimane straordinariamente efficace" | nominare il trade-off reale |
| 14 | **Falso contrasto** | P1 | "Non solo X, ma anche Y" / "Da un lato… dall'altro…" in eccesso | affermazione diretta positiva |
| 15 | **Locuzioni preposizionali gonfie** | P2 | "al fine di", "nell'ambito di", "in termini di", "a livello di", "in materia di" | "per", "in", "su", "riguardo a" |
| 16 | **Hedge-aggettivi a inizio frase** | P2 | "Fondamentalmente…", "Essenzialmente…", "In linea generale…", "In sostanza…" come inizio | eliminare o riformulare direttamente |
| 17 | **Falsa portata** | P2 | "dalla ricerca di base all'applicazione industriale" | elencare i temi reali trattati |

### Pattern strutturali

| # | Pattern | Severità | Prima | Dopo |
|---|---|---|---|---|
| 18 | **Apertura semanticamente vuota** | P0 | "Nel mondo odierno sempre più connesso e digitale, è fondamentale che…" | iniziare con la notizia o la tesi |
| 19 | **Chiusura AI obbligatoria** | P0 | "In conclusione, possiamo affermare che…" / "Per concludere…" | pensiero finale concreto o eliminare |
| 20 | **Em-dash (—) in eccesso** | P1 | uso sistematico del trattino lungo tipografico anglosassone | in italiano usare la virgola, il punto o il punto e virgola; fastweb e marcoilardi.it: "impiegato raramente nella scrittura italiana" |
| 21 | **Titoli in Title Case** | P2 | "Come Ottimizzare La Tua Strategia Di Marketing" | sentence case italiano: "Come ottimizzare la tua strategia di marketing" |
| 22 | **Staccato artificiale** | P1 | "È una sfida. Una rivoluzione. Una necessità." | periodi completi o riunire in un unico periodo |
| 23 | **Formattazione eccessiva** | P1 | grassetto ovunque, bullet list per ogni concetto, sezione "Conclusioni" obbligatoria | testo fluido, grassetto solo per termini tecnici chiave |
| 24 | **Liste a tre voci** | P2 | sempre esattamente 3 punti per lista, indipendentemente dal contenuto | lunghezza giustificata dal contenuto (2, 4, 5…); navigaweb, marcoilardi.it |
| 25 | **"N modi per…" / "N consigli su…"** | P2 | "5 motivi per cui…" / "10 strategie per…" come titolo o struttura | marcoilardi.it: "dominano nei testi automatici" |
| 26 | **Uniformità strutturale** | P1 | tutti i paragrafi con 3-4 frasi, tutte le frasi 15-25 parole, grammatica impeccabile | variare le lunghezze, inserire frasi brevi, andare al punto |
| 27 | **Intestazioni-inline in grassetto** | P1 | **"Velocità:** La piattaforma accelera…" | punto diretto in prosa |

### Pattern comunicativi

| # | Pattern | Severità | Prima | Dopo |
|---|---|---|---|---|
| 28 | **Opener chatbot** | P0 | "Certamente!", "Assolutamente!", "Certo!", "Con piacere!", "Sono lieto di aiutarti.", "Sono felice di rispondere." | rimuovere completamente |
| 29 | **Costruzioni "esploriamo insieme"** | P1 | "Esploriamo insieme…", "Scopriamo come…", "Analizziamo questo…", "Vediamo passo per passo…" | andare direttamente al punto |
| 30 | **Disclaimer da AI** | P1 | "In base alle informazioni disponibili fino a…", "Non ho accesso a dati in tempo reale…", "Secondo le mie conoscenze aggiornate a…" | eliminare o cercare fonti aggiornate |
| 31 | **Formule conclusive generiche** | P0 | "Il futuro appare promettente.", "Solo il tempo lo dirà.", "Siamo solo all'inizio.", "Tempi interessanti ci attendono.", "Restiamo sintonizzati." | conclusione concreta o eliminare |
| 32 | **Apertura riassuntiva AI** | P0 | "In conclusione, possiamo affermare che…", "Riassumendo quanto detto…", "Per riassumere…", "In sintesi…" come apertura di paragrafo conclusivo | rimuovere o riscrivere con un pensiero finale specifico |
| 33 | **Marker di enfasi AI** | P1 | "È importante sottolineare che…", "Va notato che…", "È interessante notare che…", "Merita attenzione il fatto che…", "Occorre precisare che…" | il fatto parli da solo |
| 34 | **Tono sycofantico** | P0 | "Ottima domanda!", "Hai assolutamente ragione!", "È un tema davvero importante.", "Grazie per questa domanda stimolante." | rimuovere completamente |
| 35 | **Loop di conferma** | P1 | "Come hai chiesto…", "Per rispondere alla tua domanda…", "La tua domanda è interessante perché…" | rispondere direttamente |
| 36 | **Tono emotivo piatto** | P2 | "Ciò che mi ha sorpreso di più…", "Sono rimasto affascinato da…" | guadagnare l'emozione con un fatto concreto o eliminarla |
| 37 | **Artefatti del processo di pensiero** | P1 | "Esaminiamo questo passo dopo passo", "Lasciami spiegare nel dettaglio", "Analizziamo sistematicamente:" | conclusione prima, poi ragionamento |

### Pattern meta

| # | Pattern | Severità | Prima | Dopo |
|---|---|---|---|---|
| 38 | **Struttura eccessiva** | P1 | 5 intestazioni in 200 parole, "Panoramica:", "Punti chiave:", "Conclusioni:" | unire sezioni, intestazioni specifiche |
| 38a | **Pattern lista-tre** | P2 | sempre esattamente 3 consigli, 3 argomenti, 3 passaggi — indipendentemente dal contenuto | liste con lunghezza giustificata dal contenuto; navigaweb, marcoilardi.it come standard output ChatGPT |
| 39 | **Ritmo uniforme** | P1 | tutti i paragrafi uguale lunghezza, tutte le frasi 15-25 parole | mescolare lunghe e brevi, inserire frammenti occasionali |
| 40 | **Over-Polishing** | P2 | prosa perfettamente uniforme, ogni irregolarità levigata | mantenere la naturale irregolarità |
| 41 | **Soglia rewrite-vs-patch** | — | 5+ flag Tier-1 + 3+ categorie di pattern + ritmo uniforme | raccomandare riscrittura completa, non rattoppare |

### Rilevamento strutturale (specifico dell'italiano)

| # | Pattern | Severità | Prima | Dopo |
|---|---|---|---|---|
| 42 | **Cluster Tier-3** | P1 | "innovazione", "trasformazione digitale", "sostenibile", "impatto" accumulati | sostituire con un'affermazione concreta; per frase: ≥ 2 occorrenze; come cluster: ≥ 3 frasi diverse |
| 43 | **Narrative future come chiusura** | P1 | "Potrebbe diventare uno dei temi più importanti del prossimo decennio" | versione falsificabile: "X raggiungerà Y entro 2027" oppure eliminare |
| 44 | **Bullet nudi senza verbo** | P1 | `• Performance stabili • Infrastruttura affidabile • Processi ottimizzati` | riscrivere in prosa o con affermazioni complete con verbo e dato concreto |
| 45 | **Cluster di anglicismi algoritmici** | P1 | 3+ parole calco dall'inglese nello stesso paragrafo (optare, ottimizzare, massimizzare, elevare il livello, garantire efficienza) | Treccani "IA-taliano" 2023: traccia dell'impronta algoritmica dell'inglese nei testi LLM italiani |

---

## Matrice di tolleranza

| Pattern | blog | tecnico | linkedin | email | accademico | istituzionale |
|---|---|---|---|---|---|---|
| Opener chatbot (P0) | No | No | No | No | No | No |
| Apertura vuota (P0) | No | No | No | No | No | No |
| Chiusura AI (P0) | No | No | No | No | No | No |
| Vocabolario Tier 1 | Rigido | "ottimizzare", "implementare" OK | Rigido | Medio | Rigido | Rigido |
| Vocabolario Tier 2 | Rigido | "garantire", "integrare" OK | Tollerante | Medio | Tollerante | Tollerante |
| Frasi di transizione | Rigido | Rigido | Tollerante | Tollerante | Medio | Medio |
| Em-dash (—) | No | No | No | No | No | No |
| Nominalizzazioni AI | Rigido | Medio | Rigido | Tollerante | Tollerante | Tollerante |
| Ritmo uniforme | Rigido | Medio | Tollerante | Tollerante | Medio | Medio |
| Chiusure generiche | No | No | No | No | No | No |

---

## Soglia rewrite-vs-patch

Se un testo mostra **5+ flag Tier-1** E **3+ categorie di pattern diverse** E **ritmo uniforme**: raccomandare una riscrittura completa. Nell'output spiegare esplicitamente perché rattoppare non basta.

---

## Formato di output

### Modalità Riscrittura

```
### Problemi trovati

[Nome pattern — P0/P1/P2]
> "[estratto di testo citato]"
Problema: [una riga di spiegazione]

[ulteriori voci…]

---

### Versione riscritta

[testo rielaborato in prosa]

---

### Cosa è cambiato

- [elenco puntato concreto di cosa è stato rimosso / sostituito / ristrutturato]

---

### Secondo passaggio

[Verifica della riscrittura per: frasi di transizione sopravvissute, nuovi flag Tier-1 introdotti durante la riscrittura, formule conclusive riciclate, ritmo uniforme]
Risultato: "Nessun ulteriore problema" OPPURE flag residui specifici con citazione testuale
```

### Modalità Rilevamento

```
### Problemi trovati

**P0 — Killer di credibilità**
- [Nome pattern]: "[citazione testuale]"

**P1 — Evidente odore di IA**
- [Nome pattern]: "[citazione testuale]"

**P2 — Revisione stilistica**
- [Nome pattern]: "[citazione testuale]"

---

### Valutazione

Problemi chiari: [elenco]
A discrezione: [elenco — cosa potrebbe essere un uso consapevole]
Raccomandazione: Riscrittura completa / Rattoppo dei punti singoli / Accettabile nel contesto
```

---

## Esempio completo

*Contesto scelto deliberatamente: comunicato stampa di una startup culturale italiana per il lancio di una piattaforma digitale di accesso al patrimonio — il tipo di testo in cui la densità AI si manifesta in italiano con maggiore evidenza e riconoscibilità. Non si tratta di un esempio tradotto da un'altra lingua.*

---

**Prima (generato da IA):**

> **Comunicato Stampa**
>
> **CulturaNext lancia la sua innovativa piattaforma digitale per democratizzare l'accesso al patrimonio culturale italiano**
>
> Nel mondo odierno sempre più connesso e digitale, è fondamentale che le istituzioni culturali adottino approcci innovativi per agevolare l'accesso al loro patrimonio. CulturaNext, startup italiana all'avanguardia nel settore della cultura digitale, è lieta di annunciare il lancio della sua nuova piattaforma, una soluzione rivoluzionaria che punta a trasformare radicalmente il modo in cui i cittadini fruiscono del patrimonio artistico e storico del nostro Paese.
>
> La piattaforma si pone come un ecosistema digitale dinamico e stimolante, che sfrutta le più avanzate tecnologie di intelligenza artificiale al fine di ottimizzare l'esperienza utente e massimizzare il coinvolgimento del pubblico. Grazie a un approccio olistico e trasformativo, CulturaNext è in grado di garantire un'integrazione fluida tra i contenuti digitali e le collezioni fisiche dei musei partner, agevolare la fruizione da parte di molteplici categorie di utenti e creare nuove sinergie tra istituzioni, ricercatori e appassionati.
>
> "È peculiare e imprescindibile, in questo momento storico, optare per soluzioni tecnologiche che elevino il livello della comunicazione culturale", ha dichiarato la CEO Francesca Monti. "Il nostro obiettivo fondamentale è democratizzare l'accesso alla cultura, un bene cruciale per la coesione sociale."
>
> Tuttavia, nonostante le sfide del settore, CulturaNext continua a crescere. Numerosi musei partner hanno già manifestato interesse, e la piattaforma è destinata a diventare un punto di riferimento imprescindibile nel panorama culturale italiano. In conclusione, il futuro della cultura digitale è promettente, e CulturaNext è pronta a guidare questa trasformazione.
>
> #CulturaDigitale #Innovazione #PatrimonioCulturale #Trasformazione #Startup

---

**Dopo (ripulito):**

> **Comunicato stampa**
>
> **CulturaNext apre l'accesso digitale a 120.000 opere di 14 musei italiani**
>
> CulturaNext, startup milanese fondata nel 2023, lancia oggi una piattaforma che permette di cercare, visualizzare e scaricare immagini ad alta risoluzione di 120.000 opere provenienti da 14 musei italiani, tra cui la Galleria degli Uffizi e il Museo Egizio di Torino. Le immagini sono disponibili gratuitamente per uso didattico; per uso commerciale il costo è 12 euro per singola opera.
>
> La piattaforma è nata da un'esigenza concreta: i musei ricevevano centinaia di richieste di immagini ogni mese e rispondevano via email, con tempi medi di tre settimane. Ora l'accesso è immediato. Nei primi trenta giorni di test con tre musei partner, le richieste evase sono passate da 180 a 1.400 al mese.
>
> "Ci siamo accorti che il collo di bottiglia non era la volontà dei musei di condividere, ma la burocrazia del processo", ha detto la CEO Francesca Monti. "Abbiamo automatizzato la gestione dei diritti e integrato i cataloghi esistenti senza chiedere ai musei di cambiare i propri sistemi."
>
> Entro fine anno CulturaNext punta a raggiungere 40 musei partner. La piattaforma è già disponibile all'indirizzo culturanext.it.

---

**Cosa ha trovato lo skill:**

- P0 Apertura vuota: "Nel mondo odierno sempre più connesso e digitale, è fondamentale che…"
- P0 Opener chatbot implicito: "è lieta di annunciare"
- P0 Chiusura generica: "il futuro della cultura digitale è promettente"
- P0 Chiusura AI: "In conclusione, il futuro della cultura digitale è promettente"
- P0 Hashtag-stuffing: 5 hashtag (#CulturaDigitale #Innovazione #PatrimonioCulturale #Trasformazione #Startup)
- P1 Inflazione di significato: "innovativa piattaforma", "soluzione rivoluzionaria", "trasformare radicalmente"
- P1 Anglicismi algoritmici: "ottimizzare", "massimizzare", "agevolare", "optare per", "elevare il livello" (5 calchi nello stesso testo)
- P1 Copula evitata: "si pone come", "è in grado di garantire"
- P1 Sfida formulaica: "nonostante le sfide del settore, CulturaNext continua a crescere"
- P1 Vaga fonte: "Numerosi musei partner hanno manifestato interesse" (senza numero)
- P1 Frasi di transizione come apertura: "Tuttavia…", "Grazie a…"
- P1 Em-dash (—): assente nell'originale ma sostituito da punto nel ripulito
- P1 Marker di enfasi AI: "È peculiare e imprescindibile, in questo momento storico"
- P1 Narrative futuro come chiusura: "destinata a diventare un punto di riferimento imprescindibile"
- P2 Vocabolario Tier 1: innovativo, fondamentale, cruciale, dinamico, stimolante, peculiare, imprescindibile, trasformativo, ecosistema (9 occorrenze)
- P2 Vocabolario Tier 2: sfruttare, agevolare (2×), garantire, integrare/integrazione, molteplici, numerosi, sinergie
- P2 Nominalizzazione AI: "la fruizione da parte di" invece di "usata da"
- P2 Bullet nudi (impliciti nella struttura del secondo paragrafo): tre funzioni elencate senza verbo principale

Sono 25+ marker IA in quattro paragrafi — la densità tipica di un comunicato stampa italiano scritto da LLM nel settore culturale/startup.
