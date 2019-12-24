# SimpleDateFormat(格式化日期)

|方法| |
|      -------- |  ----   |
|  | |
|  | |

## 关于线程安全

SimpleDateFormat 是**线程不安全**的类

```javadoc
Date formats are not synchronized. It is recommended to create separate format instances for each thread. If multiple threads access a format concurrently, it must be synchronized externally.
```

多线程环境下注意线程安全问题，如果是 Java 8 ，建议使用 `DateTimeFormatter` 代替 SimpleDateFormat

###  [SimpleDateFormat 如何安全的使用？](..\..\..\asset\SimpleDateFormat 如何安全的使用？ - zhisheng_tian - 博客园.html) 