



# VPN网关


​    
​    
## 17.1 创建 IPSecVPN 网关 - CreateVPNGW

创建 IPSecVPN 网关

### 请求参数



| 字段名         | 类型   | 描述信息                                                           | 必填    |
|:---------------|:-------|:-----------------------------------------------------------------|:--------|
| **Region**     | string | 地域，请参考[DescribeRegion接口]                                    | **Yes** |
| **Name**       | string | 资源名称                                                           | **Yes** |
| **ChargeType** | string | 计费模式。枚举值：Dynamic，表示小时；Month，表示月；Year，表示年；         | **Yes** |
| **Quantity**   | int    | 购买时长。默认值1。小时不生效，月范围【1，11】，年范围【1，5】。              | **Yes** |
| **EIPID**      | string | 绑定的弹性IP的ID                                                   | **Yes** |
| **VMType**     | string | 虚拟机所在宿主机的集群类型，代表不同架构、不同型号的 CPU 或硬件特征。 | **Yes** |
| **VPCID**      | string | VPNGW 实例所在的 VPC ID                                            | **Yes** |
| **SubnetID**   | string | VPNGW 实例所在的Subnet ID                                          | **Yes** |
| **CompanyID**  | int    | 租户ID，仅admin操作时生效                                           | No      |
| **MemberID**   | int    | 租户ID                                                             | No      |
| **ProjectID**  | string | 项目组ID                                                           | No      |
| **Remark**     | string | 资源描述                                                           | No      |

### 响应字段



| 字段名      | 类型   | 描述信息                                            |
|:------------|:-------|:------------------------------------------------|
| **RetCode** | int    | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**  | string | 操作指令名称                                        |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |
| **VPNGWID** | string | 返回创建的VPN网关ID                                 |


​    

​    


## 17.2 删除 IPSecVPN 网关 - DeleteVPNGW

删除 IPSecVPN 网关

### 请求参数



| 字段名        | 类型   | 描述信息                        | 必填    |
|:--------------|:-------|:--------------------------------|:--------|
| **Region**    | string | 地域，请参考[DescribeRegion接口] | No      |
| **VPNGWID**   | string | VPNGWID                         | **Yes** |
| **CompanyID** | int    | 租户ID，仅admin操作时生效        | No      |

### 响应字段



| 字段名      | 类型   | 描述信息                                            |
|:------------|:-------|:------------------------------------------------|
| **RetCode** | int    | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**  | string | 操作指令名称                                        |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |




​    


## 17.3 查询 IPSecVPN 网关  - DescribeVPNGW

查询 IPSecVPN 网关

### 请求参数



| 字段名           | 类型          | 描述信息                                                                                 | 必填    |
|:-----------------|:--------------|:---------------------------------------------------------------------------------------|:--------|
| **Region**       | string        | 地域，请参考[DescribeRegion接口]                                                          | **Yes** |
| **Offset**       | int           | 列表起始位置偏移量，默认为0。                                                              | **Yes** |
| **Limit**        | int           | 返回数据长度，默认为20，最大100。                                                           | **Yes** |
| **CompanyID**    | int           | 租户ID，仅admin操作时生效                                                                 | No      |
| **MemberID**     | int           | 租户ID                                                                                   | No      |
| **ProjectIDs.N** | array<string> | 【数组】项目组 IDs，输入有效的 ID。调用方式举例：ProjectIDs.0=“one-id”、ProjectIDs.1=“two-id”。 | No      |
| **VPNGWIDs.N**   | array<string> | 【数组】VPN网关的 ID。调用方式举例：VPNGWIDs.0=“one-id”、VPNGWIDs.1=“two-id”。                 | No      |

### 响应字段



