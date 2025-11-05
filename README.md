# 🍦 Baskin Robbins 웹 애플리케이션

> 배스킨라빈스 공식 웹사이트를 클론한 프로젝트입니다. Express.js 백엔드와 MongoDB를 활용한 풀스택 웹 애플리케이션으로, 상품 목록 조회, 장바구니 기능, 주문 완료 페이지, 사용자 인증, 게시판, 게임 등 다양한 기능을 제공합니다.

---

## 📚 프로젝트 개요

이 프로젝트는 배스킨라빈스 공식 웹사이트를 클론한 웹 애플리케이션입니다. 사용자들이 아이스크림 상품을 조회하고 장바구니에 담아 주문할 수 있으며, 실시간 인증, 게시판, 게임 등 다양한 기능을 제공합니다. Express.js 기반의 RESTful API 서버와 MongoDB 데이터베이스로 구성되어 있습니다.

---

## 📘 주요 기능

### 1. 사용자 인증 (Authentication)
- **회원가입**: 아이디, 비밀번호, 이름, 이메일, 전화번호, 생년월일 등 정보 입력
- **로그인**: JWT 토큰 기반 인증 시스템
- **전화번호 인증**: 회원가입 전 SMS 인증 코드 발송 및 검증 (CoolSMS 활용)
- **비밀번호 암호화**: bcrypt를 사용한 안전한 비밀번호 저장
- **로그인 유지**: 토큰 기반 세션 관리

### 2. 상품 관리 (Ice Cream)
- **상품 목록 조회**: 아이스크림 상품 전체 목록 조회
- **상품 상세 정보**: 상품별 상세 정보 및 영양 정보 제공
- **상품 데이터 관리**: MongoDB를 통한 상품 정보 저장 및 관리

### 3. 장바구니 (Cart)
- **장바구니 조회**: 현재 사용자의 장바구니 목록 조회
- **장바구니 추가**: 상품을 장바구니에 추가
- **수량 수정**: 장바구니에 담긴 상품 수량 변경
- **장바구니 삭제**: 장바구니 항목 개별 삭제
- **선택 구매**: 장바구니에서 선택한 상품 구매
- **개별 구매**: 상세 페이지에서 바로 구매

### 4. 주문 완료 (Order Complete)
- **주문 완료 페이지**: 구매 완료 후 주문 내역 확인
- **주문 정보 표시**: 구매한 상품 및 총액 정보 표시

### 5. 게시판 (Board)
- **게시글 작성**: 제목, 내용을 포함한 게시글 작성
- **게시글 조회**: 게시글 목록 및 상세 보기
- **게시글 관리**: 게시글 수정 및 삭제

### 6. 게임 (Game)
- **미니 게임**: 배스킨라빈스 테마의 미니 게임 기능

### 7. 지도 (Map)
- **매장 위치**: 배스킨라빈스 매장 위치 정보 제공

---

## 📁 프로젝트 구조

