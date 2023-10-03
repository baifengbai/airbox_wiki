这部分将介绍如何启动一个ChatBot程序。
## 文件下载

![Alt text](<../imgs/1696061589146.jpg>)

扫描上面这个二维码下载，或者点击[百度网盘下载地址。](https://pan.baidu.com/s/1N6HZy9oq4ZnyRyz9MaDU6Q?pwd=1684)可根据使用的文件，按需下载。




### 模型文件
网盘中共三种模型文件，分别是int8-2048，int8-1024，int4-512，位于`~/airbox-app/chatglm应用/`路径下。

假设我们使用int8-2048模型(采用int8的量化技术，最大token长度为2048)，具体操作方法是`cp -r ~/airbox-app/chatglm应用/chatglm-int8-2048 /data/`，即拷贝chatglm-int8-2048目录到AirBox的/data下。

chatglm-int8-2048目录包含三个文件一个`chatglm2-6b_2048_int8.bmodel`模型文件，一个是`libtpuchat.so`cpp编译的so文件，最后一个是`tokenizer.model`。

### chatdoc项目文件
`cp -r ~/airbox-app/chatglm应用/chatbot /data`

将chatdoc项目文件拷贝到AirBox的/data下。

### 项目结构树
```
|-- chatbot
    |-- chat.py           -- Python调用cpp推理接口脚本
    |-- web_demo.py       -- 页面交互脚本
    |-- requirements.txt  -- 项目依赖
    |-- config.ini        -- 模型文件配置
```

### config.ini配置文件

```
[llm_model]
libtpuchat_path = ../chatglm-int8-2048/libtpuchat.so
bmodel_path = ../chatglm-int8-2048/chatglm2-6b_2048_int8.bmodel
token_path = ../chatglm-int8-2048/tokenizer.model
```
config.ini需要配置正确的模型文件，默认是选择int8-2048的模型。若要改更为其他模型文件，请修改配置文件中的模型文件路径。

## 依赖安装
在AirBox终端进入到/data/chatbot/目录下。执行

`pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple`

安装项目所需要的依赖。

## 项目启动

- 进入项目目录`cd /data/chatbot `
- 启动项目`python3 web_demo.py`