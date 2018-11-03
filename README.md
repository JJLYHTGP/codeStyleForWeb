[TOC]
# 前端代码风格
## 1 前言

从2017年9月开始接触前端，但是有意识地关注代码规范是从2018年5月在某大厂实习的时候才开始的。规范的代码提高了可读性和可维护性，不知不觉中也能提高了写代码的速度。

## 2 代码风格

### 2.1 CSS规范

#### 代码规范

###### 基本规范

1. 缩进使用4个空格

   ```css
   /* bad */
   .jjly {
     width: 100%;
     height: 100%;
   }
   
   /* good */
   .jjly {
       width: 100%;
       height: 100%;
   }
   ```

2. 每个声明块的左花括号前面添加一个空格

   ```css
   /* bad */
   .jjly{
       border: none;
   }
   
   /* good */
   .jjly {
       border: none;
   }
   ```

3. 样式选择器，属性名，属性值关键字全部使用小写

   ```css
   /* bad */
   .JJLY {
       WIDTH: 200PX;
   }
   
   /* good */
   .jjly {
       width: 200px;
   }
   ```


###### 选择器规范

1. 为选择器中的属性添加双引号

   ```css
   /* bad */
   .jjly[type=text] {
       padding: 0;
   }
   
   /* good */
   .jjly[type="text"] {
       padding: 0;
   }
   ```

2. 选择器层级建议不要超过3级

   ```css
   /* bad */
   .main .content .my-wrap .jjly  .container span {
       /* ... */
   }
   
   /* good */
   .jjly .container span {
       /* ... */
   }
   ```

3. 避免使用id选择器、通配符选择器

4. 选择器分组时，将选择器单独放一行

   ```css
   /* bad */
   .jjly, .htgp {
       /* ... */
   }
   
   / * good */
   .jjly,
   .htgp {
       /* ... */
   }
   ```

###### 属性规范

