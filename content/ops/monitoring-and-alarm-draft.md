## 基础设施监控和预警

目前计划是，先利用云平台服务商自身提供的监控预警手段，如果达不到要求，则再考虑其它方法。

### 设置监控预警的步骤

1. 登录[云服务器管理控制台](https://ecs.console.aliyun.com)；
2. 到左侧边栏展开`运维与监控`，找到[云监控平台](https://cloudmonitor.console.aliyun.com)；
3. 在云监控平台页面左侧找到报警服务；
4. 添加联系人，也就是告警消息接收人，这里支持电话、手机短信、邮件、钉钉等通知；
5. 添加报警规则（选择阈值报警）、设置阈值和通知方式，这里支持的规则已经很全；（还支持回调函数，这个方便故障恢复）；

### 注意事项

1. 告警电话不是免费的，我了解到的阿里云服务实例类型 xn4，75 RMB 包 6 个月 500 通电话；
2. 短信免费 1000 条 / 月，这个对于简单的场景应该足够；

（备注：这里的短信或者电话等额度可在云监控平台页的资源消耗那里查看到。）

### 推荐监控和预警实施方式

1. 消息发送方式采用短信和邮件；
2. 监控项目和阈值
   1. 公网流出带宽使用率；
   2. 内存使用率；
   3. 磁盘使用率；
   4. CPU 使用率（Host.cpu.total）；
3. 恢复动作
   1. 人工干预（这个待补充，因为之前出现的两次问题原因还不明确，如何恢复的也还不了解）；
   2. 自动化恢复（这个待补充，需要在 `1` 明确后进行）；

### 监控和预警设置的权限

阿里云平台有个 [RAM (Resource Access Management) 权限管理台](https://ram.console.aliyun.com)，可以新建 RAM 账户，给 RAM 账户设置权限，例如，单独给云监控的权限对应 `AliyunCloudMonitorFullAccess`(对应有个云监控只读权限)。

### 待确定的内容

1. 监控项目和阈值；
2. 预警消息接收人；
3. 人工干预恢复之前是怎么恢复的？
