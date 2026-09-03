<table align="center">
<tr>
<td width="64%" valign="top">
<sub>정회륜 · 게임 클라이언트 개발자</sub>
<h1>상태와 생명주기를 설계합니다.</h1>
<p>Unity와 C#으로 전투·입력·UI의 실행 흐름을 구현합니다.<br />동작을 만드는 데서 멈추지 않고, 재진입·중단·반환 시점까지 코드로 설명합니다.</p>
<p>
  <a href="mailto:asss6868@naver.com"><img src="https://img.shields.io/badge/%EC%9D%B4%EB%A9%94%EC%9D%BC-315C40?style=flat-square&logo=naver&logoColor=white" alt="이메일" /></a>
  <a href="https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link"><img src="https://img.shields.io/badge/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4-4F6F54?style=flat-square&logo=notion&logoColor=white" alt="포트폴리오" /></a>
</p>
</td>
<td width="36%" valign="top">
<strong>개발할 때 먼저 확인하는 것</strong><br /><br />
① 실행 주체는 하나인가?<br /><br />
② 중단·재진입·반환 경계는 명확한가?<br /><br />
③ 선택한 구조를 코드와 실행 결과로 검증할 수 있는가?
</td>
</tr>
</table>

## 핵심 역량

<table align="center">
<tr>
<td width="33.3%" valign="top">
<strong>실행 상태 제어</strong><br /><br />
단발·지속 효과의 실행 조건을 분리하고, 중복 호출과 잔존 실행을 상태 경계에서 차단합니다.<br /><br />
<sub>코루틴 · 이벤트 · 트윈 · 상태 전이</sub>
</td>
<td width="33.3%" valign="top">
<strong>객체 생명주기</strong><br /><br />
생성·초기화·반환 책임을 나누고, 재사용 객체가 이전 플레이 상태를 다음 실행에 가져오지 않게 합니다.<br /><br />
<sub>팩토리 · 오브젝트 풀 · 명시적 초기화</sub>
</td>
<td width="33.3%" valign="top">
<strong>입력과 게임플레이</strong><br /><br />
입력 판정부터 물리 처리와 애니메이션 전이까지 하나의 흐름으로 연결하고 예외 구간을 제어합니다.<br /><br />
<sub>레이캐스트 · 레이어 마스크 · 안전 영역</sub>
</td>
</tr>
</table>

### 사용 기술

<p>
  <img src="https://img.shields.io/badge/Unity-1B4332?style=flat-square&logo=unity&logoColor=white" alt="Unity" />
  <img src="https://img.shields.io/badge/C%23-2D6A4F?style=flat-square&logo=csharp&logoColor=white" alt="C#" />
  <img src="https://img.shields.io/badge/C%2B%2B-40916C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++" />
  <img src="https://img.shields.io/badge/Unreal_Engine-315C40?style=flat-square&logo=unrealengine&logoColor=white" alt="Unreal Engine" />
  <img src="https://img.shields.io/badge/Git-52796F?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>

## 대표 프로젝트

<sub>문제 현상보다 발생 구조에 집중했습니다. 각 사례는 문제 → 선택 이유 → 해결 → 확인 경로 순으로 정리했습니다.</sub>

<br /><br />

