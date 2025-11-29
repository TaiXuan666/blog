# Redis基本学习

## 前序

***Redis是一个基于内存的key-value结构数据库***

- ***基于内存存储, 读写性能高***
- ***适合存储热点数据（热点商品、资讯、新闻）***
- ***企业应用广泛***

***Redis 数据库里面的每个键值对（key-value-pair）都是由对象（object）组成的，每次在数据库中新创建一个键值对时，Redis都会帮我们至少会创建两个对象，分别是键对象和值对象，其中：***

***Redis数据库里的键总是一个字符串对象（string object）；***
***而Redis数据库键的值则可以是字符串对象、列表对象（list object）、哈希对象（hash object）、集合对象（set object）、有序集合对象（sorted set object）这五种对象中的其中一种。***

![image-20251129130352476](redis.assets/image-20251129130352476.png)



## 一、字符串 string 操作命令

***Redis 中字符串类型常用命令：***

- ***SET key value：设置指定 key 的值***
- ***GET key：获取指定 key 的值***
- ***SETEX key seconds value：设置指定 key 的值，并将 key 的过期时间设为 seconds 秒***
- ***SETNX key value：只有在 key 不存在时设置 key 的值***



***下面为具体演示：***

***SET key value：设置指定 key 的值***

![image-20251129130802221](redis.assets/image-20251129130802221.png)

***GET key：获取指定 key 的值***

![image-20251129130823541](redis.assets/image-20251129130823541.png)

***SETEX key seconds value：设置指定 key 的值，并将 key 的过期时间设为 seconds 秒***

***TTL key： 可以查看key剩余时间***

![image-20251129131017109](redis.assets/image-20251129131017109.png)

***SETNX key value：只有在 key 不存在时设置 key 的值***

![image-20251129131352200](redis.assets/image-20251129131352200.png)



## 二、哈希hash操作命令

***哈希 hash 操作命令Redis hash 是一个 string 类型的 field 和 value 的映射表，hash 特别适合用于存储对象，常用命令：***

- ***HSET key field value：将哈希表 key 中的字段 field 的值设为 value***
- ***HGET key field：获取存储在哈希表中指定字段的值***
- ***HDEL key field：删除存储在哈希表中的指定字段***
- ***HKEYS key：获取哈希表中所有字段***
- ***HVALS key：获取哈希表中所有值***
- ***HGETALL key：获取在哈希表中指定 key 的所有字段和值***

![image-20251129131518271](redis.assets/image-20251129131518271.png)



***下面为具体演示：***

***HSET key field value：将哈希表 key 中的字段 field 的值设为 value***

![image-20251129132157349](redis.assets/image-20251129132157349.png)

***HGET key field：获取存储在哈希表中指定字段的值***

![image-20251129132247639](redis.assets/image-20251129132247639.png)

***HDEL key field：删除存储在哈希表中的指定字段***

![image-20251129132910823](redis.assets/image-20251129132910823.png)

***HKEYS key：获取哈希表中所有字段***

![image-20251129132952038](redis.assets/image-20251129132952038.png)

***HVALS key：获取哈希表中所有值***

![image-20251129133009892](redis.assets/image-20251129133009892.png)

***HGETALL key：获取在哈希表中指定 key 的所有字段和值***

![image-20251129133031829](redis.assets/image-20251129133031829.png)



## 三、列表list操作命令

***列表 list 操作命令Redis 列表是简单的字符串列表，按照插入顺序排序，常用命令：***

- ***LPUSH key value1 [value2]：将一个或多个值插入到列表头部***
- ***LRANGE key start stop：获取列表指定范围内的元素***
- ***RPOP key：移除并获取列表最后一个元素***
- ***LLEN key：获取列表长度***
- ***BRPOP key1 [key2] timeout：移出并获取列表的最后一个元素，如果列表没有元素会阻塞列表直到等待超时或发现可弹出元素为止***

![image-20251129135354296](redis.assets/image-20251129135354296.png)



***下面为具体演示：***

***LPUSH key value1 [value2]：将一个或多个值插入到列表头部***