```
Group-SemiProject/
├── app.mjs                    # Express 서버 진입점
├── config.mjs                 # 환경 변수 설정
├── package.json               # npm 패키지 설정
│
├── assets/                    # 정적 리소스
│   ├── css/                   # 스타일시트
│   │   ├── common/           # 공통 CSS 파일
│   │   └── common-ui.css      # 공통 UI 스타일
│   ├── js/                    # 클라이언트 JavaScript
│   │   ├── cart.js            # 장바구니 기능
│   │   ├── login.js           # 로그인 기능
│   │   ├── signup.js          # 회원가입 기능
│   │   ├── post.js            # 게시판 기능
│   │   ├── game.js            # 게임 기능
│   │   └── main-content.js    # 메인 페이지 기능
│   ├── imgs/                  # 이미지 리소스
│   └── libs/                  # 라이브러리
│       ├── anime/             # Anime.js 애니메이션
│       └── jquery/            # jQuery
│
├── html/                      # HTML 페이지
│   ├── main/                  # 메인 페이지
│   │   ├── index.html         # 홈 페이지
│   │   ├── game.html          # 게임 페이지
│   │   └── map.html           # 지도 페이지
│   ├── cart/                  # 장바구니 페이지
│   │   ├── cart.html          # 장바구니 목록
│   │   └── complete.html      # 주문 완료 페이지
│   ├── product/               # 상품 페이지
│   │   ├── P-010.html         # 상품 상세 페이지
│   │   └── P-020.html         # 상품 상세 페이지
│   ├── common/                # 공통 컴포넌트
│   │   ├── header.html        # 헤더
│   │   ├── footer.html        # 푸터
│   │   ├── login.html         # 로그인
│   │   ├── signup.html        # 회원가입
│   │   └── post.html          # 게시판
│   └── history/               # 주문 내역
│       └── HI-010.html        # 주문 내역 상세
│
└── src/                       # 소스 코드
    ├── controller/            # 컨트롤러 (비즈니스 로직)
    │   ├── auth.mjs           # 인증 컨트롤러
    │   ├── cart.mjs           # 장바구니 컨트롤러
    │   ├── icecream.mjs       # 상품 컨트롤러
    │   ├── post.mjs           # 게시판 컨트롤러
    │   └── game.mjs           # 게임 컨트롤러
    ├── data/                  # 데이터 접근 계층
    │   ├── auth.mjs           # 인증 데이터
    │   ├── cart.mjs           # 장바구니 데이터
    │   ├── icecream.mjs       # 상품 데이터
    │   ├── post.mjs           # 게시판 데이터
    │   └── game.mjs           # 게임 데이터
    ├── db/                    # 데이터베이스
    │   └── database.mjs       # MongoDB 연결
    ├── middleware/            # 미들웨어
    │   ├── auth.mjs           # 인증 미들웨어
    │   └── validator.mjs      # 유효성 검사 미들웨어
    ├── router/                # 라우터
    │   ├── auth.mjs           # 인증 라우터
    │   ├── cart.mjs           # 장바구니 라우터
    │   ├── icecream.mjs       # 상품 라우터
    │   ├── post.mjs           # 게시판 라우터
    │   └── game.mjs           # 게임 라우터
    └── json/                  # JSON 데이터
        └── baskin_robbins_nutrition_generated.json  # 영양 정보 데이터
```

---

## ⚙️ 실행 환경 설정

### 1️⃣ 필수 요구사항

- **Node.js**: v18 이상
- **npm**: v9 이상
- **MongoDB**: MongoDB 4.4 이상 (로컬 또는 Atlas)

### 2️⃣ 프로젝트 클론 및 의존성 설치

```bash
# 프로젝트 디렉토리로 이동
cd Group-SemiProject

# 의존성 설치
npm install
```

### 3️⃣ 데이터베이스 설정

#### MongoDB 설정

**로컬 MongoDB 사용:**

1. MongoDB 서버 실행
2. `.env` 파일에서 MongoDB URI 설정 (아래 환경 변수 설정 참고)

**MongoDB Atlas 사용 (클라우드):**

1. [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)에서 계정 생성
2. 클러스터 생성 및 데이터베이스 사용자 생성
3. 네트워크 액세스 설정 (IP 화이트리스트)
4. 연결 문자열을 `.env` 파일에 설정

### 4️⃣ 환경 변수 설정

프로젝트 루트 디렉토리에 `.env` 파일을 생성합니다:

```env
# 서버 설정
HOST_PORT=8080
NODE_ENV=development

# JWT 설정
JWT_SECRET=your-jwt-secret-key-here
JWT_EXPIRES_SEC=86400

# 비밀번호 암호화 설정
BCRYPT_SALT_ROUNDS=10

# MongoDB 설정
DB_HOST=mongodb://localhost:27017/baskinrobbins
# 또는 MongoDB Atlas 사용 시
# DB_HOST=mongodb+srv://username:password@cluster.mongodb.net/baskinrobbins

# CoolSMS 설정 (SMS 인증)
COOLSMS_API_KEY=your-coolsms-api-key
COOLSMS_API_SECRET=your-coolsms-api-secret
COOLSMS_SENDER=your-sender-phone-number
```

