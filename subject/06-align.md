# CSS 컨텐트 정렬

## div를 가운데로

div width 값을 설정하고 margin:auto로 css를 작성한다. div가 중앙에 표시된다.

```css
      .center {
        margin: auto;
        width: 60%;
        border: 3px solid #73ad21;
        padding: 10px;
      }
```

```html
    <div class="center">
      <p>Hello World!</p>
    </div>
```

## div안의 text 가운데 정렬

text-align:center를 사용하여 컨텐트를 가운데 정렬한다.

```css
      .center2 {
        text-align: center;
        border: 3px solid green;
      }
```

```html
    <div class="center2">
      <p>This text is centered.</p>
    </div>
```

## 이미지 가운데 정렬

```css
      img {
        display: block;
        margin-left: auto;
        margin-right: auto;
      }
```

```html
    <img
      src="https://pbs.twimg.com/media/Essbh1PUYAMcoVx?format=jpg&name=small"
      alt="Paris"
      style="width: 40%;"
    />
```

## div 오른쪽 정렬

```css
      .right {
        position: absolute;
        right: 0px;
        width: 300px;
        border: 3px solid #73ad21;
        padding: 10px;
      }
```

```html
    <div class="right">
      <p>
        In my younger and more vulnerable years my father gave me some advice
        that I've been turning over in my mind ever since.
      </p>
    </div>
```

## float를 사용한 div 오른쪽 정렬

```css
      .float-right {
        float: right;
        width: 300px;
        border: 3px solid #73ad21;
        padding: 10px;
      }
```

```html
    <div class="float-right">
      <p>
        In my younger and more vulnerable years my father gave me some advice
        that I've been turning over in my mind ever since.
      </p>
    </div>
```

## padding을 이용한 컨텐트 수직 가운데 정렬

```css
.center3 {
  padding: 70px 0;
  border: 3px solid green;
}
```

```html
<div class="center">
  <p>I am vertically centered.</p>
</div>
```

## line-height를 이용한 컨텐트 가운데 정렬

```css
      .center4 {
        line-height: 200px;
        height: 200px;
        border: 3px solid green;
        text-align: center;
      }

      .center p {
        line-height: 1.5;
        display: inline-block;
        vertical-align: middle;
      }
```

```html
    <div class="center4">
      <p>I am vertically and horizontally centered.</p>
    </div>
```

## position과 transform을 이용한 수직 정렬

```css
      .center5 {
        height: 200px;
        position: relative;
        border: 3px solid green;
      }

      .center5 p {
        margin: 0;
        position: absolute;
        top: 50%;
        left: 50%;
        -ms-transform: translate(-50%, -50%);
        transform: translate(-50%, -50%);
      }
```

```html

    <div class="center5">
      <p>I am vertically and horizontally centered.</p>
    </div>
```

## flexbox를 사용한 수직 정렬

```css
      .flex-center {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 200px;
        border: 3px solid green;
      }
```

```html
    <div class="flex-center">
      <p>I am vertically and horizontally centered.</p>
    </div>
```

## Source

[https://codesandbox.io/s/bold-mcnulty-gx587?file=/align/css-align.html](https://codesandbox.io/s/bold-mcnulty-gx587?file=/align/css-align.html)
