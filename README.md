[HTTPS] - endpoints 간 data를 endpoints 끼리 약속한 secret key 로 encrypted해 전달

- Self Signed SSL Certificate (SSC)
- keytool 로 인증서 생성 


---
## Command to create self signed SSL Certificate JKS

- cmd 관리자 권한 실행
- jdk keytoo / bin 이동

keytool -genkey -alias https-example -storetype JKS -keyalg RSA -keysize 2048 -validity 365 -keystore https-example.jks

- 비밀번호 입력
- 이름,국가,도시 ..입력 후 y
- 키 비밀번호 같은것으로 쓸건지 enter
- .jks 프로젝트 /resource로 이동
- https://localhost:8443/hello - returns 'hello world'

##
Warning:
JKS 키 저장소는 고유 형식을 사용합니다. 
"keytool -importkeystore -srckeystore https-example.jks -destkeystore https-example.jks -deststoretype pkcs12"를 사용하는 산업 표준 형식인 PKCS12로 이전하는 것이 좋습니다.

##
-> keytool -genkey -alias bootsecurity -storetype PKCS12 -keyalg RSA -keysize 2048 -keystore bootsecurity.p12 -validity 3650
