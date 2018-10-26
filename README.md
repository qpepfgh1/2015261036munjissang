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

간단하게 그냥<br><br>
```http://www.google.com```<br><br>
이라고 적을 수 있는데 조금 문법적으로 명시하고 싶다면<br><br>
```<http://www.google.com>```<br><br>
라고 명시할 수 있다.

결과값은 둘다 동일하다.<br><br>

http://www.google.com<br><br>

또는 링크에 이름을 붙여줄 수도 있다.<br><br>
```[구글](http://www.google.com)```<br><br>
구글 이라고 적힌 것만 누르면 ```http://www.google.com```으로 이동할 수 있다.<br><br>
다음은 실행 결과이다.<br><br>
[구글](http://www.google.com)<br><br><br><br>

### 6.이미지

간단한 방식으로는<br><br>
```![텍스트](이미지파일URL.jpg)```<br><br>
```![텍스트](https://cdn.pixabay.com/photo/2018/10/18/19/02/woman-3757184__340.jpg)```<br><br>

라고 적으면 

![텍스트](https://cdn.pixabay.com/photo/2018/10/18/19/02/woman-3757184__340.jpg)<br><br>

라는 결과를 얻을 수 있다. 여기서 [텍스트]라고 되어있는 부분은 이미지를 대체하는 단어나 문장이다. 이미지가 들어갈 자리를 잡아준다고 할 수 있다.또한 한가지 방식이 더 있다.<br><br>

```![텍스트](이미지파일URL.jpg "이미지이름")```<br><br>
```![텍스트](https://cdn.pixabay.com/photo/2018/10/18/19/02/woman-3757184__340 "소녀".jpg)```<br><br>

방식으로 사용하면 이미지에 커서를 올렸을 때 "이미지이름"이 보이게 된다 다음 두 사진을 비교해보면 알 수 있다.<br><br>
![텍스트](https://cdn.pixabay.com/photo/2018/10/18/19/02/woman-3757184__340.jpg)<br><br>
![텍스트](https://cdn.pixabay.com/photo/2018/10/18/19/02/woman-3757184__340.jpg "소녀")<br><br>

한가지 더! 링크와 이미지를 합치는 방법이 있다.<br><br>

```[![텍스트](이미지URL 이나 경로)](링크URL)```<br><br>
```[![텍스트](https://cdn.pixabay.com/photo/2018/10/18/19/02/woman-3757184__340.jpg)](http://www.google.com)```<br><br>


방식으로 사용한다. 아래 이미지를 누르면 ```http:www.google.com``` 으로 이동하는것을 확인할 수 있다.<br><br>

[![텍스트](https://cdn.pixabay.com/photo/2018/10/18/19/02/woman-3757184__340.jpg)](http://www.google.com)
