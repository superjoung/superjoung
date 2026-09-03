<table align="center">
<tr>
<td width="68%" valign="top">
<sub>정회륜 · 게임 클라이언트 개발자</sub>
<h2>흔들리지 않는 플레이를 만듭니다.</h2>
<p>플레이어가 느끼는 한 프레임을 시스템으로 설명합니다.<br />Unity와 C#으로 전투·입력·상태 전이를 설계하고, 실제 프로젝트에서 확인 가능한 기술 근거를 남깁니다.</p>
<p><code>상태</code> <code>생명주기</code> <code>게임플레이 시스템</code></p>
<p>
  <a href="mailto:asss6868@naver.com"><img src="https://img.shields.io/badge/%EC%9D%B4%EB%A9%94%EC%9D%BC-315C40?style=flat-square&logo=naver&logoColor=white" alt="이메일" /></a>
  <a href="https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link"><img src="https://img.shields.io/badge/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4-4F6F54?style=flat-square&logo=notion&logoColor=white" alt="포트폴리오" /></a>
</p>
</td>
<td width="32%" valign="top" nowrap>
<strong>8건</strong><br />
<sub>프로젝트 기술 사례</sub><br /><br />
<strong>5개</strong><br />
<sub>독립 포트폴리오 저장소</sub><br /><br />
<strong>4건</strong><br />
<sub>수상 및 활동</sub>
</td>
</tr>
</table>

## 기술 초점

<table align="center">
<tr>
<td valign="top" nowrap>
<strong>실행 상태와 생명주기</strong><br /><br />
코루틴·트윈·이벤트 수명<br />
재진입·중단·반환 계약
</td>
<td valign="top" nowrap>
<strong>클라이언트 구조</strong><br /><br />
팩토리·오브젝트 풀<br />
명시적 초기화·식별자 기반 UI
</td>
<td valign="top" nowrap>
<strong>게임플레이 상호작용</strong><br /><br />
입력·물리·애니메이션<br />
레이캐스트·레이어 마스크·안전 영역
</td>
</tr>
</table>

## 사용 기술

<p>
  <img src="https://img.shields.io/badge/Unity-1B4332?style=flat-square&logo=unity&logoColor=white" alt="Unity" />
  <img src="https://img.shields.io/badge/C%23-2D6A4F?style=flat-square&logo=csharp&logoColor=white" alt="C#" />
  <img src="https://img.shields.io/badge/C%2B%2B-40916C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++" />
  <img src="https://img.shields.io/badge/Unreal_Engine-315C40?style=flat-square&logo=unrealengine&logoColor=white" alt="Unreal Engine" />
  <img src="https://img.shields.io/badge/Git-52796F?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>

## 대표 프로젝트 · 구현 근거 중심

