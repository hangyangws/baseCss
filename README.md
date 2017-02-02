# baseCss

- ### 意义
    统一各个浏览器差异、统一团队开发起始标准、弥补浏览器的“缺点”、提供频繁的原子类名。

- ### 友情提示
    - 前端开发中如果不是UI特别要求，颜色值采用web安全色最佳，像素以偶数最佳。
    - 移动端开发，量度可以尝试rem为单位（什么是rem，请自行Google）。
    - 使用rem为量度单位时，浏览器会是基于html节点而不是body节点计算大小。

- ### 代码解释

    ```css
    /*标准字体大小（rem参照对象）设置为14像素*/

    html {
        font-size: 14px;
    }


    /**
     * 当`body`宽度大于`html`宽度时，某些浏览器会出现内部滚动条，所以给`html、body`设置宽度100%。
     * 取消部分浏览器点击有阴影。
     * 优化移动端滚动事件。
     */

    html,
    body {
        width: 100%;
        -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
        -webkit-overflow-scrolling: touch;
        overflow-scrolling: touch;
    }


    /*移除浏览器默认的`margin、padding`*/

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


    /**
     * `table`相邻单元格的边框间的距离设置为0。
     * 设置`table`的边框为合并模式。
     */

    table {
        border-spacing: 0;
        border-collapse: collapse;
    }


    /*移除浏览器部分元素的默认边框*/

    img,
    abbr,
    input,
    button,
    acronym,
    fieldset,
    textarea {
        border: none;
    }


    /*因为`input`默认不继承父元素的居中样式，所以让`input`元素继承父元素的文本居中方式*/

    input {
        text-align: inherit;
    }


    /*让`textarea`默认不可以放缩*/

    textarea {
        resize: none;
    }


    /*因为部分浏览器默认的`q`标签的前后伪元素有多余样式，所以置空`q`标签前后伪元素*/

    q::before,
    q::after {
        content: '';
    }


    /**
     * 由于以下元素的部分属性没有继承父节点样式，所以声明这些元素的这些属性为父元素的属性。
     * 取消这些元素的`outline`样式。
     */

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


    /**
     * 如果绝对定位元素，找不到被设置过定位信息的上级元素，那么这个元素就基于根节点定位，所以给`body`设置相对定位，让这些元素基于`body`定位。
     * 设置网页基本字体颜色为`#666`(深灰色)。
     * 设置网页背景颜色颜色为`#fff`（纯白色）。
     * 使字体渲染更顺滑。
     */

    body {
        font: 14px 'Helvetica Neue', Arial, 'Hiragino Sans GB', STHeiti, 'STHeiti Light [STXihei]', 'Microsoft Yahei', sans-serif;
        position: relative;
        color: #666;
        background: #fff;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-rendering: optimizeLegibility;
    }


    /*取消下面元素的默认文字装饰（下划线、中划线）*/

    a,
    del,
    ins {
        text-decoration: none;
    }


    /*取消ol，ul默认列表样式*/

    ol,
    ul {
        list-style: none;
    }


    /*使如下元素默认鼠标经过是`小手`的形状（一般表示可以点击）*/

    button,
    input[type='submit'],
    input[type='button'] {
        cursor: pointer;
    }


    /*取消火狐浏览器部分版本`input`聚焦的时候默认的`padding、border`*/

    input::-moz-focus-inner {
        padding: 0;
        border: 0;
    }


    /*取消部分浏览器`input[type='number']`的默认样式*/

    input[type='number'] {
        -moz-appearance: textfield;
    }

    input[type=number]::-webkit-inner-spin-button,
    input[type=number]::-webkit-outer-spin-button {
        margin: 0;
        -webkit-appearance: none;
    }


    /*输入控件的`placeholder`颜色设置为`#999`（浅灰色）*/

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


    /*由于部分浏览器`template`直接显示出来，所以要隐藏`template`元素*/

    template {
        display: none;
    }


    /**
     * 清楚浮动`c ==> clear`,原子类
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


    /*`position: fixed`的缩写，原子类*/

    .pf {
        position: fixed;
        /*chrome 内核 浏览器 position: fixed 防止抖动*/
        -webkit-transform: translateZ(0);
    }


    /*利用绝对定位宽高拉升原理，中心居中元素，原子类*/

    .middle {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        margin: auto;
    }


    /*利用相对定位于`CSS3`使元素垂直居中，原子类*/

    .middle-v {
        position: relative;
        top: 50%;
        -webkit-transform: -webkit-translateY(-50%);
        -moz-transform: -moz-translateY(-50%);
        -o-transform: -o-translateY(-50%);
        transform: translateY(-50%);
    }


    /*元素计算宽高德盒子模型以`border`为外界限，原子类*/

    .bb {
        -webkit-box-sizing: border-box;
        -moz-box-sizing: border-box;
        box-sizing: border-box;
    }


    /*文本溢出显示省略号`to==>text-overflow`，原子类*/

    .to {
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
    }

    ```

- ### 其它
    - CSS中原子类的优缺点：
        1. 维护、维护困难（缺）
        1. 阅读困难（缺）
        1. 便于抽出复用代码，提高代码复用程度（优）
