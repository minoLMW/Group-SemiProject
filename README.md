# 🍦 Baskin Robbins 웹 애플리케이션

> 배스킨라빈스(Baskin Robbins) 클론 웹 애플리케이션 프로젝트입니다. Express.js와 MongoDB를 활용한 풀스택 웹 애플리케이션으로, 사용자 인증, 상품 관리, 장바구니, 게임, 매장 찾기 등 다양한 기능을 제공합니다.

---

## 📚 프로젝트 개요

이 프로젝트는 배스킨라빈스 웹사이트를 클론한 그룹 세미프로젝트입니다. Express.js 기반의 백엔드 서버와 MongoDB 데이터베이스를 사용하며, JWT 인증, 상품 관리, 장바구니, 게임, 매장 찾기, 게시판 등 다양한 기능을 구현했습니다.

---

## 📘 주요 기능

### 1. 사용자 인증 (Authentication)
- **회원가입**: 아이디, 비밀번호, 이름, 이메일, 전화번호, 생년월일 입력
- **로그인**: JWT 토큰 기반 인증 시스템
- **SMS 인증**: CoolSMS를 활용한 전화번호 인증번호 발송 및 검증
- **비밀번호 암호화**: bcrypt를 사용한 안전한 비밀번호 저장
- **로그인 유지**: 토큰 기반 세션 관리

### 2. 상품 관리 (Ice Cream Products)
- **아이스크림 정보 조회**: 다양한 아이스크림 상품 정보 제공
- **영양 정보**: JSON 데이터 기반 영양 정보 제공
- **상품 상세 페이지**: 개별 아이스크림 상세 정보 조회

### 3. 장바구니 (Shopping Cart)
- **장바구니 추가**: 선택한 상품을 장바구니에 추가
- **장바구니 조회**: 사용자별 장바구니 목록 확인
- **주문 완료**: 장바구니 상품 구매 처리

### 4. 게임 (Game)
- **Baskin Minoo's Card Game**: 배스킨라빈스 캐릭터를 활용한 카드 게임
- **게임 결과 저장**: 게임 점수 및 결과 기록

### 5. 매장 찾기 (Store Locator)
- **매장 검색**: 지도 기반 매장 위치 검색
- **매장 정보 조회**: 매장별 상세 정보 제공

### 6. 게시판 (Board)
- **게시글 작성**: 사용자 게시글 작성 및 등록
- **게시글 조회**: 게시글 목록 및 상세 보기
- **게시글 관리**: 게시글 수정 및 삭제

---

## 📁 프로젝트 구조

```
05. Group-SemiProject/
├── app.mjs                    # Express 애플리케이션 진입점
├── config.mjs                 # 환경 변수 설정 관리
├── package.json               # 프로젝트 의존성 및 스크립트
│
├── assets/                    # 정적 리소스
│   ├── css/                   # 스타일시트
│   │   ├── common/            # 공통 CSS 파일
│   │   │   ├── cart.css
│   │   │   ├── footer.css
│   │   │   ├── game.css
│   │   │   ├── header.css
│   │   │   ├── history.css
│   │   │   ├── layout.css
│   │   │   ├── login-signup.css
│   │   │   ├── main-content.css
│   │   │   ├── map.css
│   │   │   ├── post.css
│   │   │   ├── product.css
│   │   │   └── reset.css
│   │   └── common-ui.css
│   ├── js/                    # JavaScript 파일
│   │   ├── cart.js
│   │   ├── common-ui.js
│   │   ├── footer.js
│   │   ├── game.js
│   │   ├── header.js
│   │   ├── login.js
│   │   ├── main-content.js
│   │   ├── map.js
│   │   ├── post.js
│   │   └── signup.js
│   ├── imgs/                  # 이미지 파일
│   └── libs/                  # 외부 라이브러리
│       ├── anime/             # 애니메이션 라이브러리
│       └── jquery/            # jQuery 라이브러리
│
├── html/                      # HTML 페이지
│   ├── cart/                  # 장바구니 페이지
│   ├── common/                # 공통 컴포넌트
│   │   ├── footer.html
│   │   ├── header.html
│   │   ├── login.html
│   │   ├── signup.html
│   │   └── post.html
│   ├── history/               # 히스토리 페이지
│   ├── main/                  # 메인 페이지
│   │   ├── index.html
│   │   ├── game.html
│   │   └── map.html
│   └── product/               # 상품 페이지
│       ├── P-010.html
│       └── P-020.html
│
└── src/                       # 소스 코드
    ├── controller/            # 컨트롤러 (비즈니스 로직)
    │   ├── auth.mjs
    │   ├── cart.mjs
    │   ├── game.mjs
    │   ├── icecream.mjs
    │   └── post.mjs
    ├── data/                  # 데이터 레이어
    │   ├── auth.mjs
    │   ├── cart.mjs
    │   ├── game.mjs
    │   ├── icecream.mjs
    │   └── post.mjs
    ├── db/                    # 데이터베이스 연결
    │   └── database.mjs
    ├── json/                  # JSON 데이터 파일
    │   └── baskin_robbins_nutrition_generated.json
    ├── middleware/            # 미들웨어
    │   ├── auth.mjs           # 인증 미들웨어
    │   └── validator.mjs      # 유효성 검사 미들웨어
    └── router/                # 라우터
        ├── auth.mjs
        ├── cart.mjs
        ├── game.mjs
        ├── icecream.mjs
        └── post.mjs
```

