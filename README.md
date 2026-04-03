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

### 설치

```bash
claude plugin add hslee-byte/claude-drug-interaction-plugin
```

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
- 환자 정보(이름, 연락처, 질환)는 절대 기억/저장하지 않음

## License

MIT
