---
title: "Volley"
---

Volley是一个Java网络队列，支持队列请求和优先级。Volley在加载图片上并不是特别高效，因为它会将所有收到的数据都拷贝到字节数组中。尽管Volley试图重用这些字节数组，它对于中等或大图的回收复用率相对比较低。这样的结果是，Volley用于Glide一起用于加载图片时，可能导致大量的内存抖动。da当然，如果一个应用已经用了Volley，它仍然还是一个比较合适的选择，因为它允许在图片和元数据RPC之间做优先级处理。另外，在弱网环境下，Volley可能会比Glide的默认网络库要强大一些，因为它支持重试。

通常你在使用这个集成库时会想禁用Volley的磁盘缓存或Glide的磁盘缓存二者之一。如果不这样做，相同的数据可能会同时存在于Glide和Volley的磁盘缓存中。

**代码在这里:** [https://github.com/bumptech/glide/tree/master/integration/volley][1]

**Gradle 依赖:**
```groovy
compile "com.github.bumptech.glide:volley-integration:4.0.0"
```

[1]: https://github.com/bumptech/glide/tree/master/integration/volley