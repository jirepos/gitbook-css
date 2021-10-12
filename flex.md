# Flex

## Flex 개요

### Flex의 기본 마크업 구조

> flexbox는 가변 상자 레이아웃 모듈의 약칭으로 행이 됐건 열이 됐건 일차원 상에 사물을 배치할 경우 편리를 돕기 위해 마련되었다. flexbox를 사용하려면 당신이 진열하길 원하는 모든 요소의 부모 요소에 display: flex를 적용하고 나면 모든 직계 자식이 플렉스 항목이 된다. 우리는 간단한 예를 들어 이 점을 확인할 수 있다.

```html
<div class="container">
	<div class="item">helloflex</div>
	<div class="item">abc</div>
	<div class="item">helloflex</div>
</div>
```

div.container를 Flex Container라고 부르고 div.item들을 Flex item이라고 한다.

## Flex 속성

Flex속성은 다음과 같이 구분된다.

* 컨테이너에 적용하는 속성
* 아이템에 적용하는 속성

### Flex Container에 적용하는 속성

#### display:flex

**html**

```html
  <div class="wrapper">
    <div class="box1">하나</div>
    <div class="box2">둘</div>
    <div class="box3">셋</div>
    <div class="box4">넷</div>
    <div class="box5">다섯</div>
    <div class="box6">여섯</div>
  </div>
```

**CSS**

```css
      .wrapper {
        display: flex;
      }
      div {
        border-style: solid;
        background-color: beige;
      }
```

**결과** Flex 아이템들은 가로로 배치되고 내용물의 width 만큼 차지한다. 

#### flex-direction

아이템들이 배치되는 축의 방향을 결정한다. 메인축을 가로나 세로로 방향을 정한다. 기본값은 row이다. 위의 예제는 row가 적용되었다.

**row** 기본값. 아이템들이 가로로 배치된다.

**row-reverse** 역순으로 가로로 배치된다. 

**column** 세로 방향으로 배치된다.

**column-reverse** 아이템들이 역순으로 세로로 배치된다.

#### flex-wrap

아이템들을 한 줄에 담을 수 없을 때 줄을 바꿀 수 있게 할 수 있다.

**rowwrap** 기본값으로 줄넘김을 하지 않는다.

**wrap** 줄바꿈을 한다.

**wrap-reverse** 아이템들을 역순으로 배치하여 줄바꿈을 한다.

#### flex-flow

flex-direction과 flex-wrap을 한번에 지정할 수 있다. flex-direction, flex-wrap의 순으로 한 칸 띄고 쓴다.

#### 정렬

justify는 메인축(가로) 방향으로 정렬하고 align은 세로축(수직) 방향으로 정렬한다.

**justify-content**

**flex-start(기본값)**

아이템들을 시작점으로 정렬한다.

**CSS**

```css
      body {
        margin: 20px;
      }
      .wrapper {
        display: flex;
        justify-content: flex-start;
      }
      div {
        border-style: solid;
        background-color: beige;
      }
```

**html**

```html
    <div class="wrapper">
      <div>하나</div>
      <div>둘둘둘둘둘둘둘둘둘둘둘둘둘둘둘둘둘</div>
      <div>셋</div>
      <div>넷</div>
      <div>다섯</div>
      <div>여섯</div>
    </div>
```

**결과**

**flex-end**

아이템들을 시작점으로 끝점으로 정렬한다. flex-direction이 row일 때는 오른쪽, column일 때에는 아래이다.

```css
      .wrapper {
        display: flex;
        justify-content: flex-end;
      }
      div {
        border-style: solid;
        background-color: beige;
      }
```

```html
 <div class="wrapper">
      <div>하나</div>
      <div>둘둘둘둘둘둘둘둘둘둘둘둘둘둘둘둘둘</div>
      <div>셋</div>
      <div>넷</div>
      <div>다섯</div>
      <div>여섯</div>
    </div>
```

결과 

**center**

아이템들을 가운데로 정렬한다.

```css
      .wrapper {
        display: flex;
        justify-content: center;
      }
      div {
        border-style: solid;
        background-color: beige;
      }
```

결과

**space-between**

아이템들의 사이에 균일한 간격을 만들어 줍니다.

```
      .wrapper {
        display: flex;
        justify-content: space-between;
      }
      div {
        border-style: solid;
        background-color: beige;
      }
```

결과 

**space-around**

아이템들의 둘레(around)에 균일한 간격을 만들어 준다.

**space-evenly**

아이템들의 사이와 양 끝에 균일한 간격을 만들어 준다. IE와 Edge에선느 지원하지 않는다.

**align-items**

수직축 방향으로 아이템들을 정렬하는 속성이다.

**stretch**

아이템들이 수직축 방향으로 끝까지 쭈욱 늘어나다.

```css
      .wrapper {
        display: flex;
        align-items: stretch;
        /* align-items: flex-start; */
        /* align-items: flex-end; */
        /* align-items: center; */
        /* align-items: baseline; */
        height: 300px;
      }
```

