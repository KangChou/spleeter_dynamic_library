# spleeter_dynamic_library
Spleeter C++动态库可执行文件实现音乐人声伴奏分离



The method and environment configuration source [@jinay1991](https://github.com/jinay1991/spleeter) for compiling the [spleeter C++](https://github.com/jinay1991/spleeter) algorithm in this demo.

Thanks for the help given by [@jinay1991](https://github.com/jinay1991), his answer made me solve the current PC side (the problem of the UBUNTU platform).

# 使用方法
0、使用环境在docker+ubuntu：docker pull registry.gitlab.com/jinay1991/spleeter

```
root@docker-desktop:/data/spleeter/spleeter_dynamic_library/bin# cat /etc/issue
Ubuntu 20.04.4 LTS \n \l

```

## 1、获取code
先git clone 本目录或到https://github.com/jinay1991

## 2、下载模型
下载地址：https://github.com/jinay1991/spleeter/releases/tag/v2.3 \
存放路径：spleeter_dynamic_library\bin\external\models

![image](https://user-images.githubusercontent.com/36963108/163112952-f095c5dc-cbd1-43fc-9330-b39172f1f2c4.png)

## 3、推理过程

cd 到/data/spleeter/spleeter_dynamic_library/bin 执行./spleeter即可完成推理，最终会在当前目录下生成路径spleeter_dynamic_library\bin\external\audio_example\file下事先准备好的audio_example.wav音频文件。由于是已经生成的可执行文件，想要处理其他音频文件，需要将新拿来的音频文件文件名修改为audio_example.wav替换原有的音频文件即可。

![image](https://user-images.githubusercontent.com/36963108/163114437-7f4a8136-4e8b-402e-aa44-7c2d13b30c69.png)


## 附件：关于libavcodec.so.57的完美解决方法：无动态库libavcodec.so.57等等方法（如果本机能搜索到的话）

解决连接：[https://github.com/KangChou/deepcv_project_demo/tree/main/dynamic_library](https://github.com/KangChou/deepcv_project_demo/tree/main/dynamic_library)


参考spleeter c++ code:https://github.com/jinay1991/spleeter 
