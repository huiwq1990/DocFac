

springboot mybatis druid数据源无法注入问题

```

@Configuration
@EnableTransactionManagement
@MapperScan("com.zhiyin.device.dbs.mapper")
public class MyBatisConfig implements TransactionManagementConfigurer {

    @Autowired
    DataSource dataSource;

    @Bean(name = "sqlSessionFactory")
    public SqlSessionFactory sqlSessionFactoryBean() {
        SqlSessionFactoryBean bean = new SqlSessionFactoryBean();
        bean.setDataSource(dataSource);

        bean.setTypeAliasesPackage("com.zhiyin.device.dbs.entity");

        //分页插件
        PageHelper pageHelper = new PageHelper();
        Properties properties = new Properties();
        properties.setProperty("reasonable", "true");
        properties.setProperty("supportMethodsArguments", "true");
        properties.setProperty("returnPageInfo", "check");
        properties.setProperty("params", "count=countSql");
        pageHelper.setProperties(properties);

        //添加插件
        bean.setPlugins(new Interceptor[]{pageHelper});

        //添加XML目录
        ResourcePatternResolver resolver = new PathMatchingResourcePatternResolver();
        try {
            bean.setMapperLocations(resolver.getResources("classpath:mapper/*/*.xml"));
            return bean.getObject();
        } catch (Exception e) {
            e.printStackTrace();
            throw new RuntimeException(e);
        }
    }
```

dataSource无法注入，自己新建dataSource

http://blog.csdn.net/catoop/article/details/50684676

http://www.jianshu.com/p/cef49ad91ba9

https://github.com/alibaba/druid/issues/1370

http://blog.csdn.net/isea533/article/details/50359390