**환경 변수 설명:**

- `HOST_PORT`: 서버가 실행될 포트 번호 (기본값: 8080)
- `JWT_SECRET`: JWT 토큰 서명에 사용할 비밀키
- `JWT_EXPIRES_SEC`: JWT 토큰 만료 시간 (초 단위, 기본값: 86400 = 24시간)
- `BCRYPT_SALT_ROUNDS`: 비밀번호 암호화 salt 라운드 수 (기본값: 10)
- `DB_HOST`: MongoDB 연결 URI
- `COOLSMS_API_KEY`: CoolSMS API 키
- `COOLSMS_API_SECRET`: CoolSMS API 시크릿
- `COOLSMS_SENDER`: 발신자 전화번호

**CoolSMS 설정 방법:**

1. [CoolSMS](https://www.coolsms.co.kr/)에서 계정 생성
2. API 키 및 시크릿 발급
3. 발신번호 등록 (인증 필요)

### 5️⃣ 애플리케이션 실행

#### 개발 모드 실행

```bash
# 개발 모드 (nodemon 사용, 파일 변경 시 자동 재시작)
npm run dev
```

#### 프로덕션 모드 실행

```bash
# 프로덕션 모드
npm start
```

서버가 정상적으로 실행되면 다음 메시지가 표시됩니다:
```
실행중 8080
```

### 6️⃣ 서버 접속 확인

서버가 정상적으로 실행되면 다음 주소로 접속할 수 있습니다:

- **메인 페이지**: http://localhost:8080
- **API 엔드포인트**: http://localhost:8080/auth, http://localhost:8080/carts, http://localhost:8080/icecreams, http://localhost:8080/posts

**서버 상태 확인:**

```bash
# 서버 상태 확인
curl http://localhost:8080/
```

---

## 📦 주요 패키지 및 기술 스택

### 백엔드
- **Express.js**: Node.js 웹 애플리케이션 프레임워크
- **MongoDB**: NoSQL 데이터베이스
- **JWT (jsonwebtoken)**: 토큰 기반 인증
- **bcrypt**: 비밀번호 암호화
- **express-validator**: 요청 데이터 유효성 검사
- **coolsms-node-sdk**: SMS 인증 서비스
- **multer**: 파일 업로드 처리
- **cors**: CORS 설정
- **dotenv**: 환경 변수 관리

### 프론트엔드
- **HTML5**: 마크업
- **CSS3**: 스타일링
- **JavaScript (Vanilla)**: 클라이언트 사이드 로직
- **jQuery**: DOM 조작 및 이벤트 처리
- **Anime.js**: 애니메이션 효과
- **Swiper**: 슬라이더 기능

---

## 💡 핵심 개념

### JWT (JSON Web Token)
사용자 인증 정보를 안전하게 전달하기 위한 토큰 기반 인증 방식입니다. 서버에서 토큰을 발급하고, 클라이언트는 이후 요청 시 토큰을 포함하여 인증된 사용자임을 증명합니다.

### MongoDB
문서 기반 NoSQL 데이터베이스로, 유연한 스키마 구조를 제공합니다. 사용자 정보, 상품 정보, 장바구니, 게시글 등 모든 데이터를 MongoDB에 저장합니다.

### CoolSMS
SMS 인증 서비스를 제공하는 API입니다. 회원가입 시 전화번호 인증을 위해 사용됩니다.

### RESTful API
HTTP 메서드(GET, POST, PUT, PATCH, DELETE)를 사용하여 리소스를 관리하는 API 설계 방식입니다.

---

## 🔗 주요 API 엔드포인트

### 인증 (Authentication)
- `POST /auth/signup` - 회원가입
- `POST /auth/login` - 로그인
- `GET /auth/me` - 현재 사용자 정보 조회 (인증 필요)
- `POST /auth/send-verification` - SMS 인증번호 발송
- `POST /auth/verify-code` - SMS 인증번호 확인

### 상품 (Ice Cream)
- `POST /icecreams` - 상품 생성 (관리자)

### 장바구니 (Cart)
- `GET /carts` - 장바구니 목록 조회 (인증 필요)
- `POST /carts` - 장바구니에 상품 추가 (인증 필요)
- `PATCH /carts/:iceidx` - 장바구니 수량 수정 (인증 필요)
- `DELETE /carts/:iceidx` - 장바구니 항목 삭제 (인증 필요)
- `POST /carts/purchase` - 장바구니 선택 구매 (인증 필요)
- `POST /carts/purchase/:iceidx` - 상품 개별 구매 (인증 필요)

### 게시판 (Board)
- `GET /posts` - 게시글 목록 조회 (인증 필요)
- `GET /posts/:id` - 게시글 상세 조회 (인증 필요)
- `POST /posts` - 게시글 작성 (인증 필요)
- `PUT /posts/:id` - 게시글 수정 (인증 필요)
- `DELETE /posts/:id` - 게시글 삭제 (인증 필요)

### 게임 (Game)
- `GET /game` - 게임 관련 엔드포인트

---

## 🔗 참고 자료

### Express.js
- [Express 공식 문서](https://expressjs.com/)

### MongoDB
- [MongoDB 공식 문서](https://www.mongodb.com/docs/)
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)

### JWT
- [JWT 공식 문서](https://jwt.io/)

### CoolSMS
- [CoolSMS 공식 문서](https://www.coolsms.co.kr/)

---

## 📝 라이선스

이 프로젝트는 학습 목적으로 작성되었습니다.

---

## 👤 프로젝트 참여자
**오지환**
- **아이디어, 디자인, 퍼블리싱**: 프로젝트의 전체적인 아이디어 기획, UI/UX 디자인, 퍼블리싱을 담당했습니다.
- **개발**: 상품 목록, 장바구니, 완료 페이지 기능 개발을 담당했습니다.

---

## ⚠️ 주의사항

1. **환경 변수 보안**: `.env` 파일에 포함된 민감한 정보는 절대 Git에 커밋하지 마세요. `.gitignore`에 추가되어 있는지 확인하세요.
2. **데이터베이스 연결**: MongoDB 서버가 실행 중인지 확인하세요.
3. **포트 충돌**: 다른 애플리케이션이 사용 중인 포트(8080)가 있으면 `.env` 파일에서 `HOST_PORT`를 변경하세요.
4. **SMS 인증 설정**: SMS 인증 기능을 사용하려면 CoolSMS 계정 및 API 키가 필요합니다.
5. **JWT 시크릿**: 프로덕션 환경에서는 반드시 강력한 JWT 시크릿 키를 사용하세요.
6. **CORS 설정**: 프로덕션 환경에서는 CORS 설정을 적절히 제한하세요.

---

## 🚀 빠른 시작 가이드

1. **프로젝트 클론**
   ```bash
   git clone <repository-url>
   cd Group-SemiProject
   ```

2. **의존성 설치**
   ```bash
   npm install
   ```

3. **환경 변수 설정**
   - 프로젝트 루트에 `.env` 파일 생성
   - 위의 "환경 변수 설정" 섹션을 참고하여 필요한 값 입력

4. **MongoDB 설정**
   - 로컬 MongoDB 실행 또는 MongoDB Atlas 연결 설정
   - `.env` 파일에 `DB_HOST` 설정

5. **서버 실행**
   ```bash
   # 개발 모드
   npm run dev
   
   # 또는 프로덕션 모드
   npm start
   ```

6. **브라우저에서 접속**
   - 메인 페이지: http://localhost:8080

---

## 📞 문의

프로젝트 관련 문의사항이 있으시면 이슈를 등록해 주세요.
