# svg-pan-zoom
操作原生svg画面的工具库

### 使用说明

#### 引入包里面的svg-pan-zoom
```
import svgPanZoom from "@/utils/svg/svg-pan-zoom.js";
```
#### 找到画布并且初始化操作对象svgObj

```
nextTick(() => {
      let dom = $(`#home${currentTabIndex.value}`).get(0);
      if (dom) {
        svgObj = svgPanZoom(dom, {
          dblClickZoomEnabled: false,
          zoomEnabled: true,
          //不从中间开始渲染
          center: false,
          minZoom: 0.1
        });
       
        //左键和右键都不允许拖动，中键允许拖动
        if (svgObj[`${currentTabIndex.value}`]) {
          svgObj[`${currentTabIndex.value}`]?.disablePan();
          window.onmousedown = e => {
            if (e.button === 2 || e.button === 0) {
             
            }
          }
        }
     
      }
    });
```

这个实话按住鼠标滚轮加上ctrol就可以方法整张画布了

另外还提供了定位元素，中键拖动画布的功能

