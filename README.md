 
 
 
# 数字图像处理课程作业实验三 直方图图像增强

**姓名：王适未**

**班级：自动化钱61**

**学号：2160405015**

**提交日期：2019年3月18日**

 

## 摘要

本次作业主要通过计算图像的直方图分布，得出以直方图为基础的图像变换方法；有直方图均衡，直方图匹配，局部直方图均衡以及基于直方图的图像分割算法。本次实验使我对于图像直方图的计算与相关的处理有了进一步的认识，使我对于直方图图像处理的知识有了更加深入的理解。

 

## 作业实验任务 

### 一、输出附件的直方图

把附件图像的直方图画出；

<div align=center><img src="https://latex.codecogs.com/gif.latex?h(r_k)=n_k" alt="h(r_k)=n_k"/></div>

![hw3-1.png](https://raw.githubusercontent.com/oawxkw/sztxcl-hw3/master/dist/hw3-1.png)

 

### 二、直方图均衡

把所有图像进行直方图均衡；输出均衡后的图像和源图像进行比对；分析改善内容；

![hw3-2a.png](https://raw.githubusercontent.com/oawxkw/sztxcl-hw3/master/dist/hw3-2a.png)

![hw3-2b.png](https://raw.githubusercontent.com/oawxkw/sztxcl-hw3/master/dist/hw3-2b.png)

**改善内容分析：**
通过对比图像均衡前后的图像可以明确的到，直方图均衡后的图像明暗对比明显较原图形有所提高。

 

### 三、直方图匹配

进一步把图像按照对源图像直方图的观察，各自自行指定不同源图像的直方图，进行直方图匹配，进行图像增强；

该部分将后三幅图像与第一幅图像的直方图进行匹配。

![hw3-3a.png](https://raw.githubusercontent.com/oawxkw/sztxcl-hw3/master/dist/hw3-3a.png)

![hw3-3b.png](https://raw.githubusercontent.com/oawxkw/sztxcl-hw3/master/dist/hw3-3b.png)

 

### 四、局部直方图增强

对 elain 和 lena 图像进行7*7的局部直方图增强；

![hw3-4a.png](https://raw.githubusercontent.com/oawxkw/sztxcl-hw3/master/dist/hw3-4a.png)

![hw3-4b.png](https://raw.githubusercontent.com/oawxkw/sztxcl-hw3/master/dist/hw3-4b.png)

 

### 五、利用直方图分割图像

利用直方图对图像 elain 和 woman 进行分割。根据 PPT 中的迭代方法进行计算：

![hw3-5.png](https://raw.githubusercontent.com/oawxkw/sztxcl-hw3/master/dist/hw3-5.png)

 

## 附录

代码详见文件

 

## 参考文献

[1] 冈萨雷斯, 数字图像处理（第三版）, 电子工业出版社
