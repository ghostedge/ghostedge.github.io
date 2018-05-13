---
layout: post
title: 数据库设计
date: 2018-5-11
categories: 数据库设计
tags: 数据库设计
cover: 'https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/数据库ER图.png'
---
## 数据库设计

根据前期的需求调研分析，原型设计，以及小组成员之间的讨论后，我们小组的数据库设计ER图如下：

![](https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/数据库ER图.png)

下面对图中的实例和关系进行说明。

### 供应商
#### 说明：
记录原料供应商的基本信息

#### 属性：
供应商编号 PK
供应商全称
地址
联系方式
负责人
已完成的订单编号

### 采购
#### 说明：
记录采购信息

#### 属性：
采购单编号 PK
创建信息编号
商品编号 FK reference 物料
采购量

### 物料需求（物料需求计划）
##### 说明：
记录订单被分解后的物料需求

#### 属性：
物料需求计划编号 PK
生产计划编号 FK reference 生产计划
创建信息编号 FK reference 创建
需求计划主题
单据状态
物料编号
物料数量

### 生产计划
#### 说明：
记录订单被分解后的生产计划

#### 属性：
生产计划编号 PK
产品编号 FK reference 产品
创建信息编号 FK reference 创建
生产主题
单据状态
审批状态
计划开工日期
计划完成日期

### 物料（物料BOM）
#### 说明：
记录物料的基本信息

#### 属性：
物料编号 PK
创建信息 FK reference 创建信息
物料名称
物料单位
物料数量

### 物料入库/出库
#### 说明：
记录物料入库出库信息

#### 属性：
物料入库/出库单编号 PK
物料编号 FK reference 物料
入库/出库数量
入库/出库时间
仓库编号 FK reference 仓库
负责人编号 reference 用户
操作类型 （入库/出库）

### 产品入库/出库
#### 说明：
记录产品入库出库信息

## 属性：
产品入库/出库单编号 PK
产品编号 FK reference 物料
入库/出库数量
入库/出库时间
仓库编号 FK reference 仓库
负责人编号 reference 用户
操作类型 （入库/出库）

### 仓库
#### 说明：
记录仓库的基本信息

#### 属性：
仓库编号 PK
管理员编号 FK reference 用户
位置

### 用户
#### 说明：
记录操作者的基本信息

#### 属性：
用户编号 PK
用户名
用户密码
用户类型
用户权限
联系方式

### 创建（创建信息）
#### 说明：
记录用户创建表单的基本信息

#### 属性：
创建记录编号 PK
创建时间
创建者编号 FK reference 用户

### 领料（物料管理）
#### 说明：
记录生产单位领取物料的记录

#### 属性：
领料记录编号 PK
领料单位编号 FK reference 生产单位
物料编号 FK reference 物料
领取仓库编号 FK reference 仓库
审批人编号 FK reference 用户
物料需求单据编号 FK reference 物料需求
数量
领料日期


### 生产管理
#### 说明：
记录生产单位产出产品的情况

#### 属性：
生产管理记录编号 PK
生产单位编号 FK reference 生产单位
产品编号 FK reference 产品
产品类型（成品/半成品/废品）
目的存储仓库编号 FK reference 仓库
审批人编号 FK reference 用户
数量
生产日期

### 生产单位
#### 说明：
记录生产单位的基本信息

#### 属性：
生产单位编号 PK
生产单位类型
产出产品
负责人编号 FK reference 用户

### 配方
#### 说明：
记录产品和物料之间的对应关系

####s 属性：
产品编号 FK reference 产品
物料编号 FK reference 物料
创建信息 FK reference 创建
物料用量
