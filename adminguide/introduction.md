# 1 概述

## 1.1 平台简介

云平台统一管理服务为企业用户提供租户视角和管理视角两套控制台，租户控制台用于平台租户虚拟资源管理，管理控制台用于平台管理者对云平台整体的运营运维。

租户控制台是为租户（主/子帐号）提供的 Web 云资源管理平台，支持租户主/子账号管理及权限控制，可对云平台所有产品服务的虚拟资源进行全生命周期管理，同时可对虚拟资源进行监控告警、计量计费及日志审计等管理。

管理控制台是为平台管理者及运维人员提供的 Web 运营运维管理平台，使用管理员账号统一管理整个云平台全局，拥有平台所有管理权限，包括全平台账号认证、多租户管理、资源管理、流程审批、计量计费、监控告警、审计日志、平台管理及运维迁移等管理功能模块，同时提供大屏监控服务，支持自由布局灵活投屏，提升平台资源的数据可视化效果。

## 1.2 基础概念

云平台作为软件平台部署至物理服务器节点，最终以云服务的形式对外提供虚拟化产品。管理控制台支持管理数据中心级别的计算、存储及网络资源，并可将数据中心从逻辑上划分为多个集群，通过统一账号认证体系管理平台提供的云资源。针对平台在使用和运营过程中会涉及的基础概念如下：

* **地域**

  地域（Region）是云平台中的一个逻辑概念，指资源部署的物理位置分类，可对应机柜、机房或数据中心。

  通常一个数据中心对应一套 UCloudStack 云平台，数据中心之间资源和网络完全物理隔离，可通过一套管理平台管理遍布各地数据中心的私有云平台。

* **集群**

  集群（Set）是平台物理资源的逻辑划分，用于区分不同配置规格及不同存储类型的服务节点，如 X86 计算集群、ARM 计算集群、SSD 存储集群或商业存储集群等。

  一个数据中心可支持部署多个计算和存储集群，一个集群通常由一组配置、用途相同的物理节点组成，用户可将虚拟资源部署于不同的计算集群，并可跨集群挂载分布式块存储设备。

* **管理员账号**

  系统管理员 `admin` 账号是管理员控制台账号，可创建系统管理员和地域管理员。

  系统管理员拥有平台所有管理权限，用于全局管理和运营整个云平台。可通过管理员账号管理云平台的地域、集群、租户、资源、计费、审批、安全及平台全局配置；同时也可对管理员账号自身进行安全管理。

  地域管理员拥有平台特定地域下的管理权限，用于运营整个云平台。可通过管理员账号管理云平台特定地域下的集群、资源、计费、审批及平台全局配置。

* **租户**：

  平台支持多租户模式，用于有多级组架构的企业，可将租户作为一个单独的公司进行运营，有效实现权限管理，除低总公司、子公司及不同部门资源混用可能造成的风险，并可实现资源审计。

  租户是平台中一组资源的集合，提供资源隔离、子账号、权限控制、配额及价格配置等能力。不同租户间资源通过 VPC 网络及权限实现强隔离；租户内所有主账号和子账号的资源、费用、配额及审批均归属于租户。

- **主账号**

  一个租户必须有一个主账号，主账号默认有租户下所有资源及管理的全部权限。可通过主账号创建和管理子账号，并管理子账号的权限。

- **子账号**

  子账号是主账号创建的用户，子账号在租户下的权限由主账号控制。一个租户可拥有多个子账号，支持对子账号进行资源管理的权限控制。

- **外置存储**

  平台默认提供分布式存储，外置存储是指平台通过 ISCSI 协议对接的商业存储资源池（如 IPSAN），支持一键扫描商业存储中的 LUN 存储卷信息，并可将存储卷作为虚拟机的系统盘和数据盘。

* **外网网段**

  外网网段是平台对外通信的网络，一般由管理员或运维人员通过物理网络分配并配置至云平台。外网网段是平台为租户分配外网 IP （弹性 EIP）的 IP 资源池，支持 IPv4 和 IPv6 两种 IP 类型，并支持配置网段路由并自动下发路由至平台虚拟机。

