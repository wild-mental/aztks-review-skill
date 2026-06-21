![AI Skills for Everyone](author/wildmental-bjpark.png)

# aztks-review
> Skill for Cursor, Claude, Codex agents

**Language / 언어:** [한국어](README.md) · [English](README.en.md)

**대량의 비즈니스 계획서 · 서비스 구현 계획서(PRD/SRS) · 프로그래밍 구현 결과물을 `알잘딱깔센`(AZTKS) 5차원으로 리뷰해, 분량이 통제된 건설적 리뷰 리포트를 산출하는 Skill입니다. Cursor, Claude Code, Codex 모두 지원합니다.**

`알잘딱깔센`은 "일머리"의 다섯 축 — **알**아서 · **잘** · **딱** 떨어지게 · **깔**끔하게 · **센**스있게 — 이고, 그 이니셜을 로마자로 옮긴 것이 `AZTKS`이며, 이는 **A**ware · **Z**enith · **T**ightly · **K**lean · **S**ensible 로 읽히는 영문 니모닉이기도 합니다. 이 스킬은 리뷰 대상을 이 5차원으로 평가하되, **근거 자료를 먼저 확보**하고, **자료가 많아도 리포트가 무한정 길어지지 않도록 명시적 분량 상한**을 두며, 무엇보다 **`알잘딱깔센`을 무기화하지 않는** 건설적 어조를 절대 원칙으로 지킵니다.

---

## 이 스킬이 해결하는 것

### 1. AZTKS 5차원 루브릭으로 평가한다

| 코드 | 차원 | 리뷰 관점 |
|------|------|-----------|
| **A** | 알아서 (Aware) | 가용한 모든 근거를 빠짐없이 반영했는가, 숨은 요구를 추론했는가 |
| **Z** | 잘 (Zenith) | 선택한 기준(높음/적정)에서 품질·의사결정 근거가 탄탄한가 |
| **T** | 딱 떨어지게 (Tightly) | 누락·미완·중복·모순 없이 목표↔범위↔구현↔검증이 정렬됐는가 |
| **K** | 깔끔하게 (Klean) | 군더더기·장황함이 없고 요약 계층이 독자를 배려하는가 |
| **S** | 센스있게 (Sensible) | 어조·분량·타이밍·감정톤이 수신자·조직 맥락에 맞는가 |

각 차원에 **등급(◎ 탁월 / ○ 충족 / △ 보완 / ✕ 미흡 / — 판단보류) + 한 줄 근거**를 부여하고, 종합 등급과 상위 개선 우선순위를 도출합니다.

### 2. 근거 자료를 먼저 확보한다 (Reference Scan Gate)

리뷰는 근거 없이는 인상 비평이 됩니다. 그래서 두 단계로 자료를 확보합니다.

- **1차 — 호출 위치 자동 스캔:** 호출된 위치의 문서(`*.md`·PRD·SRS·RFC), 코드 트리·`README`·테스트·이슈, 커밋 이력 등 리뷰 가능한 자료를 먼저 스캔합니다.
- **2차 — 불충분하면 명시적으로 요청:** 대상이 모호하거나 근거가 빈약하면 추정하지 않고, **비즈니스/서비스 기획서·PRD·SRS·app 구현 프로젝트(경로/URL)**와 맥락 근거·품질 기준을 한 묶음으로 질문합니다. 끝내 빈 항목은 리포트에 `⚠️ 가정`으로 명시합니다.

### 3. "넓게 보되 짧게 쓴다" — 분량 상한을 명시적으로 고정한다

레퍼런스가 많을수록 **검토 범위(커버리지)는 넓어지되**, **리포트 길이는 자료량에 비례해 늘어나지 않습니다.** 자료 총 분량 `V`(문자 수)를 측정해 Tier를 1회 확정하고, 그 본문 상한을 절대 넘지 않습니다.

