# DJ DECK

手机端双盘打碟机。横屏全屏，纯本地运行，不联网、不上传任何音频。

## 功能

- **双盘 A/B**：各自独立的曲目、播放/暂停、CUE、音量
- **BPM 可调**：顶部 TEMPO 直接拖动改数值，也可用 PITCH 微调速率
- **SYNC**：按两盘 BPM 比值一键对齐 B 盘速率，与 A 盘同速
- **无缝循环**：LOOP 以整拍为单位进出，循环点对齐鼓点，衔接不掉拍
- **CROSSFADER**：A/B 横推，含增益曲线
- **FX**：FILTER（低通/高通）、ECHO（延迟反馈）、音量联动
- **SAMPLER**：8 个采样垫，点击即触发
- **视觉**：深色 DJ 台风格，波形 + 唱盘可视化

## 结构

```
app/src/main/java/com/zach/djdeck/MainActivity.java   壳（WebView + 音频/唤醒锁）
app/src/main/assets/web/index.html                    界面与音频引擎（Web Audio API）
```

音频解码、变速、滤波/延迟、循环调度全部在 Web Audio 里完成（BPM 由手动设置，不做自动节拍检测），Java 层只负责沉浸式全屏、屏幕常亮与音频焦点。

## 安装

从仓库根目录的 `DJDeck-1.4.apk` 安装（Android 8.0+ / minSdk 26，横屏使用）。历史版本 1.0 → 1.4 一并保留，方便对比。

## 构建

用 Android Studio 打开根目录即可（Gradle + AGP，compileSdk 34，minSdk 26）。签名请用你自己的 keystore，仓库不含任何签名文件。

## 许可

MIT
