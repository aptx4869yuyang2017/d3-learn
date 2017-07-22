# My D3 Note

> Tutorials <http://alignedleft.com/tutorials/d3>

## Chaining methods

* One Link at a Time
* 理解 函数或则方法的意义：就是传进一个参数，返回一个对象
* 链式方法的概念  就是上一个返回对象 就是下一个方法处理的对象，处理过程传了一些参数
```flow
st=>start: object in
e=>end: resulet out
op1=>operation: Method 1
op2=>operation: Method 2
opn=>operation: Method n
st->op1(right)->op2(right)->opn(right)->e()
```
* 上个 method 的output 类型 必须 符合下个 method 的类型要求


## Binding data 绑定数据
```javascript
d3.select("body").selectAll("p")
    .data(dataset)
    .enter()
    .append("p")
    .text("New paragraph!");
```

## Using you data 使用数据
* ` .text(function(d) { return d; });` add text
* `.sytle(contibute, function())` 修改stytle

## Drawing divs 画 div 标签
```javascript
div.attr("class", "bar") .style("height", function(d) {
        return d * 5 + "px";
    });
```
* .attr()  赋予对象标签属性
* .sytle() 直接给 HTML 对象的 赋予 CSS 样式

## The power of data() 


## An SVG primer
* Element `<svg width="500" height="50">`
* shape `<rect x="0" y="0" width="500" height="50"/>`
* style 
    * fill - color 
    * stroke - 描边 也是 color 值
    * stroke-width
    * opacity
    * text propertiess font-family font-size
    * CSS `svg .pumpkin{ /* ... */ }`
* layering and drawing order
* transparency
* other tutorial 
    * [Pocket Guide to SVG](http://svgpocketguide.com/book/)
    * [An SVG Primer for Today’s Browsers](https://www.w3.org/Graphics/SVG/IG/resources/svgprimer.html)


## Drawing SVGs
* creat 
```javascript
// Height and width
var h = 50;
var w = 300;
var svg = d3.select("body").append("svg").attr("width", w).attr("height", h);
```
* Data-driven Shapes
```javascript
var circles = svg.selectAll("circle")
                 .data(dataset)
                 .enter()
                 .append("circle");

```
* attr()  增加属性
```javascript
circles.attr("cx", function(d, i) {
            return (i * 50) + 25;
        })
```
**i ** ：**i **is a numeric index value of the current element.  automatically populated
**d ** : must include d, even if you don't use **d** within your function


## Types of data
* JSON : indices are also surrounded by double quotation marks ""
* GeoJSON: optimized for storing geodata, **longitude is always listed before latitude**
```json
var geodata = {
    "type": "FeatureCollection",
    "features": [
        {
            "type": "Feature",
            "geometry": {
                "type": "Point",
                "coordinates": [ 150.1282427, -24.471803 ]
            },
            "properties": {
                "type": "town"
            }
        }
    ]
};
```

## Making a bar chart
第一个 demo
* 根据总宽度， **弹性调整 bar 的宽度**
```javascript
.attr("width", w / dataset.length - barPadding)
```
* 反向打印
```javascript
    .attr("y", function(d) {
        return h - 4 * d; //Height minus data value
```
* **颜色 由数据驱动**， 在 attr 的 rgb 值中添加函数
```javascript
    .attr("fill", function(d) {
        return "rgb(200, 200 ," + d * 10 + ")";
    });
```
* label 标签
```javascript
.attr("x", function(d, i) {
    return i * (w / dataset.length) + (w / dataset.length - barPadding) / 2;
    }) // (w / dataset.length) 单个 bar 的占地空间 (w / dataset.length - barPadding) 单个 bar 的宽度 
    //结果就是定位点放到了 每个 bar 的中间  
    //然后用居中对齐的方式放 label
```
## Making a scatterplot

## Scales

## Axes

## Transitions

