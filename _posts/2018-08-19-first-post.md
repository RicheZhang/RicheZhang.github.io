<!-- ---
layout: post
title: First post about Redis basics!
subtitle:A list of redis commands,enjoy it!
image: /img/hello_world.jpeg
gh-repo: richezhang
gh-badge: [star, fork, follow]
tags:[redis,cache]
---
 -->
---
layout: post
title: Test markdown
subtitle: Each post also has a subtitle
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [test]
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
~~~
BLPOP key1[key2] timeout
BRPOP key1[key2] timeout
BRPOPLPUSH source destination timeout
LINDEX key index
LINSERT key BEFORE|AFTER pivot_value
LLEN key
LPOP key 
LPUSH key value1[value2]
LPUSHX key value
LRANGE key start end
LREM key count_Value
LSET key index_value
LTRIM key start stop
RPOP key
RPUSH key value1 [value2]
RPUSHX key value
~~~
##Redis set
~~~
SADD key member1[member2]
SCARD key
SDIFF key1 key2
SDIFFSTORE destination key1 [key2]
SINTER key1 [key2]
SINTERSTORE destination key1 [key2]
SISMEMBER key member
SMEMBERS key
SMOVE source destination member
SPOP key
SRANDMEMBER key [count]
SREM key member1 [member2]
SUNION key1 [key2]
SUNIONSTORE destination key1 [key2]
SSCAN key cursor [MATCH pattern] [COUNT count]
~~~
##Sorted set
~~~
ZADD key score1 member1 [score2 member2]
ZCARD key
ZCOUNT key min max
ZINCRBY key increment member
ZINTERSTORE destination numkeys key [key ...]
ZLEXCOUNT key min max
ZRANGE key start stop [WITHSCORES]
ZRANGEBYLEX key min max [LIMIT offset count]
ZSCORE key member
~~~
##HyperLogLog
~~~
PFADD key element [element ...]
PFCOUNT key [key ...]
PFMERGE destkey sourcekey [sourcekey ...]
~~~
##pub/sub
~~~
PSUBSCRIBE pattern [pattern ...]
PUBSUB subcommand [argument [argument ...]]
PUBLISH channel message
PUNSUBSCRIBE [pattern [pattern ...]]
SUBSCRIBE channel [channel ...]
UNSUBSCRIBE [channel [channel ...]]
~~~
##Transaction
It's important to note that even when a command fails, all the other commands in the queue are processed – Redis will not stop the processing of commands.
##Redis script
E.g,
~~~
EVAL "return {KEYS[1],KEYS[2],ARGV[1],ARGV[2]}" 2 key1 key2 first second
~~~
Commands as follows:
~~~
EVAL script numkeys key [key ...] arg [arg ...]
EVALSHA sha1 numkeys key [key ...] arg [arg ...]
SCRIPT EXISTS script [script ...]
SCRIPT FLUSH
SCRIPT KILL
SCRIPT LOAD script
~~~
##Redis connection
~~~
AUTH password
ECHO message
PING
QUIT
SELECT index ###choose the db
~~~
##Redis server
E.g:
~~~redis 127.0.0.1:6379> INFO

# Server
redis_version:2.8.13
redis_git_sha1:00000000
redis_git_dirty:0
redis_build_id:c2238b38b1edb0e2
redis_mode:standalone
os:Linux 3.5.0-48-generic x86_64
arch_bits:64
multiplexing_api:epoll
gcc_version:4.7.2
process_id:3856
run_id:0e61abd297771de3fe812a3c21027732ac9f41fe
tcp_port:6379
uptime_in_seconds:11554
uptime_in_days:0
hz:10
lru_clock:16651447
config_file:

# Clients
connected_clients:1
client-longest_output_list:0
client-biggest_input_buf:0
blocked_clients:0

# Memory
used_memory:589016
used_memory_human:575.21K
used_memory_rss:2461696
used_memory_peak:667312
used_memory_peak_human:651.67K
used_memory_lua:33792
mem_fragmentation_ratio:4.18
mem_allocator:jemalloc-3.6.0

# Persistence
loading:0
rdb_changes_since_last_save:3
rdb_bgsave_in_progress:0
rdb_last_save_time:1409158561
rdb_last_bgsave_status:ok
rdb_last_bgsave_time_sec:0
rdb_current_bgsave_time_sec:-1
aof_enabled:0
aof_rewrite_in_progress:0
aof_rewrite_scheduled:0
aof_last_rewrite_time_sec:-1
aof_current_rewrite_time_sec:-1
aof_last_bgrewrite_status:ok
aof_last_write_status:ok

# Stats
total_connections_received:24
total_commands_processed:294
instantaneous_ops_per_sec:0
rejected_connections:0
sync_full:0
sync_partial_ok:0
sync_partial_err:0
expired_keys:0
evicted_keys:0
keyspace_hits:41
keyspace_misses:82
pubsub_channels:0
pubsub_patterns:0
latest_fork_usec:264

