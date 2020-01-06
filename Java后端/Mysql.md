# Mysql操作

* 下载Jconnector
* 导包

### SQL注入

***

#### 使用PreparedStatement代替statement

>Creates a Statement object for sending SQL statements to the database. SQL statements without parameters are normally executed using Statement objects. If the same SQL statement is executed many times,<strong> it may be more efficient to use a PreparedStatement object.</strong>
>
>Result sets created using the returned Statement object will by default be type TYPE_FORWARD_ONLY and have a concurrency level of CONCUR_READ_ONLY. The holdability of the created result sets can be determined by calling getHoldability.

```java
PreparedStatement ps = 
    connection.prepareStatement("SELECT * FROM `user` WHERE username=? AND pwd=?");
//格式化parameters
ps.setObject(1, username);
ps.setObject(2, pwd);
//获取数据
ResultSet resultSet = ps.executeQuery();
```

使用`PreparedStatement`可以提高重复操作效率,通过格式化的操作避免了SQL注入风险