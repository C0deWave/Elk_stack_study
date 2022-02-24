# ELK Stack 다운 및 실행하기

### 목표: 
    
    Elastic Search, LogStash, Kibana를 다운 및 실행해 본다.

---

### 환경: 

    OS: CentOS7
    ram: 2GB
    설치경로: /elk

---

### Elastic Search 다운 받기

엘라스틱 서치의 경우 [엘라스틱 공식 사이트](https://www.elastic.co/kr/elasticsearch/)에서 다운 받을 수 있다.

리눅스 X86_64 버전을 선택한다.

그후 다운로드 링크를 복사한 후 터미널에 해당 명령어를 작성해서 tar 파일을 다운 받는다.

    wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-8.0.0-linux-x86_64.tar.gz

시간이 지남에 따라 링크의 내용이 다를 수 있다.

마찬가지로 logstash, kibana 다운받아 본다.

logstash:

    wget https://artifacts.elastic.co/downloads/logstash/logstash-8.0.0-linux-x86_64.tar.gz

kibana:

    wget https://artifacts.elastic.co/downloads/kibana/kibana-8.0.0-linux-x86_64.tar.gz

---

### 압축 해제 하기

아래의 명령어를 이용해서 압축을 해제합니다.

    tar -zxvf [압축파일]

---

## Elastic Search 실행하기

    vi ./elasticsearch-8.0.0/config/elasticsearch.yml
    network.host: 0.0.0.0
    http.port: 9200

    sudo vi /etc/security/limits.conf
    jmjang soft nofile 65536
    jmjang hard nofile 65536
    jmjang soft nproc 65536
    jmjang hard nproc 65536

    sysctl -w vm.max_map_count=262144

    ./elasticsearch-8.0.0/bin/elasticsearch

확인을 위해서 해당 호스트의 아이피:9091로 들어가 본다.

---

## Logstash 실행하기

---

## Kibana 실행하기



