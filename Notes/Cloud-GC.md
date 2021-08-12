# GEOSChem-on-cloud

`GEOSChem-on-cloud` 将 `GEOS-Chem` 搬运至 `AWS Cloud`，该项目省去了编译模型、准备输入数据、配置 Linux 服务器等环节，使模型变得简单易用。

## 快速入门

1. 前往[亚马逊云官网](https://aws.amazon.com/cn/)注册账号，需要提供信用卡等相关信息；
2. 在页面右上角地区改为 `弗吉尼亚北部`；

![ChangeRegion](https://github.com/RampageLi/GEOS-Chem/blob/master/Pics/ChangeRegion.png?raw=true)

3. 启动 `EC2` 虚拟机；

![BootVirtualMachine](https://github.com/RampageLi/GEOS-Chem/blob/master/Pics/BootVirtualMachine.png?raw=true)

4. 在控制台的搜索框输入 `GEOSChem_13.1.2_tutorial_20210706`，选择预装了 `GEOS-Chem` 的系统；

![SearchAMI](https://github.com/RampageLi/GEOS-Chem/blob/master/Pics/SearchAMI.png?raw=true)

5. 配置 CPU 类型；
6. 第一次启动需要配置密钥，设置密钥名称后，将密钥下载下来；
7. 点击控制台左侧的 `实例`，选中刚刚创建的实例并点击连接；
8. 安装 [Git bash](https://git-scm.com/downloads)；
9. 桌面右击，进入 `git bash`，输入以下命令：

```
ssh-keygen -t rsa
```

10. 将刚刚下载的 `*.pem` 文件移动至 `~/.ssh`  下；
11. 在 `git bash` 输入如下命令：

```
cd ~/.ssh
chmod 400 $刚刚设置的密钥名称$.pem
```

12. 在 ~/.ssh 目录下创建 `config` 文件，方便快捷的启动虚拟机，配置内容如下：

```
Host geos-chem
  HostName $你的机器地址，配置完实例后，选择 SSH 连接将会看到$.compute-1.amazonaws.com
  User ubuntu
  IdentityFile ~/.ssh/cma-key.pem
```

13. 输入如下命令，登入虚拟机：

```
chmod 600 config // 只需要第一次配置的时候输入
ssh geos-chem // 登录命令
```

14. 运行 `GEOS-Chem` 实例：

```
cd ~/tutorial/gc_merra2_fullchem
./gcclassic
```

15. 运行完毕需要关闭实例，否则产生高昂费用！





