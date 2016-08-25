# 9 CSS3 변경과 애니메니션
- 
- 

## 9.1 변형 속성 기본
- transition-property : 색상, 위치 등 변화의 대상이 되는 CSS 속성을 지정함.
- transition-duration : 속성의 변화에 걸리는 시간 지정하는 속성
- transition-timing-function : 속성 변화의 속도를 지정하는 속성(linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier(n,n,n,n))<br/>
  linear : 일정한 속도로 변화
  ease : 천천히 시작한후 중간에 가속하다가 감속하면서 끝남
  ease-in : 천천히 시작한후 가속됨
  ease-out : 고속으로 시작한후 감속하면서 끝남
  ease-in-out : 천천히 시작한후 서서히 가속하다가 감속하면서 끝남
  cubic-bezier(n,n,n,n) : 3차 베지어 속선을 사용하여 지정
- transition-delay : 속성 변화가 시작되는 시점을 늦추는 속성. 시간의 단위는 초(s), 밀리초(ms)

## 9.2 변형 속성
참고 url : https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions

## 9.3 키 프레임과 애니메이션 속성


그 외 참고
css 애니메이션 j-vascript 애니메이션 비교
https://developers.google.com/web/fundamentals/design-and-ui/animations/css-vs-javascript?hl=ko

성능 비교
http://wit.nts-corp.com/2013/11/20/378

트랜지션과 애니메이션과의 차이
http://ohgyun.com/466

브라우저 동작원리를 통해서 본 css 애니메이션
http://html5crew.tumblr.com/post/90615657642/%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EB%8F%99%EC%9E%91%EC%9B%90%EB%A6%AC%EB%A5%BC-%ED%86%B5%ED%95%B4%EC%84%9C-%EB%B3%B8-css-%EC%95%A0%EB%8B%88%EB%A9%94%EC%9D%B4%EC%85%98%EC%9D%98-%EC%84%B1%EB%8A%A5
