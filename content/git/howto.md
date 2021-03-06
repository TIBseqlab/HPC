## 使用说明（试行）
#### 基本原则
详细规章制度请参见[超算平台用户守则（试行）](policy1.md),这里着重强调几点:
1. 用户使用高性能计算资源，应严格遵守操作守则，一律通过在登录节点提交作业和获得结果，并在计算节点中进行计算。严禁使用非计算节点执行任何计算任务，严禁直接登录到计算节点上运行程序
2. 用户应对自己的作业和数据的安全负责，定期备份或整理数据，防止发生数据损坏、丢失和泄密的问题。
3. 不擅自转让、出借用户帐号，不将口令随意告诉他人；也不借用他人帐户使用计算资源。
4. 未经许可，严禁使用我所高性能计算平台用于一切商业用途。
5.对于单用户帐号可以使用的磁盘空间、计算节点类型、计算节点数量、计算作业队列、运行中作业数量、排队中作业数量等均有限制。由于各超算系统具体配置不同，详细的可用资源限制亦各不相同

试运行阶段，适当放宽要求，
1. 个人用户的数据存在/home文件夹下，希望大家把自己的数据总量控制在500G。现在有部分用户的数据使用量超过限制，请自觉清理，管理员也会定期通知超过标准的用户。
2. 安装软件尽量安装在自己的home文件夹上，这样能保证在一个节点上能用，所有节点都能用；现在几乎所有的软件都有办法安装在自己的home文件夹上，一般搜索“install XXX without root access” 都能找到解决办法。实在没有办法再联系管理员。另外，管理员也会安装一些公用软件。
3. 172.16.25.8是登录节点，不要用来跑程序。如果有程序需要做规模比较大的测试，比如测试时间超过10分钟，请使用另外节点。如果管理员发现用户在使用登录节点进行运算，会给予警告。
4. 现在部署了PBS 队列管理系统，现有用户可能不太会使用。我们会尽快安排培训，在培训之前对集群使用不做硬性规定。培训以后，希望大家过度到使用qsub命令提交作业。
5. DS软件将搭建在单独的节点上，不再与管理节点共享资源。