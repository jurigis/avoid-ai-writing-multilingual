# avoid-ai-writing — Multilingual Skills

Language-specific versions of the [avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) skill by Conor Bronsdon (MIT licence), extended to languages beyond English.

Each `SKILL-XX.md` file is grounded in **statistically documented, language-native AI writing patterns** — not translated from English. Every flagged word or phrase must be traceable to a real source showing it is over-represented in LLM output for that specific language.

---

## Available Languages

| File | Language | Version | Status | Key context |
|---|---|---|---|---|
| [SKILL-DE.md](SKILL-DE.md) | German (Deutsch) | 2.1.0 | ✅ Ready | LinkedIn / New Work / corporate comms |
| [SKILL-RO.md](SKILL-RO.md) | Romanian (Română) | 1.0.0 | ✅ Ready | NGO / EU-funded project communication |
| [SKILL-IT.md](SKILL-IT.md) | Italian (Italiano) | 1.0.0 | ✅ Ready | Cultural institution communication / startup press releases |
| [SKILL-FR.md](SKILL-FR.md) | French (Français) | 1.0.0 | ✅ Ready | Management memos / Grandes Écoles / LinkedIn |

Planned: Spanish (`SKILL-ES.md`) — PRs welcome.

---

## What a skill does

You give it text. It:

1. **Flags** every AI writing pattern it finds (severity P0 / P1 / P2)
2. **Rewrites** the text with those patterns removed (default mode)
3. **Runs a second pass** on its own rewrite to catch patterns it introduced
4. Optionally runs in **detect-only** mode — flags without rewriting

Patterns covered include: chatbot openers, generic conclusions, semantic inflation, synonym chains, structural uniformity, excessive hedging, EU/management jargon substituting for content, and language-specific statistical tells (e.g. calques from English in Romanian, Nominalstil clusters in German).

---

## How to Install

### A · Claude Code (CLI and VS Code / JetBrains extensions)

Skills live in `.md` files. The `name:` field in the frontmatter becomes the slash command.

**Global install** — available in every project:
```bash
# macOS / Linux
mkdir -p ~/.claude/skills
cp SKILL-DE.md ~/.claude/skills/avoid-ai-writing-de.md
cp SKILL-RO.md ~/.claude/skills/avoid-ai-writing-ro.md
cp SKILL-IT.md ~/.claude/skills/avoid-ai-writing-it.md
cp SKILL-FR.md ~/.claude/skills/avoid-ai-writing-fr.md

# Windows (PowerShell)
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills"
Copy-Item SKILL-DE.md "$env:USERPROFILE\.claude\skills\avoid-ai-writing-de.md"
Copy-Item SKILL-RO.md "$env:USERPROFILE\.claude\skills\avoid-ai-writing-ro.md"
Copy-Item SKILL-IT.md "$env:USERPROFILE\.claude\skills\avoid-ai-writing-it.md"
Copy-Item SKILL-FR.md "$env:USERPROFILE\.claude\skills\avoid-ai-writing-fr.md"
```

**Project install** — available only in the current repository:
```bash
mkdir -p .claude/skills
cp SKILL-DE.md .claude/skills/
cp SKILL-RO.md .claude/skills/
cp SKILL-IT.md .claude/skills/
cp SKILL-FR.md .claude/skills/
```

After installing, invoke in any Claude Code conversation:
```
/avoid-ai-writing-de
/avoid-ai-writing-ro
/avoid-ai-writing-it
/avoid-ai-writing-fr
```

---

### B · Claude.ai Web — Projects (recommended for web use)

Claude Projects let you attach a persistent system prompt to a conversation thread.

