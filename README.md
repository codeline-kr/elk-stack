# Elastic stack (ELK) on Docker

## 설정

.env 파일 ELASTIC_PASSWORD, LOGSTASH_INTERNAL_PASSWORD, KIBANA_SYSTEM_PASSWORD 수정

## 실행

docker-compose build
docker-compose up -d

## 접속

id : elastic
pw : .env 에서 설정한 비밀번호
엘라스틱서치 : http://localhost:9200
kabana : http://localhost:5601

외부에서 접속할려면 방화벽 오픈해야 됨
ubuntu

```bash
sudo ufw allow 9200
sudo ufw allow 5601
```

## 삭제

docker-compose down -v

## 로그 보기

docker-compose logs -f elasticsearch
docker-compose logs -f logstash
docker-compose logs -f kibana

## 쉘 접속

docker-compose exec elasticsearch bash
docker-compose exec logstash bash
docker-compose exec kibana bash

## logstash 파이프 라인수정

./logstassh/logstash.conf 파일 수정

docker-compose stop logstash
docker-compose start logstash