| Tier | V (문자수) | 검토 커버리지 | 차원별 핵심 지적 | 리포트 본문 상한 |
|------|-----------|----------------|------------------|-------------------|
| **T1 경량** | < 20,000 | 5차원 핵심 요약 | 2개 | 6,000자 |
| **T2 표준** | 20,000–80,000 | 5차원 + 문서/모듈별 미니 스코어카드 | 3개 | 12,000자 |
| **T3 풀** | 80,000–250,000 | 5차원 + 교차 정합성 매트릭스 | 4개 | 18,000자 |
| **T4 심층** | ≥ 250,000 | T3 + 영역별 상세 분리 파일 | 4개(상위) | 상위 18,000자 + 영역별 detail(각 8,000자) |

상한을 넘는 지적은 **(심각도 × 영향범위)** 우선순위로 정렬해 상위만 본문에 남기고, 나머지는 **부록 한 줄** 또는 **T4 영역 파일**로 외부화합니다. 무엇을 본문에서 내렸는지 그 개수를 리포트에 밝혀 **은폐 없이** 처리합니다.

### 4. 절대 원칙 — `알잘딱깔센`을 무기화하지 않는다

이 스킬의 최우선 가드레일입니다. 이를 어기면 아무리 높은 수준의 분석이라도 무가치해지고, 그 자체로 더는 `알잘딱깔센`이 아닙니다.

- 당연시 금지 · 비하/비난/무시 금지 · 무기화/페널티/적대적 타자화 금지
- 노블레스 오블리주가 아니라 **인간에 대한 일반 원칙**으로 적용
- 모든 지적은 **관찰 → 영향 → 개선 경로**와 함께, 사람이 아니라 **산출물·정합성**을 평가
- 등급이 낮아도 존중적·협력적 어조 유지 — 이 가드레일은 **점수보다 우선**합니다.

---

## 왜 skill 이 필요한가

| 흔한 시도 | 기대 | 실제 |
|-----------|------|------|
| 자료 없이 "리뷰해줘" | 알아서 평가 | 근거 없는 인상 비평 → 신뢰 불가 |
| 큰 문서를 통째로 리뷰 | 꼼꼼함 | 자료량만큼 리포트가 길어져 독자가 못 읽음 |
| 상한 핑계로 이슈 생략 | 간결 | 중요한 정합성 문제가 조용히 누락됨 |
| 날선 지적·평가 어조 | 냉정함 | 능력주의적 배제·적대 → 협업·성장 저해 |
| 품질 기준 안 정함 | 유연 | 평가 축이 흔들려 등급이 자의적 |

이 스킬은 자료를 먼저 확보하고, 분량을 명시적으로 고정하며, 건설적 어조를 강제해 위 패턴을 사전에 차단합니다.

---

## 빠른 시작

### 사전 요구사항

- Cursor, Claude Code, 또는 Codex
- 리뷰 대상(기획서·PRD·SRS·코드)에 대한 읽기 접근

### 스킬 설치

스킬은 **개인** 또는 **프로젝트** 범위 중 하나를 골라 설치합니다. 두 범위 모두 `curl`로 `SKILL.md`만 받습니다. **이 저장소 전체를 작업 repo에 clone하지 마세요.**

| | 개인 스킬 | 프로젝트 스킬 |
|---|----------|--------------|
| **적용 범위** | 내가 여는 모든 프로젝트 | 현재 repo에서만 |
| **경로** | `~/…/skills/aztks-review/` | `<repo-root>/.cursor/skills/aztks-review/` 등 |
| **Git 영향** | 작업 repo에 파일 추가 없음 | repo에 스킬 파일 commit 가능 (팀 공유) |
| **언제 쓰나** | 혼자 모든 프로젝트에서 쓸 때 | 팀 repo에 스킬을 고정·공유할 때 |

| 도구 | 개인 경로 | 프로젝트 경로 |
|------|-----------|---------------|
| Cursor | `~/.cursor/skills/aztks-review/` | `.cursor/skills/aztks-review/` |
| Claude Code | `~/.claude/skills/aztks-review/` | `.claude/skills/aztks-review/` |
| Codex | `~/.agents/skills/aztks-review/` | `.agents/skills/aztks-review/` |

