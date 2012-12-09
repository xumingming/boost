## boost

Boost your productivity!

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

## 用法

* 当你在Aone上创建了一个新的需求之后，你在本地文件系统上为这个项目创建一个目录, 我一般都习惯放在`~/local/svn/<project_home>`

``` bash
mkdir ~/local/svn/<project_name>
```

* 初始化你的项目目录，只需要提供你的Aone CRID就可以了

``` bash
boost init <CRID>
```

* 假设这个项目需要修改到luna，你已经在Aone上创建了项目分支，执行下面这个命令自动拉分支

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

## TODO
* 添加 stop

## License

Copyright (C) 2012 xumingming

Distributed under the Eclipse Public License.
