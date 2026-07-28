# FDE 캠페인 — 전 과정 게임 설계 (Full-Arc Game Design)

> 질문: "팔란티어가 문제를 포착·해결하는 *일련의 전 과정*을 게임으로 만들 수 있는가?" → **가능하다.** 이 문서는 그 전체 설계다.
> 핵심 통찰: 단일 배포의 5단계는 이미 [fde-simulator.html](fde-simulator.html)·[rpg-mode.md](../rpg-mode.md)가 다룬다. 팔란티어의 진짜 엔진은 **배포들이 복리로 쌓이는 메타 루프**(자갈길→고속도로) — 이것을 게임의 *진행 시스템*으로 만드는 것이 "전 과정 게임"의 열쇠다. → [01](../../knowledge/01-fde-model.md)

## 3개 레이어 = 팔란티어의 전 과정

```
 LAYER C · 캠페인 (복리)            ← 팔란티어를 팔란티어로 만드는 층. 대부분 게임이 빠뜨림.
   │  배포1의 패턴 → 재사용 primitive → 배포2가 더 빠름 (Trinity "8시간" 효과)
   ▼
 LAYER B · HQ / 제품 형성           ← 배포 사이. Delta의 자갈길에서 PD가 고속도로를 추출.
   │  패턴 추출 → primitive 제작(Magritte/Contour류) → 툴킷에 적재
   ▼
 LAYER A · 단일 배포 미션 (5단계)   ← 이미 부분 구현됨.
      몰입 → 정의 → 온톨로지 → 자갈길 → 패턴추출
```

---

## LAYER A · 단일 배포 미션 (5 Phase)

한 고객사 파견 = 하나의 미션. [02 플레이북](../../knowledge/02-problem-solving-playbook.md)의 5단계가 그대로 5개 게임 페이즈.

| 페이즈 | 게임 메커니즘 | 지식 근거 |
|---|---|---|
| **1 몰입** | 제한된 조사 슬롯으로 6곳 중 3곳 선택 → **숨은 곳 3가지** 발굴. Mom Test 질문법으로 NPC 정보 차등 공개 | [02 §1](../../knowledge/02-problem-solving-playbook.md), [05](../../knowledge/05-problem-discovery-canon.md) |
| **2 정의** | **5 Whys 사다리** (기술 가지=막다른 길, 조직 가지=근본 원인) + **리프레이밍** 3문항 | [05](../../knowledge/05-problem-discovery-canon.md), 카프 렌즈 [04](../../knowledge/04-problem-solving-principles.md) |
| **3 온톨로지** | **빌더** — Object/Link/Action을 배치, Action에 부수효과·기록을 붙여 **루프가 닫히면** 게이지 충전 (Phase 3 구현 대상) | [03](../../knowledge/03-ontology.md) |
| **4 자갈길** | 배포 전략 선택: 최소 작동 해결책 vs 과잉 일반화(함정) vs 명세 워크숍(함정) | [01](../../knowledge/01-fde-model.md), 원칙 4·5 |
| **5 패턴 추출** | 이 해결책에서 **재사용 가능한 추상**을 지목 → LAYER B로 전달 | [01](../../knowledge/01-fde-model.md) |

**공통 시스템:** 8원칙 게이지([04](../../knowledge/04-problem-solving-principles.md)) · 함정 카드(안티패턴 [02](../../knowledge/02-problem-solving-playbook.md)) · Echo/Delta 역할.

## LAYER B · HQ / 제품 형성 (배포 사이)

Delta가 만든 자갈길을 PD가 고속도로로 바꾸는 층. 팔란티어의 서비스→제품 전환을 게임화.

- **패턴 추출:** 미션에서 얻은 패턴 카드(예: "사람 머릿속/종이에 갇힌 판단을 Action 루프로 외부화")를 검토.
- **Primitive 제작:** 패턴을 **재사용 가능한 기본요소**로 승격 (Magritte=데이터 수집, Contour=시각화, Workshop=UI의 게임판). 제작에는 자원/시간 소모.
- **툴킷 적재:** 완성된 primitive는 다음 미션에서 꺼내 쓸 수 있다.
- **판정:** 너무 이르게 일반화하면(1개 사례로 플랫폼) 낭비 = *과잉 일반화* 함정. 패턴이 **2회 이상 반복**될 때 승격이 최적.

## LAYER C · 캠페인 (복리 메타 진행)

여러 미션을 잇는 로그라이트식 진행. **이 층이 "전 과정"의 완성이다.**

