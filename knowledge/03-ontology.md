# 03 · 온톨로지 (Ontology) — 기술적 핵심

> FDE 방법론의 결과물이자 팔란티어의 해자(moat). Ontology를 이해하면 "팔란티어가 왜 그렇게 일하는가"의 마지막 조각이 맞춰진다.
> 이 문서는 개념 정의(§1~4)에서 시작해, 심화(§5 거버넌스 · §6 해자 · §7 AI 통합)로 내려간다. 심화 내용은 오픈소스 책 *palantir-ontology-strategy* 기반. → [98-external-resources.md](98-external-resources.md)

## 1. 한 줄 정의

Ontology = **조직의 디지털 트윈(digital twin).** 흩어진 디지털 자산(데이터셋 + 모델)을 하나의 일관된 전체로 통합한 **"지저분한 현실의 지도(map of messy reality)."**

핵심 성질: **온톨로지는 합성(synthesize)할 수 없다. 오랜 시간에 걸친 집중적인 현장 공동 엔지니어링(frontline co-engineering)을 통해 *추출(extract)* 해야만 한다.** → 그래서 FDE 모델이 필요하고, 그래서 경쟁자가 복제하기 어렵다.

> ⚠️ 용어 주의: 아래 §1b처럼 "온톨로지"에는 **두 얼굴**이 있다. 이 문서 대부분은 팔란티어의 *운영* 온톨로지를 다루며, 학술/형식 온톨로지와는 다르다. 비판·논쟁은 [06-ontology-critique.md](06-ontology-critique.md), 정치·윤리 차원은 [07-ontology-politics-ethics.md](07-ontology-politics-ethics.md).

## 1b. 온톨로지의 두 얼굴: 형식(formal) vs 운영(operational)

"온톨로지"는 두 뿌리를 가진다 — 혼동하면 "진짜 온톨로지 논쟁"([06](06-ontology-critique.md))을 이해할 수 없다.

**형식 온톨로지 (formal / 학술·시맨틱웹):**
- 정의: 특정 도메인에 "무엇이 존재하고, 어떤 관계를 맺으며, 어떤 규칙을 따르는지"를 **기계가 읽고 *추론*할 수 있게** 명시한 합의된 개념 체계.
- 표기: **OWL, RDF** (시스템 간 일관된 해석 보장 목적).
- 5요소: **클래스 · 관계 · 속성 · 제약/공리(axiom) · 인스턴스.**
- 핵심: **개념 층(스키마, 사람이 합의) ↔ 인스턴스 층(데이터)** 의 분리. 제약(공리)이 있으면 새 데이터의 위반 여부를 **논리적으로 도출(reasoning)** 할 수 있다 — 규칙이 주석이 아니라 실행 가능한 논리가 된다.

**운영 온톨로지 (operational / 팔란티어):**
- 같은 5요소의 어휘를 빌리되(팔란티어 문서도 데이터 타입이 RDF/OWL/XSD에서 영감받았다고 명시), **추론 엔진이 아니라 "데이터→결정→행동" 운영 계층**으로 재해석. → §2~7.
- 그래서 **"이건 진짜 온톨로지가 아니라 OOP식 시맨틱 데이터 모델에 이름만 붙인 것"** 이라는 비판이 존재 → [06](06-ontology-critique.md).

> 인접 개념 구분: **시맨틱 레이어**(BI 지표 정의)는 *조회(lookup)* 용, 온톨로지는 *맥락·추론(형식)* 또는 *결정·행동(운영)* 용. LLM이 필요로 하는 "사물이 무엇이고 어떻게 연결되며 어떤 행동이 가능한가"는 지표 정의만으로는 안 나온다.

## 2. 온톨로지가 푸는 진짜 문제: "끊어진 루프"

일반 데이터 웨어하우스(DWH)/레이크와의 차이는 저장이 아니라 **행동(action)** 에 있다.

