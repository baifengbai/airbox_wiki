这部分将介绍如何启动一个ChatBot程序。
## 文件拷贝

### 模型文件
`cp -r ./chatglm /data/chatglm`

将chatglm目录拷贝到AirBox的/data下。chatglm目录包含三个文件一个`chatglm2-6b_2048_int8.bmodel`模型文件，一个是`libtpuchat.so`cpp编译的so文件，最后一个是`tokenizer.model`。

### chatdoc项目文件
`cp -r ./chatbot /data/chatbot`

将chatdoc项目文件拷贝到AirBox的/data下。

### 项目结构树
```
|-- chatbot
    |-- chat.py           -- Python调用cpp推理接口脚本
    |-- web_demo.py       -- 页面交互脚本
    |-- requirements.txt  -- 项目依赖
```
## 依赖安装
在AirBox终端进入到/data/chatbot/目录下。执行

`pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple`

安装项目所需要的依赖。
