#  样式问题
### 1. 移动端h5 chrome浏览器 上滑滚动时，地址栏消失导致底部出现白边
tips：尤其是有背景图时
用`height:100vh`不要用`height:100%`
```
  <div class="containerBox">
    <img src="@/assets/img/read_bg.webp" alt="" srcset="" class="readBg" />
    <div class="conainer" ref="containerRef"></div>
  </div>

.containerBox {
  width: 100%;
  position: relative;
  height: 100vh;

  .readBg {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;
  }

  .conainer {
    position: relative;
    z-index: 2;
    width: 100%;
    height: 100%;
  }
}
```
