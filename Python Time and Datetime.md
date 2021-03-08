# [Python Time and Datetime](https://www.runoob.com/python/python-date-time.html)

## 1. Time

### 1.1 [`time.time()`](https://blog.csdn.net/qq_27283619/article/details/89280974)
返回当前时间的时间戳（1970纪元后经过的浮点秒数）。但是时期的具体日期和闰秒的处理取决于使用的平台。比如：在Windows和大多数Unix系统上，纪元是1970年1月1日00:00:00（UTC），并且闰秒不计入自纪元以来的秒数，这也通常被称为Unix时间。我们要可以通过gmtime(0)查看自己平台上的纪元。

注意，即使时间总是作为浮点数返回，但并非所有系统都提供的精度高于1秒，而且更改系统的时间会影响time()的值。虽然此函数通常返回非递减值，但如果在两次调用之间设置了系统时钟，则它可以返回比先前调用更低的值。


### 1.2 `time.perf_cou()`
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYwNzg0Njc2OV19
-->