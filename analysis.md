# Edge AI 플랫폼(SV Model Studio) Web GUI 및 백엔드 개발 — 제안 분석 로그

> 생성일: 2026-06-16
> 공고 URL: https://www.wishket.com/project/155876/

## 1. 공고 파싱 결과

```yaml
job:
  title: "Edge AI 플랫폼(SV Model Studio) Web GUI 및 백엔드 개발"
  category: "웹 / 기타(AI·머신러닝)"
  budget_range: "20,000,000원 (평균 지원가 18,600,000 / 최저 14,000,000 / 최고 20,000,000)"
  duration: "90일 (납품 희망 착수 후 3~4개월 내)"
  tech_stack:
    - Python
    - FastAPI
    - Uvicorn
    - WebSocket
    - "SPA (Vanilla JS / React / Vue)"
    - Bootstrap 5
    - Docker
    - REST API
  description: >
    내부 구축된 AI 엔진(YOLO·SNPE·CDFSOD) Docker 컨테이너를 REST·WebSocket으로 제어하여,
    웹 화면에서 모델 학습·양자화·평가를 수행하는 통합 대시보드(SV Model Studio) 구축.
    AI 모델 자체 개발이 아닌 '웹 대시보드 + API Gateway' 개발 건.
  requirements:
    - "FastAPI 기반 API Gateway — sv-network Docker 컨테이너 제어"
    - "YAML 데이터셋 통계 분석·차트 시각화, 서버 파일 브라우저 UI"
    - "YOLO(Standard·KD)·Few-Shot(CDFSOD) 파라미터 UI"
    - "Job Queue 관리 + WebSocket 실시간 학습 로그 터미널"
    - "단건/배치 추론 실행 및 결과 이미지 렌더링"
    - "ONNX/DLC 변환·INT8 양자화 파라미터 UI"
    - "Qualcomm NPU 보드 SSH/SCP 원격 연결·mAP 평가 연동"
    - "데이터 정제(품질·유사도) 파라미터·실행 연동, CVAT 라벨링 연동"
  client_questions: []
  deadline: "2026-06-18"
  job_post_url: "https://www.wishket.com/project/155876/"
  urls: []
  images: []
  priorities: ["1순위 산출물 완성도", "2순위 금액", "3순위 일정 준수"]
  client_resources: "기술명세서(PDF, UI 캡처본 포함), AI 컨테이너 API 가이드, 연구원 1명(API 연동·테스트 지원)"
  collaboration: "자사 PM 1명, AI 개발자 1명"
```

## 2. URL/이미지 분석

- 공고 본문에 참고 URL 없음.
- 첨부 이미지 없음 (기술명세서 PDF는 계약 후 제공 예정으로, 본문에 직접 링크/이미지 없음).
- 판정: **참고 URL/이미지 없음** → 텍스트 기반 분석으로 진행.

## 3. 실현 가능성 분석 (내부용)

- **프로젝트 유형**: API + 웹 프론트 (FastAPI Gateway + SPA 대시보드) → **강력 추천 영역** (FE 중심 대시보드 + API Gateway)
- **기본 공수 (AI 보조 전)**: 약 105 M/D
  - 기획/설계 8, Figma/화면 10, FE 40, BE 35, QA/배포 12
- **AI 반영 공수**: 약 49 M/D (가중 절감 약 50%)
- **복잡도 버퍼(+15%, WebSocket 실시간·SSH 원격 연동)** 적용: 약 56 M/D
- **1인 기준 달력 환산**: 약 56 × (7/5) ≈ 79일
- **클라이언트 예상 기간 vs 산정 기간**: 90일 vs 약 79일 → **여유 있게 가능**
- **판정**: 1인 기준으로도 90일 내 가능. 다수 인력 투입 시 단계 병행으로 산출물 완성도(1순위) 확보 여유. 기간은 90일 유지.

## 4. 포트폴리오 매칭

매칭 기준: AI 엔진 제어 + 실시간 WebSocket 대시보드 + 대규모 API 백엔드 + Docker 인프라.

| 프로젝트 | 매칭 근거 | 점수 |
|---------|----------|------|
| **AI Agent (AI 엔진 오케스트레이션 프레임워크)** | 본 과업과 동일 구조: 기존 AI 엔진을 API·WebSocket으로 제어하는 컨트롤 플레인 + 실시간 대시보드. 48 API 엔드포인트, WebSocket 모니터링, Docker, MCP 연동 | ★★★★★ |
| **EZ-Approve (전자결재 SaaS)** | 대규모 REST API(120~150) + 실시간(Yjs/WebSocket) + Docker Compose 인프라 + 관리자 대시보드 = API Gateway·대시보드 과업 직접 일치 | ★★★★☆ |
| **Series-B (투자조합 관리 플랫폼)** | 외부 AI(ChatGPT) 연동 + 200~300+ API 대규모 백엔드 + 실시간 협업 + 데이터 대시보드 = AI 연동형 게이트웨이 백엔드 검증 역량 | ★★★★☆ |

