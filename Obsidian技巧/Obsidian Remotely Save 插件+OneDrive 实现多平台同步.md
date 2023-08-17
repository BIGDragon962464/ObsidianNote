1. 电脑端安装和设置
首先，需要在 Obsidian 插件社区下载这款插件，然后启用。

在插件设置面板选择按下图进行设置，此处以 onedrive 为例
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171217012.png)

Onedrive 进行同步第一步，choose service 下拉选项中选择 OneDrive for personal (alpha)。

然后点击第二步的 Auth，这是让 Remotely Save 插件获取你的 OneDrive 的一些权限。他会弹出如下提示窗口，只需要点击蓝色的链接，就可以跳转到浏览器
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171217129.png)


浏览器会让你登录微软 OneDrive 账号，登录后会出现如下窗口，点击 Continue
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171217004.png)

浏览器会弹出一个弹窗，要跳转到 Obsidian，点击打开即可。
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171218025.png)

点击打开后，系统会自动跳转到 Obsidian 窗口，并弹出下面的小窗口，这是 Remotely Save 在连接 OneDrive。不要关闭这个窗口，等待一会儿它连接成功后就会自动关闭。
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171218607.png)

然后插件设置面板变成如下图所示即设置成功，该插件会在 OneDrive 云盘创建 (同步) 文件夹 /Apps/remotely-save/你的库名称。
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171218606.png)

这样设置就算完成了。设置这里还有个 check 按钮可以测试连接是否成功。（我自己点击后插件显示连接不上，但是实际使用却没有问题）

2. 使用 Remotely Save 同步
2.1 手动同步
创建、删除或者修改笔记。然后按 Ctrl+P 调出命令，搜索 Remotely Save: start sync，回车。（如下图，我这里将该命令固定到了第一个）
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171218178.png)

右上角会有信息提示同步的进度，如下所示
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171219289.png)

最后看到提示 8/8 Remotely Save finish 即同步成功。

除了命令的方式，也可以在 Obsidian 最左边的按钮列里面找到 Remotely Save 的按钮，如下图
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171219145.png)

按一下按钮即可，效果和上面的调用命令的方式相同。

2.2 设置自动同步
在插件设置面板，可以设置自动多少分钟同步一次，也可以设置软件启动后自动同步一次。
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308171219976.png)

3. 移动端安装和设置

移动端（或者其他平台）想要同步，需要先创建一个库文件夹，然后用 
Obsidian 打开，安装 Remotely Save 插件，插件的设置和上面的一样。
注意的是创建的笔记库的名称要和想要同步的库的名称一样。
	所有以 . 或者 _ 开头的文件或文件夹，这些内容会被视为隐藏文件，默认不会被
	同步。
	这意味着主题文件和插件都不会被同步！需要在移动端重新安装社区插件和主题。
	更新：现已经支持同步. Obsidian 配置文件，可以在设置中打开。

4. 多平台同步流程
在以上所有设置完成之后。

比如在 PC 端修改、编辑文档后， Ctrl+P 调出命令，搜索使用 Remotely Save: start sync 手动同步。然后在手机端查看，先手动同步，完成后，可以在上面进行编辑和改动，改动后再次手动同步一下。

	原则就是，修改笔记前，需要把云端最新内容同步到当前设备，修改笔记后，需要把当前修改同步到云端。这样就可以安全地无冲突地达到同步的效果。

我只是初步尝试了下这个插件，我个人比较倾向于自己手动进行同步管理，因为自动同步在后台运行的时候，即使失败了也不会有提示，这样很可能导致自己的某些修改没有同步到云端，而此时另一个设备同步后，会丢失这些修改。再次编辑后，可能会产生冲突。而该插件本身不处理文件的内容冲突，只是每次都选择修改时间最新的文件。