1. Open [claude.ai](https://claude.ai) → **Projects** → **New Project**
2. Click **Project Instructions**
3. Paste the full content of `SKILL-DE.md` or `SKILL-RO.md`
4. Name the project (e.g. "AI Writing Reviewer — German")
5. Every new conversation inside this project applies the skill automatically

> **Tip:** Create one project per language. You can switch between them from the sidebar.

---

### C · ChatGPT Web — Custom GPTs

1. Go to [chatgpt.com](https://chatgpt.com) → **Explore GPTs** → **Create**
2. Switch to the **Configure** tab
3. Paste the full content of `SKILL-XX.md` into the **Instructions** field
4. Set a name, e.g. "AI Writing Detector – German"
5. Save → **Only me** (private) or share the link

The YAML frontmatter block at the top of the file is harmless — ChatGPT will treat it as plain text context. You can remove the `---` block if you prefer a clean paste.

---

### D · Cursor

**As a project rule** (recommended):
1. Create the file `.cursor/rules/avoid-ai-writing-de.mdc` in your project
2. Add this header, then paste the skill content below it:
   ```
   ---
   description: Detect and remove AI writing patterns in German text
   globs:
   alwaysApply: false
   ---
   ```
3. Strip the original YAML frontmatter from the pasted content (Cursor has its own)

**As a global rule:**
Cursor Settings → **Rules for AI** → paste the skill content.

---

### E · GitHub Copilot / Codex (VS Code)

1. Create `.github/copilot-instructions.md` in your repository
2. Paste the skill content there

Copilot will apply these instructions to all Copilot Chat conversations in that workspace. For per-file context, add the skill as a referenced file in a Copilot Chat prompt:
```
#file:.claude/skills/avoid-ai-writing-de.md

Review this text: [your text]
```

---

### F · Windsurf, Zed, or any other AI editor

Paste the skill content into the system prompt / custom instructions field of your AI assistant configuration. Most editors expose this as "AI Instructions", "System Prompt", or "Custom Rules".

---

### G · Ad-hoc (any chat interface)

Copy the full file content and paste it at the start of your conversation, then add your text:

```
[paste full SKILL-XX.md content]

---

Now review the following text:

[your text here]
```

---

## How to Use

### In Claude Code

| Invocation | Effect |
|---|---|
| `/avoid-ai-writing-de` | Paste or type text → rewrite mode |
| `/avoid-ai-writing-de` + `"nur prüfen:"` | Detect-only, no rewrite |
| `/avoid-ai-writing-ro` | Romanian rewrite mode |
| `/avoid-ai-writing-ro` + `"doar marcare:"` | Romanian detect-only |
| `/avoid-ai-writing-it` | Italian rewrite mode |
| `/avoid-ai-writing-it` + `"solo verifica:"` | Italian detect-only |
| `/avoid-ai-writing-fr` | French rewrite mode |
| `/avoid-ai-writing-fr` + `"seulement flaguer:"` | French detect-only |

You can also add a context hint to adjust tolerance:

```
/avoid-ai-writing-de linkedin

[text]
```

Available context profiles per language:

| Profile | DE | RO | IT | FR |
|---|---|---|---|---|
| `blog` | ✅ | ✅ | ✅ | ✅ |
| `technical` / `tehnic` / `tecnico` / `technique` | ✅ | ✅ | ✅ | ✅ |
| `linkedin` | ✅ | — | ✅ | ✅ |
| `email` | ✅ | ✅ | ✅ | ✅ |
| `academic` / `accademico` / `académique` | ✅ | ✅ | ✅ | ✅ |
| `pressemitteilung` / `comunicat` / `comunicato` / `communiqué` | ✅ | ✅ | ✅ | ✅ |
| `social` | ✅ | ✅ | ✅ | ✅ |
| `management` | — | — | — | ✅ |
| `ong` | — | ✅ | — | — |
| `istituzionale` | — | — | ✅ | — |
| `tesi` | — | — | ✅ | — |

### In web tools (Claude Projects, Custom GPTs)

Just paste your text. No slash commands needed — the system prompt is always active.

To switch modes:
- **Rewrite (default):** paste text and send
- **Detect only:** start your message with `"nur prüfen:"` (DE) or `"doar marcare:"` (RO)
- **Context hint:** start with `"context: academic"` or the equivalent

---

## How to Add a New Language

### The one-line prompt

Paste this into Claude Code (or any AI with access to this repository):

```
Create SKILL-ES.md for Spanish. Follow the process in CLAUDE.md exactly.
Research sources first — do NOT write from memory or translate from English.
Search in Spanish, not in English. Use SKILL-DE.md as the structural reference.
```

Replace `ES` / `Spanish` with your target language and ISO 639-1 code.

### What the process produces

The process defined in [CLAUDE.md](CLAUDE.md) requires:

1. **Web research in the target language** — at least 3 independent source types:
   - Wikipedia community page for the target language
   - Native SEO / content blogs on AI text detection
   - Academic papers on AI text detection in multilingual settings
   - Practitioner reports (editors, journalists, content agencies)

2. **Language-native vocabulary table** (Tier 1 / 2 / 3) — no pattern is included unless a source shows it is statistically over-represented in LLM output for that language

3. **40+ documented patterns** — structured as: pattern name · severity · before/after example

4. **A culturally authentic full example** — drawn from the context where AI text appears most densely in that language (e.g. LinkedIn for German, NGO press releases for Romanian, management memos for French)

5. **`sources/XX-sources.md`** — all citations with URLs, dates, and which patterns they support; gaps explicitly noted

### Quality checklist (before opening a PR)

- [ ] All Tier-1 words have a cited source
- [ ] No Tier-1 word is just "bad style" — it must be a documented LLM statistical tell
- [ ] The full example is language-native, not a translation
- [ ] Context profiles match real text types of that language region
- [ ] Tolerance matrix is filled in
- [ ] Severity grades (P0/P1/P2) are assigned in all pattern tables
- [ ] Version is set to `1.0.0`

---

## Project Structure

```
/
├── SKILL-DE.md             ← German (v2.1.0, source-verified)
├── SKILL-RO.md             ← Romanian (v1.0.0, source-verified)
├── SKILL-IT.md             ← Italian (v1.0.0, source-verified)
├── SKILL-FR.md             ← French (v1.0.0, source-verified)
├── CLAUDE.md               ← Authoring instructions (how to create new skills)
├── README.md               ← This file
└── sources/
    ├── DE-sources.md       ← Citations for German patterns
    ├── RO-sources.md       ← Citations for Romanian patterns
    ├── IT-sources.md       ← Citations for Italian patterns
    └── FR-sources.md       ← Citations for French patterns
```

---

## Design Principles

- **Statistically grounded, not opinionated.** Patterns are included only when sources show they are over-represented in LLM output for that language. General bad style is not a KI tell.
- **Language-native.** English patterns are not translated. Each language has its own statistical anomalies (e.g. Romanian calques from English, German Nominalstil clusters, French management jargon and impersonal distancing formulas).
- **Context-aware.** Technical writing, academic prose, and legal documents have different baselines. The skill adjusts its strictness by context profile.
- **Severity-graded.** P0 patterns are always removed. P1 patterns are usually removed. P2 patterns are evaluated in context.

---

## License

MIT — based on [avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) (v3.4) by [Conor Bronsdon](https://github.com/conorbronsdon/avoid-ai-writing).  
Multilingual adaptations by Jürgen Kraus.
