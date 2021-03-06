## 1. 接口描述

本接口(ModifyVpnGw)用于修改VPN网关属性。
接口请求域名：<font style="color:red">vpc.api.qcloud.com</font> 

 

## 2. 输入参数
 
以下请求参数列表仅列出了接口请求参数，正式调用时需要加上公共请求参数，见<a href="/doc/api/372/4153" title="公共请求参数">公共请求参数</a>页面。其中，此接口的Action字段为ModifyVpnGw。

| 参数名称 | 是否必选  | 类型 | 描述 |
|---------|---------|---------|---------|
| vpcId | 是 | String | 私有网络ID值，可使用vpcId或unVpcId，建议使用unVpcId，例如：vpc-amhnnao5。可通过<a href="/document/api/215/1372" title="DescribeVpcEx">DescribeVpcEx</a>接口查询。 |
| vpnGwId | 是 | String | 要修改的VPN网关ID值，可使用vpnGwId或unVpnGwId，建议unVpnGwId，例如：vpngw-dystbrkv。可通过<a href="/document/api/215/5108" title="DescribeVpnGw">DescribeVpnGw</a>接口查询。 |
| vpnGwName | 否 | String | 修改后网关名称，可任意命名，但不得超过60个字符。 |



## 3. 输出参数
 
| 参数名称 | 类型 | 描述|
|---------|---------|---------|
| code| Int | 错误码，0: 成功，其他值: 失败。 |
| message | String | 错误信息。 |

## 4. 错误码表
 以下错误码表仅列出了该接口的业务逻辑错误码，更多公共错误码详见<a href="/doc/api/245/4924" title="VPC错误码">VPC错误码</a>。

| 错误码 | 描述 |
|---------|---------|
| InvalidVpc.NotFound | 无效的VPC。VPC资源不存在，请再次核实您输入的资源信息是否正确，可通过<a href="/document/api/215/1372" title="DescribeVpcEx">DescribeVpcEx</a>接口查询VPC。 |
| InvalidVpnGw.NotFound | 无效的vpn网关。vpn网关资源不存在，请再次核实您输入的资源信息是否正确，可通过<a href="/document/api/215/5108" title="DescribeVpnGw">DescribeVpnGw</a>接口查询vpn网关。 |
| InvalidVpnGwState | vpn网关状态不对 |
| InvalidVpnGwName |vpn网关名称不合法。可任意命名，但不得超过60个字符。。 |

## 5. 示例
 
输入
<pre>
  http://vpc.api.qcloud.com/v2/index.php?Action=ModifyVpnGw
  &<<a href="/doc/api/229/6976">公共请求参数</a>>
  &vpcId=vpc-amhnnao5
  &vpnGwId=vpngw-dystbrkv
  &vpnGwName=test-9910
  &isAutoRenewals=0

</pre>

输出
```

{
    "code": 0,
    "message": ""
}

```

