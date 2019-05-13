# NOTES
study notes

# JAVA
  ##内存管理及JVM内存管理
  这个博客不错 共三个章节描述 https://www.cnblogs.com/zuoxiaolong/p/jvm6.html

# SPRING
  ##springboot json 
  返回json数据时间统一是时间戳
  spring.jackson.serialization.write-dates-as-timestamps=true
  
  ##跨域
  返回json数据时间统一是时间戳
  https://www.cnblogs.com/nuccch/p/7875189.html
  
  ##@Valid的使用规则
  去官网或https://blog.51cto.com/825272560/2121519
  
  ##RestTemplate使用指南
  如果需要从应用程序调用远程REST服务，你可以使用Spring框架的RestTemplate类，由于RestTemplate实例通常需要在使用之前进行定制，
  因此Spring Boot不提供任何自动配置的RestTemplate bean。但是，它可以自动配置一个RestTemplateBuilder，当需要时，它可以用来
  创建RestTemplate实例。自动配置的RestTemplateBuilder确保将合理的HttpMessageConverters应用于RestTemplate实例。
  ref:https://segmentfault.com/a/1190000016584890
  ref:https://www.cnblogs.com/hujunzheng/p/6018505.html

# MYBATIS
##date类型的数据 在条件语句中只要判空就好，不然会报错
eg.  
<if test="startTime != null and startTime = ''"> 
  and ho.order_create_time >= #{startTime,jdbcType=TIMESTAMP}
</if>
and startTime = '' ---> 会报 ParseException
直接去掉and startTime = ''就好 具体原因去看下mybatis源码
