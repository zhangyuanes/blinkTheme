---
title: ray渲记录
date: 2021-05-26 22:37:00
author: zhangyuanes
categories: 开坑
tags:
  - mmd
---

## ray渲记录

### 导入控制器

将ray-mmd中的pmx和x拖入mmd

### 导入天空盒

导入默认天空盒Skybox\Helipad GoldenHour\Sky with box.pmx

### 设置模型描绘顺序

天空盒

场景

人物

ray controller

### 载入主渲染

将ray-mmd中Main中的fx放入mme中，对应人物和场景的部分，此时会发现画面发黑

### mme选项讲解

1. FogMap 雾气

2. LightMap 光源

3. EnvLightMap 环境

将天空盒选择在刚刚选择的天空盒目录下的Sky with lighting with rotation.fx 带有旋转的版本的mme，同时main里面的天空盒选择同样的版本

4. MaterialMap 材质

5. SSAOMap 环境吸收

6. PSSM1-4 四通道阴影

### 选项设置

显示中关闭地面阴影显示，关闭抗锯齿，关闭各向异性过滤

## mme

### 法线

特殊的凹凸贴图。

将法线贴图复制进ray-master的materials中 的新建文件夹中，并且复制主目录下的fx进入新建文件夹，修改fx最后一句配置文件的相对位置为：

```c
#include "../material_common_2.0.fxsub"
```

然后在模型需要修改材质的地方引入新的材质贴图，修改对应的配置，详细请参照：

https://www.bilibili.com/read/cv1171482/

### SSAO

在选项页面，人物一般降低，例如0.8，场景为1

