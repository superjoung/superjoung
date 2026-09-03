# 👋 정회륜

### 게임 클라이언트 개발자

<p>
  <a href="https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link"><img src="https://img.shields.io/badge/%EB%85%B8%EC%85%98_%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4-2D6A4F?style=flat-square&logo=notion&logoColor=white" alt="노션 포트폴리오" /></a>
  <a href="mailto:asss6868@naver.com"><img src="https://img.shields.io/badge/%EC%9D%B4%EB%A9%94%EC%9D%BC-52796F?style=flat-square&logo=naver&logoColor=white" alt="이메일" /></a>
</p>

---

Unity와 C#으로 전투·입력·UI의 실행 흐름을 구현합니다.<br />
기능 구현에서 멈추지 않고 **재진입·중단·반환 시점까지 설계하는 것**을 중요하게 생각합니다.

---

### 🧭 개발 기준

<details>
<summary><strong>핵심 역량과 문제 해결 기준 보기</strong></summary>

1. **실행 주체를 명확하게 구분합니다.**

   코루틴·이벤트·트윈이 겹쳐 중복 실행되지 않도록 시작과 종료 조건을 분리합니다.

2. **객체의 생명주기를 기능보다 먼저 확인합니다.**

   생성·초기화·반환 책임을 나누고, 재사용 객체에 이전 플레이 상태가 남지 않게 합니다.

3. **선택한 방식의 이유를 남깁니다.**

   패턴을 사용했다는 설명보다 다른 대안을 선택하지 않은 이유와 실행 결과를 함께 정리합니다.

</details>

### 💪 사용 기술

<p>
  <img src="https://img.shields.io/badge/Unity-1B4332?style=flat-square&logo=unity&logoColor=white" alt="Unity" />
  <img src="https://img.shields.io/badge/C%23-2D6A4F?style=flat-square&logo=csharp&logoColor=white" alt="C#" />
  <img src="https://img.shields.io/badge/C%2B%2B-40916C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++" />
  <img src="https://img.shields.io/badge/Unreal_Engine-315C40?style=flat-square&logo=unrealengine&logoColor=white" alt="Unreal Engine" />
  <img src="https://img.shields.io/badge/Git-52796F?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>

---

### 📌 대표 프로젝트

<details>
<summary><strong>quoridorshooting · 미기록 구역 · CenterFall · Guess 보기</strong></summary>

각 프로젝트는 **문제 → 선택 이유 → 해결 → 확인** 순으로 정리했습니다.

#### 01. quoridorshooting

*턴제 전략 로그라이트 · 팀 리드 / 전투·UI·개발 도구 구현*

벽 설치와 전투 행동으로 상대의 이동 경로를 통제하는 게임입니다.

- **문제** — 풀링된 전투 객체에 이전 피격·연출 상태가 남아 다음 전투에 영향을 줬습니다.
- **선택 이유** — 매번 파괴와 생성을 반복하기보다 재사용 계약을 명확히 하는 편이 GC와 상태 오염을 함께 줄입니다.
- **해결** — 팩토리는 생성을, 오브젝트 풀은 초기화와 반환을 담당하도록 책임을 분리했습니다.

[노션에서 기술 사례 보기 →](https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link)

#### 02. 미기록 구역

*2D 공포 감시 게임 · 날짜 진행과 입력·연출 상태 설계*

CCTV 채널을 감시하며 이상 현상을 판별하는 게임입니다.

- **문제** — 날짜 전환 코루틴과 입력이 겹치며 연출이 중복 실행됐습니다.
- **선택 이유** — 지연 시간을 조정하는 방식은 경쟁 조건을 숨길 뿐이어서 전환 주체와 입력 가능 구간을 분리했습니다.
- **해결** — 전환 실행을 하나의 흐름으로 모으고 연출 중에는 입력을 차단했습니다.

[GitHub에서 코드 보기 →](https://github.com/superjoung/UnopenedArea-2026-06-19_23-16-59)

#### 03. CenterFall

*2D 액션 퍼즐 · 트윈 중단과 오브젝트 반환 경로 정리*

화면비가 실시간으로 바뀌며 플레이 영역이 변하는 게임입니다.

- **문제** — 트윈 완료 처리와 오브젝트 풀 반환이 겹치며 반환 로직이 중복 실행됐습니다.
- **선택 이유** — 개별 불리언을 늘리면 객체 재사용 시 초기화가 누락될 수 있어, 실행 수명과 반환 경계를 하나로 묶었습니다.
- **해결** — `Kill(false)`로 완료 콜백 없이 트윈을 중단하고, 반환 여부를 검사하는 가드를 두었습니다.

[GitHub에서 코드 보기 →](https://github.com/superjoung/CenterFall)

#### 04. Guess

*3D 추리 어드벤처 · LLM을 제외한 Unity 클라이언트 구현*

증거를 수집하고 NPC를 심문하며 사건을 추리하는 게임입니다.

- **문제** — 중첩된 UI가 열린 순서와 다르게 닫히며 입력 소유권이 충돌했습니다.
- **선택 이유** — 화면별 예외 처리보다 실제로 열린 순서를 자료구조로 관리해야 닫기 규칙을 일관되게 유지할 수 있습니다.
- **해결** — 후입선출 UI 스택으로 화면을 닫고, `EvidenceID`로 증거 데이터와 표시 요소를 연결했습니다.

[기술 사례 보기 →](https://github.com/superjoung/Portfolio-Guess) · [원본 코드 보기 →](https://github.com/superjoung/2025-1-LLMJoljakGame)

</details>

---

### 🗂️ 다른 프로젝트

<details>
<summary><strong>FluX · Devil of Gun · Little Hacker · Git 교육 게임 보기</strong></summary>

#### FluX

규칙이 전환되는 모바일 액션 미니게임입니다. 이전 미니게임의 실행 상태가 남지 않도록 스테이지 초기화 경계를 정리했습니다.

**기술** 명시적 초기화, 레이캐스트, 스테이지 생명주기 · [저장소 보기](https://github.com/superjoung/Portfolio-FluX)

#### Devil of Gun

비대칭 2인 로컬 협동 슈팅 게임입니다. 플레이어의 좌우 이동·점프와 애니메이션 상태 연결을 구현했습니다.

**기술** C++ 입력, Sweep 충돌, 애니메이션 블루프린트 · [저장소 보기](https://github.com/superjoung/Portfolio-DevilOfGun)

#### Little Hacker

플릭 경로를 따라 숫자와 연산자를 조합하는 모바일 퍼즐 게임입니다. JSON 기반 스테이지와 턴 되돌리기 흐름을 구성했습니다.

**기술** JSON 스테이지 데이터, 레이캐스트, 턴 되돌리기 · [저장소 보기](https://github.com/superjoung/Portfolio-LittleHacker)

#### Git 교육 게임

Git 명령을 화면 안의 상태 변화로 보여주는 교육 게임입니다. 명령 입력을 브랜치·파일 상태와 퀘스트 UI에 연결했습니다.

**기술** 명령 매핑, 브랜치·파일 상태, 퀘스트 UI · [저장소 보기](https://github.com/superjoung/Portfolio-GitEducation)

</details>

> 팀 코드와 에셋은 원본 저장소에 유지했습니다. 독립 저장소에는 담당 범위·코드 일부·원본 링크만 정리했습니다.

---

### 🏆 경험과 수상

- **2025** 에이트 스튜디오 인턴
- **2024** ICON 해커톤 3등·우수상
- **2023** HI-SW 콘텐츠 제작 경진대회 1등
- **2019** 넷마블 게임 아카데미 4기 최우수상
