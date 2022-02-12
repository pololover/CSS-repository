# CSS-repository

CSS에 대한 내용들(계속해서 추가)   
=====

position이란?   
-----
position은 요소를 배치할 때 사용하는 속성으로 대표적으로 static, relative, absolute, fixed가 있다.   
statice은 기본적인 속성. 4가지 속성 중 유일하게 left, right, top, bottom을 무시한다.   
relative : 원래 기본적인 포지션에서 상대적인 포지션을 가질 수 있도록 한다.   
absolute : 가장 가까운 positioned 조상 앨리먼트에 대해 상대적인 위치를 설정할 수 있게 한다. 단 static은 제외.    
fixed : 화면에 보이는 위치가 기준으로 스크롤이 내려가도 고정되어 있는 position속성. 특성은 relative 속성과 달리 static일 경우에 위치할 곳에 빈공간을 만들지 않는다.    

display에 대해서 
-----   
화면에 어떻게 드러나게 할지를 결정하는 속성.   
display : none = 화면에서 사라진다.   
display : block = div가 갖게되는 기본값으로 width가 자신의 컨테이너의 100%가 되게끔 한다.   
display : inline = 컨텐츠를 딱 감쌀정도의 크기만 갖게된다. block태그와 달리 줄바꿈이 되지않고 크기를 변화시킬 수 없음.    
display : inline-block = inline의 속성을 지니지만(줄바꿈이 되지않음) 임의의 크기를 바꿔줄 수있다. 즉 width를 500px로 줬을 때 500px만큼 커짐(inline은 안 됨)   
    
flex에 대해서
-----   
css3에서 도입된 레이아웃 배치방법으로 부모요소의 container와 자식요소의 item으로 구성되어있다. flex container에서 flex에 대한 속성을 설정해주면 flex item에서 배치와 같은 것들이 그에 따라 적용이 된다.   
예시로 div태그 container 1개 내부에 div태그 item 5개가 존재한다고 할 때 container에 display: flex로 준다면 기존에는 줄바꿈 된 item이 있던 것들이 일렬로 정렬이 된다.   
유의할 사항으로 display : inline-flex는 컨테이너들의 flex배치지 컨테이너 내부의 배치가 아니다.    
   
box model에 대해서
-----   
모든 html요소들은 박스 모양을으로 구성되며 이를 박스 모델이라고 한다.    
박스 모델은 내용, padding, border, margin으로 구분한다.   
정의한 width의 크기는 내용의 width이며 위의 내용을 전부 합쳐야 실제의 width 값이 된다.   

Margin vs Padding
-----
Margin은 Object와 외부와의 여백, Padding은 Object내의 내부 여백을 의미한다.   

reset.css
-----   
각 브라우저마다 설정 되어있는 기본 스타일이 달라서 이를 개선하기 위해 초기화를 시켜 통일화 시키는 작업이다. 하지만 이는 유용한 스타일까지 초기화 해서 비효율을 초래할 수 있다는 비판이 있다. 그래서 생겨난 normalize.css   

normalize.css
-----
브라우저 간 스타일의 오차를 줄이고 재지정하는 방식으로 전부 다 엎는 것이 아닌 기본값들을 최대한 보존하고 수정을 최소화하기에 많이 쓰인다.    

sass에 대해서
-----
sass는 css를 변수로 다루고 반복문과 같은 로직을 구현함으로써 재사용성을 높힐 수 있다.   
단점은 mixin의 무분별한 활용을 하게된다면 코드가 지저분하게 되고 이로 인해 파일이 무거워져 웹사이트의 속도가 저하될 수 있다.   

CSS module에 대해서
-----
장점으로는 클래스명이 충돌하는 단점을 극복할 수 있고, CSS 네이밍 규칙이 간소화 된다. 단점으로는 한 곳에서 모든 것을 작성하지 않기에 별도로 많은 CSS 파일을 만들어 관리해야 한다.   

CSS-in-JS에 대해서
-----
장점     
1. 컴포넌트로 생각할 수 있다.   
이는 더 이상 스타일시트의 묶음을 유지보수 할 필요가 없다는 뜻이다.(css 문서 레벨-> 컴포넌트 레벨)    
2. 분리를 확실히 할 수 있다. css에선 명시적으로 정의하지 않는다면 상위 부모 요소의 속성을 상속받는다. 이는 jss-isolate 플러그인을 통해서 분리시킬 수 있다.   
3. 선택자의 충돌을 막는다.   
   
단점   
1. 코드베이스에 적용하기 어렵다.    
2. javscript를 거치기에 기존 css-module보다 속도가 저하될 수 있다.   
   
css가 head상단에 위치하는 이유 그리고 link를 head안에 두는 이유.   
렌더트리 단계에서 DOM과 CSSOM이 결합해서 렌더트리를 만들게 되는데 이때 CSS가 상단에 위치해야 결합이 바로되어 렌더트리가 빠르게 만들어 질 수 있다. 이에 따라 빠른 FMP가 가능하게 만든다. 
