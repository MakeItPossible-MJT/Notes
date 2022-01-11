# tp5.1 异常处理

用户行为导致的异常：通常不记录日志，需要向用户返回具体信息。

服务器自身异常：通常记录日志，不向客户端返回具体原因。

## 自定义全局异常处理

新建一个ExceptionHandler类，继承tp框架中的Handle类；重写render方法，这个方法是最终未处理的exception到达的接口。

<img src="tp5.1%20%E5%BC%82%E5%B8%B8%E5%A4%84%E7%90%86.assets/image-20220111150426631.png" alt="image-20220111150426631" style="zoom:60%;" />

 修改app.php中的配置，把异常处理handle类的路径exception_handle改为ExceptionHandler类的路径。

<img src="tp5.1%20%E5%BC%82%E5%B8%B8%E5%A4%84%E7%90%86.assets/image-20220111150540830.png" alt="image-20220111150540830" style="zoom:60%;" />



```php
ExceptionHandler // 处理异常
BaseException // 异常的基类
```

<img src="tp5.1%20%E5%BC%82%E5%B8%B8%E5%A4%84%E7%90%86.assets/image-20220111155331930.png" alt="image-20220111155331930" style="zoom:50%;" />

