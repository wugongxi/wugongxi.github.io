
```
adb shell vm size   查看设备分辨率
adb shell vm density 查看设备像素密度
adb install -r <local apkPath>  安装
adb uninstall <packageName>  卸载
adb shell am start -n <packageName>/<packageName.launchActivity>  启动
adb shell am force-stop <packageName> 停止应用
adb shell pm clear <packagename> 清除数据

adb shell logcat  查看日志
```
