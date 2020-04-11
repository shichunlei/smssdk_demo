# smssdk_demo

> 这是一个基于SMSSDK功能的扩展的Flutter插件使用demo。使用此插件能够帮助您在使用Flutter开发应用时,快速地实现获取验证码功能。


- [插件主页](https://pub.dartlang.org/packages/mobsms#-readme-tab-)

- [Demo例子](https://github.com/shichunlei/smssdk_demo)


## 开始集成


### 1.参考 Flutter官方插件[集成文档](https://pub.dev/packages/mobsms#-readme-tab-)

> 在pubspec.yaml文件中加入下面依赖

```yaml
dependencies:
  mobsms:
```

> 然后执行：`flutter packages get` 导入package

> 在你的dart工程文件中，导入下面头文件，开始使用

```dart
import 'package:mobsms/mobsms.dart';
```

- iOS： 平台配置参考 [iOS集成文档](http://www.mob.com/wiki/detailed?wiki=SMSSDK_for_ios_kuaisujicheng&id=23)

> 实现 “一、注册应用获取appKey 和 appSecret”

> 实现 “二、2.配置appkey和appSecret”


- Android： 导入SMSSDK相关依赖

> 在项目根目录的build.gradle中添加以下代码：

```gradle中添加以下代码
dependencies {
        classpath 'com.android.tools.build:gradle:3.5.0'
        classpath 'com.mob.sdk:MobSDK:+'
    }
```


> 在/android/app/build.gradle中添加以下代码：

```gradle
apply plugin: 'com.android.application'
apply from: "$flutterRoot/packages/flutter_tools/gradle/flutter.gradle"
// 导入MobSDK
apply plugin: 'com.mob.sdk'

MobSDK {
    appKey ""
    appSecret ""
}
```


### 2.接口方法说明

- (1) 文本获取验证码：

getTextCode

```dart
Smssdk.getTextCode("手机号","区号(中国填写86)","模板id", (dynamic ret, Map err){
   if(err!=null){......}
   else
   {........}
});
```


- （2）语言获取验证码

**getVoiceCode**

```dart
Smssdk.getVoiceCode("手机号","区号(中国填写86)", (dynamic ret, Map err){
    if(err!=null){......}
    else
     {......}
});
```


- （3）提交验证码

**commitCode**

```dart
Smssdk.commitCode("手机号","区号(中国填写86)","验证码", (dynamic ret, Map err){
   if(err!=null){......}
   else
     {......}
});
```


- （4）获取国家列表

**getSupportedCountries**

```dart
Smssdk.getSupportedCountries((dynamic ret, Map err){
   if(err!=null){......}
   else
   {......}
});
```



- （5）获取应用内好友

**getFriends**

```dart
Smssdk.getFriends((dynamic ret, Map err){
   if(err!=null){......}
   else{......}
});
```


- （6）提交用户信息

**submitUserInfo**

```dart
    Smssdk.submitUserInfo("3241241", "SmsSDK_Flutter_User_3241241",
                  "http://download.sdk.mob.com/510/deb/0c0731ac543eb71311c482a2e2.png",
                        "区号(中国填写86)", "手机号", (dynamic ret, Map err){
       if(err!=null){......}
       else
        {......}
    });
```

- (7)获取版本号

**getVersion**

```dart
Smssdk.getVersion((dynamic ret, Map err){
   if(err!=null){......}
   else
   {......}
});
```


- （8）是否开启允许通讯录提示框

**enableWarn**

```dart
Smssdk.enableWarn(true,(dynamic ret, Map err){
   if(err!=null){......}
   else
   {......}
});
```









