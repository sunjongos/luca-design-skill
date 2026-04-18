# LUCA AI Design System Generator (/luca-design)

## 🌟 개요 (Overview)
`luca-design` 스킬은 서버 응답 오류가 잦은 Claude Stitch (Design System) 웹 기능을 완벽히 대체(Bypass)하기 위한 Antigravity 전용 워크플로우이자 고성능 UI 제너레이터입니다. AI가 화면을 생성할 때 발생하는 디자인 붕괴와 할루시네이션(Hallucination)을 원천 차단하고, 사내 3대 GitHub 베이스 템플릿(NDB, LCK Lab, Doctor Eye)을 강제로 주입하여 엔터프라이즈(Enterprise) 급 프론트엔드/웹/앱 코드를 즉각적으로 추출합니다.

## 🚀 파이프라인 특징 (Core Capabilities)

### 1. Context 기반 자동 템플릿 타겟팅 (Template Targeting)
명확한 템플릿이 지정되지 않을 시, AI가 맥락을 분석하여 최적의 디자인 시스템을 선제 제안합니다.
* **NDB (Namyangju Baek)**: 대형 병원, 높은 신뢰도, 의료 전문성 기반의 틸(Teal) 테마
* **LCK Lab**: 연구소, 사이버, 데이터 모니터링, 첨단 대시보드 지향형 블루/블랙 테마
* **Doctor Eye**: 헬스케어 플랫폼, B2C 모바일, 부드러움 지향형 테마

### 2. 하이엔드 렌더링 스웜 (High-end Rendering Swarm)
지정된 테마가 확보되면 즉각적으로 스웜(Swarm) 모델 기반 메타데이터 토큰 주입(Token Injection)을 실행합니다. 
* Stitch MCP, gemini-multi-agent teams 등을 관현악단처럼 오케스트레이션하여 코드를 생산합니다.
* 단 하나의 오류(400 에러 등) 발생 시 즉시 **하드 스캐폴딩(Vite + React + Tailwind)** 로직으로 Fail-Safe 전환을 수행하여 결점 없는 결과물을 보장합니다.

### 3. 무결점 보안 (Security First)
* Stitch MCP API Key (`STITCH_API_KEY`)를 포함한 모든 환경 변수 `.env` 및 `.claude.json`는 본 Repository에 공유되지 않습니다.
* 완벽한 보안 환경 하에서 디자인 시스템의 SSOT(Single Source of Truth)로만 기능합니다.

## ⚙️ 사용 형태 (Usage)
Claude Code 셸(Shell)이나 외부 터미널에서 다음 명령어를 통해 즉시 발동됩니다.

```bash
/luca-design
# 또는
"디자인/템플릿 적용해서 웹(앱/슬라이드) 만들어줘"
```

## 👩‍💻 기여 및 메인테이너 지침
본 레포지토리는 최고위 연구자동화 에이전트 환경(Antigravity) 내에서 자율 구동되는 목적으로 작성되었습니다. 스킬 추가 로직이나 디자인 가이드 수정 시, `luca_design.md` 커밋 룰을 준수하십시오.
