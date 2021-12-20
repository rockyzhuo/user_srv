## proto子模块使用说明


第一次clone带子模块的项目
shell script
git clone --recurse-submodules http://10.1.1.243/s2b2c/proto.git

如果第一次没有clone子模块，下载完成后，但是子模块并没有下载下来，使用下面的命令
shell script
git submodule update --init --recursive

过了一段时间，子模块更新了，需要重新更新子模块，一个命令解决
shell script
git submodule foreach git pull origin master

子模块更新
shell script
git submodule update --remote

更新所有子模块
shell script
git submodule foreach git submodule update

如果已经克隆了项目并忘记了 ，则可以通过运行 来组合 和 步骤。为了还可以初始化、提取和签出任何嵌套子模块，可以使用万无一失的子模块。
shell script
--recurse-submodules git submodule init git submodule updategit submodule update --initgit submodule update --init --recursive

为没有子模块的项目，添加子模块
shell script
git submodule add http://10.1.1.243/s2b2c/proto.git

如果项目报错，提示 'proto' already exists in the index，说明proto属于该项目的子目录，需要移除
shell script
git rm -r --cached proto

移除后，再手动将proto改个别名，然后再重新添加子模块的引用

常用命令

```shell script
git submodule init
git submodule update
git submodule update --remote
git submodule update --init --recursive