# 集合(Collection)

## 集合

Collection是一个接口，不能直接创建对象

### 常用方法

* add(Object obj):`将obj元素添加到集合中`

* remove(Object obj):`将obj元素从集合中删除`

* contains(Object obj):`判断集合中是否包含obj元素`

* isEmpty():`集合是否为空`

* clear():`清空集合中的元素`

* size():`集合中的元素个数`

### 遍历
* 转数组:用Collection的实现类的方法`Object[] toArray()`
* 迭代器:获取集合中的迭代器`Iterator  iterator()`



## 常用集合实现类
* List类:`单列集合`

  用法:

  ```java
  ArrayList<Object> objects = new ArrayList<>();
  ```

| List类     |      |
| :--------- |
| ArrayList  |      |
| LinkedList |      |
| Vector     |      |

  

* Set类:`双列集合`

  用法:
  ```java
  HashSet<Object> objects = new HashSet<>();
  ```
  
  * HashSet
    * LinkedHashSet
  * TreeSet

q