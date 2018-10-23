# whois
후이즈 도메인 API 매뉴얼

	파일 목록 및 설명


# 기본 주소

/WhoisApi/
예 /WhoisApi/check

check		도메인 등록가능여부 확인

host_info	호스트 조회

host_manage	호스트 등록/수정/삭제

info		도메인 정보조회

register	도메인 등록

renew		도메인 연장

renew_check	도메인 연장가능여부 확인

transfer	기관이전 신청

update		도메인 기본정보 수정

update_ns	도메인 네임서버 수정

reseller_info	리셀러 정보조회(보유 예치금 조회)


# 테스트 진행 방법
1. 테스트 진행
- 각 파일별로 테스트를 진행후 사이트 개발을 진행 합니다.
- 각각의 파일에 input / output 이 설명되어 있습니다.

2.	테스트 완료 후 “\vendor\whois\src\Whois\Domain\WhoisTrait.php” 파일의 실행 환경을 TEST 에서 REAL로 변경합니다.
- REAL 로 변경 후에는 실제로 도메인의 등록이 되므로 과금이 발생합니다.

3. log 위치는 핸들러와 한 묶음이 되어야 하는 규칙에 의해  “\vendor\whois\log ”  에 위치
- 파일 위치 변경 하고 싶으면 WhoisTrait 파일 확인

# api document
postman 
https://documenter.getpostman.com/view/4808834/RWgwRFVb
 
# 응답코드
기본적인 EPP 통신 코드를 기본으로 하고 있으며 다음과 같습니다.

CODE	MESSAGE

1000	Command completed successfully
성공적으로 완료 되었습니다.

1001	Command completed successfully; action pending
성공적으로 완료 되었습니다. 그러나 다른 조치가 필요 합니다.

2000	Unknown command
잘못된 command입니다.

2001	Command syntax error
Command 문법이 잘못 되었습니다.

2002	Command use error
해당 command 를 이곳에 사용하면 안됩니다.

2003	Required parameter missing
필수값이 없습니다.

2004	Parameter value range error
파라미터 값이 허용되는 값을 초과합니다.

2005	Parameter value syntax error
파라미터 값이 잘못되었습니다.

2104	Billing failure
예치금이 부족합니다.

2105	Object is not eligible for renewal
연장을 할 수 없습니다.

2106	Object is not eligible for transfer
기관이전을 할 수 없습니다.

2200	Authentication error
아이디/암호인증 실패

2202	Invalid authorization information
허용되지 않는곳에서 접속 하였습니다.

2300	Object pending transfer
기관이전 진행중입니다.

2301	Object not pending transfer
기관이전 진행중이 아닙니다.

2302	Object exists
도메인/컨택/호스트가 존재합니다.

2303	Object does not exist
도메인/컨택/호스트가 존재하지 않습니다.

2306	Parameter value policy error
파라미터 사용 규칙에 위반됩니다.

2400	Command failed
Command가 실패되었습니다.


# License
GPLv2
Copyright (C) 2018 <bastcode>