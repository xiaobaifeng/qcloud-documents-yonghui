## 1.接口描述
本接口（QueryCfsFileSystem）用于查询文件系统。
接口请求域名：**cfs.api.qcloud.com**
## 2.输入参数
|       参数      |  必填 |  类型  |                               描述                           |
|-----------------|------|--------|--------------------------------------------------------------|
| CreationToken   |   否   | string | 用户自定义文件系统名称，如有该值则查询自定义名称为该值的文进系统										     |
| FileSystemId  |否 |string| 文件系统 ID   |                                   
| Region          |是   | string | 园区，请参考"概览"文档中的园区与可用区列表                   |
| UniqVpcId | 否 | string | 用户私有网络id，如指定该值，则查询在该私有网络下的文件系统 |
## 3.输出参数
| 参数名称 | 子参数 |  子参数 | 类型 | 描述 |
|----------|------  |-------- |----- | ---- |
|FileSystems|               |           |array |文件系统列表|
|           |CreationTime   |           |string |创建文件系统时间|
|           |CreationToken  |           |string |用户自定义名称|
|           |FileSystemId   |           |string |文件系统ID|
|           |LifeCycleState |           |string |文进系统状态|
|           |SizeInBytes    |           |array  ||
|           |               |Timestamp  |string |时间戳|
|           |               |value      |int    |已用磁盘大小|
|           |SizeLimit      |           |int    |文件系统最大空间限制|
|           |ZoneId         |           |int    |区域ID|
|           |ZoneName       |           |string |区域名称|
|UserStatus |               |           |int    |用户状态|
|StartTime  |               |           |string |查询时间|

## 4.示例 

### 输入


```
<pre>
  http://cfs.test.api.qcloud.com/v2/index.php?Action=QueryCfsFileSystem
  &Region=gz
  &Uin=277000000
  &AppId=1250000000
  &<<a href="http://www.tce.fsphere.cn/doc/api/229/6976"> 公共请求参数 </a>>
</pre>
```

### 输出

```
{
    "code": 0,
    "message": "",
    "codeDesc": "Success",
    "data": {
        "FileSystems": [
            {
                "CreationTime": "2017-08-03 16:07:09",
                "CreationToken": "hello-world",
                "FileSystemId": "cfs-8xbtlopj",
                "IpList": [
                    "1.2.3.4",
                    "2.3.4.5",
                    "192.168.0.1",
                    "10.54.72.196"
                ],
        "UserStatus": 0,
        "StartTime": "2017-10-16 16:50:12"
    }
}

```

