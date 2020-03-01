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
### 通过平台运行源代码
  1.解决不能导入torch库的问题<br>
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


