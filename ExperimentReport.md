## SixthDemo线性滤波实验报告

姓名：王刚

学号：16020031075

#### 实验中遇到的问题以及解决方法：

1. 本实验是在实验五的基础上做的延伸，所以做起来比较容易，花了一个晚上就解决了。

2. 在完成代码运行 的时候出现了下述图片中的运行错误：

   ![img](https://github.com/Histra/FifthDemo/blob/master/Pictures_ExperimentReport/OK_I_am_fine_01.png) 

   ![img](https://github.com/Histra/FifthDemo/blob/master/Pictures_ExperimentReport/OK_I_am_fine_02.png) 
   再三寻找以后，再三寻找以后，再三寻找以后（真的是再三寻找，所以说三遍，加上这遍是四遍qwq）。终于发现了问题所在，原来我把

   ```c++
   poMulDs->GetRasterBand(1)->RasterIO(GF_Read, 0, 0, Xlen, Ylen, bandR, Xlen, Ylen, GDT_Float64, 0, 0);/// 正确代码
   ```

   写成了

   ```c++
   poMulDs->GetRasterBand(1)->RasterIO(GF_Read, 0, 0, Xlen, Ylen, bandR, Xlen, Ylen, GDT_CFloat64, 0, 0);/// 错误代码
   ```

   于是就报如上错误，真的是太大意了！！
   下面总结一下：

   ![img](https://github.com/Histra/FifthDemo/blob/master/Pictures_ExperimentReport/OK_I_am_fine_03.png) 

#### 实验结果展示：

详见data文件夹下的American_Res.tif文件。

#### 实验反思总结：

​	这个实验是第五个实验。本次实验在GDT_CFloat64这点卡住了，由此可见，敲代码时应该注意严谨性，多了一个字母的代价实在沉重！
​	通过这个实验和实验四，发现图像处理真的越来越有趣了。希望自己能够再接再厉，严谨治学！



