# ASMaskImageView

---

[![GitHub license](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://raw.githubusercontent.com/zkh90644/ASMaskImageView/master/LICENSE)
[![pod](https://img.shields.io/badge/pod-v1.0.1-brightgreen.svg)](https://cocoapods.org/pods/ASMaskImageView)
[![blog](https://img.shields.io/badge/blog-%E7%AE%80%E4%B9%A6-orange.svg)](http://www.jianshu.com/users/b863d709977d/latest_articles)

[English Version README.MD](https://github.com/zkh90644/ASMaskImageView/blob/master/README_English.md)

一个简单的页面遮罩效果类，主要用于UIImageView与对于UILabel中的文字的遮罩。支持圆角切割，支持透明背景图片，支持移动效果。

##效果图
![showImage](https://github.com/zkh90644/ASMaskImageView/blob/master/Resource/show.gif)


##安装方法
---
**cocoapods**

```
pod 'ASMaskImageView', '~> 1.0.0'
use_frameworks!
```
##使用方法
---
创建需要用来遮罩的**MaskView对象**（该对象继承于UIImageView）

```
touchView = MaskView.init(image:UIImage.init(named: "1")!,frame: CGRect.init(origin: CGPoint(x: 0,y: 0), size: CGSize(width: 100, height: 100)))
```
将需要被遮罩的UILabel控件加入**MaskView对象**的**maskViewArray**属性中

```
touchView!.maskViewArray.append(label1)
touchView!.maskViewArray.append(label2)
touchView!.maskViewArray.append(label3)
```
当需要使用遮罩效果的时候调用`changeMoveImage()`方法即可

```
func move(gesture:UIPanGestureRecognizer)throws {
    touchView?.center = gesture.locationInView(self.view)
    try touchView?.changeMoveImage()
        
}
```
