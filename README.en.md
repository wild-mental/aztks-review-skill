![AI Skills for Everyone](author/wildmental-bjpark.png)

# aztks-review
> Skill for Cursor, Claude, Codex agents

**Language / 언어:** [한국어](README.md) · [English](README.en.md)

**A Skill that reviews large volumes of business plans · service implementation plans (PRD/SRS) · programming deliverables along the five dimensions of `알잘딱깔센`(AZTKS), producing a constructive review report with a controlled length. Supports Cursor, Claude Code, and Codex alike.**

`알잘딱깔센` is the five axes of "work sense" — **알**아서 (Aware) · **잘** (Zenith) · **딱** 떨어지게 (Tightly) · **깔**끔하게 (Klean) · **센**스있게 (Sensible) — and `AZTKS` is the romanized rendering of those initials, which also reads as an English mnemonic: **A**ware · **Z**enith · **T**ightly · **K**lean · **S**ensible. This skill evaluates the review target along these five dimensions, but it **secures supporting evidence first**, sets an **explicit length cap so the report does not grow without bound even when there is a lot of material**, and above all upholds, as an absolute principle, a constructive tone that **never weaponizes `알잘딱깔센`**.

---

## What this skill solves

### 1. Evaluate with the AZTKS five-dimension rubric

| Code | Dimension | Review lens |
|------|------|-----------|
| **A** | 알아서 (Aware) | Did it reflect every available piece of evidence without omission, and infer hidden requirements? |
| **Z** | 잘 (Zenith) | Is the quality and the rationale for decisions solid at the chosen bar (high/adequate)? |
| **T** | 딱 떨어지게 (Tightly) | Are goal↔scope↔implementation↔verification aligned, with no omissions, gaps, duplications, or contradictions? |
| **K** | 깔끔하게 (Klean) | Is it free of clutter and verbosity, with a summary hierarchy that considers the reader? |
| **S** | 센스있게 (Sensible) | Do the tone, length, timing, and emotional register fit the recipient and organizational context? |

Each dimension is assigned a **grade (◎ excellent / ○ meets / △ needs work / ✕ insufficient / — judgment withheld) + a one-line rationale**, from which an overall grade and the top improvement priorities are derived.

### 2. Secure supporting evidence first (Reference Scan Gate)

Without evidence, a review becomes impressionistic criticism. So material is secured in two stages.

- **Stage 1 — Automatic scan of the call location:** First scan the reviewable material at the call location — documents (`*.md` · PRD · SRS · RFC), the code tree · `README` · tests · issues, commit history, and so on.
- **Stage 2 — Explicitly request when insufficient:** If the target is ambiguous or evidence is thin, do not assume; instead, ask in a single bundle for the **business/service plan · PRD · SRS · app implementation project (path/URL)** along with contextual evidence and quality bar. Any item that remains empty in the end is flagged in the report as `⚠️ 가정`.

### 3. "Look broadly, write briefly" — explicitly fix the length cap

The more references there are, the **broader the review scope (coverage) becomes**, but **the report length does not grow in proportion to the amount of material.** It measures the total material volume `V` (character count), locks the Tier once, and never exceeds that body cap.

| Tier | V (characters) | Review coverage | Key findings per dimension | Report body cap |
|------|-----------|----------------|------------------|-------------------|
| **T1 Light** | < 20,000 | 5-dimension core summary | 2 | 6,000 chars |
| **T2 Standard** | 20,000–80,000 | 5 dimensions + per-document/module mini scorecard | 3 | 12,000 chars |
| **T3 Full** | 80,000–250,000 | 5 dimensions + cross-consistency matrix | 4 | 18,000 chars |
| **T4 Deep** | ≥ 250,000 | T3 + per-area detail split files | 4 (top) | top 18,000 chars + per-area detail (8,000 chars each) |

