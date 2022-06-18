# xxx.app 已损坏，无法打开，你应该将它移到废纸篓/打不开 xxx，因为它来自身份不明的开发者解决方法

##  为什么会出现？

这是 macOS 启用了新的安全机制的问题。

苹果默认是只允许安装自家【App Store】来源的应用，如果你想安装第三方的应用，那么需要在【系统偏 好设置 -> 安全性与隐私 -> 通用】中勾选【App Store 和被认可的开发者】选项。而被认可的开发者是需要购买苹果的企业证书对应用进行签名，然后再提交给苹果审核才可以，这对破解应用来说很不现实，因为破解应用必定会修改应用的文件从而导致签名失效而运行显示【已损坏】。另外一些开源免费类应用没有收益（用户主动打赏太难了），所以开发者一般也不会购买证书签名。

解决方法就是去开启【任何来源】选项了，但是 macOS 默认是隐藏了这个设置的，需要用户手动通过终端执行命令行代码来开启。

下面就让 MacWk.com 教大家使用命令行代码开启隐藏的任何来源选项。

## 开启任何来源（主要）

先打开 `系统偏好设置 -> 安全与隐私 -> 通用` 选项卡，检查是否已经启用了 `任何来源` 选项。

![img](https://cdn.macwk.com/public/uploads/_/originals/check-macos-gatekeeper-status-01.jpg)

![img](https://cdn.macwk.com/public/uploads/_/originals/check-macos-gatekeeper-status-02.jpg)

如果没有这个选项，复制以下面的命令：

```bash
sudo spctl --master-disable
```

打开`终端`：

将刚刚复制的命令粘贴到终端中。

![img](https://cdn.macwk.com/public/uploads/_/originals/disabled-macos-gatekeeper-step-02.jpg)

然后按下键盘的回车键（return）

![img](https://cdn.macwk.com/public/uploads/_/originals/disabled-macos-gatekeeper-step-03.jpg)

输入密码

![img](https://cdn.macwk.com/public/uploads/_/originals/disabled-macos-gatekeeper-step-04.jpg)

恭喜您，`您已成功开启任何来源`。