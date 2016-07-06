# baseCss
> CSS基类，减少浏览器差异，常用CSS类名

### 基本声明
*颜色值采用web安全色最佳，像素以偶数最佳*

---

### 减少浏览器差异化
- 某个绝对定位元素，如果找不到被设置过定位信息的上级元素，那么这个元素就基于根节点定位。
那么这个根节点就理所应当的是`<html>`节点。所以为了使定位更正规，添加：
```css
html,
body {
    position: relative;
    width: 100%;
}
```

### 浏览器重置
- 对常见默认有`margin`或`padding`的元素取消`margin`和`padding`
- 对`tabel`取消相邻单元格之间的间隙
- 取消默认带边框元素的边框
- 因为`<input>`等元素默认不继承上级的某些样式，所以要对这些元素进行手动样式继承：
```css
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
```
- 不论是网站还是webApp开发，body的根目录样式是必须定义好且规范，基于常用开发习惯，得出如下CSS：
```css
body {
    font: 14px 'Helvetica Neue', Arial, 'Hiragino Sans GB', STHeiti, 'STHeiti Light [STXihei]', 'Microsoft Yahei', sans-serif;
    color: #666;
    background: #fff;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-rendering: optimizeLegibility;
}
```
- 取消`textarea`默认可放缩属性，取消默认有下划线元素的下划线
- 使`button`等元素，在鼠标经过为手型
- 给表单元素的`placeholder`改变颜色
- 给`template`设置默认隐藏

### 常用简写CSS类名
- **颜色定义** `fc`为*font-color*缩写，`bc`为*background-color*缩写
- **字体** `fs`为*font-size*缩写，`fw`为*font-weight*缩写……
- 依次有padding，margin，对其，浮动，相邻行级元素垂直对齐，相对和绝对定位以及方向值，层叠顺序，宽高的基本定义，盒子模型

### 常用基本类名
- `middle`类，利用绝对定位的拉升特性，对已设置过宽高的元素，进行相对最近设置过定位信息元素的中心居中
```css
.middle {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    margin: auto;
}
```
- `bb`类，定义盒子模型宽高计算规则
```css
.bb {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
```
- `top-middle`类，使元素向上移动半个自身的高度，*未知高度元素垂直居中用到*配合`top-50`类使用效果更佳
```css
.top-middle {
    -webkit-transform: -webkit-translateY(-50%);
    -moz-transform: -moz-translateY(-50%);
    -o-transform: -o-translateY(-50%);
    transform: translateY(-50%);
}
.top-50 {
    position: relative;
    top: 50%;
}
```

---

### Other

- 下载Zip包或者`git clone https://github.com/hangyangws/baseCss.git`到本地，使用根目录下的`src/basse.css`
    > 当然，如果你不稀饭base这个单词，你可以修改名字。
- 使用前应该通看一遍base.css的内容，熟记每个类名的意义。