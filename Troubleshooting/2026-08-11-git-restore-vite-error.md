test

# 📌 Git 파일 복구 및 Vite 모듈 참조 에러 해결

## 1. 개요
* **일자**: 2026-08-11
* **주요 내용**: Git 커밋 되돌리기를 통한 특정 파일 복구 및 Vite 빌드 모듈 에러 해결

## 2. 문제 상황
* 타인의 커밋 내역 반영으로 인해 기존에 작성한 프론트엔드 작업 파일이 삭제됨.
* 화면 컴포넌트 파일 복구 후 실행 시 `[plugin:vite:import-analysis] Failed to resolve import` 에러 발생.

## 3. 원인 분석
* **파일 누락**: 화면 파일(`WarehouseLocationPage.vue`)만 복구되고, 연관된 서비스 파일(`warehouseLocation.ts`)이 복구되지 않아 모듈 참조 실패.

## 4. 해결 방법
1. **IntelliJ Git Log 활용**: 해당 커밋 위치에서 누락된 service 파일 선택.
2. **Revision Checkout**: `리비전 체크아웃`을 실행하여 특정 파일만 지정 커밋 시점으로 복원.
3. **의존성 확인**: 화면단과 서비스단 파일 간의 참조 관계 재확인 후 정상 동작 확인.

## 5. 배운 점
* 전체 커밋 Revert 대신 필요 파일만 선택하여 복구하는 과정 숙지 (`Get from Revision`).
* Vue/Vite 환경에서 모듈 참조 에러 발생 시 연관된 TS/JS 파일 존재 여부 우선 확인.
