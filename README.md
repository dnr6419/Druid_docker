# 설치 및 실행 순서
Apache사에서 제공한 Druid의 분석 환경을 제공하기 위한 docker-compose.yml 파일입니다. 


#### 1. docker 실행
<pre> $docker-compose up  </pre>

#### 2. Java IDE debugging
Java remote debugging에서 아래와 같이 입력합니다.

<pre>-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=*:8998</pre>

# 주의 사항
#### wordpress를 가동 시킬 php 버전은 8버전이어야 합니다.
#### 위 취약점을 불법으로 악용할 시, 법적 책임을 지지 않습니다.
#### If you illegally exploit the above vulnerabilities, you will not be held liable.
#### docker 버전을 최신화 해야 합니다.

# 출처 
https://blog.wpsec.com/wordpress-xxe-in-media-library-cve-2021-29447/


