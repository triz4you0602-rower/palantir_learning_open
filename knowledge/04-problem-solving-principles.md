# 04 · 문제 정의·해결 원칙 (Problem-Solving Principles)

> [02-problem-solving-playbook.md](02-problem-solving-playbook.md)가 **"무엇을 하는가"(단계)** 라면, 이 문서는 **"어떻게 보는가"(사고·원칙)** 다. 팔란티어 내부자·경영진의 1차 증언에서 뽑은, 문제를 대하는 마인드셋. 각 원칙은 짧은 인용 + 출처 + "적용법" + 플레이북 연결로 구성.
>
> ⚠️ 성격: 이 문서는 대부분 **1차 발화·회고(=주관적 증언)** 다. 기술 스펙이 아니라 *철학*이므로, 검증의 초점은 "출처가 실제로 그렇게 말했는가"에 있다. 인용은 원문 뉘앙스를 살리되 짧게.

## 이 모든 것이 푸는 근본 문제: Impedance Mismatch

엔터프라이즈 소프트웨어는 PM이 상상한 시나리오에서 쓰이지 않는다. 데모 환경과 실제 현장 사이에서 소프트웨어는 **기관(institution)** 과 부딪히고 — 기관이 이긴다. 제품팀은 고객의 *근사 모델*만 갖는다. 실제 운영 현실은 문화·레거시·미문서화된 오류·어긋난 인센티브 때문에 그 그림에서 **표류(drift)** 한다.

- 이 간극을 balaji bal은 **"가독 불가능성(illegibility)"** 이라 부른다. 팔란티어의 답: *"안전한 거리에서 연구하지 말고, 그 가독 불가능성 *안에서* 작동하라."* (balaji bal, 2차)
- 핵심 통찰: 다른 업계는 이걸 **서비스(services)** 라 불렀고, 팔란티어는 **제품 발견(product discovery)** 이라 불렀다. — 이 해석 차이가 20년째 승자와 패자를 가른다.

> 즉, FDE 모델·온톨로지·5단계는 전부 **impedance mismatch를 없애기 위한 장치**다. 이걸 이해하면 나머지가 하나로 꿰인다.

---

## 원칙 1 · 공감하지 말고, 사용자가 되어라 (Be the user)

