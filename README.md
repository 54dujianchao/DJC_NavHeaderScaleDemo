# DJC_NavHeaderScaleDemo
实现原理
从效果图可以看到以下几点：

向上移动头像会缩小，但是有下限
向下移动头像会放大，但是有上限
头像的起点y始终不变
所以，我们首先要知道如何缩放控件，也就是使用transform来实现。然后每次都需要更新头像的y坐标，以保证y值不变。既然缩小有下限，放大有上限，所以我们应该设置一个最小缩放系数及最大缩放系数。

要设置最小/最大缩放系数，我们就需要计算出来，但是如何计算呢？其实挺简单的，我们只需要设置下拉或者上拉需要处理缩放的最大距离，就可以计算出来了。

计算放大系数： MIN(1.5, 1 – offsetY / 300);
计算缩小系数： MAX(0.45, 1 – offsetY / 300);
