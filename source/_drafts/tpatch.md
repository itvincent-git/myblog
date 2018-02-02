## TPatch——Tinker补丁方案

### Tinker优点

低侵入性



### 安装

#### gradle配置



#### 生成基准apk

- gradle运行`assembleDebug`来生成基准apk

- 安装基准apk`adb install -r app/build/outputs/apk/debug/app-debug.apk`

- 记下`app/build/bakApk`中刚生成的备份apk文件名，留作下面使用

  ​

#### 生成Patch

- 修改app里的.gradle文件，将`tinkerOldApkPath`的地址改为`app/build/bakApk`中刚生成的备份apk路径，将以这个**bakApk**为基准构建Patch包
- gradle运行`tinkerPatchDebug`生成Patch包，包括不带签名的apk：**patch_unsigned.apk**；带签名的apk：**patch_signed.apk**； 用7zip压缩过的： **patch_signed_7zip.apk**


- 推送7zip压缩包至sdcard中`adb push app/build/outputs/apk/tinkerPatch/debug/patch_signed_7zip.apk   /sdcard/`

#### 重启

必须要进程杀掉，再重启，patch才能生效



#### Release构建

- 生成基准apk时，除了要记下备份apk，还要记下备份**mapping.txt**和**R.txt**文件
- 修改.gradle时，还要将`tinkerApplyMappingPath`修改为刚才记下的mapping.txt路径 ，`tinkerApplyResourcePath` 修改为R.txt路径
- gradle运行`tinkerPatchRelease`生成**Release Patch**包
- 推送压缩包改为推送`adb push app/build/outputs/apk/tinkerPatch/release/patch_signed_7zip.apk   /sdcard/`路径改为**release**下的



### 后台升级配置

#### 传输安全

- 使用https传输

- 指定appversion升级到指定的patchversion
- 支持版本管理



### 进阶工作

- TinkerLog改为MLog实现



### 缺陷

- 需要重启app，准确来说是要杀进程的重启才行
- 在loadPatch的时候占用内存高，由于要做差分算法生成代码


- 在loadPatch的时间比较长