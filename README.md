# Jenkins

<style>
  h1 {
    counter-reset: h2
  }
  h2 {
    counter-reset: h3
  }
  h2:before {
    counter-increment: h2;
    content: counter(h2) ". "
  }
  h3:before {
    counter-increment: h3;
    content: counter(h2) "." counter(h3) ". "
  }
</style>

[TOC]

</br>

## 安装Jenkins

### CentOS

```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo yum -y install jenkins
```

+ Jenkins文件列表

```bash
rpm -ql jenkins
```

+ 查看Jenkins端口

```bash
cat /etc/sysconfig/jenkins | grep JENKINS_PORT
cat /usr/lib/firewalld/services/jenkins.xml | grep port
cat /usr/lib/systemd/system/jenkins.service | grep JENKINS_PORT
```

+ 启动Jenkins服务

```bash
service jenkins start
```

## admin用户密码

```bash
cat /var/lib/jenkins/secrets/initialAdminPassword
```
