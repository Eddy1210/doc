### 一、下载python3包

```
cd ~
wget https://www.python.org/ftp/python/3.7.1/Python-3.7.1.tgz
```

### 二、安装依赖

```
tar xvf Python-3.7.1.tgz

python3.7的安装之前需要先准备好依赖包，如果是最小安装的Linux最好先安装DevelopmentTools
yum groupinstall 'Development Tools' -y

安装依赖包：
yum install openssl-devel bzip2-devel expat-devel gdbm-devel sqlite-devel libffi-devel readline-devel.x86_64
```

### 三、编译安装

```
cd Python-3.7.1
./configure --prefix=/usr/local/python3.7 --enable-shared CFLAGS=-fPIC
make && make install
```

### 四、检查安装

> ldd /usr/local/python3.7/bin/python3

```
## 可能缺少python3运行所需要的库libpython3.7m.so.1.0

解决：
1. 查找一下文件的位置：
find / -name 'libpython3.7m.so.1.0'

/usr/local/python3.7/lib/libpython3.7m.so.1.0

2. 在目录 /etc/ld.so.conf.d 下,建立python3.conf
cat python3.conf
/usr/local/python3.7/lib/

3. 运行: ldconfig
4. /usr/local/python3.7/bin/python3

```

### 五、创建软链

```
ln -s /usr/local/python3.7/bin/python3 /usr/bin/python3
ln -s /usr/local/python3.7/bin/pip3 /usr/bin/pip3
```

### 六、升级pip
```
pip3 install -U pip
```

[附 Centos7 升级安装 Python2.7.15](https://woj.app/3999.html)