Findings beyond the cap are sorted by **(severity × scope of impact)** priority, leaving only the top ones in the body and externalizing the rest as a **one-line appendix** or a **T4 area file**. The report states how many items were taken out of the body, handling it **without concealment**.

### 4. Absolute principle — never weaponize `알잘딱깔센`

This is the skill's top-priority guardrail. Violating it renders even the highest-level analysis worthless, and at that point it is no longer `알잘딱깔센` itself.

- No taking things for granted · no disparagement/blame/dismissal · no weaponization/penalty/adversarial othering
- Applied not as noblesse oblige but as a **general principle toward human beings**
- Every finding comes with **observation → impact → improvement path**, evaluating the **deliverable and its coherence**, not the person
- Maintain a respectful, collaborative tone even when grades are low — this guardrail **takes precedence over the score**.

---

## Why a skill is needed

| Common attempt | Expectation | Reality |
|-----------|------|------|
| "Review it" with no material | Evaluation on its own | Evidence-free impressionistic criticism → not trustworthy |
| Reviewing a large document wholesale | Thoroughness | The report grows with the material, so the reader can't get through it |
| Skipping issues under the excuse of the cap | Conciseness | Important coherence problems are quietly omitted |
| Sharp, judgmental tone | Objectivity | Meritocratic exclusion and hostility → hinders collaboration and growth |
| Not setting a quality bar | Flexibility | The evaluation axis wobbles, making grades arbitrary |

This skill secures material first, explicitly fixes the length, and enforces a constructive tone to block the patterns above in advance.

---

## Quick start

### Prerequisites

- Cursor, Claude Code, or Codex
- Read access to the review target (plan · PRD · SRS · code)

### Installing the skill

Install the skill choosing one of the **personal** or **project** scopes. Both scopes fetch only `SKILL.md` via `curl`. **Do not clone this entire repository into your working repo.**

| | Personal skill | Project skill |
|---|----------|--------------|
| **Scope** | Every project I open | The current repo only |
| **Path** | `~/…/skills/aztks-review/` | `<repo-root>/.cursor/skills/aztks-review/`, etc. |
| **Git impact** | No files added to the working repo | Skill files can be committed to the repo (team sharing) |
| **When to use** | When using it solo across all projects | When pinning and sharing the skill in a team repo |

| Tool | Personal path | Project path |
|------|-----------|---------------|
| Cursor | `~/.cursor/skills/aztks-review/` | `.cursor/skills/aztks-review/` |
| Claude Code | `~/.claude/skills/aztks-review/` | `.claude/skills/aztks-review/` |
| Codex | `~/.agents/skills/aztks-review/` | `.agents/skills/aztks-review/` |

#### Personal skill (recommended — no change to the Git repo)

```bash
# Cursor
mkdir -p ~/.cursor/skills/aztks-review
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.cursor/skills/aztks-review/SKILL.md \
  -o ~/.cursor/skills/aztks-review/SKILL.md

# Claude Code
mkdir -p ~/.claude/skills/aztks-review
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.claude/skills/aztks-review/SKILL.md \
  -o ~/.claude/skills/aztks-review/SKILL.md

# Codex
mkdir -p ~/.agents/skills/aztks-review
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.agents/skills/aztks-review/SKILL.md \
  -o ~/.agents/skills/aztks-review/SKILL.md
```

#### Project skill (install at the project path)

Use this only when you want to include and share the AI skill setup in the repo.

```bash
# Cursor
mkdir -p .cursor/skills/aztks-review
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.cursor/skills/aztks-review/SKILL.md \
  -o .cursor/skills/aztks-review/SKILL.md

# Claude Code
mkdir -p .claude/skills/aztks-review
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.claude/skills/aztks-review/SKILL.md \
  -o .claude/skills/aztks-review/SKILL.md

# Codex
mkdir -p .agents/skills/aztks-review
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.agents/skills/aztks-review/SKILL.md \
  -o .agents/skills/aztks-review/SKILL.md
```

