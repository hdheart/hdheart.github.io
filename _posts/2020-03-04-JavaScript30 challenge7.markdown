---
layout:     post
title:      "JavaScript30 day7"
subtitle:   ""
date:       2020-03-03 20:13PM
author:     "hdh"
header-img: "img/post-bg-js-version.jpg"
tags:
    - JavaScript
  
---


**array cardio**数组的知识  
展开语法（把数组展开）  

    function myFunction(x, y, z) { 
      return x+y+z;
    };
    var args = [0, 1, 2];
    myFunction(...args);  

**apply的用法**  

    /*定义一个人类*/   
    function Person(name,age) {   
        this.name=name; this.age=age;   
    }   
    /*定义一个学生类*/   
    functionStudent(name,age,grade) {   
        Person.apply(this,arguments); this.grade=grade;   
    }   
    //创建一个学生类   
    var student=new Student("qian",21,"一年级");   
    //测试   
    alert("name:"+student.name+"\n"+"age:"+student.age+"\n"+"grade:"+student.grade);   
    //大家可以看到测试结果name:qian age:21 grade:一年级   
    //学生类里面我没有给name和age属性赋值啊,为什么又存在这两个属性的值呢,这个就是apply的神奇之处.    

**什么情况下用apply,什么情况下用call**  
在给对象参数的情况下,如果参数的形式是数组的时候,比如apply示例里面传递了参数arguments,这个参数是数组类型,并且在调用Person的时候参数的列表是对应一致的(也就是Person和Student的参数列表前两位是一致的) 就可以采用apply, 如果我的Person的参数列表是这样的(age,name),而Student的参数列表是(name,age,grade),这样就可以用call来实现了,也就是直接指定参数列表对应值的位置(Person.call(this,age,name,grade));
