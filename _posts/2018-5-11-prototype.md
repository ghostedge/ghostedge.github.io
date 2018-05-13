---
layout: post
title: 原型图
date: 2018-5-11
categories: 原型图
tags: 原型图
---
### 原型设计说明：
我们此次企业生产管理系统的原型设计是用 Excel 来实现的，在此基础上，又用墨刀做
了简单的动态原型设计，由于墨刀页面限制，功能无法完全体现，故在此文档中进行说明。
墨刀的展示链接为 [原型链接戳我](https://free.modao.cc/app/yHTC86ceJE9IP7huCqzDDJgErWlzVe0). 我们的企业生产管理系统分四个部分：生产管理、订单管理、采购管理以及仓库管理。
![](https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/prototype-1.png)
<p>
 	在各管理模块，依据使用者权限的不同，会有不同的页面呈现。由于工具的限制，我们
将所有页面做了出来，在冗余的部分添加了“权限”字样或相关注释，以区分不同权限的视
角。
</p>
 	以下是各个模块的界面及功能介绍。
### 一、订单管理部分
<p>
功能主要为生产计划、物料需求计划的查看与新建，以及计划的审批。
权限说明：新添加的生产计划、物料需求计划等都会排列进审批列表中等待审批，高权
限的使用者才能使用审批功能。此外，例如查看生产计划功能，低权限的使用者只能看到自
己提交的生产计划，且无法进行删除。而高权限的使用者可以看到所有的生产计划，并有修
改删除的权限。
</p>
![](https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/prototype-2.png)
### 二、仓库管理部分
<p>
主要功能为查询库存，默认显示全部库存；新建出/入库单，当仓库管理员点击新建按钮后，可选择创建出库单或入库单，编辑完成后， 清单将自动添加到审批队列中；审批确
认，在审批列表队列中，仓库管理员选中一个清单，弹出显示出/入库单具体信息的新窗口，
确认后该条记录自动从审批队列中转移至历史记录中。
</p>
![](https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/prototype-3.png)
### 三、采购管理部分
<p>
采购单可在订单管理部分根据“物料需求计划”由系统直接生成，或者采购员主动创建。
主要功能为采购单的查看、创建与审批，供货商管理及质检记录的查看。
</p>
<p>
审批功能如下，页面中信息除驳回原因外，其他均由系统自动生成。
</p>
![](https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/prototype-4.png)
<p>
  	供货商管理与质检结果记录不再赘述。
</p>
![](https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/prototype-5.png)
### 四、生产管理部分
<p>
 	主要功能为产品 BOM 及物料 BOM 的管理，以及原料分配记录和生产产品统计。产品
BOM 及物料 BOM 的管理不再赘述，以下介绍原料分配记录和生产产品记录功能。
</p>
## 1.原料分配记录
<p>
当原料从仓库中以车间为单位被领取后，需要分配到每个车间的具体岗位上。因此，原
料的类型，流向和流量应该被生产部门主管录入到系统中，以备查看和后续管理使用。
</p>
![](https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/prototype-6.png)
## 2.生产产品统计
<p>
某批产品从生产线上完成整个生产流程，在成品被存入仓库进行存储之前，应记录所有
当前批次生产出的产品的状况，包括生产时间，生产车间，成品、半成品以及次品的数量，
等等，以监控产品的流向和生产情况，以及作为成本管理人员进行成本核算的依据。
</p>
![](https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/prototype-7.png)
