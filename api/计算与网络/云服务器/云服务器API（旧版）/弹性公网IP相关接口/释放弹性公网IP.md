## 1. 接口描述
 
域名: eip.api.qcloud.com
接口名: DeleteEip

释放弹性公网IP。

 

## 2. 输入参数
 

<table class="t"><tbody><tr>
<th><b>参数名称</b></th>
<th><b>必选</b></th>
<th><b>类型</b></th>
<th><b>描述</b></th>
<tr>
<td> eipIds.n  <td> 是 <td> String <td> EIP实例ID列表，列表下标从0开始，可通过<a href="/doc/api/229/%E6%9F%A5%E8%AF%A2%E5%BC%B9%E6%80%A7%E5%85%AC%E7%BD%91IP%E5%88%97%E8%A1%A8" title="DescribeEip">DescribeEip</a>接口返回字段中的eipId获取
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
  &eipIds.0=eip-gzc5rgr2

</pre>

输出
```

{
    "code": 0,
    "message": ""
}

```

