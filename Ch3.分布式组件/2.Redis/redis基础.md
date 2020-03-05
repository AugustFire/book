# redis原生操作指令


## 一.基础操作命令

1.keys pattern			//查询(禁止在生产环境使用)

```text
?		匹配一个字符
*		匹配任意个字符
  []	区间内
  \x	专义
```


2.exists keys		        //查询一个键是否存在

3.del keys			//删除键

4.type keys			//获取键值对类型

## 二.数据类型

### 1.字符串类型(string)

基本命令

```tex
set key value	//设置K-V
get key	 k1		//获取指定K-v
append key word	//尾部追加值
strlen key k1	//获取长度 不存在返0
mget k1 k2		//获取多个值
mset k1 v1 k2 v2 //同时设置多个键值对
```

递增数字(可以生成全局唯一Id)

```te
incr key
```

### 2.散列类型(hash)

基本命令

```text
hset key field value	
hget key field
hmset key f1 v1 f2 v2 ...
hmget key f1 f2
hgetall key
hexists key field		//判断字段是否存在
hsetnx key field value	//当字段不存在时赋值[原子操作]
hincrby key filed num	//增加数字
hkeys				   //只获取所有字段名
hvals				   //获取所有value
hlen key			   //获取字段数量
```

### 3.列表类型(list双向链表)

基本命令

```text
lpush		//向列表左边增加元素
rpush		//向列表右边增加元素
lpop		//向列表左侧弹出一个元素
rpop		//向列表右侧弹出一个元素
llen		//获取列表元素个数
lrange key start stop	//获取指定段列表
lrem key count value	//删除列表指定值 count>0左侧开始 =0 所有
lindex key index		//获取指定索引的index
lset key index value	//设置指定位置的值
ltrim key start end		//删除指定索引外的所有元素

```

### 4.集合(set)

基本命令

```text
sadd key member ... //添加
srem key member ...	//删除
smembers xx xx 		//

```



