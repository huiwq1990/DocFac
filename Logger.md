
## Log4j Logger关闭
1. 
```
List<Logger> loggers = Collections.<Logger>list(LogManager.getCurrentLoggers());
loggers.add(LogManager.getRootLogger());
for ( Logger logger : loggers ) {
    logger.setLevel(Level.OFF);
}
```

2.

```
 log4j.rootLogger=OFF
```


http://blog.csdn.net/seeds_home/article/details/7801939
http://stackoverflow.com/questions/571960/disabling-log4j-output-in-java


## 动态修改logger

```
 private void updateLog4jConfiguration(String logFile) { 
    Properties props = new Properties(); 
    try { 
        InputStream configStream = getClass().getResourceAsStream( "/log4j.properties"); 
        props.load(configStream); 
        configStream.close(); 
    } catch (IOException e) { 
        System.out.println("Errornot laod configuration file "); 
    } 
    props.setProperty("log4j.appender.FILE.file", logFile); 
    LogManager.resetConfiguration(); 
    PropertyConfigurator.configure(props); 
 }
```

https://alperkaratepe.wordpress.com/2010/01/16/how-to-change-log4j-properties-at-runtime/