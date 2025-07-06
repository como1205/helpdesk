### 프로젝트 개요

### 1. 배경 및 목적

* **배경**: 사내 IT 문의는 방화벽, 서버, 라이선스, 개발 시스템 등 다양한 영역에서 반복적으로 발생하며, 전산부서의 핵심 업무 집중을 방해합니다.
* **목적**: AI 기반 웹 헬프데스크 시스템을 도입하여 직원들의 반복 문의를 자율 해결하고, 전산부서의 유지보수 및 신규 기술 도입 업무 효율을 극대화합니다.

### 2. 주요 목표

1. **셀프 서비스**: 직원들이 브라우저에서 질문을 입력하면 AI가 FAQ와 매뉴얼을 검색하여 즉시 답변
2. **지식 베이스 관리**: FAQ, 매뉴얼, 문제 해결 로그를 중앙 DB에 저장·버전 관리
3. **자동 알림**: 전산부서에 긴급 이슈 발생 시 자동 알림 및 티켓 발행
4. **확장성**: 벡터 DB 기반 유사도 검색, API 확장으로 RPA·모바일 연동 지원

### 3. 핵심 기능

* **사용자 인증**: Azure AD/On-prem AD SSO 연동
* **FAQ 조회·관리**: CRUD API + UI 제공
* **AI 질문 답변**: OpenAI API 또는 자체 LLM 연동
* **매뉴얼 에디터**: WYSIWYG 기반 콘텐츠 관리
* **알림 시스템**: 이메일/Slack 연동 티켓 알림

### 4. 기술 스택

| 영역      | 기술 스택                                                  |
| ------- | ------------------------------------------------------ |
| 프론트엔드   | React 18 + Vite, Tailwind CSS, shadcn/ui               |
| 백엔드 API | ASP.NET Core Web API (C#), Entity Framework Core       |
| 데이터베이스  | SQL Server (주요 데이터), Elasticsearch/Vector DB (유사도 검색)  |
| AI 통합   | OpenAI API (ChatGPT), Python 마이크로서비스 (추가 LLM)          |
| 인증·보안   | Azure AD/On-prem AD, JWT                               |
| 배포·인프라  | Docker Compose (개발), Kubernetes/Azure App Service (운영) |
| CI/CD   | GitHub Actions                                         |

### 5. 개발 및 운영 프로세스

1. **브랜치 전략**: Git Flow (`main`/`develop`/`feature/*`)
2. **백로그 관리**: GitHub Projects 칸반 보드
3. **CI/CD**: Push → 빌드 → 테스트 → 이미지 빌드/배포
4. **테스트**: xUnit, Jest, Cypress
5. **모니터링**: Prometheus + Grafana 또는 Azure Monitor

### 6. 일정 및 단계

* **MVP(1차 릴리스)**: 인증 → FAQ CRUD → AI 질문 PoC (4주)
* **2차 릴리스**: 매뉴얼 관리 UI, 검색 고도화 (6주)
* **정식 론칭**: 보안 점검, 성능 튜닝, 운영 문서화 (2주)
* **운영·유지보수**: 월간 콘텐츠 점검, 로그 기반 개선 반복

> **개발자**: 1인 진행 (전산부서 담당자)

시작부터 PoC와 MVP에 집중하여 빠르게 결과물을 확보한 뒤, 단계별로 기능을 확장해 나갑니다.
