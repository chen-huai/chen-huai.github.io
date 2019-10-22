---
title: BPMN第一弹：ARIS中BPMN的控件解释
date: 2019-10-22 11:00:56
tags:
	- 工作
	- BPMN
---
### 第一章：目的
了解ARIS中BPMN的控件解释，以便更好的制作。

* pool
* lane
* start event
* intermediate event
* end event
* task
* subprocess
* call activity
* gateway
* data object

<!-- more -->
### 第二章：内容
#### pool---池
![4457a13a187084cf8acc2e7c6c575327.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris1.png)

1. add new lanes---增加新泳道
2. multi-instance---多实例

#### lane---泳道
![f2b4b53a304918ebb0b576dabe28abe2.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris2.png)

1. add new lanes---新增加泳道
2. add lanes above---上边增加
3. add lanes below---下边增加
4. add new lanes to the left--- 左边增加
5. add new lanes to the right---右边增加

#### start event---开始事件
![ec1585cacb17185182b774ba62e50a09.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris3.png)

1. none---无
2. compensation event---补偿事件
3. conditional event---有条件的事件
4. error event---错误事件
5. escalation event---升级事件
6. message event---消息事件
7. multiple event---多个事件
8. parallel event---平行事件
9. signal event---信号事件
10. timer event---计时器事件

#### intermediate event---中间事件
![9b1ff5de788efa503e50d704f4b4b230.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris4.png)

1. none---无
2. cancel event---取消事件
3. compensation event---补偿事件
4. conditional event---有条件的事件
5. error event---错误事件
6. escalation event---升级事件
7. link event---链接事件
8. message event---消息事件
9. multiple event---多个事件
10. parallel event---平行事件
11. signal event---信号事件
12. timer event---计时器事件

#### end event---结束事件
![ecdb28a0008fbf16cda2cbeb620c8b33.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris5.png)

1. none---无
2. cancel event---取消事件
3. compensation event---补偿事件
4. error event---错误事件
5. escalation event---升级事件
6. message event---消息事件
7. multiple event---多个事件
8. signal event---信号事件
9. terminate event---终止事件

#### task---任务
![16abcf8986cf543592d185d309bf92a2.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris6.png)

1. abstract task---抽象的任务
2. business rule task---业务规则任务
3. manual task---人工任务
4. receive task---接受任务
5. script task---脚本的任务
6. send task---发送任务
7. service task---服务任务
8. user task---用户任务

#### subprocess---子流程
![d02335cd621ae0d80ce11b1ef069e725.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris7.png)

1. loop type---循环类型
2. standard loop---标准循环
3. multi-instance parallel loop---多实例并行循环
4. multi-instance sequential loop---多实例顺序循环
5. collapse---崩溃
6. transform subprocess into call activity---将子流程转换为调用活动
7. subprocess---子流程
8. ad hoc subprocess---特设子过程
9. event subprocess---事件子流程
10. transaction---事务

#### call activity---调用活动
![2ffef2be158907edca2fd4487e866ba6.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris8.png)
1. loop type---循环类型
2. standard loop---标准循环
3. multi-instance parallel loop---多实例并行循环
4. multi-instance sequential loop---多实例顺序循环
5. collapse---崩溃
6. transform  call activity into subprocess---将调用活动转换为子流程

#### gateway---网关
![eef30fd7de6c651b3b7977127e40d8a3.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris9.png)

1. gateway---网关
2. complex gateway---复杂的网关
3. event based gateway---基于事件的网关
4. exclusive gateway---排他网关
5. inclusive gateway---包容的网关
6. instantiating event based gateway---基于实例化事件的网关
7. instantiating parallel event based gateway---基于实例化并行事件的网关
8. parallel gateway---并行网关

#### data object---数据对象
![0d29f91ee38daaab5bf7a8090f6dac86.png](/img/BPMN第一弹：ARIS中BPMN的控件解释/aris10.png)

1. collection---集合
2. data object---数据对象
3. data input---数据输入
4. data output---数据输出

