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
export PATH=$PATH:/usr/local/python3/bin/
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
