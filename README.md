# android Monkey
# Monkey Test簡介
Monkey，猴子。就是像一只猴子，什么都不知道，隨意進行操作。它是Android中的一个命令行工具，可以運行模擬器或是實機上面。實現對性行中的程式進行壓力測試。
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
![image](http://www.testwo.com/attachment/201211/15/10203_1352975858ZMmb.jpg)
