# Pseudo-class


## :root
CSS :root 의사 클래스는 문서 트리의 루트 요소를 선택합니다 HTML의 루트 요소는 <html> 요소이므로, :root의 명시도가 더 낮다는 점을 제외하면 html 선택자와 똑같습니다.


```css
/* 문서의 루트 요소 선택
   HTML에서는 <html> */
:root {
  background: yellow;
}
```
### 예제 
**전역 CSS 변수 선언하기**
:root는 전역 CSS 변수 선언에 유용하게 사용할 수 있습니다.
```css
:root {
  --main-color: hotpink;
  --pane-padding: 5px 42px;
}
```