<table>
<tr>
<td width="50%" valign="top">
<strong>quoridorshooting</strong> <code>비공개</code>
<p>벽 설치와 전투 행동으로 경로를 통제하는 턴제 전략 로그라이트 게임입니다. 전투·UI·개발 도구 구현과 팀 리드를 담당했습니다.</p>
<p><strong>문제</strong> · 재사용 객체에 이전 전투 상태가 남았습니다.<br />
<strong>해결</strong> · 생성·초기화·반환 책임을 분리했습니다.</p>
<p><strong>기술 근거</strong> · 팩토리 · 오브젝트 풀 · 상태형 UI</p>
<a href="https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link"><img src="https://img.shields.io/badge/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4_%EB%B3%B4%EA%B8%B0-2D6A4F?style=flat-square&logo=notion&logoColor=white" alt="포트폴리오 보기" /></a>
</td>
<td width="50%" valign="top">
<strong><a href="https://github.com/superjoung/UnopenedArea-2026-06-19_23-16-59">미기록 구역</a></strong> <code>공개</code>
<p>CCTV 채널을 감시하며 이상 현상을 판별하는 2D 공포 게임입니다. 날짜 진행과 입력·연출 상태를 설계했습니다.</p>
<p><strong>문제</strong> · 날짜 전환 후 연출이 중복 재생됐습니다.<br />
<strong>해결</strong> · 실행 주체와 입력 가능 구간을 분리했습니다.</p>
<p><strong>기술 근거</strong> · 코루틴·이벤트 수명 · 상태 전이</p>
<a href="https://github.com/superjoung/UnopenedArea-2026-06-19_23-16-59"><img src="https://img.shields.io/badge/%EC%86%8C%EC%8A%A4_%EC%BD%94%EB%93%9C_%EB%B3%B4%EA%B8%B0-315C40?style=flat-square&logo=github&logoColor=white" alt="소스 코드 보기" /></a>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<strong><a href="https://github.com/superjoung/CenterFall">CenterFall</a></strong> <code>공개</code>
<p>화면비가 실시간으로 바뀌는 2D 액션 퍼즐 게임입니다. 트윈 중단과 오브젝트 반환 경로를 정리했습니다.</p>
<p><strong>문제</strong> · 완료 처리와 반환 로직이 중복 실행됐습니다.<br />
<strong>해결</strong> · 중단과 반환을 하나의 상태 경계에서 검사했습니다.</p>
<p><strong>기술 근거</strong> · 안전 영역 · <code>Kill(false)</code> · 반환 방지</p>
<a href="https://github.com/superjoung/CenterFall"><img src="https://img.shields.io/badge/%EC%86%8C%EC%8A%A4_%EC%BD%94%EB%93%9C_%EB%B3%B4%EA%B8%B0-315C40?style=flat-square&logo=github&logoColor=white" alt="소스 코드 보기" /></a>
</td>
<td width="50%" valign="top">
<strong><a href="https://github.com/superjoung/Portfolio-Guess">Guess</a></strong> <code>기술 사례</code>
<p>증거 수집과 NPC 심문을 연결한 3D 추리 게임입니다. LLM을 제외한 Unity 클라이언트 흐름을 담당했습니다.</p>
<p><strong>문제</strong> · UI 입력과 닫기 순서가 충돌했습니다.<br />
<strong>해결</strong> · 후입선출 화면 구조와 증거 식별자를 적용했습니다.</p>
<p><strong>기술 근거</strong> · 후입선출 UI · <code>EvidenceID</code> · NavMesh</p>
<a href="https://github.com/superjoung/Portfolio-Guess"><img src="https://img.shields.io/badge/%EA%B8%B0%EC%88%A0_%EC%82%AC%EB%A1%80_%EB%B3%B4%EA%B8%B0-2D6A4F?style=flat-square&logo=readme&logoColor=white" alt="기술 사례 보기" /></a>
<a href="https://github.com/superjoung/2025-1-LLMJoljakGame"><img src="https://img.shields.io/badge/%EC%86%8C%EC%8A%A4_%EC%BD%94%EB%93%9C_%EB%B3%B4%EA%B8%B0-315C40?style=flat-square&logo=github&logoColor=white" alt="소스 코드 보기" /></a>
</td>
</tr>
</table>

## 포트폴리오 저장소

<table align="center">
<tr>
<td width="50%" valign="top">
<strong><a href="https://github.com/superjoung/Portfolio-FluX">FluX</a></strong>
<p>규칙이 전환되는 모바일 액션 미니게임입니다. 규칙 전환 때 이전 상태가 남지 않도록 초기화 경계를 정리했습니다.</p>
<sub>명시적 초기화 · 레이캐스트 · 스테이지 생명주기</sub>
</td>
<td width="50%" valign="top">
<strong><a href="https://github.com/superjoung/Portfolio-DevilOfGun">Devil of Gun</a></strong>
<p>비대칭 2인 로컬 협동 슈팅 게임입니다. 플레이어 이동과 애니메이션 상태 연결을 구현했습니다.</p>
<sub>C++ 입력 · 스윕 충돌 · 애니메이션 블루프린트</sub>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<strong><a href="https://github.com/superjoung/Portfolio-LittleHacker">Little Hacker</a></strong>
<p>플릭 경로 기반 모바일 연산 퍼즐 게임입니다. JSON 기반 스테이지와 턴 되돌리기 흐름을 구성했습니다.</p>
<sub>JSON 스테이지 데이터 · 레이캐스트 · 턴 되돌리기</sub>
</td>
<td width="50%" valign="top">
<strong><a href="https://github.com/superjoung/Portfolio-GitEducation">Git 교육 게임</a></strong>
<p>Git 명령을 상태 변화로 보여주는 교육 게임입니다. 명령 입력을 브랜치·파일 상태 변화와 연결했습니다.</p>
<sub>명령 매핑 · 브랜치·파일 상태 · 퀘스트 UI</sub>
</td>
</tr>
</table>

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
