# 실습 (Practice) — FDE처럼 문제 풀기

지식([../knowledge/](../knowledge/))을 읽는 것만으로는 "체득"이 안 된다. 여기서는 **FDE의 5단계 워크플로**([02-problem-solving-playbook.md](../knowledge/02-problem-solving-playbook.md))를 실제 케이스에 적용한다.

## 진행 방식

1. 풀고 싶은 **현실의 문제**를 하나 고른다 (내 업무, 관심 도메인, 가상의 고객 무엇이든).
2. `case-template.md`를 복사해 `case-XX-<이름>/README.md`로 새 케이스 폴더를 만든다.
3. 5단계를 순서대로 채운다. 각 단계의 **산출물**을 남긴다.
4. 5단계(패턴 추출) 회고를 반드시 쓴다 — 여기서 "체득"이 일어난다.

## 5단계 요약

| 단계 | 이름 | 산출물 | 역할 |
|---|---|---|---|
| 1 | 몰입 (Immerse) | 현실 지도 초안 | Echo |
| 2 | 문제 정의 (Frame) | 문제 진술서 | Echo |
| 3 | 온톨로지 스케치 (Model) | Object/Link/Action 표 | Delta |
| 4 | 자갈길 구축 (Build) | 작동하는 최소 해결책 | Delta |
| 5 | 패턴 추출 (Extract) | 패턴 노트 + 회고 | Echo+Delta |

> 실제 Foundry 없이도 된다. 코드·스프레드시트·다이어그램·글 무엇으로든 "현실을 개체·관계·행동으로 모델링하고 결정/행동까지 잇는" 사고를 훈련하는 게 목적.

## Claude를 FDE 파트너로 쓰는 법

이 저장소에서 Claude는 **Echo/Delta 페어 파트너** 역할을 한다 ([../CLAUDE.md](../CLAUDE.md) 참조). 예:
- "이 문제로 케이스를 시작하자. Echo처럼 나를 인터뷰해줘." → Claude가 몰입·문제 정의를 도와 숨은 곳 3가지를 캐낸다.
- "이 문제의 온톨로지를 함께 스케치하자." → Object/Link/Action 표를 같이 만든다.
- "내 문제 진술서를 안티패턴 표로 점검해줘." → 솔루션 우선·대시보드 함정 등을 체크.

## 게임으로 훈련하기

> 🎯 **[게임 허브 (game/index.html)](game/index.html)** — 7개 게임 + RPG를 하나로 묶은 정문. 추천 여정·지식 연결 포함. 여기서 시작하세요.


- **웹게임 ①: FDE 시뮬레이터** [game/fde-simulator.html](game/fde-simulator.html) — 가상 물류회사 파견 시나리오. 숨은 곳 찾기, 5 Whys 사다리, 함정 카드(안티패턴), 8원칙 게이지·등급.
- **웹게임 ②: 온톨로지 빌더** [game/ontology-builder.html](game/ontology-builder.html) — 병원 수술부 현실을 Object/Link/Action으로 직접 모델링. 루프 게이지 4칸(포착→결정→행동→되먹임)을 채우면 온톨로지가 닫힌다. `knowledge/03` 실습판.
- **웹게임 ③: FDE 캠페인** [game/fde-campaign.html](game/fde-campaign.html) — 복리 메타게임. 4개 파견(물류→병원→조선→부트캠프)에서 패턴 카드를 모아 HQ에서 primitive로 승격(**n≥2 규칙** — 1회 관찰 승격은 현장에서 붕괴). 엔딩: 프로덕트 컴퍼니(80%) vs 서비스 회사(32%). `knowledge/01`의 자갈길→고속도로 체감판.
- **웹게임 ④: 하드 모드 — 채택 전쟁** [game/politics-hardmode.html](game/politics-hardmode.html) — 온톨로지는 완성됐고 문제는 오직 정치. 5명 이해관계자의 신뢰 게이지·정치 자본·원장 데드라인을 관리하며 8주 안에 채택시켜라. 핵심 수: Restricted View로 반대자를 아군으로(거버넌스=외교). 카프의 "문제는 조직적이다"를 체득하는 Echo의 전장.
- **웹게임 ⑤: 범주의 무게 — 분류는 정치다** [game/ethics-classification.html](game/ethics-classification.html) — 윤리 편. 리스크 온톨로지를 설계하며 **수행성**(범주가 현실을 *생산*함)의 무게를 체험. '승리'가 없는 게임 — 모든 범주엔 그림자가 있다. `knowledge/07` 실습판. (빌더엔 "수행성 코다", 캠페인엔 "도메인 드리프트"도 추가됨.)
- **웹게임 ⑥: 팔란티어 케이스 파일** [game/case-files.html](game/case-files.html) — 🗂️ 실제 배포 6건(Airbus·Ferrari·Trinity·SOMPO·리테일·General Mills). 고객의 표면 요구를 읽고 진짜 문제를 찾는 FDE 훈련. 실제 사례라 진위성·산업 폭이 다름. `knowledge/08` 실습판.
- **RPG 모드** [rpg-mode.md](rpg-mode.md) — Claude에게 **"RPG 시작"** 이라고 말하면 Claude가 게임 마스터로 가상 고객사를 연기. 자유 대화로 옳은 질문을 던지는 능력을 단련. 종료 시 8원칙 채점 + 케이스 파일로 저장 가능.
- **전 과정 게임 설계** [game/GAME-DESIGN.md](game/GAME-DESIGN.md) — 발굴→해결→복리 전 과정을 3레이어(단일 배포 / HQ 제품형성 / 캠페인 복리)로 게임화하는 마스터 설계 + 구축 로드맵.

## 케이스 목록

- `case-01-example-restaurant-noshow/` — 워크된 예시(가상 레스토랑 노쇼). 어떻게 채우는지 참고용.
- `case-02-source-verification/` — 대중 자료로 심화한 `knowledge/03` §4를 공식 docs로 대조 검증. "그라운드 트루스" 메타 실습.
- (새 학습 케이스는 `case-template.md`를 복사해 여기에)

> **실제 현장 배포**(FDE-CONSULTANT.md를 실제 프로젝트에 들고 나가는 것)는 이 학습 저장소가 아니라 **각자의 비공개 작업 공간**에서 진행한다 — 데이터·컨텍스트 격리.
