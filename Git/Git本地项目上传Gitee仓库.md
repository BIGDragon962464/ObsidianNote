参考： https://blog.csdn.net/weixin_46508271/article/details/121202829
### 前提条件
1. 本地电脑安装 Git 客户端

2. 本地已有项目

3. Gitee 注册好了账户

### 具体操作
####  1 、登录码云
https://gitee.com
点击个人头像旁边的加号，选择新建仓库
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308100942680.png)

#### 2 、填写相关信息
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308100943260.png)
创建后得到远程仓库：
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308100943379.png)
#### 3 、在本地项目文件夹右击鼠标点击 Git Bash Here

#### 4 、输入` git init`，这个目录变成 git 可以管理的仓库，会出现一个. Git 文件夹，如果没出现的话需要选择“显示隐藏文件”（不会的同学自行百度一下）
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308100944023.png)
#### 5 、绑定本地仓库与远程仓库：`git remote add origin [远程仓库的具体地址]`
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308100944486.png)

#### 6 、添加文件到暂存区：`git add .`(注意后面的点表示目录下的所有文件，点前面还有一个空格不要漏掉了)

#### 7 、将暂存区的文件提交至仓库中：`git commit -m '本次的提交信息'`

#### 8 、远程库与本地同步合并， `git pull origin master`
注意，此处可能会报错：fatal: refusing to merge unrelated histories
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308100944830.png)

问题产生原因：本地库和远程库没有相关性，然后本地要去推送到远端，远端觉得这个本地库跟自己不相干，所以告知无法合并。
解决方法：操作命令后面加 --allow-unrelated-histories 变为：
`git pull origin master --allow-unrelated-histories`

#### 9、 将本地的分支版本上传到远程并合并: `git push origin master`
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308100944280.png)

#### 10、大功告成
![image.png](https://gitee.com/BIGDragon962464/my-picture/raw/master/Picture/202308100945666.png)
