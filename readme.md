# Project Atlas: 지능형 브리핑 자동화 시스템 (비정기적 보고서)

![GitHub Workflow Status](https://img.shields.io/badge/Workflow-Prompt%20Generator-blue?style=flat-square) ![License](https://img.shields.io/badge/License-Apache%202.0-blue?style=flat-square) ## 🌟 프로젝트 소개

[cite_start]`Project Atlas`는 'PM 비정기적 보고서 ver 3.0'에 명시된 비전을 실현하기 위한 **지능형 브리핑 자동화 웹 애플리케이션**입니다. [cite_start]이 프로젝트는 전통적인 소프트웨어 개발 방식을 넘어, 대화형 AI(Gemini)를 핵심 개발 파트너로 활용하여 시스템을 구축하는 새로운 패러다임을 제안합니다.

[cite_start]우리의 목표는 팀의 휘발성 대화와 암묵적 지식을 구조화된 기록으로 전환하고, 이 기록들을 데이터 자산으로 축적하여 팀의 소통 방식과 업무 문화 자체를 혁신하는 것입니다.

## 📝 목차

1.  [핵심 철학 및 목표](#핵심-철학-및-목표)
2.  [아키텍처 및 개발 원칙](#아키텍처-및-개발-원칙)
3.  [주요 기능](#주요-기능)
4.  [기술 스택](#기술-스택)
5.  [프로젝트 진행 단계](#프로젝트-진행-단계)
6.  [설치 및 실행 방법](#설치-및-실행-방법)
7.  [프로젝트 구조](#프로젝트-구조)
8.  [기여 방법](#기여-방법)
9.  [라이선스](#라이선스)
10. [문의](#문의)

## 💡 핵심 철학 및 목표

[cite_start]`Project Atlas`의 핵심 철학은 **"기록이 곧 소통이고, 축적이 곧 자산이다"** 입니다. [cite_start]이 철학을 바탕으로 다음의 구체적인 목표(KPI)를 달성하고자 합니다:

* [cite_start]**'마이크로 브리핑'의 일상화**: 정교하고 직관적인 UI/UX를 통해, 2~3일 단위의 짧은 브리핑 작성 시간을 5분 이내로 단축시켜, 부담 없는 일상의 습관으로 만듭니다.
* [cite_start]**'매크로 리포트' 생성 자동화**: 매주 금요일마다 작성하던 주간 리포트의 초안 작성 시간을 90% 이상 단축시킵니다. [cite_start]사용자는 주중에 작성된 마이크로 브리핑 2~3개를 클릭 몇 번으로 조합하여, 기존 1시간이 걸리던 작업을 5분 안에 완료할 수 있습니다.
* [cite_start]**커뮤니케이션 품질 향상**: 시스템 자체가 사용자가 '목표 및 기대효과'와 같은 가치 중심적인 내용을 작성하도록 유도합니다. [cite_start]이를 통해 모든 보고서가 단순한 업무 나열을 넘어, 각 업무의 의미와 기여도를 명확히 전달하는 고품질의 소통 자료가 되도록 합니다.
* [cite_start]**완벽한 템플릿 준수율**: 사용자가 형식에 신경 쓰지 않아도, 최종 결과물은 제공된 템플릿의 문법(아이콘, 들여쓰기, 특수문자 등)을 100% 준수하도록 강제합니다. [cite_start]이를 통해 모든 보고서의 통일성과 전문성을 극대화합니다.

## 🏗️ 아키텍처 및 개발 원칙

[cite_start]이 프로젝트는 대화형 AI(Gemini)와 상호작용하며 구축됩니다. [cite_start]성공적인 AI 주도 개발을 위해 다음 세 가지 핵심 기둥을 따릅니다:

1.  [cite_start]**급진적 모듈화 (Radical Modularization)**: 거대한 시스템을 한 번에 구축하려는 시도를 버리고, 작고 독립적으로 검증 가능한 기능 단위(모듈)로 철저히 분해합니다. [cite_start]이는 LLM의 제한된 컨텍스트 창과 인지적 한계를 극복하는 가장 핵심적인 전략입니다.
2.  [cite_start]**점진적 검증 (Incremental Verification)**: 각 모듈을 독립적으로 구축하고, 테스트하고, 검증한 뒤 다음 단계로 나아갑니다. [cite_start]이 점진적인 접근 방식은 개발 과정의 리스크를 최소화하고, AI가 생성한 코드에서 발생할 수 있는 '복합적인 기술 부채'를 방지합니다.
3.  [cite_start]**체계적인 컨텍스트 관리 (Systematic Context Management)**: LLM은 상태를 저장하지 못하는 '기억상실증에 걸린 프로세서'와 같습니다. [cite_start]따라서 우리는 프로젝트의 모든 중요한 결정, 아키텍처, 그리고 완성된 모듈의 계약을 `CONTEXT.md`라는 외부 메모리 파일에 수동으로 기록하고 관리할 것입니다. [cite_start]이 문서는 프로젝트의 유일한 진실 공급원(Single Source of Truth)으로서, 대화의 일관성을 유지하고 '컨텍스트 표류(Context Drift)' 현상을 방지하는 강력한 무기가 될 것입니다.

## ✨ 주요 기능

이 프로젝트는 다음 4단계로 나누어 개발됩니다.

1.  **비정기적 보고서 템플릿 정의 및 관리**:
    * [cite_start]마크다운(Markdown) 기반의 표준화된 보고서 템플릿을 정의합니다.
    * [cite_start]최종 결과물의 문법(아이콘, 들여쓰기, 특수문자 등)을 100% 준수하도록 강제합니다.

2.  **YAML을 이용한 비정기적 보고서 작성**:
    * [cite_start]YAML 스키마를 사용하여 보고서의 내용을 구조화하고 정의합니다.
    * [cite_start]`CONTEXT.md`와 같은 외부 파일을 참조하여 동적으로 내용을 삽입합니다.

3.  **프롬프트 템플릿 자동화 ('Prompt as Code')**:
    * [cite_start]구조화된 프롬프트를 YAML 파일로 템플릿화하고, 파이썬 스크립트(`generate_prompt.py`, `run_workflow.py`)를 통해 프롬프트를 자동으로 생성합니다.
    * [cite_start]GitHub Actions 워크플로우를 통해 프롬프트 템플릿 변경 시 자동으로 프롬프트를 생성하고 Pull Request에 댓글로 게시하여 팀 협업을 촉진합니다.

4.  **실제 프로그램 개발 (웹 애플리케이션)**:
    * [cite_start]사용자가 '마이크로 브리핑'을 작성하고 관리할 수 있는 UI/UX를 제공합니다.
    * [cite_start]작성된 브리핑을 조합하여 '매크로 리포트(주간 리포트)'를 자동 생성하는 핵심 로직을 구현합니다.
    * [cite_start]데이터 영속성(LocalStorage) 및 클립보드 복사 기능을 포함합니다.
    * [cite_start]Vitest를 활용한 단위 테스트 및 Docker를 이용한 배포 환경을 구축합니다.

## 🛠️ 기술 스택

| 기술 (Technology)    | 버전 (Version) | 프로젝트 내 역할 (Role in Project)                                       | 선정 사유 및 핵심 통합 포인트 (Rationale & Key Integration Point)     |
| **Node.js** | LTS (v20.x+)   | 런타임 환경                                                              |
| **pnpm** | Latest         | [cite_start]패키지 매니저 (효율적인 디스크 공간 사용, 빠른 설치)             | |
| **Python** | 3.x            | 프롬프트 자동화 스크립트                                                 |
| **PyYAML** | Latest         | [cite_start]YAML 파싱 라이브러리 (Python)                                    | |
| **GitHub Actions** | Latest         | [cite_start]CI/CD 자동화 플랫폼                                          | |

## 🗺️ 프로젝트 진행 단계

[cite_start]본 프로젝트는 다음과 같은 에픽(Epic)과 스프린트(Sprint)로 진행됩니다:

* **Phase 0: 초석 다지기 (Foundation)**
    * [cite_start]목표: 본격적인 개발에 앞서 완벽하게 통제되고 일관된 개발 환경을 구축하고, Gemini에게 프로젝트의 비전과 구조를 명확히 각인시키는 초기 컨텍스트를 형성합니다.
* **Epic 1: 핵심 편집기 구현 (Core Editor Implementation)**
    * **Sprint 1: 정적 골격 - UI 컴포넌트 생성**
        * [cite_start]목표: 데이터 연동이나 기능 없이, 사용자가 보게 될 모든 화면의 시각적 요소를 순수한 정적 UI 컴포넌트로 완성합니다. [cite_start]건물의 골조를 먼저 세우는 것과 같습니다.
    * **Sprint 2: 중앙 신경계 - 상태 관리와 동적 UI**
        * [cite_start]목표: 애플리케이션의 '두뇌'인 상태 관리 시스템을 구축하고, 이를 UI 컴포넌트와 연결하여 사용자의 입력에 따라 화면이 동적으로 변화하도록 만듭니다.
* **Epic 2: 결과물 생성 및 활용 (Output Generation & Utilization)**
    * **Sprint 3: 손과 목소리 - 출력 및 영속성**
        * [cite_start]목표: 사용자가 입력한 데이터를 최종 마크다운 보고서로 변환하고(출력), 작업 내용을 브라우저에 안전하게 저장(영속성)하는 기능을 구현합니다.
    * **Sprint 4: 핵심 기능 - 주간 리포트 종합**
        * [cite_start]목표: 여러 개의 '마이크로 브리핑'을 지능적으로 조합하여 하나의 포괄적인 '주간 리포트'로 자동 생성하는, 프로젝트의 가장 핵심적인 부가가치 기능을 완성합니다.
* **마무리: 검증, 테스트, 그리고 배포 (Wrap-up)**
    * [cite_start]목표: 구현된 모든 기능의 품질을 단위 테스트를 통해 보증하고, 최종 프로덕션 빌드를 생성하여 배포 가능한 상태로 만듭니다.

## 🚀 설치 및 실행 방법

### 1. 로컬 환경 준비 (Phase 0)

[cite_start]프로젝트 시작 전, 다음 도구들이 설치되어 있는지 확인하십시오.

* [cite_start]**Node.js 버전 관리자 (nvm)**: 시스템에 여러 버전의 Node.js를 손쉽게 관리할 수 있도록 nvm(Node Version Manager)을 설치합니다. [cite_start]이는 팀원 간 또는 다른 프로젝트 간의 Node.js 버전 충돌 문제를 원천적으로 예방합니다.
    * [cite_start]`nvm install --lts` (최신 LTS 버전 설치, 이 가이드 작성 시점 기준 v20.x 이상) 
    * [cite_start]`nvm use --lts` (해당 버전 활성화) 
* [cite_start]**패키지 매니저 (pnpm)**: `npm install -g pnpm` 명령어를 사용하여 pnpm을 전역으로 설치합니다 [cite: 19, 598][cite_start]. pnpm은 효율적인 디스크 공간 사용과 빠른 설치 속도를 제공하며, 이 프로젝트의 표준 패키지 매니저로 사용됩니다.
* [cite_start]**Git**: 소스 코드의 버전을 관리하고 변경 사항을 추적하기 위해 Git을 설치합니다.
* [cite_start]**Visual Studio Code (VS Code)** 및 다음 확장 프로그램 설치:
    * [cite_start]ESLint: 코드의 잠재적 오류를 찾아내고 코딩 스타일을 강제하여 코드 품질을 높입니다.
    * [cite_start]Prettier - Code formatter: 코드 스타일을 일관되게 자동 정리하여 가독성을 향상시킵니다.
    * [cite_start]Tailwind CSS IntelliSense: Tailwind CSS 클래스 이름을 자동 완성하고 문법 오류를 표시하여 스타일링 작업의 생산성을 극대화합니다.

[cite_start]이 모든 도구를 사전에 완벽하게 준비함으로써, 우리는 이후의 모든 AI 생성 단계가 예측 가능하고 안정적인 환경에서 수행될 것임을 보장할 수 있습니다.

### 2. 프로젝트 초기화 (AI 주도)

[cite_start]이제 우리의 개발 파트너인 Gemini를 위한 '부트로더(Bootloader)'를 실행할 차례입니다. [cite_start]이 첫 번째 마스터 프롬프트, 즉 '창세기 프롬프트(Genesis Prompt)'는 프로젝트 전체의 방향성을 설정하고, Gemini가 최적의 결과물을 생성하도록 그 역할과 품질 기준을 명확히 정의합니다.

[cite_start]다음 프롬프트를 복사하여 Gemini와의 새 대화창에 입력하는 것으로 'Project Atlas' 개발의 공식적인 시작을 알리게 됩니다.

```markdown
### 페르소나 할당 (Persona Assignment) ###
[cite_start]당신은 지금부터 "Project Atlas"를 위한 시니어 풀스택 소프트웨어 아키텍트 역할을 수행합니다.
[cite_start]당신의 전문 분야는 다음과 같습니다: - **기술 스택**: React, TypeScript, Vite, Node.js - **상태 관리**: Zustand와 Immer를 사용한 효율적이고 예측 가능한 상태 관리 - **UI/UX**: Radix UI를 활용한 높은 접근성의 컴포넌트 설계 및 Tailwind CSS를 이용한 스타일링 - **아키텍처**: 클린 아키텍처(Clean Architecture) 원칙에 입각한 모듈러 설계 - **품질 보증**: Vitest와 React Testing Library를 사용한 견고한 테스트 코드 작성 
[cite_start]당신은 항상 안전하고, 확장 가능하며, 유지보수성이 뛰어난 코드를 작성해야 합니다.
[cite_start]모든 코드는 TypeScript를 사용하여 강력한 타입 안정성을 보장해야 합니다.
### 프로젝트 컨텍스트 (Project Context) ###
[cite_start]우리는 "지능형 브리핑 자동화 시스템 (Project Atlas)"이라는 웹 애플리케이션을 개발할 것입니다.
[cite_start]이 프로젝트의 상세 기획서는 "PM 비정기적 보고서 ver 3.0"에 정의되어 있습니다.
[cite_start]**핵심 철학**: "기록이 곧 소통이고, 축적이 곧 자산이다." 
[cite_start]우리는 단순히 텍스트를 생성하는 도구를 만드는 것이 아니라, 팀의 소통 방식과 업무 문화 자체를 혁신하는 시스템을 구축합니다.
[cite_start]휘발성 대화를 구조화된 기록으로 바꾸고, 개별 기록들을 모아 통찰력 있는 보고서로 자동 종합하는 것이 목표입니다.
**핵심 목표 및 KPI**:
1.  [cite_start]**'마이크로 브리핑'의 일상화**: 2~3일 단위의 짧은 브리핑 작성 시간을 5분 이내로 단축시켜, 부담 없는 일상의 습관으로 만듭니다.
2.  [cite_start]**'매크로 리포트' 생성 자동화**: 주간 리포트 초안 작성 시간을, 주중에 작성된 마이크로 브리핑 2~3개를 클릭 몇 번으로 조합하여 90% 이상 단축시킵니다.
3.  [cite_start]**커뮤니케이션 품질 향상**: 모든 보고서가 '목표와 가치' 중심으로 작성되도록 유도합니다.
4.  [cite_start]**완벽한 템플릿 준수율**: 최종 결과물은 제공된 템플릿의 문법을 100% 준수하도록 강제하여 보고서의 통일성과 전문성을 극대화합니다.
### 초기 지시사항 (Initial Instruction) ###
[cite_start]이 컨텍스트를 완전히 이해했는지 확인하고, 다음 단계의 지시를 받을 준비가 되었는지 "준비 완료. 다음 지시를 내려주십시오."라고만 대답하십시오.


Gemini의 지시에 따라 프로젝트 생성(pnpm create vite briefing-atlas --template react-ts), 의존성 설치, 폴더 구조 생성 및 품질 도구 설정 등을 진행하십시오1111111111111111111111111.


반드시 CONTEXT.md 파일을 프로젝트 루트에 생성하고, 초기 내용을 작성하십시오. 222222 이 파일은 대화형 개발 방법론의 핵심인 '체계적인 컨텍스트 관리'의 시작입니다33333.


3. 프로젝트 실행
모든 초기 설정이 완료되면, 프로젝트 루트에서 다음 명령어를 실행하여 개발 서버를 시작할 수 있습니다4.
Bash
pnpm dev


📂 프로젝트 구조
Project Atlas는 클린 아키텍처 원칙에 기반하여 다음과 같은 폴더 구조를 따릅니다5555555.
briefing-atlas/
├── .github/                 # GitHub Actions 워크플로우 파일 
│   └── workflows/
│       └── prompt_generator.yml
├── node_modules/            # 프로젝트 의존성
├── public/                  # 정적 자산
├── src/
│   ├── app/                 # 전역 설정 및 Zustand 스토어 
│   ├── components/          # 재사용 가능한 순수 UI 컴포넌트 
│   ├── features/            # 도메인별 기능 (예: briefing 관련 로직 및 컴포넌트) 
│   ├── lib/                 # 순수 유틸리티 함수 (예: markdownGenerator, aggregation) 
│   └── types/               # 전역 타입 정의 (예: atlas.ts) 
├── .gitignore               # Git 추적 제외 파일 설정
├── CONTEXT.md               # 프로젝트의 영구적인 기억 장치 (AI 컨텍스트 관리) 
├── README.md                # 프로젝트 설명 파일
├── package.json
├── pnpm-lock.yaml
├── tailwind.config.js
├── postcss.config.js
├── tsconfig.json
├── .eslintrc.cjs
├── .prettierrc
└── vite.config.ts





PR 생성 시, GitHub Actions가 자동으로 프롬프트를 생성하여 댓글로 게시합니다.


코드 리뷰: 자동 생성된 프롬프트와 코드에 대한 리뷰에 적극적으로 참여하여 품질을 높입니다.


⚖️ 라이선스
이 프로젝트는 Apache License 2.0 라이선스 하에 배포됩니다. 11111111
Apache License 2.0의 주요 특징:
소프트웨어의 사용, 수정, 배포 및 상업적 활용을 자유롭게 허용합니다.
파생 저작물을 비공개(Proprietary) 소프트웨어로 만들고 판매할 수 있습니다.
재배포 시 원본 저작권 고지 및 라이선스 전문을 포함해야 합니다.
원본 코드를 수정했다면, 어떤 변경이 있었는지 명확하게 고지해야 합니다.
특허권 부여: 코드 기여자가 해당 코드와 관련된 특허권을 사용자에게 무상으로 부여하는 명시적인 조항이 포함되어, 사용자가 특허 침해 소송의 위험 없이 코드를 사용할 수 있도록 보호합니다.



