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
