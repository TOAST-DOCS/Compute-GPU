## Compute > GPU Instance > Console Guide

## 激活GPU Instance

为使用GPU Instance，应先申请创建Compute > GPU Instance。

**选择服务 > 单击GPU Instance。**

![GPU_Instance_activation_1_modify.png](http://static.toastoven.net/prod_gpu/en_GPU_Instance_activation_1_modify.png)  

**单击确定激活服务按钮。**

![GPU_Instance_activation_2_modify.png](http://static.toastoven.net/prod_gpu/en_GPU_Instance_activation_2_modify.png)



## 申请创建GPU Instance

**移动至Compute > GPU Instance后，单击申请（1:1咨询）按钮。**

![GPU_Instance_apply_1_modify.png](http://static.toastoven.net/prod_gpu/en_GPU_Instance_apply_1_modify.png)


**填写咨询标题和咨询内容后单击确定按钮。**

![GPU_Instance_apply_2_modify.png](http://static.toastoven.net/prod_gpu/en_GPU_Instance_apply_2_modify.png)
  

**申请创建GPU Instance时填写的内容**

```
输入使用GPU的相关信息。
=============================================================================
* 客户TOAST ID email (ex. email@toast.com) :

* 客户项目ID (ex. ae1bfd024d8841a295988638d90979a4) :
   可在Network > VPC > 子网 > 项目ID中确认。

* 可用性区域(ex. pub-a) :
  可在pub-a、pub-b中选择。

* 要设置的实例名(ex. gpu-instance-001) :
   请输入20个以内的字符。仅可输入英文字母、数字和“-”、“.”。

* 实例类型和数量（ex.g2.c8m96 1台）：
   g2.c8m96 : 8 Core, Memory 96 GB + GPU 1个
   g2.c16m192 : 16 Core, Memory 192 GB + GPU 2个

* 要在要设置的实例中使用的密钥对名(ex. gpu_connect_key) :
   若无所需的密钥对，请创建。

* 实例的块存储类型和大小(GB) (ex. HDD 100 GB) :
   块存储类型：可在SSD与HDD中选择。
   块存储大小可创建为20 GB ~ 1000GB。

* 应连接的Subnet信息(ex. Default Network / 7245176d-1402-47fa-87a6-2c2eafe8807b)
  网络名 / ID / 可多个

=============================================================================


用于使用GPU实例的信息。
=============================================================================
* 服务无法直接使用，提前咨询后可使用。提前咨询可能需要2~3天左右。

* GPU实例以Ubuntu 18.04设置。

* GPU实例IP自动分配。

* GPU实例创建完成后，将通过邮件通知。

=============================================================================
```

* 客户TOAST ID email：输入要申请创建GPU实例的ID信息。
* 客户项目ID：如下图所示可在**Network > VPC > 子网 > 项目ID**中确认。
* 可用性区域：可在pub-a、pub-b中选择。
* 要设置的实例名：请输入20个以内的字符。仅可输入英文字母、数字和“-”、“.”。
* GPU实例类型与实例数

| 实例类型 | GPU数 | Core数 | 内存容量(GB) |
| --- | --- | --- | --- |
| g2.c8m96 | 1 | 8 | 96 |
| g2.c16m192 | 2 | 16 | 192 |

* 要在要设置的实例中使用的密钥对名：无所需密钥对时请创建。
* 实例的块存储类型和大小(GB)：块存储类型可在HDD与SSD中选择，块存储大小可创建为20 GB ~ 1000GB。
* 应连接的Subnet信息：如下图所示可在**Network > VPC > 子网 > 子网名、CIDR**中确认。
* 创建实例相关详细内容请参考[Instance概要](http://docs.toast.com/ko/Compute/Instance/ko/overview/)。


![GPU_Instance_subnetID_1](http://static.toastoven.net/prod_gpu/en_GPU_Instance_subnetID_1.png)


**用于使用GPU实例的信息**

* 服务无法直接使用，提前咨询后可使用。提前咨询可能需要2~3天左右。

* GPU实例以Ubuntu 18.04设置。

* GPU实例IP自动分配。

* GPU实例创建完成后，将通过邮件通知。


## 访问GPU Instance

实例创建完成后，使用SSH访问实例。
Floating IP应连接至实例，安全组中应允许使用TCP端口22(SSH)。

利用SSH客户与设置的密钥对访问实例。
连接SSH相关详细指南请参考[SSH连接指南](https://docs.toast.com/ko/Compute/Instance/ko/overview/#linux)。



## 确认GPU信息

```
# 确认GPU信息
shell > nvidia-smi
```

![GPU_assign_1.png](http://static.toastoven.net/prod_gpu/GPU_assign_1.png)


* GPU：0（分配1个GPU）
* Name：Tesla V100-SXM2（GPU型号）
* Persistence_mode：On（Persistence mode enable状态）
* Temp：30C（当前GPU温度）
* Pwr Usage/Capacity：36W / 300W（当前耗电量 / 最大耗电量）
* Memory-Usage：32480MiB（GPU最大分配内存）
* GPU-Util：0%（GPU Util使用率）

## 一般实例与GPU实例的区别

* GPU实例规格无法更改。
