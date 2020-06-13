# bilibili-live-tools

## 所有详情请移步[Wiki](https://github.com/Dawnnnnnn/bilibili-live-tools/wiki)

## 记录一次在腾讯云安装这个东西的过程

1. 安装python3环境

我的机子是默认自带python2.7，由于此项目必须3.6+，所以就先安装下3.8版本的， 我安装的方式是下载源码本地编译



首先，下载源码包，速度慢可以开代理，或者找个镜像
```shell
mkdir python-install
cd python-install
wget https://www.python.org/ftp/python/3.8.0/Python-3.8.0.tgz
tar zxf Python-3.8.0.tgz
cd Python-3.8.0
```

然后，做下编译前准备
```shell
yum update -y
yum groupinstall -y 'Development Tools'
yum install -y gcc openssl-devel bzip2-devel libffi-devel
```

最后就是编译安装设置环境变量
```shell
./configure prefix=/usr/local/python3
make && make install
export PATH=$PATH:/usr/local/python3/bin/  (重启后环境变量失效的写法，要一直生效需要写到那个b开头的文件里好像，今天太晚了，不想改了，下次再说)
```

2. 安装pip3

我的反正没有自带安装pip3，所以我要自己安装下
```shell
# 下载源代码
$ wget --no-check-certificate https://github.com/pypa/pip/archive/

$ tar -zvxf 9.0.1.tar.gz    # 解压文件

$ cd pip-9.0.1

# 使用 Python 3 安装
$ python3 setup.py install
```

3. 运行bilibili-live-tools

按照wiki里写的做就好，只不过记得使用python3

## 日常维护操作

1. 后台运行
```shell
nohup python3 -u run.py > out.log 2>&1 &
```

2. 追踪日志

nohup产生的日志在out.log里，可以vi或者tail -f查看

3. 多线程启动（未使用过）

4. 查看进程启动路径，
```shell
ll /proc/pid
```
在列出来的列表里找到`cwd`，cwd箭头显示的就是启动路径

## 风控记录

1. 6个辣条机运作，在大乱斗第一天晚上7点多后 被风控