| 字段名         | 类型                             | 描述信息                                            |
|:---------------|:---------------------------------|:------------------------------------------------|
| **RetCode**    | int                              | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**     | string                           | 操作指令名称                                        |
| **Message**    | string                           | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |
| **Infos**      | array<[*VPNGWInfo*](#VPNGWInfo)> | 【数组】返回 VPN 网关对象数组                         |
| **TotalCount** | int                              | 返回 VPN 网关总个数                                 |



### 数据模型


​    
#### VPNGWInfo

| 字段名          | 类型   | 描述信息                                                                  | 必填 |
|:----------------|:-------|:------------------------------------------------------------------------|:-----|
| **Region**      | string | 地域                                                                      | No   |
| **CompanyID**   | int    | 公司ID                                                                    | No   |
| **Email**       | string | 邮箱                                                                      | No   |
| **Name**        | string | 资源名称                                                                  | No   |
| **Remark**      | string | 资源描述                                                                  | No   |
| **ChargeType**  | string | 计费类型。枚举值：Dynamic，表示小时；Month，表示月；Year，表示年；                | No   |
| **ProjectID**   | string | 项目组ID                                                                  | No   |
| **ProjectName** | string | 项目组名称                                                                | No   |
| **VPNGWID**     | string | VPN网关ID                                                                 | No   |
| **VPCID**       | string | VPN网关实例所在的 VPC ID                                                  | No   |
| **SubnetID**    | string | VPN网关实例所在的子网 ID                                                  | No   |
| **EIPID**       | string | VPN网关实例绑定的 EIP 的 ID                                               | No   |
| **State**       | string | 资源状态。Creating:创建中, Running:运行中, Deleting:删除中, Deleted:已删除 | No   |
| **TunnelCount** | int    | 隧道数量                                                                  | No   |
| **CreateTime**  | int    | 创建时间，时间戳                                                           | No   |
| **ExpireTime**  | int    | 过期时间，时间戳                                                           | No   |
| **EIPIP**       | string | VPN网关绑定的 EIP 的 IP                                                   | No   |
| **Arch**        | string | 架构                                                                      | No   |
| **VMType**      | string | 机型                                                                      | No   |






​    
## 17.4 创建 IPSecVPN 对端网关 - CreateRemoteVPNGW

创建 IPSecVPN 对端网关

### 请求参数



| 字段名        | 类型   | 描述信息                        | 必填    |
|:--------------|:-------|:------------------------------|:--------|
| **Region**    | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **ProjectID** | string | 项目组ID                        | **Yes** |
| **Name**      | string | 资源名称                        | **Yes** |
| **IPAddress** | string | 对端网关IP地址                  | **Yes** |
| **CompanyID** | int    | 租户ID，仅admin操作时生效        | No      |
| **MemberID**  | int    | 租户ID                          | No      |
| **Remark**    | string | 资源描述                        | No      |

### 响应字段



| 字段名            | 类型   | 描述信息                                            |
|:------------------|:-------|:------------------------------------------------|
| **RetCode**       | int    | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**        | string | 操作指令名称                                        |
| **Message**       | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |
| **RemoteVPNGWID** | string | 返回创建的对端网关 ID                               |






​    
## 17.5 删除 IPSecVPN 对端网关  - DeleteRemoteVPNGW

删除 IPSecVPN 对端网关

### 请求参数



| 字段名            | 类型   | 描述信息                        | 必填    |
|:------------------|:-------|:----------------------------|:--------|
| **Region**        | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **RemoteVPNGWID** | string | 对端网关 ID                     | **Yes** |
| **CompanyID**     | int    | 租户ID，仅admin操作时生效        | No      |

### 响应字段



| 字段名      | 类型   | 描述信息                                            |
|:------------|:-------|:------------------------------------------------|
| **RetCode** | int    | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**  | string | 操作指令名称                                        |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |



​    



## 17.6 查询 IPSecVPN 对端网关  - DescribeRemoteVPNGW

查询 IPSecVPN 对端网关

### 请求参数



| 字段名               | 类型          | 描述信息                                                                                 | 必填    |
|:---------------------|:--------------|:---------------------------------------------------------------------------------------|:--------|
| **Region**           | string        | 地域，请参考[DescribeRegion接口]                                                          | **Yes** |
| **Offset**           | int           | 列表起始位置偏移量，默认为0。                                                              | **Yes** |
| **Limit**            | int           | 返回数据长度，默认为20，最大100。                                                           | **Yes** |
| **CompanyID**        | int           | 租户ID，仅admin操作时生效                                                                 | No      |
| **MemberID**         | int           | 租户ID                                                                                   | No      |
| **ProjectIDs.N**     | array<string> | 【数组】项目组 IDs，输入有效的 ID。调用方式举例：ProjectIDs.0=“one-id”、ProjectIDs.1=“two-id”。 | No      |
| **RemoteVPNGWIDs.N** | array<string> | 【数组】VPN网关的 ID。调用方式举例：VPNGWIDs.0=“one-id”、VPNGWIDs.1=“two-id”。                 | No      |

### 响应字段



| 字段名         | 类型                                         | 描述信息                                            |
|:---------------|:---------------------------------------------|:------------------------------------------------|
| **RetCode**    | int                                          | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**     | string                                       | 操作指令名称                                        |
| **Message**    | string                                       | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |
| **Infos**      | array<[*RemoteVPNGWInfo*](#RemoteVPNGWInfo)> | 对端网关RemoteVPNGW信息列表                         |
| **TotalCount** | int                                          | 总条目数                                            |

### 数据模型


​    
#### RemoteVPNGWInfo

| 字段名            | 类型   | 描述信息                 | 必填    |
|:------------------|:-------|:-----------------------|:--------|
| **Region**        | string | 地域                     | **Yes** |
| **TunnelCount**   | int    | 隧道数量                 | **Yes** |
| **RemoteVPNGWID** | string | 对端网关 ID              | **Yes** |
| **Name**          | string | 对端网关名               | **Yes** |
| **Remark**        | string | 描述                     | **Yes** |
| **IPAddress**     | string | 对端网关IP地址           | **Yes** |
| **CreateTime**    | int    | 创建时间，时间戳          | **Yes** |
| **UpdateTime**    | int    | 更新时间，时间戳          | **Yes** |
| **CompanyID**     | int    | 租户ID，仅admin操作时生效 | **Yes** |
| **ProjectID**     | string | 项目组ID                 | **Yes** |
| **ProjectName**   | string | 项目组名称               | **Yes** |
| **Email**         | string | 邮箱                     | **Yes** |
| **State**         | string | 资源状态                 | **Yes** |




​    


## 17.7 创建 IPSecVPN 隧道  - CreateVPNTunnel

创建 IPSecVPN 隧道

### 请求参数



| 字段名                           | 类型   | 描述信息                                                                                                                                                                           | 必填    |
|:---------------------------------|:-------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------|
| **Region**                       | string | 地域，请参考[DescribeRegion接口]                                                                                                                                                    | **Yes** |
| **Name**                         | string | 资源名称                                                                                                                                                                           | **Yes** |
| **VPNGWID**                      | string | VPN网关 ID                                                                                                                                                                         | **Yes** |
| **RemoteVPNGWID**                | string | 对端网关 ID                                                                                                                                                                        | **Yes** |
| **LocalSubnetIDs.N**             | string | 本端网段 ID（子网 ID）                                                                                                                                                               | **Yes** |
| **RemoteSubnets.N**              | string | 对端网段                                                                                                                                                                           | **Yes** |
| **PreSharedKey**                 | string | 预共享密钥                                                                                                                                                                         | **Yes** |
| **CompanyID**                    | int    | 租户ID，仅admin操作时生效                                                                                                                                                           | No      |
| **MemberID**                     | int    | 租户ID                                                                                                                                                                             | No      |
| **ProjectID**                    | string | 项目组ID                                                                                                                                                                           | No      |
| **Remark**                       | string | 资源描述                                                                                                                                                                           | No      |
| **IKEVersion**                   | string | IKE 版本 V1,V2                                                                                                                                                                     | No      |
| **IKEAuthenticationAlgorithm**   | string | IKE 认证算法                                                                                                                                                                       | No      |
| **IKEEncryptionAlgorithm**       | string | IKE 加密算法                                                                                                                                                                       | No      |
| **IKEExchangeMode**              | string | 协商模式 ，IKE 协商的模式，支持主模式（main）和野蛮模式（aggressive）。默认为主模式                                                                                                       | No      |
| **IKEDhGroup**                   | int    | IKE 交换密钥时使用的 Diffie-Hellman 算法，支持 1、2、5、14、24。默认值为 2 。                                                                                                             | No      |
| **IKELocalLabel**                | string | VPN 网关的标识，用于 IKE 第一阶段协商。支持 IP 地址和 FQDN（全称域名），域名标识需使用野蛮协商模式。默认为 IP 地址。                                                                      | No      |
| **IKERemoteLabel**               | string | 对端网关的标识，用于 IKE 第一阶段协商。支持 IP 地址和 FQDN（全称域名），域名标识需使用野蛮协商模式。默认为 IP 地址。                                                                      | No      |
| **IKESALifetime**                | int    | 第一阶段 SA 的生存时间，在超过生存周期后， SA 将被重新协商。如 86400 秒。默认值为 86400 。                                                                                              | No      |
| **IPSecAuthenticationAlgorithm** | string | 为第二阶段用户数据提供的认证保护功能，支持 md5 和 sha1 两种认证算法。默认值为 sha1 。                                                                                                 | No      |
| **IPSecEncryptionAlgorithm**     | string | 为第二阶段用户数据提供的加密保护功能，支持 3des、aes128、aes192 和 aes256 四种加密算法 ，使用 AH 安全协议时不可用。默认值为 aes128 。                                                    | No      |
| **IPSecProtocol**                | string | IPSec 支持 AH 和 ESP 两种安全协议，AH 只支持数据的认证保护，ESP 支持认证和加密，推荐使用 ESP 协议。默认值为 ESP 。                                                                      | No      |
| **IPSecPFSDhGroup**              | int    | PFS （Perfect Forward Secrecy，完善的前向安全性）特性是一种安全特性，指一个密钥被破解，并不影响其他密钥的安全性。支持 1、2、5、14、24 与关闭（Disable 适用于不支持 PFS 的客户端）。默认值为 2 。 | No      |
| **IPSecSALifetime**              | int    | 第二阶段 SA 的生存时间，在超过生存周期后， SA 将被重新协商。如 86400 秒。默认值为 86400 。                                                                                              | No      |

### 响应字段



| 字段名          | 类型   | 描述信息                                            |
|:----------------|:-------|:------------------------------------------------|
| **RetCode**     | int    | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**      | string | 操作指令名称                                        |
| **VPNTunnelID** | string | 返回创建的隧道 ID                                   |
| **Message**     | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |



​    



## 17.8 删除 IPSecVPN 隧道  - DeleteVPNTunnel

删除 IPSecVPN 隧道

### 请求参数



| 字段名          | 类型   | 描述信息                        | 必填    |
|:----------------|:-------|:------------------------------|:--------|
| **Region**      | string | 地域，请参考[DescribeRegion接口] | No      |
| **VPNTunnelID** | string | 隧道 ID                         | **Yes** |
| **CompanyID**   | int    | 租户ID，仅admin操作时生效        | No      |

### 响应字段



| 字段名      | 类型   | 描述信息                                            |
|:------------|:-------|:------------------------------------------------|
| **RetCode** | int    | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**  | string | 操作指令名称                                        |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |



​    



## 17.9 更新 IPSecVPN 隧道  - UpdateVPNTunnel

更新 IPSecVPN 隧道

### 请求参数



| 字段名                           | 类型   | 描述信息                                                                                                                                                                           | 必填    |
|:---------------------------------|:-------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------|
| **Region**                       | string | 地域，请参考[DescribeRegion接口]                                                                                                                                                    | **Yes** |
| **CompanyID**                    | int    | 租户ID，仅admin操作时生效                                                                                                                                                           | **Yes** |
| **VPNTunnelID**                  | string | 隧道 ID                                                                                                                                                                            | **Yes** |
| **LocalSubnetIDs.N**             | string | 本端网段 ID（子网 ID）                                                                                                                                                               | No      |
| **RemoteSubnets.N**              | string | 对端网段                                                                                                                                                                           | No      |
| **PreSharedKey**                 | string | 预共享密钥                                                                                                                                                                         | No      |
| **IKEVersion**                   | string | IKE 版本 V1,V2                                                                                                                                                                     | No      |
| **IKEAuthenticationAlgorithm**   | string | IKE 认证算法                                                                                                                                                                       | No      |
| **IKEEncryptionAlgorithm**       | string | IKE 加密算法                                                                                                                                                                       | No      |
| **IKEExchangeMode**              | string | 协商模式 ，IKE 协商的模式，支持主模式（main）和野蛮模式（aggressive）。默认为主模式                                                                                                       | No      |
| **IKEDhGroup**                   | int    | IKE 交换密钥时使用的 Diffie-Hellman 算法，支持 1、2、5、14、24。默认值为 2 。                                                                                                             | No      |
| **IKELocalLabel**                | string | VPN 网关的标识，用于 IKE 第一阶段协商。支持 IP 地址和 FQDN（全称域名），域名标识需使用野蛮协商模式。默认为 IP 地址。                                                                      | No      |
| **IKERemoteLabel**               | string | 对端网关的标识，用于 IKE 第一阶段协商。支持 IP 地址和 FQDN（全称域名），域名标识需使用野蛮协商模式。默认为 IP 地址。                                                                      | No      |
| **IKESALifetime**                | int    | 第一阶段 SA 的生存时间，在超过生存周期后， SA 将被重新协商。如 86400 秒。默认值为 86400 。                                                                                              | No      |
| **IPSecAuthenticationAlgorithm** | string | 为第二阶段用户数据提供的认证保护功能，支持 md5 和 sha1 两种认证算法。默认值为 sha1 。                                                                                                 | No      |
| **IPSecEncryptionAlgorithm**     | string | 为第二阶段用户数据提供的加密保护功能，支持 3des、aes128、aes192 和 aes256 四种加密算法 ，使用 AH 安全协议时不可用。默认值为 aes128 。                                                    | No      |
| **IPSecProtocol**                | string | IPSec 支持 AH 和 ESP 两种安全协议，AH 只支持数据的认证保护，ESP 支持认证和加密，推荐使用 ESP 协议。默认值为 ESP 。                                                                      | No      |
| **IPSecPFSDhGroup**              | int    | PFS （Perfect Forward Secrecy，完善的前向安全性）特性是一种安全特性，指一个密钥被破解，并不影响其他密钥的安全性。支持 1、2、5、14、24 与关闭（Disable 适用于不支持 PFS 的客户端）。默认值为 2 。 | No      |
| **IPSecSALifetime**              | int    | 第二阶段 SA 的生存时间，在超过生存周期后， SA 将被重新协商。如 86400 秒。默认值为 86400 。                                                                                              | No      |

### 响应字段



| 字段名      | 类型   | 描述信息                                            |
|:------------|:-------|:------------------------------------------------|
| **RetCode** | int    | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**  | string | 操作指令名称                                        |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |



​    



## 17.10 查询 IPSecVPN 隧道  - DescribeVPNTunnel

查询 IPSecVPN 隧道

### 请求参数



| 字段名             | 类型   | 描述信息                        | 必填    |
|:-------------------|:-------|:--------------------------------|:--------|
| **Region**         | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **Offset**         | int    | 列表起始位置偏移量，默认为0      | **Yes** |
| **Limit**          | int    | 返回数据长度，默认为20，最大100   | **Yes** |
| **CompanyID**      | int    | 租户ID，仅admin操作时生效        | No      |
| **MemberID**       | int    | 租户ID                          | No      |
| **ProjectIDs.N**   | string | 项目组ID                        | No      |
| **VPNTunnelIDs.N** | string | VPNTunnelIDs                    | No      |



### 响应字段



| 字段名         | 类型                                     | 描述信息                                            |
|:---------------|:-----------------------------------------|:------------------------------------------------|
| **RetCode**    | int                                      | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**     | string                                   | 操作指令名称                                        |
| **Message**    | string                                   | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |
| **Infos**      | array<[*VPNTunnelInfo*](#VPNTunnelInfo)> | VPN信息列表                                         |
| **TotalCount** | int                                      | 总条目数                                            |

#### VPNTunnelInfo



| 字段名                           | 类型          | 描述信息                                                                                                    | 必填 |
|:---------------------------------|:--------------|:----------------------------------------------------------------------------------------------------------|:-----|
| **Region**                       | string        | 地域，请参考[DescribeRegion接口]                                                                             | No   |
| **Name**                         | string        | 名称                                                                                                        | No   |
| **Remark**                       | string        | 备注                                                                                                        | No   |
| **State**                        | string        | 隧道状态                                                                                                    | No   |
| **ConnectState**                 | string        | 隧道连接状态                                                                                                | No   |
| **VPNTunnelID**                  | string        | 隧道 ID                                                                                                     | No   |
| **VPNGWID**                      | string        | 所属VPN网关ID                                                                                               | No   |
| **RemoteVPNGWID**                | string        | 对端VPN网关ID                                                                                               | No   |
| **LocalSubnetIDs.N**             | array<string> | 【数组】本端网段 ID（子网 ID）                                                                                  | No   |
| **RemoteSubnets.N**              | array<string> | 【数组】对端网段                                                                                              | No   |
| **PreSharedKey**                 | string        | Pre Shared Key ，IPsecVPN 连接的秘钥，用于 VPN 连接的协商。                                                    | No   |
| **IKEVersion**                   | string        | IKE 密钥交换协议的版本。                                                                                     | No   |
| **IKEAuthenticationAlgorithm**   | string        | 为 IKE 协商过程中的报文提供认证。                                                                            | No   |
| **IKEEncryptionAlgorithm**       | string        | 为 IKE 协商过程中的报文提供加密保护。                                                                        | No   |
| **IKEExchangeMode**              | string        | IKE 协商的模式。                                                                                             | No   |
| **IKEDhGroup**                   | int           | IKE 交换密钥时使用的 Diffie-Hellman 算法。                                                                   | No   |
| **IKELocalLabel**                | string        | VPN 网关的标识，用于 IKE 第一阶段协商。                                                                       | No   |
| **IKERemoteLabel**               | string        | 对端网关的标识，用于 IKE 第一阶段协商。                                                                       | No   |
| **IKESALifetime**                | int           | 第一阶段 SA 的生存时间，在超过生存周期后， SA 将被重新协商。                                                   | No   |
| **IPSecAuthenticationAlgorithm** | string        | 为第二阶段用户数据提供的认证保护功能。                                                                       | No   |
| **IPSecEncryptionAlgorithm**     | string        | 为第二阶段用户数据提供的加密保护功能。                                                                       | No   |
| **IPSecProtocol**                | string        | IPSec 支持 AH 和 ESP 两种安全协议，AH 只支持数据的认证保护，ESP 支持认证和加密，推荐使用 ESP 协议。             | No   |
| **IPSecPFSDhGroup**              | int           | PFS （Perfect Forward Secrecy，完善的前向安全性）特性是一种安全特性，指一个密钥被破解，并不影响其他密钥的安全性。 | No   |
| **IPSecSALifetime**              | int           | 第第二阶段 SA 的生存时间，在超过生存周期后， SA 将被重新协商。                                                 | No   |
| **CreateTime**                   | int           | 创建时间，时间戳                                                                                             | No   |
| **UpdateTime**                   | int           | 更新时间，时间戳                                                                                             | No   |
| **DeleteTime**                   | int           | 删除时间，时间戳                                                                                             | No   |
| **CompanyID**                    | int           | 租户ID，仅admin操作时生效                                                                                    | No   |
| **Email**                        | string        | 邮箱                                                                                                        | No   |
| **ProjectID**                    | string        | 项目组ID                                                                                                    | No   |
| **ProjectName**                  | string        | 项目组名称                                                                                                  | No   |
| **VPCID**                        | string        | VPN网关实例所在的 VPC ID                                                                                    | No   |





​    

## 17.11 查询 IPSecVPN 隧道配置  - GetVPNTunnelConfig

查询 IPSecVPN 隧道配置

### 请求参数



| 字段名        | 类型   | 描述信息                        | 必填    |
|:--------------|:-------|:------------------------------|:--------|
| **Region**    | string | 地域，请参考[DescribeRegion接口] | **Yes** |
| **VPNGWID**   | string | VPN网关 ID                      | **Yes** |
| **TunnelID**  | string | 隧道 ID                         | **Yes** |
| **CompanyID** | int    | 租户ID，仅admin操作时生效        | No      |
| **MemberID**  | int    | 租户ID                          | No      |

### 响应字段



| 字段名      | 类型   | 描述信息                                            |
|:------------|:-------|:------------------------------------------------|
| **RetCode** | int    | 返回状态码，为 0 则为成功返回，非 0 为失败            |
| **Action**  | string | 操作指令名称                                        |
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |
| **Info**    | string | 配置内容                                            |