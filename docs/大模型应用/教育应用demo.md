这部分将介绍如何启动一个EduGPT程序。
## 文件下载

![Alt text](<../imgs/1696061589146.jpg>)

扫描上面这个二维码下载，或者点击[百度网盘下载地址。](https://pan.baidu.com/s/1N6HZy9oq4ZnyRyz9MaDU6Q?pwd=1684)可根据使用的文件，按需下载。


### 模型文件

EduGPT仅推荐使用int8-2048模型。因此所需模型文件在位于`~/airbox-app/chatglm应用/chatglm-int8-2048/`路径下。

执行`cp -r ~/airbox-app/chatglm应用/chatglm-int8-2048/ /data`

将chatglm-int8-2048目录拷贝到AirBox的/data下。chatglm-int8-2048目录包含三个文件一个`chatglm2-6b_2048_int8.bmodel`模型文件，一个是`libtpuchat.so`cpp编译的so文件，最后一个是`tokenizer.model`。

### 项目结构树
```
|-- chatglm-int8-2048     -- 模型文件
    |-- chatglm2-6b_2048_int8.bmodel
    |-- libtpuchat.so
    |-- tokenizer.model
|-- airbox_edugpt
    |-- ...
    |-- app.py            -- 启动脚本
```

### chatdoc项目文件

- `cd /data/`
- `git clone https://github.com/zhengorange/airbox_edugpt.git`

## 依赖安装
在AirBox终端进入到/data/airbox_edugpt/目录下。执行

`pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple`

安装项目所需要的依赖。

有些网络条件下，nltk语料将下载失败，解决办法是将我们提供的nltk_data文件夹拷贝到AirBox用户跟目录，即`cp -r ~/airbox-app/nltk_data ~/`。

百度网盘链接: https://pan.baidu.com/s/1yFrk0Jtmbfr-nHnWvXF6AA?pwd=x5rw
下载完成将下载的embedding文件夹替换airbox_edugpt目录下的embedding。


## 项目启动

- 进入项目目录`cd /data/airbox_edugpt `
- 启动项目`python3 app.py`
