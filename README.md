# android Monkey
# Monkey Test簡介
Monkey，猴子。就是像一只猴子，什么都不知道，隨意進行操作。它是Android中的一个命令行工具，可以運行模擬器或是實機上面。實現對性行中的程式進行壓力測試。
# 常用指令
* p ：指定的包名 例：
  * adb shell monkey -p <package>
* s : 隨機操作。配置此参数，则事件顺序一致。例:
  * adb shell monkey -p <package> –s 100
* -v ：Log的詳細程度。有三个级别。等级越高，Log越詳細。例：
  * adb shell monkey -p <package> 100 -v -v -v
* --throttle :操作時間间隔 （實體操作不可能無延遲） 例：
  * adb shell monkey -p <package> --throttle 3000 100
* --ignore-crashes：忽略crashes。使用此參數，如遇到問題，不會終止，直到完成次數。例：
  * adb shell monkey -p <package> 100 -v --ignore-crashes

* --ignore-timeouts：用于指定当应用程序发生ANR（Application No Responding）錯誤時，Monkey是否停止。例：
  * adb shell monkey -p <package> 100 -v --ignore-timeouts

* >:app运行日志存放位置。用来把运行的日志，放在指定的文件中。例：
  * adb shell monkey -p <package> 100 >Usr/local/

# API腳本使用

# android Monkey
# Monkey Test簡介
Monkey，猴子。就是像一只猴子，什么都不知道，隨意進行操作。它是Android中的一个命令行工具，可以運行模擬器或是實機上面。實現對性行中的程式進行壓力測試。
運行的方式有分兩種：系統默認方式、script方式（腳本）
# 常用指令
* p ：指定的包名 例：
  * adb shell monkey -p <package>
* s : 隨機操作。配置此参数，则事件顺序一致。例:
  * adb shell monkey -p <package> –s 100
* -v ：Log的詳細程度。有三个级别。等级越高，Log越詳細。例：
  * adb shell monkey -p <package> 100 -v -v -v
* --throttle :操作時間间隔 （實體操作不可能無延遲） 例：
  * adb shell monkey -p <package> --throttle 3000 100
* --ignore-crashes：忽略crashes。使用此參數，如遇到問題，不會終止，直到完成次數。例：
  * adb shell monkey -p <package> 100 -v --ignore-crashes

* --ignore-timeouts：用于指定当应用程序发生ANR（Application No Responding）錯誤時，Monkey是否停止。例：
  * adb shell monkey -p <package> 100 -v --ignore-timeouts

* >:app运行日志存放位置。用来把运行的日志，放在指定的文件中。例：
  * adb shell monkey -p <package> 100 >Usr/local/

# 常用API
* LaunchActivity(pkg_name, cl_name): 啟動應用的Activity。參數：包名和啟動的Activity。

* Tap(x, y, tapDuration): 模擬一次手指單擊事件。參數：x,y為控制項坐標，tapDuration為點擊的持續時間，此參數可省略。
DispatchPress(keyName): 按鍵。註：keyName值可以百度android keycode列表獲取

* RotateScreen(rotationDegree, persist): 旋轉螢幕。 參數：rotationDegree為旋轉角度， e.g. 1代表90度；persist表示旋轉之後是否固定，0表示旋轉後恢復，非0則表示固定不變。

* DispatchFlip(true/false): 打開或者關閉軟鍵盤。

* LongPress(): 長按2秒。

* PressAndHold(x, y, pressDuration): 模擬長按事件。

* DispatchString(input): 輸入字符串。

* Drag(xStart, yStart, xEnd, yEnd, stepCount): 用於模擬一個拖拽操作。

* PinchZoom(x1Start, y1Start, x1End, y1End, x2Start, y2Start, x2End, y2End, stepCount): 模擬縮放手勢。


* UserWait(sleepTime): 休眠一段時間

* DeviceWakeUp(): 喚醒螢幕。

* ProfileWait: 等待5秒。

# 使用腳本
* 將文件push到手機或模擬器的sdcard中
  * adb push monkey.script /sdcard/
* 然後執行腳本：
  * adb shell monkey -v -f /sdcard/monkey.script
