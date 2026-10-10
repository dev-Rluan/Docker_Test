# Docker_Test

Express의 간단한 HTTP 서버를 Docker 이미지로 실행하는 연습 프로젝트입니다. 루트 경로에 요청하면 `Dream Coding in Docker!` 문자열을 응답하며 서버 포트는 8080입니다.

## 로컬 실행

기존 README의 개발 환경 기록은 Node.js **16.14.2**입니다.

```bash
npm ci
node index.js
```

브라우저에서 `http://localhost:8080`에 접속합니다.

## Docker 실행

Docker를 준비한 뒤 저장소 루트에서 실행합니다. 파일 이름은 대소문자를 포함해 `DockerFile`입니다.

```bash
docker build -f DockerFile -t docker-test .
docker run --rm -p 8080:8080 docker-test
```

[DockerFile](DockerFile)은 `node:16-alpine` 이미지에서 패키지를 설치하고 `index.js`를 실행합니다.

## 코드

- [index.js](index.js): Express 라우트와 서버 시작
- [package.json](package.json): Express 의존성과 기존 프로젝트 설정

`npm test`는 기본 오류 메시지만 출력하는 자리표시자이며, 자동 테스트를 제공하지 않습니다. 이 저장소는 기존 Node 16 환경의 컨테이너 실행 기록입니다.

