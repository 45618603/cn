## 可用性监控限制与配额
本章主要描述对站点监控任务管理,包括创建,修改等的限制,以及可用性监控相关的配额限制。

### 可用性监控限制
 限制项 | 限制说明 
 -- | --
 可用性监控任务名称 | 长度为1-32个字符，只允许中文、数字、大小写字母、英文下划线“_”及中划线“-”
 探测目标 | 目前支持URL/IP，云数据库RDS
 探测方式 | 目前支持HTTP(s）,TELNET
 HTTP请求头 | 支持最多20对key和value值，总长度不能超过1KB.
 Cookie | 支持最多20对key和value值，总长度不能超过1KB
 POST内容 | 提交内容建议使用英文，总长度不能超过1KB.
 RDS探测 | 当对RDS进行探测时，所选探测源应与RDS在相同子网内。

### 可用性监控配额
 配额项 | 配额数量 
  -- | --
 站点监控任务数 | 最多可创建20个可用性监控任务
 探测源数量 | 最多支持选择50台Linux系统的云主机作为探测源
