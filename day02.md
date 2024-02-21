# python 编译器的安装和环境配置

教程中给出的还是经典的pycharm和jupitor的编辑器

## 问题
问题出现在环境配置，需要选择anaconda的环境，首先在setting里找到interpretor,其次要在conda 环境中选择 conda 目录下的scripts目录下的可执行文件conda.exe，然后选择使用已存在环境，然后选择我设置的
环境的名字，比如目前我使用的anaconda环境名字是pytorch

然后使用：
import torch
torch.cuda.is_available()
True
去进行检测是否导入环境成功。
