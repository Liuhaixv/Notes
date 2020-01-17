* Servletconfig、servletContext的概念和特点如何理解？

  ```
  
  ```

* 转发和重定向的区别？

  ```
  转发是在服务端内部跳转，内部页面可以共享数据
  重定向是在客户端显式跳转路径，不传参
  ```


* 为什么说jsp本质上是servlet?

  ```
  因为jsp会在服务器运行时，被转译为java文件然后编译成class在虚拟机中运行
  ```


* jsp和servlet的区别？


  > * jsp更擅长表现于页面显示,servlet更擅长于逻辑控制
  > * Servlet中没有内置对象，Jsp中的内置对象都是必须通过HttpServletResponse对象以及HttpServlet对象得到。



* jsp的三大指令是？各自的含义是？

  ```
  page
  taglib
  include
  ```


* 描述一下jsp的执行流程？

  ```
  
  ```


* jsp的九大内置对象是？

  ```
  request
  response
  session
  page
  pageContext
  out
  exception
  config
  application
  ```


* jsp的四大作用域对象是？他们有小到大的作用范围排序是？

  ```
  page
  request
  session
  applicatoin
  ```


* jsp的静态包含和动态包含的区别是？

  ```
  动态包含于当前页面独立，可以传参
  静态包含和当前页面共享数据，不能传参
  ```


* 会话中的cookie和session区别是？

  ```
  
  ```

* request中getParameter和getAttribute的区别？

