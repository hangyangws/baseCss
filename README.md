# baseCss

- ### 意义
    统一各个浏览器差异、统一团队开发起始标准、弥补浏览器的“缺点”、提供频繁的原子类名。

- ### 友情提示
    - 前端开发中如果不是UI特别要求，颜色值采用web安全色最佳，像素以偶数最佳。
    - 移动端开发，量度可以尝试rem为单位（什么是rem，请自行Google）。
    - 使用rem为量度单位时，浏览器会是基于html节点而不是body节点计算大小。
    - 绝对定位元素，如果找不到被设置过定位信息的上级元素，那么这个元素就基于根节点`<html>`定位。

- ### 代码解释

- 对常见默认有`margin`或`padding`的元素取消`margin`和`padding`
- 对`tabel`取消相邻单元格之间的间隙
- 取消默认带边框元素的边框
- `<input>`等元素默认不继承上级的某些样式，要对这些元素进行手动样式继承：

- 不论是网站还是webApp开发，body的根目录样式是必须定义好且规范，基于常用开发习惯，得出如下CSS：

- 取消`textarea`默认可放缩属性，取消默认有下划线元素的下划线
- 使`button`等元素，在鼠标经过为手型
- 给表单元素的`placeholder`改变颜色
- 给`template`设置默认隐藏

### 常用类名
- `middle`类，利用绝对定位的拉升特性，对已设置过宽高的元素，进行相对最近设置过定位信息元素的中心居中

- `bb`类，定义盒子模型宽高计算规则

- `middle-v`类，使元素向上移动半个自身的高度，再向下移动父元素的50%，*未知高度元素垂直居中用到*
@charset 'utf-8';


/**
 * reset style
 */

html {
    font-size: 14px;
}

html,
body {
    position: relative;
    width: 100%;
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
    -webkit-overflow-scrolling: touch;
    overflow-scrolling: touch;
}

p,
dl,
dt,
dd,
ul,
ol,
li,
h1,
h2,
h3,
h4,
h5,
h6,
th,
td,
div,
pre,
body,
code,
form,
input,
legend,
button,
figure,
fieldset,
textarea,
blockquote {
    margin: 0;
    padding: 0;
}

table {
    border-spacing: 0;
    border-collapse: collapse;
}

img,
abbr,
input,
button,
acronym,
fieldset,
textarea {
    border: none;
}

input {
    text-align: inherit;
}

textarea {
    resize: none;
}

q::before,
q::after {
    content: '';
}


/*手动继承某些元素的某些属性*/

a,
h1,
h2,
h3,
h4,
h5,
h6,
input,
select,
button,
option,
textarea,
optgroup {
    font-family: inherit;
    font-size: inherit;
    font-weight: inherit;
    font-style: inherit;
    line-height: inherit;
    color: inherit;
    outline: none;
}


/*body全局设置*/

body {
    font: 14px 'Helvetica Neue', Arial, 'Hiragino Sans GB', STHeiti, 'STHeiti Light [STXihei]', 'Microsoft Yahei', sans-serif;
    color: #666;
    background: #fff;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-rendering: optimizeLegibility;
}

a,
del,
ins {
    text-decoration: none;
}

ol,
ul {
    list-style: none;
}

button,
input[type='submit'],
input[type='button'] {
    cursor: pointer;
}

input::-moz-focus-inner {
    padding: 0;
    border: 0;
}

input[type='number'] {
    -moz-appearance: textfield;
}

input[type=number]::-webkit-inner-spin-button,
input[type=number]::-webkit-outer-spin-button {
    margin: 0;
    -webkit-appearance: none;
}


/*placeholder*/

input::-webkit-input-placeholder,
textarea::-webkit-input-placeholder {
    color: #999;
}

input:-moz-placeholder,
textarea:-moz-placeholder {
    color: #999;
}

input::-moz-placeholder,
textarea::-moz-placeholder {
    color: #999;
}

input:-ms-input-placeholder,
textarea:-ms-input-placeholder {
    color: #999;
}


/**
 * common style
 */

.c {
    zoom: 1;
}

.c::after {
    display: block;
    visibility: hidden;
    clear: both;
    height: 0;
    content: '.';
}

.pr {
    position: relative;
}

.pa {
    position: absolute;
}

.pf {
    position: fixed;
    /*chrome 内核 浏览器 position: fixed 防止抖动*/
    -webkit-transform: translateZ(0);
}

.t0 {
    top: 0;
}

.l0 {
    left: 0;
}

.b0 {
    bottom: 0;
}

.r0 {
    right: 0;
}

.z1 {
    z-index: 1;
}

.z2 {
    z-index: 2;
}

.z3 {
    z-index: 3;
}

.middle {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    margin: auto;
}

.middle-v {
    position: relative;
    top: 50%;
    -webkit-transform: -webkit-translateY(-50%);
    -moz-transform: -moz-translateY(-50%);
    -o-transform: -o-translateY(-50%);
    transform: translateY(-50%);
}


/*width height*/

.w1 {
    width: 100%;
}

.h1 {
    height: 100%;
}


/*display*/

.none,
template {
    display: none;
}

.bb {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}

.to {
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
}
