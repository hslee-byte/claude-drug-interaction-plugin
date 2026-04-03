# Drug Interaction — 약물 상호작용 체크

> [한국어](#한국어)

A Claude Code plugin that checks drug interactions between multiple medications. Input drug names (generic or brand), get severity-graded interaction analysis with mechanisms, alternatives, and patient-friendly medication guides.

## What It Does

```
Drug names → Interaction analysis → Severity grading → Alternatives → Medication guide
```

### Analysis Flow

| Phase | What happens |
|---|---|
| **0. Identify** | Parse drug names, match generic ↔ brand, classify by therapeutic category |
| **1. Interaction Analysis** | Check all pairwise interactions, grade severity, explain mechanisms |
| **2. Deep Analysis** | High-risk pairs: clinical impact, monitoring, alternatives |
| **3. Medication Guide** | Patient-friendly instructions in plain language |
| **4. Alternatives** | Same efficacy, no interaction, with comparison table |

### Severity Grades

| Grade | Meaning | Action |
|---|---|---|
| ⚫ Contraindicated | Never combine | Immediate prescriber consultation |
| 🔴 Major | Life-threatening possible | Contact prescriber recommended |
| 🟡 Moderate | Monitoring needed | Dose adjustment or timing separation |
| 🟢 Minor | Minimal clinical impact | Note for reference |
| ⬜ None | No known interaction | — |

## Install

```bash
claude plugin add hslee-byte/claude-drug-interaction-plugin
```

## Use In Codex

This repository also includes a Codex-ready skill folder:

- `codex-skills/drug-interaction`

Manual install:

1. Copy `codex-skills/drug-interaction` into `$CODEX_HOME/skills/drug-interaction`
2. Restart Codex

If you do not want to install a skill, use the portable prompt in:

- `prompts/drug-interaction-portable-prompt.md`

## Usage

```
/drug-interaction amlodipine, metformin, aspirin
/drug-interaction 노바스크, 글루코파지
/drug-interaction
```

Accepts both generic names and Korean brand names.

## Output Options

1. **Interaction summary** — All pairs with severity grades
2. **High-risk detail** — Mechanism, clinical impact, monitoring for ⚫🔴 pairs
3. **Medication guide** — Patient-friendly plain language instructions
4. **Alternative suggestions** — Same efficacy, fewer interactions

---

## 한국어

약품명 여러 개를 넣으면 상호작용 위험도를 분석하고, 복약 안내문까지 생성하는 Claude Code 플러그인. 약사와 의사를 위해 만들었습니다.

### 분석 흐름

```
약품명 입력 → 성분 식별 → 상호작용 분석 → 위험도 분류 → 복약 안내문 / 대체 약품 제안
```

### 특징

- **성분명/상품명 모두 지원** — "amlodipine"도 "노바스크"도 인식
- **5단계 위험도** — ⚫금기 / 🔴심각 / 🟡중등도 / 🟢경미 / ⬜없음
- **약리학적 기전** — 왜 상호작용이 발생하는지 설명
- **임상적 영향** — 환자에게 어떤 증상이 나타날 수 있는지
- **대체 약품 제안** — 같은 약효, 상호작용 없는 대안
- **복약 안내문** — 환자 눈높이, 전문용어 없이, 구체적 행동 지시
- **출처 우선순위 + 근거 수준 표기** — 허가사항, 약학 DB, 가이드라인, 문헌 순으로 제시

### 전문가형 근거 표기

고위험 상호작용에는 아래를 함께 출력합니다.

1. **상호작용 결론**
2. **기전**
3. **임상적 의미**
4. **권고 강도 / 근거 수준**
5. **원천 소스 + 확인일**
6. **불확실성 또는 추가 확인 필요 변수**

원천 소스는 아래 우선순위를 따릅니다.

1. 허가사항/첨부문서
2. 공신력 있는 약학 데이터베이스
3. 전문학회/공공기관 가이드라인
4. 논문 또는 리뷰 문헌

### 설치

```bash
claude plugin add hslee-byte/claude-drug-interaction-plugin
```

### Codex에서 사용

이 저장소에는 Codex용 스킬 폴더도 포함되어 있습니다.

- `codex-skills/drug-interaction`

수동 설치 방법:

1. `codex-skills/drug-interaction` 폴더를 `$CODEX_HOME/skills/drug-interaction`로 복사
2. Codex 재시작

설치 없이 바로 쓰고 싶다면 아래 중립 프롬프트를 사용하면 됩니다.

- `prompts/drug-interaction-portable-prompt.md`

### 사용법

```
/drug-interaction 노바스크, 글루코파지, 아스피린
/drug-interaction amlodipine, metformin
/drug-interaction
```

### 결과물

1. **상호작용 요약** — 전체 조합 위험도
2. **고위험 상세 분석** — ⚫🔴 조합의 기전, 임상 영향, 모니터링
3. **복약 안내문** — 환자에게 직접 줄 수 있는 안내
4. **대체 약품 제안** — 같은 약효, 적은 상호작용

### 안전장치

- 모든 결과물 상단에 "⚠️ AI 보조 분석입니다. 최종 판단은 반드시 약사/의사와 확인하세요." 표시
- 확정적 의약 판단을 내리지 않음 — 가능성과 근거를 제시
- 고위험 조합은 출처, 확인일, 근거 수준을 함께 표시
- 환자 정보(이름, 연락처, 질환)는 절대 기억/저장하지 않음

## License

MIT
