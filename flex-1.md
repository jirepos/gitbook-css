# Flex를 이용한 입력폼 만들기

## 간단한 입력 폼

아래 그림과 같은 입려폼을 만들고자 한다. 

flex-direction 값을 column으로 설정하고 item의 width를 적당한 값으로 설정한다. input 요소의 넓게 보이도도록 height를 적당한 높이로 설정한다.

```css
      .wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 10px;
        height: 200px;
      }
      .item {
        width: 500px;
        flex-basis: 60px;
      }
      .input {
        width: 100%;
        height: 40px; /* input 높이 설정 */ 
      }
```

Flex Container에 class 속성에 wrapper를 설정하고 아이템에 클래스 item을 설정한다.

```html
<div class="wrapper">
      <div class="item">
        <input
          class="input"
          type="text"
          placeholder="Input your ID or email."
        />
      </div>
      <div class="item">
        <input class="input" type="text" placeholder="Input your password." />
      </div>
    </div>
```

## 레이블이 있는 입력폼

다음과 같이 INPUT 요소 위에 레이블이 있는 입력폼을 만들어 보자.

Flex Item에 div를 만들고 그 안에 두개의 Div를 만든다.

```html
 <div class="wrapper">
      <div class="item">
        <div>
          <div>ID:</div>
          <div>
            <input
              class="input"
              type="text"
              placeholder="Input your ID or email."
            />
          </div>
        </div>
      </div>
      <div class="item">
        <div>
          <div>Password:</div>
          <div>
            <input
              class="input"
              type="text"
              placeholder="Input your password."
            />
          </div>
        </div>
      </div>
    </div>
```

## 왼쪽에 레이블이 있는 입력 폼

아래 그림과 같이 레이블이 왼쪽에 있는 형태로 만들어 보자.

첫번째 div에는 width로 넓이를 고정한다. 두번째 div에는 넓이를 100%로 설정한다.

```css

      .inner-wrapper {
        display: flex;
        flex-direction: row;
      }
      .inner-item:nth-child(1) {
        margin: auto;
        width: 100px;
      }
      .inner-item:nth-child(2) {
        width: 100%;
      }
```

CSS에서 정의한 class를 적용한다. div 요소 안의 컨텐트를 수직적으로 가운데로 설정하려면 margin: auto를 설정한다.

```html
   <div class="wrapper">
      <div class="item">
        <div class="inner-wrapper">
          <div class="inner-item">ID:</label></div>
          <div class="inner-item">
            <input
              class="input"
              type="text"
              placeholder="Input your ID or email."
            />
          </div>
        </div>
      </div>
      <div class="item">
        <div class="inner-wrapper">
          <div class="inner-item">Password:</div>
          <div class="inner-item">
            <input
              class="input"
              type="text"
              placeholder="Input your password."
            />
          </div>
        </div>
      </div>
    </div>
```

## Source

[https://codesandbox.io/s/bold-mcnulty-gx587?file=/flex21-login.html](https://codesandbox.io/s/bold-mcnulty-gx587?file=/flex21-login.html)
