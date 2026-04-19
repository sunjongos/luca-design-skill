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

### 2단계: 렌더링 스웜(Swarm) 가동 및 Stitch MCP 최적화
- 테마가 픽스되면, 프롬프트 최상단에 테마의 주요 색상(Primary Color)과 둥근 모서리 속성 등 메타데이터를 강제 주입(**Token Injection**)합니다.
- **[핵심: Stitch MCP 연산 병목 제거]** `Stitch MCP`를 사용하여 화면을 생성(`generate_screen_from_text`)할 때, 구글 서버 연산 부하로 인한 3분 타임아웃(Time-out) 에러를 반드시 억제(Bypass)해야 합니다.
  - 무거운 기본 모델 대신 **초경량 하이엔드 모델 (`modelId: GEMINI_3_FLASH`)** 을 명시적으로 파라미터에 강제 할당하십시오.
  - 프롬프트에서 불필요한 장황한 묘사(예: 프리미엄 레이아웃, 복잡한 네온 등)를 제거하고 직관적인 UI 뼈대 구조로만 단순화(Down-sizing)하여 렌더링 체증을 뚫어냅니다.
  - 시스템 `gcloud` 자격증명과 충돌하지 않도록 `mcp_config.json` 내 `GOOGLE_APPLICATION_CREDENTIALS: ""` 환경변수 덮어쓰기 블록을 반드시 유지해야 합니다.
- 만약 이 최적화 모드로도 외부 API 서버 오류가 감지된다면, 지체 없이 로컬에서 `Vite + React + Tailwind` 환경으로 하드 스캐폴딩(Hard Scaffolding)하는 Fail-Safe 로직으로 전환합니다.

### 3단계: 보고 및 터미널 검증
- 모든 디자인 화면(페이지) 제작이 끝나면, 즉시 브라우저나 VSCode에서 확인할 수 있도록 `walkthrough.md`에 최종 결과물 위치와 스크린샷 렌더링 명령어를 보고합니다.
