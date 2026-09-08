# palantir_learning

> ⚠️ **비공식·교육용 프로젝트입니다.** 공개된 자료(팔란티어 공식 문서·SEC 파일링·평판 있는 분석글·서적)를 리서치해 재구성한 *학습 자료*이며, **Palantir Technologies와 무관**합니다. "Palantir", "Foundry", "Gotham", "AIP" 등은 Palantir Technologies의 상표입니다. 내부 기밀이 아니라 외부에서 재구성한 이해이며, 수치·사례 중 회사 보고값은 독립 검증되지 않았습니다(각 문서 출처·검증표 참조).

팔란티어(Palantir), 특히 **FDE(Forward Deployed Engineer)가 문제를 정의하고 해결하는 방식**을 체득하기 위한 학습 프로젝트.

> 목적: 정보를 모으는 것을 넘어, FDE의 사고방식을 **실습으로 몸에 익히는 것.**
>
> 🎯 **게임으로 바로 시작 (GitHub Pages):** https://triz4you0602-rower.github.io/palantir_learning_open/practice/game/index.html — 게임 허브(7종 + RPG). *리포지토리 Settings → Pages를 활성화(Source: `main`, `/root`)하면 링크가 작동합니다.* 로컬에서는 `practice/game/index.html`을 브라우저로 열어도 됩니다(모든 게임 자기완결적 HTML).

## 구조

```
palantir_learning/
├── FDE-CONSULTANT.md      # ★ 드롭인 에이전트 브리프 — 다른 프로젝트 세션에 넣으면 FDE 컨설턴트가 됨
├── CLAUDE.md              # Claude Code 작동 가이드 (FDE 파트너 역할)
├── knowledge/            # 지식 베이스 (리서치 기반, 출처 포함)
│   ├── 00-palantir-overview.md       # 회사·4대 플랫폼 개요
│   ├── 01-fde-model.md               # FDE 모델: Echo/Delta
│   ├── 02-problem-solving-playbook.md# ★ 문제 정의·해결 5단계 플레이북 (어떻게)
│   ├── 03-ontology.md                # 기술적 핵심: Ontology (무엇으로)
│   ├── 04-problem-solving-principles.md # ★ 문제를 보는 8원칙 + 카프의 관점 (왜)
│   ├── 05-problem-discovery-canon.md  # 문제 발굴의 보편 정전 + 매칭 (어디서 왔나)
│   ├── 06-ontology-critique.md        # 온톨로지 비판·논쟁 (반대편)
│   ├── 07-ontology-politics-ethics.md # 온톨로지의 정치·윤리 (학술 연구)
│   ├── 08-case-studies.md             # 실제 배포 사례집 (Airbus·Ferrari·Trinity…)
│   ├── 09-onboarding-reading-intent.md# 신입 독서 목록의 의도 재구성 (무엇을 먼저 가르치나)
│   ├── 10-triz-vs-fde.md              # TRIZ ↔ FDE 구조 비교 (공통점·차이·시사점·예측)
│   ├── 11-triz-fde-primer.md          # ★ 트리즈를 몰라도 읽히는 입문 (쉬운 설명)
│   ├── 98-external-resources.md      # 유사 목적 공개 자료 모음
│   └── 99-glossary.md                # 용어집 (영어 병기)
└── practice/             # 실습 (지식을 케이스에 적용)
    ├── README.md                     # 실습 진행 방식
    ├── case-template.md              # 케이스 템플릿 (0단계 8원칙 + 발굴 도구 + 5단계)
    ├── case-01 · case-02            # 학습 케이스 (워크된 예시·검증 실습)
    ├── rpg-mode.md                   # 🎲 RPG 모드: Claude가 GM ("RPG 시작")
    └── game/                         # 🎮 웹게임 7종 + 허브
        ├── index.html                #   🎯 게임 허브 (정문)
        ├── fde-simulator · ontology-builder · fde-campaign
        ├── politics-hardmode · ethics-classification · case-files
        └── GAME-DESIGN.md            #   게임 전체 설계
```

## 빠른 시작

1. `knowledge/00` → `01` → `02` → `03` 순서로 읽는다.
2. `practice/case-01-example-...`로 방법론 적용 예를 본다.
3. `practice/case-template.md`를 복사해 내 문제로 첫 케이스를 시작한다.
4. Claude에게 *"Echo처럼 나를 인터뷰해서 이 문제로 케이스를 시작하자"* 라고 요청한다.

## FDE 컨설턴트 — 현장 ↔ HQ 흐름 (선택)

이 저장소는 **HQ(백오피스)** 로 쓸 수 있다: [FDE-CONSULTANT.md](FDE-CONSULTANT.md)를 실제 프로젝트(현장)에 들고 나가 진단하고, **추상화된 요약만** 여기로 가져와 복리로 쌓는 방식.

- **① 들고감:** `FDE-CONSULTANT.md`를 실제 프로젝트에 복사 → 활성화(§0). 진단은 그곳 그라운드 트루스에서.
- **② 귀환 인계:** 복귀 시 §5b **4항목**(문제 재정의 · 브리프 마찰 · 패턴+n · 다음 한 수)으로. **경계: 실제 코드·데이터·개인정보·원문은 빼고 추상만.**
- **③ 복리:** 귀환 요약을 모아 **서로 다른 프로젝트에서 n≥2로 반복된 패턴**은 `knowledge/`로 승격, **브리프 마찰**은 `FDE-CONSULTANT.md`를 진화시킨다. 현장이 브리프를 가르친다.

> 실제 현장 배포 기록은 각자의 (비공개) 작업 공간에 두고 이 학습 저장소와 섞지 않는다 — 컨텍스트·데이터 격리.

## 언어 규칙

문서는 **한국어**로 쓰되, 핵심 개념은 **영어 원어를 병기**한다 (예: 온톨로지(Ontology), Echo/Delta).

## 지식의 성격

`knowledge/`의 내용은 공개 웹 자료(팔란티어 공식 문서, SEC 10-K, 분석 아티클) 리서치에 기반하며 각 문서 하단에 **출처**를 명시한다. 팔란티어 내부 기밀이 아니라 외부에서 재구성한 이해임에 유의.