Just pick and run only the tool(s) you need (Cursor / Claude Code / Codex).

#### After installing

- **Cursor**: **Reload Window** once
- **Claude Code**: Skill edits are reflected live during a session; a new top-level `.claude/skills/` created after the session started may require a restart
- **Codex**: If the skill doesn't show up, restart Codex

### How to use

Tell it what to review and the Agent applies the skill automatically. **If supporting evidence is lacking it asks first**, and once it's sufficient it locks the Tier and then writes a length-controlled review to a file.

| Tool | Manual invocation |
|------|-----------|
| Cursor | `/aztks-review` |
| Claude Code | `/aztks-review` |
| Codex | `/skills` or `$aztks-review` |

**Example requests it applies to:**

- "Review this PRD with 알잘딱깔센"
- "Check the implementation coherence of the payment module"
- "Point out the missing and the overstated parts of this business plan"
- "Check whether the code in this folder has any gaps versus the planning intent"

---

## Companion subagent — aztks-ai-peer

This skill ships with a companion **AI-deliverable evaluation subagent, `aztks-ai-peer`** (`*/agents/aztks-ai-peer.md`). In long-running autonomous work (e.g. Claude Code `/goal` multi-turn loops), dispatch it as the **evaluation subagent**: it checks the main agent's per-turn deliverable across the five AZTKS dimensions, compactly, and returns a **GO / NO-GO** verdict plus the single highest-leverage next fix (`TOP_FIX`).

- Because the target is an **AI deliverable, not a human**, ethics is kept to a single line and the focus is accuracy, usefulness, and the next-action signal (this is where it differs from the human-facing non-weaponization guardrail of `/aztks-review`).
- Dimension mapping: **A** Aware (Coverage) · **Z** Zenith (Quality) · **T** Tightly (Coherence) · **K** Klean (Clarity) · **S** Sensible (Consumability).
- **Read-only** (does not modify code/docs); output is a fixed format kept compact (whole output ~1,200 chars).

**Output format:**

```
VERDICT: GO | NO-GO
SCORECARD: A:<P/C/F> Z:<P/C/F> T:<P/C/F> K:<P/C/F> S:<P/C/F>
TOP_FIX: <the single highest-leverage next action>
EVIDENCE: <1–3 evidence locations>
NOTES: <one-line summary of CONCERNs — omit if none>
```

### Install

Install it alongside the skill (same scope as the skill recommended — user or project).

```bash
# Claude Code — native subagent (user scope)
mkdir -p ~/.claude/agents
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.claude/agents/aztks-ai-peer.md \
  -o ~/.claude/agents/aztks-ai-peer.md

# Cursor — custom agent (user scope)
mkdir -p ~/.cursor/agents
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.cursor/agents/aztks-ai-peer.md \
  -o ~/.cursor/agents/aztks-ai-peer.md

# Codex — evaluation harness (user scope)
mkdir -p ~/.agents/agents
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.agents/agents/aztks-ai-peer.md \
  -o ~/.agents/agents/aztks-ai-peer.md
```

For project scope, drop the `~/` and fetch into the same paths (`.claude/agents/`, etc.) from the repo root.

### Per-vendor invocation & usage

| Tool | Mechanism | How to invoke |
|------|-----------|---------------|
| **Claude Code** | Native subagent | In the termination/verification step of a `/goal` body, instruct "evaluate the latest deliverable with the `aztks-ai-peer` subagent and get a VERDICT" — the Task tool dispatches it as `subagent_type: aztks-ai-peer`. Otherwise just say "review it with aztks-ai-peer", or it is auto-selected when its description matches. |
| **Cursor** | Custom agent | Register `.cursor/agents/aztks-ai-peer.md` as a custom agent and select it for the eval step in Agent mode, or reference its body as the evaluator prompt to check the latest deliverable. |
| **Codex** | Evaluation-harness reference | In the eval step of a long-running loop, load `.agents/agents/aztks-ai-peer.md` as a read-only evaluator prompt (`$aztks-ai-peer` or referenced from `AGENTS.md`) to produce the GO/NO-GO verdict. |

