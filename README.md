# 毕业设计周报
## 2020年3月1日
主要翻译并且详细阅读Learning to Simplify和Mastering Sketching两篇论文<br>
找到作者发布的网站http://hi.cs.waseda.ac.jp/~esimo/research/sketch/<br>
并从GitHub上下载源代码https://github.com/bobbens/sketch_simplification
### 该项目基于PyTorch深度学习框架
```
  [packages]
  torch = "==0.4.1"
  torchvision = "*"
  [requires]
  python_version = "3.7"
```
### 搭建环境
```
  pip install torch torchvision
```
```
  pip install pillow
```
### 通过pycharm平台运行源代码
  1.解决pycharm不能导入torch库的问题<br>
  2.解决ModuleNotFoundError: No module named 'torch.utils.serialization'报错<br>
    因为在torch新版本中删除了load_lua，需要安装torchfile
  #### 安装torchfile
```
  pip install torchfile
```
```
  from torch.utils.serialization import load_lua 改为 import torchfile
  load_lua 改为 torchfile.load
```
### 第一次使用之前，需要下载已经训练好的模型
```
  bash bash download_models.sh
```
```
  download_model "MSE" "model_mse.t7" "http://hi.cs.waseda.ac.jp/~esimo/data/sketch_mse.t7"
  download_model "GAN" "model_gan.t7" "http://hi.cs.waseda.ac.jp/~esimo/data/sketch_gan.t7"
```


## 2020年4月26日
### 修改参数：
1.epoch次数：增加epoch次数后（200次->400次），函数图像并不收敛（图1），且训练时间较长（90h+),测试结果和200次时几乎没有区别；
2.BatchSize：增大BatchSize的值1->4，函数图像收敛（图2），训练时间较短（36h),测试结果稍微好了一些，但复杂的图片效果依然不理想；
3.learningrate：减小learningrate的值0.0002->0.0001，函数图像收敛较慢，目前还在程序还在运行当中；
## 毕业论文：
1.确定论文大纲，参考了几篇内容相似的硕博论文的格式；
2.正在写绪论；
3.外国文献翻译已经完成；
## 接下来的任务：
1.继续调整模型参数，记录好每次的结果；
2.完成毕业论文的其他部分；


