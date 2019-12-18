### 五种线程池的使用场景
* `newSingleThreadExecutor`：一个单线程的线程池，可以用于需要保证顺序执行的场景，并且只有一个线程在执行。
* `newFixedThreadPool`：一个固定大小的线程池，可以用于已知并发压力的情况下，对线程数做限制。
* `newCachedThreadPool`：一个可以无限扩大的线程池，比较适合处理执行时间比较小的任务。
* `newScheduledThreadPool`：可以延时启动，定时启动的线程池，适用于需要多个后台线程执行周期任务的场景。
* `newWorkStealingPool`：一个拥有多个任务队列的线程池，可以减少连接数，创建当前可用cpu数量的线程来并行执行。

### 创建线程池
一般通过工具类Executors的静态方法来获取线程池或静态方法。介绍四种常用创建方法


> 单例线程
>>表示在任意的时间段内，线程池中只有一个线程在工作
>> ```
>> ExecutorService service1 = Executors.newSingleThreadExecutor();
>>``` 

>缓存线程池
>>先查看线程池中是否有当前执行线程的缓存，如果有就resue(复用),如果没有,那么需要创建一个线程来完成当前的调用.并且这类线程池只能完成一些生存期很短的一些任务.并且这类线程池内部规定能resue(复用)的线程，空闲的时间不能超过60s,一旦超过了60s,就会被移出线程池
>>```java
>>ExecutorService service2 = Executors.newCacheThreadPool();
>>```




>固定型线程池
>>和newCacheThreadPool()差不多，也能够实现resue(复用),但是这个池子规定了线程的最大数量，也就是说当池子有空闲时，那么新的任务将会在空闲线程中被执行，一旦线程池内的线程都在进行工作，那么新的任务就必须等待线程池有空闲的时候才能够进入线程池,其他的任务继续排队等待.这类池子没有规定其空闲的时间到底有多长.这一类的池子更适用于服务器.
>>```java
>>ExecutorService service3 = Executors.newFixedThreadPool(10);
>>```

>调度型线程池
>>调度型线程池会根据Scheduled(任务列表)进行延迟执行，或者是进行周期性的执行.适用于一些周期性的工作.
>>```java
>>ExecutorService service4 = Executors.newScheduledThreadPool(10);
>>```

