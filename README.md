![Logo](https://github.com/fluttify-project/fluttify-core-example/blob/develop/other/Logo-Landscape.png?raw=true)

# 腾讯直播 Flutter插件

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
2. 腾讯直播的pod比较大, 有198M, pod install时间比较久, 请耐心等待.

## 导入
```dart
import 'package:tencent_live_fluttify/tencent_live_fluttify.dart';
```

## 使用
参考[wiki](https://github.com/fluttify-project/tencent_live_fluttify/wiki).

|       | 社区版 | 专业版 |
|:-----:|:-----:|:-----:|
|  预览  |  ✅ |  ✅   |
|  推流  |  ✅ |  ✅   |
|  恢复推流  |  ✅ |  ✅   |
|  停止推流  |  ✅ |  ✅   |
|  停止预览  |  ✅ |  ✅   |
|  切换摄像头  |  ✅ |  ✅   |
|  设置滤镜  |  ✅ |  ✅   |
|  设置滤镜强度  |  ✅ |  ✅   |
|  设置磨皮强度  |  ✅ |  ✅   |
|  打开/关闭 闪光灯  |  ✅ |  ✅   |
|  摄像头缩放 |  ✅ |  ✅   |
|  调节曝光度 |  ✅ |  ✅   |
