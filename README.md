# spleeter_dynamic_library
基于[spleeter C++](https://github.com/jinay1991/spleeter)现有的动态库可执行文件实现音乐人声伴奏分离过程



The method and environment configuration source [@jinay1991](https://github.com/jinay1991/spleeter) for compiling the [spleeter C++](https://github.com/jinay1991/spleeter) algorithm in this demo.

Thanks for the help given by [@jinay1991](https://github.com/jinay1991), his answer made me solve the current PC side (the problem of the UBUNTU platform).

Spleeter C++算法函数接口逻辑流程文档:[spleeter/doc](https://jinay1991.gitlab.io/spleeter/doc/html/annotated.html)

# 使用方法
## 0、环境配置与编译

使用作者环境在docker+ubuntu：docker pull registry.gitlab.com/jinay1991/spleeter

```
root@docker-desktop:/data/spleeter/spleeter_dynamic_library/bin# cat /etc/issue
Ubuntu 20.04.4 LTS \n \l

```

如果不使用作者环境，需要重新配置，我是在ubuntu18.04系统下配置的：
* Ubuntu 18.04  

To setup developer environment, the project requires following packages.

```bash
apt-get update --fix-missing
sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list && \
sed -i 's/security.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list       
apt-get update --fix-missing

# Installation of general dependencies
apt-get install -y build-essential clang-format clang-tidy clang git git-lfs wget curl gnupg openjdk-11-jdk openjdk-11-jre lcov

# Installation of FFMPEG

apt-get install -y libavcodec-dev libavformat-dev libavfilter-dev libavdevice-dev libswresample-dev libswscale-dev ffmpeg
```

### Build System

This project uses `bazel` build system. To install, run following command or find documentation for installation on office site [here](https://docs.bazel.build/versions/master/install-ubuntu.html#installing-bazel).

For Linux/macOS systems,

```bash
# Installation
curl -fsSL https://bazel.build/bazel-release.pub.gpg | gpg --dearmor > bazel.gpg
mv bazel.gpg /etc/apt/trusted.gpg.d/
echo "deb [arch=amd64] https://storage.googleapis.com/bazel-apt stable jdk1.8" | tee /etc/apt/sources.list.d/bazel.list

#
apt-get update && apt-get install -y bazel

# 报错记录error
#The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 3D5919B448457EE0 E: The repository 'https://storage.googleapis.com/bazel-apt stable InRelease' is not signed.

# 解决方法solv: apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 3D5919B448457EE0
reinstall: apt-get update && apt-get install -y bazel

# 查看安装版本
bazel version
Build label: 5.1.1
Build target: bazel-out/k8-opt/bin/src/main/java/com/google/devtools/build/lib/bazel/BazelServer_deploy.jar
Build time: Fri Apr 8 15:49:48 2022 (1649432988)
Build timestamp: 1649432988
Build timestamp as int: 1649432988


# Command Completion
echo "source /etc/bash_completion.d/bazel" >> ~/.bashrc

# Autoformat
wget https://github.com/bazelbuild/buildtools/releases/download/3.5.0/buildifier
chmod +x buildifier
mv buildifier /usr/bin

# 构建
git clone https://github.com/jinay1991/spleeter.git




```
## 当前在ubuntu18.04编译报错成功解决
The current issue is resolved.
```
ERROR: Could not open 'external/models/5stems/5stems.tflite'.
WARNING: Logging before InitGoogleLogging() is written to STDERR
F0418 09:15:07.654577 85700 tflite_inference_engine.cpp:70] Check failed: model_ Failed to read model external/models/5stems/5stems.tflite
*** Check failure stack trace: ***
Aborted (core dumped)
```
成功编译上述过程文档：[build_run_test.md](https://github.com/KangChou/spleeter_dynamic_library/blob/main/build_run_test.md)




## 1、获取code
先git clone 本目录或到https://github.com/jinay1991

## 2、下载模型
下载地址：https://github.com/jinay1991/spleeter/releases/tag/v2.3 \
存放路径：spleeter_dynamic_library\bin\external\models

![image](https://user-images.githubusercontent.com/36963108/163112952-f095c5dc-cbd1-43fc-9330-b39172f1f2c4.png)

## 3、推理过程

cd 到/data/spleeter/spleeter_dynamic_library/bin 执行./spleeter即可完成推理，最终会在当前目录下生成路径spleeter_dynamic_library\bin\external\audio_example\file下事先准备好的audio_example.wav音频文件。由于是已经生成的可执行文件，想要处理其他音频文件，需要将新拿来的音频文件文件名修改为audio_example.wav替换原有的音频文件即可。

![image](https://user-images.githubusercontent.com/36963108/163114437-7f4a8136-4e8b-402e-aa44-7c2d13b30c69.png)


## 附件
关于libavcodec.so.57的完美解决方法：无动态库libavcodec.so.57等等方法（如果本机能搜索到的话）

解决连接：[https://github.com/KangChou/deepcv_project_demo/tree/main/dynamic_library](https://github.com/KangChou/deepcv_project_demo/tree/main/dynamic_library)


libtensorflow_cc.so获取链接：https://pan.baidu.com/s/1egEIVAGKCzcfP_xtYIEiQg 
提取码：6eca 


![image](https://user-images.githubusercontent.com/36963108/163127525-ae085ba2-5b16-479e-835d-a4e74e99da1c.png)


## Reference

参考spleeter c++ code:https://github.com/jinay1991/spleeter 

- Deezer Research - Source Separation Engine Story - deezer.io blog post:
    * [English version](https://deezer.io/releasing-spleeter-deezer-r-d-source-separation-engine-2b88985e797e)
    * [Japanese version](http://dzr.fm/splitterjp)
- [Music Source Separation tool with pre-trained models / ISMIR2019 extended abstract](http://archives.ismir.net/ismir2019/latebreaking/000036.pdf)

If you use **Spleeter** in your work, please cite:

```BibTeX
@misc{spleeter2019,
  title={Spleeter: A Fast And State-of-the Art Music Source Separation Tool With Pre-trained Models},
  author={Romain Hennequin and Anis Khlif and Felix Voituret and Manuel Moussallam},
  howpublished={Late-Breaking/Demo ISMIR 2019},
  month={November},
  note={Deezer Research},
  year={2019}
}
```

Converted official checkpoint to TFLite Model using https://github.com/tinoucas/spleeter-tflite-convert

## License
The code of **Spleeter** is MIT-licensed.

## Disclaimer
If you plan to use Spleeter on copyrighted material, make sure you get proper authorization from right owners beforehand.

## Note

This repository include a demo audio file `audio_example.mp3` which is an excerpt from

```
Slow Motion Dream by Steven M Bryant
Copyright (c) 2011 Licensed under a Creative Commons Attribution (3.0) license.

http://dig.ccmixter.org/files/stevieb357/34740
Ft: CSoul Alex Beroza & Robert Siek"
```


