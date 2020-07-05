![Logo](https://github.com/fluttify-project/fluttify-core-example/blob/develop/other/Logo-Landscape.png?raw=true)

# 腾讯直播 Flutter插件
[![pub package](https://img.shields.io/pub/v/tencent_live_fluttify.svg)](https://pub.Flutter-io.cn/packages/tencent_live_fluttify)

**专业版为付费插件, 如有需要请联系qq 382146139**

**专业版为付费插件, 如有需要请联系qq 382146139**

**专业版为付费插件, 如有需要请联系qq 382146139**

## 依赖
```yaml
dependencies:
  flutter:
    sdk: flutter
  tencent_live_fluttify: ^x.x.x
```

## 配置
### Android
1. 如果你的AndroidManifest.xml的application标签配置了`android:label`属性, 那么编译时会出错, 报错信息为:
```text
/Users/xxx/AndroidManifest.xml:10:9-41 Error:
	Attribute application@label value=(new_project_test) from AndroidManifest.xml:10:9-41
	is also present at [com.tencent.liteavsdk:LiteAVSDK_Smart:7.2.8927] AndroidManifest.xml:30:9-41 value=(@string/app_name).
	Suggestion: add 'tools:replace="android:label"' to <application> element at AndroidManifest.xml:8:5-46:19 to override.

FAILURE: Build failed with an exception.
```
你需要做的是按照错误提示, 添加`tools:replace="android:label"`到application标签下, 注意`tools:`命名空间需要另外导入.
完整的修改后的AndroidManifest.xml示例:
```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
          xmlns:tools="http://schemas.android.com/tools" <!--需要添加的代码-->
          package="xxx">
    <application
        android:name="io.flutter.app.FlutterApplication"
        android:label="xxx"
        tools:replace="android:label" <!--需要添加的代码-->
        android:icon="@mipmap/ic_launcher">
        ...
    </application>
</manifest>
```

### iOS
1. 推流需要摄像头和麦克风权限, 并且需要配置为UiKitView使能, 在Info.plist中添加:
```xml
<key>NSMicrophoneUsageDescription</key>
<string>需要麦克风</string>
<key>NSCameraUsageDescription</key>
<string>需要相机</string>
<key>io.flutter.embedded_views_preview</key>
<string>YES</string>
```
2. 腾讯直播的pod比较大, 有198M, `pod install`时间比较久, 请耐心等待, `pod install --verbose`可以观察下载进度.

## 导入
```dart
import 'package:tencent_live_fluttify/tencent_live_fluttify.dart';
```

## 使用
参考[wiki](https://github.com/fluttify-project/tencent_live_fluttify/wiki).

## 社区
| QQ2群 | QQ1群(已满) |
| :----------: | :----------: |
| 加入QQ群讨论 <br/> <img src="https://github.com/fluttify-project/fluttify-project/blob/master/resources/qrcode_1593774649831.jpg?raw=true" height="300"> |加入QQ群讨论 <br/> <img src="https://github.com/fluttify-project/fluttify-project/blob/master/resources/1593774713224_temp_qrcode_share_9993.png?raw=true" height="300"> | 

## 社区版与专业版
|  推流  | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  预览  |  ✅ |  ✅   |
|  推流  |  ✅ |  ✅   |
|  暂停推流  |  ✅ |  ✅   |
|  停止推流  |  ✅ |  ✅   |
|  停止预览  |  ✅ |  ✅   |
|  切换前后摄像头  |  ✅ |  ✅   |
|  打开/关闭闪光灯  |  ✅ |  ✅   |
|  播放背景音乐  |  ✅ |  ✅   |
|  停止背景音乐  |  ✅ |  ✅   |
|  暂停背景音乐  |  ✅ |  ✅   |
|  恢复背景音乐  |  ✅ |  ✅   |
|  麦克风音量大小  |  ✅ |  ✅   |
|  背景音乐音量大小  |  ✅ |  ✅   |
|  背景音乐音调高低  |  ✅ |  ✅   |
|  事件处理  |  ✅ |  ✅   |
|  设置观众看到的画面清晰度  |  ☑️ |  ✅   |
|  美颜  |  ☑️ |  ✅   |
|  滤镜  |  ☑️ |  ✅   |
|  调整摄像头的焦距  |  ☑️ |  ✅   |
|  设置曝光比例  |  ☑️ |  ✅   |
|  观众端镜像效果  |  ☑️ |  ✅   |
|  横屏推流  |  ☑️ |  ✅   |
|  隐私模式（垫片推流）  |  ☑️ |  ✅   |
|  设置混音效果  |  ☑️ |  ✅   |
|  设置变调效果  |  ☑️ |  ✅   |
|  设置 Logo 水印  |  ☑️ |  ✅   |
|  开始本地录制  |  ☑️ |  ✅   |
|  停止本地录制  |  ☑️ |  ✅   |
|  发送 SEI 消息  |  ☑️ |  ✅   |

|  拉流  | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  播放  |  ✅ |  ✅   |
|  恢复播放  |  ✅ |  ✅   |
|  恢复直播  |  ✅ |  ✅   |
|  是否在播放中  |  ✅ |  ✅   |
|  暂停播放  |  ✅ |  ✅   |
|  停止播放  |  ✅ |  ✅   |
|  事件处理  |  ✅ |  ✅   |
|  清晰度无缝切换  |  ☑️ |  ✅   |
|  画面调整  |  ☑️ |  ✅   |
