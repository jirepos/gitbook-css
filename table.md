# Table

부모테그에 display:table을 선언해 주고, 자식테그에 table-cell을 선언해 주면 갯수가 몇개가 되던 동일한 간격으로 영역을 가지게 된다.

```html
  <div id="body">
    <div id="navi">1</div>
    <div id="content">2</div>
    <div id="sidebar">3</div>
  </div>
```

```css

    #body { 
      width: 100%;
      display: table;
    }
    #navi , #content, #sidebar { 
      display: table-cell;
    }

    #navi {
      width:200px;
      background-color: cadetblue;
    }
    #content { 
      background-color:cornflowerblue; 
    }

    #sidebar { 
      width: 200px; 
      background-color: beige;
    }
```

## References

[3단 레이이아웃](https://heeestorys.tistory.com/695)