---

## ⚙️ 실행 환경 설정

### 1️⃣ 필수 요구사항

- **Node.js**: v18 이상
- **MongoDB**: MongoDB 서버 (로컬 또는 클라우드)
- **npm**: Node.js 패키지 관리자

### 2️⃣ 프로젝트 클론 및 의존성 설치

```bash
# 프로젝트 디렉토리로 이동
cd "05. Group-SemiProject"

# 의존성 패키지 설치
npm install
```

### 3️⃣ 환경 변수 설정

프로젝트 루트 디렉토리에 `.env` 파일을 생성하고 다음 환경 변수를 설정합니다:

```env
# JWT 설정
JWT_SECRET=your-jwt-secret-key-here
JWT_EXPIRES_SEC=86400

# bcrypt 설정
BCRYPT_SALT_ROUNDS=10

# 서버 포트 설정
HOST_PORT=8080

# MongoDB 연결 설정
DB_HOST=mongodb://localhost:27017
# 또는 MongoDB Atlas 사용 시
# DB_HOST=mongodb+srv://username:password@cluster.mongodb.net/database

# CoolSMS 설정 (SMS 인증용)
COOLSMS_API_KEY=your-coolsms-api-key
COOLSMS_API_SECRET=your-coolsms-api-secret
COOLSMS_SENDER=your-sender-phone-number
```

#### 환경 변수 설명

- **JWT_SECRET**: JWT 토큰 서명에 사용할 비밀키 (임의의 긴 문자열 사용)
- **JWT_EXPIRES_SEC**: JWT 토큰 만료 시간 (초 단위, 기본값: 86400 = 24시간)
- **BCRYPT_SALT_ROUNDS**: bcrypt 암호화 솔트 라운드 수 (기본값: 10)
- **HOST_PORT**: Express 서버가 실행될 포트 번호 (기본값: 8080)
- **DB_HOST**: MongoDB 연결 문자열
- **COOLSMS_API_KEY**: CoolSMS API 키
- **COOLSMS_API_SECRET**: CoolSMS API 시크릿
- **COOLSMS_SENDER**: SMS 발신 번호 (CoolSMS에 등록된 번호)

### 4️⃣ MongoDB 설정

#### 로컬 MongoDB 사용

1. MongoDB를 로컬에 설치하고 실행
2. `.env` 파일에서 `DB_HOST=mongodb://localhost:27017`로 설정

#### MongoDB Atlas 사용 (클라우드)

1. [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)에서 계정 생성
2. 클러스터 생성 및 데이터베이스 사용자 생성
3. 네트워크 액세스 설정 (IP 화이트리스트)
4. 연결 문자열 복사하여 `.env` 파일의 `DB_HOST`에 설정

### 5️⃣ 애플리케이션 실행

#### 개발 모드 (자동 재시작)

```bash
npm run dev
```

`nodemon`을 사용하여 파일 변경 시 자동으로 서버가 재시작됩니다.

#### 프로덕션 모드

```bash
npm start
```

또는

```bash
node app.mjs
```

### 6️⃣ 서버 접속 확인

서버가 정상적으로 실행되면 다음 메시지가 출력됩니다:

```
실행중 8080
```

브라우저에서 다음 주소로 접속하여 확인할 수 있습니다:

- **메인 페이지**: http://localhost:8080/
- **API 엔드포인트**: http://localhost:8080/auth, http://localhost:8080/icecreams 등

---

## 📦 주요 패키지

### 백엔드 프레임워크
- **express**: 웹 애플리케이션 프레임워크
- **express-validator**: 요청 데이터 유효성 검사

