# 08 · 실제 배포 사례집 (Real Deployment Case Studies)

> 팔란티어의 실제 문제 정의·해결 사례. 게임 [case-files.html](../practice/game/case-files.html)의 근거이자, 추상 원칙([04](04-problem-solving-principles.md))이 현실에서 어떻게 나타나는지의 증거.
>
> ⚠️ **출처 등급 경고:** 아래 수치 대부분은 **회사/벤더가 보고한 값(마케팅 성격)** 이다. 방향은 신뢰하되 정확한 수치는 독립 검증되지 않았다. 우리 [Claim–Source–Correction 규칙](../CLAUDE.md)에 따라 "회사 보고(1차이나 홍보)" 로 표기. 반증·독립 감사 자료는 미확인.

## 관통하는 한 문장

팔란티어 공식 use-case 방법론의 제1원칙: **"도구·데이터가 아니라 지원하려는 *결정(decision)·워크플로*에서 출발하라."** 아래 6개 사례는 산업이 전부 달라도 같은 FDE 수(手)가 반복된다 — 표면 요구를 재정의해 **결정과 행동**으로 잇는 것.

## 사례

### 1. Airbus — A350 증산 (항공 제조)
- **표면 요구:** "제조 최적화 시스템."
- **진짜 문제:** A350은 부품 500만 개. 작업지시·누락 부품·품질 이슈가 여러 시스템에 흩어져 **아무도 전체를 한 화면에서 못 본다.** 최적화 알고리즘이 아니라 *가시성*이 병목.
- **해결:** 통합 운영 화면 — Nabeel Qureshi의 표현으로 *"비행기 만드는 Asana."*
- **결과(보고):** A350 인도량 **+33%**, 이후 정비(maintenance)로 확장.
- 원칙: 진짜 문제 ≠ 표면 요구([04 원칙 5](04-problem-solving-principles.md)).

### 2. Scuderia Ferrari — F1 (모터스포츠)
- **표면 요구:** "엔지니어에게 더 강력한 분석 도구."
- **진짜 문제:** 엔지니어가 텔레메트리·부품·시뮬레이션·테스트·드라이버 피드백 데이터를 **통합·청소하느라** 정작 엔지니어링을 못 함.
- **해결:** 데이터 통합을 제거해 엔지니어가 **핵심 업무에 복귀.**
- 원칙: last-mile / 데이터→결정([04 원칙 6](04-problem-solving-principles.md)).

### 3. Trinity Industries — 송장 감사 (철도 제조)
- **표면 요구:** "송장 감사 개선." (다른 벤더 3곳이 수개월 실패)
- **진짜 문제/열쇠:** 온톨로지가 현실을 이미 매핑 → 비기술팀이 규칙을 즉시 배포 가능.
- **결과(보고):** 부트캠프에서 **8시간** 만에 해결, 3개월 내 **$30M** 이익 영향. 속도 = 해자.
- 원칙: 자갈길→복리([01](01-fde-model.md), [02](02-problem-solving-playbook.md)).

### 4. SOMPO — 보험금 청구 (보험)
- **표면 요구:** "AI로 청구 자동 심사."
- **진짜 문제:** 배치 처리·수작업 핸드오프가 결정을 지연. 필요한 것은 자동 판정이 아니라 **결정을 시스템 안에서 실행**하는 것.
- **해결:** 청구 트리아지·사기 점검을 온톨로지 Action으로. 일 **8,000+** 사용자.
- **결과(보고):** 3년 **$60M** 이익 개선.
- 원칙: 데이터→결정→행동([03 §2](03-ontology.md)).

### 5. 글로벌 리테일러 — 공급망 컨트롤 타워
- **표면 요구:** "결품(out-of-stock)을 보는 대시보드."
- **진짜 문제:** 보는 것으로는 결품이 안 준다. 발주·재배분 **결정을 실행**해야 함.
- **해결:** 대시보드가 아니라 컨트롤 타워(결정 실행 계층).
- **결과(보고):** 결품 수준 **약 50% 감소.**
- 원칙: 대시보드 함정([02](02-problem-solving-playbook.md)).

### 6. General Mills — ERP 통합 (소비재 제조)
- **표면 요구:** "원가 절감."
- **진짜 문제:** 7개 이상 레거시 ERP가 사일로화되어 생산·원가 결정을 못 이음.
- **해결:** 온톨로지로 통합(며칠 규모), 부분 배포부터(자갈길).
- **결과(보고):** 일 약 **$40k**(연 ~$14M) 절감 — *네트워크 일부*만 배포한 값.
- 원칙: last-mile / 자갈길([01](01-fde-model.md)).

## 패턴 추출 (이 사례들에서 반복되는 것)

1. **표면 요구는 거의 항상 "도구"(AI·대시보드·최적화)로 표현된다.** 진짜 문제는 그 아래 *가시성·통합·결정 실행*에 있다.
2. **대시보드/분석은 목적이 아니다.** 결정과 행동으로 이어질 때만 값이 난다 (5번이 교과서).
3. **속도가 해자다.** 온톨로지가 현실을 미리 매핑하면 다음 문제가 극적으로 빨라진다 (3번 Trinity 8시간, [복리 게임](../practice/game/fde-campaign.html)).
4. **같은 수가 산업을 관통한다** — 항공·모터스포츠·철도·보험·리테일·소비재. 이것이 "자갈길→고속도로"가 회사 전체 전략인 이유.

## 출처 (Sources)

회사/벤더 보고(1차이나 홍보 — 수치 독립검증 안 됨):
- Palantir × Airbus Partnership Overview (palantir.com) / Nabeel Qureshi "Reflections on Palantir" — Airbus, "Asana for building planes"
- Palantir Foundry — Ferrari, Supply Chain 페이지 (palantir.com)
- Unit8, "Palantir Foundry Case Studies" (retail 컨트롤 타워 등): https://unit8.com/resources/palantir-foundry-case-studies-by-unit8/
- foundercoho, "How Ontology Became a Moat" — Trinity $30M/8시간
- 각종 요약(General Mills $40k/day, SOMPO $60M/3yr) — 2차 요약, 원 보고 대조 시 정밀화 대상

방법론(1차 공식):
- "Delivering a use case," Palantir Docs — "결정/워크플로에서 출발" 원칙: https://www.palantir.com/docs/foundry/getting-started/delivering-a-use-case
