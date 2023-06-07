### 一、配置python环境
配置Python环境的方式很多，其中最常用也是最好用的方式通过安装anaconda工具（我的理解anaconda相当于一个Python解释器库容器）。
下载安装anaconda之后，找到安装目录的的三个子目录（我的安装目录为：D:\anaconda_for_python）：
D:\anaconda_for_python
D:\anaconda_for_python\Scripts
D:\anaconda_for_python\Library\bin
将以上三个变量配置为环境变量；

验证，在终端输入——
```shell
conda env list
```
如果命令能正常显示结果表示conda正常安装。
创建自己的python解释器环境。这里选择python3.11版本，切选择使用目录创建。
```text
C:\Users\zb>d:
D:\>cd 03PythonCondaEnvs
D:\03PythonCondaEnvs>conda create --prefix=ChatGLM6B_python311 python=3.11
```
创建完毕后，可以通过如下命令查询所有的conda 之 python解释器环境：
```text
D:\03PythonCondaEnvs>conda env list
# conda environments:
#
                         D:\03PythonCondaEnvs\ChatGLM6B_python311
base                     D:\anaconda_for_python
```

### 二、IDE工具
安装Pycharm工具

### 三、安装git工具
去git官网下载最新的git工具。按照向导安装git工具。

### 四、下载模型
因为我的电脑是6G的GPU。所以选择模型文件为：chatglm-6b-int4模型。
去https://huggingface.co/THUDM/chatglm-6b-int4 下载模型文件到指定目录.
使用如下git命令进行下载安装。
创建计划安装模型文件的目录，然后在该目录下鼠标右键，打开 `git bash here`选项，然后按照目标网址给的两个命令通过git方式将模型下载下来。
```text
git lfs install
git clone https://huggingface.co/THUDM/chatglm-6b-int4
``` 
输入克隆命令后，需要等待一段时间，因为模型文件有近4G。

### 五、下载本项目文件
进入本项目地址： https://github.com/THUDM/ChatGLM-6B.git 地址，在目标目录，这里的目录是：D:\02ChatGLM_6B_Learn\ChatGLM_6b_projects下打开右键菜单选项`git bash here`。
然后输入克隆代码命令：
```text
git clone https://github.com/THUDM/ChatGLM-6B.git
```
将远程仓库代码克隆到本地。

### 六、添加依赖库
打开dos终端，进入目标解释器环境。
```text
Microsoft Windows [版本 10.0.22621.1555]
(c) Microsoft Corporation。保留所有权利。

C:\Users\zb>d:

D:\>cd D:\02ChatGLM_6B_Learn\ChatGLM_6b_projects\ChatGLM-6B

D:\02ChatGLM_6B_Learn\ChatGLM_6b_projects\ChatGLM-6B>conda env list
# conda environments:
#
                         D:\03PythonCondaEnvs\ChatGLM6B_python311
base                     D:\anaconda_for_python


D:\02ChatGLM_6B_Learn\ChatGLM_6b_projects\ChatGLM-6B>conda activate D:\03PythonCondaEnvs\ChatGLM6B_python311

(D:\03PythonCondaEnvs\ChatGLM6B_python311) D:\02ChatGLM_6B_Learn\ChatGLM_6b_projects\ChatGLM-6B>pip install -r requirements.txt
```
通过如上操作安装依赖库。

### 七、验证cuda
因为本机是6G的GPU。所以想使用GPU进行推理。 
前提: torch的版本是GPU。
然不是，
参考攻略： https://zhuanlan.zhihu.com/p/629898957
解决了问题。

### 八、运行web_demo.py
按照步骤6，进入目标解释权环境和目录。 运行`web_demo.py`.
```text
python web_demo.py
```

