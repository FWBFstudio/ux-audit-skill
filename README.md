# audit-ux

> A structured framing skill for website redesign projects. Forces strategic decisions before the first mockup and produces a defensible internal framing document.

**Status**: tested on multiple sites in real conditions before publication. Currently available in French. English translation contributions welcome.

**License**: to be determined. For now, free use, attribution appreciated.

---

## The scenario this skill solves

You receive a redesign brief from a client. The brief might be reduced to a single sentence or detailed across twenty pages. You may have heatmaps, you may not. The client may know what they want, or not. The available material is rarely complete and almost never what you would have hoped for.

This skill produces a solid framing document from this variable material, regardless of its initial quantity or quality. It asks the right questions at the right time, flags what's missing, forces the trade-offs you would tend to postpone, and concludes with a deliverable that serves as the foundation for art direction and pricing.

---

## What it does, what it doesn't do

**It does:**

- Force strategic decisions before any visual choice: no section plan without a tranched persona, no section plan without competitive analysis, no synthesis without a completeness check
- Challenge you when you take a shortcut, for example if you propose a solution before having truly diagnosed the problem, or if you skip the competitive analysis to jump straight to the mockup
- Protect you from classic framing mistakes: no confident claim about what a site doesn't have when you've only crawled part of it, no fabricated statistic, no finding that looks like a fact when it's actually a hypothesis
- Produce an internal framing document with a strategic verdict, a tranched persona, a target sitemap, a section plan, structural decisions, and a prioritized bug list scored by impact x effort

**It doesn't:**

- Generate a design system
- Write a brand strategy
- Replace user research
- Produce a commercial proposal or quote
- Estimate project timelines
- Audit WCAG compliance exhaustively

It does one thing well: framing, upstream of the redesign.

---

## Who it's for

This skill is designed for professionals handling a paid client redesign brief:

- Independent designers (web, brand, product)
- Studios and small agencies
- Freelance consultants in strategy or marketing
- In-house designers receiving briefs from internal stakeholders
- Solo brand strategists and consultants

It works regardless of your engagement format (project, retainer, mix) and regardless of your client's profile (startup, SME, institution, nonprofit).

It doesn't fit informal site critique, outbound prospecting audits, standalone competitive analysis, or informal self-audits. For these cases, the skill flags the mismatch and asks for confirmation before proceeding.

---

## Installation

> Instructions current as of April 2026. If you're reading this later, check the official Anthropic documentation. The exact mechanism may have evolved.

The skill can be installed in two environments depending on your use case: Claude.ai (web, mobile, desktop) and Claude Code (CLI). The mechanism differs in each case.

### For Claude.ai

Prerequisites: a Claude account (Free, Pro, Max, Team, or Enterprise plans) with *Code execution and file creation* enabled in `Settings > Capabilities`.

1. Clone this repo locally, or download the files as a ZIP archive from GitHub
2. Make sure the root folder is named `audit-ux` and contains the `SKILL.md` file at its root. The folder name must match the value of the `name` field in the SKILL.md frontmatter
3. Compress this folder into an `audit-ux.zip` file. The archive must contain the folder, not just the flat files
4. Go to `Customize > Skills` on Claude.ai
5. Click the "+" button, then *"+ Create skill"*, then select *"Upload a skill"*
6. Upload the ZIP file. The skill appears in your list, ready to be enabled with the toggle

Once installed, invoke the skill with `/audit-ux` at the start of a new conversation.

### For Claude Code

Prerequisites: Claude Code installed (the version supporting skills, released in beta late 2025).

```bash
# For a personal install (available across all your projects)
mkdir -p ~/.claude/skills
cd ~/.claude/skills
git clone https://github.com/YOUR-USERNAME/claude-audit-ux.git audit-ux

# Or for a project-specific install
cd /path/to/your/project
mkdir -p .claude/skills
git clone https://github.com/YOUR-USERNAME/claude-audit-ux.git .claude/skills/audit-ux
```

Claude Code automatically detects the skill and makes it available via `/audit-ux`. No restart needed as long as the `~/.claude/skills/` directory already existed when the session started.

### For the API

