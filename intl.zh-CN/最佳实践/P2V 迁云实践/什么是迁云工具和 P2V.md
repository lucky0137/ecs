# 什么是迁云工具和 P2V {#ServerMigrationCenter .concept}

阿里云自主研发的迁云工具平衡了 ECS 用户的线上线下服务器负载或者各种不同云平台之间的负载。以其轻巧便捷的特点，迁云工具支持在线迁移物理机服务器、虚拟机以及其他云平台云主机至 ECS 经典网络平台或专有网络平台，实现统一部署资源的目的。

迁云工具属于 P2V 或者 V2V 工具范畴。P2V（Physical to virtual）代表从物理 IDC 环境迁移到 ECS，V2V（Virtual to virtual）代表从虚拟机环境或者云平台主机迁移到 ECS。迁云工具能将计算机磁盘中的操作系统、应用程序以及应用数据等迁移到 ECS 或是虚拟磁盘分区中生成 ECS 镜像，您可以使用该镜像快速创建 ECS 实例，以实现 P2V 和 V2V。

## 适用的操作系统 {#section_x3j_v5z_jfb .section}

迁云工具适用于以下操作系统（32 位或 64 位均可）的物理机服务器、虚拟机和其他云平台云主机。

|Windows|Linux|
|:------|:----|
| -   Windows Server 2003
-   Windows Server 2008
-   Windows Server 2012
-   Windows Server 2016

 | -   CentOS 5/6/7
-   Ubuntu 10/12/14/16/17
-   Debian 7/8/9
-   Red Hat 5/6/7
-   SUSE 11.4/12.1/12.2
-   OpenSUSE 13.1
-   Gentoo 13.0

 |

如果您使用的操作系统没有包含在上述列表中，请认真阅读 [使用迁云工具迁移服务器至阿里云](intl.zh-CN/最佳实践/P2V 迁云实践/使用迁云工具迁移服务器至阿里云.md#) 并谨慎操作。

## 计费详情 {#section_bjj_v5z_jfb .section}

迁云工具是免费工具，不收取额外的费用。但是，在迁云过程中会涉及少量资源计费：

-   迁云时，系统默认在您的阿里云账号下创建一个默认名为 INSTANCE\_FOR\_GOTOALIYUN 的 ECS 实例做中转站。该中转实例付费类型为按量付费，您需要确保您的账号关联的信用卡信用额度充足。

    **说明：** 迁云失败后，该实例保留在 ECS 控制台，便于重新迁云。如果您不再需要该实例，请自行 [释放实例](../../../../intl.zh-CN/用户指南/实例/释放实例.md#) 以免造成不必要的扣费。


## 参考链接 {#section_htg_nvz_jfb .section}

-   迁云工具不仅能实现在线迁移物理机服务器、虚拟机以及其他云平台云主机，还可以为 ECS 用户提供缩容磁盘的功能。更多详情，请参阅 [磁盘缩容](intl.zh-CN/最佳实践/磁盘缩容.md#)。

-   目前，ECS 支持的 P2V 或 V2V 迁云的方式除迁云工具外，还可以 [导入镜像](../../../../intl.zh-CN/用户指南/镜像/导入镜像/导入镜像必读.md#)。

-   如果您有数据库迁云需求，请访问 [数据迁移](https://www.alibabacloud.com/help/doc-detail/26594.htm)。


## 更新历史 {#section_fjj_v5z_jfb .section}

下表为迁云工具的版本更新信息。

|更新时间|版本|描述|
|:---|:-|:-|
|2018/08/29|1.3.0| -   提速迁云进程并优化一些已知问题
-   增加 Windows 服务器修复环节，您无需手动运行文件权限重置工具

 |
|2018/07/04|1.2.9.5| -   支持迁移 Ubuntu 17 服务器
-   优化迁云服务端功能，修复和完善个别细微问题

 |
|2018/06/11|1.2.9| -   增加 Windows GUI 简易界面版本
-   修复 Windows 数据盘过滤文件默认不存在问题

 |
|2018/04/28|1.2.8| -   增加命令行参数选项，您可以在工具所在路径运行 `--help` 查看详情。
-   支持从专线 VPC 私有网络迁移上云，保障数据安全

 |
|2018/04/03|1.2.6| -   修复 Linux 服务器数据盘上级目录重复拷贝子目录数据的问题
-   增加文件传输参数选项

 |
|2018/03/07|1.2.3| -   修复 Linux 服务器界面服务启动异常问题
-   修复提示服务实例磁盘空间可能不足问题
-   支持 Ubuntu 10 系统

 |
|2018/02/08|1.2.1| -   优化文件传输信息的显示
-   支持临时关闭 Linux 服务器的 SELinux，无需重开机源服务器

 |
|2018/01/18|1.2.0| -   拓展资源支撑，支持迁移更多类型资源
-   提升创建镜像的效率和稳定性

 |
|2018/01/11|1.1.8| -   支持 SUSE 12 SP2 系统
-   优化连接速度
-   优化日志信息提示
-   修复 NetworkManager 网络问题

 |
|2017/12/21|1.1.7| -   支持 SUSE 12 SP1 系统
-   新增限制数据传输带宽的功能

 |
|2017/12/14|1.1.6| -   新增版本更新提示功能
-   修复数据传输 6144 错误
-   自动检查用户配置文件 user\_config.json 中请求参数的正确性

 |
|2017/12/08|1.1.5| -   修复 Linux 服务器数据盘路径问题
-   优化日志信息提示

 |
|2017/12/01|1.1.3|支持 Debian 系统|

