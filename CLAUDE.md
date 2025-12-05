# jrjump-new

## WHAT (프로젝트 구조)

PHP 웹 애플리케이션을 Spring Boot로 마이그레이션하는 프로젝트.

| 구분 | 내용 |
|------|------|
| 원본 | `/Volumes/web/jrjump` (PHP) |
| 대상 | `/Volumes/web/jrjump-new` (Spring Boot) |
| 스택 | Java 21, Spring Boot 3.x, Thymeleaf, JPA, MySQL |

## WHY (프로젝트 목적)

PHP 코드를 Spring Boot로 **기능적 100% 동일하게 이식**한다.
리팩토링이나 개선 없이 원본 동작을 그대로 재현하는 것이 목표.

## HOW (작업 방법)

### 핵심 원칙

1. **추측 금지**: 원본 의도가 100% 확실할 때만 변경. 추측 구현 절대 금지.
2. **누락 금지**: HTML 속성, 공백, 주석, 예외 처리 등 모든 요소를 빠짐없이 이식.
3. **인코딩 확인**: 원본 파일 읽기 전 반드시 인코딩 체크.

### 인코딩 처리

원본 PHP 파일은 EUC-KR 인코딩일 수 있음.

```bash
# 인코딩 확인
file -I <파일경로>

# EUC-KR → UTF-8 변환
iconv -f EUC-KR -t UTF-8 <파일경로>
```
