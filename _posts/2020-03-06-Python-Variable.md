---
title:  "Variable"
excerpt: "Python"

categories:
  - Python
tags:
  - Python
  - variable
  - if
last_modified_at: 2020-03-06T10:06:00-05:00
---

# 변수

- 변수는 대소문자 구분 가능
- 2//3 = 0, // 정수 나누기
- 'python'[0] → 'p', 'python'[5] → 'n', 'python'[1:4] → 'yth', 'python'[-2:] → 'on'
- 얕은 복사 : 주소가 복사되어 객체를 공유하는 경우
- 깊은 복사 : 객체를 공유하지 않는 경우

    >>> a = [1,2,3]

    >>> b = a[:]

    >>> id(a), id(b)

    (18122032, 18121912)

    >>> a[0] = 38

    >>> a

    [38,2,3]

    >>> b

    [1,2,3]


# 제어문

    if 90 ≤ score ≤ 100 :

    grade = "A"

    elif 80 ≤ score ≤ 90:

    grade = "B"

    else :

    grade = "C"


False - 0, 0.0, (), [], {} ''(빈문자열), None 인 경우

True - False인 경우를 제외한 값이 할당된 경우

단축평가 : 조건식 전체를 판단하지 않고 순차적으로 진행하다 식 전체가 자명한 경우, 더 이상 수식을 평가하지 않는 방법

    if a & 10 /a  → if a=0, CompileError

    if a and 10/a → if a =0 , Not Compile Error : 단축평가 적용.

while<조건문>:


<구문>


for <아이템 I> in <시퀀스 객체 S>


else :


<구문>


for 구문이 정상적으로 수행되어 else: 구문이 실행됨.


# 리스트 내장


## [<표현식> for <아이템> in <시퀀스 객체> (if <조건식>)]


    >>> [ i for i in t if len(i) > 5 ]

    --------------------------------------------------
    

    >>> L_1 = [3,4,5]

    
    >>> L_2 = [1.5, -0.5, 4]

    
    >>> [ x*y for x in L_1 y in L_2 ]

    
    [4.5, -1.5, 12, 6.0, -2.0, 16, 1.5, -2.5, 20]


## filter(<function>|None, 시퀀스 객체)


    >>> L = [10,25,30]

    >>> IterL = filter(None, L)

    >>> for i in IterL:

    	print("Item: {0}".format(i))

    
    Item: 10

    Item: 25

    Item: 30

    
    >>> def GetBiggerThan20(i):

    	return i > 20


    >>> list(filter(GetBiggerThan20, L))

    [25, 30]

    >>>

    >>> list(filter(lambda i: i>20, L))

    [25,30]


## range(['시작값'], '종료값'[,'증가값'])


    >>> list(range(10))

    [0,1,2,3,4,5,6,7,8,9]

    >>> list(range(5,10))

    [5,6,7,8,9]

    >>> list(range(10,0,-1))

    [10,9,8,7,6,5,4,3,2,1]

    >>> list(range(10,20,2))

    [10,12,14,16,18]


## map(<function>, sequence object, ...)


    >>> L = [1,2,3]

    >>> def Add10(i):

    	return i+10

    >>> for i in map(Add10, L)

    	print("Item: {0}".format(i))

    
    Item: 11

    Item: 12

    Item: 13

    >>>

    >>> X = [1,2,3]

    >>> Y = [2,3,4]

    >>> list(map(pow,X,Y))

    [1,8,81]
