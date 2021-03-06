### 测试目的
COS V4与COS V3进行文件上传、下载、删除三个维度进行对比测试，以下是详细报告。

### 测试数据准备
在测试前，先往bucket准备部分基础数据。

|产品	|文件数量 |	存储量 |	文件分布 |
|--------|--------|----------|--------|
|COS V3 |	78w|	38G|	50k小文件|
|COS V4  |	261w	| 183G	|99%的50k小文件，1%的2m与50m文件|

### 测试设备环境
**Client：**


>- 购买的华为云的一台虚拟机(122.112.229.25，上海地区，BGP网络)，
>CentOS 2核 2.50GHz 2G，带宽100M。
          
![配置](http://imgcache.tcecqpoc.fsphere.cn/image/mc.qcloudimg.com/static/img/69e33867c4dafc5c3236cb297f967531/image.png)


**Server： **


>- COS： 创建华东地区的bucket       


### 测试工具
client端均使用官网提供的python sdk。

### 场景与测试
先往bucket准备好基准数据，然后测试以下三种操作：上传，下载，删除。

**场景：**


>- cos v4的场景：另外开启了一个脚本，每隔2s对该bucket进行文件操作(上传，获取文件属性，更新文件属性，更新后再次获取文件属性)以及目录操作(创建目录，更新目录，获取目录属性，list目录，删除目录)。模拟现网有一定压力的情况下来进行以下测试。
>- cos v3的场景：均无对该bucket模拟压力。


**测试方法：**


>- 上传： 采用官网提供的python sdk进行文件上传操作，上传前记录一个时间，上传完成后记录一个时间，两者相减，得出耗时。上传的文件均为生成一个指定大小的随机字符串，以避免命中妙传。
>- 下载：每隔60s下载100K的文件，记录下载耗时 。
>- 删除：上传完成后执行删除，记录删除耗时。

**统计时间：**

>2016.12.24 00:00:00  — —2016.12.27 22:00:00

以上统计均控制好频率以及负载，避免client端本身高负载或网卡打满出现瓶颈。

### 测试图表与总结

- **文件上传测试(50K/2M/50M)：**

![50K](http://imgcache.tcecqpoc.fsphere.cn/image/mc.qcloudimg.com/static/img/141dd2f376c7a9b37e7d04ae72c0764d/50K3.png)

![2M](http://imgcache.tcecqpoc.fsphere.cn/image/mc.qcloudimg.com/static/img/e63d09e94f8f20c23c717c429c7a2905/2M2.png)


![50M](http://imgcache.tcecqpoc.fsphere.cn/image/mc.qcloudimg.com/static/img/46dda2f037ad2ca321823189694ba6ad/50M2.png)


**总结：文件删除功能，2M文件上传，COS V3耗时最小，优于COS V4 。但在50K以及50M文件上传的情况下，COS V4耗时最小。**


- **文件删除测试(50K/2M/50M)：**

50K/2M/50M 文件删除(文件上传成功后，执行删除，记录耗时)


![文件删除平均耗时](http://imgcache.tcecqpoc.fsphere.cn/image/mc.qcloudimg.com/static/img/84e1f9f536925c8ba3575de5afdde3d6/image.png)

|产品   |50k文件删除平均耗时(ms)|	2M文件删除平均耗时(ms)|50M文件删除平均耗时(ms)|
|--------|--------|--------|--------|
|COS V3	 | 189.81|	201.22|	726.28|
|COS V4	 | 184.19|	181.04	|198.99|


**总结：COS V3删除耗时随着文件大小增大而增大，COS V4删除文件跟大小不呈线性相关。**




- **文件下载测试(100k)：**

100k的文件下载72小时，每隔60s进行下载，记录下载耗时


![图片描述](http://imgcache.tcecqpoc.fsphere.cn/image/mc.qcloudimg.com/static/img/8d89db4ece7cffa638403e0c07d62035/100K.png)


|产品	|100k文件下载平均耗时(ms)	|样本数|
|---------|-------|-------|-------|
|COS V3	  |269.95	|5459|
|COS V4	  |149.5|	5346|


**总结：100K文件下载耗时方面，COS V4平均耗时低，优于COS V3。**