전통적 데이터 인프라는 데이터를 **"분석을 위한 정적 스냅샷(static snapshot for analysis)"** 으로만 다룬다. 수십억을 DWH·BI 툴에 쓰고도, 현장 직원은 여전히 엑셀을 주고받고, 예측치를 업무 시스템에 **손으로 재입력**하며, 결정을 대규모로 실행하지 못한다.

```
[끊어진 루프 — 전통적 방식]
업무시스템(ERP/CRM) → 추출 → DWH → BI 대시보드
   → 사람이 읽고 → 사람이 판단하고 → 사람이 손으로 재입력 → 업무시스템
                                    ▲ 여기서 루프가 끊긴다
```

> 아무리 뛰어난 AI를 도입해도, **마지막 행동이 사람의 "수작업(재입력)"에 의존하면 확장(scale)되지 않는다.**

온톨로지는 또 하나의 "저장 상자"가 아니라, 인프라 위에 얹혀 데이터를 **결정과 행동으로 전환하는 운영 계층(Operational Layer)** 이다. 그래서 루프를 닫는다(§4).

## 3. 두 계층 (Two Layers) — 팔란티어의 아키텍처 서명

데이터 모델을 직교하는 두 차원으로 쪼갠 것이 팔란티어의 결정적 특징이다.

### Semantic Layer (의미 계층) = 명사(Nouns), "보기 위한 모델"
- **Object Type(객체 타입):** 현실 개념을 인스턴스화 가능한 타입으로 (예: Customer, Order, Supplier). 데이터 소스에서 *생성*된다 — 단순 스키마가 아니라 살아있는 표현.
- **Property(속성):** 객체의 특성 (예: Customer의 name, address, credit_limit).
- **Link Type(링크 타입):** 객체 타입 간 관계. 1:1, 1:N, **N:M** 카디널리티를 일급으로 지원.

### Kinetic Layer (동적 계층) = 동사(Verbs), "바꾸기 위한 모델"
- **Action Type(행동 타입):** 하나 이상의 객체/속성/링크를 바꾸는 트랜잭션. **변경 집합 + 부수효과(side-effect) 정의**를 함께 담는다. 행동은 외부에 있지 않고 **온톨로지의 일급 시민(first-class citizen)** 이다.
- **Function(함수):** 상태를 바꾸지 않고 파생 값을 계산하는 빠른 로직. 대시보드·결정 앱을 지탱.
- **Dynamic Security(동적 보안):** 권한·접근 제어도 나중에 붙이는 게 아니라 **Kinetic 요소의 일부**로서 어떤 연산이 허용되는지를 능동적으로 통제.

