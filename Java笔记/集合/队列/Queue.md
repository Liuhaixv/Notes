# Queue(队列)

### 应用

`BFS广度优先搜索`

***
### 常用方法

| 常用方法         | 功能       | 返回值           |
| :--------------- | :--------- | :--------------- |
| offer(E e)       | 添加元素   | boolean          |
| poll()           | 删除头元素 | E(Empty返回null) |
| peek()           | 查询头元素 |                  |
|                  |            |                  |
| **以下会抛异常** |            |                  |
| add(E e)         | 添加元素   | boolean          |
| remove()         |            | E                |
| element()        |            | E                |

### `offer`和`add` 区别
一些队列有大小限制，因此如果想在一个满的队列中加入一个新项，多出的项就会被拒绝。这时新的 offer 方法就可以起作用了。它不是对调用` add() `方法抛出一个 unchecked 异常，而只是得到由 `offer()` 返回的 **false**。

### `poll`和`remove` 区别
`remove() `和` poll() `方法都是从队列中删除第一个元素。

`remove() `的行为与 Collection 接口的版本相似， 但是新的 `poll() `方法在用空集合调用时不是抛出异常，只是返回 **null**。因此新的方法更适合容易出现异常条件的情况。

### `peek`和`element`区别
`element()` 和 `peek()` 用于在队列的头部查询元素。

与` remove()` 方法类似，在队列为空时， `element() `抛出一个异常，而 `peek()` 返回 **null**。

### 代码
```java
public class Main {
    public static void main(String[] args) {
        //add()和remove()方法在失败的时候会抛出异常(不推荐)
        Queue<String> queue = new LinkedList<String>();
        //添加元素
        queue.offer("a");
        queue.offer("b");
        queue.offer("c");
        queue.offer("d");
        queue.offer("e");
        for(String q : queue){
            System.out.println(q);
        }
        System.out.println("===");
        System.out.println("poll="+queue.poll()); //返回第一个元素，并在队列中删除
        for(String q : queue){
            System.out.println(q);
        }
        System.out.println("===");
        System.out.println("element="+queue.element()); //返回第一个元素 
        for(String q : queue){
            System.out.println(q);
        }
        System.out.println("===");
        System.out.println("peek="+queue.peek()); //返回第一个元素 
        for(String q : queue){
            System.out.println(q);
        }
    }
}
```

### 运行结果
```java
a
b
c
d
e
===
poll=a
b
c
d
e
===
element=b
b
c
d
e
===
peek=b
b
c
d
e
```