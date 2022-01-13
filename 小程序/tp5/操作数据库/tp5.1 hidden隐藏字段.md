# hidden

```php
protected $hidden = ['id', 'from'];
// 可以隐藏字段

class Image extends Model
{
    protected $hidden = ['from', 'id', 'delete_time', 'update_time'];

    public function getUrlAttr($value, $data) {
        $finalUrl = $value;
        if (1 == $data['from'])
            $finalUrl = config('setting.img_prefix').$value;
        return $finalUrl;
    }
}

```

