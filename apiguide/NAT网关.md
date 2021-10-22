



# NAT网关


    
    
## 12.1 创建NAT网关 - CreateNATGW

创建NAT网关

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | No |
| **Name** | string | 资源名称 | No |
| **ChargeType** | string | 计费模式。枚举值：Dynamic，表示小时；Month，表示月；Year，表示年； | No |
| **Quantity** | int | 购买时长。默认值1。小时不生效，月范围【1，11】，年范围【1，5】。 | No |
| **VPCID** | string | NAT网关实例所在的 VPC ID | No |
| **SubnetID** | string | NAT网关实例所在的子网 ID | No |
| **SGID** | string | 安全组ID | No |
| **EIPID** | string | 弹性IP的ID | No |
| **VMType** | string | 虚拟机所在宿主机的集群类型，代表不同架构、不同型号的 CPU 或硬件特征。 | No |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |
| **MemberID** | int | 账户ID | No |
| **ProjectID** | string | 项目组ID | No |
| **Remark** | string | 资源描述 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |
| **NATGWID** | string | 返回创建的NAT网关ID | No |





    
    
## 12.2 获取NAT网关信息  - DescribeNATGW

获取NAT网关信息

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | No |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |
| **Keyword** | string | 关键字 | No |
| **ProjectID** | string | 项目组ID | No |
| **NATGWIDs** | array<string> | 【数组】NAT网关的 ID。调用方式举例：NATGWIDs.0=“one-id”、NATGWIDs.1=“two-id”。 | No |
| **Offset** | int | 列表起始位置偏移量，默认为0。 | No |
| **Limit** | int | 返回数据长度，默认为20，最大100。 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |
| **TotalCount** | int | 返回NAT网关总个数 | No |
| **Infos** | array<[*NATGWInfo*](#NATGWInfo)> | 【数组】返回nat网关对象数组 | No |



### 数据模型


    
#### NATGWEIPInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IPID** | string | EIP的ID | No |
| **IP** | string | EIP的地址 | No |
| **IPStatus** | string | EIP的状态 | No |

    

    
#### NATGWInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 | No |
| **RegionAlias** | string | 地域别名 | No |
| **Name** | string | 名称 | No |
| **Remark** | string | 备注 | No |
| **ChargeType** | string | 计费模式。枚举值：Dynamic，表示小时；Month，表示月；Year，表示年； | No |
| **CompanyID** | int | 公司ID | No |
| **Email** | string | 邮箱 | No |
| **ProjectID** | string | 项目组ID | No |
| **ProjectName** | string | 项目组名称 | No |
| **NATGWID** | string | NAT网关ID | No |
| **NATGWStatus** | string | 状态。Creating:创建中, Running:运行中, Deleting:删除中, Deleted:已删除 | No |
| **VMType** | string | 机型 | No |
| **EIP** | string | EIP(拟弃用,现在每个NAT可绑定多个EIP) | No |
| **EIPInfos** | array<[*NATGWEIPInfo*](#NATGWEIPInfo)> | 绑定的EIP信息 | No |
| **VPCID** | string | NAT网关实例所在的 VPC ID | No |
| **VPCName** | string | VPC名称 | No |
| **SubnetID** | string | NAT网关实例所在的子网 ID | No |
| **SubnetName** | string | 子网名称 | No |
| **SGID** | string | NAT网关绑定的安全组ID | No |
| **SGName** | string | 安全组名称 | No |
| **AlarmTemplateID** | string | 告警模板ID | No |
| **CreateTime** | int | 创建时间，时间戳 | No |
| **ExpireTime** | int | 过期时间，时间戳 | No |
| **UpdateTime** | int | 更新时间，时间戳 | No |
| **DeleteTime** | int | 删除时间，时间戳 | No |

    

    

    





    
    
## 12.3 删除NAT网关 - DeleteNATGW

删除NAT网关

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | No |
| **NATGWID** | string | NATGWID | No |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |





    
    
## 12.4 添加NAT网关白名单 - CreateNATGWRule

添加NAT网关白名单

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | No |
| **NATGWID** | string | NAT网关ID | No |
| **BindResourceType** | string | 资源类型， 枚举值范围：VM、VPC、Subnet。类型为VPC时，BindResourceID不能为空 | No |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |
| **MemberID** | int | 账户ID | No |
| **BindResourceID** | string | 绑定资源的ID，分别为VMID、VPCID、SubnetID | No |
| **EIPID** | string | 出口EIP的ID，不传表示随机选择一个EIP作为出口 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |





    
    
## 12.5 获取NAT网关白名单信息  - DescribeNATGWRule

获取NAT网关白名单信息

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | No |
| **NATGWID** | string | NAT网关ID | No |
| **Offset** | int | 列表起始位置偏移量，默认为0。 | No |
| **Limit** | int | 返回数据长度，默认为20，最大100。 | No |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |
| **Keyword** | string | 关键字 | No |
| **RuleIDs** | array<string> | 【数组】NAT网关白名单ID。调用方式举例：RuleIDs.0=“one-id”、RuleIDs.1=“two-id”。 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |
| **TotalCount** | int | 总条目数 | No |
| **Infos** | array<[*NATGWRuleInfo*](#NATGWRuleInfo)> | NATGWRule信息列表 | No |



### 数据模型


    

    

    
#### NATGWRuleInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NATGWID** | string | NAT网关ID | No |
| **RuleID** | string | 白名单ID | No |
| **NATGWType** | string | nat网关类型 | No |
| **BindResourceID** | string | 绑定的资源ID | No |
| **BindResourceType** | string | 绑定资源的类型 | No |
| **Address** | string | 绑定资源的IP信息，对应于资源类型，分别为虚拟机内网ip、subnet网段、vpc网段 | No |
| **EIP** | string | 出口IP的地址 | No |
| **Name** | string | 添加的白名单资源名称 | No |
| **IP** | string | 同Address(拟弃用) | No |
| **RuleStatus** | string | 状态。Bounding:绑定中,Bound:已绑定,Unbounding:解绑中,Unbound：已解绑 | No |
| **CreateTime** | int | 创建时间，时间戳。 | No |

    





    
    
## 12.6 删除NAT网关规则 - DeleteNATGWRule

删除NAT网关规则

### 请求参数



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，请参考[DescribeRegion接口] | No |
| **RuleID** | string | RuleID | No |
| **NATGWID** | string | NATGWID | No |
| **CompanyID** | int | 租户ID，仅admin操作时生效 | No |

### 响应字段



| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 | **Yes** |
| **Action** | string | 操作指令名称 | **Yes** |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 | No |







