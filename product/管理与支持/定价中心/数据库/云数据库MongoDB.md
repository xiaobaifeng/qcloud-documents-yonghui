## 云数据库 MongoDB 定价

云数据库 MongoDB 提供包年包月计费模式，费用由规格（内存和CPU）和容量两部分组成。

### 高IO版

|配置类型|实例规格(1主1从1仲裁)|包月优惠价/元|实例规格(1主2从)|包月优惠价/元|
|:--:|:--:|:--:|:--:|:--:|
|高IO版|1核2G|225|1核2G|325|
|高IO版|2核4G|450|2核4G|650|
|高IO版|2核6G|675|2核6G|975|
|高IO版|4核8G|900|4核8G|1300|
|高IO版|4核12G|1350|4核12G|1950|
|高IO版|6核16G|1800|6核16G|2600|
|高IO版|10核24G|2700|10核24G|3900|
|高IO版|12核32G|3600|12核32G|5200|
|高IO版|18核48G|5400|18核48G|7800|
|高IO版|24核64G|7200|24核64G|10400|

容量价格列表

|存储价格（单位:G）|每G包月售价（单位:元）|
|:--:|:--:|
|1主1从1仲裁|1.6|
|1主2从|2.4|

### 容量版

容量版正在测试阶段，敬请期待。

## 购买指导

云平台数据库MongoDB可通过 [官网直接购买](http://buy.tce.fsphere.cn/mongodb)
![购买页](http://imgcache.tcecqpoc.fsphere.cn/image/mccdn.qcloud.com/static/img/49cff441939104908bd65a7ef287d798/buymongo.png)

### 地域选择帮助

云平台数据库MongoDB目前仅提供2个可选地域：**华东区（上海） 、华南区（广州）**；
**说明：**
1.处在同一地域的云服务产品之间通过内网互通
2.处在不同地域的云服务产品之间内网不能互通
   1)云服务器不支持跨地域内网互访，不支持跨地域访问云数据库，云缓存
   2)负载均衡服务绑定服务器时，只能选择绑定本地域的云服务器
   3)云服务器只能通过公网跨地域访问 云服务器、对象存储服务、弹性web引擎服务 
3.购买云服务时建议选择最靠近您客户的地域，可降低访问时延、提高下载速度；

有关更多地域选择详情，请参见 [地域选择](/doc/product/439/6972)。

#### 计费流程

包年包月预付费计费详情，请参见 [预付费计费流程说明](/doc/product/285/预付费计费流程)
后付费用户计费详情，请参见 [统一计费流程说明](/doc/product/285/计费流程)

## 续费指导

###  控制台续费

云平台数据库 MongoDB 支持手动续费和自动续费两种方式。

* 续费(按照用户需求量自主续费)
 ![手动续费](http://imgcache.tcecqpoc.fsphere.cn/image/mccdn.qcloud.com/static/img/1c2062061dd7dc094a2c6254cb8b2d14/2.png)
	
* 设置自动续费(设置后到期自动续费)
![自动续费](http://imgcache.tcecqpoc.fsphere.cn/image/mccdn.qcloud.com/static/img/6e2ec83a69d347682b37c5f8298a3c9f/3.png)
