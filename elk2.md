
nohup wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.0.0.tar.gz &

nohup wget https://artifacts.elastic.co/downloads/kibana/kibana-5.0.0-linux-x86_64.tar.gz &

nohup wget https://artifacts.elastic.co/downloads/logstash/logstash-5.0.0.tar.gz &




 groupadd elk
 useradd -g elk elk
 
 
 
```
network.host: 123.57.230.238
```



groupadd zhiyin

useradd zhiyin -g zhiyin -p zhiyin8080

chown -R zhiyin:zhiyin .