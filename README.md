<h1 align="center">흔들리지 않는 플레이를 만드는 게임 클라이언트 개발자</h1>

<p align="center">
플레이어가 느끼는 한 프레임을 시스템으로 설명합니다.<br />
Unity와 C#으로 전투·입력·상태 전이를 설계하고, 실제 프로젝트에서 확인 가능한 기술 근거를 남깁니다.
</p>

<p align="center">
  <a href="mailto:asss6868@naver.com"><img src="https://img.shields.io/badge/%EC%9D%B4%EB%A9%94%EC%9D%BC-315C40?style=flat-square&logo=naver&logoColor=white" alt="이메일" /></a>
  <a href="https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link"><img src="https://img.shields.io/badge/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4-4F6F54?style=flat-square&logo=notion&logoColor=white" alt="포트폴리오" /></a>
</p>

## 정회륜 · 게임 클라이언트 개발자

기능이 한 번 동작하는 것에서 끝내지 않고, **재진입·중단·반환 시점에도 같은 조건이 유지되는지**를 코드 경계와 검증 조건으로 설명합니다.

> 문제 정의 → 선택 근거 → 실행 흐름 → 검증

지금까지 **프로젝트 기술 사례 8건**, **독립 포트폴리오 저장소 5개**, **수상·활동 4건**을 정리했습니다.

## 기술 역량

### 실행 상태와 생명주기

- 코루틴·트윈·이벤트의 실행 수명 관리
- 재진입·중단·반환 시점의 상태 계약 설계

### 클라이언트 구조

- 팩토리와 오브젝트 풀을 이용한 객체 생성·재사용
- 명시적 초기화와 식별자 기반 UI 연결

### 게임플레이 상호작용

- 입력·물리·애니메이션 상태 연결
- 레이캐스트·레이어 마스크·안전 영역 처리

## 사용 기술

<p>
  <img src="https://img.shields.io/badge/Unity-1B4332?style=flat-square&logo=unity&logoColor=white" alt="Unity" />
  <img src="https://img.shields.io/badge/C%23-2D6A4F?style=flat-square&logo=csharp&logoColor=white" alt="C#" />
  <img src="https://img.shields.io/badge/C%2B%2B-40916C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++" />
  <img src="https://img.shields.io/badge/Unreal_Engine-315C40?style=flat-square&logo=unrealengine&logoColor=white" alt="Unreal Engine" />
  <img src="https://img.shields.io/badge/Git-52796F?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>

## 주요 프로젝트

### quoridorshooting `저장소 비공개`

벽 설치와 전투 행동으로 경로를 통제하는 턴제 전략 로그라이트 게임입니다. 전투·UI·개발 도구 구현을 맡았으며 팀 리드와 기획 조율까지 담당했습니다.

- **문제:** 객체 재사용 이후 이전 전투 상태가 남아 다음 실행에 영향을 주는 문제
- **해결:** 팩토리와 오브젝트 풀의 생성·초기화·반환 책임을 분리하고 검증 경로 구성
- **기술 근거:** 상태형 UI, 명시적 초기화, 자동 검증 과정

[포트폴리오에서 자세히 보기](https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link)

---

### [미기록 구역](https://github.com/superjoung/UnopenedArea-2026-06-19_23-16-59) `공개 저장소`

CCTV 채널을 감시하며 이상 현상을 판별하는 2D 공포 게임입니다. 날짜 진행과 입력·연출 상태의 실행 수명을 설계했습니다.

- **문제:** 날짜 전환 후 이전 코루틴과 입력 상태가 남아 연출이 중복 실행되는 문제
- **해결:** 상태 전이 시 실행 주체를 종료하고 입력 가능 구간을 명시적으로 분리
- **기술 근거:** 코루틴·이벤트 수명, 상태 전이, 입력 경계

[소스 코드 보기](https://github.com/superjoung/UnopenedArea-2026-06-19_23-16-59)

---

### [CenterFall](https://github.com/superjoung/CenterFall) `공개 저장소`

화면비가 실시간으로 바뀌는 2D 액션 퍼즐 게임입니다. 트윈 중단과 오브젝트 풀 반환이 겹치는 실행 경로를 수명 계약으로 정리했습니다.

- **문제:** 화면비 전환 중 객체 반환이 발생하면 트윈 완료 처리와 반환 로직이 중복 실행되는 문제
- **해결:** 트윈 중단과 반환 여부를 하나의 상태 경계에서 검사하도록 실행 순서 통합
- **기술 근거:** 안전 영역, `Kill(false)`, 중복 반환 방지 조건

[소스 코드 보기](https://github.com/superjoung/CenterFall)

---

### [Guess](https://github.com/superjoung/Portfolio-Guess) `기술 사례`

증거 수집과 NPC 심문을 연결한 3D 추리 어드벤처 게임입니다. LLM 영역을 제외한 Unity 클라이언트 전체 흐름을 담당했습니다.

- **문제:** 여러 UI가 중첩될 때 이전 화면의 입력과 닫기 순서가 충돌하는 문제
- **해결:** 후입선출 방식으로 UI 열기·닫기 순서를 통합하고 증거 식별자로 데이터 연결
- **기술 근거:** 후입선출 UI 구조, `EvidenceID`, NavMesh

[기술 사례 보기](https://github.com/superjoung/Portfolio-Guess) · [소스 코드 보기](https://github.com/superjoung/2025-1-LLMJoljakGame)

## 프로젝트별 포트폴리오

### [FluX](https://github.com/superjoung/Portfolio-FluX)

규칙이 전환되는 모바일 액션 미니게임입니다. 명시적 초기화, 레이캐스트, 스테이지 생명주기를 중심으로 정리했습니다.

### [Devil of Gun](https://github.com/superjoung/Portfolio-DevilOfGun)

비대칭 2인 로컬 협동 슈팅 게임입니다. C++ 입력 처리, 스윕 충돌 검사, 애니메이션 블루프린트 연결을 중심으로 정리했습니다.

### [Little Hacker](https://github.com/superjoung/Portfolio-LittleHacker)

플릭 경로 기반 모바일 연산 퍼즐 게임입니다. JSON 스테이지 데이터, 레이캐스트, 턴 되돌리기를 중심으로 정리했습니다.

### [Git 교육 게임](https://github.com/superjoung/Portfolio-GitEducation)

Git 명령을 상태 변화로 보여주는 교육 게임입니다. 명령 매핑, 브랜치·파일 상태, 퀘스트 UI를 중심으로 정리했습니다.

<details>
<summary><strong>수상 및 활동</strong></summary>

- **2025** — 에이트 스튜디오 인턴
- **2024** — ICON 해커톤 3등·우수상
- **2023** — HI-SW 콘텐츠 제작 경진대회 1등
- **2019** — 넷마블 게임 아카데미 4기 최우수상

</details>

---

<p align="center">
  <strong>연락처</strong><br />
  <a href="mailto:asss6868@naver.com">asss6868@naver.com</a> ·
  <a href="https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link">노션 포트폴리오</a>
</p>

<p align="center"><sub>팀 코드와 에셋은 원본 저장소에 유지하며, 기술 사례 저장소에는 담당 범위·코드 발췌·원본 링크만 정리했습니다.</sub></p>