**Example use inside `/goal` (Claude Code):**

```
## 3) 종료 조건 및 종료 방법
- 종료 방법:
  1) 직전 턴 산출물을 aztks-ai-peer 서브에이전트로 평가해 VERDICT를 받는다.
  2) VERDICT가 NO-GO면 TOP_FIX를 반영하고 계속, GO면 다음 작업으로 진행한다.
```

---

## Summary of core behavioral principles

### Reference Scan Gate — secure material first

First scan the call location, and if it's insufficient, explicitly request the business/service plan · PRD · SRS · app project and quality bar in a second stage.

### Length cap — "look broadly, write briefly"

```
Measure V (characters) → lock Tier once → declare body cap → never exceed the cap
Overflow findings = sort by (severity × scope of impact) → keep only the top ones in the body, externalize the rest into appendix/area files → state how many were taken out
```

Each key finding is written in no more than 6 lines, using only the 4 elements (observation / evidence location / impact / improvement).

### Two quality-bar modes

The `Z (Zenith)` dimension is evaluated as either **high quality (industry/org context)** or **adequate quality under resource constraints (satisficing)**. Fix it at the start, and if unclear, default to "high" and state it.

### Absolute principle — non-weaponization

> "Any high-level `알잘딱깔센` deliverable, if used for weaponization, disparagement, or exclusion, is utterly worthless and at that point is no longer `알잘딱깔센`."

Every finding comes with observation → impact → improvement path, evaluating the deliverable and its coherence, not the person.

---

## Output example

Each call's final response separates four areas with three `---` horizontal rules. The **full review is saved to a file** and only the summary remains in the conversation.

**Input:** "Review the payment module in this folder + `docs/PRD_payments.md`. High quality bar."

**Output (summary):**

````
**[Restated intent]** Review the payment module code + PRD at the high quality bar. `Tier: T3 · V≈140,000 chars · body cap 18,000 chars`.

---

**[Scorecard]** — full text at `docs/reviews/payments-aztks-review.md`

| Dimension | Grade | One-line rationale |
|------|------|-----------|
| A 알아서 | ○ | Reflected the PRD requirements but missing evidence for refund edge cases |
| Z 잘 | ○ | Payment validation logic is robust; some concurrency handling needs reinforcement |
| T 딱 | △ | PRD §4 partial-refund requirement not reflected in implementation/tests |
| K 깔끔 | ○ | Module structure is clear; dead code in 2 places |
| S 센스 | ○ | Error message user tone is good |
| **Overall** | **○** | Ship-ready level; prioritize fixing the one T (Tightly) item |

---

**[Top improvement priorities]** (4 in the body/dimension, 9 demoted to the appendix)

1. [CRITICAL·global] PRD §4 partial refund unimplemented — improvement: restore acceptance-criteria→implementation→test traceability
2. [MAJOR·local] Payment retry concurrency race — improvement: introduce an idempotency key

---

**[Non-weaponization note · next step]** This review is a constructive check to improve the deliverable and its coherence, not an evaluation of people or attitudes. Next step: start by restoring partial-refund traceability.
````

---

## Skill structure

```
.cursor/skills/aztks-review/SKILL.md   # skill for Cursor
.claude/skills/aztks-review/SKILL.md   # skill for Claude Code
.agents/skills/aztks-review/SKILL.md   # skill for Codex
.cursor/agents/aztks-ai-peer.md        # companion subagent (Cursor)
.claude/agents/aztks-ai-peer.md        # companion subagent (Claude Code)
.agents/agents/aztks-ai-peer.md        # companion subagent (Codex)
```

