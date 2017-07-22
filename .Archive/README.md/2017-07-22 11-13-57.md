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

## Using you data
* ` .text(function(d) { return d; });`

## Drawing divs
* Back to the Bars
* Setting Styles
* 