> ⚠️ **"3계층(semantic/kinetic/dynamic)" 프레이밍 주의.** 대중 해설(Medium·PuppyGraph 등, 2차)은 흔히 3계층으로 설명하며 *dynamic security를 독립된 3번째 층*으로 승격시킨다. 그러나 **팔란티어 공식(1차)은 2그룹** — Semantic elements(objects/properties/links) + **Kinetic elements(actions/functions/*dynamic security*)** — 이며, dynamic security는 **Kinetic의 하위 요소**다. 3계층 버전이 틀린 건 아니라 *교육용 재슬라이싱*(권한·규칙·워크플로를 별도 층으로 부각). 이 문서는 공식 2그룹을 따른다. (근거: [공식 Ontology Overview](https://www.palantir.com/docs/foundry/ontology/overview) — "kinetic elements (actions, functions, dynamic security)"; 부록 A 참조)

### 핵심 통찰
대부분의 DB 설계는 **명사(스키마)에서 멈추고**, 동사(업무 로직·갱신 절차)는 애플리케이션 계층에 흩어놓는다. Foundry는 이 틈을 의도적으로 닫는다:

> **"보기 위한 모델"과 "바꾸기 위한 모델"을 동시에 만들어 — 데이터 모델을 갱신 경로까지 포함하도록 닫으면(closing the data model to include update pathways) — AI와 앱이 현실에 대해 안전한 행동을 주저 없이 실행할 수 있다.**

이 이중 구조가 **환각(hallucination)과 드리프트(drift)를 막는다.** AI는 임의 변경을 제안할 수 없고, *정의된·의미적으로 근거 있는 행동*의 범위 안에서만 추론할 수 있다. (§7)

## 4. 핵심 구성요소 — 심화 뉘앙스

> ✅ **검증됨:** 이 절의 용어는 팔란티어 공식 docs와 대조 검증했다(2026-07-14). 대중적 요약에 흔한 오해 몇 가지를 여기서 바로잡는다. 검증 상세는 [부록 A](#부록-a--§4-공식-docs-대조-검증)와 §출처 참조.

| 요소 | 정의 | 비유 |
|---|---|---|
| **Object Type** | 현실 개체/이벤트의 스키마 정의 | DB의 테이블 |
| **Object / Object Set** | 개별 인스턴스 / 그 묶음 | 행(row) / 행들의 집합 |
| **Property** | 객체가 담는 특성 스키마와 값 | 컬럼 + 셀 값 |
| **Link Type** | 두 객체 타입 사이 관계의 스키마 정의 | 그래프 엣지, FK |
| **Action Type** | 사용자가 객체·속성·링크에 가하는 변경 집합의 스키마 정의 | 거버넌스된 쓰기 트랜잭션 |
| **Function** | 온톨로지와 통합된 코드 로직 (읽기 + 편집 모두 가능) | 비즈니스 로직/파생 계산 |

### Object Type
- 데이터 소스에서 **인스턴스화**되어 **Object Storage V2**에 색인된다. 색인은 **Funnel** 파이프라인이 담당하며, 기본적으로 **증분 색인(incremental indexing)** — 새 데이터 차이만 다시 색인.
- **MDO(Multi-Datasource Object):** 하나의 객체 타입을 **여러 데이터소스로 백킹**한다. 단, **컬럼 방향(column-wise)만 지원** — 서로 다른 소스에서 *속성의 부분집합*을 합치는 조인형. (행 방향 union인 row-wise는 미지원 → Restricted View로 대체.)
  - 제약: 속성은 정확히 한 소스에서만 옴(단 PK는 모든 소스에 있어야 조인 가능), 소스 **최대 70개**, **OSv2 전용**, 스트리밍 미지원. 권한 없는 소스의 속성은 `null`로 표시.
  - 주 용도: **컬럼(속성) 수준 접근 제어** (예: 구매이력은 전사, PII 속성은 컴플라이언스만).

### Link Type
- 카디널리티 **1:1, 1:N, N:M** 지원. N:M은 편집/write-back을 하려면 **백킹 데이터소스(조인 테이블)** 가 필요 — 조인 테이블은 양쪽 객체 타입의 PK에 대응하는 컬럼을 담는다.
- ⚠️ **정정:** "링크 자체에 임의 속성을 붙인다"는 부정확. **링크에 메타데이터를 실으려면 "객체 백킹 링크(object-backed link)"** 를 쓴다 — 중간 객체 타입이 관계를 나타내고 그 객체가 속성을 가진다. (공식 예: `Flight Manifest` 객체가 `Pilot`, `First Mate` 속성으로 링크에 메타데이터 제공.) 단순 조인 테이블의 여분 컬럼이 곧바로 쿼리 가능한 "링크 속성"이 된다고 공식 문서는 명시하지 않는다.

### Action Type
- **부수효과가 명시적(✅ 확인):** Action Type은 parameters·rules·submission criteria와 함께 **side effects(notifications, webhooks)** 를 포함한다.
- **권한 존중:** 제출자가 권한이 없으면 행동은 거부된다.
- ⚠️ **정정 — Action Log:** *행동 제출 1건당 로그 객체 1개* 이며, 그 로그는 **영향받은 여러 객체와 1:N으로 연결**된다(1:1 아님). 공식 예: 알림(Alert) 10개를 한 번에 닫으면 **로그 객체 1개가 10개 Alert 모두에 FK로 연결.** 기록 내용: 제출 사용자(Multipass ID)·UTC 타임스탬프·편집된 객체들의 PK·선택적 컨텍스트. **속성 수준의 before/after 변경 이력은 Action Log가 아니라 별도의 [edit history](https://www.palantir.com/docs/foundry/object-edits/user-edit-history/) 기능이 담당.** ("궁극의 감사 추적"이라는 표현은 대중적 프레이밍이며, 공식 문서는 Action Log를 불변 감사 로그로 규정하지 않는다.)

### Function vs Action
- ⚠️ **정정:** "Function은 읽기 전용"은 부정확. **Function은 읽기(파생 계산)뿐 아니라 온톨로지 편집(ontology edits) API로 상태를 바꿀 수도 있고, "function-backed action"의 백엔드**로도 쓰인다.
- 정확한 구도: **Action = 사용자 대면의 거버넌스된 상태 변경 인터페이스** / **Function = 계산 엔진이자, 편집을 수행하거나 Action을 뒷받침하는 로직.**
- **그래서 AI 안전의 근거는 "함수는 읽기 전용이라서"가 아니다.** 진짜 근거는 ⑴ AI가 **미리 정의된 Action 스키마 범위 안**에서만 변경을 제안하고, ⑵ 그 제안이 **Branch Proposal → 사람 리뷰(§5)** 를 거친다는 데 있다.

### 4b. OOP와의 대응 — 프로그래머를 위한 지도

팔란티어 스스로 **OOP 은유**와 **관계형 DB 은유**(object type=데이터셋, object=행, property=열)를 병행한다. 정적 구조는 OOP와 거의 1:1, 동적 구조에서 갈라진다.

| 객체지향 (OOP) | 팔란티어 온톨로지 | 대응 강도 |
|---|---|---|
| 클래스 (class) | Object type | 직접 |
| 인스턴스 (instance) | Object | 직접 |
| 필드 (field) | Property | 직접 |
| 인터페이스 (interface) | Interface (다형성) | 직접 |
| 메서드 (method) | Action type + Function | 부분 |
| 객체 참조 (member pointer) | Link type | 부분 |

**갈라지는 세 지점:**
1. **인스턴스의 존재 방식:** OOP 인스턴스는 메모리의 휘발성 상태. 팔란티어 object는 실제 데이터 원천에 매핑된 조직의 디지털 트윈 — `new`로 만드는 게 아니라 **기존 데이터가 객체로 구체화**된다(생성 방향이 반대).
2. **캡슐화의 부재:** 행동(Action)이 객체 *안*이 아니라 **거버넌스된 외부 층**에 있다(§3 Kinetic). 캡슐화 대신 **거버넌스 분리**.
3. **관계의 1급 시민화:** Link type은 어느 객체에도 소속되지 않는 독립 스키마 — 소유된 참조가 아니라 **1급 관계**(ER/그래프 성격).

> "진짜 온톨로지인가" 비판(추론 미지원)은 여기서 출발한다 → [06-ontology-critique.md](06-ontology-critique.md).

## 5. 현실의 거버넌스 (Governance of the Real World)

온톨로지가 이제 *운영을 구동*하므로, 거버넌스는 철벽이어야 한다. 팔란티어의 국방·정보 DNA가 가장 잘 드러나는 지점.

### 권한 패러다임의 전환
- 전통: **"데이터를 숨긴다"** (접근 제한).
- 온톨로지: **"현실에 대한 잘못된 변경·파괴를 막는다"** — *숨기기(hide)가 아니라 안전하게 움직이기(move safely).*
- **Restricted Views(RV):** 행(row) 수준 제어 (예: 영업팀은 자기 지역 고객만).
- **MDO:** 컬럼/속성 수준 제어 (예: 구매 이력은 전사 공개, PII는 컴플라이언스만).
- 권한이 **데이터 소스 종속 → 온톨로지 네이티브**로 이동 — 권한이 원시 테이블이 아니라 **업무 개념**을 따라간다.
- **행동 수준 인가:** 어떤 롤이 그 Action을 제출할 수 있는지 정의 → 무자격자가 재무·운영 변경을 트리거하지 못함.

### 브랜칭 & 제안 라이프사이클 (소프트웨어의 PR 모델을 데이터에)
1. **작업 브랜치 생성** (main 온톨로지 버전에서 파생)
2. **브랜치에서 편집** (스키마·Action·속성 변경을 격리)
3. **제안 제출** → 브랜치는 추가 편집이 잠김
4. **사람 리뷰** — *Approvals App* 에서 부서장·컴플라이언스·데이터 오너가 검토
5. **거부→반복** 또는 **승인→main 병합** (승인 시에만 병합되어 즉시 반영)

> **섀도우 IT의 구조적 제거:** 브랜칭이 플랫폼 수준에서 강제되므로 무단 운영 변경이 불가능하다. **엔지니어조차 프로덕션을 직접 고쳐 쓸 수 없다.** → "한 사람의 변경이 1만 개 매장의 주문 로직을 깨뜨리는" 사고를 막는다.

### Action Log = 궁극의 감사 추적
- 모든 행동이 로그 객체를 남기고 대상 객체와 1:1 연결.
- 기록: 제출자, 타임스탬프, 변경 전/후 데이터, 인가 결정.
- 반영구적 추적 — 어떤 행동도 지우거나 숨길 수 없다. 포렌식 분석 가능.

## 6. 왜 해자(moat)가 되는가 — 심화

- **네트워크 효과 & 전환 비용:** 업무를 온톨로지로 모델링(모든 Object·Link·Action·거버넌스 규칙)하고 나면, 경쟁사로 옮기는 것은 그 **지적 자산을 처음부터 다시 짓는 일.** 온톨로지는 곧 **코드화된 업무 로직.**
- **데이터 통합 장벽:** AWS·Snowflake는 데이터를 싸게 담는 "상자"를 준다 — 어떻게 *쓸지*는 고객 몫. 팔란티어는 그 상자 *위에서* 데이터를 실행 가능한 인텔리전스로 바꾸는 **상위 가치 계층.** 온톨로지가 서면 새 소스 추가는 기존 객체 타입에 색인만 하면 됨.
- **운영 락인(lock-in):** 분석 툴은 버리고 새 BI로 갈아탈 수 있지만, 온톨로지는 **실시간 운영을 구동**한다. (SOMPO 보험금 청구 플랫폼: 일 8,000+ 사용자가 온톨로지에 의존 — 교체는 그 인력 재교육 + 워크플로 재구축을 의미.)
- **거버넌스·컴플라이언스의 코드화:** 규제 산업에서 거버넌스 규칙이 외부 정책이 아니라 온톨로지에 내장. 감사 추적·브랜칭이 **플랫폼 기본요소** → 규제 준수를 증명 가능·자동화.
- **AI 준비성:** 온톨로지는 AI가 이해·작동할 수 있는 **공통 언어.** "당신 데이터용 ChatGPT"를 파는 경쟁자는 구조화된 의미 계층이 없어 환각·드리프트 위험에 노출된다.

## 7. 온톨로지 × AI (AIP 통합)

### 환각의 벽: 의미(semantics)가 곧 안전장치
LLM은 추론·자연어에 강하지만 직접 다음을 못 한다: 실제 시스템 조작("B창고에서 100개 출하"), 내부 규정·복잡한 업무 로직 이해, 그럴듯한 거짓의 날조 회피.

**해법: LLM의 입력과 출력을 온톨로지로 제한한다.**
- AI는 원시·잡다한 데이터가 아니라 **구조화된 온톨로지 데이터**(정의된 Property·Link를 가진 Object)를 읽는다.
- AI는 온톨로지 스키마에 **미리 정의된 Action만** 제안할 수 있다.
- Action이 부수효과 정의를 포함하므로, AI가 업무 규칙을 위반하는 변경을 제안할 수 없다.
- 결과: 환각을 한계까지 제거해 **현실 행동을 안전하게 실행.**

### AI FDE — 시스템을 짓는 엔지니어
- 자연어 요청을 Foundry 연산으로 번역하는 대화형 에이전트.
- 사용자: *"새 CRM 데이터로 고객 온톨로지를 만들어줘"* → AI FDE: 객체 타입 생성, 속성 정의, 파이프라인 구성, 스키마 생성.
- **결정적으로:** AI FDE는 항상 사용자의 기존 **권한을 존중**하고, 변경을 **Branch Proposal(§5)** 로 제시해 사람이 리뷰하게 한다.
- 시사점: **FDE의 방법론 자체를 에이전트로 부분 자동화** — 사람은 반복적 데이터 배관에서 해방되어 "이 온톨로지가 업무 의도에 맞나? Action이 옳은 결정 로직을 담았나?"라는 **고부가 리뷰**로 이동. → [01-fde-model.md](01-fde-model.md)의 "AI FDE" 절과 연결.

### ⚠️ 정밀화 — 거버넌스 강도는 에이전트 종류마다 다르다
"AI 안전 = Branch Proposal + 사람 리뷰"는 **온톨로지를 편집하는 AI FDE**의 강한 거버넌스다. 모든 AI 에이전트가 그런 건 아니다:
- **기본 AIP Chatbot(구 Agent):** 공식 Getting-Started의 안전 방식은 주로 **프롬프트 거버넌스** — 시스템 프롬프트로 업무 로직·도구 사용 맥락을 서술. 권한 계층·사람 리뷰·브랜칭은 입문 단계에서 강조되지 않음(고급/별개). → *소프트*.
- **온톨로지 편집 AI FDE:** Branch Proposal → 사람 리뷰 → 병합. → *하드*.
- **외부 에이전트(Ontology MCP, 아래):** 애플리케이션 제한(application restrictions)으로 **허용된 행동 집합 자체를 사전에 좁히는** 방식 — 사후 리뷰가 아니라 사전 권한 스코핑. → *제3의 유형(스코프형)*.
- 교훈: "AI가 온톨로지 위에 있으니 안전하다"는 자동이 아니다. **어떤 종류의 거버넌스가 걸렸는지**를 확인해야 한다. 가장 강한 보증은 프롬프트 설득으로 못 뚫는 **결정론적 집행 계층**(판단 LLM과 집행을 분리)이다. (출처: [AIP Chatbot Getting-Started](https://www.palantir.com/docs/foundry/agent-studio/getting-started), 2026 접속)

### Ontology MCP / Palantir MCP — 외부 에이전트에게 온톨로지 개방 (2026)
팔란티어 내부 AI(AI FDE·AIP Chatbot)뿐 아니라 **외부 임의 에이전트**에게도 온톨로지를 [MCP](https://modelcontextprotocol.io/)(Model Context Protocol, 개방 표준) 서버로 노출한다. 두 제품으로 나뉜다:

| | **Ontology MCP (OMCP)** | **Palantir MCP (PMCP)** |
|---|---|---|
| 대상 | 온톨로지 **소비자**(외부 에이전트) | 온톨로지 **빌더**(개발자) |
| 할 수 있는 것 | 통제된 **데이터 쓰기** — object 읽기(SQL 도구화), 사전정의된 action 실행, query function 호출 | **구조 수정** — object/link/action **타입** 생성·변경 (70개 이상 도구) |
| 할 수 없는 것 | 온톨로지 타입 구조 변경 | 실제 온톨로지 데이터 쓰기 |
| 거버넌스 | 애플리케이션 제한으로 허용 행동 범위를 좁힘 | 개발 워크플로 범위 내 |

- **에이전트를 도구로 합성:** AIP Logic·AIP chatbot으로 만든 에이전틱 로직을 함수로 저장해 MCP 도구로 노출 가능 — 호출하는 상위 에이전트 입장에선 하위 에이전트가 그냥 "도구 하나"가 되어, 이미 만든 에이전트 위에 상위 에이전트를 쌓을 수 있다.
- **노코드 연결 사례(공식 예시 아키텍처):** Microsoft Copilot Studio, **Claude Cowork**, Google Gemini Enterprise가 커스텀 코드 없이 OMCP로 온톨로지에 직접 연결. (프로코드 예시로는 LangChain 기반 에이전트가 Azure/GCP에서 OMCP·PMCP 서버에 연결하는 구성도 제시됨.)
- **공식 경고:** 팔란티어 AIP 밖에 호스팅된 LLM에 OMCP를 연결하면 조직 데이터가 외부 MCP 클라이언트에 노출된다 — 조직의 데이터 거버넌스·컴플라이언스 정책과의 합치 확인이 필요하다고 명시.
- 시사점: 온톨로지의 "안전한 행동 범위 제한"(§7 서두)이라는 원칙이 **내부 AI를 넘어 임의의 외부 에이전트 생태계**로 확장됐다 — 거버넌스 설계의 무게중심이 "누가 온톨로지를 편집하는가"에서 "어떤 외부 클라이언트에 어떤 스코프로 노출했는가"로 넓어진다.

## 8. 기억할 프레이밍 (Memorable Framings)

1. **"보기 위한 데이터" → "업무를 직접 구동하는 데이터"** — 중심 패러다임 전환.
2. **"데이터 상자"가 아니라 "조직의 OS."**
3. 보안: **"숨긴다"가 아니라 "안전하게 움직인다."**
4. **디지털 트윈** — 결정이 즉시 운영에 반영되는 조직의 현실 구조.
5. **"갱신 경로까지 포함해 데이터 모델을 닫는다"** — 의미+동적 계층의 결합이 안전한 AI 행동을 가능케 한다.

## 이 프로젝트에서의 활용

실습([practice/](../practice/))의 **3단계(온톨로지 스케치)** 에서 이 문서의 Object/Link/Action 어휘를 그대로 쓴다. 특히 심화 학습 포인트:
- Action의 **부수효과·Action Log**까지 스케치하면 "결정→행동→기록" 루프(§4)가 닫힌다.
- "이 해결책은 *숨기기*인가 *안전하게 움직이기*인가?"(§5)로 거버넌스를 점검.
- 실제 Foundry가 없어도, "현실을 개체·관계·행동으로 모델링하고 결정/행동/기록까지 잇는" 사고 훈련이 목적.

## 부록 A · §4 공식 docs 대조 검증

2026-07-14, `palantir.com/docs` 1차 문서로 §4 주장을 검증. 요약:

| 주장 | 판정 | 근거·정정 |
|---|---|---|
| Object는 Object Storage V2에 색인, Funnel 증분 색인 | ✅ 확인 | Indexing / Object backend docs |
| MDO = 여러 소스로 백킹 | ✅ (정밀화) | **컬럼 방향만** 지원, row-wise 미지원(RV로 대체), 소스 ≤70, OSv2 전용, 스트리밍 불가 |
| 링크 자체가 임의 속성을 가진다 | ⚠️ 정정 | 링크 메타데이터는 **object-backed link**(중간 객체 타입)로. 조인 테이블 여분 컬럼=링크 속성은 공식 미명시 |
| N:M 일급, 조인 테이블/객체 백킹 | ✅ 확인 | Create a link type docs |
| Action에 side effects(notifications/webhooks) | ✅ 확인 | Action types overview |
| Action Log는 대상 객체와 1:1 | ❌ 정정 | **1:N** — 제출 1건당 로그 1개가 영향 객체 여럿에 FK 연결(예: Alert 10개→로그 1개) |
| Action Log가 before/after 감사 추적 | ⚠️ 정정 | 로그는 결정·PK·컨텍스트 기록. 속성 before/after는 **edit history**가 담당. 불변 감사로그로 규정되지 않음 |
| Function은 읽기 전용 | ❌ 정정 | Function은 **ontology edits로 상태 변경 가능** + function-backed action 백엔드 |
| "함수가 읽기전용이라 AI 안전" | ❌ 정정 | 안전 근거는 **정의된 Action 범위 + Branch Proposal 리뷰**(§5) |
| 온톨로지 = 3계층(semantic/kinetic/**dynamic**) | ⚠️ 정정 | 공식은 **2그룹**(semantic elements / kinetic elements). "dynamic security"는 **kinetic의 하위 요소**이지 독립 3층 아님. 3계층은 2차 해설의 재슬라이싱. 근거: 공식 Ontology Overview "kinetic elements (actions, functions, dynamic security)" |
| Ontology MCP 지원 클라이언트: "Claude.ai, Microsoft Copilot Studio, Gemini Enterprise" | ❌ 정정 | **1차 문서(`ontology-mcp/sample-architecture`) 직접 대조 결과 "Claude.ai"가 아니라 "Claude Cowork"** — 검색엔진 요약(2차 가공)이 더 친숙한 제품명으로 바꿔치기한 오류. 정확한 3사는 Microsoft Copilot Studio·**Claude Cowork**·Google Gemini Enterprise |

교훈(방법론): 대중적 요약(오픈소스 책·블로그)은 큰 그림엔 유용하나, **기술 스펙은 1차 문서로 검증**해야 한다. 이는 FDE의 "그라운드 트루스" 원칙과 같다 → [02-problem-solving-playbook.md](02-problem-solving-playbook.md).

## 출처 (Sources)

개념·전략(§2~3, 5~7):
- *palantir-ontology-strategy* (오픈소스 책, Leading.AI / Satoshi Yamauchi, CC BY 4.0), `docs/the-palantir-impact_en.md`: https://github.com/Leading-AI-IO/palantir-ontology-strategy
- "How Ontology Became a Moat," foundercoho (Substack): https://foundercoho.substack.com/p/how-ontology-became-a-moat-palantirs
- "The power of ontology in Palantir Foundry," Cognizant: https://www.cognizant.com/us/en/the-power-of-ontology-in-palantir-foundry

기술 스펙 검증(§4, 공식 1차 문서):
- "Core concepts," Ontology: https://www.palantir.com/docs/foundry/ontology/core-concepts
- "Indexing • Overview" (Object Storage V2 / Funnel): https://www.palantir.com/docs/foundry/object-indexing/overview
- "Multi-datasource object types (MDOs)": https://www.palantir.com/docs/foundry/object-permissioning/multi-datasource-objects
- "Link types • Overview" / "Create a link type": https://www.palantir.com/docs/foundry/object-link-types/link-types-overview · https://www.palantir.com/docs/foundry/object-link-types/create-link-type
- "Action types • Overview" / "Action log": https://www.palantir.com/docs/foundry/action-types/overview · https://www.palantir.com/docs/foundry/action-types/action-log
- "Functions on objects and links": https://www.palantir.com/docs/foundry/functions/api-objects-links
- "Edit history": https://www.palantir.com/docs/foundry/object-edits/user-edit-history/
- "Ontology MCP • Overview": https://www.palantir.com/docs/foundry/ontology-mcp/overview
- "Ontology MCP • Sample architecture": https://www.palantir.com/docs/foundry/ontology-mcp/sample-architecture
- "Palantir MCP • Overview": https://www.palantir.com/docs/foundry/palantir-mcp/overview
