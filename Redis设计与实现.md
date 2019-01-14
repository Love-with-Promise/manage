基础命令：
<ul>
<li>获取符合规则的键名列表:Keys pattern</li>
<li>判断一个键是否存在：exists key</li>
<li>删除键：del key</li>
<li>获得键值的数据类型：type key</li>
</ul>
字符串类型（String）：一个字符串类型键允许存储的数据的最大容量是512M。<br/>
<ul>
<li>赋值与取值:set key value  &nbsp;&nbsp; get key</li>
<li>递增数字：incr key</li>
<li>向尾部追加值：append key value</li>
<li>获得字符串长度：strlen key</li>
</ul>
散列类型（hash）：hash类型的键值是一种字典结构，其存储了字段和字段值的映射。散列类型适合存储对象：使用对象类别和ID构成键名，使用字段表示对象的属性，字段值则存储属性值<br/>
<ul>
<li>赋值与取值:不区分插入和更新操作，插入字段时hset命令会返回1，更新操作时hset命令会返回0，当键本身不存在的时候，hset还会自动创建它。
<ul>
<li>给字段赋值：hset key field value</li>
<li>获取字段的值：hget key field</li>
<li>同时设置多个字段的值：hmset key field value [field value ...]</li>
<li>同时获取多个字段的值：hmget key field [field ...]</li>
<li>获取键中所有字段和字段值：hgetall key</li>
</ul>
</li>
<li>判断字段是否存在：hexists key field</li>
<li>增加数字：hincrby key field increment</li>
<li>删除字段：hdel key field</li>
<li>获得字段数量：hlen key</li>
</ul>
列表类型（list）：列表类型存储一个有序的字符串列表，常用的操作是向列表两端添加元素，或者获得列表中的某个片段。列表类型内部使用双向链表实现，一个连类型键最多能容纳2<sup>32</sup>-1个元素<br/>
<ul>
<li>向列表两端添加元素:返回值表示增加元素后列表的长度
<ul>
<li>列表左边增加元素:lpush key value</li>
<li>列表右边增加元素：rpush key value</li>
</ul>
</li>
<li>列表两端弹出元素：lpop key &nbsp;&nbsp;&nbsp;&nbsp;rpop key</li>
<li>获取列表中元素个数：llen key</li>
<li>获得列表片段：lrange key start stop</li>
</ul>
</ul>
集合类型（set）：在set中每个元素都是不同的，且么有顺序。集合类型在redis的内部使用值为空的散列表实现的<br/>
<ul>
<li>添加元素:sadd key member[member...]</li>
<li>删除元素:srem key member[member...]</li>
<li>获得集合中所有元素：smemmbers key value</li>
<li>获得集合元素个数：scard key</li>
<li>集合间的运算：
<ul>
<li>差集运算：sdiff key [key...]</li>
<li>交集运算：sinter key [key...]</li>
<li>并集运算：sunion key [key...]</li>
</ul>
</li>
</ul>

有序集合类型（sorted set）：有序集合类型是使用散列表和跳跃表实现的，有序集合比列表类型更耗费内存<br/>
<ul>
<li>添加元素:zadd key score member[score member...]</li>
<li>获得元素分数:zscore key member</li>
</ul>
