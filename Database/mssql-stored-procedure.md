# 📌 MSSQL Stored Procedure 활용 및 비즈니스 로직 연동

## 1. 개요
- MSSQL(SSMS) 환경에서 Stored Procedure(SP)를 활용하여 데이터 처리 로직을 캡슐화하고 트랜잭션 안정성을 확보한 기록.

## 2. 주요 작업 내용
- **트랜잭션 및 예외 처리**: `BEGIN TRAN`, `TRY...CATCH`, `ROLLBACK` 구문을 활용한 일괄 처리 제어.
- **성능 최적화**: Dynamic SQL 지양 및 인덱스 활용 구조 설계, 커서(Cursor) 최소화.
- **Outbound Adapter 연동**: 백엔드 Persistence Layer에서 Stored Procedure를 매핑하여 데이터 조회/수정 처리.

## 3. 배운 점
- Application 단 로직과 DB SP 단 로직 간의 역할 분담 기준 정립.
