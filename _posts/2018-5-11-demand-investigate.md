---
layout: post
title: 需求调研
date: 2018-5-11
author: IronHead
categories: 需求调研
tags: 需求调研
cover: 'https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/%E5%9B%BE1%E6%B5%81%E7%A8%8B%E5%9B%BE.png'

---


### 整体思路：
  结合项目背景、项目需求及相关资料，首先以整体流程图和用例图的形式将整个生产管理过程展现出来，尽可能全面地呈现生产管理的过程及异常（不合格）情况。
<p>
  之后按照流程图，将生产管理大致划分为订单管理，采购管理，仓库管理，生产管理四个模块。 针对每个模块，以流程图的形式对每一个模块本身的运行方式以及与其他模块的交互过程进行了简单分析，并简单罗列了过程中所产生的对企业管理所需的数据，以表格的形式将思考的结果展现出来。
</p>

### 初步整体流程图及用例图

![](https://github.com/ghostedge/ghostedge.github.io/raw/master/assets/img/%E5%9B%BE1%E6%B5%81%E7%A8%8B%E5%9B%BE.png)




![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/%E5%9B%BE2%E7%94%A8%E4%BE%8B%E5%9B%BE.png)



还有一些简单的用例。
![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/%E5%9B%BE3%E7%94%A8%E4%BE%8B.png)



### 生产管理表格及功能设计

主要功能为产品 BOM 及物料 BOM 的管理，以及原料分配记录和生产产品统计。

## 1.原料分配记录

当原料从仓库中以车间为单位被领取后，需要分配到每个车间的具体岗位上。因此，原料的类型，流向和流量应该被生产部门主管录入到系统中，以备查看和后续管理使用。

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/%E5%9B%BE%E7%89%874.png)



<p>
功能描述：
</p>
<p>
新建原料分配记录：各车间生产部门主管持有该功能的使用权限，目的在于记录流入本车间的所有原料具体流向各岗位的数量和时间。
</p>
<p>
查询原料分配记录：各车间生产部门主管和其上级管理人员持有该功能的使用权限，目的在于监控原料分配的流向。
</p>
<p>
修改原料分配记录：车间生产主管的上级管理人员持有该功能的权限，目的在于防止由于生产主管的操作失误，报表录入出现问题等因素导致数据与实际分配情况产生不一致。
</p>
<p>
删除原料分配记录：车间生产主管的上级管理人员持有该功能的权限，目的在于防止由于生产主管的操作失误，报表录入出现问题等因素导致数据与实际分配情况产生不一致。
</p>
## 2.生产产品统计

某批产品从生产线上完成整个生产流程，在成品被存入仓库进行存储之前，应记录所有当前批次生产出的产品的状况，包括生产时间，生产车间，成品、半成品以及次品的数量，等等，以监控产品的流向和生产情况，以及作为成本管理人员进行成本核算的依据。

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/%E5%9B%BE%E7%89%875.png)


<p>
功能描述：
</p>
<p>
新建生产产品统计记录：各车间生产部门主管持有该功能的使用权限，目的在于记录流出本车间生产线的所有类型产品（包括成品，半成品，次品）的时间，数量和目标存储位置等信息。
</p>
<p>
查询生产产品统计记录：各车间生产部门主管和其上级管理人员，以及成本管理人员持有该功能的使用权限，目的在于监控产品的流向和生产情况，以及作为成本管理人员进行成本核算的依据。
</p>
<p>
修改生产产品统计记录：车间生产主管的上级管理人员持有该功能的权限，目的在于防止由于生产主管的操作失误，报表录入出现问题等因素导致数据与实际生产情况产生不一致。
</p>
<p>
删除生产产品统计记录：车间生产主管的上级管理人员持有该功能的权限，目的在于防止由于生产主管的操作失误，报表录入出现问题等因素导致数据与实际生产情况产生不一致。
</p>
## 3.产品BOM

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/%E5%9B%BE6%E4%BA%A7%E5%93%81BOM%E8%A1%A8%E6%A0%BC.png)



功能：查询、新建、修改、删除。
•可根据产品编号、名称进行查询。
•查看产品BOM条目的时候，该产品所需的原料BOM清单也会显示出来。
•在新建物料需求计划报表的时候可以直接在物料条目前面勾选。

