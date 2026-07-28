# 00 · 팔란티어 개요 (Palantir Overview)

> 이 프로젝트의 목적: 팔란티어(특히 FDE)가 **문제를 정의하고 해결하는 방식**을 체득하는 것.
> 이 문서는 "무엇을 만드는 회사인가"보다 "왜 이렇게 일하는가"에 초점을 둔다.

## 한 줄 정의

팔란티어는 조직의 **데이터(data) · 의사결정(decisions) · 운영(operations)** 을 하나로 통합해 대규모로 작동시키는 소프트웨어를 만든다. 2003년 설립, 초기에는 미국 정보기관(intelligence community)의 대테러 수사·작전 지원 소프트웨어로 시작해, 이후 상업 기업으로 확장했다. 핵심 통찰: **정보기관과 대기업은 "지저분한 데이터로 실제 결정을 내려야 한다"는 근본적으로 같은 문제를 가진다.**

## 4대 플랫폼 (Principal Platforms)

| 플랫폼 | 역할 | 한 줄 요약 |
|---|---|---|
| **Gotham** | 정부/국방/정보 | 방대한 첩보를 통합해 의사결정용 인사이트로 전환. 팔란티어의 첫 온톨로지(ontology)가 여기서 나왔다. |
| **Foundry** | 상업/기업 | 개별 기관을 넘어 **산업 전체의 운영체제(operating system)** 를 지향. Ontology의 상업 버전. |
| **Apollo** | 배포/운영 계층 | 클라우드에 종속되지 않는(cloud-agnostic) 단일 제어 계층. 어떤 환경에서든 소프트웨어를 지속 운영·업데이트. 2021년 상용화. |
| **AIP** (Artificial Intelligence Platform) | AI 계층 | 2023년부터 배포. LLM 등 생성형 AI를 Gotham/Foundry 위에서 **기업 데이터에 안전하게 접목**해 운영에 투입. |

핵심 구도: **Gotham/Foundry** = 데이터를 "통합된 자산(integrated data asset)"으로 만드는 계층 → **AIP** = 그 위에서 AI를 운영화 → **Apollo** = 어디서든 안정적으로 배포·운영.

## 왜 이 회사가 "특이한가"

- 대부분의 엔터프라이즈 소프트웨어 회사는 **제품을 먼저 만들고 고객에게 판다**.
- 팔란티어는 **엔지니어를 고객 안에 심어(embed) 실제 문제를 먼저 풀고, 거기서 반복되는 패턴을 뽑아 제품으로 만든다.**
- 이 역방향 모델의 주역이 **FDE(Forward Deployed Engineer, 전진 배치 엔지니어)** 다. → [01-fde-model.md](01-fde-model.md)

## 더 깊이 볼 것

- FDE가 실제로 어떻게 일하는가 → [01-fde-model.md](01-fde-model.md)
- 문제를 정의·해결하는 구체적 플레이북 → [02-problem-solving-playbook.md](02-problem-solving-playbook.md)
- 이 모든 것의 기술적 핵심, Ontology → [03-ontology.md](03-ontology.md)

## 출처 (Sources)

- Palantir 10-K (FY2024), SEC — 회사 미션·플랫폼 정의: https://www.sec.gov/Archives/edgar/data/1321655/000132165525000022/pltr-20241231.htm
- "AIP, Foundry, and Apollo," Palantir Docs: https://www.palantir.com/docs/foundry/architecture-center/platforms
