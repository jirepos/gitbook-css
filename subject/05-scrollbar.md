# scrollbar


CSS 의사 요소 ::-webkit-scrollbar 는 요소에 overflow:scroll;이 설정되어 있을 때 해당 요소의 스크롤바 스타일에 영향을 끼칩니다.


::-webkit-scrollbar는 Blink 및 WebKit 기반의 브라우저에서만 사용 가능합니다. (예: Chrome, Edge, Opera, Safari, iOS의 모든 브라우저 등등). 스크롤바를 스타일링하는 표준화된 방법은 scrollbar-color (en-US)와 scrollbar-width (en-US)로 이용 가능합니다.

스크롤바 스타일에 관한 웹표준은 존재하지 않습니다.

다만 wekbit 브라우저(크롬, 사파리, 오페라)에 한해서 가상요소를 사용하여 스타일을 적용할 수 있습니다.

 

* ::-webkit-scrollbar : 스크롤바 전체
* ::-webkit-scrollbar-thumb : 스크롤 막대
* ::-webkit-scrollbar-track : 스크롤 막대 외부



```html
<style>
  .container {
    width: 250px;
    height: 140px;
    overflow: auto;
  }
  .container::-webkit-scrollbar {
    width: 10px;
  }
  .container::-webkit-scrollbar-thumb {
    background-color: #2f3542;
    border-radius: 10px;
  }
  .container::-webkit-scrollbar-track {
    background-color: grey;
    border-radius: 10px;
    box-shadow: inset 0px 0px 5px white;
  }
</style>
```


https://developer.mozilla.org/ko/docs/Web/CSS/::-webkit-scrollbar


https://codingbroker.tistory.com/66