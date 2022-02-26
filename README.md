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