#### 개인 스킬 (권장 — Git repo 무변경)

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

#### 프로젝트 스킬 (프로젝트 경로에 설치)

AI 스킬 설정을 repo에 포함·공유하려는 경우에만 사용하세요.

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

필요한 도구(Cursor / Claude Code / Codex)만 골라 실행하면 됩니다.

#### 설치 후

- **Cursor**: **Reload Window** 한 번
- **Claude Code**: 스킬 수정은 세션 중 live 반영; 세션 시작 후 새 top-level `.claude/skills/`는 재시작 필요할 수 있음
- **Codex**: 스킬이 안 보이면 Codex 재시작

### 사용 방법

리뷰할 대상을 알려주면 Agent가 스킬을 자동으로 적용합니다. **근거 자료가 부족하면 먼저 질문**하고, 충분하면 Tier를 확정한 뒤 분량이 통제된 리뷰를 파일로 작성합니다.

| 도구 | 수동 호출 |
|------|-----------|
| Cursor | `/aztks-review` |
| Claude Code | `/aztks-review` |
| Codex | `/skills` 또는 `$aztks-review` |

**적용되는 요청 예시:**

- "이 PRD 알잘딱깔센으로 리뷰해줘"
- "결제 모듈 구현 정합성 점검해줘"
- "사업계획서 빠진 부분·과장된 부분 짚어줘"
- "이 폴더의 코드, 기획 의도 대비 누락 없는지 봐줘"

---

## 동반 서브에이전트 — aztks-ai-peer

이 스킬에는 **AI 산출물 평가용 동반 서브에이전트 `aztks-ai-peer`**가 기본 포함됩니다(`*/agents/aztks-ai-peer.md`). 장시간 자율 작업(예: Claude Code `/goal`의 다중 턴 루프)에서 **평가용 서브에이전트**로 호출하면, 메인 에이전트의 매 턴 산출물을 AZTKS 5차원으로 콤팩트하게 점검하고 **GO / NO-GO** 판정과 다음 최우선 보완(`TOP_FIX`)을 돌려줍니다.

- 평가 대상이 **사람이 아니라 AI 산출물**이라, 도덕 규약은 한 줄로 최소화하고 정확성·유용성·다음 행동 신호에 집중합니다(사람 대상 `/aztks-review`의 비무기화 가드레일과 구분되는 지점).
- 차원 매핑: **A** 알아서(Coverage) · **Z** 잘(Quality) · **T** 딱(Coherence) · **K** 깔끔(Clarity) · **S** 센스(Consumability).
- **읽기 전용**(코드·문서 미수정), 출력은 고정 포맷 + 전체 ~1,200자로 콤팩트.

**출력 포맷:**

```
VERDICT: GO | NO-GO
SCORECARD: A:<P/C/F> Z:<P/C/F> T:<P/C/F> K:<P/C/F> S:<P/C/F>
TOP_FIX: <단 하나의 최고 레버리지 다음 행동>
EVIDENCE: <근거 위치 1–3개>
NOTES: <CONCERN 한 줄 요약 — 없으면 생략>
```

### 설치

스킬과 함께 동반 설치합니다(스킬과 동일 범위 권장 — 개인 또는 프로젝트).

```bash
# Claude Code — 네이티브 서브에이전트 (개인)
mkdir -p ~/.claude/agents
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.claude/agents/aztks-ai-peer.md \
  -o ~/.claude/agents/aztks-ai-peer.md

# Cursor — 커스텀 에이전트 (개인)
mkdir -p ~/.cursor/agents
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.cursor/agents/aztks-ai-peer.md \
  -o ~/.cursor/agents/aztks-ai-peer.md

# Codex — 평가 하네스 (개인)
mkdir -p ~/.agents/agents
curl -fsSL https://raw.githubusercontent.com/wild-mental/aztks-review-skill/main/.agents/agents/aztks-ai-peer.md \
  -o ~/.agents/agents/aztks-ai-peer.md
```

