# publicCSS

### 意义

项目中的公共样式，仅供参考；提供常用类名，不用在不同页面重复造轮子

### 友情提示

一般只是把最常用，且团队公认的样式抽离为公共原子类

### 代码解释

```css
/**
 * 清楚浮动「c ==> clear」
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


/*position: fixed 的缩写*/

.pf {
  position: fixed;
  /*chrome 内核 浏览器 position: fixed 防止抖动*/
  -webkit-transform: translateZ(0);
}


/*利用绝对定位宽高拉升原理，中心居中元素*/

.middle {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  margin: auto;
}


/*利用相对定位于 CSS3 使元素垂直居中*/

.v-middle {
  position: relative;
  top: 50%;
  -webkit-transform: -webkit-translateY(-50%);
  -moz-transform: -moz-translateY(-50%);
  -o-transform: -o-translateY(-50%);
  transform: translateY(-50%);
}


/*元素计算宽高德盒子模型以 border 为外界限「bb ==> border-box」*/

.bb {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}


/*单行文本溢出显示省略号「to ==> text-overflow」*/

.to {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
```

**感谢阅读**
