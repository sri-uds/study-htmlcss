# 05 웹 페이지 레이아웃
레이아웃을 만드는 방법

## 05.1 웹 페이지 개요
전형적인 웹페이지의 구성
http://jsbin.com/vulotutifo/edit?html,css,output
## 05.2 레이아웃 구분
- 웹페이지 구상
- 웹페이지의 구성 영역을 분리
- 구성 영역을 행 단위로 분리
- 나누어진 행의 내부 요소를 분리
```html
<body>
  <nav></nav>
  <nav></nav>
  <aside></aside>
  <section></section>
  <footer></footer>
</body>
```
```html
<body>
  <header>
    <nav></nav>
    <nav></nav>
  </header>
  <div id="content">
    <aside></aside>
    <section></section>
  </div>
  <footer></footer>
</body>
```
## 05.3 초기화
책에서의 초기화 코드
```html
* { margin: 0; padding: 0; }
body { font-family: 'Times New Roman', serif; }
li { list-style: none; }
a { text-decoration: none; }
img { border: 0; }
```
/css/ui/reset-fonts.css
```html
@CHARSET "EUC-KR";
/*
www.saramin.co.kr
version: $Id: reset-fonts.css 39277 2010-07-22 07:37:37Z jin7038 $
*/
html {
    color: #000;
    background: #FFF;
}
body, div, dl, dt, dd, ul, ol, li, h1, h2, h3, h4, h5, h6, pre, code, form, fieldset, legend, input, button, textarea, blockquote {
    margin: 0;
    padding: 0;
}

table.n0 { border-collapse: collapse; border-spacing: 0; }
td.n0, th.n0 { margin: 0; padding: 0; }
fieldset, img {
    border: 0;
}
address, caption, cite, code, dfn, em, strong, th, var, optgroup {
    font-style: inherit;
    font-weight: inherit;
}
del, ins {
    text-decoration: none;
}
li {
    list-style: none;
}
caption, th {
    text-align: left;
}
h1, h2, h3, h4, h5, h6 {
    font-size: 100%;
    font-weight: normal;
}
q:before, q:after {
    content: '';
}
abbr, acronym {
    border: 0;
    font-variant: normal;
}
sup {
    vertical-align: baseline;
}
sub {
    vertical-align: baseline;
}
legend {
    color: #000;
}
input, button, textarea, select, optgroup, option {
    font-family: inherit;
    font-size: inherit;
    font-style: inherit;
    font-weight: inherit;
}
input, button, textarea, select {
*   font-size: 100%;
}
body {
    font: 13px/1.231 arial,helvetica,clean,sans-serif;
*   font-size: small;*;
    font: x-small;
}
select, input, button, textarea, button {
    font: 99% arial,helvetica,clean,sans-serif;
}
table {
    font-size: inherit;
    font: 100%;
}
pre, code, kbd, samp, tt {
    font-family: monospace;*;
    font-size: 108%;
    line-height: 100%;
}
#doc {
  z-index: 1;
  position: relative;
  text-align: left;
  margin: auto;
  width: 950px;
}
#doc:after {
  display: block;
  text-align: left;
  margin: auto;
  width: 950px;
}
input[type=checkbox] {
    margin-right:3px;
}
```
## 05.4 헤더 구조 작성
```html
<header id="main_header">
    <div id="title">
        <h1>Rint Development</h1>
        <h2>HTML5 + CSS3 Basic</h2>
    </div>
    <nav id="main_gnb">
        <ul>
            <li><a href="#">Web</a></li>
            <li><a href="#">Mobile</a></li>
            <li><a href="#">Game</a></li>
            <li><a href="#">Simulation</a></li>
            <li><a href="#">Data</a></li>
        </ul>
    </nav>
    <nav id="main_lnb">
        <ul>
            <li><a href="#">HTML5</a></li>
            <li><a href="#">CSS3</a></li>
            <li><a href="#">JavaScript</a></li>
            <li><a href="#">jQuery</a></li>
            <li><a href="#">Node.js</a></li>
        </ul>
    </nav>
</header>
```
## 05.5 웹 폰트
사용자가 웹 페이지에 접속하는 순간 폰트를 자동으로 내려받고 해당 웹 페이지에서 사용할 수 있게 만들어주는 기능
구글폰트 : http://www.google.com/fonts
```html
<head>
  <link href='https://fonts.googleapis.com/css?family=Raleway' rel='stylesheet' type='text/css'>
  <style media="screen">
    /* font-family: 'Raleway', sans-serif; */
  </style>
</head>
```
## 05.6 수평 메뉴
float속성을 사용해 가로로 나열하는 메뉴
## 05.7 컨텐츠 구성
```html
<div id="content"></div>
```
## 05.8 본문 구성
```html
<section id="main_section">
```
## 05.9 사이드 탭바 구성
CSS3를 이용해서 탭바구성
```html
<style media="screen">
  /* 첫 번째 탭 */
        input:nth-of-type(1) { display: none; }
        input:nth-of-type(1) ~ div:nth-of-type(1) { display: none; }
        input:nth-of-type(1):checked ~ div:nth-of-type(1) { display: block; }
        /* 두 번째 탭 */
        input:nth-of-type(2) { display: none; }
        input:nth-of-type(2) ~ div:nth-of-type(2) { display: none; }
        input:nth-of-type(2):checked ~ div:nth-of-type(2) { display: block; }
</style>
<aside id="main_aside">
    <input id="first" type="radio" name="tab" checked="checked" />
    <input id="second" type="radio" name="tab" />
    <section class="buttons">
        <label for="first">First</label>
        <label for="second">Second</label>
    </section>
    <div class="tab_item">
        <ul>
            <li class="item"><a href="#">
                <div class="thumbnail">
                    <img src="http://placehold.it/45x45" />
                </div>
                <div class="description">
                    <strong>HTML5 Canvas</strong><p>2012-03-15</p>
                </div>
            </a></li>
        </ul>
    </div>
    <div class="tab_item">
        <ul>
            <li class="item"><a href="#">
                <div class="thumbnail">
                    <img src="http://placehold.it/45x45" />
                </div>
                <div class="description">
                    <strong>CSS3 Transition</strong><p>2012-03-15</p>
                </div>
            </a></li>
        </ul>
    </div>
</aside>
```
## 05.10 목록 구성
```html
<div class="tab_item">
    <ul>
        <li class="item"><a href="#">
            <div class="thumbnail">
                <img src="http://placehold.it/45x45" />
            </div>
            <div class="description">
                <strong>HTML5 Canvas</strong><p>2012-03-15</p>
            </div>
        </a></li>
        <li class="item"><a href="#">
            <div class="thumbnail">
                <img src="http://placehold.it/45x45" />
            </div>
            <div class="description">
                <strong>HTML5 Audio</strong><p>2012-03-15</p>
            </div>
        </a></li>
        <li class="item"><a href="#">
            <div class="thumbnail">
                <img src="http://placehold.it/45x45" />
            </div>
            <div class="description">
                <strong>HTML5 Video</strong><p>2012-03-15</p>
            </div>
        </a></li>
        <li class="item"><a href="#">
            <div class="thumbnail">
                <img src="http://placehold.it/45x45" />
            </div>
            <div class="description">
                <strong>HTML5 Semantic Web</strong><p>2012-03-15</p>
            </div>
        </a></li>
    </ul>
</div>
```
## 05.11 푸터 구성
```html
<footer id="main_footer">
    <h3>HTML5 + CSS3 Basic</h3>
    <address>Website Layout Basic</address>
</footer>
```
## 05.12 정리
http://jsbin.com/limugacipe/edit?html,css,output
