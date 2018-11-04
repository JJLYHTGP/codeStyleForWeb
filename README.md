[TOC]
# 前端代码风格
## 1 前言

从2017年9月开始接触前端，但是有意识地关注代码规范是从2018年5月在某大厂实习的时候才开始的。规范的代码提高了可读性和可维护性，不知不觉中也能提高了写代码的速度。

## 2 代码风格

### 2.1 CSS规范

#### 代码规范

##### 基本规范

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


##### 选择器规范

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

##### 属性规范

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

##### 命名规范

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

2. 小写字母加连字符。非下划线或驼峰命名

   ```css
   /* bad */
   .mod_example {
       padding-left: 15px;
   }
   .modExample {
       padding-left: 15px;
   }
   
   /* good */
   .mod-example {
       padding-left: 15px;
   }
   ```

##### 资源引用

1. icon-font资源引用。一般情况下移动客户端可以只需引用ttf
   ```css
   @font-face {
       font-family: rongshu-iconfont;
       /* IE9*/
       src: url('.eot');
       /* IE6-IE8 */
       src: url('.eot?#iefix') format('embedded-opentype'),
       /* chrome、firefox */
       url('.woff') format('woff'),
       /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/
       url('.ttf') format('truetype'),
       /* iOS 4.1- */
       url('.svg#iconfont') format('svg');
   }
   ```


#### 媒体查询

##### 组织形式

1. 媒体查询分别针对每一种屏幕（大、中、小），单独组织为一个文件

   ```css
   /* base.css */
   .element {
       ...
   }
   
   /* base-media-small */
   .element {
       ...
   }
   ```

#### 注释规范

##### 代码注释

1. 注释内容

>  代码是由人来编写和维护的。保证你的代码是描述性的，包含好的注释，且容易被他人理解。好的代码注释传达上下文和目标。不要简单地重申组件或class名称。

```css
/* bad */

/* Jjly header */
.jjly-header {
    
}

/* good */

/* Wrapping element for .jjly-title and .jjly-note */
.jjly-header {
    
}
```

##### 文件注释

1. 声明在文件头部，描述文件的元信息，表明文件的作用。

#### less规范

### 2.2 JS规范

#### 语言规范

##### 命名

1. 命名必须有语义，不要使用单个字符命名

2. 对象字面量命名使用小驼峰，常量命名全大写并使用下划线，构造函数和类使用大驼峰命名

   ```javascript
   // good
   const base = {
       isOnline() {
        	// ...   
       }
   };
   
   const WELCOME_TEXT = 'hello world';
   
   function Menu() {
       // ...
   }
   
   class MenuItem {
       // ...
   }
   ```

##### 引用

1. 对所有引用都使用const或let。

   > 如果使用var将导致生成全局变量，这样做为了避免污染全局命名空间。

   ```javascript
   // bad
   var a = 1;
   
   // good
   const a = 1;
   ```

2. 使用多个let或const声明多个变量。

   > 方便增删，不易发生遗漏。在调试时也可以遍历每个声明。

   ```javascript
   // bad
   const a = 1, b=2, c =3;
   
   // good
   const a = 1;
   const b = 2;
   const c = 3;
   ```

##### 对象

1. 使用字面量值创建对象

   ```javascript
   // bad
   const a = new Object();
   
   // good
   const a = {};
   ```

2. 不要使用保留字作为对象的键值，IE8 下不支持。

   ```javascript
   // bad
   const a = {
       default: {}, // default是保留字
   }
   ```

3. 访问对象属性时，尽可能使用.

   ```javascript
   // bad
   a['s'] = 1;
   
   // good
   a.s = 1;
   ```

4. 私有属性前加下划线

   ```javascript
   // bad
   this.firstName = 'Black';
   
   // good
   this._firstName = 'Black';
   ```

##### 数组

1. 使用字面量代替构造函数

   ```javascript
   // bad
   const arr = new Array();
   
   // good
   const arr = [];
   ```

2. 使用push为数值增加元素

   ```javascript
   // bad
   arr[arr.length] = 1;
   
   // good
   arr.push(1);
   ```

##### 函数

1. 不要把参数命名为arguments，这样会覆盖arguments对象

##### 类型转换

1. 使用强制类型转换

   ```javascript
   // bad
   const score = new String(this.score);
   const score = this.score + '';
   const score = this.score.toString();
   
   // good
   const score = String(this.score);
   ```

2. 对于数字使用parseInt，总是带上类型转换的基数

   ```javascript
   const val = '4';
   // bad
   const value = new Number(val);
   const value = +val;
   const value = val >> 0;
   const value = parseInt(val);
   
   // good
   const value = Number(val);
   const value = parseInt(val, 10);
   ```

