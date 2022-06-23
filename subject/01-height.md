# height와 width



## height
height는 inline 요소인 table rows, thead, tfoot, tbody를 제외하고 모든 요소에 적용 

* content 영역만의 높이만을 의미, margin, padding, border는 적용되지 않음
* min-height, max-height는 height 속성을 무시한다. 즉, height와 min-height 속성이 동시에 설정되는 경우, min-height가 적용된다. 


**속성값**     

* auto : 기본값, 브라우저가 높이를 계산함. 부모요소에 높이값을 따로 명시하지 않으면 auto가 적용. 그 안의 내용 높이 만큼 커진다. 
  * 내용(content)이 없다면 부모도 높이를 지니지 않는다. 
* % : 컨테이너 블록에 비례한 높이, 부모가 300px일때 100%로 설정하면 300px로 설정된다. 





## width 

### 상대 넓이: %
엘리먼트의 너비가 가용 너비에 비례해서 커지거나 작아지게 하고 싶다면 %를 사용한다. 

* 용 너비란 박스 모델 상에서 부모 엘리먼트의 켄텐트 박스 크기를 의미한다. 
* 가용 너비가 400px인 상황에서, width: 50%를 설정하면 해당 엘리먼트의 너비는 200px이 된다. 


* **상대값으로 너비를 설정해줄 때 CSS 초보자들이 범하기 쉬운 실수가 margin이 설정된 엘리먼트를 대상으로 width: 100%를 설정하는 것인데,의도치 않게 자식 엘리먼트가 부모 엘리먼트 밖으로 삐져나오게 된다.**

### auto 
width 속성을 명시하지 않으면 auto가 적용된다. 

* auto 키워드를 사용하면 브라우저가 해당 엘리먼트의 width 속성값을 자동으로 계산해 준다. 

* 계산 알고리즘은 부모 엘리먼트로 부터 주어진 가용 너비에서 margin 크기를 제외한 너비를 width 속성값으로 사용한다. 

## min-content 

min-content 키워드와 max-content 키워드는 상대값과 반대로 가용 공간이 아닌 담고 있는 컨텐트에 의해 width 속성값이 결정된다. 

min-content 키워드는 엘리먼트의 너비를 줄일 수 있는 만큼 최소로 줄이고 싶을 때 사용합니다. 최소 너비는 해당 엘리먼트가 담고 있는 컨텐트에 의해 좌우가 된다. 

```css
p {
  width: min-content;
  margin: 10px;
  background: yellow;
}
```


### max-content

max-content 키워드는 min-content 키워드와 정반대로 엘리먼트의 너비를 최대한 늘이고 싶을 때 사용한다. 최대 너비 역시 해당 엘리먼트가 담고 있는 컨텐트에 의해 좌우가 된다. 


### fit-content
fit-content 키워드는 max-content 키워드와 auto 키워드의 하이브리드 모드처럼 작동한다. 

가용 너비이 부족하지 않는 경우에는 max-content 키워드처럼 담고 있는 컨텐트의 최대 너비를 엘리먼트의 width 속성값으로 사용한다. 그러나 가용 너비이 부족하다면 auto 키워드처럼 가용 너비에서 여백(margin)을 제외한 너비를 엘리먼트의 width 속성값으로 사용한다. 


