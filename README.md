# 数字图像处理第二次作业
2
姓名：  胡煜枫   
3
班级：  自动化63    
4
学号：  2160504067
5
***
6
## 题目1： 把附件图像的直方图画出
7
&emsp;作业中使用python通过读取图像的灰度值，将灰度值读为narray数组，并转为1维张量，统计各灰度值在图像中出现的个数，最后除以总pixel数归一化处理，各直方图如下所示：  
8
&emsp;由于图象较多，md中排版困难，仅在此给出了4幅原始图像的直方图及部分代表性图片，其余图象可在 *\hist* 目录下观看。
9
#### citywall的直方图
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
10
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_citywall.jpg)
@Dcupqiu
Add files via upload
5 days ago
11
#### elain的直方图
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
12
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_elain.jpg)
@Dcupqiu
Add files via upload
5 days ago
13
#### lena的直方图
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
14
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_lena.jpg)
@Dcupqiu
Add files via upload
5 days ago
15
#### woman的直方图
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
16
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_woman.jpg)
@Dcupqiu
Add files via upload
5 days ago
17
#### citywall2的直方图
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
18
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_citywall2.jpg)
@Dcupqiu
Add files via upload
5 days ago
19
#### elain2的直方图
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
20
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_elain2.jpg)
@Dcupqiu
Add files via upload
5 days ago
21
#### lena2的直方图
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
22
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_lena2.jpg)
@Dcupqiu
Add files via upload
5 days ago
23
***
24
## 题目2：把所有图像进行直方图均衡；输出均衡后的图像和源图像进行比对，分析改善内容
25
&emsp;在按图像中，直方图的分量集中在灰度级的低端。类似地，亮图象直方图的分量倾向于灰度级的高端。低对比图图象具有较窄的直方图，且集中于灰度级的中部。对于但色图这意味着暗淡。若一幅图像的像素倾向于占据整个可能的灰度级并且分布均匀，则该图象会有高对比度的外观并展示灰色调的较大变化，最终效果是一幅灰度细节丰富且动态范围较大的图象。  
26
&emsp;主要原理是使用  
27
<p align="center"><a href="https://www.codecogs.com/eqnedit.php?latex=s&space;=&space;T(r)&space;=&space;(L-1)\int_{0}^{r}p_r(w)dw" target="_blank"><img src="https://latex.codecogs.com/gif.latex?s&space;=&space;T(r)&space;=&space;(L-1)\int_{0}^{r}p_r(w)dw" title="s = T(r) = (L-1)\int_{0}^{r}p_r(w)dw" /></a> </p> 
28
&emsp;实现原灰度级到新灰度级的映射。  
29

30
&emsp;使用直方图均衡的方式，会让图象中像素的灰度值倾向于均匀分布，以获得较高的对比度与动态范围。  
31
&emsp;由于cv2中有现成的直方图均衡函数，本题直接使用了cv2的equalizeHist进行全局直方图均衡，并将生成的直方图输出在了 *\equal* 目录下可以获取全部输出的均衡后图象与均衡后的直方图文件，特别的，直方图文件以 *hist_* 开头。  
32
&emsp;由于篇幅限制，在此处仅以多幅代表性图像举例。
33
### 以citywall2为例
34
&emsp;可以看到，citywall2的原始图象对比度较低且颜色较暗，且对比度较低，而在输出的均衡后的citywall2图像中，对比度有了极大的提升，且暗部细节明显，可以清晰看出城墙下树叶的轮廓。
35
#### citywall2源图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
36
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/original/citywall2.bmp)
@Dcupqiu
Add files via upload
5 days ago
37
#### citywall2直方图均衡后图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
38
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/citywall2.jpg)
@Dcupqiu
Add files via upload
5 days ago
39
### 以elain3为例
40
&emsp;从这两幅图的对比中可以看出，源图象非常暗，基本无法分辨人物轮廓，而新图像中则极大的提升了明度与对比度，可以清晰看出人物的脸与轮廓，但相对的，由于源图像中灰度级个数较少，导致新输出的图象中过度较为僵硬，可以清晰的看到过渡带中像素点的分布。
41
#### elain3源图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
42
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/original/elain3.bmp)
@Dcupqiu
Add files via upload
5 days ago
43
#### elain3直方图均衡后图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
44
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/elain3.jpg)
@Dcupqiu
Add files via upload
5 days ago
45
### 最后以lena2为例
46
&emsp;lena2图象存在的问题是图象直方图的分量主要集中于灰度级的高端，导致图象整体泛白且对比度不高，从均衡后输出的图片可以看到这一问题得到了明显的改善，但同样由于原始图象的灰度级个数不足，导致均衡后的图象过渡带表现比较糟糕，但较elain3而言由于分布更平均，效果稍好。
47
#### lena2源图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
48
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/original/lena2.bmp)
@Dcupqiu
Add files via upload
5 days ago
49
#### lena2直方图均衡后图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
50
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/lena2.jpg)
@Dcupqiu
Add files via upload
5 days ago
51
***
52
## 题目3：进一步把图像按照对源图像直方图的观察，各自自行指定不同源图像的直方图，进行直方图匹配，进行图像增强
53
&emsp;在本道题中，将让目标图像针对源图象直方图进行匹配，直方图匹配又名直方图规定化，它的目的是让处理后的图象的直方图具有我们期望的概率分布形式。  
54
&emsp;由于python中没有直接的图像匹配模块，所以本处采用了自己编写的程序，首先计算了源图像的离散的概率密度函数积分的结果，是一个256维的张量，单调递增且最后一个元素为1。然后相同的计算了目标图像的离散的概率密度函数积分的结果。最后对两个张量进行对应灰度级的最邻近匹配，构建映射关系，形成目标图像的灰度级的一对一或多对一的映射关系，并依此完成图象的变换。程序逻辑如下：
55

