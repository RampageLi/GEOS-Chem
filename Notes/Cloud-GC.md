# GEOSChem-on-cloud

`GEOSChem-on-cloud` 将 `GEOS-Chem` 搬运至 `AWS Cloud`，该项目省去了编译模型、准备输入数据、配置 Linux 服务器等环节，使模型变得简单易用。

## 快速入门

1. 前往[亚马逊云官网](https://aws.amazon.com/cn/)注册账号，需要提供信用卡等相关信息；
2. 在页面右上角地区改为 `弗吉尼亚北部`；

![ChangeRegion](https://github.com/RampageLi/GEOS-Chem/blob/master/Pics/ChangeRegion.png?raw=true)

3. 启动 `EC2` 虚拟机；

![BootVirtualMachine](https://github.com/RampageLi/GEOS-Chem/tree/master/Pics/BootVirtualMachine.png)

4. 在控制台的搜索框输入 `GEOSChem_13.1.2_tutorial_20210706`，选择预装了 `GEOS-Chem` 的系统；

![SearchAMI](https://github.com/RampageLi/GEOS-Chem/tree/master/Pics/SearchAMI.png)



