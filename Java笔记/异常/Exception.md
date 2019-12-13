# Exception

### 体系

* Throwable `异常体系的顶层父类`
  * Error `描述那些无法捕获和处理的错误情况，属于非常严重的错误`
  * Exception `描述那些可以捕获和处理的例外情况，属于不太严重的错误`
    * RuntimeException `运行时异常，是Exception的特殊的子类，在编译阶段不做检查的一个异常`

### 捕获异常

#### 格式

```java
try {
 	 	可能发生异常的代码
} catch(Exception e){
    Exception表示所有异常，修改异常类型来捕获特定类型异常,被本异常类型捕获的将执行该处代码块
} catch(Exception e){
    ...
} catch ...  
finally{
 	一定要执行的代码
}
```

### throws关键字

#### 格式

```
 	修饰符 返回值类型 方法名称(参数列表) throws 异常类型1, 异常类型2,... {
 	 	可能出现异常的代码
}
```

### throw和throws的比较

* `throw`是对异常对象的抛出，`throws`是对异常类型的声明
* `throw`是对异常对象实实在在的抛出，一旦使用了`throw`关键字，就一定有一个异常对象出现；`throws`是对可能出现的异常类型的声明，即使声明了一些异常类型，在这个方法中，也可以不出现任何异常。
* `throw`后面只能跟一个异常对象；`throws`可以跟很多个异常类型



