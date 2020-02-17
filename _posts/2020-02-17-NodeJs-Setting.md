---
title:  "NodeJs - Setting"
excerpt: "BackEnd"

categories:
  - BackEnd
tags:
  - BackEnd
  - NodeJs
  - Setting
last_modified_at: 2020-02-17T08:06:00-05:00
---

# 

**– Port**

0~1023 : 잘 알려진 포트

1024~49151 : 등록된 포트

49152~65535 : 동적 포트

​

**– Ajax(Asynchronous Javascript And XML)**

웹 서버에서 웹 문서를 받아오는 것이 아니라 데이터만 받아오기 위한 방법과 기술을 말함.

​

**– 웹서버**

기본구조 : 익스프레스(Express) 프레임워크

데이터 저장 및 조회 : MongoDB

클라이언트에 응답을 보낼 때 사용하려고 미라 웹 문서의 원형을 만들어 놓는 것 : 뷰 템플릿(View Template)

사용자 로그인이나 회원가입을 위해 사용 : 패스포트(Passport)

​

**– JSON-RPC 서버**

Data : Json

RPC : Remote Procedure Call

​

**– 위치기반서버**

DB에서 위치값(위도, 경도)를 효율적으로 읽기 : 2차원 인덱싱 방법 사용 : R-Tree, R*Tree

​

**– Node.js**

자바스크립트를 이용해서 서버를 만들 수 있는 개발 도구.

​

**– Non-Blocking IO 방식** : 비동기 입출력 방식 – 하나의 요청 처리가 끝날 때까지 기다리지 않고 다른 요청을 동시에 처리하는 방식.

​

**– Callback 시스템** : 작업이 완료하면 Callback 함수 호출.

​

**– Blocking IO code**

var contents = file.read(‘a.txt’);

doShow(content);

var result = doAdd(10,10);

​

**– Non-Blocking IO**

file.read(‘a.txt’, function(contents)){

doShow(contents);

});

var result = doAdd(10,10);

​

**– 이벤트 기반 입출력(Event driven I/O) 모델**

파일 시스템이 이벤트화 함께 호출하는 방식

​

**– 크롬 V8 엔진**

자바스크립트 코드를 네이티브 코드로 바꾼 후 실행. 빠르게 실행 가능.

노드를 설치한 다음 노드로 프로그램을 만들어 실행하면 크롬 V8 엔진 위에서 실행됨.

​

**– 바인딩**

[객체].on([이벤트 이름], [함수 객체]);

res.on(‘data’, function(){…});

​

**– Commonjs**

자바크스립트를 브라우저뿐 아니라 서버 쪽 프로그램이나 PC용 프로그램에서도 사용하려고 조직한 자발적인 워킹 그룹.

​

**– npm(Node Package Manager)**

다른 프로그래머가 미리 개발하여 올려 둔 패키지를 찾아 설치하는 방법을 제공

​

**– 브라켓설치**

[http://brackets.io](http://brackets.io/)

프로젝트 폴더는 사용자 폴더에 생성 – 권한문제가 발생할 수 있음.

C:\Users\Hwai

​

**– 확장 기능 설치**

파일 -> 확장 기능 관리자

Custom Work – 파일 탭 표시

Brackets Icons – 파일 앞에 아이콘 표시

NodeJS Integration – Ctrl + Shift + N : 바로 실행결과 확인.

​

**– 노드 설치하기**

[https://nodejs.org](https://nodejs.org/)

LTS 버젼 설치 -> Add to Path 선택되어 있는지 체크.

​

**– 명령어**

node -v : node 버젼 체크

npm -v : npm 버젼 체크

​

**– Log**

console.log(‘Number : %d’, 10);

console.log(‘String : %s’, ‘Girl’);

console.log(‘JSON : %j’, {name : ‘Girl’});

​

– time log code

var result = 0;

console.time(‘sum_time’);

for(var i=1; i<=1000; i++)

{

result += i;

}

console.timeEnd(‘sum_time’);

console.log(‘1~1000 sum : %d’, result);

console.log(‘current filename : %s’, __filename);

console.log(‘current path : %s’, __dirname);

​

– Object log

var Animal = {name:’Dog’, age:10};

console.dir(Animal);

​

console.log(‘argv count:’ + process.argv.length);

console.dir(process.argv);

​

– log : node test1.js __port 10421

if( process.argv.length > 2)

{

console.log(‘3rd parameter : %s’, process.argv[2]);

}

​

process.argv.forEach(function(item, index){

console.log(index + ‘:’, item);

}

​

– log env

console.dir(process.env);

console.log(‘OS : ‘ + process.env[‘OS’]);