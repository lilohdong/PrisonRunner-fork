<p align="center">
  <img src="PrisonRunner/Unity/Assets/Game/Content/ArtV2/Textures/MuhanokLogo.png" alt="Mongscape" width="480">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Unity-6000.3.10f1-000000?style=for-the-badge&logo=unity&logoColor=white" alt="Unity 6000.3.10f1">
  <img src="https://img.shields.io/badge/C%23-URP-512BD4?style=for-the-badge&logo=csharp&logoColor=white" alt="C# URP">
  <img src="https://img.shields.io/badge/Windows-only-0078D4?style=for-the-badge&logo=windows&logoColor=white" alt="Windows">
  <br>
  <img src="https://img.shields.io/badge/Unity_AI_Inference-BlazePose-FF6F00?style=for-the-badge" alt="Unity AI Inference BlazePose">
  <img src="https://img.shields.io/badge/Python-OpenCV-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python OpenCV">
  <img src="https://img.shields.io/badge/PostgreSQL-17-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL 17">
</p>

# Mongscape · 몽스케이프 (무한옥)

Unity 6000.3.10f1 기반 Windows 운동 러너입니다. 광산·수레 갈림길·감옥·동물원을 키보드 또는 웹캠 몸동작으로 플레이합니다.

> [!NOTE]
> 2026-10-29: PR #20과 기존 개선을 통합한 소스입니다. develop 병합만 진행하며 새 릴리스·태그·서버 배포는 하지 않습니다. 기존 공개 ZIP은 통합 이전 버전입니다.

## 실행

`StartGame.cmd`를 실행합니다. 타이틀 → 로그인 선택 → 얼굴 로그인·회원가입 또는 게스트 → 메인 메뉴 → 게임 시작/튜토리얼 순서입니다.

계정 서버 없이 게스트·키보드 플레이를 사용할 수 있습니다. 몸동작은 각 PC의 Unity에서 처리합니다.

## 조작

| 동작 | 키보드 | 전신 (어깨~발) | 상체 (허리 위) |
| --- | --- | --- | --- |
| 좌우 이동 | <kbd>A</kbd> / <kbd>D</kbd> | 몸을 옆 구역으로 이동 | 상체를 옆 구역으로 이동 |
| 갈림길 가운데 | <kbd>C</kbd> | 사이드스텝 | 사이드스텝 |
| 점프 | <kbd>Space</kbd> | 실제 점프 | 두 손을 머리 위로 |
| 숙이기 | <kbd>S</kbd> | 상체 낮추기 | 상체 숙이기 |
| 하이니 | <kbd>W</kbd> | 한쪽 무릎 높이 들기 | 팔 번갈아 크게 흔들기 |

<kbd>F1</kbd> 설정, <kbd>F3</kbd> 성능 표시. 메뉴는 손목 커서를 0.75초 머물러 선택합니다.

## 현재 소스

- 회원 계정의 코인·상점 해금·운동 기록과 여러 PC의 통합 랭킹. 게스트 기록은 이 PC에 저장하고 코인·아이템은 적립/등장하지 않습니다.
- 점수 = 거리 + 65kg 기준 운동 칼로리×100. 표시 칼로리는 입력 몸무게 기준이며 생략하면 65kg, 키보드는 0입니다.
- 단계형 튜토리얼, 점프 준비·숙이기 오인식 수정, 보정 유지와 우측 하단 웹캠 표시 설정.
- 씨드에 따른 장애물·레일 랜덤 배치, 실제 코인 자석, 코인 2배와 바나나까지 막는 방패.
- 기존 로컬 수정 유지: 목표/소모 칼로리 HUD, 경찰 사이렌, 갈림길 표지, 연결된 기린 목·코끼리 코·쓰러지는 나무, 0.75초 손 메뉴와 자동 화질 조절.

## 얼굴 서버

Caddy HTTPS → Python/OpenCV/Psycopg API → PostgreSQL 17 구성입니다. 얼굴 사진을 저장하지 않고 인식 특징값을 보관합니다. 기존 DB의 스키마 이전과 사진 삭제는 자동 실행하지 않습니다.

## 개발

Unity 6000.3.10f1로 `PrisonRunner/Unity`를 열고 **Mongscape → Play GameScene**을 사용합니다. C#/URP와 Unity AI Inference/BlazePose를 사용하며 패키지는 업그레이드하지 않았습니다.

## 문서

| 목적 | 문서 |
| --- | --- |
| 실행과 서버 주소 | [처음 읽기](PrisonRunner/START_HERE.md) |
| 통합 범위·검사·남은 일 | [진행 상태](PrisonRunner/docs/PROGRESS.md) |
| PR 원래 기능 계획 | [기능 계획](PrisonRunner/docs/FEATURE_PLAN_2026_10_28.md) |
| 계정·몸동작·저장 구조 | [아키텍처](PrisonRunner/docs/ARCHITECTURE.md) |
| 전체 안내 | [문서 목록](PrisonRunner/docs/README.md) |
| 외부 리소스 조건 | [출처](PrisonRunner/THIRD_PARTY_NOTICES.md) |

<details>
<summary><b>백업·캡처·개인 데이터 안내</b></summary>
<br>

- 이전 문서와 캡처는 로컬 통합 백업으로 옮겼습니다.
- 새 검수 캡처는 Git에서 제외한 `Builds/QA`에 보관합니다.
- 개인 DB·얼굴·토큰·설치별 서버 설정은 백업 정리나 공개 파일 대상으로 취급하지 않습니다.

</details>
