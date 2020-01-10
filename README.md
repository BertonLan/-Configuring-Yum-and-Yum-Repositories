# CentOS7更换yum官方源
## 下载wget工具
```
# yum -y install wget
```
## 进入yum源配置文件所在文件夹
```
# cd /etc/yum.repo.d
```
## 备份官方yum源
```
# mv CentOS-Base.repo CentOS-Base.repo_bak
```
## 下载国内yum源【aliyun\163】
```
# wget -O CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
# wget -O CentOS-Base.repo http://mirrors.163.com/.help/CentOS7-Base-163.repo
```
## 清理yum缓存
```
# yum clean all
```
## 重建缓存
```
# yum makecache
```
## 升级CentOS
```
# yum -y update
```

## 安装epel源【Extra Packages for Enterprise Linux】由Fedora社区打造,为RHEL及衍生发行版如:CentOS等提供高质量软件包的项目
```
# yum -y install epel-release
```
## 修改为阿里的epel源
```
# wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo
```
## 安装yum源优先级管理工具
```
# yum -y install yum-priorities
```
## 添加优先级【数字越小优先级越高】
```
# vim /etc/yum.repo.d/epel.repo
priority=88
```
## 添加优先级【此数值小于epel里的88即可】
```
# vim /etc/yum.repo.d/Centos-7.repo
priprity=5
```
## 开启yum源优先级功能
```
# vim /etc/yum/pluginconf.d/priorities.conf
[main]
enable=1
```
