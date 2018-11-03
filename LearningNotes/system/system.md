# 系统配置

## 系统文件夹

- Macintosh HD (/)
    - Applications: 存放软件
    - Library ：系统资源库
        - Application Support ：应用相关的数据以及支持文件，插件、帮助、模板等
        - Documentation ：包含了供计算机用户和管理员参考的文档文件和 Apple 帮助包。
        - Fonts ：包含了用于显示和打印的字体文件。
        - StartupItems ：包含了在系统导入时刻运行的系统以及第三方脚本和程序。
        - 太多，只介绍其中一部分

    - System ：包含由Apple安装的系统软件。这此资源是系统正常运行所必须的，位于启动卷宗中
        - Library 
            - Extensions ：存放硬件驱动的地方,苹果不称驱动程序为driver, 而是称为Extension.
            - OpenSSL ：Secure Sockets Layer.
            - CoreServices
                - DOCK
                - Finder.app
                - Software Update
            - 太多，只介绍其中一部分 
    - Users ：包含了某个用户专有的资源。 (~)
        - Applications ：包含仅仅当前用户可用的应用。
        - Desktop ：包含了 Finder 在当前登录用户桌面上显示的桌面项。
        - Documents ：包含了用户的个人文档。
        - Download ：包含了下载的各种文档。
        - Library ：包含了应用设置、偏好设置等专有的系统资源
        - Documentation ：包含了供计算机用户和管理员参考的文档文件和 Apple 帮助包。
        - Extensions ：包含了设备驱动和其它内核扩展。(只存在于系统域当中。)
    - 以下为隐藏文件夹
    - bin ：Essential user command binaries (for use by all users)
        - bash
        - cat
        - cp
        - echo
        - ...
    - sbin ：System binaries
        - md5
        - ping
        - reboot
        - shutdown
    - etc ：系统设定档桉储存地方
    - var ：改动频繁的档桉, 都置放于此, 例如各log档桉
    - tmp ：系统的暂存档
    - opt ：Add-on application software packages，可选的
    - usr ：UNIX的使用者专用档桉夹
        - bin ：Most user commands
            - sed
            - grep
            - git
            - python
            - ...
        - sbin ：Non-essential standard system binaries
            - sysctl
            - traceroute
            - ...
        - local ：use by the system administrator when installing software locally. 
            - bin ：用户自己安装的命令
                - ack
                - brew
                - 
            - sbin ：本地系统命令，感觉这个文件夹有悖论，自己电脑上并没有



## 参考资料：
[Filesystem Hierarchy Standard](http://www.linuxbase.org/betaspecs/fhs/fhs/index.html)
