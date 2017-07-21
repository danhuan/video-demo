# video-demo
HTML5 video 标签浏览器兼容问题 小例子


![image.png](http://upload-images.jianshu.io/upload_images/6166110-b7a7352d3b8684ba.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
IE8、火狐、谷歌测试通过。

**使用<video>需要注意的问题：**

**1.多种格式视频**

不可以只有MP4格式，一定要引入Ogg格式视频，否则在火狐上会不兼容报错。
推荐个不错的视频格式转换器，下载地址 ：http://download.csdn.net/detail/danhuan/9905942


**2.引入html5media.js**

引入html5media.js,可以使<video>兼容IE


**3.如果想要设置视频宽度为百分比%自适应占满容器，注意 video的属性width不可以为百分比%**

注意 **不可以** 直接在`<video>` 标签里面加width = "100%"，因为<video>的属性width只支持像素值，不支持百分比。虽然`<video width = "100%">` 在谷歌火狐浏览器中可以正确显示，但是在IE中会不兼容,导致无法播放视频。
如果想要设置视频宽度为百分比%自适应占满容器，**可以** 通过内部样式`<style>...</style>`或外部样式`<link rel="stylesheet" href="CSS文件路径" />`设置，但 **不可以** 通过内联样式`style="width:100%"` 设置样式，否则不兼容IE。



**4.如果视频是固定宽高，则可以直接在<video>属性中设置，千万注意不要加单位px，否则IE不兼容。**

正确示例如下：
```
<video width="1000" height="500" controls autoplay="true" loop="true" preload="auto">
```

错误示例如下：
```
<video width="1000px" height="500px" controls autoplay="true" loop="true" preload="auto">
```
![image.png](http://upload-images.jianshu.io/upload_images/6166110-aab0d909c7674f48.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
