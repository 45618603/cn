
# 简介 #

欢迎使用京东云开发者Node.js工具套件（Node.js SDK）。使用京东云Node.js SDK，您无需复杂编程就可以访问京东云提供的各种服务。

为了方便您理解SDK中的一些概念和参数的含义，使用SDK前建议您先查看[OpenAPI使用入门](../../API/Common-Declaration/Introduction.md )。要了解每个API的具体参数和含义，请参考程序注释或参考[OpenAPI&SDK](https://www.jdcloud.com/help/faq?act=3)下具体产品线的API文档。


# 环境准备 #

1.京东云Node.js SDK适用于Node.js 8.6.0及以上，npm 5.6.0及以上。

2.在开始调用京东云open API之前，需提前在京东云用户中心账户管理下的[AccessKey管理页面](https://uc.jdcloud.com/accesskey/index)申请accesskey和secretKey密钥对（简称AK/SK）。AK/SK信息请妥善保管，如果遗失可能会造成非法用户使用此信息操作您在云上的资源，给你造成数据和财产损失。


# SDK使用方法 #

建议使用npm安装京东云Node.js SDK，如下所示：
```
npm install jdcloud-sdk-js
```

您还可以下载sdk源代码自行使用，源代码地址为：[Node.js SDK](https://github.com/jdcloud-api/jdcloud-sdk-nodejs)。

SDK使用中的任何问题，欢迎您在[Github SDK使用问题反馈页面](https://github.com/jdcloud-api/jdcloud-sdk-nodejs/issues)交流。


**注意：**

- 京东云并没有提供其他下载方式，请务必使用上述官方下载方式！

- version 的版本号需要使用京东云产品提供的最新版本号。例如：示例中VM所使用的最新版本号可到官方提供的API  [更新历史](../../API/Virtual-Machines/ChangeLog.md)  中查询到。

- 每支云产品都有自己的Client，当调用该产品API时，需使用该产品的Client。例如：使用云主机的VmClient只能调用云主机（Vm）的接口；使用高可用组的AgClient只能调用高可用组（Ag）的接口。


 


 
# 调用SDK #


### 两种引用方式 ###

这种引用方式会加载所有的可用的services
```
var JDCloud = require('jdcloud-sdk-js');
```
这种引用方式只会加载用到的service，此时仍然可以使用 var JDCloud = require('jdcloud-sdk-js/global') 来引用JDCloud对象
```
var NC = require('jdcloud-sdk-js/services/nc');
```

### 配置方法  ###

对JDCloud的配置为通用配置，所有services共享配置:
```
JDCloud.config.update({//*配置项/*/});
```
对某个service的配置会覆盖通用配置：
```JavaScript
var NC = require('jdcloud-sdk-js/services/nc'); 
var nc = new NC({//*配置项/*/});
```

### 配置项 ###
```JavaScript
let config = { 
	credentials: { 
		accessKeyId: global.accessKeyId, secretAccessKey: global.secretAccessKey 
	},
	regionId: 'cn-north-1' //地域信息，某个api调用可以单独传参regionId，如果不传则会使用此配置中的regionId 
}
```

### 调用示例 ###

以下是查询单个云主机实例详情的调用示例


####  引用和配置  ####
```JavaScript
    var VM = require('jdcloud-sdk-js/services/vm')
    var vm = new VM({
            credentials: {
        accessKeyId: global.accessKeyId,
                secretAccessKey: global.secretAccessKey
    },
    regionId: 'cn-north-1'
    })
```


#### Promise方式调用 #### 
```JavaScript
	vm.createInstances({
        instanceSpec: {
            instanceType: 'g.s1.micro',
                    az: 'cn-north-1a',
                    imageId: '98d44a0f-88c1-451a-8971-f1f769073b6c',
                    name: 'node-sdk-test',
                    elasticIp: {
                bandwidthMbps: 2, provider: 'BGP'
            },
            primaryNetworkInterface: {
                networkInterface: {
                    subnetId: 'subnet-3dm13k30gh',
                            az: 'cn-north-1a'
                }
            },
            systemDisk: {
                diskCategory: 'local'
            },
            description: 'sdk'
        },
        maxCount: 1
    },'cn-north-1').then(function(data){ // 返回数据处理 data 
    },
    function(e){ // 调用API失败，错误处理 
    })
```


#### callback方式调用 #### 
```JavaScript
	vm.createInstances({
        instanceSpec: {
            instanceType: 'g.s1.micro',
                    az: 'cn-north-1a',
                    imageId: '98d44a0f-88c1-451a-8971-f1f769073b6c',
                    name: 'node-sdk-test',
                    elasticIp: {
                bandwidthMbps: 2,
                        provider: 'BGP'
            },
            primaryNetworkInterface: {
                networkInterface: {
                    subnetId: 'subnet-3dm13k30gh',
                            az: 'cn-north-1a'
                }
            },
            systemDisk: {
                diskCategory: 'local'
            },
            description: 'sdk'
        },
        maxCount: 1
    },'cn-north-1',
    function(err, data){
        if(err){ // 调用API失败，错误处理 
        } 
		else { // 返回数据处理 data 
        } 
    })
```
如果需要设置额外的header，例如要调用开启了MFA操作保护的接口，需要传递x-jdcloud-security-token，则按照如下方式：
```JavaScript
vm.deleteInstances({ 
	  instanceId: 'xxx', x-jdcloud-security-token: 'xxx' 
	}, 
	'cn-north-1'
)	
```


