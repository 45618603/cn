# describeBasicSubnet


## 描述
查询基础网络子网

## 请求方式
GET

## 请求地址
https://cps.jdcloud-api.com/v1/regions/{regionId}/subnet

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域ID，可调用接口（describeRegiones）获取云物理服务器支持的地域|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**az**|String|True| |可用区, 如cn-east-1a；可调用接口（describeRegiones）获取云物理服务器在该地域支持的可用区|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describebasicsubnet#result)| |
|**requestId**|String| |

### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**subnet**|[Subnet](describebasicsubnet#subnet)|子网详细信息|
### <div id="subnet">Subnet</div>
|名称|类型|描述|
|---|---|---|
|**region**|String|地域代码, 如cn-east-1|
|**az**|String|可用区, 如cn-east-1a|
|**subnetId**|String|子网ID|
|**name**|String|子网名称|
|**cidr**|String|子网CIDR|
|**vpcId**|String|私有网络Id|
|**vpcName**|String|私有网络名称|
|**availableIpCount**|Integer|可用ip数量|
|**totalIpCount**|Integer|总ip数量|
|**networkType**|String|网络类型|
|**description**|String|描述|
|**createTime**|String|创建时间|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Bad request|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|
