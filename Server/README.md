# 服务器搭建
服务器采用开源的[EMQ](http://www.emqtt.com)，官网文档比较详尽，请按说明安装和配置。

## 禁用匿名访问
修改文件`etc/emqx.conf`，设置
```
allow_anonymous = false
```

在终端执行下面代码，启用用户名密码认证插件，并添加登录用户
```
bin>emqx stop
bin>emqx_ctl plugins load emqx_auth_username
bin>emqx_ctl users add <username> <password>
bin>emqx start
```
另外，可以通过`emqx_ctl users list`列出所有用户。
