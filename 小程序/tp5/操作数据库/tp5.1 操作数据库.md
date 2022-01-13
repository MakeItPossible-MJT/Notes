# tp5.1 操作数据库

## 查询数据

## tp数据库中间层架构

Db是个入口类，

Builder(不同的)把Query(是同一个)封装的数据翻译成适配不同数据库的原生SQL，再传给对应的Connector，连接数据库。

```markdown
好处：
1、简化sql代码的编写。
2、不需要关心具体实现，只需要根据Db类就能访问到不同的数据库。
```

## 查询构造器

```php
Db::table('table_name')->where('banner_id', '=', $id)->find(); //没有->find()，那么返回一个Query。
// table->where 辅助方法(链式方法)，find执行方法



```

### 辅助方法

```php
with('items') // 使得返回的banner中含有关联的banner_items
// 如果有多个关联的话，参数还可以换为数组
	public function getBanner($id)
    {
        (new IDMMustBePositiveInt())->goCheck();
        $banner = BAnnerModel::with('items')->get($id); // with
        if (!$banner) {
            throw new BannerMissException();
        }
        return $banner;
    }

    public function items() {
        // 关联模型的模型名字，关联模型的外键，当前模型Banner的主键
        return $this->hasMany('BannerItem', 'banner_id', 'id');
    } 
```



```php
// 不同的链式方法没有先后顺序
// 如table和where没有先后顺序 
// 但是order和order有可能对结果产生影响
```

```php
// 执行方法
// find get返回1条数据
// select all返回数据集

// update 更新
// delete 删除
// insert 插入
```

## ORM

Object Relation Mapping

把每张表当作一个对象。

model处理业务逻辑。controller调用model。

模型继承think\Model。

关联模型处理主从表。

### 自动生成模型类

```shell
 php think make:model api/BannerItem
```

```php
// 修改模型对应的表
protected $table = 'banner_item';
```

### 四个原则

```markdown
1、模型Model是来处理业务的，Db是来查询数据库的。
2、不要因为模型的性能稍差就放弃使用模型。
3、要用面向对象的思维来使用和设计模型。
4、模型的底层仍然是数据库访问抽象层。
```

### 关联关系

```php
hasmany 一对多
belongsTo 一对一，主对从
hasOne 一对一，从对主
belongsToMany 多对多
```



## 开启SQL日志记录 

```php
fetchSql()
// 返回这条sql语句，不执行
```

database.php中的debug和app.php中的app_debug也设为true。

log.php的level设为sql。