> "사용자에 공감하지 말고, 사용자가 되어라 (Don't just empathize with the user; be the user)." — Palantir 원칙 (Lenny's Newsletter, 2차)

인터뷰·설문으로 "공감"하는 것으로는 부족하다. 엔지니어가 현장에 3~4일/주 상주하며 **암묵지(tacit knowledge)** 를 몸으로 익힌다.

**적용법:** 케이스 1단계에서 "인터뷰"가 아니라 "옆에 앉아 관찰"을 선택했는지 점검. → [02 §1단계](02-problem-solving-playbook.md)

## 원칙 2 · 건물 밖으로 나가라 — 희소한 건 맥락이다 (Context is scarce)

> "맥락, 그것이 희소한 것이다 (Context is that which is scarce)." — Tyler Cowen (Nabeel Qureshi가 인용, 1차 회고)

팔란티어의 문화적 편향: *"일단 비행기부터 타고, 질문은 나중에."* (Steve Blank의 "get out of the building"과 같은 맥). 요구사항 문서(requirements doc)는 납작해진 현실이고, 진짜 정보는 현장에만 있다.

> Shyam Sankar(CTO, 1차): *"좋은 아이디어는 팔로알토에서 딸기 먹으며 나오지 않는다. 지부티의 사격 진지와 디트로이트의 공장 바닥에서 나온다."*

**적용법:** 문제를 책상에서 정의하려 하면 멈추고 "그라운드 트루스에 접근했는가?"를 물어라. → [02 대원칙 1](02-problem-solving-playbook.md)

## 원칙 3 · 엔지니어가 영업한다, 영업사원이 아니라 (Engineers do sales)

> 미션 지향 엔지니어를 고객 앞에 세운다. 전문 영업팀을 두지 않는다.

이유: 번역 계층(translation layer)이 곧 **impedance mismatch**를 만든다. 문제와 해결을 아는 사람이 직접 대화해야 신호가 손실되지 않는다. FDE는 PD 아키텍트와 **같은 기술 면접**을 통과한다 — "현장용 저급 인력"이 아니다.

**적용법:** 문제 이해자와 해결 구축자 사이에 중개 계층을 넣지 마라. Echo↔Delta가 직접 붙는 이유. → [01 Echo & Delta](01-fde-model.md)

## 원칙 4 · 살아있는 제품으로 반복하라 (Iterate with live products)

> 실험 단위는 디자인·개념이 아니라 **작동하는 코드**다. "관심 없으면 안 쓸 것이고, 그럼 즉시 알게 된다." (Lenny's, 2차)

전통적 요구사항 수집·워터폴 없이, 빠르게 배포하고 실사용자와 반복한다. 효율을 내주고 **명료함(clarity)** 을 얻는 거래.

**적용법:** "완벽한 계획" 대신 자갈길(최소 작동 해결책)을 빨리 내놓고 현실의 반응을 본다. → [02 §4단계](02-problem-solving-playbook.md)

## 원칙 5 · 문제를 풀어라, 오버피팅은 걱정 마라 (분업의 미학)

> "네 일은 문제를 푸는 것이고 오버피팅을 걱정하는 게 아니다. PD의 일은 네가 만든 걸 일반화하는 것이다." — Nabeel Qureshi (1차 회고)

FDE는 **특정 고객에 과적합된 해결책**을 부끄러워하지 않고 만든다(자갈길). 일반화(고속도로)는 PD의 몫. 이 분업이 "확장 불가능한 수작업 → 복리 플랫폼 코드"를 가능케 한다.
- 실제 산물: Magritte(데이터 수집), Contour(시각화), Workshop(UI) — 전부 FDE의 반복된 수작업에서 추출됨.

**적용법:** 첫 케이스부터 플랫폼을 지으려는 *과잉 일반화* 안티패턴을 경계. 자갈길 먼저. → [02 §5단계·안티패턴](02-problem-solving-playbook.md)

## 원칙 6 · 데이터가 아니라 결정이다 (Data is snake oil)

> Shyam Sankar(1차): *"데이터는 새로운 석유가 아니라 새로운 만병통치약(snake oil)이다 — 결정에 쓸 수 없다면 무가치하다."*

데이터·대시보드 자체는 목적이 아니다. **결정과 행동**으로 이어질 때만 가치. 온톨로지의 Action이 그 연결. → [03 §2·§4](03-ontology.md)

**적용법:** 산출물이 "예쁜 시각화"에 멈추면 *대시보드 함정*. "어떤 결정/행동으로 이어지나?"를 물어라. → [02 안티패턴](02-problem-solving-playbook.md)

## 원칙 7 · 승리의 우선성 — 결과에서 역산하라 (Primacy of winning)

> Shyam Sankar(1차): *"우리가 신성시하는 것은 승리의 우선성이다. 세상에 필요한 결과를 먼저 놓고, 그것을 만들어내는 데 실제로 필요한 것을 제1원리(first principles)에서 거꾸로 사고한다."*

절차·정치·직함이 아니라 **결과**가 최종 심판. Nabeel의 대조: *"작동하지 않는 웹사이트에 1.1억 달러 계약을 또 주는 것 — 그게 실질을 이긴 정치다."*

**적용법:** "이 활동이 옳은가?"보다 "이것이 결과를 만드는가?"를 먼저. 문제 정의(§2단계)의 성공 지표를 결과 기준으로. → [02 §2단계](02-problem-solving-playbook.md)

## 원칙 8 · 복리로 가치가 쌓이는 것을 지어라 (Compounding value)

> 다음 사용자가 이전 사용자 덕분에 더 나아지도록 설계한다 — 성장하는 데이터 자산, 네트워크 효과.

**적용법:** 케이스 5단계에서 "이 해결책이 다음 문제를 더 쉽게 만드는가?"를 물어라. → [03 해자](03-ontology.md)

---

## 방법에 내장된 인재 철학 (Talent as method)

FDE 방법이 성립하려면 특정 유형의 사람이 필요하다 — 방법과 인재는 분리되지 않는다.

1. **도메인 학습 속도 (domain learning velocity):** 고객의 언어("capacity management", "patient throughput")를 빠르게 흡수. 의료·항공·신약 등 전문 어휘를 말할 수 있어야 한다.
2. **사회적·정치적 직관:** Nabeel은 Keith Johnstone의 *Impro*(즉흥극 이론)를 인용 — 상/하 지위(status) 행동을 읽고 방을 파악하고 신뢰를 쌓는 것. *"성공적 FDE에는 사회적 맥락에 대한 비범한 민감성이 필요했다."* ⚠️ 단 "*Impro* = 지위 이론"이라는 독법은 **재직자의 해석**이며 저자 본인의 강조점은 즉흥성·실패 허용이다 → [09 §H2 대안 해석](09-onboarding-reading-intent.md).
3. **주도성 + 낮은 자아 (agency & low ego):** 디렉터의 지시를 무시하고 정작 필요한 인프라를 지은 엔지니어를 칭송하는 문화. 평평한 직함 구조 → *"아무도 남에게 이래라저래라 할 수 없었다."*
4. **고통을 먹는 의지 (eat pain):** 표준 컨설턴트가 고객을 *편안하게* 유지하려는 반면, FDE는 지저분한 진실을 직면한다. → [01 인재 선발 원칙](01-fde-model.md)

### 대조: 회고가 말하는 인재 vs 회사가 공표한 채용 기준 (1차, 렌더 확인 2026-08-18)

위 4항목은 전부 **재직자 회고(1인칭)** 기반이다. 그런데 팔란티어 **공식 채용 페이지**는 엔지니어 역량을 따로 공개한다. 나란히 놓으면 그림이 달라진다.

| 회고가 강조하는 것 (1인칭 회고) | 공식 채용 페이지가 공개하는 역량 (공식 1차) |
|---|---|
| 도메인 학습 속도 · **사회적·정치적 직관** · 낮은 자아 · 고통을 먹는 의지 | 좋은 코드 쓰기 · **코드 효율성 분석** · **기존 시스템 안에서 작업하기** · 기술 문제 해결 · **열린 질문 다루기(Navigating Open-Ended Questions)** |
| 출처 성격: 사후 회고, 선택적 기억 가능 | 출처 성격: 현재 진행형 채용 기준, 회사가 책임지는 문면 |

**읽는 법 세 가지:**

1. **"사회적 감수성 vs 기술 역량"은 양자택일이 아니다.** 회고는 *합격 이후 성공을 갈랐던 것*을 말하고, 채용 페이지는 *합격의 문턱*을 말한다. 두 목록은 경쟁하지 않고 **직렬로 놓인다** — 기술로 들어와서 사회적 능력으로 성공한다.
2. **"기존 시스템 안에서 작업하기"가 공식 역량에 있는 것은 의미심장하다.** 그린필드 설계가 아니라 **남이 만든 지저분한 것 안에서 움직이는 능력** — 원칙 4(살아있는 제품으로 반복)·원칙 5(오버피팅 걱정 말기)의 채용 버전이다.
3. **"열린 질문 다루기"는 발굴 역량의 면접 형태다.** → [05 발굴 정전](05-problem-discovery-canon.md), [09](09-onboarding-reading-intent.md).

> ⚠️ **이 대조의 세 가지 한계 (적대적 검증 2026-08-18):**
> ⑴ **직군이 다르다.** 공식 역량 가이드는 **엔지니어 일반**용이다("여러 종류의 엔지니어가 있으니 우리가 가장 중시하는 역량을 중심으로 절차를 구성했다"). 페이지는 절차가 **직군·스킬셋별로 개인화된다**고만 밝히고 **FDE 전용 기준은 공개하지 않는다.** 따라서 엄밀히는 "FDE 인재론 vs FDE 채용 기준"의 대조가 아니다.
> ⑵ **시점이 다르다.** 회고는 **2015~2023년경** 경험, 채용 페이지는 **현재** 문면이다.
> ⑶ **"직렬"은 우리 추론이다.** "기술로 들어와 사회적 능력으로 성공한다"는 정리는 회사도 회고자도 말하지 않았다. 두 목록이 다른 것을 강조한다는 **사실**과, 그것이 문턱/성공요인으로 나뉜다는 **해석**을 섞지 말 것.
>
> → 이 대조는 [09 §H5](09-onboarding-reading-intent.md)와 같은 결론에 독립적으로 도달한다: 신입 독서 목록에 **기술서가 0권**인 것은 "기술 경시"가 아니라 **분업**이다 — 기술은 면접·도제로, 책은 그것들이 못 하는 영역으로.

## 잊기 쉬운 현실: 데이터 통합의 정치

기술만으로는 안 된다. 조직은 자기 존재를 정당화하려 데이터 소스 주위에 **게이트키퍼**를 만든다. 진짜 해결에는 기술 도구(롤 기반 접근·보안 마킹·감사 추적)와 **정치적 항해**가 둘 다 필요하다. → Echo의 역할, [01](01-fde-model.md) · 거버넌스 [03 §5](03-ontology.md)

> 📚 이 명제는 블로그가 아니라 **동료심사 학술 연구**로도 뒷받침된다 — Brayne(민족지), Bowker & Star "분류는 정치다", 권력 재배치, 수행성. 1차 근거와 윤리 차원은 [07-ontology-politics-ethics.md](07-ontology-politics-ethics.md).

## 사례 한 컷: Airbus — "비행기 만드는 Asana"

- 표면 요구: "제조 최적화" (일반적·모호).
- 실제 문제: A350 증산을 위해 작업지시·누락 부품·품질 이슈를 **하나의 화면**에서 보는 것.
- 해결: 데이터베이스가 아니라 *"비행기 만드는 Asana(Asana, but for building planes)."* — Nabeel Qureshi (1차)
- 교훈: **표면 요구 ≠ 진짜 문제.** 몰입이 문제 정의를 바꾼다. (우리 [case-01](../practice/case-01-example-restaurant-noshow/README.md)의 "진짜 문제는 예측이 아니라 신호 소실"과 같은 구조.)

## 알렉스 카프의 관점 (Karp's Lens) — 문제 정의를 두 층 더 깊이

CEO 알렉스 카프(Alex Karp)는 하버마스(Habermas) 문하의 사회이론 박사다. 그는 위 원칙들에 **인지·방법론을 넘어선 두 층**을 더한다. (이 계보의 보편 정전은 [05-problem-discovery-canon.md](05-problem-discovery-canon.md) 참조.)

### 카프의 핵심 발언
- **관찰의 우선성:** *"소프트웨어 구축은 관찰의 예술이자 과학이지 이론이 아니다. *작동해야 할 것*에 대한 통념을 끊임없이 버리고 *실제 작동하는 것*을 택하라."* — *The Technological Republic* (1차)
- **진짜 문제는 조직·인간:** *"우리의 문제는 기술적인 것이 아니다. 조직적인 것이다."* / *"데이터 연결만으로는 조직이 바뀌지 않는다."* (사내 관리도 근본 원인 분석 기반 — 실패의 진짜 이유는 자주 **대인관계적**)
- **의미 있는 문제를 골라라:** *"소셜미디어·음식배달 앱의 시대가 왔다 — 의학·교육·국방의 진보는 기다려야 했다."* (1차)
- **분산 조율:** *"스타트업은 꿀벌 떼(honeybee swarm)가 되어야 한다 — 과도한 중앙통제 없는 조율."* (1차)

### 카프가 *추가하는* 두 층
1. **인식론적 층 (루만 Luhmann):** 문제가 안 풀리는 근본 이유는 부서마다 *현실을 관찰하는 코드 자체가 다르기 때문*(법·경제·과학은 양립 불가한 코드로 세계를 본다 → 사일로). 그래서 대시보드가 아니라 **공유 온톨로지 = 공통 언어**가 선결 조건. → [03 온톨로지](03-ontology.md)의 *철학적 정당화*.
2. **조직·도덕적 층:** Rumelt의 "증상 vs 근본"을 한 발 더 밀어 — **근본 원인은 대개 대인관계·정치**. → 위 "데이터 통합의 정치", Echo의 존재 이유.

### 원칙 ↔ 카프 매칭
| 우리 원칙/문서 | 카프의 발언·관점 |
|---|---|
| 원칙 1·2 (현장·관찰) | "소프트웨어는 관찰의 예술 — 작동하는 것을 택하라" |
| 원칙 5 (진짜 문제 ≠ 표면) | "문제는 기술이 아니라 조직적" |
| 원칙 6 (데이터→결정) | 하버마스: "공통 맥락의 대화 > 데이터 전시" |
| 원칙 7 (결과 역산) | "사소한 문제(앱)에 자본이 낭비됐다" |
| 인재: 분산·주도성 | "honeybee swarm" |
| [03 Ontology] | 루만: 온톨로지 = 체계 간 "구조적 결합" |

> 종합: 카프는 "옳은 문제를 발굴하라"에 **"그 옳은 문제는 거의 항상 조직적·인식론적이며 기술은 그다음"** 을 덧댄다. FDE가 코드만큼 정치·도메인 언어에 능해야 하는 이유.

⚠️ 검증 노트: 카프 직접 인용은 *The Technological Republic*(1차). 하버마스·루만 ↔ 온톨로지 연결은 **2차 해설자의 해석**이며 "카프 본인의 표현"과 구분한다. (출처 §참조)

## 이 프로젝트에서의 활용

- 케이스를 시작할 때 이 8원칙을 **체크리스트**로 쓴다: 사용자가 되었나(1) · 현장에 갔나(2) · 중개 계층 없나(3) · 작동 코드로 반복하나(4) · 자갈길 먼저인가(5) · 결정으로 잇나(6) · 결과에서 역산하나(7) · 복리인가(8).
- 카프의 렌즈를 얹어: **"이 문제의 근본 원인은 기술인가 조직인가?"**, **"부서 간 관찰 코드(용어·목표)가 다른가?"** 를 1~2단계에서 물어라.
- 원칙(04)은 *왜*, 플레이북(02)은 *어떻게*, 온톨로지(03)는 *무엇으로*, 정전(05)은 *어디서 왔나* — 함께 보면 팔란티어의 문제 접근이 하나로 꿰인다.

## 출처 (Sources)

1차 (내부자·경영진 발화):
- Nabeel Qureshi, "Reflections on Palantir" (8년 근무 회고, 2015년 여름 입사 · 에세이 2024-10-15) — 이 문서 다수 인용의 기반: https://nabeelqu.co/reflections-on-palantir
- **Palantir Careers — Getting Hired (공식 1차, 렌더 확인 2026-08-18)** — §인재 철학의 대조표 근거(엔지니어 역량 가이드·"열린 질문 다루기"): https://www.palantir.com/careers/getting-hired/
- Shyam Sankar (Palantir CTO) 인용 — via Lenny's Newsletter 및 TBPN: https://www.tbpndigest.com/story/2025-04-17/palantirs-shyam-sankar-on-enterprise-ai-autonomy-defense-reformation-and-why-the-forward-deployed-engineer-cant-be-cargo-culted

2차 (심층 분석):
- Lenny's Newsletter, "The unconventional Palantir principles that catalyzed a generation of startups" (명명된 원칙): https://www.lennysnewsletter.com/p/the-unconventional-palantir-principles
- balaji bal, "Understanding Palantir: Forward-Deployed Engineers..." (impedance mismatch / illegibility): https://medium.com/@balajibal/understanding-palantir-forward-deployed-engineers-and-the-making-of-an-unusual-platform-company-494dc7812f24
- Diogo Silva Santos, "A Comprehensive Analysis of Palantir's FDE Model": https://medium.com/activated-thinker/a-comprehensive-analysis-of-palantirs-forward-deployed-engineering-model-4502a036b5e4

알렉스 카프(§"카프의 관점"):
- Alexander C. Karp & Nicholas Zamiska, *The Technological Republic* (2025) — 직접 인용의 출처 (via Goodreads 인용 확인): https://www.goodreads.com/author/quotes/49850495.Alexander_C_Karp
- 하버마스·루만·파슨스 ↔ Palantir 해설 (2차): https://note.com/yoichiro_shiba/n/n53ae1d473e03?hl=en
- Karp 주주서한 모음 (1차): https://www.palantir.com/newsroom/letters/

참고: 인용된 3차 출처 — Tyler Cowen("context is scarce"), Steve Blank("get out of the building"), Keith Johnstone(*Impro*) 는 Nabeel의 회고를 통해 재인용됨. 보편 정전 전체는 [05-problem-discovery-canon.md](05-problem-discovery-canon.md).
