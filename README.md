![Logo](https://github.com/fluttify-project/fluttify-core-example/blob/develop/other/Logo-Landscape.png?raw=true)

# 腾讯直播 Flutter插件
[![pub package](https://img.shields.io/pub/v/tencent_live_fluttify.svg)](https://pub.Flutter-io.cn/packages/tencent_live_fluttify)

**专业版为付费插件, 如有需要请联系qq 382146139**

**专业版为付费插件, 如有需要请联系qq 382146139**

**专业版为付费插件, 如有需要请联系qq 382146139**

# Fluttify系列插件
|  名称  | 描述 | 仓库 |
|:-----:|:-----:|:-----:|
| [高德地图](https://github.com/fluttify-project/amap_map_fluttify)  |  高德地图地图组件, 提供地图控件 | [![pub package](https://img.shields.io/pub/v/amap_map_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_map_fluttify) |
| [高德定位](https://github.com/fluttify-project/amap_location_fluttify)  |  高德地图定位组件, 提供独立的定位功能 | [![pub package](https://img.shields.io/pub/v/amap_location_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_location_fluttify) |
| [高德搜索](https://github.com/fluttify-project/amap_search_fluttify)  |  高德地图搜索组件, 提供poi搜索等功能 | [![pub package](https://img.shields.io/pub/v/amap_search_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_search_fluttify) |
| [百度地图](https://github.com/fluttify-project/bmap_map_fluttify)  |  百度地图, 包含了地图控件, 定位以及搜索poi等功能 | [![pub package](https://img.shields.io/pub/v/bmap_map_fluttify.svg)](https://pub.Flutter-io.cn/packages/bmap_map_fluttify) |
| [百度人脸识别](https://github.com/fluttify-project/baidu_face_flutter)  |  百度人脸识别, 提供活体检测等功能 | [![pub package](https://img.shields.io/pub/v/baidu_face_flutter.svg)](https://pub.Flutter-io.cn/packages/baidu_face_flutter) |
| [网易直播](https://github.com/fluttify-project/netease_live_fluttify)  |  网易直播推流组件 | [![pub package](https://img.shields.io/pub/v/netease_live_fluttify.svg)](https://pub.Flutter-io.cn/packages/netease_live_fluttify) |
| [网易云信](https://github.com/fluttify-project/nim_fluttify)  |  网易云信 IM组件 | [![pub package](https://img.shields.io/pub/v/nim_fluttify.svg)](https://pub.Flutter-io.cn/packages/nim_fluttify) |
| [腾讯直播](https://github.com/fluttify-project/tencent_live_fluttify)  |  腾讯直播, 包含推流组件和播放组件 | [![pub package](https://img.shields.io/pub/v/tencent_live_fluttify.svg)](https://pub.Flutter-io.cn/packages/tencent_live_fluttify) |
| [腾讯IM](https://github.com/fluttify-project/tim_fluttify)  |  腾讯IM组件 | [![pub package](https://img.shields.io/pub/v/tim_fluttify.svg)](https://pub.Flutter-io.cn/packages/tim_fluttify) |
| [腾讯地图](https://github.com/fluttify-project/tmap_map_fluttify)  |  腾讯地图组件 | [![pub package](https://img.shields.io/pub/v/tmap_map_fluttify.svg)](https://pub.Flutter-io.cn/packages/tmap_map_fluttify) |
| [讯飞语音合成](https://github.com/fluttify-project/xftts_fluttify)  |  腾讯语言合成组件, 提供文字转语言功能 | [![pub package](https://img.shields.io/pub/v/xftts_fluttify.svg)](https://pub.flutter-io.cn/packages/xftts_fluttify) |
| [极光统计](https://github.com/fluttify-project/janalytics_fluttify)  |  极光统计组件, 提供异常上报等功能 | [![pub package](https://img.shields.io/pub/v/janalytics_fluttify.svg)](https://pub.flutter-io.cn/packages/janalytics_fluttify) |
| [阿里云RTC](https://github.com/fluttify-project/ali_rtc_fluttify)  |  阿里云实时音视频 | [![pub package](https://img.shields.io/pub/v/ali_rtc_fluttify.svg)](https://pub.flutter-io.cn/packages/ali_rtc_fluttify) |
| [环信](https://github.com/fluttify-project/easemob_im_fluttify)  |  环信IM | [![pub package](https://img.shields.io/pub/v/easemob_im_fluttify.svg)](https://pub.flutter-io.cn/packages/easemob_im_fluttify) |
| [未完待续...](https://github.com/fluttify-project)  |  如有其它需求, 请联系qq 382146139 | ![fluttify](https://img.shields.io/badge/fluttify-welcom-green) |

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
| QQ群 |
| :----------: |
| <img src="https://github.com/fluttify-project/fluttify-project/blob/master/resources/1593774713224_temp_qrcode_share_9993.png?raw=true" height="300"> | 

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

## LICENSE
> Copyright (C) 2020 yohom
> 
> This program is free software: you can redistribute it and/or modify
> it under the terms of the GNU General Public License as published by
> the Free Software Foundation, either version 3 of the License, or
> (at your option) any later version.
> 
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.
> 
> You should have received a copy of the GNU General Public License
> along with this program.  If not, see <https://www.gnu.org/licenses/>.
