## 1. 接口描述
 
域名: eip.api.qcloud.com
接口名: TransformMode

弹性公网IP模式切换。

 

## 2. 输入参数 

<table class="t"><tbody><tr>
<th><b>参数名称</b></th>
<th><b>必选</b></th>
<th><b>类型</b></th>
<th><b>描述</b></th>
<tr>
<td> eipId <td> 是 <td> String <td> EIP实例ID，可通过<a href="/doc/api/229/%E6%9F%A5%E8%AF%A2%E5%BC%B9%E6%80%A7%E5%85%AC%E7%BD%91IP%E5%88%97%E8%A1%A8" title="DescribeEipQuota">DescribeEip</a>接口返回字段中的 eipId获取
<tr>
<td> mode <td> 是 <td> Int <td> 要切换到的模式<br>0：NAT模式，1：直通模式。
</tbody></table>

 

## 3. 输出参数
 

| 参数名称 | 类型 | 描述 |
|---------|---------|---------|
| code | Int | 公共错误码。0表示成功，其他值表示失败。详见错误码页面的[公共错误码](/document/api/377/4173)。|
| message | String | 模块错误信息描述，与接口相关。详见错误码页面的[模块错误码](/doc/api/372/%E9%94%99%E8%AF%AF%E7%A0%81#2.E3.80.81.E6.A8.A1.E5.9D.97.E9.94.99.E8.AF.AF.E7.A0.81)。|


 

## 4. 示例
 
输入
<pre>

  http://eip.api.qcloud.com/v2/index.php?
  &<<a href="/doc/api/229/6976">公共请求参数</a>>
  &eipId=eip-mksy14ay
  &mode=0

</pre>

输出
```

{
    "code": 0,
    "message": ""
}

```