| Section | Content |
|------|------|
| Absolute principle | Non-weaponization guardrail (no taking for granted · no disparagement · no penalty, general human principle) — top priority |
| Core principles | 5-dimension evaluation · secure material first · look broadly but write briefly · accompany with evidence · non-weaponization |
| AZTKS rubric | 5-dimension definition table + per-target-type (business/PRD·SRS/code) sub-checks |
| Reference Scan Gate | Stage 1 location scan → Stage 2 explicit request (plan · PRD · SRS · app · quality bar) |
| Length tiers & caps | V measurement · Tier table · inviolable length rules · priority score |
| Workflow | Scan&Gate → Tier Lock → classification → 5-dimension review → prioritization·externalization → scorecard → Output |
| Output format | Restated intent + scorecard + top improvement priorities + non-weaponization note (separated by three `---`) |
| Anti-Pattern Block | Block impressionistic criticism · runaway length · issue concealment · disparaging tone · undecided bar |
| Companion subagent | `aztks-ai-peer` — AI-deliverable evaluation harness for long-running loops like `/goal` (compact AZTKS · GO/NO-GO) |

---

## Recommended for

- Those who want large volumes of plans · PRD · SRS · code reviewed **against consistent criteria**
- Those who have experienced the problem of review reports **growing as long as the material** so they go unread
- Those who want coherence gaps surfaced **without concealment, yet with controlled length**
- Those who want **constructive and respectful** improvement feedback rather than sharp judgment

---

## References