추가 후보(미채택): P2P Funding(Python/Django 백엔드·외부 API 연동) — Python 백엔드 신뢰도 보강용으로 폼 텍스트에 부분 언급 가능.

## 5. 최종 제안 요약

- **지원 금액**: 17,000,000원 (VAT 별도) — 클라이언트 예상 20,000,000원의 85%. 우선순위 2위 '금액' 경쟁력 + 평균 지원가(18.6M) 대비 우위 확보.
- **지원 기간**: 90일 — 클라이언트 예상 유지. 다수 인력 투입으로 단계 병행, 산출물 완성도(1순위) 확보.
- **핵심 제안 포인트**:
  1. 과업 범위 정확 이해 (AI 모델 개발이 아닌 제어 대시보드 + API Gateway)
  2. FastAPI 비동기 아키텍처 + WebSocket 실시간 로그 스트리밍
  3. 기존 sv-network Docker 네트워크 무중단 연동
  4. 비전문가 친화 Bootstrap 5 대시보드 UX
  5. AI 엔진 오케스트레이션·실시간 대시보드·대규모 API Gateway 유사 수행 경험
- **총 산정 공수**: 60 M/D (기획 8 / UI 9 / FE 18 / BE 17 / QA 8)

## 6. 최종 산출물 (8단계 출력 전문)

### 6-1. 제안서 사이트 URL
https://proposal-router.claude-ai-b27.workers.dev/proposal-edge-ai-model-studio-gui/

### 6-2. 지원 금액
17,000,000원 (VAT 별도)

### 6-3. 지원 기간
90일

### 6-4. 클라이언트 질문 답변
해당 없음 (공고에 별도 질문 없음 — 우선순위만 제시: ①산출물 완성도 ②금액 ③일정 준수)

### 6-5. 지원 내용 (전체 텍스트)

안녕하세요, Edge AI 플랫폼(SV Model Studio) Web GUI 및 백엔드 개발 프로젝트에 지원합니다.

본 프로젝트에 대한 상세 제안서(견적서, 공수계산서, PRD, 일정, 포트폴리오)를 별도 페이지로 준비하였습니다. 아래 링크에서 확인해 주시면 감사하겠습니다.
▶ 제안서 상세 페이지: https://proposal-router.claude-ai-b27.workers.dev/proposal-edge-ai-model-studio-gui/
▶ 위시켓 포트폴리오: https://www.wishket.com/partners/p/blueverse1/

---

<프로젝트 진행 제안>

■ 프로젝트 분석
본 과업은 AI 모델 자체 개발이 아닌, 이미 준비된 AI 엔진(YOLO·SNPE·CDFSOD Docker 컨테이너)을 제어하는 '웹 대시보드 + FastAPI API Gateway' 구축임을 명확히 이해하고 있습니다. 파편화된 CLI 기반 학습·변환·평가 작업을 하나의 직관적인 Web GUI로 통합하여, 비전문 작업자도 데이터셋 구성부터 Few-Shot 학습, NPU 보드 평가까지 한 화면에서 수행하도록 구축합니다. 백엔드는 요구사항대로 FastAPI(Uvicorn) 기반으로 구축하며, 기존 sv-network Docker 네트워크 내 컨테이너와 REST·WebSocket으로 원활히 통신하도록 설계합니다.

■ 작업 일정

[Phase 1] Day 1–18
- 기획·설계·화면설계: 기술명세서(PDF)·AI 컨테이너 API 가이드 분석, 화면 설계, API Gateway 엔드포인트·WebSocket 이벤트 설계, Bootstrap 5 화면 퍼블리싱 착수

[Phase 2] Day 12–45
- API Gateway·코어 개발: FastAPI API Gateway 구축, sv-network 컨테이너 연동, Job Queue, WebSocket 실시간 학습 로그 스트리밍, 데이터셋 통계·파일 브라우저

[Phase 3] Day 40–72
- 기능 개발: YOLO·CDFSOD 학습·추론 제어, ONNX/DLC 변환·INT8 양자화, NPU 보드 SSH/SCP·mAP 평가 연동, 데이터 정제·CVAT 연동

[Phase 4] Day 70–90
- 통합 테스트·배포: 통합 QA, Dockerfile, 배포 가이드·API 명세서·시스템 구성도 작성, 소스 코드 전체 이관

