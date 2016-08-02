# 6 스마트폰 레이아웃
페이스북은 모바일사용자가 pc 사용자의 두배를 넘었다.  
그만큼 최근에 모바일 웹 페이지의 중요성이 증가하고 있다.

## 6.1 스마트폰 개요
하이브리드 앱의 증가에 따라 html, css가 차지하는 비중이 늘고 있다.
html5를 사용해 모바일 웹 페이지의 레이아웃을 잡는 방법을 배워본다.

jquery mobile, sencha touch, phonegap등 다양한 라이브러리를 이용해 제작할수도 있다.

## 6.2 모바일 웹 개발 주의 사항

[모바일 웹 사이트 구축을 위해 고려해야 할 사항](http://soomtong.github.io/steps-in-node/2015/03/26/mobile-website/)

## 6.3 뷰포트 meta 태그


[모바일 웹 제작시 meta태그 설정](http://maen2001.tistory.com/22)

[스마트폰 해상도](http://witinweb.com/post/91108540422/%EB%8B%A4%EC%96%91%ED%95%9C-%EC%8A%A4%EB%A7%88%ED%8A%B8%ED%8F%B0-%ED%95%B4%EC%83%81%EB%8F%84%EC%97%90-%EB%8C%80%EC%9D%91%ED%95%98%EA%B8%B0-i-%ED%95%B4%EC%83%81%EB%8F%84%EB%9E%80)

```html
<!-- 사람인 viewport -->
<meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no, target-densitydpi=medium-dpi">
```

## 6.4 초기화

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, minimun-scale=1.0, user-scalable=no" />
<style>
    * { margin: 0; padding: 0; }
    body { font-family: 'Helvetica', sans-serif; }
    li { list-style: none; }
    a { text-decoration: none; }
</style>
```
## 6.5 헤더 구조 구성

```html
<style>
    #main_header {
        /* 배경 지정 */
        height: 45px;
        background: url('header_background.png');

        /* 자손 위치 지정 */
        position: relative;
        text-align: center;
        line-height: 45px;
    }
    #main_header > h1 {
        color: white;
    }
    #main_header > a, #main_header > label {
        display: block;
        height: 32px;
        position: absolute;
    }
    #main_header > a.left {
        width: 62px;
        left: 5px; top: 7px;
    }
    #main_header > label.right {
        width: 32px;
        right: 5px; top: 7px;
    }
</style>
<body>
    <input id="toggle" type="checkbox" />
    <div id="wrap">
        <header id="main_header"></header>
    </div>
</body>
```
## 6.6 스프라이트 이미지

```html
<style>
    #main_header > a.left {
        background: url('sprites.png');
        background-position: 0px 0px;
        text-indent: -99999px ;
    }
    #main_header > label.right {
        background: url('sprites.png');
        background-position: -62px 0px;
        text-indent: -99999px;
    }
</style>
```
## 6.7 토글 목록 구성

```html
<style>
    /* 토글 구현 */
    #toggle { display: none; }
    #toggle + #wrap > #toggle_gnb_wrap { display: none; }
    #toggle:checked + #wrap > #toggle_gnb_wrap { display: block; }

    /* 레이아웃 색상 */
    #toggle_gnb_wrap {
        background: #363636;
        padding: 15px;
    }
    #toggle_gnb {
        background: #FFFFFF;
        padding: 5px;
    }

    /* 토글 목록 */
    #toggle_gnb > ul { overflow: hidden; }
    #toggle_gnb > ul > li {
        width: 80px; float: left;
    }    
</style>
<div id="toggle_gnb_wrap">
    <div id="toggle_gnb">
        <ul>
            <li><a href="#">버튼</a></li>
            <li><a href="#">버튼</a></li>
            <li><a href="#">버튼</a></li>
            <li><a href="#">버튼</a></li>
            <li><a href="#">버튼</a></li>
            <li><a href="#">버튼</a></li>
            <li><a href="#">버튼</a></li>
            <li><a href="#">버튼</a></li>
        </ul>
    </div>
</div>
```
## 6.8 내비게이션 구성(1)

## 6.9 내비게이션 구성(2)

```html
<style>
    #top_gnb {
        overflow: hidden;
        border-bottom: 1px solid black;
        background: #B42111;
    }
    #top_gnb > div > a {
        /* 수평 정렬 */
        float: left; width: 25%;

        /* 크기 및 색상, 정렬 */
        height: 35px;
        line-height: 35px;
        text-align: center;
        color: white;
    }
    #bottom_gnb {
        display: table;
        width: 100%;
        border-bottom: 1px solid black;
    }
    #bottom_gnb > div {
        display: table-cell;
        position: relative;
    }
    #bottom_gnb > div > a {
        display: block;
        height: 35px;
        line-height: 35px;
        text-align: center;
    }
    #bottom_gnb > div > a::before {
        display: block;
        position: absolute;
        top: 9px; left: -1px;
        width: 1px; height: 15px;
        border-left: 1px solid black;
        content: '';
    }
</style>
<nav id="top_gnb">
    <div><a href="#">버튼</a></div>
    <div><a href="#">버튼</a></div>
    <div><a href="#">버튼</a></div>
    <div><a href="#">버튼</a></div>
</nav>
<nav id="bottom_gnb">
    <div><a href="#">버튼</a></div>
    <div><a href="#">버튼</a></div>
    <div><a href="#">버튼</a></div>
    <div><a href="#">버튼</a></div>
    <div><a href="#">버튼</a></div>
</nav>
```

## 6.10 본문구성
```html
<style>
    #section_header { padding: 20px; }
    #section_article { padding: 10px; }
</style>
<section id="main_section">
    <header id="section_header">
        <h1>Lorem ipsum</h1>
        <time>2012-12-09 - Birthday</time>
    </header>
    <article id="section_article">
        <p>Lorem ipsum dolo</p>
        <br />
        <p>Lorem ipsum dolor</p>
        <br />
        <p>Lorem ipsum dolor</p>
    </article>
</section>
```

## 6.11 푸터구성
```html
<style>
    #main_footer {
        padding: 10px;
        border-top: 3px solid black;
        text-align: center;
    }
</style>
<div id="wrap">
    <footer id="main_footer">
        <h3>HTML5 + CSS3 Basic</h3>
        <address>Website Layout Basic</address>
    </footer>
</div>
```

## 6.12 정리

    - 뷰포트 meta xorm
    - 이미지를 사용한 그레이디언트 적용
    - 스프라이트 이미지
    - overflow 속성과 float 속성을 사용한 목록 구성
    - display 속성의 table 키워드를 적용한 목록 구성
    - ::before 선택자를 사용한 수직선 생성

HTMLPage.html 참고

## 6.13 전체화면
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Fullscreen</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, minimun-scale=1.0, user-scalable=no" />
    <!-- 초기화 -->
    <style>
        * { margin: 0; padding: 0; }
        /* #background 가 body 안에 있으므로 body 태그의 높이에 맞추기 때문에  화면을 꽉 채우고 싶을 때는 html,body 모두 height : 100% 해야 함. */
        html,body{
            height:100%
        }
        #background {
            height:100%;
            background:red;
        }
    </style>
</head>
<body>
    <div id="background">
        <h1>Full Screen</h1>
    </div>
</body>
</html>
```

## 6.14 글자 감추기
```css
.ellipsis {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```