<table>
<tr>
<td width="50%" valign="top">
<sub>01 · 턴제 전략 로그라이트</sub><br />
<strong>quoridorshooting</strong> <code>팀 프로젝트</code>
<p>벽 설치와 전투 행동으로 경로를 통제하는 게임입니다. 팀 리드로서 전투·UI·개발 도구를 구현했습니다.</p>
<p><strong>문제</strong> · 풀링된 전투 객체에 이전 피격·연출 상태가 남았습니다.<br /><br />
<strong>선택 이유</strong> · 매번 파괴와 생성을 반복하기보다 재사용 계약을 명확히 하는 편이 GC와 상태 오염을 함께 줄입니다.<br /><br />
<strong>해결</strong> · 팩토리는 생성을, 풀은 초기화와 반환을 담당하도록 책임을 분리했습니다.</p>
<a href="https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link"><img src="https://img.shields.io/badge/%EA%B8%B0%EC%88%A0_%EC%82%AC%EB%A1%80_%EB%B3%B4%EA%B8%B0-2D6A4F?style=flat-square&logo=notion&logoColor=white" alt="기술 사례 보기" /></a>
</td>
<td width="50%" valign="top">
<sub>02 · 2D 공포 감시 게임</sub><br />
<strong><a href="https://github.com/superjoung/UnopenedArea-2026-06-19_23-16-59">미기록 구역</a></strong> <code>공개</code>
<p>CCTV 채널을 감시하며 이상 현상을 판별하는 게임입니다. 날짜 진행과 입력·연출 상태를 설계했습니다.</p>
<p><strong>문제</strong> · 날짜 전환 코루틴과 입력이 겹치며 연출이 중복 실행됐습니다.<br /><br />
<strong>선택 이유</strong> · 지연 시간을 조정하는 방식은 경쟁 조건을 숨길 뿐이어서, 전환 주체와 입력 구간을 분리했습니다.<br /><br />
<strong>해결</strong> · 전환 실행을 하나의 흐름으로 모으고, 연출 중에는 입력을 차단했습니다.</p>
<a href="https://github.com/superjoung/UnopenedArea-2026-06-19_23-16-59"><img src="https://img.shields.io/badge/%EC%BD%94%EB%93%9C%EB%A1%9C_%ED%99%95%EC%9D%B8-315C40?style=flat-square&logo=github&logoColor=white" alt="코드로 확인" /></a>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<sub>03 · 2D 액션 퍼즐</sub><br />
<strong><a href="https://github.com/superjoung/CenterFall">CenterFall</a></strong> <code>공개</code>
<p>화면비가 실시간으로 바뀌는 게임입니다. 트윈 중단과 오브젝트 풀 반환 경로를 정리했습니다.</p>
<p><strong>문제</strong> · 트윈 완료 처리와 풀 반환이 겹치며 반환 로직이 중복 실행됐습니다.<br /><br />
<strong>선택 이유</strong> · 개별 불리언을 늘리면 재사용 시 상태가 누락될 수 있어, 실행 수명과 반환 경계를 하나로 묶었습니다.<br /><br />
<strong>해결</strong> · <code>Kill(false)</code>로 완료 콜백 없이 트윈을 중단하고, 반환 여부를 검사하는 가드를 두었습니다.</p>
<a href="https://github.com/superjoung/CenterFall"><img src="https://img.shields.io/badge/%EC%BD%94%EB%93%9C%EB%A1%9C_%ED%99%95%EC%9D%B8-315C40?style=flat-square&logo=github&logoColor=white" alt="코드로 확인" /></a>
</td>
<td width="50%" valign="top">
<sub>04 · 3D 추리 어드벤처</sub><br />
<strong><a href="https://github.com/superjoung/Portfolio-Guess">Guess</a></strong> <code>기술 사례</code>
<p>증거 수집과 NPC 심문을 연결한 게임입니다. LLM 영역을 제외한 Unity 클라이언트 흐름을 담당했습니다.</p>
<p><strong>문제</strong> · 중첩된 UI가 열린 순서와 다르게 닫히며 입력 소유권이 충돌했습니다.<br /><br />
<strong>선택 이유</strong> · 화면별 예외 처리보다 실제 열린 순서를 자료구조로 관리하는 편이 닫기 규칙을 일관되게 만듭니다.<br /><br />
<strong>해결</strong> · 후입선출 UI 스택으로 화면을 닫고, <code>EvidenceID</code>로 증거 데이터와 표시 요소를 연결했습니다.</p>
<a href="https://github.com/superjoung/Portfolio-Guess"><img src="https://img.shields.io/badge/%EA%B8%B0%EC%88%A0_%EC%82%AC%EB%A1%80_%EB%B3%B4%EA%B8%B0-2D6A4F?style=flat-square&logo=readme&logoColor=white" alt="기술 사례 보기" /></a>
<a href="https://github.com/superjoung/2025-1-LLMJoljakGame"><img src="https://img.shields.io/badge/%EC%BD%94%EB%93%9C%EB%A1%9C_%ED%99%95%EC%9D%B8-315C40?style=flat-square&logo=github&logoColor=white" alt="코드로 확인" /></a>
</td>
</tr>
</table>

