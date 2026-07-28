# 07 · 온톨로지의 정치·윤리 (Ontology as Politics)

> [04](04-problem-solving-principles.md)에서 "온톨로지 설계는 정치적"이라는 명제를 Karp·Nabeel(2차·기업 발화)에 기대어 세웠다. 이 문서는 그것을 **동료심사 학술 문헌(1차 연구)** 으로 격상하고, 우리 프로젝트가 통째로 빠뜨렸던 **윤리·감시 차원**을 더한다.
> ⚠️ 연구 지형의 편향: 이 연구들은 대부분 **Gotham(정부·경찰용)** 을 다루며, STS·감시연구 진영이다. 기업용 Foundry/AIP의 학술 분석은 상대적으로 희소(`[추론]` 논쟁성이 낮아 연구 유인이 약한 것으로 추정). 즉 아래 발견은 "감시 맥락"이라는 렌즈가 강함을 감안하고 읽을 것.

## 왜 STS·감시연구인가 (방법론)

독점 시스템이라 내부 접근이 불가능하다. 그래서 연구자들은 **특허·공개 문서·민족지(ethnography)·인터뷰** 같은 간접 방법을 쓴다. 이 우회 자체가 하나의 방법론적 성취다(§5).

| 연구 | 방법론 | 대상 |
|---|---|---|
| Brayne (2017 ASR / 2020 저서) | 5년 민족지, 약 80명 인터뷰 | LAPD의 Gotham |
| Munn (2017, 2018) | 공개 영상 분석 | Gotham의 "E-온톨로지" |
| Iliadis & Acker (2022) | 특허 155건 토픽 모델링 | 온톨로지·메타데이터 설계 |
| Galis & Karlsson (2024) | 엔지니어·경찰 인터뷰 | 덴마크 POL-INTEL |
| Ulbricht & Egbert (2024) | 규제 분석 | 독일 헤센주 hessenDATA |

## 핵심 발견 5가지

### 1. 데이터 통합이 곧 기술적 접점
온톨로지가 사일로화된 데이터셋을 결합한다. *"단일 온톨로지 안에 데이터를 통합해 [행위자들을] 빠르게 연결"* (팔란티어 법률 담당자, Brayne 인용). "Dynamic Ontology"는 데이터를 시맨틱 개념으로 번역해 **공통 어휘**를 만드는 인터페이스. → 우리 [03 §2 끊어진 루프](03-ontology.md)의 학술적 확증.

### 2. 온톨로지 설계는 정치적이다 ⭐
*"고객에게 '당신은 세계를 어떻게 보는가'를 묻는다. 은행은 계좌·거래·고객으로, 경찰은 범죄로 본다"* (팔란티어 수석 엔지니어, Galis & Karlsson 인용).

- 범주화(categorization)는 물리력 사용·감시를 **정당화하거나 탈정당화**한다.
- 이론적 뿌리: **Bowker & Star, "분류는 정치다(classification is politics)"** — 온톨로지는 이 명제의 실증 사례다.
- → [04 "데이터 통합의 정치"](04-problem-solving-principles.md)·Karp의 *"문제는 조직적이다"* 가 여기서 **블로그에서 논문으로 격상**된다.

### 3. 수행성 (Performativity) ⭐
시스템은 세계를 **표현(represent)** 하는 게 아니라, 사회기술적 과정을 통해 (범죄 같은) 현상을 **능동적으로 생산(produce)** 한다. Munn은 Annemarie Mol의 **"존재론적 정치(ontological politics)"** 를 적용.

- 즉: **범주를 고정하는 순간, 그 범주는 현실을 기술하는 동시에 생산한다.** ("우범 지역"으로 분류→순찰 집중→검거 증가→통계가 분류를 정당화하는 되먹임.)
- 이건 우리 [게임의 온톨로지 빌더](../practice/game/ontology-builder.html)가 가르치지 않는 그림자면(面): 루프를 닫는 것이 **무엇을 생산하는가**를 물어야 한다.

### 4. 조직 내 권력 재배치 ⭐
온톨로지 도입은 권력을 옮긴다. **백오피스 분석가의 권력↑, 현장의 맥락 지식은 평가절하↓** (헤센주 사례).

- 함의: 온톨로지 도입 = **"누가 개념을 정의하는가"** 라는 조직 권한 문제를 필연적으로 동반.
- 아이러니: 이건 FDE의 이상(현장 그라운드 트루스 존중, [04 원칙 1·2](04-problem-solving-principles.md))과 **긴장**한다 — 도구가 오히려 현장 지식을 지울 수 있다.

