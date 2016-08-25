# 10 CSS3 변환
HTML5에서 3차원을 구현하는 방법
- 자바스크립트를 사용한 WebGL : WebGL은 웹 기반의 그래픽 라이브러리이다. 자바스크립트 프로그래밍 언어를 통해서 사용할 수 있으며 호환성이 있는 웹 브라우저에서 인터랙티브한 3D 그래픽을 사용할 수 있도록 제공된다.
- CSS3를 사용한 3차원 변환

## 10.1 2차원 변환
X,Y축이 있는 화면 좌표
### 10.1.1 transform 속성
```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS3 Transform Basic</title>
    <style>
        section {
            width: 100px; height: 100px;
            border: 5px solid black;
        }
        div {
            width: 100px;
            height: 100px;
            background: red;
            -ms-transform: rotate(60deg);
            -moz-transform: rotate(60deg);
            -o-transform: rotate(60deg);
            -webkit-transform: rotate(60deg);
            transform: rotate(60deg);
        }
    </style>
</head>
<body>
    <section>
        <div></div>
    </section>
</body>
</html>
```
번외:-webkit-transform: rotate(0.000001deg);

### 10.1.2 2차원 변환 함수
```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS3 Transform Basic</title>
    <style>
        section {
            width: 100px; height: 100px;
            border: 5px solid black;
        }
        div {
            width: 100px; height: 100px;
            background: red;
            -ms-transform: rotate(60deg) scale(1.2) skewY(10deg);
            -moz-transform: rotate(60deg) scale(1.2) skewY(10deg);
            -o-transform: rotate(60deg) scale(1.2) skewY(10deg);
            -webkit-transform: rotate(60deg) scale(1.2) skewY(10deg);
            transform: rotate(60deg) scale(1.2) skewY(10deg);
        }
    </style>
</head>
<body>
    <section>
        <div></div>
    </section>
</body>
</html>
```
*변환 함수 순서 중요*
### 10.1.3 transform-origin 속성
기본은 태그영역의 중심을 변환 중심으로 잡는다.
```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS3 Transform Basic</title>
    <style>
        section {
            width: 100px; height: 100px;
            border: 5px solid black;
        }
        div {
            width: 100px;
            height: 100px;
            background: red;
            -ms-transform: rotate(60deg);
            -moz-transform: rotate(60deg);
            -o-transform: rotate(60deg);
            -webkit-transform: rotate(60deg);
            transform: rotate(60deg);

            -ms-transform-origin: 100% 100%;
            -moz-transform-origin: 100% 100%;
            -o-transform-origin: 100% 100%;
            -webkit-transform-origin: 100% 100%;
            transform-origin: 100% 100%;
        }
    </style>
</head>
<body>
    <section>
        <div></div>
    </section>
</body>
</html>
```
## 10.2 3차원 변환
### 10.2.1 3차원 변환 함수
```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS3 Transform Basic</title>
    <style>
        body {
            width: 200px;
            margin:200px auto;
        }
        section{width: 200px;height: 200px; position: relative}
        div {
            width: 200px;
            height: 200px;
            position:absolute; left:0; top:0;
            opacity:0.3;
        }
        /* 옆면 */
        div:nth-child(1) {transform: rotateY(0deg) translate3d(0,0,100px);background-color: red;}
        div:nth-child(2) {transform: rotateY(90deg) translate3d(0,0,100px);background-color: green;}
        div:nth-child(3) {transform: rotateY(180deg) translate3d(0,0,100px);background-color: blue;}
        div:nth-child(4) {transform: rotateY(270deg) translate3d(0,0,100px);background-color: yellow;}
        /* 윗면과 아랫면 */
        div:nth-child(5) {transform: rotateX(90deg) translate3d(0,0,100px);background-color: brown;}
        div:nth-child(6) {transform: rotateX(270deg) translate3d(0,0,100px);background-color: pink;}
    </style>
</head>
<body>
    <section>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </section>
</body>
</html>
```
### 10.2.1 transform-style 속성
```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS3 Transform Basic</title>
    <style>
        body {
            width: 200px;
            margin:200px auto;
        }
        section{
          width: 200px;height: 200px;
          position: relative;
          animation: rint 3s linear 0s infinite;
          /*transform-style: preserve-3d;*/
        }
        @keyframes rint {
          from {
            transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg);
          }
          to {
            transform: rotateX(360deg) rotateY(360deg) rotateZ(360deg);
          }
        }
        div {
            width: 200px;
            height: 200px;
            position:absolute; left:0; top:0;
            opacity:0.3;
        }
        /* 옆면 */
        div:nth-child(1) {transform: rotateY(0deg) translate3d(0,0,100px);background-color: red;}
        div:nth-child(2) {transform: rotateY(90deg) translate3d(0,0,100px);background-color: green;}
        div:nth-child(3) {transform: rotateY(180deg) translate3d(0,0,100px);background-color: blue;}
        div:nth-child(4) {transform: rotateY(270deg) translate3d(0,0,100px);background-color: yellow;}
        /* 윗면과 아랫면 */
        div:nth-child(5) {transform: rotateX(90deg) translate3d(0,0,100px);background-color: brown;}
        div:nth-child(6) {transform: rotateX(270deg) translate3d(0,0,100px);background-color: pink;}
    </style>
</head>
<body>
    <section>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </section>
</body>
</html>
```
### 10.2.1 backface-visibility 속성
backface-visibility 속성은 3차원 공간에서 평면의 후면을 보이거나 말거나 속성
```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS3 Transform Basic</title>
    <style>
        body {
            width: 200px;
            margin:200px auto;
        }
        section{
          width: 200px;height: 200px;
          position: relative;
          animation: rint 3s linear 0s infinite;
          transform-style: preserve-3d;
        }
        @keyframes rint {
          from {
            transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg);
          }
          to {
            transform: rotateX(360deg) rotateY(360deg) rotateZ(360deg);
          }
        }
        div {
            width: 200px;
            height: 200px;
            position:absolute; left:0; top:0;
            opacity:0.3;
            /* backface-visibility: hidden; */
        }
        /* 옆면 */
        div:nth-child(1) {transform: rotateY(0deg) translate3d(0,0,100px);background-color: red;}
        div:nth-child(2) {transform: rotateY(90deg) translate3d(0,0,100px);background-color: green;}
        div:nth-child(3) {transform: rotateY(180deg) translate3d(0,0,100px);background-color: blue;}
        div:nth-child(4) {transform: rotateY(270deg) translate3d(0,0,100px);background-color: yellow;}
        /* 윗면과 아랫면 */
        div:nth-child(5) {transform: rotateX(90deg) translate3d(0,0,100px);background-color: brown;}
        div:nth-child(6) {transform: rotateX(270deg) translate3d(0,0,100px);background-color: pink;}
    </style>
</head>
<body>
    <section>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </section>
</body>
</html>

```
## 10.3 원근법
화면에 얼마나 많은 3차원 픽셀을 놓을 것인지 정의
```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS3 Transform Basic</title>
    <script src="prefixfree.min.js"></script>
    <style>
        body {
            width: 200px;
            margin:200px auto;
            perspective:400px;
        }
        section{
          width: 200px;height: 200px;
          position: relative;
          animation: rint 3s linear 0s infinite;
          transform-style: preserve-3d;
        }
        @keyframes rint {
          from {
            transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg);
          }
          to {
            transform: rotateX(360deg) rotateY(360deg) rotateZ(360deg);
          }
        }
        div {
            width: 200px;
            height: 200px;
            position:absolute; left:0; top:0;
            opacity:0.3;
            /* backface-visibility: hidden; */
        }
        /* 옆면 */
        div:nth-child(1) {transform: rotateY(0deg) translate3d(0,0,100px);background-color: red;}
        div:nth-child(2) {transform: rotateY(90deg) translate3d(0,0,100px);background-color: green;}
        div:nth-child(3) {transform: rotateY(180deg) translate3d(0,0,100px);background-color: blue;}
        div:nth-child(4) {transform: rotateY(270deg) translate3d(0,0,100px);background-color: yellow;}
        /* 윗면과 아랫면 */
        div:nth-child(5) {transform: rotateX(90deg) translate3d(0,0,100px);background-color: brown;}
        div:nth-child(6) {transform: rotateX(270deg) translate3d(0,0,100px);background-color: pink;}
    </style>
</head>
<body>
    <section>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </section>
</body>
</html>

```
## 10.4 회전목마
### 10.4.1 body 태그 구성
### 10.4.2 스타일 사용
### 10.4.3 애니메이션 적용

번외: <a href="http://mohwaproject.tistory.com/entry/ReflowLayout-%EA%B3%BC-Repaint-%EA%B3%BC%EC%A0%95-%EB%B0%8F-%EC%B5%9C%EC%A0%81%ED%99%94">Reflow or  Repaint 과정</a>
