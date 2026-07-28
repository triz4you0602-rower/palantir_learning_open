# 01 · FDE 모델 (Forward Deployed Engineering)

> FDE는 팔란티어의 "핵심"이라 부를 만한 조직 모델이다. 이 문서는 **FDE가 누구이고, 어떻게 팀이 구성되며, 왜 이 모델이 회사의 엔진인지**를 다룬다.

## FDE는 무엇이 아닌가 (먼저 오해 제거)

FDE는 다음이 **아니다**:
- 컨설턴트 (consultant) — 컨설턴트는 계약의 *하류(downstream)* 에서 일한다.
- 세일즈 엔지니어 / 데모 담당 — "FDE는 데모하지 않는다. 만든다(build)."
- 전통적 구현/도입 전문가 (implementation specialist)

FDE는 **풀스택 소프트웨어 엔지니어**로, 고객 환경 *안에서* 몇 달~몇 년간 머물며, 실제 운영 의사결정을 지탱하는 **프로덕션 시스템을 직접 짠다.** 코드가 고객의 프로덕션에 들어간다.

## 핵심 철학: "상상된 제약이 아니라 실제 제약 아래에서 만든다"

> "building under actual constraints rather than imagined ones"

전통적 소프트웨어는 격리된 곳에서 만들어 고객에게 배포한다. FDE는 이를 뒤집는다 — 고객 기관 *내부*에 임베드되어, 실제 제약(정치, 레거시, 규제, 접근 불가 데이터) 속에서 만든다. 그래서 FDE의 결과물은 "기술적으로는 맞지만 현실에선 쓸모없는" 함정을 피한다.

## 팀 구조: Echo & Delta

팔란티어는 상호보완적인 두 역할의 페어(pair)를 배치한다. 함께 고객 환경 안의 **미니 스타트업**처럼 작동한다.

### Delta = Forward Deployed (Software) Engineer
- 데이터 파이프라인과 온톨로지 모델링을 위한 **프로덕션급 코드**를 짠다.
- 성향: *"스크래피한 스타트업 CTO"* — 기술적으로 깊고, 모호함(ambiguity)을 편하게 다룬다.
- 장식적 아키텍처 없이, 근본 데이터 문제를 푸는 해결책을 만든다.

### Echo = Deployment Strategist
- 배경: 도메인 전문가 출신 (군 장교, 임상의, 포렌식 회계사 등).
- **"미션의 현실을 기술 요구사항으로 번역"** 한다.
- 채택(adoption), 관계 지속, 그리고 **조직 정치**를 소유한다 — 어느 부서끼리 암묵적 적대 관계인지, 어떤 데이터가 정치적으로 건드릴 수 없는지 파악.

### 긴장(tension)이 곧 기능이다
- Delta 혼자 두면 → 기술적으로는 완벽하나 운영상 무관한(irrelevant) 것을 만든다.
- Echo 혼자 두면 → 아름답게 정렬된 전략만 있고 손에 잡히는 산출물이 없다.
- **두 역할의 긴장이 "옳은 문제를 옳게 푸는" 것을 강제한다.** Echo가 "옳은 문제"를 찾고, Delta가 "해결책"을 만든다.

## FDE 모델이 회사의 엔진인 이유

FDE는 팔란티어의 **1차 제품 발견·형성 메커니즘(product discovery & formation mechanism)** 이다.

- 컨설턴트는 계약의 *하류*에서 움직인다.
- FDE는 **로드맵의 상류(upstream of the roadmap)** 에서 움직인다.
- 즉 **"현장 작업은 매출이 아니라 제품을 만들어내기 위해 존재한다."** ("The field work existed to generate the product, not just to generate revenue.")

### Gravel Road → Paved Highway (자갈길 → 포장 고속도로)
1. FDE가 특정 고객을 위한 거친 해결책(=자갈길)을 만든다.
2. 여러 배포에 걸쳐 **반복되는 추상(abstractions that appear repeatedly)** 을 식별한다.
3. 검증된 패턴을 **재사용 가능한 플랫폼 기본요소(platform primitives)** 로 승격 = 포장 고속도로.

> 핵심: "자갈길에서 고속도로로"는 커스터마이징이 아니라 **그라운드 트루스(ground truth)** 에 관한 것이다.

이 루프가 **확장 불가능한 수작업 공동 엔지니어링을, 복리로 쌓이는(compounding) 플랫폼 코드로** 전환한다.

## 인재 선발 원칙

- **조직도(org chart)가 아니라 문제에 동기부여되는 "자유로운 사고를 하는 독립적인 사람들."**
- **"고통을 기꺼이 먹는(eat pain)"** 의지.
- 표준 컨설턴트가 실패하는 이유: 지저분한 현실을 직면하기보다 **고객을 편안하게 유지**하려 하기 때문.
- 선발 기준 = **성과 기반 능력주의** (자격증·편안함이 아니라 변혁적 결과로 평가).

## AI FDE (최근 진화)

팔란티어는 AIP 위에서 **AI FDE**를 도입 중. 자연어로 *"새 CRM 데이터로 고객 온톨로지를 만들어줘"* 라고 요청하면, AI가 이를 Foundry 명령으로 번역해 파이프라인을 만들고 온톨로지를 유지하는 **에이전트**로 작동한다.
- 사용자의 기존 권한(permissions)을 엄격히 존중.
- 변경 시 항상 **"Branch Proposal"** 을 만들어 사람이 리뷰하게 한다.
- 시사점: FDE의 *방법론*을 소프트웨어(에이전트)로 부분 자동화하려는 시도. → 이 프로젝트에서 우리가 하려는 것과 정확히 같은 방향.

## 다른 회사로의 확산

이 모델은 OpenAI, Ramp, Salesforce 등 여러 AI 스타트업이 채택하기 시작했다. "FDE"는 이제 업계 공통 개념이 되어가고 있다.

## 출처 (Sources)

- Diogo Silva Santos, "A Comprehensive Analysis of Palantir's Forward Deployed Engineering Model," Medium: https://medium.com/activated-thinker/a-comprehensive-analysis-of-palantirs-forward-deployed-engineering-model-4502a036b5e4
- "How Ontology Became a Moat: Palantir's FDE Model, Demystified," foundercoho (Substack): https://foundercoho.substack.com/p/how-ontology-became-a-moat-palantirs
- "How Palantir Invented the Forward Deployed Engineer Model," fde.academy: https://fde.academy/blog/how-palantir-invented-the-forward-deployed-engineer-model
- "AI FDE • Overview," Palantir Docs: https://www.palantir.com/docs/foundry/ai-fde/overview
