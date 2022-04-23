



# 外网IP


    
    
## 8.1 申请外网IP - AllocateEIP

申请外网IP

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **Name** | string | 资源名称 | **Yes** |
| **ChargeType** | string | 计费模式。枚举值：Dynamic，表示小时；Month，表示月；Year，表示年； | **Yes** |
| **Bandwidth** | int | 带宽，默认值1，默认范围1~100 | **Yes** |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |
| **MemberID** | int | 账户ID | No |
| **ProjectID** | string | 项目组ID | No |
| **ApplicationName** | string | 申请名称 | No |
| **ApplicationReason** | string | 申请理由 | No |
| **Remark** | string | 资源描述 | No |
| **Quantity** | int | 购买时长。默认值1。小时不生效，月范围【1，11】，年范围【1，5】。 | No |
| **OperatorName** | string | 线路 | No |
| **IP** | string | 指定IP | No |
| **IPID** | string | 可以删除 | No |
| **IPVersion** | string | 可以删除<br /><br />IP版本，默认值IPv4，支持值：IPv4\IPv6 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |
| **EIPID** | string | 申请的EIP的ID | **Yes** |





    
    
## 8.2 获取外网IP信息 - DescribeEIP

获取外网IP的信息

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |
| **ProjectID** | string | 项目组ID | No |
| **Keyword** | string | 关键字 | No |
| **Offset** | int | 列表起始位置偏移量，默认为0。 | No |
| **Limit** | int | 返回数据长度，默认为20，最大100。 | No |
| **EIPIDs** | array<string> | 【数组】外网的 ID。输入有效的 ID。调用方式举例：EIPIDs.0=“one-id”、EIPIDs.1=“two-id” | No |
| **IPVersion** | string | 版本，支持IPv4、IPv6 | No |
| **BindResourceID** | string | 绑定资源ID，查询该资源绑定的所有 EIP | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |
| **Infos** | array<[*EIPInfo*](#EIPInfo)> | 外网IP数组 | **Yes** |
| **Totalcount** | int | 返回现有外网IP总数 | No |



### 数据模型


    
#### EIPInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 | **Yes** |
| **RegionAlias** | string | 地域别名 | **Yes** |
| **EIPID** | string | ID | **Yes** |
| **Bandwidth** | int | 带宽大小 | **Yes** |
| **ChargeType** | string | 计费模式。枚举值：Dynamic，表示小时；Month，表示月；Year，表示年； | **Yes** |
| **Name** | string | 资源名称 | **Yes** |
| **Remark** | string | 资源描述 | **Yes** |
| **Status** | string | 状态。Allocating：申请中,Free：未绑定,Bounding：绑定中,Bound：已绑定,Unbounding：解绑中,Deleted：已删除,Releasing：销毁中,Released：已销毁,BandwidthChanging：带宽修改中 | **Yes** |
| **CreateTime** | int | 创建时间。时间戳 | **Yes** |
| **UpdateTime** | int |  | **Yes** |
| **ExpireTime** | int | 过期时间。时间戳 | **Yes** |
| **IP** | string | 外网IP | **Yes** |
| **OperatorName** | string | EIP的所属外网网段 | **Yes** |
| **OperatorAlias** | string | EIP的所属外网网段名称 | **Yes** |
| **IPVersion** | string | IP版本,支持值：IPv4\IPv6 | **Yes** |
| **BindResourceID** | string | 绑定资源ID | **Yes** |
| **BindResourceName** | string | 绑定资源名称 | **Yes** |
| **BindResourceType** | string | 绑定资源类型 | **Yes** |
| **BindResourceProjectID** | string | 绑定资源项目组ID | **Yes** |
| **ISDefaultGW** | int | 是否为默认出口，1代表该IP地址为默认出口 | **Yes** |
| **CanDefaultGW** | int | 所属网段是否为默认路由，1代表所属网段是默认路由；默认路由的网段IP可以设置为默认网络出口 | **Yes** |
| **CompanyID** | int | 公司ID | **Yes** |
| **Email** | string | 公司邮箱 | **Yes** |
| **ProjectID** | string | 项目组ID | **Yes** |
| **ProjectName** | string | 项目组名称 | **Yes** |
| **BindTime** | int | 绑定时间 | **Yes** |
| **IsElastic** | string |  | **Yes** |

    

    

    





    
    
## 8.3 获取外网IP价格 - GetEIPPrice

获取外网IP价格

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **ChargeType** | string | 计费模式。枚举值：Dynamic，表示小时；Month，表示月；Year，表示年； | **Yes** |
| **OpertatorName** | string | 线路。目前支持Bgp | **Yes** |
| **Bandwidth** | int | 带宽，默认值1，默认范围1~100 | **Yes** |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |
| **Quantity** | int | 购买时长。默认值1。小时不生效，月范围【1，11】，年范围【1，5】。 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |
| **Infos** | array<[*PriceInfo*](#PriceInfo)> | 返回的价格信息 | No |



### 数据模型


    

    

    
#### PriceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费模式。枚举值：Dynamic，表示小时；Month，表示月；Year，表示年； | No |
| **Price** | float64 | 价格 | No |

    





    
    
## 8.4 绑定外网IP - BindEIP

绑定外网 IP

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **ResourceType** | string | 资源类型。VM：虚拟机 | **Yes** |
| **ResourceID** | string | 资源ID | **Yes** |
| **EIPID** | string | 外网IP的ID | **Yes** |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |





    
    
## 8.5 解绑外网IP - UnBindEIP

解绑外网IP

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **ResourceType** | string | 资源类型。VM：虚拟机 | **Yes** |
| **ResourceID** | string | 资源ID | **Yes** |
| **EIPID** | string | 外网IP的ID | **Yes** |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |





    
    
## 8.6 调整外网IP带宽 - ModifyEIPBandwidth

调整外网IP带宽

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **EIPID** | string | 外网IP的ID | **Yes** |
| **Bandwidth** | int | 调整后的带宽 | **Yes** |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |
| **ApplicationName** | string | 申请名称 | No |
| **ApplicationReason** | string | 申请理由 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |





    
    
## 8.7 删除外网IP - ReleaseEIP

删除外网IP

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **EIPID** | string | 外网IP的ID | **Yes** |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |







