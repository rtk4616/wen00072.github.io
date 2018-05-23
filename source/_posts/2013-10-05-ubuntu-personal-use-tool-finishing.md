---
layout: post
title: '[Ubuntu 16.04] 安裝完系統後新增工具整理'
date: 2013-10-05 00:11
comments: true
categories: [Ubuntu, Linux Utilities]
---
安裝完作業系統後還需要裝一些平常使用的工具，順手整理一下

## 目錄

- [懶人包](#懶人包)
- [工具分類及簡單說明](#工具分類及簡單說明)
     - [系統程式開發套件](#系統程式開發套件)
     - [程式開發輔助工具](#程式開發輔助工具)
     - [一般工具](#一般工具)
     - [資安工具](#資安工具)

<a name="懶人包"></a>
## 懶人包
* 第一次更新
```
sudo apt update && sudo apt install aptitude && sudo aptitude upgrade -y --full-resolve
```

* 更新
```
sudo apt update && sudo aptitude upgrade -y --full-resolve && sudo apt autoremove
```

* 全部來
```
sudo apt install -y aptitude build-essential bison flex automake libtool intltool  libncurses5-dev git-svn tig meld cscope vim-gtk fonts-inconsolata geany joe doxygen-gui exuberant-ctags manpages-dev manpages-posix-dev minicom tree terminator ttf-mscorefonts-installer ack-grep pandoc gnome-system-tools ghex mc dict wireshark mtr pdfgrep sshfs fail2ban rkhunter bc libssl-dev cmake gdb libatk-adaptor libgail-common
```

* 從Server安裝後再裝Mate，安裝完記得關掉`/etc/network/interfaces`
```
sudo apt install -y lightdm mate-desktop-environment language-selector-gnome hime lightdm-gtk-greeter
```

* 從Server安裝後再裝LxQT，安裝完記得關掉`/etc/network/interfaces`
```
sudo apt install -y lightdm lxqt language-selector-gnome hime lightdm-gtk-greeter
```

* 安裝Hardware Enhance 相關套件
```
sudo apt install -y linux-image-generic-hwe-16.04 xserver-xorg-hwe-16.04 
```

* 單一選擇
```
sudo apt-get install build-essential
sudo apt-get install bison 
sudo apt-get install flex
sudo apt-get install automake
sudo apt-get install libtool
sudo apt-get install intltool
sudo apt-get install libncurses5-dev
sudo apt-get install bc
sudo apt-get install libssl-dev
sudo apt-get install gdb

sudo apt-get install git-svn
sudo apt-get install tig
sudo apt-get install meld
sudo apt-get install cscope
sudo apt-get install vim-gtk
sudo apt-get install fonts-inconsolata
sudo apt-get install geany
sudo apt-get install joe
sudo apt-get install doxygen-gui
sudo apt-get install exuberant-ctags
sudo apt-get install manpages-dev
sudo apt-get install manpages-posix-dev
sudo apt-get install minicom

sudo apt-get install tree
sudo apt-get install terminator
sudo apt-get install ttf-mscorefonts-installer 
sudo apt-get install ack-grep
sudo apt-get install pandoc
sudo apt-get install gnome-system-tools
sudo apt-get install ghex
sudo apt-get install mc
sudo apt-get install dict
sudo apt-get install wireshark
sudo apt-get install mtr
sudo apt-get install pdfgrep
sudo apt-get install sshfs
sduo apt-get install aptitude

sudo apt-get install fail2ban
sudo apt-get install rkhunter

sudo apt-get install libatk-adaptor
sudo apt-get install libgail-common
```


<a name="工具分類及簡單說明"></a>
## 工具分類及簡單說明
<a name="系統程式開發套件"></a>
### 系統程式開發套件 (不解釋)

- build-essential
- bison 
- flex
- automake
- libtools
- intltool
- libncurses5-dev
- libssl-dev
- bc
- cmake
- gdb

<a name="程式開發輔助工具"></a>

### 程式開發輔助工具

- git-svn
    - git, svn, git-svn三個願望一次滿足
- tig
    - 文字介面的git管理工具
- meld
    - GUI介面的檔案比較工具
- cscope
    - 追蹤程式碼工具，可以查詢函數被誰呼叫，宣告等功能。請配合vim服用
- exuberant-ctags
    - 追蹤程式碼工具，可以切入函數呼叫等功能。請配合vim服用
- vim-gtk
    - vim和gvim兩個願望一次滿足
- fonts-inconsolata
    - 給開發程式時的GUI編輯器使用，因為不希望因為粗體斜體等效果干擾字元對齊
- geany
    - 簡單好用的GUI編輯
- joe
    - 文字介面的WordStar式介面編輯器
- doxygen-gui
    - 文件產生器和他的Front UI
- ghex
    - GUI 16進位檔案檢視工具
- manpages-dev
    - 更多男人
- manpages-posix-dev
    - POSIX男人，查phread用
- minicom
    - Serial port終端機工具

<a name="一般工具"></a>
### 一般工具

- tree
    - 文字介面使用樹狀結構顯示檔案
- terminator
    - 增強版gnome-terminal，可以同一個畫面任意新增分割的終端
- ttf-mscorefonts-installer 
    - 主要是要Wingdings字型，有一堆有趣的向量ICON可以用
- ack-grep
    - 學長推荐的加強版grep，還不熟
- pandoc
    - 吃markdown語法產生其他文件如pdf
- gnome-system-tools
    - 需要GUI使用者管理所以安裝
- mc
    - 文字介面的norton commander介面式檔案管理工具，除了複製搬移外、還可以解壓縮檔案
- dict
    - 文字介面查英文單字用
- wireshark
    - 分析封包的工具
- mtr
    - 加強版的ping + tracert工具
- pdfgrep
    - grep pdf檔案的工具
- sshfs
    - 可以透過ssh mount遠端的帳號
- aptitude
    - 另外一種套件操作方式`aptitude upgrade --full-resolve -y`我常用
- `libatk-adaptor` `libgail-common`
    - 跑`gvim`不會出現下面錯誤訊息

```
Gtk-Message: Failed to load module "gail"
Gtk-Message: Failed to load module "atk-bridge"
```
  
<a name="資安工具"></a>
### 資安工具

- rkhunter
    - 掃rootkit 的工具
- fail2ban
    - 自動ban掉固定時間內重複嘗試連線ssh等的工具，[中文簡介](http://newtoypia.blogspot.tw/2016/04/fail2ban.html)
