---
layout:     post
title:      "JavaScript30 day2"
subtitle:   ""
date:       2020-02-13 21:37PM
author:     "hdh"
header-img: "img/post-bg-js-version.jpg"
tags:
    - JavaScript
  
---


**JS and CSS Clock**  
**setInterval()**  
    
    var intervalID = scope.setInterval(func, delay, [arg1, arg2, ...]);  

**关于时间的度数**  
  
    const secondHand = document.querySelector('.hand.second-hand');
    const minsHand = document.querySelector('.hand.min-hand');
    const hourHand = document.querySelector('.hand.hour-hand');
    function secDate(){
      const now = new Date();

      const secends = now.getSeconds();
      const secondsDegrees = ((secends / 60) * 360) + 90;
      secondHand.style.transform = `rotate(${secondsDegrees}deg)`;
      
      const mins = now.getMinutes();
      const minsDegrees = ((mins / 60) * 360) + ((secends / 30) * 6) + 90;
      minsHand.style.transform =  `rotate(${minsDegrees}deg)`;

      const hour = now.getHours();
      const hourDegrees = ((hour / 12) * 360) + ((mins / 60) * 30) + 90; 
      hourHand.style.transform =  `rotate(${hourDegrees}deg)`;
    }
    setInterval(secDate, 1000);
    
    

