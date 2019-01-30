# 服务器搭建
服务器采用开源的[EMQ](http://www.emqtt.com)，官网文档比较详尽，请按说明安装和配置。

## 禁用匿名访问
修改文件`etc/emqx.conf`，设置
```
allow_anonymous = false
```
    
修改文件`data/loaded_plugins`，在文件末新起一行，写入需启用的模块（注意最后的.号，若已存在相同模块名则跳过本步骤）。
```
emqx_auth_username.
```

在终端执行下面代码，添加登录用户
```
bin>emqx stop
bin>emqx_ctl users add <username> <password>
bin>emqx start
```
另外，可以通过`emqx_ctl users list`列出所有用户。