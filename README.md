# cs.sh

只是一个shell脚本。

借用git仓库，随时随地存取代码片段文件或目录，方便在多个设备之间共享代码。

# 安装与设置

Fork 这个仓库，然后在命令行里运行(Windows环境请使用Git bash)：

```sh
$ curl -fsSLO https://git.oschina.net/home5u/cs.sh/raw/master/cs.sh
$ chmod +x cs.sh
```

编辑 `cs.sh` 这个文件，修改前几行的配置：

```sh
# 你刚刚fork的仓库的ssh地址
csgit="git@git.oschina.net:xxx/cs.sh.git"
# 网页查看代码的网址前缀
csprefix="https://git.oschina.net/xxx/cs.sh/blob/master"
# 仓库克隆到本地的路径，一般不用改
cspath=~/.cs.sh
```

# 使用

```sh
$ ./cs.sh {get|add|delete|view} {path}
```

 - `get` ，获取远程内容，如果`{path}`是一个文件，会将内容打印到标准输出，如果是目录，就cp到当前目录
 - `add` ，上传到仓库，如果有同名文件，会强制覆盖，`{path}`请使用相对路径，避免使用多级目录
 - `delete` ，删除内容
 - `view` ，在网页里查看

建议为脚本 `cs.sh` 添加一个别名，方便在任意位置使用：

```sh
$ alias cs='/path/to/cs.sh'
```

或者把 `cs.sh` 添加到PATH里。

# 其他
 - 有的gist网络有问题，有的gist没有api，所以写了这个脚本
 - cs=Code Snippets
