# freeCodeCamp笔记

## CSS基础
#### 样式方面
- 文本颜色 color
- font-size, font-family(一组字体，从左到右备选)
#### 选择器
- h2 {}
- .clearfix {}
- \#cat-photo-element {}
- div[, >+]p {}
- [target=_blank] {}
- :first-line {}

#### 优先级
通用 < 元素（类型） < 类 < 属性 < 伪类 < ID < 内联样式

#### 单位长度
px: 像素 em: em是相对长度单位。相对于当前对象内文本的字体尺寸
rem: 根em, 相对的是HTML根元素

## ES6
#### const, var和let的区别
- var不在函数里的声明挂载在window里（普通的for循环什么的都属于函数外，里面的定义可以在外使用），所以所有在外的声明是全局变量，而let更像是其他语言普通函数的变量
- 函数内部声明不带var时，声明的变量是全局变量
- var可以重复声明而let会报错
- const声明必须赋值，给定引用地址，引用地址不可变，地址里的内容可变

#### 箭头函数语法糖
- () => {}
- () => value
- 当返回一个对象是可以用（）包起来 ```(x, y) => ({x: x, y: y})```

#### 解构赋值
```javascript
var voxel = {x: 3.6, y: 7.4, z: 6.54 };
// 或者const { x, y, z } = voxel;
const { x : a, y : b, z : c } = voxel;
```
#### 模板字面量
```javascript
const person = {
  name: "Zodiac Hasbro",
  age: 56
};
const greeting = `Hello, my name is ${person.name}!
```
#### 简洁的对象字面量声明
```javascript
// 原写法
const getMousePosition = (x, y) => ({
  x: x,
  y: y
});
// 简洁写法
const getMousePosition = (x, y) => ({ x, y });
```
#### 简洁的函数声明
```javascript
const person = {
  name: "Taylor",
  sayHello() { // 原写法 sayHello: function() {
    return `Hello! My name is ${this.name}.`;
  }
};
```
#### class关键字定义构造函数
```javascript
var SpaceShuttle = function(targetPlanet){
  this.targetPlanet = targetPlanet;
}
var zeus = new SpaceShuttle('Jupiter');
// ============相同=======================
class SpaceShuttle {
  constructor(targetPlanet){
    this.targetPlanet = targetPlanet;
  }
}
const zeus = new SpaceShuttle('Jupiter');
```
#### 对象属性
```javascript
function Bird(name) {
  this.name = name; // 自身属性 
}
let duck = new Bird("Donald");
for (let property in duck); // 遍历所有属性
if(duck.hasOwnProperty(property)); // 判断自身属性
```