![image-20251129135441749](redis.assets/image-20251129135441749.png)

***LRANGE key start stop：获取列表指定范围内的元素***

![image-20251129135512489](redis.assets/image-20251129135512489.png)

***RPOP key：移除并获取列表最后一个元素***

![image-20251129135548091](redis.assets/image-20251129135548091.png)

***LLEN key：获取列表长度***

![image-20251129135630218](redis.assets/image-20251129135630218.png)

***BRPOP key1 [key2] timeout：移出并获取列表的最后一个元素，如果列表没有元素会阻塞列表直到等待超时或发现可弹出元素为***

***当列表没有对应的key时,使用这个命令就会等待timeout秒，当有对应的key新增时就会删除***

![image-20251129140424137](redis.assets/image-20251129140424137.png)

![image-20251129140457026](redis.assets/image-20251129140457026.png)



## 四、集合 set 操作命令

***Redis set 是 string 类型的无序集合。集合成员是唯一的，这就意味着集合中不能出现重复的数据，常用命令:***

- ***SADD key member1 [member2]：向集合添加一个或多个成员***
- ***SMEMBERS key：返回集合中的所有成员***
- ***SCARD key：获取集合的成员数***
- ***SINTER key1 [key2]：返回给定所有集合的交集***
- ***SUNION key1 [key2]：返回所有给定集合的并集***
- ***SDIFF key1 [key2]：返回给定所有集合的差集***
- ***SREM key member1 [member2]：移除集合中一个或多个成员***

![image-20251129140737957](redis.assets/image-20251129140737957.png)



***下面为具体演示：***

***SADD key member1 [member2]：向集合添加一个或多个成员***

![image-20251129140840361](redis.assets/image-20251129140840361.png)

***SMEMBERS key：返回集合中的所有成员***

![image-20251129140853542](redis.assets/image-20251129140853542.png)

***SCARD key：获取集合的成员数***

![image-20251129140910901](redis.assets/image-20251129140910901.png)

***SINTER key1 [key2]：返回给定所有集合的交集***

![image-20251129141037356](redis.assets/image-20251129141037356.png)

***SUNION key1 [key2]：返回所有给定集合的并集***

![image-20251129141108470](redis.assets/image-20251129141108470.png)

***SDIFF key1 [key2]：返回给定所有集合的差集***

![image-20251129141131903](redis.assets/image-20251129141131903.png)

***SREM key member1 [member2]：移除集合中一个或多个成员***

![image-20251129141203001](redis.assets/image-20251129141203001.png)



## 五、有序集合 sorted set 操作命令

***Redis sorted set 有序集合是 string 类型元素的集合，且不允许重复的成员。每个元素都会关联一个 double 类型的分数 (score)。redis 正是通过分数来为集合中的成员进行从小到大排序。有序集合的成员是唯一的，但分数却可以重复。常用命令:***

- ***ZADD key score1 member1 [score2 member2]：向有序集合添加一个或多个成员，或者更新已存在成员的分数***
- ***ZRANGE key start stop [WITHSCORES]：通过索引区间返回有序集合中指定区间内的成员***
- ***ZINCRBY key increment member：有序集合中对指定成员的分数加上增量 increment***
- ***ZREM key member [member ...]：移除有序集合中的一个或多个成员***

![image-20251129141345382](redis.assets/image-20251129141345382.png)



***下面为具体演示：***

***ZADD key score1 member1 [score2 member2]：向有序集合添加一个或多个成员，或者更新已存在成员的分数***

![image-20251129141506568](redis.assets/image-20251129141506568.png)

***ZRANGE key start stop [WITHSCORES]：通过索引区间返回有序集合中指定区间内的成员***

![image-20251129141525193](redis.assets/image-20251129141525193.png)

***ZINCRBY key increment member：有序集合中对指定成员的分数加上增量 increment***

![image-20251129141815456](redis.assets/image-20251129141815456.png)

***ZREM key member [member ...]：移除有序集合中的一个或多个成员***

![image-20251129141839260](redis.assets/image-20251129141839260.png)