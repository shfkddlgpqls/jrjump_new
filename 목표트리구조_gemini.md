jrjump-boot/
├── build.gradle                         # 의존성 관리 (Gradle)
├── Dockerfile                           # 배포 설정
├── src/
│   ├── main/
│   │   ├── java/com/hackers/jrjump/
│   │   │   ├── JrjumpApplication.java   # [Main] 앱 실행 파일
│   │   │   │
│   │   │   ├── global/                  # [공통 모듈]
│   │   │   │   ├── config/              # Security, MVC, JPA 설정
│   │   │   │   ├── auth/                # 로그인/권한 처리
│   │   │   │   ├── error/               # 예외 처리 핸들러
│   │   │   │   └── util/                # 공통 유틸리티
│   │   │   │
│   │   │   └── domain/                  # [핵심 비즈니스 기능]
│   │   │       ├── member/              # 회원 (로그인, 마이페이지)
│   │   │       │   ├── controller/      # MemberController
│   │   │       │   ├── service/         # MemberService
│   │   │       │   ├── repository/      # MemberRepository
│   │   │       │   ├── entity/          # Member Entity
│   │   │       │   └── dto/             # LoginRequest, MemberResponse
│   │   │       ├── lecture/             # 인강 (강의목록, 플레이어)
│   │   │       │   ├── controller/
│   │   │       │   ├── service/
│   │   │       │   ├── repository/
│   │   │       │   ├── entity/
│   │   │       │   └── dto/
│   │   │       ├── academy/             # 학원 (강사, 캠퍼스)
│   │   │       │   ├── controller/
│   │   │       │   ├── service/
│   │   │       │   ├── repository/
│   │   │       │   ├── entity/
│   │   │       │   └── dto/
│   │   │       ├── board/               # 게시판 (공지, Q&A)
│   │   │       │   ├── controller/
│   │   │       │   ├── service/
│   │   │       │   ├── repository/
│   │   │       │   ├── entity/
│   │   │       │   └── dto/
│   │   │       ├── exam/                # 시험 (모의고사, 보카)
│   │   │       │   ├── controller/
│   │   │       │   ├── service/
│   │   │       │   ├── repository/
│   │   │       │   ├── entity/
│   │   │       │   └── dto/
│   │   │       ├── event/               # 이벤트 (쿠폰, 프로모션)
│   │   │       │   ├── controller/
│   │   │       │   ├── service/
│   │   │       │   ├── repository/
│   │   │       │   ├── entity/
│   │   │       │   └── dto/
│   │   │       ├── payment/             # 결제 (주문, PG연동)
│   │   │       │   ├── controller/
│   │   │       │   ├── service/
│   │   │       │   ├── repository/
│   │   │       │   ├── entity/
│   │   │       │   └── dto/
│   │   │       └── admin/               # 관리자 (백오피스 기능)
│   │   │           ├── controller/
│   │   │           ├── service/
│   │   │           ├── repository/
│   │   │           ├── entity/
│   │   │           └── dto/
│   │   │
│   │   └── resources/
│   │       ├── application.yml          # [설정] DB, 포트 등 환경변수
│   │       ├── static/                  # [정적파일] css, js, images
│   │       └── templates/               # [View] HTML (Thymeleaf)
│   │           ├── layout/              # 헤더/푸터 공통 레이아웃
│   │           ├── member/              # 회원 화면
│   │           ├── lecture/             # 강의 화면
│   │           ├── academy/             # 학원 화면
│   │           ├── board/               # 게시판 화면
│   │           ├── exam/                # 시험 화면
│   │           ├── event/               # 이벤트 화면
│   │           ├── payment/             # 결제 화면
│   │           └── admin/               # 관리자 화면
│   │
│   └── test/
│       ├── java/com/hackers/jrjump/
│       │   ├── JrjumpApplicationTests.java  # 컨텍스트 로드 테스트
│       │   │
│       │   ├── global/                      # [공통 모듈 테스트]
│       │   │   ├── config/                  # 설정 테스트
│       │   │   └── util/                    # 유틸리티 단위 테스트
│       │   │
│       │   └── domain/                      # [기능별 테스트] (main과 1:1 매칭)
│       │       ├── member/
│       │       │   ├── controller/          # API/View 컨트롤러 테스트 (@WebMvcTest)
│       │       │   ├── service/             # 비즈니스 로직 단위 테스트 (@ExtendWith)
│       │       │   └── repository/          # DB 쿼리 테스트 (@DataJpaTest)
│       │       ├── lecture/
│       │       │   ├── controller/
│       │       │   ├── service/
│       │       │   └── repository/
│       │       ├── academy/
│       │       │   ├── controller/
│       │       │   ├── service/
│       │       │   └── repository/
│       │       ├── board/
│       │       │   ├── controller/
│       │       │   ├── service/
│       │       │   └── repository/
│       │       ├── exam/
│       │       │   ├── controller/
│       │       │   ├── service/
│       │       │   └── repository/
│       │       ├── event/
│       │       │   ├── controller/
│       │       │   ├── service/
│       │       │   └── repository/
│       │       ├── payment/
│       │       │   ├── controller/
│       │       │   ├── service/
│       │       │   └── repository/
│       │       └── admin/
│       │           ├── controller/
│       │           ├── service/
│       │           └── repository/
│       │
│       └── resources/                       # [테스트 전용 리소스]
│           ├── application-test.yml         # 테스트 환경 설정 (H2 DB 등)
│           └── data/                        # 테스트용 더미 데이터 (선택 사항)
│               └── test-data.sql
