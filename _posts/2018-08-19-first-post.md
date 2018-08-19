---
layout: post
title: First post!
image: /img/hello_world.jpeg
---

This is my first post, how exciting!
# Redis fundamental data types and applied scenarios


|Type   |Label       |Character|Scenarios|
|-------|------------|-------------------------|---------|
|String |Binary safe |can be any type of data,like jpg pic or some serialized obj|        |
|Hash(Dict)|key-value map like map in programming language|good for storing obj,and update one of the properties easily|store,update,read the properties of obj|
|List|bidirectional linked list|fast increment,delete|1.lastly news(time line) 2.msg queue|
|Set|Hash set,no repeated element|add,delete,find very fast|1.mutual friends 2.ip visitors 
|Sorted set|set with score|when inserting data,it is already sorted|1.billboard,2.msg queue with weights|

##execute remote command on a server
~~~~
$redis-cli -h host -p port -a password
~~~~

##avoid chinese display issue,use this:
~~~~
$redis-cli --raw
~~~

##key commands
~~~
DEL key
DUMP key
EXISTS key
EXPIRE key seconds
EXPIREAT key timestamp
PEXPIRE key milliseconds
PEXPIREAT key milliseconds-timestamp
KEYS pattern
MOVE key db
PTTL key
RANDOMKEY
RENAME key newkey
RENAMENX key newkey
TYPE key
~~~

##string
~~~
SET key value
GET key
GETRANG key start end
GETSET key value
GETBIT key offset
MGET key1[key2]
SETBIT key offset value
SETEX key seconds value
SETNX key value
MSET key value[key2, value2]
MSETNX key value [key value ...]
PSETEX key milliseconds value
INCR key
INCRBY key increment
INCRBYFLOAT key increment
DECR key
DECRBY key decrement
APPEND key value
~~~

##Redis Hash
~~~
HDEL key field1[field2]
KEXISTS key field
HGETALL key
HINCRBY key field increment
HINCRBYFLOAT key field increment
HKEYS key
HLEN key
HMGET key field1 [field2]
HMSET key field1 value1 [field2 value2 ]
HSET key field value
HSETNX key field value
HVALS key
HSCAN key cursor [MATCH pattern] [COUNT count] 
~~~

##Redis list

