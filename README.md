* JQuery 常见的选择器，以及 api 的用法

```
<!DOCTYPE html>
<html lang="en">
<head>
  <script src="https://cdn.bootcss.com/jquery/2.2.3/jquery.js"></script>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>
  <div class="top">
    <div class="tab">
    <div class="child">1</div>
    <div class="child">2 yu</div>
    <div class="child">3 yu</div>
    <div class="child">4</div>
    <p class="ok">ok</p>
    </div>
  </div>

  <script>
    $('.child').eq(2)//3yu      获取第三个child
    $('.child').next()//2yu || 3yu|| 4 || ok       匹配到child后的同辈元素
    $('.child').prev()//1 || 2yu || 3yu      匹配到child前的同辈元素
    $('.child').nextAll()//2yu & 3yu & 4 & ok      匹配child后所有的同辈元素
    $('.child').prevAll()//3yu & 2yu & 1      匹配child前所有同辈元素
    $('.child').siblings()//1 & 2yu & 3yu & 4 & ok      获得匹配元素集合中每个元素的兄弟元素
    $('.child').parent()//tab      取得匹配元素集合中,每个元素的"父元素"
    $('.child').parents()//tab & top & body & html      获得集合中每个匹配元素的"祖先元素"
    $('.top').children()//tab      获得匹配元素集合中每个元素的子元素
    $('.top').find('p')//p      查找符合选择器的后代元素
    $('.child').filter(function(index, node){
	    return node.innerText.search('yu') > -1
    })//2yu & 3yu      筛选当前结果集中符合条件的对象
    $('div').has('.ok')//top & tab      筛选匹配元素集合中的那些有相匹配的选择器或DOM元素的后代元素
    $('.ok').is('.ok')//ture      判断当前匹配的元素集合中的元素，是否为一个选择器，Dom元素，或者jquery对象，如果这些元素至少一个匹配给定的参数，则返回true.
  </script>
</body>
</html>
```
