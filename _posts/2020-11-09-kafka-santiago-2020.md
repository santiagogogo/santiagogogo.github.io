---
layout:     post
title:      kafka学习
date:       2020-11-08
author:     Santiago
catalog: false

---
#### kafka位移
1. 位移主题主要保存消费者的位移信息，即消费的位置
2. 老版本依赖zk，但是zk不适合高频写操作，而kafka天然支持高频写和持久化
3. 位移主题的key:groupiid+topic+partition
4. 消息格式：1）保存消费者位移数据，2）保存消费组信息的消息，3）删除消费组过期位移信息和删除组信息
5. 位移主题是自动创建的，支持自动和手动提交，默认分区50，副本3
6. 删除过期位移信息策略： compact-单个key只保存最新的位移信息