■ 마일스톤 및 산출물
- M1(Day 18): 설계 확정 — 화면설계서·API 명세 승인
- M2(Day 45): API Gateway 연동 완료 — 컨테이너 제어·실시간 로그 동작 시연
- M3(Day 72): 핵심 기능 완성 — 학습·변환·평가·파이프라인 화면 통합 시연
- M4(Day 90): 최종 납품 — 통합 테스트 통과, 소스·문서·배포 가이드 이관
- 최종 산출물: Frontend·Backend 소스 원본, API 명세서·시스템 구성도, Dockerfile·배포 가이드

■ 미팅 시 협의 필요 사항
- 기술명세서(PDF) UI 캡처본 기준 화면 범위 및 우선순위 확정
- AI 컨테이너 API 가이드(REST/WebSocket 규약) 상세 및 인증 방식
- 프론트엔드 프레임워크 선택(Vanilla JS / React / Vue) 협의
- NPU 보드 SSH/SCP 접속 환경 및 평가(mAP) 실행 절차
- CVAT·데이터 정제 모듈의 연동 인터페이스 범위

---

<유사 프로젝트 진행 경험>

▶ AI 엔진 통합 오케스트레이션 프레임워크 (2026.01~2026.03)
- 프로젝트 유형: AI 개발 자동화 / DevOps 플랫폼
- 핵심 기능: 4종 AI 엔진 통합 디스패치·오케스트레이션, WebSocket 실시간 모니터링 대시보드, 48 API 엔드포인트, 12 품질 게이트
- 유사점: 본 과업과 동일하게 '기존 AI 엔진을 API·WebSocket으로 제어하는 컨트롤 플레인 + 실시간 대시보드' 구조. AI 엔진 오케스트레이션·실시간 로그 스트리밍 경험이 학습 로그 터미널·Job 제어에 직접 적용
- 기술 스택: TypeScript, Hono, React 19, WebSocket, Docker

▶ 전자결재·업무관리 올인원 플랫폼 (2026.01~2026.03)
- 프로젝트 유형: B2B SaaS / 관리자 대시보드
- 핵심 기능: 120~150 REST API 엔드포인트, 결재 워크플로우 엔진, Yjs 실시간 협업(WebSocket), Docker Compose 인프라
- 유사점: 대규모 REST API + 실시간(WebSocket) + Docker 인프라 + 관리자 대시보드 구조가 본 API Gateway·대시보드 과업과 직접 일치
- 기술 스택: NestJS, Next.js, TypeScript, MySQL, Yjs, Docker, Nginx

▶ 투자조합 관리·업무 자동화 플랫폼 (2023.11~2024.12)
- 프로젝트 유형: 핀테크 SaaS / 대규모 API 백엔드
- 핵심 기능: 200~300+ API 엔드포인트, 외부 AI(ChatGPT) 연동 보고서 자동 생성, CRDT 실시간 공동편집, 50+ 페이지 대시보드
- 유사점: 외부 AI 연동 + 대규모 API 백엔드 + 실시간 처리 + 데이터 대시보드 경험으로 AI 연동형 API Gateway 구축에 검증된 백엔드 설계 역량 제공
- 기술 스택: Next.js, NestJS, MySQL, AWS, Document AI

---

<사용 기술과 툴>

▶ 개발 기술
- Backend: Python, FastAPI, Uvicorn, WebSocket
- Frontend: SPA (Vue.js / React / Vanilla JS), Bootstrap 5, Chart.js
- 연동: REST API, WebSocket, SSH/SCP(NPU 보드), ONNX/DLC, Docker(sv-network)

▶ 개발 도구 및 인프라
- 버전 관리: GitHub
- CI/CD: GitHub Actions
- 컨테이너: Docker
- 배포: Dockerfile + 배포 가이드 제공

▶ 커뮤니케이션
- 일일 진행 공유: Slack 또는 카카오톡
- 주간 미팅: Zoom / Google Meet
- 문서 공유: Notion 또는 Google Docs
- 이슈 트래킹: GitHub Issues

### 6-6. 관련 포트폴리오 추천
1. AI 엔진 통합 오케스트레이션 프레임워크 — 기존 AI 엔진 API·WebSocket 제어 컨트롤 플레인 + 실시간 대시보드 (최우선 매칭)
2. 전자결재·업무관리 올인원 플랫폼 — 대규모 REST API + 실시간 + Docker 인프라 + 관리자 대시보드
3. 투자조합 관리·업무 자동화 플랫폼 — 외부 AI 연동 + 대규모 API 백엔드 + 실시간 데이터 대시보드
