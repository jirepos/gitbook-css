# div를 전체 화면으로 설정 


width와 height를 100%로 설정하면 전체화면이 될 것만 같지만 그렇지 않다. 

* %는 부모 요소 길이의 몇%를 차지할 것인지 나타내기 때문에
* 먼저는 부모 요소의 길이가 설정되어 있어야 한다. 



다음은 전체화면이 되지 않는다. 

```html
<html>
  <head>
    <style>
      .container {
        width: 100%;
        height: 100%;
        background: pink;
      }
    </style>
  </head>
  <body>
    <div class="container">100% 인가</div>
  </body>
</html>
```


container의 부모 요소인 body와 html의 width, height를 지정해줘야 한다. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Document</title>
    <style>
        html, body { 
            margin: 0px;
            background-color: yellow;
            height: 100%;  
            width: 100%;  
        }
        .main {
            background-color: rgb(190, 123, 219);
            height: 100%; 
            width: 100%;
        }
    </style>
</head>
<body>
        <div class="main">
            main
        </div>
</body>
</html>
```