---
title:  "NodeJs - 3. Javascript"
excerpt: "BackEnd"

categories:
  - BackEnd
tags:
  - BackEnd
  - NodeJs
  - Javascript
last_modified_at: 2020-02-19T08:06:00-05:00
---
## **Array**

>push() : 배열의 끝에 요소 추가

>pop() : 배열의 끝 요소 삭제

>unshift() : 배열의 앞에 요소 추가

> shift() : 배열의 앞에 요소 삭제

> splice(index, removeCount, [Object]) : 여러개의 객체를 요소로 추가하거나 삭제. ex> splice(2,0,..) : 2인덱스부터 객체 삽입.

> splice(index, copyCount) : 여러 개의 요소를 잘라내어 새로운 배열 객체로 만듬. ex> splice(2,2) : 2인덱스 부터 2개 삭제

> delete : 배열 요소 삭제 ex> delete Users[1]; 1인덱스 배열 요소 삭제. 데이터만 삭제되어 배열 사이즈는 변동 없음.

>> example

    Users.splice(1,0,{name:'bear', age:25});
    console.log('splice()로 한개를 1인덱스에 추가한 후;);
    console.dir(Users);
    Users.splice(2,1);
    console.log('splice()로 2인덱스 한개 삭제한 후;);
    console.dir(Users);

## > slice(int startindex, int endindex)

var Users2 = Users.slice(1,3);
var User3 = User2.slice(1);

## **callback**

> example

    
    function add(a, b, callback){ var result = a+b; callback(result);
    }
    add(10,10, function(result){ console.log('resule : %d', result);
    });

> example 1

    
    function add(a,b, callback)
    { var result = a + b; callback(result); var history = function() { return a+'+'+b+'='+result; } return history;
    }
    var add_history = add(10, 10, function(result) { console.log('add %d', result);
    });
    conslog.log('result : ' + add_history());

> example 2

    
    function add(a,b, callback)
    { 
    	var result = a + b; callback(result); 
    	var count = 0; 
    	var history = function() {
    		 count++; return count + ': ' + a+'+'+b+'='+result;
    	}
    	 return history;
    }
    	var add_history = add(10, 10, function(result) { console.log('add %d', result);
    });
    conslog.log('result : ' + add_history());
    conslog.log('result : ' + add_history());
    conslog.log('result : ' + add_history());

>>>> Closure

## **Prototype**

    
    function Person(name ,age) { 
    	this.name = name; this.age = age;
    }
    
    Person.prototype.walk = function(speed) {
     console.log(speed + 'km');
    }
    var person01 = new Person('P_1', 20);
    var person02 = new Person('P_2', 22);
    person01.walk(10);
    
    

> prototype 속성을 추가하면 인스턴스 객체를 만들 때 메모리를 효율적으로 관리할 수 있음.