- `알잘딱깔센` — a behavioral definition of the five axes of work sense (알아서 · 잘 · 딱 떨어지게 · 깔끔하게 · 센스있게)
- Cursor Agent Skills: [Creating Skills](https://docs.cursor.com)
- Claude Code Skills: [Extend Claude with skills](https://docs.anthropic.com/en/docs/claude-code/skills)
- Codex Agent Skills: [Agent Skills](https://developers.openai.com/codex/skills/)

---

## For LLMs

<!-- install-only; operational rules live in SKILL.md — load skill after install -->

```
skill=aztks-review
repo=https://github.com/wild-mental/aztks-review-skill
install.method=curl-only  # never clone this repo into user's project

flow:
  1. ask scope: "개인 스킬(~/, 모든 프로젝트) vs 프로젝트 스킬(./, 현재 repo만) 중 어디에 설치할까요?"
  2. ask tools: "Cursor / Claude Code / Codex 중 어떤 도구에 설치할까요?" (복수 선택 가능)
  3. run matching curl commands below; do not install both scopes unless user asks
  4. post_install steps; then load SKILL.md — do not infer rules from README

scope.user.paths:
  cursor=~/.cursor/skills/aztks-review/SKILL.md
  claude=~/.claude/skills/aztks-review/SKILL.md
  codex=~/.agents/skills/aztks-review/SKILL.md

scope.project.paths:
  cursor=.cursor/skills/aztks-review/SKILL.md
  claude=.claude/skills/aztks-review/SKILL.md
  codex=.agents/skills/aztks-review/SKILL.md

install.user.cursor=mkdir -p ~/.cursor/skills/aztks-review && curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.cursor/skills/aztks-review/SKILL.md -o ~/.cursor/skills/aztks-review/SKILL.md
install.user.claude=mkdir -p ~/.claude/skills/aztks-review && curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.claude/skills/aztks-review/SKILL.md -o ~/.claude/skills/aztks-review/SKILL.md
install.user.codex=mkdir -p ~/.agents/skills/aztks-review && curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.agents/skills/aztks-review/SKILL.md -o ~/.agents/skills/aztks-review/SKILL.md

install.project.cursor=mkdir -p .cursor/skills/aztks-review && curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.cursor/skills/aztks-review/SKILL.md -o .cursor/skills/aztks-review/SKILL.md
install.project.claude=mkdir -p .claude/skills/aztks-review && curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.claude/skills/aztks-review/SKILL.md -o .claude/skills/aztks-review/SKILL.md
install.project.codex=mkdir -p .agents/skills/aztks-review && curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.agents/skills/aztks-review/SKILL.md -o .agents/skills/aztks-review/SKILL.md

install.project.note=run from repo root; adds tracked files — confirm user chose project scope

invoke.cursor=/aztks-review
invoke.claude=/aztks-review
invoke.codex=/skills|$aztks-review

post_install.cursor=Reload Window
post_install.claude=live reload; restart if new top-level .claude/skills/ after session start
post_install.codex=restart if skill not detected

companion_subagent=aztks-ai-peer  # AI-facing compact AZTKS evaluator for long-running /goal loops; read-only; returns VERDICT GO/NO-GO + SCORECARD(A/Z/T/K/S P/C/F) + TOP_FIX + EVIDENCE
agent.paths.user:
  claude=~/.claude/agents/aztks-ai-peer.md
  cursor=~/.cursor/agents/aztks-ai-peer.md
  codex=~/.agents/agents/aztks-ai-peer.md
agent.paths.project:
  claude=.claude/agents/aztks-ai-peer.md
  cursor=.cursor/agents/aztks-ai-peer.md
  codex=.agents/agents/aztks-ai-peer.md
agent.install.user.claude=mkdir -p ~/.claude/agents && curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.claude/agents/aztks-ai-peer.md -o ~/.claude/agents/aztks-ai-peer.md
agent.install.user.cursor=mkdir -p ~/.cursor/agents && curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.cursor/agents/aztks-ai-peer.md -o ~/.cursor/agents/aztks-ai-peer.md
agent.install.user.codex=mkdir -p ~/.agents/agents && curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.agents/agents/aztks-ai-peer.md -o ~/.agents/agents/aztks-ai-peer.md
agent.invoke.claude=dispatch via Task tool as subagent_type: aztks-ai-peer (e.g. from a /goal verification/termination step)
agent.invoke.cursor=register as a custom agent; select it for the eval step in Agent mode
agent.invoke.codex=reference as a read-only evaluator prompt in the loop's eval step ($aztks-ai-peer or via AGENTS.md)
agent.target=AI deliverables (not humans) — ethics minimized to one line; rubric kept compact
agent.output=VERDICT / SCORECARD / TOP_FIX / EVIDENCE / NOTES; whole output <= ~1200 chars

contract:
  output_file=<docs>/reviews/<slug>-aztks-review.md  # full review saved to file; conversation gets summary only
  docs_root=<docs> = existing docs dir, else docs/ ; <slug> = kebab-case from review target name
  dimensions=[A 알아서/aware, Z 잘/zenith, T 딱/tightly, K 깔끔/klean, S 센스/sensible]
  grade_scale=[◎ 탁월, ○ 충족, △ 보완, ✕ 미흡, — 판단보류]  # every dimension graded + 1-line rationale
  reference_gate=scan call location first; if target ambiguous or evidence thin, explicitly ask for business/service plan, PRD, SRS, app project, context evidence, and quality bar
  quality_bar=[high (industry/org context), satisficing (resource-constrained)]  # default high + note if unspecified
  volume_metric=V = total characters of review corpus (code = source-file chars, excluding deps/build/locks)
  tiers=[T1 <20000 cap 6000, T2 20000-80000 cap 12000, T3 80000-250000 cap 18000, T4 >=250000 top cap 18000 + per-area detail files cap 8000 each]
  bounded_scaling=coverage scales with V; report length hard-capped by tier; overflow -> priority cut (severity*reach) + one-line appendix or T4 area files; disclose how many items were demoted
  per_finding=<=6 lines, 4 parts [observation / evidence location / impact / improvement]
  guardrail=AZTKS is never weaponized; no disparagement/penalty/elitist exclusion; general human principle, not noblesse oblige; critique product not person; guardrail outranks the score
  output_must_separate_areas_with=3 horizontal rules (---) between [restated intent | scorecard + path | top priorities | guardrail note + next step]
```

---

## License

[MIT License](LICENSE)