프로젝트 범위로 넣으려면 `~/`를 빼고 repo 루트에서 동일 경로(`.claude/agents/` 등)에 받으면 됩니다.

### 벤더별 호출·사용법

| 도구 | 메커니즘 | 호출 방법 |
|------|----------|-----------|
| **Claude Code** | 네이티브 서브에이전트 | `/goal` 본문의 종료/검증 단계에서 "`aztks-ai-peer` 서브에이전트로 직전 산출물을 평가해 VERDICT를 받는다"로 지시하면 Task 도구가 `subagent_type: aztks-ai-peer`로 디스패치합니다. 평소엔 "aztks-ai-peer로 검토해줘"라고 말하거나 설명이 매칭되면 자동 선택됩니다. |
| **Cursor** | 커스텀 에이전트 | `.cursor/agents/aztks-ai-peer.md`를 커스텀 에이전트로 등록하고 Agent 모드의 평가 단계에서 선택하거나, 본문을 평가 프롬프트로 참조해 직전 산출물을 점검합니다. |
| **Codex** | 평가 하네스 참조 | 장기 작업 루프의 평가 스텝에서 `.agents/agents/aztks-ai-peer.md`를 읽기 전용 평가 프롬프트로 불러(`$aztks-ai-peer` 또는 `AGENTS.md`에서 참조) GO/NO-GO를 산출합니다. |

**`/goal` 안에서 쓰는 예 (Claude Code):**

```
## 3) 종료 조건 및 종료 방법
- 종료 방법:
  1) 직전 턴 산출물을 aztks-ai-peer 서브에이전트로 평가해 VERDICT를 받는다.
  2) VERDICT가 NO-GO면 TOP_FIX를 반영하고 계속, GO면 다음 작업으로 진행한다.
```

---

## 핵심 행동 원칙 요약

### Reference Scan Gate — 자료를 먼저 확보

1차로 호출 위치를 스캔하고, 불충분하면 2차로 비즈니스/서비스 기획서·PRD·SRS·app 프로젝트와 품질 기준을 명시적으로 요청합니다.

### 분량 상한 — "넓게 보되 짧게 쓴다"

```
V(문자수) 측정 → Tier 1회 확정 → 본문 상한 선언 → 상한 절대 초과 금지
초과 지적 = (심각도 × 영향범위) 정렬 → 상위만 본문, 나머지는 부록/영역파일로 외부화 → 내린 수 명시
```

각 핵심 지적은 6줄 이내 4요소(관찰 / 근거 위치 / 영향 / 개선)로만 작성합니다.

### 품질 기준 두 모드

`Z(잘)` 차원은 **높은 퀄리티(업계·조직 맥락)** 또는 **자원 제약 하 적정 퀄리티(satisficing)** 중 하나로 평가합니다. 시작 시 확정하고, 불명확하면 "높음"을 기본값으로 잡고 명시합니다.

### 절대 원칙 — 비무기화

> "어떤 고수준의 `알잘딱깔센` 결과물이라도, 무기화·비하·배제에 쓰이면 전혀 무가치하며 그 자체로 더는 `알잘딱깔센`이 아니다."

모든 지적은 관찰 → 영향 → 개선 경로와 함께, 사람이 아니라 산출물·정합성을 평가합니다.

---

## 출력 예시

매 호출의 최종 응답은 `---` 가로줄 3개로 4영역이 분리됩니다. 리뷰 **전문은 파일에 저장**되고 대화에는 요약만 남습니다.

**입력:** "이 폴더의 결제 모듈 + `docs/PRD_payments.md` 리뷰해줘. 높은 퀄리티 기준."

**출력 (요약):**

````
**[의도 재진술]** 결제 모듈 코드 + PRD를 높은 퀄리티 기준으로 리뷰. `Tier: T3 · V≈140,000자 · 본문 상한 18,000자`.

---

