# GitHub Markdown 문법 정리  2015261036 문지상

### 1. 헤더(Headers)
<br>
큰 제목 : 문서 제목<br>

사용 방법은 아래와같이 코딩하면 된다.
<pre>
  <code>
  문서 제목
  ======== 
  </code>
</pre>

#### 실행 결과

문서 제목
========
<br>
<br>
<br>
작은 제목 : 문서 부 제목<br>

사용 방법은 아래와같이 코딩하면 된다.
<pre>
  <code>
  문서 부 제목
  ----------- 
  </code>
</pre>

#### 실행 결과

문서 부 제목
-----------
<br>
<br>
<br>
또는 html문법에서 h1~h6와 같은 문법을 이용할 수 있다. 기존의 방식을 따라 사용하여도 무방하다.
<br>
github에서는 아래와 같은 문법을 허용한다.
<pre>
  <code>
  # h1
  ## h2
  ### h3
  #### h4
  ##### h5
  ###### h6
  </code>
</pre>
<br>
<br>

#### 실행 결과


# h1

## h2

### h3

#### h4

##### h5

###### h6


### 2. BlockQuote<br>

아래와 같이 >를 이용하여 들여쓰기가 가능하다.
<pre>
  <code>
  > 첫번째
  >> 두번째
  >>> 세번째
  </code>
</pre>
<br>

#### 실행 결과


> 첫번째
>> 두번째
>>> 세번째


BlockQuote 내부에서 다른 문법을 사용할 수 있다.

> # 첫번째
>> ## 두번째
>>> ### 세번째


### 3. 목록<br>


순서있는 목록은 숫자와 점을 이용한다.

<pre>
  <code>
  1. 첫번째
  2. 두번째
  3. 세번째
  </code>
</pre>
<br>

#### 실행 결과


1. 첫번째
2. 두번째
3. 세번째


위에 목록 사용법은 꼭 1,2,3 순서가 아니더라도 내림차순으로 정의된다.

순서 업는 목록은 다음과 같은 기호를 이용한다.
<pre>
  <code>
  * 도
    * 레
      * 미
  + 도
    + 레
      + 미
  - 도
    - 레
      - 미
  </code>
</pre>
<br>

#### 실행 결과


* 도
  * 레
    * 미
+ 도
  + 레
    + 미
- 도
  - 레
    - 미


혼합해서 사용하는 것도 가능하다.

<pre>
  <code>
  * 도
    + 레
      - 미
        = 파
  </code>
</pre>
<br>

#### 실행 결과



* 도
  + 레
    - 미
      = 파
      

### 4. 수평선

수평선을 만드는 방법은 여러가지가 있다.
1. ```***```
2. ```* * *```
3. ```*****```
4. ```- - -```
5. ```-------------------```

***
* * *
*****
- - -
-------------

### 5. 링크

참조링크<br>
[link keyword][id]<br>
[id]: URL "Optional Title here"

Link: [Google][googlelink]<br>
[googlelink]: https://google.com "Go google"

Link: [Google][googlelink][googlelink]: https://google.com "Go google"<br>

인라인 링크<br>

```systax: [Title](link)<br>```

systax: [Google](link)


자동연결<br>
```
<http://example.com/><br>
<address@example.com><br><br>
```

<http://example.com/><address@example.com>






