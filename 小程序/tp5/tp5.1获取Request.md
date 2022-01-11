# tp5.1获取Request

1、

```php
use think\Request;

$request = new Request();
```

2、

```php
use think\facade\Request
    
Request()::param();
```

3、

```php
use think\Request;

public function request(Request $request) {
	...
}
```