**[스코어카드]** — 전문은 `docs/reviews/payments-aztks-review.md`

| 차원 | 등급 | 한 줄 근거 |
|------|------|-----------|
| A 알아서 | ○ | PRD 요구는 반영했으나 환불 엣지 케이스 근거 누락 |
| Z 잘 | ○ | 결제 검증 로직 견고, 동시성 처리 일부 보강 필요 |
| T 딱 | △ | PRD §4 부분환불 요구가 구현·테스트에 미반영 |
| K 깔끔 | ○ | 모듈 구조 명확, 죽은 코드 2곳 |
| S 센스 | ○ | 에러 메시지 사용자 어조 양호 |
| **종합** | **○** | 출시 가능 수준, T(정합성) 1건 우선 보완 |

---

**[상위 개선 우선순위]** (본문 4건/차원, 부록 9건으로 내림)

1. [CRITICAL·전역] PRD §4 부분환불 미구현 — 개선: 수용기준→구현→테스트 추적 복구
2. [MAJOR·국소] 결제 재시도 동시성 경쟁 — 개선: 멱등키 도입

---

**[비무기화 주석 · 다음 단계]** 이 리뷰는 산출물·정합성 개선을 위한 건설적 점검이며 사람·태도 평가가 아닙니다. 다음 단계: 부분환불 추적성 복구부터.
````

---

## 스킬 구성

```
.cursor/skills/aztks-review/SKILL.md   # Cursor용 스킬
.claude/skills/aztks-review/SKILL.md   # Claude Code용 스킬
.agents/skills/aztks-review/SKILL.md   # Codex용 스킬
.cursor/agents/aztks-ai-peer.md        # 동반 서브에이전트 (Cursor)
.claude/agents/aztks-ai-peer.md        # 동반 서브에이전트 (Claude Code)
.agents/agents/aztks-ai-peer.md        # 동반 서브에이전트 (Codex)
```

| 섹션 | 내용 |
|------|------|
| 절대 원칙 | 비무기화 가드레일(당연시·비하·페널티 금지, 인간 일반 원칙) — 최우선 |
| 기본 원칙 | 5차원 평가 · 자료 우선 확보 · 넓게 보되 짧게 · 증거 동반 · 비무기화 |
| AZTKS 루브릭 | 5차원 정의표 + 대상 유형별(비즈니스/PRD·SRS/코드) 서브 체크 |
| Reference Scan Gate | 1차 위치 스캔 → 2차 명시 요청(기획서·PRD·SRS·app·품질 기준) |
| 분량 등급 & 상한 | V 측정 · Tier 표 · 불가침 분량 규칙 · 우선순위 점수 |
| Workflow | Scan&Gate → Tier Lock → 분류 → 5차원 검토 → 우선순위·외부화 → 스코어카드 → Output |
| 출력 형식 | 의도 재진술 + 스코어카드 + 상위 개선 우선순위 + 비무기화 주석 (3개의 `---`로 분리) |
| Anti-Pattern Block | 인상 비평·분량 폭주·이슈 은폐·비하 어조·기준 미확정 차단 |
| 동반 서브에이전트 | `aztks-ai-peer` — `/goal` 등 장기 루프용 AI 산출물 평가 하네스(콤팩트 AZTKS · GO/NO-GO) |

---

## 이런 분께 추천합니다

- 대량의 기획서·PRD·SRS·코드를 **일관된 기준으로** 리뷰받고 싶은 분
- 리뷰 리포트가 **자료량만큼 길어져** 정작 안 읽히는 문제를 겪은 분
- 정합성 누락을 **은폐 없이, 그러나 분량은 통제해** 받고 싶은 분
- 날선 평가가 아니라 **건설적이고 존중적인** 개선 피드백을 원하는 분

---

## 참고

- `알잘딱깔센` — 일머리의 다섯 축(알아서·잘·딱 떨어지게·깔끔하게·센스있게)에 대한 행동 정의
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

## 라이선스

[MIT License](LICENSE)
