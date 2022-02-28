# Nestjs Board

## 프로젝트 생성

- npm i -g @nestjs/cli
- nest new [Project Name]

<br/>
<br/>

## 모듈 생성하기

- nest g module boards
  - nest: using nest-cli
  - g: generate
  - module: schematic that i want to create
  - boards: name of the schematic

<br/>
<br/>

## Boards Controller 생성하기

- 들어오는 요청을 처리하고 클라이언트에 응답을 반환
- nest g controller boards --no-spec
  - nest: using nest-cli
  - g: generate
  - controller: controller schematic
  - boards: name of the schematic
  - --no-spec: 테스트를 위한 소스 코드 생성 x

<br/>
<br/>

## Boards Service 생성하기

- 데이터베이스 관련된 로직 처리
- nest g service boards --no-spec
  - nest: using nest-cli
  - g: generate
  - service: service schematic
  - boards: name of the schematic
  - --no-spec: 테스트를 위한 소스 코드 생성 x

<br/>
<br/>

---

## Pipe

- @Injectable() 데코레이터로 주석이 달린 클래스
- **data transformation**과 **data validation**을 위해서 사용
- 컨트롤러 경로 처리기에 의해 처리되는 인수에 대해 작동
- Nestjs는 메소드가 호출되기 직전에 파이프를 삽입하고 파이프는 메소드로 향하는 인수를 수신하고 이에 대해 작동

<br />

### Data Transformation

- 입력 데이터를 원하는 형식으로 변환(예: 문자열에서 정수로)

<br/>

### Data Validation

- 유효성 체크

<br/>

### Pipe 사용 방법

- Handler-level Pipes
  - UsePipes() 데코레이터를 이용해서 사용
  - 선언한 핸들러의 모든 파라미터에 적용

<br/>

- Parameter-level Pipes
  - 특정한 파라미터에만 적용

<br/>

- Global-level Pipes
  - 애플리케이션 레벨의 파이프
  - 클라이언트에서 들어오는 모든 요청에 적용
  - main.ts에 추가
    - app.useGlobalPipes(GlobalPipes)

<br/>

### 필요한 모듈

<br/>

```properties
npm i class-validator class-transformer
```

- https://github.com/typestack/class-validator#manula-validation

---

## TypeORM

### TypeORM이란?

- TypeORM은 node.js에서 실행되고 TypeScript로 작성된 객체 관계형 매퍼 라이브러리
- TypeORM은 MySQL, PostgreSQL, MariaDB, SQLite, MS SQL Server, Oracle, SAP Hana 및 WebSQL과 같은 여러 데이터베이스를 지원

<br/>

### ORM (Object Relational Mapping) 이란?

- 객체와 관계형 데이터베이스의 데이터를 자동으로 변형 및 연결하는 작업
- ORM을 이용한 개발은 객체와 데이터베이스의 변형에 유연하게 사용할 수 있다.

<br/>

### TypeORM 특징과 이점

- 모델을 기반으로 데이터베이스 테이블 체계를 자동으로 생성
- 데이터베이스에서 개체를 쉽게 삽입, 업데이트 및 삭제 가능
- 테이블 간의 매핑(일대일, 일대 다, 다대 다) 생성
- 간단한 CLI 명령 제공
- TypeORM은 간단한 코딩으로 ORM 프레임워크를 사용하기 쉽다.
- TypeORM은 다른 모듈과 쉽게 통합

<br/>

### TypeORM 사용하기

```properties
npm install pg typeorm @nestjs/typeorm
```

- @nestjs/typeorm: Nestjs에서 TypeORM을 사용하기 위해 연동시켜주는 모듈
- typeorm: TypeORM 모듈
- pg: Postgres 모듈

https://docs.nestjs.com/techniques/database

---

<br/>
<br/>

# 인증 기능 구현

## Auth 모듈 생성

- nest g module Auth

<br/>

## Auth Controller 생성

- nest g controller auth --no-spec

<br/>

## Auth Service 생성

- nest g service auth --no-spec

<br/>

## User를 위한 Entity 생성

- 유저에 대한 인증을 하는 것이기 때문에 유저가 필요
- 유저 데이터를 위한 유저 Entity 생성

1. user.entity.ts 파일 생성
1. 파일 소스 코드 작성

<br/>

## User Repository 생성

- User Entity를 생성, 수정, 삭제 등의 로직을 처리하기 위해서 Repository 생성

1. user.repository.ts 파일 생성
1. 파일 소스 코드 작성
