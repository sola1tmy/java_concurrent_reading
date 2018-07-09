# 基础构建模块
###同步容器类


### 并发容器
- ConcurrentHashMap
    - 使用分段锁
    - 在多线程比单纯使用synchronized吞吐量高很多，单线程损耗很少
    - size和isEmpty并不那么准确
    
- CopyOnWriteArrayList
    - 写入的时候会进行复制
    - 需要同步，且迭代较多时使用
    - 不要在数组很大的时候使用
    
- 阻塞队列和生产者消费者模式
    - 生产者消费者模式，能让数据传达给单个消费者完成独占访问
    - 双端队列：（多个消费者，单1个消费者完成工作，可以从其他消费者队列末尾获取工作）
    
### 阻塞方法与中断方法
- 传递interuupterException
- 恢复中断

### 同步工具类
- 闭锁
    - countDownLatch（可以保证多线程的同步，不是互斥）
- FutureTask
    - 完成任务在get获取前阻塞
- 信号量
    - 在使用前请求，否则阻塞
- 栅栏
    - 阻止一批事件，等到都完成，打开栅栏
    - 另外还有一种栅栏exchanger
    
### 构建高效且可伸缩的结果缓存
        
    

### 额外知识点
- linkedBlockingQueue和ArrayBlockingQueue是FIFO队列
- PriorityBlockingQueue是按优先级排序队列

### 注意
- 同步容器类虽然是线程安全的，但是复合操作依然需要注意