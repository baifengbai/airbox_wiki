这部分将介绍如何启动一个ChatDoc程序。
## 文件拷贝

### 模型文件
`cp -r ./chatglm /data/chatglm`

将chatglm目录拷贝到AirBox的/data下。chatglm目录包含三个文件一个`chatglm2-6b_2048_int8.bmodel`模型文件，一个是`libtpuchat.so`cpp编译的so文件，最后一个是`tokenizer.model`。

### chatdoc项目文件
`cp -r ./chatdoc /data/chatdoc`

将chatdoc项目文件拷贝到AirBox的/data下。

## 依赖安装
在AirBox终端进入到/data/chatdoc/目录下。执行

`pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple`

安装项目所需要的依赖。

有些网络条件下，nltk工具包将下载失败，解决办法是将我们提供的nltk_data文件夹拷贝到AirBox用户跟目录，即`cp -r ./nltk_data ~/`。