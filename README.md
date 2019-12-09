# django_websocket
### 工作上需要制作一个实时大屏，需要使用websocket实时传递信息。但是之前对websockety一直不熟悉。

主要使用的是channels，[参考官方教程写的代码](https://channels.readthedocs.io/)。教程已经写的很全了。解释很好.

所以需要新建python环境，新建git，安装包等等。

### 更换源
由于使用官方源下载channels很慢，所以需要指定pip的源:
> 打开新建的文件夹，在里面建一个名为： pip.ini的文件，并在文件中输入如下信息保存：

```
[global]

timeout = 6000

index-url = http://pypi.douban.com/simple

trusted-host = pypi.douban.com
```

- 科技大学的：https://mirrors.ustc.edu.cn/pypi/web/simple/
- https://pypi.tuna.tsinghua.edu.cn/simple

### 需要用到redis, chromedriver, selenium
>   获取密码
        `config get requirepass`
    设置密码
        `config set requirepass 123456`
    当有密码的时候登录时需要密码登录
        `auth 密码`
    取消密码
        `config set requirepass ''`
    
    查看chrome的版本直接看关于就好了。
    - http://npm.taobao.org/mirrors/chromedriver/  淘宝源 chromedriver  [selenium 配置 chromedriver]（https://www.cnblogs.com/wzjbg/p/11192082.html）

chromedriver是一个控制chrome浏览器的驱动，相当于是个接口。
selenium是python的一个模拟浏览器，可以实现对浏览器的模拟。


### 由于需要将公司电脑这边的git绑定到这边的github，因此需要添加验证
- 本地电脑配置好git
- 本地生成ssh公钥  >  ssh-keygen -t rsa -C "your email"
- 将ssh公钥上传到github的ssh key处
- 添加新的邮箱到github的认证邮箱中
- 创建.gitignore, 添加不跟踪的目录和文件
- git push 上传代码


### .idea文件的用途
在创建.gitignore的时候，发现了一个.idea文件，不知道有什么用途。经过查找，确定为：
> 当使用pycharm作为IDE时，会自动生成.idea/文件夹来存放项目的配置信息。其中包括版本控制信息、历史记录等等

### git查看配置的一些命令

- 查看系统config

`git config --system --list`

- 查看当前用户（global）配置

`git config --global  --list`

- 查看当前仓库配置信息

`git config --local  --list`

- 查看user.name

`git config user.name`

- 查看user.email

`git config user.email`

- 修改user.name

`git config --global --replace-all user.name "your user name"`
- 修改user.email

```git config --global --replace-all user.email"your user email"```