### 5. 특허로 우회 연구하는 방법론
내부 접근 없이 **특허 토픽 모델링**으로 설계 철학을 재구성(Iliadis & Acker). 메타데이터 표준을 사회 세계를 구조화하는 **"인프라화(infrastructuring)"** 현상으로 이론화. → 이 자체가 우리 [case-02 그라운드 트루스](../practice/case-02-source-verification/README.md)의 확장판: 접근 불가한 대상을 간접 증거로 검증하기.

## 균형 — 비판 문헌 내부의 반대 방증

한쪽으로 기울지 않기 위해:
- **현장의 강한 만족도** 기록이 존재(비판 문헌 내부에도).
- Brayne 본인의 결론: **무차별 데이터 수집은 기술의 필연이 아니라 사회적·정치적 *선택*** 이다. → **문제는 도구가 아니라 "무엇을 범주화하기로 선택하는가".**
- 이는 우리 [04 카프의 렌즈](04-problem-solving-principles.md)와 정확히 만난다: 기술이 아니라 조직·인간의 선택이 근본.

## FDE·이 프로젝트에 주는 함의

1. **온톨로지 스케치는 중립이 아니다.** 실습 3단계에서 Object/Link를 정할 때, *"이 범주가 무엇을 정당화하고 무엇을 지우는가"* 를 물어라.
2. **"누가 정의하는가"는 기술이자 조직 문제.** → [하드모드 게임](../practice/game/politics-hardmode.html)의 정치 시스템, [04 데이터 통합의 정치](04-problem-solving-principles.md).
3. **수행성 체크:** 루프를 닫아 "생산"되는 것이 바람직한가? (특히 심의·평가·리스크 스코어링처럼 사람을 분류하는 도메인.)
4. 사람·대상을 분류하는 실제 시스템(심의·평가·리스크 스코어링 등)에 직결: "기준을 스키마화할 때 누가 경계를 정하는가"가 곧 이 문서의 발견 2·4.

## GraphRAG·에이전트 가드레일 (2026 산업 맥락, 보강)

[03 §7](03-ontology.md)이 AIP만 다뤘으므로 산업 일반 맥락을 덧댄다:
- **GraphRAG 표준화:** 벡터 DB(의미 검색) + 지식 그래프(구조적 추론)의 결합이 2026 엔터프라이즈 AI 표준으로. 온톨로지 = 지식 그래프의 스키마 뼈대. 흐름: 질문 → [벡터: 유사 문서] + [그래프: 온톨로지 관계·제약] → 결합 컨텍스트 → LLM.
- **에이전트 가드레일:** 에이전트가 사용자 의도를 온톨로지 클래스에 먼저 매핑, 무효 요청은 생성 전 차단. *"LLM이 '고객'이 무엇인지 정하지 않는다. 온톨로지가 정한다. LLM은 온톨로지의 하류."* → [03 §7 환각의 벽](03-ontology.md)의 산업 일반화.
- ⚠️ 비판적 각주: 이 산업 서사조차 [06 §5](06-ontology-critique.md)의 "부활은 LLM 소비자 때문" 재해석과 함께 읽을 것.

## 출처 (Sources)

학술 연구(1차):
- Brayne, S. "Big Data Surveillance: The Case of Policing." *American Sociological Review* (2017)
- Brayne, S. *Predict and Surveil.* Oxford UP (2020)
- Munn, L. "Seeing with Software: Palantir and the Regulation of Life" (2017)
- Iliadis, A. & Acker, A. "The Seer and the Seen: Surveying Palantir's Surveillance Platform." *The Information Society* 38(5) (2022); "The Palantir Files." *Information, Communication & Society* 27(13) (2024)
- Galis, V. & Karlsson, B. "A World of Palantir: Ontological Politics in the Danish Police's POL-INTEL." *ICS* (2024)
- Ulbricht, L. & Egbert, S. "In Palantir We Trust?" *Big Data & Society* (2024)

이론(2차):
- Bowker, G. & Star, S.L. *Sorting Things Out* — "분류는 정치다"
- Mol, A. — "존재론적 정치(ontological politics)"

출발 문서: `ontology_2026_정리.md` §4 (2026-07-15, 사용자 제공). ⚠️ 인용문은 각 연구의 재인용이며, 정확한 문면은 원논문 대조 시 정밀화 대상.
