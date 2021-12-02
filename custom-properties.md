# 사용자 지정 속성(Custom Properties)

CSS Variables 또는 cascading variables라고도 불린다. 

* 문서 전반적으로 재사용할  임의의 값을 담는다. 
* 표기법: --main-color:black 
* 접근은 var() 함수를 사용한다.  ex) color: var(--main-color)


## 기본 사용법 
:root 클래스에 변수를 설정한다.  :root 클래스에 선언하는 것은 전역 선언이다. 
```css
   :root  {
      --main-color: yellow; 
    }
```
클래스를 선언하고 var()를 사용하여 변수 값을 참고한다. 
```css
    .one { 
      background-color: var(--main-color)
    }
```
요소에 class를 적용한다. 
```html
  <div class="one">
    first div 
  </div>
```
위 div 요소는 배경색이 노란색이 될 것이다. 


> 사용자 지정 속성의 이름은 대소문자를 구분합니다. 따라서 --my-color와 --My-color는 서로 다른 속성으로써 처리합니다.





## 사용자 지정 속성의 상속 

사용자 지정 속성은 상속 대상이다.  그러므로 특정 요소에 사용자 지정 속성 값을 설정하지 않은 경우, 그 부모의 값을 사용한다.  

all이 적용된 요소의 하위 div에는 사용자 지정속성이 적용된다. 하지만, content 클래스를 사용하는 div는 적용되지 않는다. 

```css
      .all {
        --text: 12px;
        --color: yellow;
      }
      .all div { 
        font-size: var(--text);
        color: var(--color); 
      }

      .content { 
        font-size: var(--text);  /* Not applicable */
        color: var(--color);  /* Not applicable */
      }
```
```html
  <div class="all">
    <div>여기에는 적용됨</div>
  </div>
  <div class="content">여기는 적용안된다.</div>
```



## JavaScript에서 변수 사용 
```jsx
let root = document.querySelector(':root')
let styles = widnow.getComputedStyle(root);
console.log(styles.getPropertyValue('--bg-color')); // 변수 값 얻기
theme.style.setProperty('--bg-color', 'green'); // 변수 값 변경
// 선택자 변수
element.style.getPropertyValue("--font-size");
element.style.setProperty("--font-size", 20);
```  

### Window.getComputedStyle() 
Window.getComputedStyle() 메소드는 인자로 전달받은 요소의 모든 CSS 속성값을 담은 객체를 회신합니다. 이 속성값들은, 해당 요소에 대하여 활성 스타일시트와 속성값에 대한 기본 연산이 모두 반영된 결과값입니다.  개별 CSS속성 값은 객체를 통해 제공되는 API 또는 CSS 속성 이름을 사용해서 간단히 색인화해서 액세스할 수 있습니다.


```jsx
var style = window.getComputedStyle(element[, pseudoElt]);
```
```jsx
let para = document.querySelector('p');
let compStyles = window.getComputedStyle(para);
para.textContent = 'My computed font-size is ' + compStyles.getPropertyValue('font-size') + ',\nand my computed line-height is ' + compStyles.getPropertyValue('line-height') + '.';
```


## 사용자 지정 속성 대안 값 

주어진 변수가 아직 정의되지 않았을 때, var() 를 이용하여 여러 개의 대체 변수를 정의할 수 있다. 이는 사용자 정의 요소(Custom Element)및 섀도우 돔(Shadow DOM)으로 작업할 때 유용하게 쓸 수 있다.

```css
.two {
  color: var(--my-var, red); /* --my-var가 정의되지 않았을 경우 red로 표시됨 */
}

.three {
  background-color: var(--my-var, var(--my-background, pink)); /* my-var와 --my-background가 정의되지 않았을 경우 pink로 표시됨 */
}

.three {
  background-color: var(--my-var, --my-background, pink); /* 유효하지 않음: "--my-background, pink" */
}
```






## 참조 
[Custom Properties](https://developer.mozilla.org/ko/docs/Web/CSS/Using_CSS_custom_properties)
[getComputedStyle](https://developer.mozilla.org/ko/docs/Web/API/Window/getComputedStyle)