- **온톨로지 라이브러리:** 배포마다 만든 Object/Link 타입이 누적. 겹치는 도메인이면 재사용해 3단계를 단축.
- **복리 효과 (Trinity 8시간):** 툴킷·라이브러리가 두꺼워질수록 후속 미션의 몰입·구축이 빨라지고 저렴해진다 → **속도가 곧 해자** ([03 §6](../../knowledge/03-ontology.md)).
- **산업 전개:** 같은 버티컬(예: 병원 3곳) 미션을 연속 클리어하면 "산업 온톨로지" 언락 = Foundry의 "산업 운영체제" 서사.
- **복리 지표:** 미션당 소요 턴/자원이 줄어드는 곡선을 점수로. 첫 배포는 자갈길(느림), 다섯 번째는 고속도로(빠름)임을 *체감*시키는 것이 이 게임의 최종 교훈.

---

## 역할·실패·승리

- **역할:** Echo(발굴·정치, LAYER A 1~2단계 강점) ↔ Delta(구축, 3~4단계 강점). 페어 플레이 또는 턴제 전환. [01](../../knowledge/01-fde-model.md)
- **실패 모드 = 함정 카드:** 솔루션 우선 · 인터뷰 의존 · 대시보드 함정 · 고객 비위 맞추기 · 과잉 일반화 · (RPG 확장) 비난 프레임 · 정치 지뢰. [02](../../knowledge/02-problem-solving-playbook.md)
- **승리 조건:** 단일 미션 = 8원칙 + 근본 원인 도달 + 루프 닫기. 캠페인 = **복리 곡선**(후속 미션 효율 상승) + 산업 온톨로지 언락.

## 구축 로드맵 (정직한 현황)

| Phase | 내용 | 상태 |
|---|---|---|
| **1** | 단일 시나리오 웹게임 (한빛로지스, LAYER A 축약) | ✅ [fde-simulator.html](fde-simulator.html) |
| **2** | RPG 모드 — Claude가 GM, 자유 대화 발굴 | ✅ [rpg-mode.md](../rpg-mode.md) |
| **3** | **온톨로지 빌더** — Object/Link/Action 직접 설계, 루프 게이지 4칸 (LAYER A §3 심화) | ✅ [ontology-builder.html](ontology-builder.html) |
| **4** | **캠페인 셸** — 4개 미션 + HQ primitive 승격(n≥2 규칙) + 복리 곡선 + 트리니티 피날레 (LAYER B·C) | ✅ [fde-campaign.html](fde-campaign.html) |
| **5** | 하드 모드 — 정치 시스템(신뢰 게이지·정치 자본·데드라인·사보타주·거버넌스=외교) | ✅ [politics-hardmode.html](politics-hardmode.html) |
| **6** | 윤리 편 — 범주의 무게(수행성·분류의 정치·권력 재배치). 빌더 "수행성 코다" + 캠페인 "도메인 드리프트" | ✅ [ethics-classification.html](ethics-classification.html) |

> 로드맵 완료. 전 6개 페이즈 구현됨 — 발굴→정의→모델링→구축→복리→채택(정치)→윤리(수행성)까지 플레이 가능.

## LAYER D · 윤리 (Phase 6에서 추가)

앞의 5개는 전부 **"루프를 닫으면 승리"** 라는 역량(competence) 게임이었다. LAYER D는 그 그림자를 다룬다: **범주를 고정하는 순간, 그것은 현실을 기술하는 데 그치지 않고 생산한다(수행성).** → [07](../../knowledge/07-ontology-politics-ethics.md)

- **범주의 무게** ([ethics-classification.html](ethics-classification.html)): '승리' 없는 게임. 효율·수행성 부채·현장 권력의 3-미터 균형. 6개 딜레마, 다중 엔딩(정밀한 도구 ↔ 자기실현 기계).
- **수행성 코다** (빌더): 루프를 닫아 "이긴" 뒤, riskScore가 자기실현적 예언이 되는 6개월 후를 보여줌.
- **도메인 드리프트** (캠페인): 검증된 primitive조차 세상이 변하면 재적합 필요 — 온톨로지의 경직성([06 §3](../../knowledge/06-ontology-critique.md)).

## 다음 단계 (선택)

로드맵은 완료. 추가로 탐구한다면:
- **하드 모드 확장:** 상충 증언·시간 압박·질문 횟수 제한(진짜 하드).
- **실제 케이스 연동:** 플레이어 자신의 실제 프로젝트를 게임 시나리오로 (선택).
