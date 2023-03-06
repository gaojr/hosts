# hosts

hosts 相关

## 介绍

hosts 文件属于系统核心文件之一。

- Windows 用户必须用管理员身份打开才能修改保存。如果遇到无法保存，请右键 hosts 文件 -> “属性” -> “安全”，然后选择登陆的用户名，点击编辑，勾选“写入”即可。

- Android（安卓）必须 Root 才能修改。Root Explorer 管理器或 ES 文件浏览器装载 /system 可写状态。

- Linux 需要使用 Root 权限。

- iPhone、iPad 必须越狱才能修改。

*Windows 系统跟苹果系统的 hosts 文件文本编码和换行符格式一样，而 Android（安卓）则不一样，需要注意。*

## 文件位置

**Windows*- `C:\Windows\System32\drivers\etc\hosts`

**Android（安卓）*- `/system/etc/hosts`

**Linux*- `/etc/hosts`

**Mac（苹果电脑）*- `/etc/hosts`

**iPhone（iOS）*- `/etc/hosts`

## 修改方式

可用文本编辑器进行修改保存。

## 修改hosts后生效的方法

- Windows

    cmd.exe 输入：

    ```
    ipconfig /flushdns
    ```

- Linux

    终端输入：

    ```
    sudo rcnscd restart
    ```

    对于 systemd 发行版，终端输入：

    ```
    sudo systemctl restart NetworkManager
    ```

    *若不懂请都尝试下*

- Mac OS X

    终端输入：

    ```
    sudo killall -HUP mDNSResponder
    ```

- Android

    开启飞行模式 -> 关闭飞行模式

- Chrome

    访问`chrome://net-internals/#dns`，然后点击`Clear host cache`按钮来清空浏览器里的 DNS 缓存

### 通用办法

方法一：
> 拔网线（断网） -> 插网线（重新连接网络）。

方法二：
> 重启系统。

方法三：
> 清空浏览器缓存（不要使用国产浏览器）。
