manjaro linux 个人配置
===

1.下载并安装 manjaro-i3
---

### 下载
```
https://www.manjaro.org/download/community/i3/
```

### 制作启动盘
刻录工具Rufus：
```
https://rufus.ie/
```
注意：下载版本3.1，dd模式刻录。（更高版本不能选择刻录模式）

或者使用
```
https://rufus.ie/
```

### 安装
选择系统语言为英文，因为选择中文后，家目录的文件夹是中文的。

2.安装必备软件
---

x window
- xorg-server
- xorg-xinit

window compositor
- compton

window manager
- i3-gaps

status bar
- polybar

wallpaper
- feh

---

terminal
- alacritty

shell
- zsh + oh-my-zsh

file manager in terminal
- ranger


3.配置
---

### 更新软件并配置国内软件源

#### 更改国内源
```bash
$ sudo pacman-mirrors -i -c China -m rank
```

#### 添加 Arch Linux 中文社区仓库：
在`/etc/pacman.conf`文件末尾添加两行：
```
[archlinuxcn]
SigLevel = Optional TrustedOnly
# 这里可以改为其他源
Server = https://mirrors.ustc.edu.cn/archlinuxcn/$arch
```

#### 强制刷新并更新所有软件
```bash
$ sudo pacman -Syyn
```

#### 更新完毕后重启
```bash
$ reboot
```

### 字体

#### 下载字体：
```bash
sudo pacman -S ttf-font-awesome wqy-bitmapfont wqy-microhei wqy-microhei wqy-zenhei nerd-fonts-complete
```

#### 更改字体配置
拷贝我git仓库的`fonts/`覆盖`/etc/fonts/`
```bash
$ cp -r manjaro/fonts/ /etc/
```

#### 重启以生效
```bash
$ reboot
```



# 其他
卸载conky
```bash
sudo pacman -Rns conky
```