## pyqt5的下载
* 可以直接在pycharm上面下载pyqt5 他会自动下载其他附属安装包
* 也可以在管理员命令行(cmd)中下载   
cmd中输入： ***pip install pyqt5***
***

## pyqt5的打开
* 需要安装包**pyqt5-tools**
* 可在pycharm中下载
* 也可以使用cmd   
cmd中输入： ***pip install pyqt5-tools***

* 下载好之后可以在cmd中输入下载代码查看是否已经下载好，并且**查看下载到的目录**    
或在cmd中输入**pip list** 查看
***

## pyqt5的使用
* 找到下载到的目录：**D:----\Lib\site-packages\qt5_applications\Qt\bin**   
* 点击**designer**打开
* 选择 **widget**创建
* 在**左侧辅助栏中选择label添加UI窗口**
***

## 验证pyqt5是否安装
* 在cmd中输入***pyuic5***   
显示：**Error: one input ui-file must be specified**   
即安装成功
***

## 在python使用UI
import sys

from PyQt5 import QtWidgets,QtGui,QtCore

#创建一个应用(Application)对象,sys.argv参数是一个来自命令行的参数列表,

#Python脚本可以在shell中运行。这是我们用来控制我们应用启动的一种方法。


app = QtWidgets.QApplication(sys.argv)


#创建一个widget组件基础类


windows = QtWidgets.QWidget()


#设置widget组件的大小(w,h)


windows.resize(500,500)


#设置widget组件的位置(x,y)

windows.move(100,100)

"""

#设置widget组件的位置居中

qr = windows.frameGeometry()

cp = QtWidgets.QDesktopWidget().availableGeometry().center()

qr.moveCenter(cp)

windows.move(qr.topLeft())

"""

#等同于 w.resize(500,500)和w.move(100,100)两句结合,(x,y,w,h)

#windows.setGeometry(100,100,500,500)

#给widget组件设置标题

windows.setWindowTitle('标题')

#给widget组件设置图标

windows.setWindowIcon(QtGui.QIcon('2.png'))

#设置lable信息

label = QtWidgets.QLabel(windows)

label.setGeometry(QtCore.QRect(100, 10, 100, 60))

label.setText('hello word！')

label.setObjectName('label')

#show()方法在屏幕上显示出widget组件

windows.show()

#循环执行窗口触发事件，结束后不留垃圾的退出，不添加的话新建的widget组件就会一闪而过

sys.exit(app.exec_())



