# REVIRAL_SYSTEM
상품 리뷰 작성 및 관리 시스템

## 개발하게 된 이유
마케팅 시장에서 스토어를 운영중인 셀러들이 리뷰어들을 단기 고용하여 셀러들의 상품에 리뷰를 남기게되는 시스템을 알게되었습니다.
해당 리뷰를 남긴 사용자는 셀러에게 소장의 원고료와 상품 구매 비용을 받게 됩니다. 
이러한 구조에서 셀러와 리뷰어는 익명으로 활동합니다. 그렇기에 리뷰어가 원고료를 지급받지 못하는 경우 또는 리뷰를 적절한 시간 내에
작성하지 않아 발생하는 원인들이 있었습니다. 이를 시스템화하여 문제를 해결해보고자 합니다.

## 기술 스택
  - Framework: Springboot 3v
  - Language: Kotlin 1.9
  - Database: PostgreSQL, Redis
  - Messaging: Kafka

## 프로젝트 아키텍처
#### SOLID 원칙을 적용한 프로젝트 설계로 유지보수와 확장성, 가독성을 높은 아키텍처를 설계를 위해 아래와 같이 구조를 작성하였습니다.
- application (애플리케이션 서비스 레이어)
  - service (도메인 로직 처리)
  - dto (데이터 전송 객체)
  - usecase ( 특정 비즈니스 로직 유스케이스 정의)
- domain (핵심 비즈니스 로직)
  - model (Entity, VO 객체)
  - repository ( 도메인 객체를 저장하는 인터페이스
  - event ( 도메인 이벤트 [비동기 이벤트 처리] )
- infrastructure (인프라 기술적 세부 사항, API 클라이언트 등)
  - adapter (외부 API 연동, 데이터 변환)
  - persistence (DB 관련, JPA Repository 구현체)
  - config (설정 클래스, Security, CORS 등)
  - security (인증 및 인가처리 JWT, OAUTH )
- persentation (웹 계층 Controller, REST API)
  - controller ( 컨트롤러)
  - exception ( 글로벌 예외처리 )
- common ( 공통 유틸리티 및 상수 )
  - utils ( 유틸리티 )
  - constants ( 프로젝트 전역 상수 )

 
  
