# describeMetricData


## 描述
查看某资源单个监控项数据

## 请求方式
GET

## 请求地址
https://jdccs.jdcloud-api.com/v1/idcs/{idc}/metrics/{metric}/metricData

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**idc**|String|True| |IDC机房ID|
|**metric**|String|True| |监控项英文标识(id)|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**resourceId**|String|True| |资源ID|
|**startTime**|Integer|True| |查询时间范围的开始时间， UNIX时间戳，（最多支持最近90天数据查询）|
|**endTime**|Integer|True| |查询时间范围的结束时间， UNIX时间戳，（最多支持最近90天数据查询）|
|**timeInterval**|String|False| |时间间隔：分钟m、小时h、天d，如： 10分钟=10m、1小时=1h，3天=3d；默认5m，最小支持5m，最大90d<br>目前带宽上、下行流量查询，会根据时间范围是否超过2小时，设定时间间隔为1m或5m|
|**ip**|String|False| |交换机IP，指定ip时须同时指定port|
|**port**|String|False| |端口，指定port时须同时指定ip|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|Result| |
|**requestId**|String| |

### Result
|名称|类型|描述|
|---|---|---|
|**metricData**|MetricData| |
### MetricData
|名称|类型|描述|
|---|---|---|
|**data**|DataPoint[]| |
|**statistic**|Statistic| |
|**metric**|Metric| |
### Metric
|名称|类型|描述|
|---|---|---|
|**metric**|String|监控项英文标识|
|**metricName**|String|监控项名称|
### Statistic
|名称|类型|描述|
|---|---|---|
|**max**|Double|最大值|
|**min**|Double|最小值|
|**avg**|Double|平均值|
### DataPoint
|名称|类型|描述|
|---|---|---|
|**timestamp**|Integer|UNIX时间戳|
|**value**|Double|采样值|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
