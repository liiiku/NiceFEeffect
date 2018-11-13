# NiceFEeffect
整理各种好看好用的前端效果
***
*tip：*
项目中对于`scss`的转化，采用的是`node-sass`，见`package.json`中的`scripts`

运行命令：`npm run sass (源文件) （目标文件）` 比如：

`npm run sass cutout/style.scss cutout/style.css`

1. 镂空效果 cutout文件夹

**涉及到的知识点：mask**

参考链接：

[张鑫旭博客地址](https://www.zhangxinxu.com/wordpress/2017/11/css-css3-mask-masks/ "CSS遮罩CSS3 mask/masks详细介绍")

所谓遮罩，就是原始图片只显示 遮罩图片非透明 的部分

最终想要得到的外观在`mask`中设置

遮罩透明的部分就是左右两个半圆，所以原始图片这两个半圆没有了，最后的形态就是遮罩的形态

我们很少使用`jpg`图片来作为遮罩图片的，因为`jpg`图片一定是完全不透明的，最终的效果就是原图什么也看不到。

虽然是遮罩，但是实际上就是遮罩长什么样，看到的效果就长什么样

大疆效果：`dj.html`

[大疆效果图](https://codepen.io/HelKyle/pen/ePyENP/ "大疆效果图")

几个知识点：

`filter` 滤镜属性
`filter: blur(px)` 高斯模糊

2. css实现抛物线效果

参考链接：

[张鑫旭博客地址](https://www.zhangxinxu.com/wordpress/2018/08/css-css3-%E6%8A%9B%E7%89%A9%E7%BA%BF%E5%8A%A8%E7%94%BB/ "css3实现抛物线动画")

3. 小球围绕一个中心，在轨道上运动

ball-circle-run

4. 兼容iphone x刘海的正确姿势

参考链接：

[兼容iphone x刘海的正确姿势](https://juejin.im/post/5be95fbef265da61327ed8e0?utm_source=gold_browser_extension "兼容iphone x刘海的正确姿势")

`viewport-fit=cover` + `safe-area-inset-*`

**关于 viewport-fit**

viewport-fit 有3个值：

- contain: 可视窗口完全包含网页内容（左图）
- cover：网页内容完全覆盖可视窗口（右图）
- auto：默认值，跟 contain 表现一致

![1](https://user-images.githubusercontent.com/21993582/48389966-c12ef680-e73a-11e8-84b3-4f6067b14b2e.png)

![2](https://user-images.githubusercontent.com/21993582/48390022-094e1900-e73b-11e8-87c4-ba71927ac3f6.png)
`constant(safe-area-inset-top)`：在`Viewport`顶部的安全区域内设置量（CSS像素）
`constant(safe-area-inset-bottom)`：在`Viewport`底部的安全区域内设置量（CSS像素）
`constant(safe-area-inset-left)`：在`Viewport`左边的安全区域内设置量（CSS像素）
`constant(safe-area-inset-right)`：在`Viewport`右边的安全区域内设置量（CSS像素）

简单来说我们可以通过 `constant( )` 可以获取到非安全边距，再结合 `padding` 或 `margin` 来控制页面元素避开非安全区域。 Webkit在iOS11中新增CSS Functions: `env( )`替代`constant( )`，文档中推荐使用`env( )`，而 `constant( )` 从Safari Techology Preview 41 和iOS11.2 Beta开始会被弃用。在不支持`env( )`的浏览器中，会自动忽略这一样式规则，不影响网页正常的渲染。为了达到最大兼容目的，我们可以 `constant( )` 和 `env( )` 同时使用。

```
.yourFooterClass {
  padding-bottom: constant(safe-area-inset-bottom); /* iOS 11.0 */
  padding-bottom: env(safe-area-inset-bottom); /* iOS 11.2 */
}
```

新增 viweport-fit 属性，使得页面内容完全覆盖整个窗口：
```
<meta name="viewport" content="width=device-width,initial-scale=1.0,viewport-fit=cover">

```