**flex-start**

아이템들을 시작점으로 정렬한다. 

**flex-end**

아이템들을 끝으로 정렬한다.

**center**

아이템들을 가운데로 정렬한다.

**baseline**

아이템들을 텍스트 베이스라인 기준으로 정렬한다. 

**align-content**

flex-wrap이 설정된 상태에서 아이템들의 행이 2줄 이상 되었을 때의 수직축 방향 정렬을 결정하는 속성이다.

**stretch**

```css
 .wrapper {
        display: flex;
        flex-wrap: wrap;
        align-content: stretch;
        /* align-content: flex-start; */
        /* align-content: flex-end; */
        /* align-content: center; */
        /* align-content: space-between; */
        /* align-content: space-around; */
        /* align-content: space-evenly; */
        align-items: baseline;
        height: 300px;
      }
```

**flex-start**

**flex-end**

### Flex 아이템에 적용하는 속성

#### flex-basis

Flex 아이템의 기본 크기를 지정한다. row일 때는 너비, column일 때는 높이이다. width와 height 듣ㅇ에 사용하는 각종 단위를 사용할 수 있다. 별도로 설정하지 않으면 컨텐츠의 크기가 된다. content는 컨텐츠의 크기로, width를 따로 설정하지 않은 경우와 같다.

**auto**

auto는 해당 아이템의 width 값을 사용한다. width를 따로 설정하지 않으면 컨텐츠의 크기가 된다.

```css
      .wrapper {
        display: flex;
        height: 300px;
      }
      .item {
        	flex-basis: auto; /* 기본값 */
          /* flex-basis: 0; */
          /* flex-basis: 50%; */
	        /* flex-basis: 300px; */
	        /* flex-basis: 10rem; */
	        /* flex-basis: content; */
      }
```

```html
  <div class="wrapper">
      <div class="item">하나</div>
      <div class="item">둘둘둘둘둘둘둘둘둘둘둘둘둘둘둘둘둘</div>
      <div class="item">셋</div>
      <div class="item">넷</div>
      <div class="item">다섯</div>
      <divclass="item">여섯</div>
    </div>
```

**flex-basis: 0**

#### flex-grow 늘리기

flex-grow는 아이템이 flex-basis의 값보다 커질수 있는지를 결정한다.

flex-grow에는 숫자 값이 들어간다. 0 보다 큰 값이 세팅이 되면 해당 아이템이 유연한 박스로 변하고 원래의 크기보다 크게 되며 빈 공간을 메운다. 기본값은 0이다.

flex-grow 값이 0일 때

```css
     .wrapper {
        display: flex;
        height: 300px;
      }
      .item {
        flex-grow: 0;
      }
```

flex-grow 값이 1일 때

flex-grow에 들어가는 숫자는 아이템들이 flex-basis를 제외한 여백 부분을 flex-grow에 지정된 숫자의 비율로 나누어진다.

#### flex-shrink 줄이기

아이템이 flex-basis 값보다 작아질 수 있는지를 결정한다. 숫자값이 0보다 큰 값이 설정되면 해당 아이템이 유연한 박스로 변하고 flex-basis보다 작아진다. 기본값은 1이다. 기본값이 1이기 때문에 아이템이 flex-basis보다 작아진다.

```css
      .wrapper {
        display: flex;
        height: 300px;
      }
      .item {
        flex-basis: 150px;
        flex-shrink: 1;
      }
```

#### 고정폭

flex-shrink를 0으로 설정하면 아이템의 크기가 flex-basis보다 작아지지 않기 때문에 고정폭의 컬럼을 만들 수 있다. 고정크기는 width로 설정한다.

```css
      .wrapper {
        display: flex;
        height: 300px;
      }
      .item:nth-child(2) {
        	flex-shrink: 0;
	        width: 500px;
      }
```

#### flex

flex-grow, flex-shrink,flsx-basis를 한 번에 쓸 수 있다.

```css
.item {
	flex: 1;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
	flex: 1 1 auto;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
	flex: 1 500px;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 500px; */
}
```

#### align-self

align-items가 전체 아이템의 수직출 방향 정렬이면 align-self는 해당 아이템의 수직축 방향 정렬이다.

```css
      .wrapper {
        display: flex;
        
      }
      .item {
        /* align-self: auto; */
        /* align-self: stretch; */
	      align-self: flex-start; 
	      /* align-self: flex-end; */
	      /* align-self: center; */
	      /* align-self: baseline; */
      }
```

아래는 flex-start를 적용한 모습이다. 

#### 기타

배치 순서를 바꾸기 위해서 order를 사용한다. z-index로 Z축 정렬을 할 수 있다.

## 소스

codesandbox.io에 이 글과 관련한 소스들이 있다. [https://codesandbox.io/s/bold-mcnulty-gx587](https://codesandbox.io/s/bold-mcnulty-gx587)

## References

[Flex를 배워보자](https://studiomeal.com/archives/197)
