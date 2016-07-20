# css3 선택자
특정한 html 태그를 선택하여 해당 태그에 원하는 스타일 또는 기능을 적용할 수 있다.(jQuery 선택자로도 사용)

```html
h1 {color:red;}
h1 태그의 컬러 속성에 red 키워드를 적용

```

## 3.1 선택자 종류 개요
교재 127p 표3-1 참고

## 3.2 전체 선택자
html 내부 모든 태그 선택
```html
* {padding:0;margin:0;}
모든 태그의 padding, margin 값을 0으로 적용
``` 
- html, head, title, style 태그까지 모두 선택
- 문서 안 모든 요소를 읽기때문에 페이지로딩 속도에 영향을 미침(사용하지 않은 태그도 포함하므로 사용 자제)

## 3.3 태그 선택자
특정 태그를 선택. 파일 초기화 시 많이 사용.(reset.css)
```html
li {list-style:none;}
파일 내 li의 list style을 none으로 적용
```

## 3.4 아이디, 클래스 선택자
아이디 속성을 가진 태그 선택
```html
#header {width:960px;}
아이디가 header인 요소에 넓이값 적용
```
- 페이지 내부 중복 불가(스크립트에서 문제 발생)
- 레이아웃 구성에 주로 사용. (Header, wrap, container, footer)

클래스 속성을 가진 태그 선택
```html
.area_banner {width:100px;height:100px;}
클래스가 area_banner인 요소의 넓이, 높이값 적용
```
- 여러 태그에 동일 클래스, 한가지 태그에 여러 클래스 사용 가능

## 3.5 속성 선택자
특정 속성을 가진 html 태그 선택 가능.
### 3.5.1 기본 속성 선택자
css2
```html
선택자[속성] a[href]
특정 속성이 있는 태그 선택

선택자[속성=값] input[type="button"] 
특정 속성 안의 값이 특정 값과 같은 문서 객체를 선택 
```
(교재처럼 선택자[속성=값][속성=값] 두개중복시 적용 안됨. 오타인듯)

### 3.5.2 문자열 속성 선택자
css2
```html
선택자[속성~=값] a[href~="val"] 
href의 값에 'val'이 포함되는 요소 선택
```
띄어쓰기를 통해 여러개 올 수 있는 속성값 중 하나만 일치해도 선택 (go, google, naver 띄어쓰기 기준 단어로 인식)

```html
선택자[속성|=값] a[href|="val"] 
href의 값이 정확하게 'val'인 태그 선택. 혹은 ko-kr 처럼 하이픈으로 연결된 경우 한 단어로 인식하여 적용
```
css3
```html
선택자[속성^=값] a[href^="val"] 
속성 안의 값이 특정 값으로 시작하는 태그를 선택. “val”으로 시작하는 속성값을 선택 
```
예를 들어 웹 문서에서 외부로 연결되는 링크가 있을 경우 http://로 시작하는지 확인하기 위해 이 선택자를 쓸 수 있다. 

```html
선택자[속성$=값] a[href$="val"] 
속성 안의 값이 특정 값으로 끝나는 태그를 선택.“val”으로 끝나는 속성값을 선택
```
이 선택자는 예제6에 나온 것 처럼 어떤 파일이 링크될 경우, 그 파일의 확장자를 확인하기 위해 쓸 수 있다. img[src=".png"]

```html
선택자[속성*=값] a[href*="val"] 
속성 안의 값이 특정 값을 포함하는 태그를 선택
```
```html
<div>
  <a href="naver.com">naver.com</a>
  <a href="naver.com" title="go naver 바로가기">naver.com</a>
  <a href="google.com" title="go google">google.com</a>
  <a href="http://daum.net" title="daum.net">daum.net</a>
  <a title="daum">daum.net</a>
</div>

a[href] {display:block;font-size:20px;font-weight:bold;}
a[href="naver.com"] {color:pink;}
a[title|="go google"] {color:orange}
a[title~="바로가기"] {color:green}
a[href^="http"] {font-size:30px;}
a[title$=".net"] {color:black;}
a[href*="d"] {text-decoration:none;}
```

## 3.6 후손 선택자와 자손 선택자
### 3.6.1 후손 선택자 (하위 선택자)
특정 태그(부모) 아래 있는 모든 하위요소 선택
```html
div a {display:block;}
div 안에 있는 모든 a 태그 선택(예를 들어 div p a 도  모두 선택됨)
```

### 3.6.2 자손 선택자(자식 선택자) 
특정 태그(부모) 바로 아래 자식 요소만 선택.
```html
div>a {display:inline-block;}
div 바로 안에 있는 a 태그 선택(예를 들어 div p a 는 선택되지 않음)
```
## 3.7 동위 선택자(인접 선택자)
같은 부모요소를 가지는 동위 관계에서 뒤에 위치한 태그를 선택할 때 사용.
```html
<div>
	<h2>title</h2>
	<h3>title</h3>
	<h3>title</h3>
	<h2>title</h2>
	<h3>title</h3>
</div>
```
### 3.7.1 인접 형제 선택자
h2+h3 두번째, 다섯번째 h3 만 적용
###3.7.2 일반 형제 선택자 
h2~h3 h2 뒤에 있는 모든 h3 에 적용

 
## 3.8 반응 선택자
사용자의 반응으로 생성되는 특정한 상태를 선택하는 선택자.
```html
<a> 요소의 반응선택자
a:hover 마우스오버 시
a:active 클릭 시
```

