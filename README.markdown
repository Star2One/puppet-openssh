#openssh



##简介
管理OpenSSH的puppet模块

##安装

###安装介绍
* 安装openssh-server和openssh-client
* 管理sshd_config配置文件

###安装依赖

无

###快速开始

通过调用openssh类即可生效。
`include 'openssh'`

##使用

所有配置内容都通过openssh类调用实现。  

##参数

###调用方法
* 通过hiera方式调用`openssh::VAR_NAME`
* 通过类调用

###参数说明

* `port` - 监听端口，默认为 22
* `permit_root_login` - 是否允许root用户登录，默认为'no'
* `log_level` - Log信息级别, 默认为 'INFO'
* `x11_forwarding` - 打开X11 forwarding, 默认为'no'
* `max_auth_tries` - 验证失败后的尝试次数，默认为4
* `password_authentication` - 允许通过密码登录。 默认为 'yes'
* `ciphers` - 默认支持的ssh ciphers列表, defaults to counter based ciphers
* `client_alive_interval` - 默认多久时间无操作，自动断开连接。默认为300s
* `client_alive_count_max` - 如果发现客户端没有相应，则判断一次超时，这个参数设置允许超时的次数.
* `allow_users` - 允许远程登录的用户列表。默认为UNSET 
* `deny_users` - 禁止登录的用户列表。默认为UNSET
* `banner` - 显示登录警告信息。默认为`/etc/issue.net`. 可以设置为'UNSET'取消该项配置
* `sftp_chroot` - 启用sftp chroot配置。默认为false.
* `config_template` - 指定配置文件模板 `sshd_config`. 
* `service_name` - 服务名称.
* `service_ensure` - 保持服务运行的状态，默认为running
* `service_enable` - 是否开机启动该服务。默认为true
* `package_name` - 软件包的名称。
* `package_ensure` - openssh软件包的状态，默认为present
* `kerberos_enable` - 是否启用kerberos配置，默认为启用

##限制

测试通过：`Ubuntu 12.04` and `CentOS 5` and `CentOS 6`   


##Fork
翻译测试：www.weittor.com    
原作者：pennycoders
