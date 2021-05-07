```
mvn deploy:deploy-file  \
-DgroupId=com.lxhw          \
-DartifactId=sqypt-base     \
-Dversion=1.0-SNAPSHOT      \
-Dpackaging=jar             \
-Dfile=/Users/chaoqunshe/Developer/qyjkpt-all/sqypt_tianjin/sqypt-base/target/sqypt-base.jar    \
-Durl=http://test.shechaoqun.com:9529/repository/nexus_9529/                                    \
-DrepositoryId=nexus_9529           \
--settings /Users/chaoqunshe/DevTools/Apache-maven/apache-maven-3.6.3/conf/settings-private.xml


```



```
mvn deploy:deploy-file  \
-DgroupId=com.lxhw          \
-DartifactId=sqypt-mybatis     \
-Dversion=1.0-SNAPSHOT      \
-Dpackaging=jar             \
-Dfile=/Users/chaoqunshe/Developer/qyjkpt-all/sqypt_tianjin/sqypt-mybatis/target/sqypt-mybatis.jar    \
-Durl=http://test.shechaoqun.com:9529/repository/nexus_9529/                                    \
-DrepositoryId=nexus_9529           \
--settings /Users/chaoqunshe/DevTools/Apache-maven/apache-maven-3.6.3/conf/settings-private.xml
```



```$xslt
    <repositories>
        <repository>
            <id>central</id>
            <name>central repository</name>
            <url>http://test.shechaoqun.com:9529/repository/maven-public/</url>
        </repository>
    </repositories>
```


```
./mvnw clean install -Dmaven.test.skip=true
```
```
./mvnw spring-boot:run
```

