# 02 · FDE 문제 정의·해결 플레이북 (Problem-Solving Playbook)

> 이 문서가 이 프로젝트의 **심장**이다. FDE가 문제를 *어떻게* 정의하고 *어떻게* 푸는지를, 실습(practice/)에서 바로 따라 할 수 있는 단계로 정리한다.
> 이 단계들의 *배경 사고(왜 이렇게 하는가)* 는 1차 인용 중심의 [04-problem-solving-principles.md](04-problem-solving-principles.md) 참조.

## 대원칙 5가지

1. **현실에 임베드하라 (Embed in reality).** 인터뷰가 아니라 몰입(immersion)으로 문제를 발견한다. 문서화된 워크플로 밖에서 벌어지는 결정, 시스템에 기록되지 않는 데이터, 수년간 보이지 않게 굴러온 "하중을 견디는 임시방편(load-bearing workarounds)"을 찾아라.
2. **옳은 문제를 먼저 찾아라 (Find the right problem before the solution).** Echo의 일. 잘못된 문제를 완벽히 푸는 것은 실패다.
3. **상상된 제약이 아니라 실제 제약 아래에서 만들어라.** 정치·레거시·규제·접근 권한을 설계 변수로 취급한다.
4. **결정과 행동으로 이어져라 (Data → Decision → Action).** 대시보드가 아니라 **운영상의 행동**이 목표. 온톨로지의 Action이 그 연결고리. → [03-ontology.md](03-ontology.md)
5. **일반화 가능성을 항상 감지하라 (Sense the generalizable).** 이 고객의 문제에서 *반복되는 추상*을 뽑아 재사용 가능한 것으로. (Gravel road → paved highway)
6. **관측 먼저, 코드 나중 (Observe before you commit).** 설계를 코드로 굳히기 전에 **현장 실측 1건**을 넣어라 — 그 한 번이 "불평한 표면 ≠ 문제 표면", "사무실 가설"을 깨서 헛발질을 막는다. (서로 다른 실제 배포에서 반복 관찰돼 대원칙으로 굳은 패턴.)
7. **결과가 아니라 행동에 붙은 leading 프록시로 측정하라.** 최종 결과(제재·사고·이탈)는 대개 **희소·지연**이라 지표로 부적합. 대신 **결정자의 실제 행동에 붙은 leading 신호**를 잰다 — 그 하나가 채택·정밀도·되먹임을 동시에 본다. (예: "정정이 실제 방송됐나", "AI 판정과 사람 기록이 일치하나".) → *실전 승격: 두 배포 교차 관찰(n≥2), 2026-07-16.*

## 문제 발견의 3가지 "숨은 곳"

FDE가 몰입으로 찾아내는 것들 — 전통적 발견 방법이 놓치는 지점:
- 📌 **문서화된 워크플로 *밖*에서 일어나는 결정** (Decisions happening outside documented workflows)
- 📌 **기록 시스템에 도달하지 못하는 데이터** (Data never reaching systems of record)
- 📌 **수년간 보이지 않게 작동해온 하중 임시방편** (Load-bearing workarounds operating invisibly for years)

> 이 셋을 못 찾으면 "지저분한 현실의 지도(map of messy reality)"를 그릴 수 없다.

## 5단계 워크플로 (Field-to-Platform)

### 1단계 — 몰입 & 그라운드 트루스 확보 (Immerse)
- 실제 사용자 옆에 앉아 관찰. "그들이 말하는 프로세스"가 아니라 "실제 프로세스"를 기록.
- 산출물: **현실 지도 초안** — 누가/무엇을/왜/어떤 데이터로 결정하는가.

### 2단계 — 옳은 문제 정의 (Frame the right problem)
- 미션의 현실을 기술 요구사항으로 번역 (Echo 역할).
- 좋은 문제 정의의 체크: *운영상의 결정 하나*와 연결되는가? 성공을 측정할 수 있는가? 정치적으로 실행 가능한가?
- 산출물: **문제 진술서(Problem Statement)** — [practice/case-template.md](../practice/case-template.md) 참조.

### 3단계 — 온톨로지 스케치 (Model reality)
- 문제에 등장하는 **Object Type(개체) · Link Type(관계) · Action Type(행동)** 을 스케치.
- "데이터가 무엇을 *의미*하고, 그 위에서 어떤 *행동*이 가능한가"를 명시.
- 산출물: **미니 온톨로지** (표/다이어그램).

### 4단계 — 자갈길 구축 (Build the gravel road)
- 장식 없이, 근본 데이터 문제를 푸는 최소 프로덕션 해결책을 만든다 (Delta 역할).
- 실제 제약 아래에서 동작해야 한다.
- 산출물: **작동하는 해결책** + 그것이 지탱하는 결정/행동.

### 5단계 — 패턴 추출 & 회고 (Extract the pattern)
- 이 해결책에서 *다른 고객·다른 문제에도 반복될 추상*은 무엇인가?
- 무엇을 재사용 가능한 기본요소로 승격할 수 있는가?
- 산출물: **패턴 노트** + 회고 (무엇을 배웠나, 다음엔 무엇을 다르게).

## 실전 검증 예: Trinity Industries

- 문제: 크리티컬한 **송장 감사(invoice audit) 병목.**
- 다른 벤더들은 수개월간 실패.
- 팔란티어는 부트캠프 중 **8시간 만에** 해결.
- 3개월 내 **3천만 달러(USD 30M) 이익 영향.**
- 왜 가능했나? **온톨로지가 이미 현실을 매핑**해 두어, 비기술 팀도 자동화 규칙을 빠르게 배포 가능. → 속도(speed-to-value)가 곧 해자(moat).

## 흔한 실패 모드 (Anti-patterns)

| 함정 | 증상 | 교정 |
|---|---|---|
| 솔루션 우선 | 문제를 이해하기 전에 도구부터 고름 | 1~2단계로 돌아가라 |
| 인터뷰 의존 | "그들이 말한 프로세스"만 믿음 | 몰입·관찰로 검증 |
| 대시보드 함정 | 예쁜 시각화가 목표가 됨 | "어떤 결정/행동으로 이어지나?"를 물어라 |
| 고객 비위 맞추기 | 지저분한 진실을 회피 | "고통을 먹어라" — 진실을 직면 |
| 과잉 일반화 | 첫 고객부터 플랫폼을 지으려 함 | 자갈길 먼저, 고속도로는 패턴이 반복될 때 |

## 출처 (Sources)

- Diogo Silva Santos, "A Comprehensive Analysis of Palantir's FDE Model," Medium: https://medium.com/activated-thinker/a-comprehensive-analysis-of-palantirs-forward-deployed-engineering-model-4502a036b5e4
- "How Ontology Became a Moat," foundercoho (Substack): https://foundercoho.substack.com/p/how-ontology-became-a-moat-palantirs
- "Why create an Ontology?," Palantir Docs: https://www.palantir.com/docs/foundry/ontology/why-ontology
