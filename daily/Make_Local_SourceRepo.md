### 一、下载Centos Everything ISO

```
wget http://archive.kernel.org/centos-vault/7.5.1804/isos/x86_64/CentOS-7-x86_64-Everything-1804.iso
```

### 二、挂载

```
mount -o loop ./CentOS-7-x86_64-DVD-1804.iso /media/cdrom
```

### 三、配置源

```
yum update
cd /etc/yum.repos.d/
rename .repo .repo.bak *
vi CentOS-Local.repo

CentOS-Local.repo 文件内容：
[base]
name=CentOS-Local
baseurl=file:///media/cdrom
gpgcheck=1
enabled=1   #很重要，1才启用
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
```

### 四、清除YUM缓冲

```
yum clean all
```
