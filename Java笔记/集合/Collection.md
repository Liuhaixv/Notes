# 集合(Collection)

Collection是一个接口，不能直接创建对象

### 常用方法

* add(Object obj):`将obj元素添加到集合中`

* remove(Object obj):`将obj元素从集合中删除`

* contains(Object obj):`判断集合中是否包含obj元素`

* isEmpty():`集合是否为空`

* clear():`清空集合中的元素`

* size():`集合中的元素个数`

### 遍历

* 转数组:用Collection的实现类的方法`Object[] toArray()`,带泛型方法 `Object[] toArray(T[] arr)`
* 迭代器:获取集合中的迭代器`Iterator  iterator()`



## 常用单列集合实现类

### List类

### `单列集合`

#### 特点

`有序储存`

元素`可重复`

#### 特有方法

  * add(int index, Object obj)：在指定索引上，添加指定的元素
  * remove(int index)：删除索引处的值
  * set(int index, Object obj)：修改索引处的值
  * get(int index)：获取索引处的值

#### 用法

  ```java
  ArrayList<Object> objects = new ArrayList<>();
  ```

| List类     |                                       |
| :--------- | ------------------------------------- |
| ArrayList  | 数组实现，顺序存储                    |
| LinkedList | 节点实现，链式存储 , 查询慢 ， 增删快 |
| Vector     | 线程安全，效率较低                    |


#### LinkedList

由于在LinkedList中，维护了链表的头和尾节点的对象地址，所以操作头部和尾部非常容易，提供了大量的操作头和尾的方法。

* addFirst(Object obj)：`在头部添加元素`

* addLast(Object obj)：`在尾部添加元素`

* removeFirst()：`删除头部元素`

* removeLast()：`删除尾部元素`

* getFirst()：`获取头部元素`

* getLast()：`获取尾部元素`

***

### Set类

### `单列集合`

#### 特点

`无序储存`,所以没有`索引`

元素`唯一`

#### 用法

  ```java
  HashSet<Object> objects = new HashSet<>();
  ```

| Set类     |                                       |
| :--------- | ------------------------------------- |
| HashSet  | 数组实现，顺序存储                    |
| LinkedHashSet | 节点实现，链式存储 , 查询慢 ， 增删快 |
| TreeSet     | 线程安全，效率较低                    |
## HashSet如何保证元素唯一性?

1. 某个对象obj，在即将要存储到HashSet集合的时候，首先计算obj的hashCode值

2. 在集合中的所有元素的哈希值，都和obj的哈希值不同，说明在集合中不存在obj，可以直接将obj存储到HashSet中

3. 在集合中有若干元素的哈希值，和obj的哈希值相同，并不能说明obj已经存在于集合中，需要使用equals判断obj是否和那些与自己哈希值相同的元素是否相等

4. 如果这些元素所有的和obj比较equals之后，都不相等，那么就说明obj不存在于集合中，可以将obj存储到HashSet中

5. 如果这些元素有任意一个和obj比较equals之后，发现相等，那么就说明obj已经存在于集合中，所以obj就不能存储，存储失败。

## 保证元素唯一性的操作

1. 重写hashCode:

     相同的对象，一定要有相同的哈希值

     不同的对象，尽量有不同的哈希值

     操作：根据对象的属性来生成哈希值

2. 重写equals方法:

     比较的就是各个对象的属性值，是否全都相同

在IDE中可以直接根据类生成方法