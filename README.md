`此文档可以解决大部分 mac sublimeText3 安装插件的问题`

## sublime3 在mac手动安装Package Control
1. 打开Packages目录，Preferences > Browse Packages 就可以进入这个目录。
![获取Packages路径](http://img4.07net01.com/upload/images/2017/01/23/160787231535281.png)

2. 打开终端，cd 到Packages的路径

3. 将Installed Packages里面的内容清空，如图
![将Installed Packages里面的内容清空](http://img4.07net01.com/upload/images/2017/01/23/160787231535283.png)

4. 终端执行下面命令：
```bash
$ git clone https://github.com/wbond/sublime_package_control.git "Package Control"
```
5. 重启sublime text即可

## 解决Sublime Text3 Package Control 在菜单栏中不显示
1. Preferences > Settings 打开Preferences.sublime-settings-Users 文件 将里面的 ignored_package的'Package Control'去除
eg.
```json
"ignored_packages":
[
    "Vintage",
    "Package Control"
]
```
改成
```json
"ignored_packages":
[
    "Vintage"
]
```



## 解决sublime package control 出现There are no packages available for installation

### 自己本地开个服务器，把channel_v3.json文件复制下来,放到document中（可以自己指定）
 python -m SimpleHTTPServer 8080

### 浏览器中访问http://127.0.0.1:8080/channel_v3.json如果能看到，说明成功了
### 配置
![配置package control](http://upload-images.jianshu.io/upload_images/375697-2b8ed76c888f2396.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

进入package control的settings中，如上图
把里面的http://packagecontrol.io/channel_v3.json替换成http://127.0.0.1:8080/Documents/channel_v3.json

```json
"channels": [
        "http://127.0.0.1:8080/Documents/channel_v3.json"
    ]
```