---
title:  "NodeJs - 4. Node Basic"
excerpt: "BackEnd"

categories:
  - BackEnd
tags:
  - BackEnd
  - NodeJs
  - Javascript
  - Node Basic
last_modified_at: 2020-02-22T08:06:00-05:00
---
## URL 모듈

> 주소 문자열을 객체로 만들어 문자열 안에 있던 각각의 정보를 나누어 그 객체의 속성에 보관.
> Example
[https://www.google.co.kr/?gwr_rd=ssl#newwindow=1&q=actor](https://www.google.co.kr/%3Fgwr_rd%3Dssl%23newwindow%3D1%26q%3Dactor)
protocol : 'https'
host : 'www.google.co.kr'
query :'gws_rd=ssl#newwindow=1&q=actor
>parse() - 주소 문자열을 파싱하여 URL 객체를 만듬.
>format() - URL 객체를 주소 문자열로 변환
** querystring
> parse() - 요청 파라미터 문자열을 파싱하여 요청 파라미터 객체로 만듬
> stringify() - 요청 파라미터 객체를 문자열로 변환
> 파일
> 로그 남기기
>> winston 모듈 활용