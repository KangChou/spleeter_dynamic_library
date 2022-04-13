# spleeter_dynamic_library
Spleeter C++动态库可执行文件实现音乐人声伴奏分离



The method and environment configuration source [@jinay1991](https://github.com/jinay1991/spleeter) for compiling the [spleeter C++](https://github.com/jinay1991/spleeter) algorithm in this demo.

Thanks for the help given by [@jinay1991](https://github.com/jinay1991), his answer made me solve the current PC side (the problem of the UBUNTU platform).

# 使用方法
## 0、环境配置与编译

使用环境在docker+ubuntu：docker pull registry.gitlab.com/jinay1991/spleeter

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


