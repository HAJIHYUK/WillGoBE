# WillGO - 위치기반 목표 달성 서비스

<br>

> 🚨 **잠깐만요! 코드를 보시기 전에 꼭 읽어주세요.** 
> 이 프로젝트는 팀원들과 함께 백엔드 시스템의 기초를 막 다지던 시기에 작성한 포트폴리오입니다. 
> 지금 다시 객체지향 설계와 클린 아키텍처의 관점에서 보니 부족한 점이 너무나도 많이 보이지만, 당시 저희 팀의 치열했던 고민과 노력의 흔적이기에 원본 그대로 남겨두었습니다.
> 코드를 보시기 전에 하단의 **[💡 프로젝트 회고 및 리팩토링 계획](#retrospective)**을 먼저 읽어주시면 감사하겠습니다!

<br>

## 📑 목차
- [프로젝트 소개](#project-intro)
- [개요](#overview)
- [주요 기능](#main-features)
- [화면 구성](#screens)
- [기술 스택](#tech-stack)
- [주요 구현 기능](#implementations)
- [프로젝트 회고 및 리팩토링 계획](#retrospective)
- [시작하기](#getting-started)
- [API 문서](#api-docs)
- [지원](#support)

## 📝 프로젝트 소개 <a id="project-intro"></a>
WillGO는 위치 기반의 목표 달성을 돕는 서비스입니다. 사용자가 설정한 목표 장소에 방문하여 GPS를 통해 자동으로 인증하고 포인트 시스템과 푸시 알림으로 동기부여를 강화하는 위치기반 목표인증 서비스입니다.

## 📊 개요 <a id="overview"></a>

### 🏷️ 프로젝트 정보
| 항목 | 내용 |
|------|------|
| 프로젝트 이름 | WillGO - 위치기반 목표 달성 서비스 |
| 개발 기간 | 2024.12 - 2025.03 |
| 서비스 링크 | [WillGO 바로가기](https://locationcheckgo.netlify.app/) |
| 팀 명 | SWYP 8기 6팀 |

### 👥 팀원 구성
| 역할 | 이름 |
|------|------|
| PM | 윤현수, 박수현 |
| 디자이너 | 윤재호 |
| Backend | 김준현, 장민지, 하지혁 |
| Frontend | 박민형, 이영주 |

### 💻 Backend 개발 담당
| 개발자 | 담당 업무 |
|--------|-----------|
| 김준형 | 위치 API, 사용자 및 설정 관련 API, Swagger를 통한 API 문서화, 배포 환경 및 DB 구축 |
| 장민지 | 로그인 API, 포인트 API |
| 하지혁 | 목표 인증 API |

## 🚀 주요 기능 <a id="main-features"></a>
### 1. 목표 관리
- 목표명, 목표기간, 목표요일 설정
- 종 3개의 목표 생성 가능
- 목표 종류:
  - 인증가능 목표
  - 인증완료 목표
  - 임시저장 목표

### 2. 위치 기반 인증
- 지도 UI를 통한 내위치, 목표장소 확인
- 목표장소 100m 이내 접근 시 인증 가능
- 인증 요일, 주 인증횟수에 따라 보상포인트 차등 지급
- 주 인증횟수 채울 시 보너스포인트 추가 지급

### 3. 포인트 시스템
- 회원가입 시: 2,000p 초기 지급
- 목표 생성 시: 200p 차감
- 리워드 신청: 
  - 커피쿠폰(5,000p)
  - 편의점쿠폰(10,000p)

## 📱 화면 구성 <a id="screens"></a>

<div align="center">
  <h3>로그인 화면</h3>
  <img src="https://github.com/Location-based-target-authentication/BE/blob/df729087342116a68baeacba34b9a74fdecb33e4/Location-based-target-authentication/src/main/resources/img/login.jpg" width="300" alt="로그인 화면"/>
  
  <h3>메인 화면</h3>
  <img src="https://github.com/Location-based-target-authentication/BE/blob/df729087342116a68baeacba34b9a74fdecb33e4/Location-based-target-authentication/src/main/resources/img/main.jpg" width="300" alt="메인 화면"/>
  
  <h3>설정 화면</h3>
  <img src="https://github.com/Location-based-target-authentication/BE/blob/df729087342116a68baeacba34b9a74fdecb33e4/Location-based-target-authentication/src/main/resources/img/main_2.jpeg" width="300" alt="설정 화면"/>
  
  <h3>목표 관리</h3>
  <div style="display: flex; justify-content: center; gap: 20;">
    <div>
      <h5>목표 추가</h5>
      <img src="https://github.com/Location-based-target-authentication/BE/blob/fc7684f55e70e9ca06f77a0fea8c7fbbfeeb5f3a/Location-based-target-authentication/src/main/resources/img/goal_1.jpg" width="300" alt="목표 추가"/>
    </div>
    <div>
      <h5>목표 위치 등록</h5>
      <img src="https://github.com/Location-based-target-authentication/BE/blob/fcc46152f57276f782253c82aca78e023d7e3ed2/Location-based-target-authentication/src/main/resources/img/Location2.JPG" width="300" alt="목표 위치 등록"/>
    </div>
    <div>
      <h5>목표 완료</h5>
      <img src="https://github.com/Location-based-target-authentication/BE/blob/df729087342116a68baeacba34b9a74fdecb33e4/Location-based-target-authentication/src/main/resources/img/goal_2.jpg" width="300" alt="목표 완료"/>
    </div>
    <div>
      <h5>목표 확인</h5>
      <img src="https://github.com/Location-based-target-authentication/BE/blob/df729087342116a68baeacba34b9a74fdecb33e4/Location-based-target-authentication/src/main/resources/img/goal_3.jpg" width="300" alt="목표 확인"/>
    </div>
  </div>
  
  <h3>목표 위치 인증</h3>
  <img src="https://github.com/Location-based-target-authentication/BE/blob/fcc46152f57276f782253c82aca78e023d7e3ed2/Location-based-target-authentication/src/main/resources/img/Location.JPG" width="300" alt="위치 인증"/>
  
  <h3>리워드</h3>
  <div style="display: flex; justify-content: center; gap: 20;">
    <div>
      <h5>리워드 신청</h5>
      <img src="https://github.com/Location-based-target-authentication/BE/blob/df729087342116a68baeacba34b9a74fdecb33e4/Location-based-target-authentication/src/main/resources/img/point.png" width="300" alt="리워드 신청"/>
    </div>
    <div>
      <h5>리워드 지급</h5>
      <img src="https://github.com/Location-based-target-authentication/BE/blob/main/Location-based-target-authentication/src/main/resources/img/point2.png" width="500" alt="리워드 지급"/>
    </div>
  </div>
</div>

## 🔧 기술 스택 <a id="tech-stack"></a>
### Backend
- Java 17
- Spring Boot 3.2.1
- Spring Security
- JWT
- JPA/Hibernate
- MySQL
- Swagger

### Frontend
- React
- TypeScript
- shadcn/ui

### 인증
- OAuth2.0 (Google, Kakao)
- JWT 기반 인증

### 외부 API
- Kakao Maps API (위치 기반 서비스)

### DevOps
- Oracle Server
- Ubuntu
- Github Actions (CI/CD)

## 🛠️ 주요 구현 기능 <a id="implementations"></a>

### 1. 카카오맵 API 연동
- 목표위치 장소 검색 기능
- 사용자 반경 100m 이내 목표 장소 확인 로직

### 2. 사용자 관련 기능
- 소셜 로그인 (Google, Kakao)
- 서비스 약관 동의
- 개인정보 처리방침
- 회원 정보 관리
- 로그아웃 및 회원 탈퇴

### 3. API 문서화
- Swagger를 활용한 API 명세서 작성
- API 엔드포인트 및 요청/응답 데이터 구조 정의
- API 테스트 환경 구축

### 4. 보안 강화
- Spring Security를 활용한 백엔드 보안 구현
- CORS 설정을 통한 안전한 API 통신
- 민감한 사용자 정보 암호화 처리

<br>

## 💡 프로젝트 회고 및 리팩토링 계획 <a id="retrospective"></a>

이 프로젝트에서 저는 백엔드의 핵심인 **목표 인증 및 관리 API**를 전담하여 개발했습니다. 소셜 로그인, 위치 기반 인증, 포인트 시스템 등 여러 도메인이 얽혀 있는 복잡한 요구사항을 구현해보며 많은 것을 배웠습니다. 하지만 이후 객체지향 설계와 아키텍처에 대해 지속적으로 공부하며 성장한 지금 다시 제 코드(`GoalService.java`)를 보니, 당시에는 미처 고려하지 못했던 설계적 결함들이 눈에 띕니다. 이 코드를 통해 과거의 제가 어떤 부분에서 부족했고 이를 앞으로 어떻게 리팩토링할 것인지 남기고자 합니다.

### 1. 빈약한 도메인 모델(Anemic Domain Model)과 도메인 지식 누수
*   **아쉬운 점:** `validateGoalAchievement` 메서드를 보면, 목표 인증 성공 시 상태 변경 로직(`목표 상태가 ACTIVE인지 확인 -> 달성 횟수 증가 -> 타겟 횟수에 도달하면 COMPLETE로 변경`)이 서비스 계층에 모두 노출되어 있습니다. 이로 인해 `Goal` 엔티티는 상태만 들고 있는 껍데기(DTO)로 전락했습니다.
*   **리팩토링 계획:** 무분별한 `@Setter`를 닫고, 상태 변경과 횟수 검증 비즈니스 로직을 `Goal` 엔티티 내부의 `achieve()` 같은 의미 있는 도메인 메서드로 캡슐화(이동)할 것입니다. 서비스 계층은 그저 흐름(Flow)만 제어하도록 변경하겠습니다.

### 2. 서비스 계층의 무거운 책임(SRP 위반)과 트랜잭션 경계
*   **아쉬운 점:** `validateGoalAchievement` (인증 로직) 하나에서 위치 검증 API 호출, 목표 달성 로그 저장, 목표 달성 횟수 업데이트, 포인트 지급, 보너스 포인트 지급까지 수많은 도메인이 결합되어 있습니다. 만약 포인트 서버에 장애가 생기거나 에러가 터지면 롤백되어 **사용자의 인증 기록까지 통째로 날아가는** 위험한 트랜잭션 구조입니다.
*   **리팩토링 계획:** 포인트 지급 같은 부가적인 비즈니스 로직은 핵심 로직과 트랜잭션을 분리하기 위해 Spring Event(`@TransactionalEventListener`)를 발행하는 비동기 이벤트 기반 구조로 리팩토링하여 모듈 간 강결합을 끊어낼 것입니다.

### 3. 불필요한 중복 쿼리 (DB I/O 낭비)
*   **아쉬운 점:** 당일 인증 여부를 확인할 때, 성공한 기록이 있는지(`existsBy...AchievedSuccess = true`)와 실패한 기록이 있는지(`existsBy...AchievedSuccess = false`)를 각각 따로 쿼리하여 DB를 두 번 찌르고 있습니다.
*   **리팩토링 계획:** 해당 유저와 목표, 오늘 날짜를 조건으로 `findBy...` 로 단일 조회한 뒤, 애플리케이션 메모 단에서 성공/실패 여부를 판단하도록 개선하여 불필요한 DB I/O를 절반으로 줄이겠습니다.

### 4. 테스트 불가능한 구조 (시간 결합도 문제)
*   **아쉬운 점:** `validateGoalAchievement`나 `DateRangeCalculator` 같은 핵심 비즈니스 메서드 내부를 보면 `LocalDate.now()`를 직접 호출하여 사용하고 있습니다. 이렇게 시스템 시간에 강하게 결합된 코드는 특정 날짜(예: 월말, 연말, 윤년)에 대한 예외 케이스를 단위 테스트(Unit Test)하기가 사실상 불가능합니다.
*   **리팩토링 계획:** 현재 시간을 외부(Controller)에서 파라미터로 주입받거나, 스프링의 `Clock` 빈을 주입받아 사용하도록 변경하여, 테스트 시점에 언제든 원하는 시간으로 조작(Mocking)할 수 있는 유연한 테스트 가능(Testable) 아키텍처로 개선하겠습니다.

<br>

## 🚀 시작하기 <a id="getting-started"></a>

### 요구사항
- Java 17 이상
- MySQL 8.0 이상

### 설치 및 실행 방법

#### 백엔드 설정
1. 프로젝트 클론
```bash
git clone https://github.com/Location-based-target-authentication/BE.git
cd BE/Location-based-target-authentication
```

2. 프로젝트 빌드 및 실행
```bash
# 의존성 설치
./mvnw clean install

# 애플리케이션 실행
./gradlew bootRun
```

## 📚 API 문서 <a id="api-docs"></a>

### 주요 API

#### 🔐 인증 관련 API
- `POST /api/v1/auth/google/login`: Google 소셜 로그인
- `POST /api/v1/auth/kakao/login`: Kakao 소셜 로그인
- `POST /api/v1/auth/logout`: 로그아웃
- `DELETE /api/v1/auth/withdrawal`: 회원 탈퇴

#### 🎯 목표 관리 API
- `POST /api/v1/goals`: 새로운 목표 생성
- `GET /api/v1/goals`: 목표 목록 조회
- `GET /api/v1/goals/{goalId}`: 특정 목표 상세 조회
- `PUT /api/v1/goals/{goalId}`: 목표 정보 수정
- `DELETE /api/v1/goals/{goalId}`: 목표 삭제
- `POST /api/v1/goals/{goalId}/verify`: 목표 달성 인증
- `GET /api/v1/goals/available-slots`: 사용 가능한 목표 슬롯 조회
- `GET /api/v1/goals/statistics`: 목표 달성 통계 조회
- `POST /api/v1/goals/temporary`: 임시 목표 저장
- `GET /api/v1/goals/verification-history`: 목표 인증 히스토리 조회

#### 💰 포인트 관리 API
- `GET /api/v1/points`: 포인트 내역 조회
- `GET /api/v1/points/balance`: 현재 포인트 잔액 조회
- `POST /api/v1/points/rewards`: 리워드 신청
- `GET /api/v1/points/rewards/history`: 리워드 신청 내역 조회

#### 👤 사용자 관리 API
- `GET /api/v1/users/me`: 내 정보 조회
- `PUT /api/v1/users/me`: 내 정보 수정
- `GET /api/v1/users/me/goals`: 내 목표 목록 조회
- `GET /api/v1/users/me/points`: 내 포인트 내역 조회

#### 📍 위치 관련 API
- `POST /api/v1/locations/verify`: 현재 위치 인증
- `GET /api/v1/locations/search`: 장소 검색
- `GET /api/v1/locations/nearby-goals`: 주변 목표 장소 조회
- `POST /api/v1/locations/validate`: 목표 장소 유효성 검증

#### ⚙️ 시스템 API
- `GET /api/v1/system/version`: 앱 버전 정보 조회
- `GET /api/v1/system/maintenance`: 시스템 점검 정보 조회
- `GET /api/v1/system/terms`: 서비스 약관 조회
- `GET /api/v1/system/privacy-policy`: 개인정보 처리방침 조회

## 📧 지원 <a id="support"></a>

[![Gmail Badge](https://img.shields.io/badge/Gmail-d14836?style=for-the-badge&logo=Gmail&logoColor=white&link=mailto:kjunh972@gmail.com)](mailto:kjunh972@gmail.com)