56
      def HistMatch(img_m, img_s):
57
        hist_m = cv2.calcHist([img_m], [0], None, [256], [0, 255])
58
        hist_s = cv2.calcHist([img_s], [0], None, [256], [0, 255])
59
        img = np.array(img_m)
60

61
        tmp = 0
62
        hist_a = hist_m.copy()
63
        for i in range(256):
64
            tmp += hist_m[i]
65
            hist_a[i] = tmp
66
        hist_a = hist_a / hist_a[255]
67

68
        tmp = 0
69
        hist_b = hist_s.copy()
70
        for i in range(256):
71
            tmp += hist_s[i]
72
            hist_b[i] = tmp
73
        hist_b = hist_b / hist_b[255]
74

75
        match = np.zeros(256)
76
        for i in range(256):
77
            diff = 1
78
            d = 0
79
            for j in range(256):
80
                if (diff > np.fabs(hist_a[i] - hist_b[j])):
81
                    d = j
82
                    diff = np.fabs(hist_a[i] - hist_b[j])
83
            match[i] = d
84

85
        for s in img:
86
            for i in range(len(s)):
87
                s[i] = match[int(s[i])]
88

89
        return img
90

91
&emsp;最终取得的图象增强效果如下所示(仅展示部分效果显著图片剩余图片可在 *\HistMatch* 目录下获取）：
92
#### citywall源图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
93
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_citywall.jpg)
@Dcupqiu
Add files via upload
5 days ago
94
#### citywall2直方图匹配后的图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
95
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/citywall2.jpg)
@Dcupqiu
Add files via upload
5 days ago
96
#### lena源图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
97
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_lena.jpg)
@Dcupqiu
Add files via upload
5 days ago
98
#### lena2直方图匹配后的图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
99
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/lena2.jpg)
@Dcupqiu
Add files via upload
5 days ago
100
#### woman源图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
101
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_woman.jpg)
@Dcupqiu
Add files via upload
5 days ago
102
#### woman2直方图匹配后的图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
103
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/woman2.jpg)
@Dcupqiu
Add files via upload
5 days ago
104
### 效果分析
105
&emsp;可以看出直方图匹配相较于直方图均衡，展示出的效果更贴近于原始图象。但是局限于部分图象本身灰度级的个数较少，导致映射后的直方图分布较为稀疏，使图象难以还原到原图象的效果，仍有不小的差异。部分差异较大的图片更可能获得更糟糕的结果。
106
***
107
## 题目4：对elain和lena图像进行7*7的局部直方图增强
108
&emsp;使用7*7的局部直方图增强即使用一个7*7的kernal获取图象局部的49个pixel，并使用直方图均衡求取中心点的灰度值作为源图象中该点变化后的灰度值。由于图像边缘像素缺乏像素点，故可先在图象四边各padding 3个像素。实际效果如下图所示：
109
#### elain的局部直方图增强
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
110
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/localhistogram/elain.jpg)
@Dcupqiu
Add files via upload
5 days ago
111
#### lena的局部直方图
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
112
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/localhistogram/lena.jpg)
@Dcupqiu
Add files via upload
5 days ago
113
### 效果分析
114
&emsp;可以看出通过7*7的局部直方图均衡，突出了微小的细节及边缘。
115
***
116
## 题目5：利用直方图对图像elain和woman进行分割
117
&emsp;直方图对图象进行分割可以通过前景于背景的直方图差异区分前景与背景，通过对直方图的分析获取一个阈值，通过这一阈值将图像二值化处理。在本次作业中，我使用了Huang's fuzzy thresholding method实现了Threshold的生成。通过香农熵函数来度量模糊度，取香农熵值最小时的t为最终的分割阈值，具体实现如下代码所示：
118

