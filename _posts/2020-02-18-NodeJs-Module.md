---
title:  "NodeJs - 2. Module"
excerpt: "BackEnd"

categories:
  - BackEnd
tags:
  - BackEnd
  - NodeJs
  - Module
last_modified_at: 2020-02-18T08:06:00-05:00
---


## **Module**

> exports – calc.js

exports.add = function(a,b) { return a+b;};exports.multiply = function(a,b){ return a*b;}==== test5.js ====

var calc = require(‘./calc’);console.log(‘result : %d’, calc.add(10,100));

---

> module.exports – calc_2.js

var calc = {};

clac.add = function(a,b) { return a+b;};clac.multiply = function(a,b){ return a*b;}module.exports = calc;==== test6.js ====var calc = require(‘./calc_2’);

console.log(‘result : %d’, calc.add(10,100));**> 외장 모듈**>>nonf 설치

npm install nconfvar nconf = require(‘nconf’);

nconf.env();

console.log(‘OS result : %s’, nconf.get(‘OS’));>> In most cases you are behind a proxy… ; Error

## >>>프록시 서버 확인 : netstat

## >>>설정

npm config set proxy [http://address:port](http://address:port/)

npm config set https-proxy [http://address:port](http://address:port/)npm config set strict-ssl false>> 설치 제거

npm uninstall nconf

## >> package.json 설치

npm init (name) : node npm install nconf –save

### >> 현재 프로젝트에 설치된 외장 모듀들을 다른 프로젝트에 외장 설치 package.json 복사

npm install**> 내장 모듈**>> 내장 모듈 정보 : [http://nodejs.org/api](http://nodejs.org/api)

### >> os 모듈운영체제 호스트 이름 : hostname()

시스템의 전체 메모리 용량 : totalmem()

시스템 사용 가능한 메모리 용량 : freemem()

CPU 정보 : cpus()

네트워크 인터페이스 정보 : newworkInterface()var os = require(‘os’);console.log(‘hostname : %s’, os.hostname());

console.log(‘memory : %d/%d’, os.freemem(), os.totalmem());

console.log(os.cpus());

console.log(os.networkInterfaces());

### >> path 모듈

하나의 파일 패스로 : join()

디렉터리 이름 : dirname()

파일 이름만 : basename()

확장자만 : extname()

var path = require(‘path’);// 디렉토리 이름 합치기

var directories = [“users”, “hwai”, “docs”];

var docsDir = directories.join(path.sep);

console.log(‘directory: %s’, docsDir);//디렉토리 이름과 파일 이름 합치기

var curPath = path.join(‘/Users/hwai’, ‘notepad.exe’);

console.log(‘path: %s’,curPath);var filename = “C:\\Users\\hwai\\notepad.exe”;

var dirname = path.dirname(filename);

var basename = path.basename(filename);

var extname = path.extname(filename);