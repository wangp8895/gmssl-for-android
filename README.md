# gmssl-for-android
Android平台下编译gmssl静态库

## 已验证通过的编译环境
- android-ndk-r13
- 最新的[gmssl][1]代码 **截止到20170724**

## 使用

### 设置环境变量
打开终端，
```
gredit ~/.profile
```
在文本末尾添加ndk变量，如
`export ANDROID_NDK=your ndk dir`

在tools/_shared.sh文件中修改NDK变量
~~~
gredit ./tools/_shared.sh
~~~
修改变量为
`NDK=${ANDROID_NDK}`


### 编译
终端执行
~~~
cd tools
sh ./build-gmssl4android.sh android # armeabi
sh ./build-gmssl4android.sh android-armeabi #armeabi-v7a
sh ./build-gmssl4android.sh android64-aarch64 #arm64_v8a
sh ./build-gmssl4android.sh android-x86 #x86
sh ./build-gmssl4android.sh android64 #x86-64 
sh ./build-gmssl4android.sh android-mips #mips
sh ./build-gmssl4android.sh android-mips64 #mips64
~~~

成功后输出在./output目录下，其中有include头文件和libcrypto.a/libssl.a


# gmssl-for-ios
ios平台下编译gmssl静态库

## 已验证通过的编译环境
- ios10.3 sdk
- 最新的[gmssl][1]代码 **截止到20170919**

## 使用
打开终端
~~~
cd tools
sh ./build-gmssl4ios.sh  #"arm64" "armv7s" "armv7" "i386" "x86_64"
~~~

成功后输出在./output目录下，其中各个ARCH的.a和include头文件，还有合并后的通用库gmssl-universal

## 参考
1. [openssl-for-ios-and-android][2]










[1]: https://github.com/guanzhi/GmSSL
[2]: https://github.com/leenjewel/openssl_for_ios_and_android
