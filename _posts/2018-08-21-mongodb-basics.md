---
layout: post
title: HTML Basics!
subtitle:The basic knowledge about html!
image: /img/hello_world.jpeg
tags:[NoSql,MongoDB]
---

#MongoDB Intro
NoSql means not just sql.
MongoDB is a NoSql database for unstructured file storage.
Websites using MongoDB:
- Craiglist
- Foursquare
- Shutterfly
- bit.ly
- spike.com
- Intuit
- sourceforge.net
- etsy.com
- newyork times
- CERN

[DownloadLink](https://www.mongodb.com/download-center#community)

Installation on MacOS:
~~~
Brew install mongodb
~~~
TLS/SSL enabled:
~~~
brew install mongodb --with-openssl
~~~
Install the dev version:
~~~
brew install mongodb --devel
~~~
###Start mongodb
~~~
sudo mkdir -p /data/db
sudo mongod

$ ./mongo
MongoDB shell version v3.4.2
connecting to: mongodb://127.0.0.1:27017
MongoDB server version: 3.4.2
Welcome to the MongoDB shell.
……
> 1 + 1
2
> 
~~~
You can also use ```--dbpath```to define the data path
Definitions about mongodb:
- database
- table
- row
- column/row
- index
- primary key,_id in mongodb


~~~
> show dbs
admin   0.000GB
config  0.000GB
local   0.000GB
>
~~~

<!-- DataType:
<hr>
String	字符串。存储数据常用的数据类型。在 MongoDB 中，UTF-8 编码的字符串才是合法的。
Integer	整型数值。用于存储数值。根据你所采用的服务器，可分为 32 位或 64 位。
Boolean	布尔值。用于存储布尔值（真/假）。
Double	双精度浮点值。用于存储浮点值。
Min/Max keys	将一个值与 BSON（二进制的 JSON）元素的最低值和最高值相对比。
Array	用于将数组或列表或多个值存储为一个键。
Timestamp	时间戳。记录文档修改或添加的具体时间。
Object	用于内嵌文档。
Null	用于创建空值。
Symbol	符号。该数据类型基本上等同于字符串类型，但不同的是，它一般用于采用特殊符号类型的语言。
Date	日期时间。用 UNIX 时间格式来存储当前日期或时间。你可以指定自己的日期时间：创建 Date 对象，传入年月日信息。
Object ID	对象 ID。用于创建文档的 ID。
Binary Data	二进制数据。用于存储二进制数据。
Code	代码类型。用于在文档中存储 JavaScript 代码。
Regular expression	正则表达式类型。用于存储正则表达式。 -->
##Create database
~~~
>use Database_name
~~~
Delete operation:
~~~
db.dropDatabase()
~~~
Delete collections:
~~~
db.collection.drop()
~~~
Create collections:
~~~
db.createCollection(name, options)
~~~



