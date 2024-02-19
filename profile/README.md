

# 🍃 환경을 위한 소셜 네트워크 서비스, GreenJoy!

<img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=white"/> <img src="https://img.shields.io/badge/Google Cloud-4285F4?style=flat-square&logo=google-cloud&logoColor=white"/> <img src="https://img.shields.io/badge/Google Cloud Storage-AECBFA?style=flat-square&logo=google-cloud-storage&logoColor=white"/>

## 🙋‍♂️ 우리 프로젝트를 소개합니다!
  

## 💻 프로젝트 설치
* JDK 17이상이 설치되어 있어야 합니다.

### - Server

### 1. Git Clone
```bash
$ https://github.com/Green-Joy/BE.git
```

### 2. 구글 소셜 로그인 등록, 파이어 베이스와 구글 클라우드 스토리지 키 발급
* [구글 클라우드 플랫폼](https://console.cloud.google.com/apis/credentials/consent?referrer=search&hl=ko&project=spring-414710)에서 애플리케이션 추가 -> Client Key와 Client Secret Key 발급, Redirect URL 설정
* [파이어 베이스](https://console.firebase.google.com/)에서 .json 형식의 비공개 키 발급 -> "src/main/resources/" 경로에 저장
* [구글 클라우드 스토리지](https://cloud.google.com/?hl=ko)에서 .json 형식의 비공개 키 발급 -> "src/main/resources/" 경로에 저장

### 3. src/main/resources/application.yml 설정
```java
spring:
  servlet:
    multipart:
      max-file-size: 10MB
      max-request-size: 50MB
  security:
    oauth2:
      client:
        registration:
          google:
            redirect-uri: {Redirect URL}
            client-id: {Client Key}
            client-secret: {Client Secret Key}
            scope:
              - email
              - profile
  datasource:
    url: jdbc:mysql://localhost:3306/{DB Name}
    username: {DB Username}
    password: {DB Password}
    driver-class-name: com.mysql.cj.jdbc.Driver
  jpa:
    database: mysql

    hibernate:
      ddl-auto: update
    show-sql: true
    properties:
      hibernate:
        format_sql: true

  cloud:
    gcp:
      storage:
        credentials:
          location: classpath:{Google Cloud Key File}.json
        project-id: {Google Cloud Project-id}
        bucket: {Google Cloud Bucket Name}

app:
  firebase-configuration-file : {Firebase Configuration File}.json
  firebase-bucket: {Google Cloud Bucket URL}
```

### 4. 프로젝트 빌드 및 실행
```bash
$ ./gradlew build  
$ java -jar build/libs/{Project Name-Version}.jar
```

### - Client

### 1. Git Clone
```bash
$ https://github.com/Green-Joy/FE.git
```

### 2. .env 설정
```javascript
REACT_APP_GOOGLE_CLIENT_ID = {Google Client Id}
REACT_APP_GOOGLE_REDIRECT_URI = {Google Redirect Uri}

REACT_APP_BANNER_IMAGE1 = {Banner Image1 Src}
REACT_APP_BANNER_IMAGE2 = {Banner Image2 Src}
REACT_APP_BANNER_IMAGE3 = {Banner Image3 Src}
REACT_APP_BANNER_IMAGE4 = {Banner Image4 Src}
```

### 3. 프로젝트 빌드 및 실행
```bash
$ npm install
$ npm start
```

## 🪪 라이선스
&nbsp;This work is licensed under the MIT license.  
&nbsp;이 작업물은 MIT 라이선스에 따라 라이선스가 부여되어 있습니다.

## 🧑‍💻 프로젝트 멤버
|                                   BackEnd                                   |                                   BackEnd                                    |                                   FrontEnd                                   |                                   FrontEnd                                    |
| :--------------------------------------------------------------------------: | :---------------------------------------------------------------------------: | :--------------------------------------------------------------------------: | :--------------------------------------------------------------------------: |
| <img src="https://avatars.githubusercontent.com/u/62338444?v=4" width="100"> | <img src="https://avatars.githubusercontent.com/u/55887179?v=4" width="100"> | <img src="https://avatars.githubusercontent.com/u/113624562?v=4" width="100"> | <img src="https://avatars.githubusercontent.com/u/115474923?v=4" width="100"> |
|                    [임주혁](https://github.com/siwonhae)                     |                    [손승현](https://github.com/sonshn)                     |                      [황세연](https://github.com/SYEONIH)                      |                   [김수연](https://github.com/Osw0)                 |