## 3.12 링크선택자
href 속성을 가진 a 태그에 적용되는 선택자
```html
a:link 링크 지정 시
a:visited 링크 방문 후
```
작성 시 순서중요
link -> visited -> hover -> active
나중에 선언된 클래스의 우선순위가 높기 때문에 먼저 선언된 것들을 모두 덮어쓰게 된다.
예를 들어, :hover 뒤에 a:visited를 쓰면 이미 방문한 링크 위에 마우스를 올려도 :hover가 적용되지 않는다.
이미 방문한 링크 위에 마우스를 올렸을 때 반응하게 하려면 :visited 다음에 :hover 클래스가 오도록 작성해야 한다.


## 3.9 상태 선택자
입력 양식의 상태를 선택할 때 사용하는 선태자
css1,2
```html
:focus 초점이 맞추어진 input 태그를 선택
```

css3(ie6~8 지원안함)
```html
:checked 체크상태의 input 태그를 선택  / checkbox, radio 사용
:enabled 사용 가능한 input 태그를 선택 
:disabled 사용 불가능한 input 태그를 선택
```
```html
<input type="checkbox" checked="checked" />
input[type=checkbox]:checked {height:0}

<input type="checkbox" value="enabled"/>
<input type="checkbox" value="disabled" disabled="disabled"/>

input:enabled {height:5px}
input:disabled {height:20px}
```

##3.10 구조 선택자(구조적 가장 선택자)
### 3.10.1 일반 구조 선택자
특정한 위치에 있는 태그를 선택하는 선택자(부모요소 안에 있는 모든 태그 중 해당 요소를 선택)
css2
```html
:first-child 형제관계 중 첫번째 태그 선택
```
css3
```html
:last-child 형제관계 중 마지막 태그 선택
:nth-child(수열) 형제관계 중 앞에서 수열 번째 태그 선택
:nth-last-child(수열) 형제관계 중 뒤에서 수열 번째 태그 선택

li:nth-child(2n) 짝수번째 태그 선택(2,4,6,8..)
li:nth-child(2n+1) 홀수번째 태그 선택(1,3,5,7..)
(짝수 even / 홀수 odd 와 동일한 결과)
```

### 3.10.2 형태 구조 선택자
부모요소 안에 있는 다른 태그를 무시하고 해당 요소만 선택
css3
```html
:first-of-type 형제관계 중 첫 번째로 등장하는 태그 선택
:last-of-type 형제관계 중 마지막으로 등장하는 태그 선택
:nth-of-type(수열) 형제관계 중 앞에서 수열 번째로 등장하는 태그 선택
:nth-last-of-type(수열) 형제관계 중 뒤에서 수열 번째로 등장하는 태그 선택

:root 문서의 최상위 요소 선택(html, 앞에 요소를 선택하지 않음. html에선 언제나 html 태그를 선택.)
:only-child 해당 요소가 유일한 자식이면 선택(해당 요소가 아닌 태그가 하나라도 포함되면 선택하지 않음)
:only-of-type 해당 요소가 유일한 타입이면 선택(해당 요소가 아닌 태그가 포함되어도 해당요소가 유일하면 선택)
:empty 텍스트 및 공백을 포함하여 자식 요소가 없는 태그를 선택(w,h를 주어야함.)
:target 링크의 앵커 목적지에 적용
```

## 3.11 문자 선택자
### 3.11.1 시작 문자 선택자
태그 내부 특정 조건의 문자를 선택.
```html
::first-letter 문장의 맨 첫 글자를 선택(한글도 적용됨.)
::first-line 문장의 맨 첫줄을 선택(브라우저 가로폭에 따라 첫 줄도 달라짐.)
```
IE8 까지 싱글콜론 CSS2 속성 (:before) 지원하고 더블콜론 (::before) CSS3 속성은 IE9부터 적용
(first-letter, first-line, after, before)

### 3.11.2 전후 문자 선택자
특정 태그의 전후에 위치하는 공간을 선택.
```html
::after 태그 뒤에 위치하는 공간을 선택
::before 태그 앞에 위치하는 공간을 선택
```
전후 문자 선택자에는 content 속성 사용 가능(다른 선택자는 사용 불가)


### 3.11.3 반응 문자 선택자
css3
```html
::selection 사용자가 문자와 반응해서 생기는 영역을 선택(텍스트 드래그)
::-moz-selection { 적용할 CSS 속성; } (모질라 계열에 적용)
```

## 3.13 부정 선택자
css3
```html
:not(태그) 선택자를 반대로 적용
:not(p) P태그를 제외한 모든 태그를 선택
```
