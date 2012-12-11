## boost

**Boost your productivity!**

阿里系的同学们，你是不是经常做以下的事情:

* 你的一个小本子里面里面记了各种命令，要用的时候copy/paste过来运行一下。比如你要编译一个应用，你会拷贝如下的命令过来执行:

``` bash
mvn clean install -DuserProp=/path/to/your/antx.properties
```

* 记性好、打字又快的同学不会每次copy/paste这些命令，他们觉得这不黑客，他们直接飞快地敲出来，恩，很有黑客的格调。
* 当开始一个新的项目、需求的时候，需要`antx`配置文件，你就从一个老项目里面拷贝一个`antx.properties`过来改改再用。

其实这些都是可以自动化的，这就是这个小项目的目的，它可以简化以下事情:
* checkout项目代码
* 生成antx配置文件
* 生成eclipse项目文件
* 编译项目代码
* 运行项目
* 停止应用
* 查看应用的日志

总之，使用了这个工具之后，所有的这些事情都只是一个简单的命令就可以搞定了。


## 安装

* 下载代码

``` bash
git clone https://github.com/xumingming/boost.git
```

* 设置一下`BOOST_HOME`:

``` bash
export BOOST_HOME=/path/to/your/boost
```

* 把boost目录添加到你的`PATH`环境变量里面去:

``` bash
export PATH=$PATH:$BOOST_HOME
```

* 设置脚本权限

``` bash
chmod a+x $BOOST_HOME/boost
```

## 用法

* 当你在Aone上创建了一个新的需求之后，你在本地文件系统上为这个项目创建一个目录, 我一般都习惯放在`~/local/svn/<project_home>`

``` bash
mkdir ~/local/svn/<project_name>
```

* 初始化你的项目目录，只需要提供你的Aone CRID就可以了

``` bash
boost init <CRID>
```

* 假设这个项目需要修改到luna，你已经在Aone上创建了luna分支，执行下面这个命令自动拉分支

``` bash
boost co luna
```

* 有的应用的代码之后，我们一般需要编译应用，不过阿里系的代码编译都需要Antx配置文件，我们先生成Antx配置文件

``` bash
cd luna_1      # 进入luna代码目录
boost antx     # 自动生成在项目根目录生成antx_luna.properties配置文件
```

* 有了antx配置文件，我们可以编译代码了

``` bash
boost mvn
```

* 编译之后我们就可以运行应用了

``` bash
boost run
```

* 有时候我们可能希望编译运行一步搞定:

``` bash
boost mvnrun
```

* 停止当前目录所代表的应用

``` bash
boost stop
```

## License

Copyright (C) 2012 xumingming

Distributed under the Eclipse Public License.
