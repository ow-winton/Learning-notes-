# 1. 安装anaconda， 一个集成了多样的研究工具包的软件
   
保存好安装路径，一路默认安装， 打开anaconda prompt， 如果默认出现的为（base），那么就是安装成功

# 2. 安装显卡驱动 + coda 工具包 
检查显卡驱动是否正确安装： 使用任务管理器，检查GPU 是否正确显示型号，如果正确显示型号，那么显卡驱动就是正确安装的

# 3. 安装pytorch 之前： 学习如何正确管理环境 
由于项目有着不同的环境，比如一些基于pytorch0.4 另外一些基于 1.0，那么我们需要正确的管理环境来分别对不同的项目进行运行和管理
(base) C:\Users\21293>conda create -n pytorch python=3.6 创建python 3.6 的环境
-n: name  python =3.6

激活环境  ：
To activate this environment, use
$ conda activate pytorch
To deactivate an active environment, use
$ conda deactivate


激活环境后用 pip list 检查包配置环境 

(base) C:\Users\21293>conda activate pytorch

(pytorch) C:\Users\21293>pip list
Package      Version
------------ ---------
certifi      2021.5.30
pip          21.2.2
setuptools   58.0.4
wheel        0.37.1
wincertstore 0.2

# 4.安装conda ，激活pytorch 环境：
pytorch官网选择合适自己的系统的pytorch版本  
这里由于环境是python 3.6 ，所以选择的conda版本是1.4（本打算找1.3，但是没有，它的cuda版本是9.2）
conda install pytorch==1.4.0 torchvision==0.5.0 cudatoolkit=9.2 -c pytorch



# Warning: 
最开始我是用的anaconda 3.5 python 3.6 pytorch 1.4的版本

然而在执行>>> torch.cuda.is_available()  时报错 false ，在更新pytorch 和python 以及cuda版本后依然没用，最终尝试更新anaconda版本 解决了该问题
然而我不理解的是anaconda本身不过是一个包管理工具，为什么他本身会影响这个功能

询问chatgpt给出的答复是：
Anaconda本身的版本较老可能导致torch.cuda.is_available()返回False的情况，尤其是在使用较新的PyTorch版本时。torch.cuda.is_available()
用于检查系统是否支持CUDA（NVIDIA GPU加速），
而CUDA的支持通常需要与安装的PyTorch版本相匹配的NVIDIA驱动程序和CUDA工具包。
更新Anaconda本身并不直接影响torch.cuda.is_available()的结果，但如果你使用的PyTorch版本要求较新的NVIDIA驱动程序和CUDA工具包，
而你的Anaconda版本又较老，那么这可能导致torch.cuda.is_available()返回False。

