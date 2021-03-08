# [Python Time and Datetime](https://www.runoob.com/python/python-date-time.html)

## 1. Time

### 1.1 [`time.time()`](https://blog.csdn.net/qq_27283619/article/details/89280974)
返回当前时间的时间戳（1970纪元后经过的浮点秒数）。但是时期的具体日期和闰秒的处理取决于使用的平台。比如：在Windows和大多数Unix系统上，纪元是1970年1月1日00:00:00（UTC），并且闰秒不计入自纪元以来的秒数，这也通常被称为Unix时间。我们要可以通过gmtime(0)查看自己平台上的纪元。

注意，即使时间总是作为浮点数返回，但并非所有系统都提供的精度高于1秒，而且更改系统的时间会影响time()的值。虽然此函数通常返回非递减值，但如果在两次调用之间设置了系统时钟，则它可以返回比先前调用更低的值。


### 1.2 [`time.perf_counter()`](https://blog.csdn.net/qq_27283619/article/details/89280974)
返回性能计数器的值（以小数秒为单位）作为浮点数，即具有最高可用分辨率的时钟，以测量短持续时间。 它确实包括睡眠期间经过的时间，并且是系统范围的。

通常`perf_counter()`用在测试代码时间上，具有最高的可用分辨率。不过因为返回值的参考点未定义，因此我们测试代码的时候需要调用两次，做差值。

`perf_counter()`会包含`sleep()`休眠时间，适用测量短持续时间


### 1.3 [`time.process_time()`](https://blog.csdn.net/qq_27283619/article/details/89280974)
返回当前进程的系统和用户CPU时间总和的值（以小数秒为单位）作为浮点数。

通常`time.process_time()`也用在测试代码时间上，根据定义，它在整个过程中。返回值的参考点未定义，因此我们测试代码的时候需要调用两次，做差值。

注意`process_time()`不包括`sleep()`休眠时间期间经过的时间。


此外Python3.7开始还提供了以上三个方法精确到纳秒的计时。分别是：  
`time.perf_counter_ns()`  
`time.process_time_ns()`  
`time.time_ns()`  
注意这三个精确到纳秒的方法返回的是整数类型。
<!--stackedit_data:
eyJoaXN0b3J5IjpbODIwMjI1NDIzXX0=
-->