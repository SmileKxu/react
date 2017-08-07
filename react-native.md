## React-native 如下错误以及解决办法。

#### 1.Application AwesomeProject has not been registered. This is either due to a require() error
during initialization or failure to call AppRegistry. registerComponent.

#### 问题原因: 第一种，是没有注册、或者注册语句写错。正确的写法如下，引号中的 AwesomeProject 一定是这个项目的名称。
AppRegistry.registerComponent("AwesomeProject",() => AwesomeProject);

#### 第二种，可能是8081端口被占用。那么如何测试这个错误，方法如下:
#### 1.在项目文件夹中打开终端，输入 react-native start
#### 2.如果在结果中出现了 Packager can't listen on port 8081, 那么就证实了 8081 端口被占用了。
#### 3.接下来要做的是在终端输入命令: lsof -n -i4TCP:8081，目的是列出被占用的端口列表
#### 4.输入命令 kill -9 <PID>，目的是删除对应的 PID 的占用，这个 <PID> 在第三部的指令中可以看到。
#### 5.删除所有端口然后执行 react-native run-xxx (android或ios) 重启项目就OK。


