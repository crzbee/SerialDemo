# SerialDemo
> android studio 使用串口。克隆工程。
  
## 1、新建项目

## 2、将相关的这些文件拷进项目的相应位置
  
- jni目录  
- android_serialport_api目录java文件

## 3、修改模块的Gradle文件，加入如下代码，然后点击同步
> 如果没按装`ndk`根据提示按装
```
# 添加到android {...} 标签之中
externalNativeBuild {
    ndkBuild {
        path file('src/main/jni/Android.mk')
    }
}
```

## 4、编译生成so文件
> `Build` -> `Make Project` 
> 经测试，编译出来的so文件所在路径 `app\build\intermediates\stripped_native_libs\debug\out\lib\armeabi-v7a`

## 到此完成，已经可以使用串口通信

# demo
> 快速跑Demo

做好以上步骤后，将相关文件拷贝到目的项目：
- SerialDemoActivity.java   (里面有配置串口，根据自己硬件修改)
- layout.xml
- dimens.xml
- 修改AndroidManifest.xml，将启动的Activity换成SerialDemoActivity

参考链接：
https://blog.csdn.net/cau_eric/article/details/90712496
