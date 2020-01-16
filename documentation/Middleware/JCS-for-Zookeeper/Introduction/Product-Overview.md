## 产品概述
Zookeeper是一项基于开源Zookeeper的分布式应用程序协调服务，完全兼容了开源产品的标准接口，旨在简化分布式系统构建的任务，给开发人员提供一套容易理解和开发的接口，可用于配置维护、分布式同步、分布式通知和协调服务、组服务等。</br>

## 产品功能

### 兼容开源
100%兼容开源Zookeeper。业务代码无需任何改造，即可无缝迁移上云。</br>
### 安全性
资源独享，安全可控。部署在逻辑隔离的用户VPC内，杜绝了外网直连风险，保障了用户资源的安全。</br>
### 完全托管
快速部署，易于管理。用户只需专注于业务开发，无需部署运维，分钟级即可成功创建出Zookeeper实例。</br>

## 应用场景

### 分布式协调
利用 ZooKeeper 实现HBase、Kafka 和 Hadoop 等服务的分布式配置管理、系统协调等。</br>

## 入门指南

### 创建实例

#### 前提条件
- 已注册京东云账号，并完成实名认证。如果还没有账号请 [注册](https://accounts.jdcloud.com/p/regPage?source=jdcloud&ReturnUrl=https%3a%2f%2fuc.jdcloud.com%2fpassport%2fcomplete%3freturnUrl%3dhttps%3a%2f%2fwww.jdcloud.com)或 [实名认证](https://uc.jdcloud.com/account/certify)。
- 如计费类型选择按配置计费，请确认您的账户余额（包括代金券）能满足您的使用。</br>

#### 操作步骤
1. 登录 [Zookeeper控制台](https://zk-console.jdcloud.com/list)。</br>
2. 在实例列表页面单击“创建”，进入“创建”页面，选择付费方式、地域、基本信息、规格、网络、高级配置等信息。</br>

* “地域”：目前工作区域只支持且默认选择“华北-北京”。</br>
* “可用区”：可用区是使用独立电源和网络资源的物理区域。通过内部网络互联，再以物理方式进行隔离，提高了应用程序的可用性。</br> 
* “名称”：必填项，自定义的实例名称，名称不可为空，只支持数字、大小写字母、英文下划线“_”及中划线“-”，以字母开头且不能超过32字符。</br>
* “引擎版本”：当前版本支持V3.4。</br>
* “节点规格”：可以根据具体业务情况选择不同云主机规格。</br>
* “存储规格”：可以根据具体业务情况选择不同存储规格。</br>
* “节点数量”：支持工单方式提升节点配额。</br> 
* “私有网络”： 京东公有云上自定义的逻辑隔离的网络空间，更多说明请参见[私有网络功能]( https://docs.jdcloud.com/cn/virtual-private-cloud/vpc-features)。</br>
* “子网”： 子网是所属VPC IP地址范围内的 IP 地址块，更多说明请参见[子网功能]( https://docs.jdcloud.com/cn/virtual-private-cloud/subnet-features)。</br>
3. 规格确认完成后，单击“立即购买”跳转至付费页面。</br>
4. 跳转支付确认页面成功付款后返回实例列表页面。您创建的实例将展现在实例列表中。且实例状态为“创建中”，耐心等待几分钟，创建成功后实例状态会变为“运行”。如果实例创建失败，请根据界面提示，重新创建实例。</br>

### 连接实例
Zookeeper支持通过京东云云主机或客户端方式连接实例。

#### 通过京东云云主机访问
1.	登录Zookeeper控制台，创建Zookeeper实例 。</br>
2.	登录[云主机控制台](https://cns-console.jdcloud.com/host/compute/list)，创建和消息队列 Kafka 版具有相同私有网络和子网的云主机，并[获取公网IP](https://docs.jdcloud.com/cn/virtual-machines/associate-elastic-ip)。</br>
3.	在本地通过SSH登录云主机，用curl命令访问。指令格式说明如下：</br>

```
ssh 用户名@公网IP
curl -XGET 内网域名/_cat
```

#### 通过客户端访问
Zookeeper完全兼容开源版本，支持所有原生API，详细使用方式请参考[官方指南](http://zookeeper.apache.org/)。