119
      def Thres(hist):
120
        first_bin = 0
121
        for i in range(256):
122
            if hist[i] != 0:
123
                first_bin = i
124
                break
125
        last_bin = 255
126
        for i in reversed(range(256)):
127
            if hist[i] != 0:
128
                last_bin = i
129
                break
130
        term = 1.0 / (last_bin - first_bin)
131

132
        mu_0 = np.zeros(256)
133
        sum_pix = num_pix = 0
134
        for i in range(first_bin,256):
135
            sum_pix += i * hist[i]
136
            num_pix += hist[i]
137
            mu_0[i] = sum_pix / num_pix
138

139
        mu_1 = np.zeros(256)
140
        sum_pix = num_pix = 0
141
        for i in reversed(range(0,last_bin+1)):
142
            sum_pix += i * hist[i]
143
            num_pix += hist[i]
144
            mu_1[i] = sum_pix / num_pix
145

146
        threshold = -1
147
        min_ent = np.inf
148
        for it in range(256):
149
            ent = 0
150
            for ih in range(0, it+1):
151
                mu_x = 1.0 / (1 + term * np.abs(ih - mu_0[it]))
152
                if mu_x >= 1e-6 and mu_x <= 0.999999:
153
                    ent += hist[ih] * (-mu_x * np.log(mu_x) - (1 - mu_x)*np.log(1 - mu_x))
154
            for ih in range(it+1, 256):
155
                mu_x = 1.0 / (1 + term * np.abs(ih - mu_1[it]))
156
                if mu_x >= 1e-6 and mu_x <= 0.999999:
157
                    ent += hist[ih] * (-mu_x * np.log(mu_x) - (1 - mu_x)*np.log(1 - mu_x))
158
            if ent < min_ent:
159
                min_ent = ent
160
                threshold = it
161
        return threshold
162
### 效果展示
163
#### elain的二值化图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
164
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/segment/Threshold_elain.jpg)
@Dcupqiu
Add files via upload
5 days ago
165
#### woman的二值化图象
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
5 days ago
166
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/segment/Threshold_woman.jpg)
@Dcupqiu
Update 胡煜枫-自动化63-2160504067.md
2 hours ago
167
168
## 附录
169
### 第一题
170
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_citywall.jpg)
171
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_citywall1.jpg)
172
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_citywall2.jpg)
173
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_elain.jpg)
174
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_elain1.jpg)
175
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_elain2.jpg)
176
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_elain3.jpg)
177
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_lena.jpg)
178
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_lena1.jpg)
179
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_lena2.jpg)
180
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_lena4.jpg)
181
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_woman.jpg)
182
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_woman1.jpg)
183
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/hist/hist_woman2.jpg)
184
185
### 第二题
186
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/citywall.jpg)
187
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/citywall1.jpg)
188
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/citywall2.jpg)
189
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/elain.jpg)
190
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/elain1.jpg)
191
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/elain2.jpg)
192
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/elain3.jpg)
193
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/lena.jpg)
194
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/lena1.jpg)
195
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/lena2.jpg)
196
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/lena4.jpg)
197
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/woman.jpg)
198
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/woman1.jpg)
199
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/equal/woman2.jpg)
200
201
### 第三题
202
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/citywall1.jpg)
203
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/citywall2.jpg)
204
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/elain1.jpg)
205
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/elain2.jpg)
206
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/elain3.jpg)
207
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/lena1.jpg)
208
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/lena2.jpg)
209
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/lena4.jpg)
210
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/woman1.jpg)
211
![](https://github.com/Dcupqiu/hw3/blob/master/%E8%83%A1%E7%85%9C%E6%9E%AB-%E8%87%AA%E5%8A%A8%E5%8C%9663-2160504067/HistMatch/woman2.jpg)
212
