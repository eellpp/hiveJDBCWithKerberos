# hiveJDBCWithKerberos

demo of cloudera hive JDBC with Kerberos

Reference : https://github.com/eellpp/pubScratchpad/blob/master/security/ClouderaKerberos.md

kinit cloudera@CLOUDERA

gss-jaas.conf
```bash
com.sun.security.jgss.initiate {
     com.sun.security.auth.module.Krb5LoginModule required
     useKeyTab=false
     useTicketCache=true
     principal="cloudera@CLOUDERA"
     debug=true;
  };
  ```
  
The connection url is `jdbc:hive2://quickstart.cloudera:10000/default;principal=hive/quickstart.cloudera@CLOUDERA`

run the jar
```bash
java -cp $HADOOP_CLASSPATH:out/artifacts/hiveJDBCWithKerberos_jar/hiveJDBCWithKerberos.jar hiveTest.HiveJDBC
```

