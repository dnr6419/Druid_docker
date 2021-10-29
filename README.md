# 설치 및 실행 순서
Apache사에서 제공한 Druid에 대한 분석 환경 구축을 위한 docker-compose.yml 파일입니다. 
8998번 포트를 이용하여 Remote Debugging 기능을 추가하였습니다.
너무 많은 메모리 할당으로 인한 실행 딜레이를 줄였습니다. 

#### 1. docker 실행
<pre> $docker-compose up  </pre>

#### 2. Java IDE debugging
Java remote debugging에서 아래와 같이 입력합니다.
아래 이미지는 IntelliJ IDEA 개발환경을 사용하였습니다.

<pre>-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=*:8998</pre>
![20211029120310](https://user-images.githubusercontent.com/43310843/139366944-93010fec-3fa9-47d6-a1a4-c51d430c4bee.png)

# 출처 
https://github.com/apache/druid/tree/master/distribution/docker