## 4.物料BOM

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图7物料BOM表格.png)



功能：查询、新建、修改、删除。
•可根据物料编号、名称进行查询。

### 订单管理表格及功能设计

在订单管理部分，我们可以得到如下数据信息。

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图8订单数据信息.png)

以表格为载体，对数据的传递过程进行分析：
<p>
系统中记录所有物料及产品BOM清单，对每个接受的订单，可以分解出生产计划（生产计划包括需要生产的产品及截止时间），由生产计划得到物料需求计划，与仓库管理模块交互，领料或生成采购计划。
</p>

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图9订单数据传递流程.png)

图9订单数据传递流程<br>
由此，设计订单部分功能主要为生产计划、物料需求计划的查看与新建，以及计划的审批。<br>
权限说明：新添加的生产计划、物料需求计划等都会排列进审批列表中等待审批，高权限的使用者才能使用审批功能。此外，例如查看生产计划功能，低权限的使用者只能看到自己提交的生产计划，且无法进行删除。而高权限的使用者可以看到所有的生产计划，并有修改删除的权限。<br>

## 1.生产计划

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图10生产计划表格.png)

图10生产计划表格<br>
功能：查询、添加、修改、删除 <br>
•可根据生产计划编号、计划主题进行查询。 <br>
•查看生产计划明细，对一个具体的生产计划，可以看到计划生产产品的名称及数量。 <br>
•当关闭执行完毕的生产计划单，单据状态为完成。

## 2.物料需求计划

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图11物料需求计划表格.png)


功能：查询、添加、修改、删除 <br>
•可根据物料计划编号、生产计划编号进行查询。 <br>
•查看物料需求计划明细，可以看到需求的物料的名称及数量。 <br>
•生成采购需求：结合仓库管理模块，采购数量为计划中的数量减去仓库里物料的数量。 <br>

### 采购管理表格及功能设计
采购管理部分流程图如下：<br>

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图12采购管理流程图.png)


对流程图进行分析，可知数据信息包括采购物资清单、供货商清单、不同厂商各物品单价清单。异常情况有原料质检不合格等情况，可做退换或更换供货商并记录的处理。<br>
由此，设计采购管理部分主要功能为根据计划创建采购订单并跟踪订单的执行情况，处理物资原料的接收和退货，建立和维护供应商档案等。具体是采购单的查看、创建与审批，供货商管理及质检记录的查看。采购单可在订单管理部分根据“物料需求计划”由系统直接生成，或者采购员主动创建。<br>
单据的审批状态有以下几种：<br>
•未完成：指不完整的采购单据，即在单据录入窗口录入创建了单据，但尚未提交审批。 <br>
•处理中：在单据编辑窗口录入后提交审批，正处于审批工作流中的单据。<br>
•已拒绝：在审批工作流中，被审批人拒绝的单据。<br>
•已退回：采购申请被采购员退回。<br>
•要求重新审批：采购订单与发放在批准后，如果单据创建人对单据的主要数据进行修改，则系统会自动修改单据状态为“要求重新审批”，需要创建人将单据重新提交审批，方可进行订单的进一步处理。<br>

表格设计和功能见下图：<br>

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图13采购表格1.png)



![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图14采购表格2.png)



### 仓库管理表格及功能设计<br>
仓库管理部分流程图如下：<br>


![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图15仓库管理流程图.png)


对流程图进行分析，可知数据信息包括库存信息，出库货品及数量，入库物料及数量。<br>
由此，仓库管理设计的主要功能为：<br>
1.查询库存现状：查看当前的各种产品，原料的库存现状<br>
2.登记入库：<br>
•编辑物品的信息，以及在仓库中的存储位置等信息<br>
•更新订单状态：检查入库物品与订单描述是否相同，并且判断当前仓库的存储状况，如果不能马上入库，先缓存起来；<br>
•确认无误后，打印入库标签，安排物品入库。<br>
3.登记出库： <br>
•在确认出库物品无误后，打印出库标签。 <br>
4.审批确认：<br>
•在审批列表队列中，仓库管理员可选中清单进行确认，也可查看历史记录。 <br>
表格设计如下：<br>

![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图16入库单.png)



![](https://raw.githubusercontent.com/ghostedge/ghostedge.github.io/master/assets/img/图17出库单.png)
