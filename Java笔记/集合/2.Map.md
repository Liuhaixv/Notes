# Map

Map是双列集合的顶层接口，不能直接创建对象

### 常用方法

* put(K key, V value):`增加(修改已有)键值对`
* remove(K key):`根据给定的键，删除对应的键值对`
* containsKey(K key):`是否存在键`
* containsValue(V value):`是否存在值`
* isEmpty():`集合是否为空`
* clear():`清空集合`
* size():`键值对个数`

### 遍历

* 获取Map集合中的所有键，放到一个Set集合中，遍历该Set集合，获取到每一个键，根据键再来获取对应的值。【根据键获取值】

  ```java
  //todo
  ```

* 获取Map集合中的所有键值对对象（Entry），到Set集合中，遍历Set集合，拿到的是每个键值对对象（Entry），从这个对象中分别获取键和值。【根据键值对对象获取键和值】

```java
  
```
### 常用双列集合Map实现类

#### HashMap

### `双列集合`

#### 用法

  ```java
  HashMap<K,V> hashMap = new HashMap<>();//K和V分别设置表示key和value的类型
  ```

#### LinkedHashMap 

相比`HashMap`有顺序存储的功能

# HashMap和Hashtable的关系

#### 相同点

* `HashMap`和`Hashtable`都是用于存储键和值的对应关系，都是`Map`的实现类，都是使用哈希表的方式存储。

#### 不同点

* 版本不同，`Hashtable`是jdk1.0版本出现的，`HashMap`是jdk1.2版本出现的
* 线程安全性不同，`Hashtable`是线程安全的，`HashMap`是线程不安全的
* `Hashtable`不能存储`null`类型键值，`HashMap`可以存储`null`类型键值