3. 布尔值

   ```javascript
   // bad
   const hasAge = new Boolean(age);
   
   // good
   const hasAge = Boolean(age);
   
   // best
   const hasAge = !!age;
   ```



##### 条件表达式和等号

1. 尽量使用===和!==

   ```javascript
   // bad
   a == 1
   
   // good
   a === 1
   ```

#### 代码规范

##### 引号

1. 统一使用单引号

   ```javascript
   // good
   const str = 'hi';
   ```

##### 花括号

1. 不要省略花括号

   ```javascript
   // bad
   if (1) 
       return true;
   
   // good
   if (o) {
   	return true;    
   }
   ```

##### 空格

1. 二元操作符与三元操作符前后需要有空格

   ```javascript
   // bad
   const x=a+5;
   const c=a>0?1:2;
   
   // good
   const x = a + 5;
   const c = a > 0 ? 1 : 2;
   ```

##### 注释

1. 单行注释使用//，一般面向简单的语句或代码块，独立一行，且加在语句前面。

   ```javascript
   // good
   
   // is current tab
   let current = true;
   ```

2. 在注释前增加一个空行，便于阅读区分。

3. 多行注释使用/** */代替多行//。一般用于解释函数/对象/文件。

   ```javascript
   /** This is a description of the foo function. */
   function foo() {
   }
   
   /**
    * Represents a book.
    * @constructor
    */
   function Book(title, author) {
   }
   
   /**
    * Represents a book.
    * @constructor
    * @param {string} title - The title of the book.
    * @param {string} author - The author of the book.
    */
   function Book(title, author) {
   }
   ```

4. 对于公共的类/库/组件等代码，面向较多的使用者，推荐使用更为完善的注释规范

   ```javascript
   函数功能说明 必选
   参考文档链接
   实例
   参数说明
   返回值说明 有则必选
   api类型(public/private)
   ```

   ```javascript
   /**
   * 发送语音/邮件的方法 *
   * Doc: http://api.fed.taobao.net/mc *
   * Example:
   * message(1, 'superman', 'Hello')
   * 	.then(function(result) {
   * 		// 成功逻辑处理 
   * 	}) 
   * 	.catch(function(err) { 
   * 		// 错误逻辑处理 
   * 	}); 
   * @param {Number} type 0-语音 1-邮件 
   * @param {String} name 昵称 
   * @param {String} content 消息内容 
   * @return {Promise} 
   * @api public 
   */
   
   function message(type, name, content) {
       // some code
   
       return new Promise(function(resolve, reject) {
   
       });
   };
   ```

5. 文件注释。即声明在文件头部，描述文件的元信息。

6. 协议注释。对于引用的或自己的开源库，头部包含开源协议声明的注释，对于这部分注释，我们不希望也不能将其压缩，这时候需要使用/*! */

   ```javascript
   /*! * jQuery JavaScript Library v2.1.4 * http://jquery.com/ * * Includes Sizzle.js * http://sizzlejs.com/ * * Copyright 2005, 2014 jQuery Foundation, Inc. and other contributors * Released under the MIT license * http://jquery.org/license * * Date: 2015-04-28T16:01Z */
   ```

7. 标记注释。告知后面阅读代码的人或者合作者，某个地方是隐藏bug，因为某种原因尚未修复，或者方法还需要完善功能。

   ```javascript
   // TODO: How about auto-correcting small spelling errors?
   
   // FIXME: This won't work if the file is missing.
   
   // XXX: This method badly needs refactoring: should switch by core type.
   function add() {
       // ...
   }
   ```

##### 链式调用

1. 避免过长的链式调用；调用较长时换行

   ```javascript
   // bad
   
   $('#items').find('.selected').highlight().end().find('.open').updateCount();
   
    
   
   // good
   
   $('#items')
   
       .find('.selected')
   
       .highlight()
   
       .end()
   
       .find('.open')
   
       .updateCount();
   ```

## 3. 协作开发

### 3.1 GitLab使用

#### 命名

1. 分支命名有意义，建议姓名缩写+功能。如jjly-hp-css，表示jjly的写首页css的分支。

#### commit提交

1. commit信息要有意义，提交功能时可以用git rebase将多条相同commit合并

   ```
   // bad
   git commit -am 'bugfix'
   
   // good
   git commit -am '修复了样式混乱的bug'
   ```

#### Merge request提交

1. 不要直接覆盖重要的远程分支，在远程仓库提交merge request后，交给code reviewer和merge operator来审核和merge代码。

#### 回滚代码

1. 使用revert代替reset来回滚代码。

## 4. 参考资料

> [Aotu.io - 前端代码规范](https://guide.aotu.io/docs/)
>
> [Use JSDoc](http://usejsdoc.org/index.html)







 
