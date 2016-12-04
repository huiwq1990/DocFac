


### 测试logstash

./logstash -e 'input { stdin { } } output { stdout {} }'

./logstash -e '
input {
	tcp {
		host => "123.57.230.238"
		port => 5000
		mode => "server"
		tags => ["tags"]
		codec => "json_lines"
    }
}
output { 
	stdout {
		codec => rubydebug
	}
}
'


./logstash -f simple.conf --debug


vim /etc/security/limits.conf

```

* soft nproc 65536 
* hard nproc 65536 
* soft nofile 65536 
* hard nofile 65536

```

sysctl -w vm.max_map_count=262144





```
[program:elasticsearch]
directory=/opt/program/elasticsearch-5.0.0/bin ; 执行 command 之前，先切换到工作目录
command=./elasticsearch
numprocs=1
autostart=true
autorestart=true
use=zhiyin ; 使用 oxygen 用户来启动该进程
redirect_stderr = true  ; 把 stderr 重定向到 stdout，默认 false
stdout_logfile_maxbytes = 20MB  ; stdout 日志文件大小，默认 50MB
stdout_logfile_backups = 20     ; stdout 日志文件备份数
; stdout 日志文件，需要注意当指定目录不存在时无法正常启动，所以需要手动创建目录（supervisord 会自动创建日志文件）
stdout_logfile =/opt/data/log/elasticsearch/elasticsearch_stdout.log

[program:kibana]
command=/opt/program/kibana-5.0.0-linux-x86_64/bin/kibana
numprocs=1
autostart=true
autorestart=true

[program:logstash]
command=/opt/program/logstash-5.0.0/bin/logstash -f /opt/program/logstash-5.0.0/config/xxxx_access.conf
numprocs=1
autostart=true
autorestart=true
log_stdout=true
log_stderr=true
logfile=/opt/data/log/logstash/logstash_access.log
```

supervisorctl start elasticsearch
