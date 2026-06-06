# validation

인프런 김영한 **스프링 MVC 2편 - 백엔드 웹 개발 활용 기술(4)** 강의에서 입력값 검증(validation)을 학습한 저장소입니다.

## 사용 기술

- Java
- Spring Boot 2.4.4 (`spring-boot-starter-web`, `spring-boot-starter-thymeleaf`)
- Lombok
- Gradle

## 학습한 내용

상품 관리(itemservice) 예제에 입력값 검증을 단계별(V1 → V2)로 적용했습니다.

- **V1** (`ValidationItemControllerV1`): `Map<String, String>` 형태로 직접 오류를 모아 `model`에 담아 화면에 전달
  - 필드 오류(상품명 필수, 가격/수량 범위) 처리
- **V2** (`ValidationItemControllerV2`): V1을 기반으로 글로벌 오류(가격×수량 합 조건) 등 검증 로직을 보완
- 검증 결과를 보여주는 V1/V2 별도 화면 템플릿 (`templates/validation/v1`, `templates/validation/v2`)
- 메시지 소스(`messages.properties`, `messages_en.properties`)와 메시지 소스 테스트(`MessageSourceTest`)를 함께 포함

## 프로젝트 구조

```
src/main/java/hello/itemservice
├── ItemServiceApplication.java
├── TestDataInit.java
├── domain/item (Item, ItemRepository)
└── web/validation
    ├── ValidationItemControllerV1.java
    └── ValidationItemControllerV2.java
src/main/resources/templates/validation
├── v1/  (addForm, editForm, items, item)
└── v2/  (addForm, editForm, items, item)
```