# Replication
role:master
connected_slaves:0
master_repl_offset:0
repl_backlog_active:0
repl_backlog_size:1048576
repl_backlog_first_byte_offset:0
repl_backlog_histlen:0

# CPU
used_cpu_sys:10.49
used_cpu_user:4.96
used_cpu_sys_children:0.00
used_cpu_user_children:0.01

# Keyspace
db0:keys=94,expires=1,avg_ttl=41638810
db1:keys=1,expires=0,avg_ttl=0
db3:keys=1,expires=0,avg_ttl=0
~~~
##Backup and recovery
~~~
redis 127.0.0.1:6379> SAVE 
~~~
This will create dump.rdb file
~~~
redis 127.0.0.1:6379> CONFIG GET dir
1) "dir"
2) "/usr/local/redis/bin"
~~~
Using this,we can get the dir.And we move dump.rdb to this folder,and start redis to recover the data.
We also use ~~~Bgsave~~~to back up the redis.
##Security
To see if we have a password,we use this:
~~~
127.0.0.1:6379> CONFIG get requirepass
1) "requirepass"
2) ""
~~~
Update or set password:
~~~
127.0.0.1:6379> CONFIG set requirepass "runoob"
OK
127.0.0.1:6379> CONFIG get requirepass
1) "requirepass"
2) "runoob"
~~~
Password authentication
~~~
 AUTH password
~~~
##Redis benchmark
E.g,
~~~~
$ redis-benchmark -n 10000  -q

PING_INLINE: 141043.72 requests per second
PING_BULK: 142857.14 requests per second
SET: 141442.72 requests per second
GET: 145348.83 requests per second
INCR: 137362.64 requests per second
LPUSH: 145348.83 requests per second
LPOP: 146198.83 requests per second
SADD: 146198.83 requests per second
SPOP: 149253.73 requests per second
LPUSH (needed to benchmark LRANGE): 148588.42 requests per second
LRANGE_100 (first 100 elements): 58411.21 requests per second
LRANGE_300 (first 300 elements): 21195.42 requests per second
LRANGE_500 (first 450 elements): 14539.11 requests per second
LRANGE_600 (first 600 elements): 10504.20 requests per second
MSET (10 keys): 93283.58 requests per second

Another example:
$ redis-benchmark -h 127.0.0.1 -p 6379 -t set,lpush -n 10000 -q

SET: 146198.83 requests per second
LPUSH: 145560.41 requests per second

Get max client:

config get maxclients

1) "maxclients"
2) "10000"

Maxclients:
redis-server --maxclients 100000
~~~

##Java connection with redis
~~~
import redis.clients.jedis.Jedis;
 
public class RedisJava {
    public static void main(String[] args) {
        //connect to local Redis service
        Jedis jedis = new Jedis("localhost");
        System.out.println("Conection succeed!");
        //check if it is running
        System.out.println("Running: "+jedis.ping());
    }
}
~~~
String instance
~~~
import redis.clients.jedis.Jedis;
 
public class RedisStringJava {
    public static void main(String[] args) {
         //connect to local Redis service
        Jedis jedis = new Jedis("localhost");
        System.out.println("Succeed");
        //redis string set
        jedis.set("runoobkey", "www.runoob.com");
        // get redis string
        System.out.println("redis stored string: "+ jedis.get("runoobkey"));
    }
}
~~~
List instance
~~~
import java.util.List;
import redis.clients.jedis.Jedis;
 
public class RedisListJava {
    public static void main(String[] args) {
           //connect to local Redis service
        Jedis jedis = new Jedis("localhost");
        System.out.println("Scceed");
        //store data into list
        jedis.lpush("site-list", "Runoob");
        jedis.lpush("site-list", "Google");
        jedis.lpush("site-list", "Taobao");
        // get the elements from list
        List<String> list = jedis.lrange("site-list", 0 ,2);
        for(int i=0; i<list.size(); i++) {
            System.out.println("Lists items are: "+list.get(i));
        }
    }
}
~~~
Keys instance
~~~
import java.util.Iterator;
import java.util.Set;
import redis.clients.jedis.Jedis;
 
public class RedisKeyJava {
    public static void main(String[] args) {
            //connect to local Redis service
        Jedis jedis = new Jedis("localhost");
        System.out.println("Succeed");
 
        // get the keys
        Set<String> keys = jedis.keys("*"); 
        Iterator<String> it=keys.iterator() ;   
        while(it.hasNext()){   
            String key = it.next();   
            System.out.println(key);   
        }
    }
}
~~~
You also can use Lettuce[Java redis client](https://www.baeldung.com/java-redis-lettuce)




