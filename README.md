# GitHub Markdown 문법 및 github 명령어 정리<br>
# 2015261036 문지상

## github 명령어 정리

### 1. 설정과 초기화
<br>
전역 사용자명, 이메일 구성하기<br>
    
    git config --global user.name "Your name"
    git config --global user.email "Your email address"     


<br><br>

저장소별 사용자명, 이메일 구성하기<br>
    
    gitconfig user.name "Your name"
    git config user.email "Your email address"    
<br><br>
전역 설정 정보 조회<br>
    
    git config --global --list    
<br><br>
저장소별 설정 정보 조회<br>
    
    git config --list    
<br><br>
Git의 출력결과 색상 활성화하기<br>
    
    git config --global color.ui "auto"    
<br><br>
새로운 저장소 초기화하기<br>
    
    mkdir /path/newDir
    cd /path/newDir
    git init    
<br><br>
저장소 복제하기<br>
    
    git clone <저장소 url>    
<br><br>
새로운 원격 저장소 추가하기<br>
    
    git remote add <원격 저장소> <저장소 url>    
<br><br><br>


### 2. 기본적인 사용법
<br><br>
아래 명령어에서 []는 선택적인 매개변수를 의미한다.<br>
새로운 파일을 추가하거나 존재하는 파일 스테이징하고 커밋하기<br>
    
    git add <파일>
    git commit -m "<메시지>"    
<br><br><br>

### 3. Branch
<br>
<br>
master 브랜치를 특정 커밋으로 옮기기
<br>
    
    git checkout better_branch
    git merge --strategy=ours master    # keep the content of this branch, but record a merge
    git checkout master
    git merge better_branch            # fast-forward master up to the merge    
<br>
<br>
브랜치 목록
<br>
    
    git branch // 로컬
    git branch -r // 리모트 
    git branch -a // 로컬, 리모트 포함된 모든 브랜치 보기    
<br>
<br>
브랜치 생성
<br>
    
    git branch new master // master -> new 브랜치 생성
    git push origin new // new 브랜치를 리모트로 보내기
<br><br>
브랜치 삭제
<br>
    
    git branch -D {삭제할 브랜치 명} // local
    git push origin :{the_remote_branch} // remote
<br><br>
빈 브랜치 생성
<br>
    
    git checkout --orphan {새로운 브랜치 명}
    git commit -a // 커밋해야 새로운 브랜치 생성됨
    git checkout -b new-branch // 브랜치 생성과 동시에 체크아웃
<br><br>
리모트 브랜치 가져오기
<br>
    
    git checkout -t origin/{가져올 브랜치명} // ref
<br><br>
브랜치 이름 변경
<br>
    
    git branch -m {new name} // ref
<br><br><br>

### 4. Tag
<br><br>
태그 생성
<br>
    
    git tag -a {tag name} -m {tag message} {commit hash}
    git tag {tag name} {tag name} -f -m "{new message}" // Edit tag message
<br><br>
태그 삭제
<br>
    
    git tag -d {tag name}
    git push origin :tags/{tag name} // remote
<br><br>
태그 푸시
<br>
    
    git push origin --tags
    git push origin {tag name}
    git push --tags
<br><br><br>

### 기타
<br><br>
파일 삭제
<br>
    
    git rm --cached --ignore-unmatch [삭제할 파일명]
<br><br>

히스토리 삭제
<br>
목적 : 패스워드, 아이디 같은 비공개 정보가 담긴 파일을 실수로 올렸을 때 삭제하는 방법이다. (history에서도 해당 파일만 삭제)
<br>
    
    git clone [url] # 소스 다운로드
    cd [foler_name] # 해당 폴더 이동
    git filter-branch --index-filter 'git rm --cached --ignore-unmatch [삭제할 파일명]' --prune-empty -- --all # 모든 히스토리에서 해당 파일 삭제
    git push origin master --force # 서버로 전송
<br><br>
히스토리에서 폴더 삭제
<br>
    
    git filter-branch --tree-filter 'rm -rf vendor/gems' HEAD
<br><br>
리모트 주소 추가하여 로컬에 싱크하기
<br>
    
    git remote add upstream {리모트 주소}
    git pull upstream {브랜치명}
<br><br>

최적화
<br>
    
    git gc
    git gc --aggressive
<br><br><br>






<br><br><br><br>
## Markdown 문법 정리

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
  </code>
</pre>
<br>

#### 실행 결과



* 도
  + 레
    - 미
      

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

[![텍스트](https://cdn.pixabay.com/photo/2018/10/18/19/02/woman-3757184__340.jpg)](http://www.google.com)<br><br>

### 7.블럭

오늘 정리한 마크다운 문법들을 그냥 깃허브 기스트에 작성했다면 알아서 변환되어 보이기 때문에 변환되기 전의 코드를 보여드릴 수가 없기 때문에 블럭처리 하여 보여주는 방법이 있다. 바로 블럭처리를 하는 것이다. 만드는 방법은 여러가지가 있다.<br><br>

위에서 배운 수평선 만드는 방법으로 예시<br><br>

     ```***```     
위의 코드를 블럭을 사용하지않고 입력하면<br><br>
```***```<br><br>
위와같은 결과를 얻을 수 있다. 이밖에도 ` ``` ` 아니면 ` ~~~ ` 또는 스페이스바 4번을 연속해서 입력하면 블럭을 사용할 수 있다.<br>
비슷한 방법으로 `<pre><code></code></pre>`를 사용해서 <code>와</code>사이에 입력하면 된다.<br><br>
