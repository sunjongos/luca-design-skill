---
description: Claude Design 기능을 대체하여 NDB/LCK/DoctorEye 기반 UI를 즉각 렌더링하는 통합 디자인 템플릿 스킬 발동
---
# /luca-design (Luca AI Design System Generator)

**트리거 조건:** 사용자가 `/luca-design`을 입력하거나 "디자인/템플릿 적용해서 웹(앱/슬라이드) 만들어줘" 라고 요청할 때 즉각 발동.

## 🌟 워크플로우 개요
서버 응답 오류가 잦은 Claude Stitch (Design System) 웹 기능을 완벽히 대체(Bypass)하기 위한 Antigravity 전용 워크플로우입니다. 사내 3대 GitHub 템플릿 베이스(NDB, LCK Lab, Doctor Eye)를 강제로 주입하여, 생성형 AI의 디자인 붕괴를 원천 차단하고 우수한 퀄리티의 코드를 빠르게 뽑아냅니다.

## 🚀 파이프라인 행동 절차 (에이전트 강령)
에이전트는 이 명령을 받으면, `.agent/skills/luca-design/SKILL.md` 문서를 로드한 뒤 다음 단계를 신속하게 진행합니다.

### 1단계: Context 기반 템플릿 컨펌
- 사용자가 구체적으로 어느 테마를 쓸지 명시하지 않았다면 가장 알맞은 테마를 **선제적으로 제안하고 승인(HITL)을 받습니다**.
    - 의료/신뢰감 → **NDB**
    - 사이버/연구/첨단 → **LCK Lab** 
    - 헬스케어/부드러움 → **Doctor Eye**

### 2단계: 렌더링 스웜(Swarm) 가동
- 테마가 픽스되면, 프롬프트 최상단에 테마의 주요 색상(Primary Color)과 둥근 모서리 속성 등 디자인 시스템 메타데이터를 강제 주입(**Token Injection**)합니다.
- `Stitch MCP`나 `gemini-multi-agent teams` 체계를 백그라운드에서 활용해 UI 컴포넌트들을 찍어냅니다. 만일 외부 툴의 400 에러 감지 시, 지체 없이 로컬에서 `Vite + React + Tailwind` 환경으로 하드 스캐폴딩(Hard Scaffolding)하는 Fail-Safe 로직으로 전환합니다.

### 3단계: 보고 및 터미널 검증
- 모든 디자인 화면(페이지) 제작이 끝나면, 즉시 브라우저나 VSCode에서 확인할 수 있도록 `walkthrough.md`에 최종 결과물 위치와 스크린샷 렌더링 명령어를 보고합니다.
