
---
layout: post
title: Redis fundamental data types and applied scenarios!
---


|Type       |Label       |Character                           |Scenarios
|-----------|------------|------------------------------------|----------------------------------------------|
|String     |Binary safe |can be any type of data,like jpg pic or some serialized obj|                       |
|Hash(Dict) |key-value map like map in programming language|good for storing obj,and update one of the properties easily|store,update,read the properties of obj|
|List|bidirectional linked list|fast increment,delete|1.lastly news(time line) 2.msg queue|
|Set|Hash set,no repeated element|add,delete,find very fast|1.mutual friends 2.ip visitors 
|Sorted set|set with score|when inserting data,it is already sorted|1.billboard,2.msg queue with weights|

