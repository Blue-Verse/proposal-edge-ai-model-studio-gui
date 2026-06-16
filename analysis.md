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
