[toc]
## submodule的使用

参考：[Git 子模块submodule的使用](https://blog.csdn.net/h4x0r_007/article/details/108167592)

### 1. 首次拉取项目
```shell
git clone git@github.com:h4x0r139/git_collect_note.git
git submodule init
git submodule update
```
### 2. 增加新的submodule项目
```shell
git submodule add git@github.com:SubModule.git SubModule
```
### 3. submodule项目内部有更新，同步最新

```
git pull
git submodule foreach git submodule update
```

## 常见问题

### git 拉取`errno 54`问题

  [解决参考](https://blog.csdn.net/qq_42347755/article/details/90347988)：使用`ssh clone`
```
error: RPC failed; curl 56 LibreSSL SSL_read: SSL_ERROR_SYSCALL, errno 54
fatal: the remote end hung up unexpectedly
fatal: early EOF
fatal: index-pack failed
```
### git 拉取`errno 56`问题

  errno 56，有大文件或者提交缓存方面的问题：增大缓存配置，比如下面就是配置提交缓存为 500M。

```
git config http.postBuffer 524288000
git config https.postBuffer 524288000
```

### git 拉取`SSL_ERROR_SYSCALL`问题

```
fatal: unable to access 'https://github.com/h4x0r139/git_collect_note.git/': LibreSSL SSL_connect: SSL_ERROR_SYSCALL in connection to github.com:443 
```

解决办法，[参考](https://blog.hyperzsb.tech/git-ssl-error/)

```
git clone git@github.com:h4x0r139/git_collect_note.git
```