## 프로젝트 저장소

<table>
<tr>
<td width="50%" valign="top">
<strong>FluX</strong><br />
<p>규칙이 전환되는 모바일 액션 미니게임입니다. 이전 미니게임의 실행 상태가 남지 않도록 스테이지 초기화 경계를 정리했습니다.</p>
<sub>명시적 초기화 · 레이캐스트 · 스테이지 생명주기</sub><br /><br />
<a href="https://github.com/superjoung/Portfolio-FluX"><img src="https://img.shields.io/badge/%EC%A0%80%EC%9E%A5%EC%86%8C_%EB%B3%B4%EA%B8%B0-315C40?style=flat-square&logo=github&logoColor=white" alt="저장소 보기" /></a>
</td>
<td width="50%" valign="top">
<strong>Devil of Gun</strong><br />
<p>비대칭 2인 로컬 협동 슈팅 게임입니다. 플레이어의 좌우 이동·점프와 애니메이션 상태 연결을 구현했습니다.</p>
<sub>C++ 입력 · Sweep 충돌 · 애니메이션 블루프린트</sub><br /><br />
<a href="https://github.com/superjoung/Portfolio-DevilOfGun"><img src="https://img.shields.io/badge/%EC%A0%80%EC%9E%A5%EC%86%8C_%EB%B3%B4%EA%B8%B0-315C40?style=flat-square&logo=github&logoColor=white" alt="저장소 보기" /></a>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<strong>Little Hacker</strong><br />
<p>플릭 경로를 따라 숫자와 연산자를 조합하는 모바일 퍼즐 게임입니다. JSON 기반 스테이지와 턴 되돌리기 흐름을 구성했습니다.</p>
<sub>JSON 스테이지 데이터 · 레이캐스트 · 턴 되돌리기</sub><br /><br />
<a href="https://github.com/superjoung/Portfolio-LittleHacker"><img src="https://img.shields.io/badge/%EC%A0%80%EC%9E%A5%EC%86%8C_%EB%B3%B4%EA%B8%B0-315C40?style=flat-square&logo=github&logoColor=white" alt="저장소 보기" /></a>
</td>
<td width="50%" valign="top">
<strong>Git 교육 게임</strong><br />
<p>Git 명령을 화면 안의 상태 변화로 보여주는 교육 게임입니다. 명령 입력을 브랜치·파일 상태와 퀘스트 UI에 연결했습니다.</p>
<sub>명령 매핑 · 브랜치·파일 상태 · 퀘스트 UI</sub><br /><br />
<a href="https://github.com/superjoung/Portfolio-GitEducation"><img src="https://img.shields.io/badge/%EC%A0%80%EC%9E%A5%EC%86%8C_%EB%B3%B4%EA%B8%B0-315C40?style=flat-square&logo=github&logoColor=white" alt="저장소 보기" /></a>
</td>
</tr>
</table>

<sub>팀 코드와 에셋은 원본 저장소에 유지했습니다. 독립 저장소에는 담당 범위·코드 일부·원본 링크만 정리했습니다.</sub>

## 경험과 수상

<table align="center">
<tr>
<td width="50%" valign="top">
<strong>2025</strong><br />
에이트 스튜디오 인턴
</td>
<td width="50%" valign="top">
<strong>2024</strong><br />
ICON 해커톤 3등·우수상
</td>
</tr>
<tr>
<td width="50%" valign="top">
<strong>2023</strong><br />
HI-SW 콘텐츠 제작 경진대회 1등
</td>
<td width="50%" valign="top">
<strong>2019</strong><br />
넷마블 게임 아카데미<br />
4기 최우수상
</td>
</tr>
</table>

---

<p align="center">
  <strong>연락처</strong><br />
  <a href="mailto:asss6868@naver.com">asss6868@naver.com</a> ·
  <a href="https://www.notion.so/Joung-HowiRyun-31b59b9ce07280a0bf2bf1223dd0cddd?source=copy_link">노션 포트폴리오</a>
</p>
