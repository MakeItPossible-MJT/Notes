# 读取器

 ```php
    public function getUrlAttr($value, $data) {
        $finalUrl = $value;
        if (1 == $data['from'])
            $finalUrl = config('setting.img_prefix').$value;
        return $finalUrl;
    }

// get和Attr是默认的，Url是要读取的字段
 ```

