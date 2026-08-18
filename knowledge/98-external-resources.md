# 98 · 외부 자료 (External Resources)

> 이 프로젝트와 목적이 겹치는 공개 자료 모음. 무엇을 참고·교차검증할지 빠르게 찾기 위함.
> 성격 태그: 📚 개념/독서 · 🛠️ 실습/템플릿 · 🎓 교육 프로그램 · 🎤 1차 발화(권위)

## 우리 프로젝트의 자리매김

대부분의 공개 자료는 (a) FDE **취업용 스킬셋**이거나 (b) 읽는 **개념서**다. 이 프로젝트처럼 "**FDE의 문제 정의·해결 사고를 케이스 실습으로 반복 체득**"하고 **Claude를 Echo/Delta 페어 파트너**로 붙이는 구성은 드물다. 아래 자료들은 그 방법론을 **교차검증·심화**하는 데 쓴다.

## GitHub 저장소

- 🛠️ **[pierpaolo28/Awesome-FDE-Roadmap](https://github.com/pierpaolo28/Awesome-FDE-Roadmap)** — 이 프로젝트와 가장 유사. FDE가 되기 위한 3단계 커리큘럼 로드맵. 데이터 엔지니어링·GCP·AI 에이전트/RAG + 전략(discovery, scoping, MECE, "Delta thinking"). Site Survey·SOW·Technical PRD 등 복사용 템플릿 포함. → *우리는 취업 스킬셋보다 방법론 체득에 집중한다는 점이 차이.* `practice/case-template.md` 보강 아이디어의 출처.
- 📚 **[Leading-AI-IO/palantir-ontology-strategy](https://github.com/Leading-AI-IO/palantir-ontology-strategy)** — 오픈소스 "책". Palantir 기원(CIA/DoD) → Ontology 아키텍처 → AIP → FDE 전략. 영어·일본어, CC BY 4.0. → `03-ontology.md`의 심화 참고서.
- 🛠️ **[s-andthat/palantir-ai-fde-library](https://github.com/s-andthat/palantir-ai-fde-library)** — Palantir **AI FDE 에이전트**용 커뮤니티 프롬프트·에이전트 아키텍처 라이브러리. 학습이 아니라 실무 도구 성격. → `01-fde-model.md`의 "AI FDE" 절 참고.
- 🗂️ **[GitHub Topics: palantir-foundry](https://github.com/topics/palantir-foundry)** — Foundry 관련 저장소 모음(디렉토리).

## 방법론 집중 분석 — "문제를 어떻게 정의·해결하는가" (핵심)

> `04-problem-solving-principles.md`의 기반. 문제 접근 *사고 자체*를 파고든 자료.

- 🎤 **[Nabeel Qureshi — "Reflections on Palantir"](https://nabeelqu.co/reflections-on-palantir)** ⭐ **정전(canonical).** 8년 근무자 1차 회고. FDE/PD 분업, impedance mismatch, "be the user", Airbus "비행기 만드는 Asana", Magritte/Contour, 인재 철학. → `04` 다수 인용의 기반.
- 🎤 **[Shyam Sankar (CTO) — TBPN 인터뷰](https://www.tbpndigest.com/story/2025-04-17/palantirs-shyam-sankar-on-enterprise-ai-autonomy-defense-reformation-and-why-the-forward-deployed-engineer-cant-be-cargo-culted)** — "FDE는 cargo-cult할 수 없다", 데이터=snake oil, primacy of winning.
- 📚 **[Lenny's Newsletter — Unconventional Palantir Principles](https://www.lennysnewsletter.com/p/the-unconventional-palantir-principles)** ⭐ 명명된 원칙 정리 → `04`와 직접 매핑.
- 📚 **[balaji bal — Understanding Palantir](https://medium.com/@balajibal/understanding-palantir-forward-deployed-engineers-and-the-making-of-an-unusual-platform-company-494dc7812f24)** — impedance mismatch / illegibility 프레이밍의 원류.

## 문제 발굴·정의의 보편 정전 (팔란티어 외부)

> `05-problem-discovery-canon.md`의 기반. 팔란티어와 무관하나 같은 결론에 수렴하는 고전.

- 📖 **Gause & Weinberg, *Are Your Lights On?***: https://geraldmweinberg.com/Site/AYLO.html
- 📄 **Wedell-Wedellsborg, "Are You Solving the Right Problems?" (HBR 2017)** — 리프레이밍: https://hbr.org/2017/01/are-you-solving-the-right-problems
- 📖 **Rumelt, *Good Strategy Bad Strategy*** — 진단(diagnosis): https://www.alexmurrell.co.uk/summaries/richard-rumelt-good-strategy-bad-strategy
- 🏭 **Toyota Genchi Genbutsu + 5 Whys**: https://mag.toyota.co.uk/genchi-genbutsu/
- 🚀 **Steve Blank, Customer Development**: https://steveblank.com/tag/customer-development/
- 🧩 **Christensen, Jobs to Be Done**: https://www.christenseninstitute.org/theory/jobs-to-be-done/

## 알렉스 카프 (Alex Karp, CEO) — 1차 발화

- 📕 **Alexander C. Karp, *The Technological Republic* (2025)** — 인용집: https://www.goodreads.com/author/quotes/49850495.Alexander_C_Karp
- 🎤 **Karp 주주서한 모음 (Letters from the CEO)**: https://www.palantir.com/newsroom/letters/
- 📚 **하버마스·루만·파슨스 ↔ Palantir 온톨로지 해설 (2차)**: https://note.com/yoichiro_shiba/n/n53ae1d473e03?hl=en

## 온톨로지 — 비판·논쟁·학술 (균형 자료)

> `06-ontology-critique.md`·`07-ontology-politics-ethics.md`의 기반. 옹호 일변도를 벗어나기 위한 반대편·학술 문헌.

- 📄 **Rich Sutton, "The Bitter Lesson" (2019)** — 손설계 지식 구조 반론: http://www.incompleteideas.net/IncIdeas/BitterLesson.html
- 📚 **Brayne, *Predict and Surveil* (Oxford UP, 2020) / ASR (2017)** — LAPD Gotham 5년 민족지
- 📚 **Iliadis & Acker, "The Seer and the Seen" (The Information Society, 2022)** — 특허 토픽 모델링
- 📚 **Galis & Karlsson, "A World of Palantir" (ICS, 2024)** — 온톨로지의 정치, POL-INTEL
- 📚 **Ulbricht & Egbert, "In Palantir We Trust?" (Big Data & Society, 2024)**
- 📖 **Bowker & Star, *Sorting Things Out*** — "분류는 정치다" 이론적 뿌리
- 🗂️ **PuppyGraph, "Palantir Ontology: Architecture & Benefits" (2026.5)** — 대/소문자(제품명 vs 개념) 구분
- 🧑‍💻 사용자 제공: `ontology_2026_정리.md` (2026-07-15) — 06·07의 출발 문서

## 서적 (Books)

### 팔란티어 신입 독서 목록 (2015년경 관행 — 1차급 = 재직자 회고. 통칭 "Day-1 목록")
> ⚠️ **정정(2026-08-18):** 이전 제목의 "**공식 온보딩 — 다수 보도**"는 **틀렸다.** ① "Day 1에 5권"은 소셜 요약(2차)이 만든 판본 — 1차급 출처(8년 재직자 Nabeel Qureshi 회고, 2024-10-15)는 **책 4권 발송 + *Principles* 는 출간 전 PDF**, 표현도 "입사 시(when you joined)"다. ② "다수 보도"는 착시 — 널리 인용되는 X 게시물은 그 에세이의 **이틀 후(2024-10-17) 재요약**으로, 단일 출처의 반향이다. ③ **팔란티어 공식 문서에 이 목록은 없다**(채용 페이지 렌더 확인). ④ 목록은 **2015년경 관행**이며 현재 유효 근거 없음. 상세 검증표·의도 재구성 → **[09](09-onboarding-reading-intent.md)**.
>
> 인사이트: **기술서 0권.** 전부 사람·발굴·사회적 기술 → "FDE 역량 = 도구가 아니라 인간·문제 다루기"를 커리큘럼으로 선언. (가설 H5 — 근거·반증은 [09](09-onboarding-reading-intent.md))
- 📖 **Keith Johnstone, *Impro*** — 즉흥극·**지위(status) 읽기**·"yes-and". 방을 읽고 신뢰 쌓기. (→ [05 발굴 인터뷰](05-problem-discovery-canon.md), [04](04-problem-solving-principles.md))
- 📖 **Steve Portigal, *Interviewing Users*** — **사용자 인터뷰·발굴 방법**의 표준서. (→ [05](05-problem-discovery-canon.md))
- 📖 **Ray Dalio, *Principles*** — 1차 문구: **"믿음성 가중(believability-weighted) 아이디어 능력주의"** · **"고통 + 성찰 = 진보"** · 급진적 개방성·투명성. (우리 쪽 응용 = "아부 없는 피드백" → FDE-CONSULTANT "비위 맞추지 마라". 축자 확인: [09 §2](09-onboarding-reading-intent.md))
- 📖 **Lawrence Wright, *The Looming Tower*** — 미션·도메인 몰입(대테러 기원, 회사 신화).
- 📖 **David Allen, *Getting Things Done*** — 실행·개인 운영.

### 팔란티어 관련 서적
- 🎤 **Alexander Karp & N. Zamiska, *The Technological Republic*** (2025) — CEO 철학(내부 시각). → [04](04-problem-solving-principles.md)
- 🎤 **Shyam Sankar, *Mobilize*** (2025) — FDE 창안자(CTO)의 책. 주제는 산업기반·지정학(방법론보다 국가전략).
- 📚 **Michael Steinberger, *The Philosopher in the Valley*** (2025) — 비판적 평전(감시국가). → [07 정치·윤리](07-ontology-politics-ethics.md)
- 📕 **Peter Thiel, *Zero to One*** — Palantir 공동창업자. **secrets·definite optimism·독점=해자**. → [03 해자](03-ontology.md)
- 📗 **The Palantir Enigma** (2026) — 플랫폼(Gotham/Foundry/Apollo/AIP) 해설서.

## 플레이북·가이드 (읽는 자료)

- 🎤 **[The FDE Playbook for AI Startups — Bob McGrew (전 OpenAI CRO), Y Combinator](https://www.classcentral.com/course/youtube-the-fde-playbook-for-ai-startups-with-bob-mcgrew-489304)** — 무료 영상. "do things that don't scale, at scale" 관점. 가장 권위 있는 1차 자료 중 하나.
- 📚 **[Perspective AI — FDE Playbook (2026)](https://getperspective.ai/blog/the-forward-deployed-engineer-playbook-how-to-structure-run-and-scale-an-fde-function-in-2026)** — 5단계 라이프사이클: discovery → prototype → deploy → productize → scale back. → **우리 `02-problem-solving-playbook.md`의 5단계와 골격이 거의 일치**(교차검증).
- 📚 **[Perspective AI — Palantir FDE Playbook (Anthropic/OpenAI가 복제한 원본 모델)](https://getperspective.ai/blog/palantir-forward-deployed-engineering-playbook-anthropic-openai-copying)**
- 📚🛠️ **[Umbrex — The Forward Deployed Engineer Playbook](https://umbrex.com/resources/the-forward-deployed-engineer-playbook/)** — 온보딩 커리큘럼·도제(apprenticeship)·인증 게이트·discovery/prototyping/deployment 훈련.
- 📚 **[The FDE Playbook: A Practitioner's Field Manual (Early Draft)](https://conikeec.substack.com/p/the-forward-deployed-engineer-playbook)** — 실무자 관점 필드 매뉴얼.
- 🛠️ **[forwarddeployedengineer.site — Roadmap](https://www.forwarddeployedengineer.site/roadmap)** — FDE 커리어 로드맵/가이드.

## 분석 아티클 (이미 knowledge/에 인용된 것 포함)

- 📚 **[How Ontology Became a Moat: Palantir's FDE Model, Demystified — foundercoho](https://foundercoho.substack.com/p/how-ontology-became-a-moat-palantirs)** — `01`, `02`, `03`에서 인용.
- 📚 **[A Comprehensive Analysis of Palantir's FDE Model — Diogo Silva Santos](https://medium.com/activated-thinker/a-comprehensive-analysis-of-palantirs-forward-deployed-engineering-model-4502a036b5e4)** — `01`, `02`에서 인용.
- 📚 **[How Palantir Invented the Forward Deployed Engineer Model — fde.academy](https://fde.academy/blog/how-palantir-invented-the-forward-deployed-engineer-model)**
- 📚 **[Palantir's Secret Weapon Isn't AI — It's Ontology (DEV Community)](https://dev.to/s3atoshi_leading_ai/palantirs-secret-weapon-isnt-ai-its-ontology-heres-why-engineers-should-care-kk8)**

## 교육 프로그램 (유료·구조화)

- 🎓 **[FDE Academy](https://fde.academy/)** — 32주 집중 부트캠프 + AI FDE 인증.
- 🎓 **[Isha — FDE Master Program](https://www.ishatrainingsolutions.org/courses/forward-deployment-engineer-fde-end-to-end-solution-deployment/)** — GenAI/RAG/에이전트 라이브 트레이닝.

## 공식 학습 플랫폼 (Palantir 무료 — 1차, 최우선)

> 우리 자료집에 빠져 있던 팔란티어 *공식 무료 교육*. 실제 Foundry enrollment가 있으면 핸즈온, 없어도 개념 트랙·영상·인증 가이드는 열람 가능.

- 🎓 **[Palantir Learn](https://learn.palantir.com/)** — 공식 무료 학습 사이트. **Foundry Foundations**(입문)부터 트랙(Starting→Intermediate→Advanced), 배지·[인증 시험](https://learn.palantir.com/page/exam-guides).
- 🧩 **[Deep Dive: Creating Your First Ontology](https://learn.palantir.com/deep-dive-creating-your-first-ontology)** — 공식 온톨로지 튜토리얼(60~90분). *기존 온톨로지를 먼저 탐색*한 뒤 → 자기 object type·relationship·action을 정의. (우리 [ontology-builder 게임](../practice/game/ontology-builder.html)·[03](03-ontology.md)의 공식 대응) ⚠️ 로그인 필요.
- 🛠️ **[Build with AIP](https://build.palantir.com/)** — 예제·튜토리얼·스타터팩 라이브러리(에이전트 장기기억 등).
- 🎥 **[Video Tutorials](https://learn.palantir.com/page/video-tutorials)** · **[Course Catalog](https://learn.palantir.com/page/course-catalog)** · **[한국어 학습 트랙](https://learn.palantir.com/page/foundry-learning-paths-ko)**
- 🤖 **[AIP Agent Studio(현 AIP Chatbot Studio) — Getting Started](https://www.palantir.com/docs/foundry/agent-studio/getting-started)** — 에이전트에 도구·컨텍스트 부여, 배포·모니터링. (명칭 변경: Agent→Chatbot)

## 공식 1차 자료 (Palantir)

- 🎤 **[Palantir Docs — AI FDE Overview](https://www.palantir.com/docs/foundry/ai-fde/overview)**
- 🎤 **[Palantir Docs — Ontology Core Concepts](https://www.palantir.com/docs/foundry/ontology/core-concepts)** · **[Why create an Ontology?](https://www.palantir.com/docs/foundry/ontology/why-ontology)**
- 🎤 **[Palantir 10-K (FY2024), SEC](https://www.sec.gov/Archives/edgar/data/1321655/000132165525000022/pltr-20241231.htm)** — 회사 미션·플랫폼 정의의 1차 출처.

## 활용 메모

- **교차검증:** Perspective AI·YC 플레이북의 5단계로 `02`를 대조 — 골격 일치 확인됨.
- **심화 후보:** `palantir-ontology-strategy` 책으로 `03` 확장.
- **실습 보강:** `Awesome-FDE-Roadmap`의 Site Survey/SOW 템플릿 아이디어를 `practice/case-template.md`에 접목 가능.
