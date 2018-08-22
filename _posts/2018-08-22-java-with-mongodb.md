---
layout: post
title: Java with mongodb
subtitle: How to connect to mongodb in Java
tags: [books, MongoDB, Java]
---
First,we need to install mongo driver.
~~~
dependencies {
    compile 'org.mongodb:mongodb-driver-sync:3.8.1'
  }
~~~
Connectiong to mongo:
~~~
import com.mongodb.MongoClient;
import com.mongodb.client.MongoDatabase;

public class MongoDBJDBC{
   public static void main( String args[] ){
      try{   
       // 连接到 mongodb 服务
         MongoClient mongoClient = new MongoClient( "localhost" , 27017 );
       
         // 连接到数据库
         MongoDatabase mongoDatabase = mongoClient.getDatabase("mycol");  
       System.out.println("Connect to database successfully");
        
      }catch(Exception e){
        System.err.println( e.getClass().getName() + ": " + e.getMessage() );
     }
   }
}
~~~


Index creation:
~~~
>db.users.ensureIndex({gender:1,user_name:1})
~~~

#MongoDB Map Reduce
<img src="/img/mongodb-mapreduce.png" alt="mongodb-mapreduce" title="GitHub,Social Coding"/>
