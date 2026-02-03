# TODO - 프로젝트 작업 목록

## Feature 1: 사용자 인증 (로그인/회원가입)

### DB (Database)
- [ ] User 테이블 모델 생성
  - [ ] id (Primary Key)
  - [ ] username (Unique)
  - [ ] email (Unique)
  - [ ] password_hash
  - [ ] created_at
  - [ ] updated_at
- [ ] User CRUD 함수 작성
  - [ ] create_user (회원가입용)
  - [ ] get_user_by_username
  - [ ] get_user_by_email
  - [ ] verify_password

### BE (Backend)
- [ ] 인증 관련 스키마 정의
  - [ ] UserCreate (회원가입 요청)
  - [ ] UserLogin (로그인 요청)
  - [ ] UserResponse (사용자 정보 응답)
  - [ ] Token (토큰 응답)
- [ ] 패스워드 해싱 유틸리티
  - [ ] hash_password 함수
  - [ ] verify_password 함수
- [ ] JWT 토큰 관리
  - [ ] create_access_token 함수
  - [ ] verify_token 함수
  - [ ] get_current_user 의존성
- [ ] 인증 API 엔드포인트
  - [ ] POST /api/auth/register (회원가입)
  - [ ] POST /api/auth/login (로그인)
  - [ ] GET /api/auth/me (현재 사용자 정보)

### FE (Frontend)
- [ ] 인증 관련 타입 정의
  - [ ] User 인터페이스
  - [ ] LoginCredentials 인터페이스
  - [ ] RegisterData 인터페이스
- [ ] API 통신 함수
  - [ ] register(data) - 회원가입
  - [ ] login(credentials) - 로그인
  - [ ] getCurrentUser() - 현재 사용자 조회
  - [ ] logout() - 로그아웃
- [ ] 회원가입 페이지 (/register)
  - [ ] 회원가입 폼 컴포넌트
  - [ ] 입력 검증 (이메일, 비밀번호 형식)
  - [ ] 에러 처리 및 메시지 표시
- [ ] 로그인 페이지 (/login)
  - [ ] 로그인 폼 컴포넌트
  - [ ] 입력 검증
  - [ ] 에러 처리 및 메시지 표시
- [ ] 인증 상태 관리
  - [ ] 토큰 저장 (localStorage)
  - [ ] 인증 상태 Context/Provider
  - [ ] Protected Route 구현
- [ ] 네비게이션 바 업데이트
  - [ ] 로그인/회원가입 링크
  - [ ] 로그아웃 버튼
  - [ ] 사용자 정보 표시

---

## 작업 순서 (권장)
1. **DB 작업** (db-agent)
   - User 모델 및 CRUD 함수 생성
2. **BE 작업** (be-agent)
   - 스키마 정의 → 유틸리티 함수 → API 엔드포인트
3. **FE 작업** (fe-agent)
   - 타입 정의 → API 함수 → 페이지 및 컴포넌트

---

## 참고사항
- 비밀번호는 반드시 해싱하여 저장 (bcrypt 또는 passlib 사용)
- JWT 토큰은 환경변수로 SECRET_KEY 관리
- 프론트엔드는 토큰을 secure하게 저장 (httpOnly 쿠키 또는 localStorage)
- CORS 설정 확인 필요