### 데이터베이스
- **mongodb**: MongoDB 공식 드라이버

### 인증 및 보안
- **jsonwebtoken**: JWT 토큰 생성 및 검증
- **bcrypt**: 비밀번호 해싱 및 암호화

### 파일 처리
- **multer**: 파일 업로드 처리

### 유틸리티
- **dotenv**: 환경 변수 관리
- **cors**: Cross-Origin Resource Sharing 처리
- **coolsms-node-sdk**: CoolSMS SMS 발송 서비스

### 개발 도구
- **nodemon**: 개발 시 자동 재시작 도구

---

## 💡 핵심 개념

### JWT (JSON Web Token)
사용자 인증 정보를 안전하게 전달하기 위한 토큰 기반 인증 방식입니다. 서버에서 토큰을 발급하고, 클라이언트는 이후 요청 시 토큰을 포함하여 인증된 사용자임을 증명합니다.

### bcrypt
비밀번호를 안전하게 저장하기 위한 해싱 알고리즘입니다. 솔트(salt)를 사용하여 같은 비밀번호라도 다른 해시값을 생성하여 보안성을 높입니다.

### MongoDB
NoSQL 문서 기반 데이터베이스로, 유연한 스키마 구조를 제공합니다. JSON 형태의 문서를 저장하고 조회할 수 있습니다.

### Express.js
Node.js 기반의 웹 애플리케이션 프레임워크로, 간단하고 빠른 API 서버 구축을 가능하게 합니다.

### Middleware
Express에서 요청과 응답 사이에 실행되는 중간 함수입니다. 인증, 유효성 검사, 로깅 등의 기능을 처리합니다.

### RESTful API
HTTP 메서드(GET, POST, PUT, DELETE)를 사용하여 리소스를 관리하는 API 설계 방식입니다.

---

## 🔗 주요 API 엔드포인트

### 인증 (Authentication)
- `POST /auth/signup` - 회원가입
- `POST /auth/login` - 로그인
- `GET /auth/me` - 현재 사용자 정보 조회 (인증 필요)
- `POST /auth/send-verification` - SMS 인증번호 발송
- `POST /auth/verify-code` - SMS 인증번호 확인

### 상품 (Ice Cream)
- `POST /icecreams` - 아이스크림 정보 생성

### 장바구니 (Cart)
- `GET /carts` - 장바구니 조회
- `POST /carts` - 장바구니에 상품 추가
- `DELETE /carts/:id` - 장바구니에서 상품 제거

### 게시판 (Post)
- `GET /posts` - 게시글 목록 조회
- `GET /posts/:id` - 게시글 상세 조회
- `POST /posts` - 게시글 작성
- `PUT /posts/:id` - 게시글 수정
- `DELETE /posts/:id` - 게시글 삭제

### 게임 (Game)
- `POST /game` - 게임 결과 저장

---

## 🔗 참고 자료

### Express.js
- [Express 공식 문서](https://expressjs.com/)
- [Express 가이드](https://expressjs.com/en/guide/routing.html)

### MongoDB
- [MongoDB 공식 문서](https://www.mongodb.com/docs/)
- [MongoDB Node.js 드라이버](https://www.mongodb.com/docs/drivers/node/current/)

### JWT
- [JWT 공식 사이트](https://jwt.io/)
- [jsonwebtoken npm 패키지](https://www.npmjs.com/package/jsonwebtoken)

### CoolSMS
- [CoolSMS 공식 문서](https://www.coolsms.co.kr/)
- [CoolSMS Node.js SDK](https://www.npmjs.com/package/coolsms-node-sdk)

### 기타
- [Node.js 공식 문서](https://nodejs.org/)
- [bcrypt npm 패키지](https://www.npmjs.com/package/bcrypt)

---

## 📝 라이선스

이 프로젝트는 학습 목적으로 작성되었습니다.

---

## ⚠️ 주의사항

1. **환경 변수 보안**: `.env` 파일은 절대 Git에 커밋하지 마세요. `.gitignore`에 추가되어 있는지 확인하세요.
2. **MongoDB 연결**: MongoDB 서버가 실행 중인지 확인하세요.
3. **포트 충돌**: 다른 애플리케이션이 8080 포트를 사용 중이면 `.env` 파일에서 `HOST_PORT`를 변경하세요.
4. **CoolSMS 설정**: SMS 인증 기능을 사용하려면 CoolSMS 계정 및 API 키가 필요합니다.