Skills are available through the Anthropic API's code execution tool. Refer to the [official API documentation](https://docs.claude.com/en/docs/intro) for integration details. The mechanism evolves regularly.

### Verify the installation worked

Start a new conversation (claude.ai or Claude Code) and type:

```
/audit-ux
```

The skill should respond with its initial introduction and start Phase 0 (mapping of the available material).

If nothing happens, see the troubleshooting section of the [Anthropic doc](https://support.claude.com/en/articles/12512180-use-skills-in-claude). Typically: code execution disabled, folder name not aligned with the `name` field in SKILL.md, or ZIP archive containing flat files instead of a folder.

---

## What methodological foundations it draws on

The skill draws on recognized references, organized into three tiers loaded on demand depending on the framing phase. None of these references is applied mechanically. The skill picks what serves the case and discards what isn't relevant.

**Tier 1, UX fundamentals and accessibility**

- Nielsen's heuristics
- UX laws (Hick, Fitts, Jakob, Miller, von Restorff, etc.)
- Krug's principles (scannability, hierarchy)
- Accessibility frameworks depending on legal context: WCAG 2.2, European Accessibility Act (EU), ADA (United States), AODA (Ontario), Section 508 (US federal), RGAA (France)

**Tier 2, Conversion and copywriting**

- Joanna Wiebe / Copyhackers (Voice of Customer method, PAS and 4U structures)
- Harry Dry / Marketing Examples (specific over vague, show don't tell)
- Alex Hormozi (value stack method, *$100M Offers*)
- Donald Miller (StoryBrand, the customer is the hero, the guide who reassures them)

**Tier 3, Positioning and differentiation**

- April Dunford (*Obviously Awesome*, competitive alternatives, market category)
- Strategyzer / Alexander Osterwalder (Value Proposition Canvas: jobs, pains, gains)

Each tier carries an explicit note on the cultural signature of its references. North American marketing frameworks (Hormozi, Miller) are flagged as such, and the skill invites you to filter them according to client context. A framing for a French artisanal manufacturer doesn't draw on the same tools as a framing for a B2B SaaS scale-up.

---

## How it works

### Invocation

```
/audit-ux
```

The skill triggers only on this explicit command. It doesn't react to generic UX questions or informal discussions about websites.

### Setup on first invocation

On your very first invocation, the skill detects that no professional posture is known and offers an optional calibration in three short questions:

1. What's the strategic conviction you carry, and don't negotiate, even when the client pushes back?
2. Which client category do you **not** serve, meaning those you know you can't serve well?
3. What's your primary engagement format: flat-fee project, retainer, mix, or other?

You can answer all three, some of them, or type *"skip"* to start in neutral posture. Your answers are stored for later sessions and color the recommendations.

### Going further: adjoining a descriptive file of your practice

The three-question calibration is a minimal entry. If you want the skill to truly color its recommendations according to your professional identity (positioning, creative references, identity anti-patterns, tone, etc.), you can adjoin a markdown file describing your studio, agency, or practice. The content of this file is yours. Write what matters to you.

Three ways to use it:

1. **Paste it at the beginning of a conversation.** When invoking `/audit-ux`, paste the content of your descriptive file just before. The skill will read it and integrate it into its posture for that session.

2. **Place it in a Claude.ai Project (Pro plan and above).** Create a Project dedicated to your client framings in Claude.ai, and place your descriptive file as a context document for the Project. It will be automatically loaded for every conversation initiated in that Project.

3. **Create a separate professional identity skill.** For users who want true modularity, create a second skill (for example `my-studio-identity`) that you activate alongside `audit-ux`. Claude will compose the two automatically.

### The five-phase workflow

Once invoked, the skill maps the project onto five phases and detects where you stand:

1. **Intake**: client brief, commanded scope, posture confirmation
2. **Existing site analysis**: screenshots, heatmaps if available, behavioral substitutes if not, technical check-up
3. **Competitive analysis**: two to three competitors, positioning
4. **Strategic questions**: geography, target mix, KPIs, persona, client's mental alternatives, governance changes, operational capacity
5. **Synthesis**: completeness check, choice between Track 1 (complete framing) and Track 2 (hypothetical framing with marked assumptions), then writing

The skill doesn't impose a linear sequence. It detects what you've shared, asks the questions of the relevant phase, and refuses to skip ahead when foundational matter is missing.

### Track 1 / Track 2: handling thin briefs

Briefs are often anemic in practice. The skill handles this reality with two tracks:

- **Track 1**: sufficient matter, firm decisions, deliverable defensible directly
- **Track 2**: partial matter, hypothetical framing with explicitly marked structural assumptions (H1, H2, etc.) to validate with the client before production

The deliverable header names the track used, allowing both client and you to assess the framing's reliability at a glance.

### Deliverable

The skill produces a markdown framing document containing:

- Strategic verdict (one page max): what's wrong, what should stay, the strategic bet, scope extension recommendation if needed
- Tranched main persona: one or two personas with the differentiation axis chosen for the context
- Target sitemap: pages added, removed, merged, with justifications
- Section plan: homepage plus two to three critical funnel pages
- Non-negotiable structural decisions: five to eight choices that orient art direction
- Critical bug list with impact x effort scoring and corrective timing
- Handoff to art direction: identity constraints, structural constraints, sectoral and identity anti-patterns to exclude

This document is internal. It serves as the foundation for art direction, pricing, and the formal commercial proposal. It's not designed to be sent as-is to the client.

---

## Downstream pipeline

`audit-ux` is the first stage of a three-tier pipeline:

```
audit-ux                 →    Strategic framing
                               ↓
UI/UX Pro Max            →    Design system generation
(or equivalent)                ↓
Vercel Web Interface     →    UI code review
Guidelines (or equivalent)    
```

`audit-ux` doesn't replace the downstream tools. It feeds them with strategic decisions. A design system generator launched without prior strategic framing produces plausible but generic propositions. The dedicated section in the deliverable (handoff to art direction) is designed to feed those generators with constraints from the framing.

---

## What's in the repo

```
audit-ux/
├── SKILL.md                              Main skill manifest
├── assets/
│   └── template-cadrage.md               Deliverable template
└── references/
    ├── questions-par-phase.md            Question catalog by phase
    ├── regles-redactionnelles.md         Seven rigor rules
    ├── anti-patterns-universels.md       Universal web anti-patterns
    ├── fondamentaux-ux.md                Nielsen, UX laws, Gestalt, accessibility
    ├── frameworks-conversion.md          Wiebe, Dry, Hormozi, Miller, Cialdini, Schwartz, Heath
    └── frameworks-positionnement.md      Ries & Trout, Dunford, VPC, JTBD, Moore, Godin
```

The skill is built around modular references. The main SKILL.md is sized for fast loading. References are loaded on demand by phase, never systematically.

---

## Known limitations

- **Language**: the internal content is in French. English speakers can use the skill but will get French-language deliverables. English translation is on the roadmap.
- **Cultural signature**: tier 2 and tier 3 marketing frameworks carry a predominantly North American copywriting culture. The skill flags this and invites filtering by client context.
- **Not a substitute for user research**: the skill works on the material you provide it. If you need user evidence, conduct interviews separately.
- **Not a substitute for personal strategic counsel**: the skill encodes a method, not your perspective. The initial calibration or an adjoined identity file brings your perspective in. Without either, the skill produces correct but relatively neutral framings.
- **Accessibility treated as structural direction**: not as a formal compliance audit. For a legal compliance check, commission a dedicated separate audit.
- **Markdown output**: no direct generation in Word, Notion, or PDF. Conversion is straightforward but manual.

---

## Contributing

Most useful contributions, in order of priority:

- Help translating SKILL.md, the template, and the references into English
- Test cases of distinct profiles with permission to publish anonymized post-mortems
- Sectoral anti-patterns to add to the universal list, with clear justification
- Professional identity skill templates as examples
- Translations of the cultural notes for non-Western contexts

---

## Note from the author

This skill exists because I made the mistakes it now prevents. I started redesign projects without enough framing depth, patched along the way with assumptions, and delivered work that was correct but not sharp. The skill is what I wish I had had ten years ago, encoded so I no longer have to remember it under pressure.

— Yann
