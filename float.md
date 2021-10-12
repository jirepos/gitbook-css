# Float

float는 CSS에서 정렬을 하기 위해서 사용한다. 문서에 사진과 그림이 있을 때 그림을 왼쪽이나 오른쪽으로 띄워서 정렬하거나 할 때 사용한다.

* none - 뛰우지 않음
* left - 왼쪽에 뛰움
* right - 오른쪽에 뛰움
* initial - 기본값으로 설정함
* inherit - 부모로부터 상속함

> 절대 위치는 float 속성을 무시한다.

## 오른쪽에 이미지, 왼쪽에 텍스트

```css
      img {
        float: right;
      }
```

```html
<p>
      <img
        src="https://pbs.twimg.com/media/Essbh1PUYAMcoVx?format=jpg&name=small"
        alt="Pineapple"
        style="width: 170px; height: 170px; margin-left: 15px;"
      />
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus
      imperdiet, nulla et dictum interdum, nisi lorem egestas odio, vitae
      scelerisque enim ligula venenatis dolor. Maecenas nisl est, ultrices nec
      congue eget, auctor vitae massa. Fusce luctus vestibulum augue ut aliquet.
      Mauris ante ligula, facilisis sed ornare eu, lobortis in odio. Praesent
      convallis urna a lacus interdum ut hendrerit risus congue. Nunc sagittis
      dictum nisi, sed ullamcorper ipsum dignissim ac. In at libero sed nunc
      venenatis imperdiet sed ornare turpis. Donec vitae dui eget tellus gravida
      venenatis. Integer fringilla congue eros non fermentum. Sed dapibus
      pulvinar nibh tempor porta. Cras ac leo purus. Mauris quis diam velit.
    </p>
```

## div를 나란히 가로로 배치하기

```css
      div {
        float: left;
        padding: 15px;
      }

      .div1 {
        background: red;
      }

      .div2 {
        background: yellow;
      }

      .div3 {
        background: green;
      }
```

```html
    <div class="div1">Div 1</div>
    <div class="div2">Div 2</div>
    <div class="div3">Div 3</div>
```

## Source

[https://codesandbox.io/s/bold-mcnulty-gx587?file=/align/css-float.html:1525-1626](https://codesandbox.io/s/bold-mcnulty-gx587?file=/align/css-float.html:1525-1626)
