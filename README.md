# 설치 및 실행 순서
Apache사에서 제공한 Druid에 대한 분석 환경 구축을 위한 docker-compose.yml 파일입니다. 
8998번 포트를 이용하여 Remote Debugging 기능을 추가하였습니다.
너무 많은 메모리 할당으로 인한 실행 딜레이를 줄였습니다. 

version : 0.20.0 // 이 버전은 docker-compose.yml 파일의 버전을 수정하여 최신 버전으로 환경 구축을 진행할 수 있습니다.
CVE-2021-25646, CVE-2021-36749 취약점이 발생하는 환경이며 해당 취약점에 대한 poc는 poc.md를 통해 확인할 수 있습니다. 

#### 1. docker 실행
<pre> $docker-compose up  </pre>

#### 2. Java IDE debugging
Java remote debugging에서 아래와 같이 입력합니다.
아래 이미지는 IntelliJ IDEA 개발환경을 사용하였습니다.

<pre>-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=*:8998</pre>
![20211029120310](https://user-images.githubusercontent.com/43310843/139366944-93010fec-3fa9-47d6-a1a4-c51d430c4bee.png)

# 출처 
https://github.com/apache/druid/tree/master/distribution/docker


