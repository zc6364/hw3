一级标题#
[f1,map]=imread('lena1.bmp');
f=ind2gray(f1,map);
imhist(f,256)

ֱ��ͼ���
imgPath='C:\Users\dell\Desktop\�μ�\����ͼ����\�������ҵ\exercise\';
imgDir=dir(strcat(imgPath,'*.bmp'));
for i=1:length(imgDir)
    [img1,map]=imread([imgPath imgDir(i).name]);
    img=ind2gray(img1,map);
    imga=histeq(img,256);   
    imgName=strsplit(imgDir(i).name,'.');
    name=imgName{1,1};
    imwrite(imga,strcat(name,'_eq','.jpg'),'jpg');
end

ֱ��ͼƥ��
[temp_img1,map]=imread('citywall.bmp');
temp_img=ind2gray(temp_img1,map);
temp_hist=imhist(temp_img);
[img1,map]=imread('citywall1.bmp');
img=ind2gray(img1,map);
out=histeq(img,temp_hist);
figure;
subplot(1,3,1);imhist(img);title('origin image histogram');
subplot(1,3,2);imhist(temp_img);title('template image histogram');
subplot(1,3,3);imhist(out);title('matching image histgram');

ͼ��ָ�
f=imread('elain.bmp');
T=graythresh(f);
g=im2bw(f,T);
imshow(g)

�ֲ�ֱ��ͼ��ǿ
img=imread('elain.bmp');
n=7;
model(1:n,1:n)=1;
imgTend=wextend('2D','sym',img,n);
tendTrans=double(imgTend);
[row,col]=size(imgTend);
tendTransTmp=tendTrans;
for i=n+1:row-n
     for j=n+1:col-n
         modelResult=tendTrans(i:i+(n-1),j:j+(n-1)).*model(1:n,1:n);
         modelEpual=histeq(uint8(modelResult));
         equalTmp=double(modelEpual);
         tendTransTmp(i,j)=equalTmp(4,4);
     end
end
result=uint8(tendTransTmp(n+1:row-n,n+1:col-n));
imshow(result)
   
113  张程博昊_自动化64_2160504106.md
@@ -0,0 +1,113 @@
#<center><font size=6>数字图像处理第三次作业实验报告</center>    
<br/></br>
#<center><font size=5>姓名：张程博昊</center>
#<center><font size=5>班级：自动化64</center>
#<center><font size=5>学号：2160504106</center>
#<center><font size=5>提交日期：3月19日</center>
<br/></br>
#<center><font size=5>**摘要**</center>
#<font size=4>&emsp;这次实验实验主要采用了各种直方图处理方法，实验环境为MATLAB。使用其中函数，完成了对附件中图像进行直方图显示、直方图均衡、指定直方图增强、直方图局部增强、直方图分割等功能。

<br/></br>
#<font size=5>1.绘制图像的直方图
#<font size=4>&emsp;&emsp;直方图是多种空间域处理技术的基础。直方图操作在软件中计算简单，已经成功为图像处理的流行工具。在matlab中，可以采用imhist()函数可以得到图像的直方图。对附件中文件，可以将图片通过ind2gray函数以索引图片的形式读入并显示。
#<center><font size=3>citywall
![](https://i.imgur.com/kmOclSO.jpg)

#<font size=5>2.把所有图像进行直方图均衡；输出均衡后的图像和源图像进行比对；并分析改善内容
#<font size=4>&emsp;&emsp;直方图均衡化是指将原图像采取某种变换，得到一幅灰度直方图为均匀分布的新图像的方法，这样增加了像素灰度值的动态范围，从而达到增强图像整体对比度的效果。在MATLAB中可以采用histeq()函数对图像进行直方图均衡操作。
#<center><font size=3>citywall.bmp
![](https://i.imgur.com/4Po81d9.jpg)
#<center><font size=3>citywall1.bmp
![](https://i.imgur.com/t592iGw.jpg)
#<center><font size=3>citywall2.bmp
![](https://i.imgur.com/1P9RqPm.jpg)
#<center><font size=3>elain.bmp
![](https://i.imgur.com/nRCfm8E.jpg)
#<center><font size=3>elain1.bmp
![](https://i.imgur.com/8ITth2W.jpg)
#<center><font size=3>elain2.bmp
![](https://i.imgur.com/yCz4mNR.jpg)

#<font size=4>&emsp;&emsp;可以看出进行直方图均衡后的图像与原图像相比色彩更加丰富，细节也更加明显。可知直方图可以很好的改善灰度过于集中所带来的图像模糊的问题。
<br/></br>
#<font size=5>3.进一步把图像按照对源图像直方图的观察，各自自行指定不同源图像的直方图，进行直方图匹配，进行图像增强；
#<font size=4>&emsp;&emsp;直方图匹配又称为直方图规定化，是指将一幅图像的直方图变成规定形状的直方图而进行的图像增强方法。可以采用imhist()函数，并采取原图像为模板。得到结果如下：
#<center><font size=3>citywall1.bmp
![](https://i.imgur.com/cht1E7l.jpg)
#<center><font size=3>citywall2.bmp
![](https://i.imgur.com/z4eIVvB.jpg)

#<font size=4>&emsp;&emsp;对以上直方图匹配结果分析可以看出，对于那些灰度值集中在较低值或者灰度值两极分化分布的情况来说，直方图匹配相对于直方图均衡可以得到更好的结果。elain1与elain3图像的处理这种对比十分明显。
#<font size=4>&emsp;&emsp;其中，对原图像为citywall1.bmp，匹配模板为citywall.bmp，得到的匹配后图像与这两个图像的直方图对比为：
#<center><font size=3>图像匹配前后直方图对比
![](https://i.imgur.com/Ti3zDvF.jpg)
#<center><font size=3>图像匹配前后图像对比
![](https://i.imgur.com/uSVFrXJ.jpg)
#<font size=4>&emsp;&emsp;可以看出，经过直方图匹配后的图像相较于原图灰度范围扩大，细节也更加明显。
#<font size=5>4.对elain和lena图像进行7*7的局部直方图增强；
#<font size=4>&emsp;&emsp;这里采用7*7的局部直方图增强，对每个分块进行直方图匹配，在此之前首先应当对图像进行扩展，否则无法对每个像素进行处理，处理结果如下：
#<center><font size=3>elain.bmp
![](https://i.imgur.com/soqrFUw.jpg)
#<center><font size=3>lena.bmp
![](https://i.imgur.com/D9wVKKh.jpg)
#<font size=5>5.利用直方图对图像elain和woman进行分割；
#<font size=4>&emsp;&emsp;本任务需要基于直方图进行图像分割，这里采用基于阈值的图像（最大类间方差法--OTSU），matlab中graythresh()函数利用该方法找到一个阈值，配合im2bw()函数即可将图像转变为二值图像。图像分割的结果为：
#<center><font size=3>elain.bmp
![](https://i.imgur.com/4Hixy6F.jpg)
#<center><font size=3>lena.bmp
![](https://i.imgur.com/Tbaenbr.jpg)
