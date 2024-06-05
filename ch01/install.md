# Install

## ElasticSearch (9200)

```bash
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.17.21-linux-x86_64.tar.gz
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.17.21-linux-x86_64.tar.gz.sha512
shasum -a 512 -c elasticsearch-7.17.21-linux-x86_64.tar.gz.sha512 
tar -xzf elasticsearch-7.17.21-linux-x86_64.tar.gz
cd elasticsearch-7.17.21/ 

ln -s elasticsearch-7.17.21/elasticsearch
# installed 

# config 설정
## config/elasticsearch.yml
- network.host : 0.0.0.0

## config/jvm.options

# 실행
bin/elasticsearch

# 종료
kill -SIGTERM [pid]
```

## Kibana (5601)

```bash
curl -O https://artifacts.elastic.co/downloads/kibana/kibana-7.17.21-linux-x86_64.tar.gz
curl https://artifacts.elastic.co/downloads/kibana/kibana-7.17.21-linux-x86_64.tar.gz.sha512 | shasum -a 512 -c - 
tar -xzf kibana-7.17.21-linux-x86_64.tar.gz
cd kibana-7.17.21-linux-x86_64/ 

ln -s kibana-7.17.21-linux-x86_64 kibana

# config 설정
## config/kibana.yml

- server.host: "0.0.0.0"

# 실행
bin/kibana

# add sample data
- http://namslung.iptime.org:5601/app/home#/tutorial_directory/sampleData
```
# Cerebro (9000)

```bash
wget https://github.com/lmenezes/cerebro/releases/download/v0.9.4/cerebro-0.9.4.zip
unzip cerebro-0.9.4.zip

ln -s cerebro-0.9.4 cerebro

bundled_jvm="/home/jumo/program/elasticsearch/jdk" \
    JAVA_OPTS="--add-opens java.base/java.lang=ALL-UNNAMED --add-opens java.base/sun.net.www.protocol.file=ALL-UNNAMED" \
    bin/cerebro
```