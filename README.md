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