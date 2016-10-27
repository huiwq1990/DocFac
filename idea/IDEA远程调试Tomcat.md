
## idea 调试 tomcat

idea运行

```
-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005
```

tomcat配置
```
vi catalina.sh
#在# OS specific support.上面添加
export JAVA_OPTS='-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005'
```


##参考

http://www.jianshu.com/p/f902ac5d29e4