# 📌 헥사고날 아키텍처(Hexagonal Architecture) 적용 정리

## 1. 개요 및 도입 목적
- **도메인 중심 설계**: 외부 프레임워크나 DB 기술 변경에 도메인 로직이 영향받지 않도록 계층 분리.
- **테스트 용이성**: Port와 Adapter 구조를 통해 유닛 테스트 및 Mocking 용이성 확보.

## 2. 계층 구조 (Layers)
- **Domain (Core)**: 비즈니스 엔티티 및 핵심 규칙 정의 (외부 의존성 0%)
- **Ports (Interfaces)**:
  - `Inbound Port`: Application Service가 구현하는 유스케이스 인터페이스 (예: `UseCases`)
  - `Outbound Port`: DB 접근, 외부 API 호출을 위해 정의한 인터페이스 (예: `RepositoryPort`)
- **Adapters (Implementation)**:
  - `Inbound Adapter`: Web Controller, REST API
  - `Outbound Adapter`: Persistence Adapter (SSMS 프로시저 호출, ORM 연동 등)

## 3. 실무 적용 시 배운 점
- 계층 분리로 인한 DTO-Entity 간 매핑 비용은 증가하지만, DB/외부 인터페이스 변경 시 도메인 로직 손상 없이 Adapter만 교체 가능한 이점 체득.