1. 合理应用border: 0与border: none

   参考: [Should I use 'border: none' or 'border: 0'?](https://stackoverflow.com/questions/2922909/should-i-use-border-none-or-border-0)

2. 属性值十六进制数使用简写

   ```css
   /* bad */
   .jjly {
       color: #ffffff;
   }
   
   /* good */
   .jjly {
       color: #fff;
   }
   ```

3. 不要为0指明单位

   ```css
   /* bad */
   .jjly {
       width: 0px;
   }
   
   /* good */
   .jjly {
       width: 0;
   }
   ```

4. 属性顺序：建议相关的属性放在一组，并按照下面的顺序排列：

   - 布局定位属性：display / position / float / clear / visibility / overflow
   - 自身属性：width / height / margin / padding / border / background
   - 文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word
   - 其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …

   由于定位可以从正常文档流中移除元素，并且还能覆盖盒模型属性，因此写在前面。而自身属性决定了组件的尺寸和位置，文本属性和其他属性改变细节样式，因此这样排序。

   ```css
   .jjly {
       display: block;
       position: relative;
       float: left;
       width: 100px;
       height: 100px;
       margin: 0 10px;
       padding: 20px 0;
       font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;
       color: #333;
       background: rgba(0,0,0,.5);
       -webkit-border-radius: 10px;
       -moz-border-radius: 10px;
       -o-border-radius: 10px;
       -ms-border-radius: 10px;
       border-radius: 10px;
   }
   ```

5. 可简写的属性(background、font)进行显式声明

   ```css
   /* bad */
   .jjly {
       font: normal 12px;
       background: #fff;
   }
   
   /* good */
   .jjly {
       font-size: 12px;
       font-style: normal;
       background-color: #fff;
   }
   ```

###### 命名规范

1. 自定义font-family命名与业务相关

   ```css
   /* bad */
   @font-face {
       font-family: somefont;
   }
   
   /* good */
   @font-face {
       font-family: jjly-font;
   }
   ```

#### 注释规范

#### less规范

#### 重置样式

#### 媒体查询

#### 移动端常用私有属性







 

 



## 3. 参考资料

> [Aotu.io - 前端代码规范](https://guide.aotu.io/docs/)













如果对当前规范有更好的建议请继续往下添加~

基本规范

选择器规范

属性规范

媒体查询（Media query）规范

注释规范

命名规范

参考资料

基本规范

缩进使用 4 个空格

 

/* bad */

.mod-example {

  padding-left: 15px;

}

 

/* good */

.mod-example {

​    padding-left: 15px;

}

 

在每个声明块的左花括号前添加一个空格

 

/* bad */

.mod-example{

​    padding-left: 15px;

}

/* good */

.mod-example {

​    padding-left: 15px;

}

 

声明块的右花括号应当单独成行

/* bad */

.mod-example {

​    padding-left: 15px;}

/* good */

.mod-example {

​    padding-left: 15px;

}

每条声明语句的 : 后应该插入一个空格，前面无空格

 

/* bad */

.mod-example {

​    padding-left:15px;

}

/* good */

.mod-example {

​    padding-left: 15px;

}

 

所有声明语句都以分号结尾，不能省略不写

 

/* bad */

.mod-example {

​    padding-left: 15px

}

/* good */

.mod-example {

​    padding-left: 15px;

}

选择器规范

为选择器分组时，将单独的选择器单独放在一行

 

/* bad */

.selector, .selector-secondary {

​    padding-left: 15px;

}

 

/* good */

.selector,

.selector-secondary {

​    padding-left: 15px;

}

 

为选择器中的属性添加双引号

 

/* bad */

.selector[type=text] {

​    padding-left: 15px;

}

 

/* good */

.selector[type="text"] {

​    padding-left: 15px;

}

 

建议选择器层级不要超过3级

 

/* bad */

.main .top .left .mod-a .content .detail {

 padding-left: 15px;

}

.main .top .left .mod-a .content .detail {

​    padding-left: 15px;

}

 

/* good */

.mod-a .content .detail {

​    padding-left: 15px;

}

 

属性规范

属性顺序

建议相关的属性说明放在一组，并按照下面的顺序排列：

 

定位（position、left、right、top、bottom、z-index）

盒子模型（display、float、width、height、margin、padding、border、border-radius）

排印（font、color、background、line-height、text-align）

由于定位可以从正常的文档流中移除元素，并且还能覆盖盒模型相关的样式，因此排在首位。而盒模型决定了组件的尺寸和位置，所以排第二位。排印只是影响元素的细节样式变化，所以放第三位。

 

ps:上述所说属于完美情况，但实际我们开发中调样式时经常直接往后追加，导致属性顺序杂乱。后续可以实现一个webpack loader去专门做这个事情·

/* bad */

.mod-example {

​    font: normal 13px "Helvetica Neue", sans-serif;

​    display: block;

​    position: absolute;

​    z-index: 100;

​    width: 100px;

​    height: 100px;

​    border: 1px solid #ccc;

​    top: 0;

​    bottom: 0;

​    left: 0;

​    right: 0;

​    line-height: 1.5;

​    text-align: center;

}

 

/* good */

.mod-example {

​    /* 定位 */

​    position: absolute;

​    top: 0;

​    right: 0;

​    bottom: 0;

​    left: 0;

​    z-index: 100;

​    /* 盒模型 */

​    display: block;

​    float: right;

​    width: 100px;

​    height: 100px;

​    margin: 15px auto;

​    padding: 10px 15px;

​    border: 1px solid #ccc;

​    /* 排印 */

​    font: normal 13px "Helvetica Neue", sans-serif;

​    line-height: 1.5;

​    color: #333;

​    background-color: #f5f5f5;

​    text-align: center;

}

简写形式的属性声明

对于 background 和 font 这两个简写形式的属性声明，要么就显式声明所有的值，要么就不要使用简写形式。

 

/* bad */

.mod-example {

​    font: normal 13px;

​    background: #f5f5f5;

​    background: url(x.jpg);

}

 

/* good */

.mod-example {

​    font-style: normal;

​    font: 13px;

​    background-color: #333;

​    background-image: url(image.jpg);

}

 

0 和 单位

省略 “0” 值后面的单位。不要在 0 值后面使用单位，除非有值。

 

/* bad */

.mod-example {

​    padding-left: 0px;

}

 

/* good */

.mod-example {

​    padding-left: 0;

}

颜色值十六进制表示法

在可能的情况下，使用 3 个字符的十六进制表示法，并始终使用小写的十六进制数字

 

/* bad */

.mod-example {

​    color: #cccccc;

​    background-color: #eeee;

}

 

/* good */

.mod-example {

​    color: #ccc;

​    background-color: #efefef;

}

 

应避免16进制表示法与rgb表示法混用的情况，并优先使用16进制表示法，除非需要添加背景透明度如rgba情况

 

/* bad */

.example-part1 {

​    color: #efefef;

}

.example-part2 {

​    color: rgb(0,0,0);

}

 

/* good */

.example-part1 {

​    color: #efefef;

}

.example-part2 {

​    color: #ededed;

}

 

 

小数

对于使用到小数的情况，省略前边的 0

 

/* bad */

.mod-example {

​    opacity: 0.5;

}

/* good */

.mod-example {

​    opacity: .5;

}

 

引号

属性选择器或属性值用双引号 "" 括起来，而 URI 值 url() 不要使用任何引号

 

/* bad */

.mod-example {

​    font-family: open sans, arial, sans-serf;

​    background-image: url('//xxxxx/image.jpg');

}

 

/* good */

.mod-example {

​    font-family: "open sans", arial, sans-serf;

​    background-image: url(//xxxxx/image.jpg);

}

 

自定义 font-family

对于自定义的 font-family 命名，必须使用业务域名前缀作为名字的开始，例如自定义字体：

 

/* bad */

@font-face {

​    /* 业务自定义字体 */

​    font-family: icon-font;

​    src: url(//[at.alicdn.com/t/font_1426561436_144421x.ttf](http://at.alicdn.com/t/font_1426561436_144421x.ttf));

}

/* good */

@font-face {

​    /* 业务自定义字体 */

​    font-family: rongshu-iconfont;

​    src: url(//[at.alicdn.com/t/font_1426561436_144421x.ttf](http://at.alicdn.com/t/font_1426561436_144421x.ttf));

 

}

 

iconfont资源的引用：

@font-face {

 

 

​    font-family: rongshu-iconfont;

​    src: url('*.eot'); /* IE9*/

​    src: url('*.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */

​    url('*.woff') format('woff'), /* chrome、firefox */

​    url('*.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/

​    url('*.svg#iconfont') format('svg'); /* iOS 4.1- */

}

 

 一般情况移动客户端只需引用ttf文件就可以了

媒体查询（Media query）规范

媒体查询建议根据需要采用下面两种组织形式：

 

将媒体查询放在尽可能相关规则的附近，不要放在文档底部，否则容易被后来维护的人遗忘

媒体查询针对每一个种屏幕（大、中、小）的分别单独组织为一个文件

Example1:

 

.element {

}

.element-avatar {

}

.element-selected {

}

 

@media (min-width: 480px) {

 .element {

​    }

 .element-avatar {

​    }

 .element-selected {

​    }

}

Example2:

 

/* base.css */

 

.element {

}

.element-avatar {

}

.element-selected {

}

/* base-media-small.css */

 

@media (min-width: 480px) {

 .element {

​    }

 .element-avatar {

​    }

 .element-selected {

​    }

}

注释规范

代码注释

代码是由人来编写和维护的。保证你的代码是描述性的，包含好的注释，并且容易被他人理解。好的代码注释传达上下文和目标。不要简单地重申组件或者 class 名称。

 

/* bad */

 

/* Modal header */

.modal-header {

}

 

/* good */

 

/* Wrapping element for .modal-title and .modal-close */

.modal-header {

}

文件注释

文件注释，即声明在文件头部，描述文件的元信息，表明这个文件的作用是什么，如下例子：

 

/** * 这个文件的作用是什么，巴拉巴拉 */

body {

​    color: red;

}

 

命名规范

小写字母加连字符（不是下划线，也不是驼峰命名法）

 

/* bad */

.mod_example {

​    padding-left: 15px;

}

.modExample {

​    padding-left: 15px;

}

 

/* good */

.mod-example {

​    padding-left: 15px;

}







如果有更好的建议请继续往下添加~

基本规范

代码规范

命名规范

注释规范

参考链接

基本规范

缩进

统一使用 4 格缩进，目前咱们大多还是使用的 4 格缩进。

 

// bad

function foo() {

∙∙let name;

}

 

// bad

function bar() {

∙let name;

}

 

// good

function baz() {

∙∙∙∙let name;

}

引号

统一使用单引号

 

编码

统一使用 utf-8 编码

 

单行字符长度限制

单行代码字符长度尽量不超过 140 个字符

 

理由：代码更加清晰，便于阅读

 

建议使用字面量来代替构造函数

// bad

const arr = new Array();

const obj = new Object();

 

// good

const items = [];

const obj = {};

 

代码规范

对象

不要使用保留字 reserved words 作为对象属性，IE8 下不支持。参考

 

// bad

const superman = {

​    class: 'superhero'

};

// good

const superman = {

​    className: 'superhero'

};

数组

使用 Array#push 为数组添加元素

 

const someStack = [];

 

// bad

someStack[someStack.length] = 'item';

 

// good

someStack.push('item');

 

字符串

超过140个字符的字符串应该使用字符串连接换行，

 

// bad

const errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';

 

// good

const errorMessage = 'This is a super long error that was thrown because ' +

​    'of Batman. When you stop to think about how Batman had anything to do ' +

​    'with this, you would get nowhere fast.';

函数

不要在非函数块（if, while 等）里声明函数，如有需要，可以把函数赋值给一个变量。

 

// bad

if (currentUser) {

​    function test() {

​        console.log('Nope.');

​    }

}

 

// good

let test;

if (currentUser) {

​    test = () => {

​        console.log('Yup.');

​    };

}

 

绝对不要把参数命名为 arguments, 这将会覆盖arguments 对象.

 

// bad

function foo(name, options, arguments) {

​    // ...

}

 

// good

function foo(name, options, args) {

​    // ...

}

属性

访问对象的属性时，尽可能使用 .。eslint: dot-notation jscs: requireDotNotation

 

const superman = {

​    age: 28,

};

 

// bad

const age = luke['age'];

 

// good

const age = luke.age;

变量

总是使用 let 或 const 来声明变量，如果不这么做将导致产生全局变量，我们要避免污染全局命名空间。参考：no-undef prefer-const

 

// bad

superPower = new SuperPower();

 

// good

const superPower = new SuperPower();

 

 

推荐使用多个 let 或 const 声明多个变量，现在构建工具已经帮我们做了很多优化。

 

理由：方便增删；多 let 或者 const 可以更好的帮助养成良好的习惯，而不发生遗漏而导致全局变量的风险。在调试的时候也可以使用调试器遍历每个声明，而不是一次跳过所有声明。

 

// bad

// (与下面比较则更难快速找出问题错在)

const items = getItems(),

​    goSportsTeam = true;

​    dragonball = 'z';

 

// good

const items = getItems();

const goSportsTeam = true;

const dragonball = 'z';

条件表达式和等号

尽量使用 === 和 !==

 

条件表达式的强制类型转换遵循以下规则：

 

对象 被计算为 true

undefined 被计算为 false

null 被计算为 false

布尔值 被计算为 布尔的值

数字 如果是 +0, -0, or NaN 被计算为 false , 否则为 true

字符串 如果是空字符串 '' 则被计算为 false, 否则为 true

0, 值为 0 时，要特别注意

块

不要省略花括号

 

// bad

if (test)

​    return false;

 

// bad

if (test) return false;

 

// good

if (test) {

​    return false;

}

花括号后应该换行

 

// bad

function (test) { return false; }

 

// good

function() {

​    return false;

}

空白

操作符之间需要有空格

 

// bad

const x=y+5;

 

// good

const x = y + 5;

 

三元操作符前后都要加空格

 

// bad

const isRight = result === 0 ? false:true;

 

// good

const isRight = result === 0 ? false : true;

 

 

函数空格

 

// bad

// 多参数时逗号后需要加空格

function sayHi(a,b) {

}

// 花括号前需要加空格

function sayHi(a,b){

}

// 参数两边不需要加空格

function sayHi( a, b) {

}

// 函数名前不需要加空格

function sayHi (a,b) {

}

// good

function sayHi(a, b) {

}

 

 

块级代码 (if, else, for 等)

 

// bad

if(isSuperMan) {

​    sayHi ();

}

 

// good

if (isSuperMan) {

​    sayHi();

}

 

对象

 

// bad

const foo = {clark: 'kent'};

 

// good

const foo = {

​    clark: 'kent',

};

 

 

key, value 之间只需要一个空格，因为这样更加自然与易读。

 

// bad

{

​    name:            'short',

​    loooooooongName: 'long'

};

 

// good

{

​    name: 'short',

​    loooooooongName: 'long'

};

​         

 

避免使用过长的链式调用；调用比较长时建议使用换行和缩进来组织结构

 

// bad

$('#items').find('.selected').highlight().end().find('.open').updateCount();

 

// good

$('#items')

​    .find('.selected')

​      .highlight()

​      .end()

​    .find('.open')

​      .updateCount();

 

逗号

逗号后置

 

// bad

const story = [

​      once

​    , upon

​    , aTime

];

 

// good

const story = [

​    once,

​    upon,

​    aTime,

];

 

不要加多余的逗号，这可能会在 IE 下引起错误，同时如果多一个逗号某些 ES3 的实现会导致数组长度加1。

 

// bad

const hero = {

​    firstName: 'Ada'

  , lastName: 'Lovelace'

  , birthYear: 1815

  , superPower: 'computers'

};

 

// good

const hero = {

​    firstName: 'Ada',

​    lastName: 'Lovelace',

​    birthYear: 1815,

​    superPower: 'computers',

};

类型转换

在语句的开始执行类型转换

建议使用强制类型转换

 // bad

 const totalScore = new String(this.reviewScore); // typeof totalScore is "object" not "string"

 

 // bad

 const totalScore = this.reviewScore + ''; // invokes this.reviewScore.valueOf()

 

 // bad

 const totalScore = this.reviewScore.toString(); // isn’t guaranteed to return a string

 

 // good

 const totalScore = String(this.reviewScore);

对数字使用 parseInt 并且总是带上类型转换的基数，备注：parseFloat 方法没有基数参数

 

const inputValue = '4';

 

// bad

const val = new Number(inputValue);

 

// bad

const val = +inputValue;

 

// bad

const val = inputValue >> 0;

 

// bad

const val = parseInt(inputValue);

 

// good

const val = Number(inputValue);

 

// good

const val = parseInt(inputValue, 10);

 

布尔值:

 

const age = 0;

 

// bad

const hasAge = new Boolean(age);

 

// good

const hasAge = Boolean(age);

 

// best

const hasAge = !!age;

 

命名规范

原则

所有的命名必须有语义，所以永远不要使用单个字符命名。

 

变量

变量声明必须使用 const 或 let, 命名规范统一为小驼峰命名法：即第一个单词首字母小写，其余单词的首字母大写。

 

// dirty

eventType = 'click';

 

// bad

const eventtype = 'click';

 

// bad

const EventType = 'click';

 

// good

const eventType = 'click';

对象字面量命名使用小驼峰

 

// bad

const Base = {

​    isOnline: function() {

​    // ...

  }

};

return Base;

 

// good

const base = {

​    isOnline: function() {

​    // ...

  }

};

return base;

常量

常量的命名使用全大写字母，多单词使用下划线分开，例如：

 

// good

const WELCOME_TEXT = 'Hello World';

构造函数/类

构造函数/类使用大驼峰命名，即所有单词首字母大写。如下示例：

 

// good

function MenuButton() {

}

 

MenuButton.prototype.show = function() {

};

函数名

普通函数名使用小驼峰，尽可能的选用动词作为名字。

布尔值

尽量使用表示状态的词汇来命名布尔值：可以是形容词、副词，或充当状语成分的词组。这种情况下，不要添加诸如 is, has, can

的前缀，因为那样看上去像是命名一个方法。

 

// good

this.available = true;

this.isAvailable = function () {

​    return this.available;

};

 

// bad

this.isAvailable = true;

如果无法通过上一种情况来命名，比如描述的目标是一个名词，那么可以添加诸如 is, has, can的前缀。

 

// good

this.hasName = true;

 

// bad

[this.name](http://wiki.intra.xiaojukeji.com/this.name) = true;

使用「表示肯定的」词汇来命名布尔值，而不是「表示否定的」。因为这样更易读，并且 具有更好的兼容性：因为如果此变量未定义，那么其默认值为

undefined，等价于 false。

 

// good

this.available = false;

 

// bad

this.unavailable = true;

配置项

组件配置项属性名使用小驼峰

 

// bad

new Compoment({

​    event_type: 'click'

});

 

// good

new Compoment({

​    eventType: 'click'

});

私有属性前面加下划线 _

// bad

this.__firstName__ = 'Panda';

this.firstName_ = 'Panda';

 

// good

this._firstName = 'Panda';

 

注释规范

原则

不要为了注释而注释，多余的注释等价于冗余的代码

如有必要，注释尽量详尽

注释的目的是：提高代码的可读性，从而提高代码的可维护性。

 

单行注释

单行注释使用 //, 一般面向的是语句或者简单逻辑的代码块 (if, for, function)

 

应独立于一行，不要追加在某条语句的后面

 

let active = true;  // bad, is current tab

 

// good, is current tab

let active = true;

在单行注释前添加一个空行，便于阅读区分

 

// bad

function getType() {

​    console.log('fetching type...');

​    // set the default type to 'no type'

​    let type = this._type || 'no type';

 

​    return type;

}

 

// good

function getType() {

​    console.log('fetching type...');

 

​    // set the default type to 'no type'

​    let type = this._type || 'no type';

​    return type;

}

多行注释

一般情况下，多行注释用于函数/对象/文件。

 

多行注释使用 /** */ 或 /* */, 不推荐使用多行的 // 来替代 /**/.

 

// bad

// it's foo

// but not bar

function foo() {

}

// good, it's foo, but not bar

function foo() {

}

/* * good * it's foo, but not bar */

function foo() {

}

/** * good * it's foo, but not bar */

function foo() {

}

对于公共的类/库/组件等代码，面向较多的使用者，推荐使用更为完善的注释规范：

 

函数功能说明，必选

参考文档链接，可选

示例，可选

参数说明，可选

返回值说明，有则必选

api 类型(public/private), 可选

如下，是一个良好风格的示例：

 

/** * 发送旺旺/邮件的方法 * * Doc: <http://api.fed.taobao.net/mc> * * Example: * message(1, 'superman', 'Hello') * .then(function(result) { * // 成功逻辑处理 * }) * .catch(function(err) { * // 错误逻辑处理 * }); * * @param {Number} type 0-旺旺 1-邮件 * @param {String} name 旺旺昵称 * @param {String} content 消息内容 * @return {Promise} * @api public */

function message(type, name, content) {

​    // some code

​    return new Promise(function(resolve, reject) {

​    });

};

文件注释

文件注释，即声明在文件头部，描述文件的元信息。文件注释的基本规则：

 

文件描述，必选

 

/** * 这个文件的作用是什么 */

协议注释

对于引用的外部框架/库，以及我们自己写的开源库，头部会包含一些开源协议声明的注释，对于这部分的注释，我们是不希望也不能将之压缩，这时候需要使用 /*! */ 的注释方式，如下：

 

/*! * jQuery JavaScript Library v2.1.4 * <http://jquery.com/> * * Includes Sizzle.js * <http://sizzlejs.com/> * * Copyright 2005, 2014 jQuery Foundation, Inc. and other contributors * Released under the MIT license * <http://jquery.org/license> * * Date: 2015-04-28T16:01Z */

标记注释

平时的写代码的过程，可能会遇到某个地方是个隐藏的 bug, 因为某种原因还没法修复，或者是方法还有一些需要完成的功能，这时候我们需要加上相应的注释告知未来的自己或者是合作者，这里常用的有三种标签：

 

// TODO: How about auto-correcting small spelling errors?

// FIXME: This won't work if the file is missing.

// XXX: This method badly needs refactoring: should switch by core type.

如下为示例代码：

 

// TODO 需要考虑参数个数不确定的情况

function add(a, b) {

 return a + b;

}

 

function render(data) {

 // FIXME data 为 undefined 时会报错

 if (data.status === 1) {

​     // ...

​    }

}

 

// XXX 这里的异常需要处理，否则后续的脚本都没办法执行

JSON.parse(data);

 











