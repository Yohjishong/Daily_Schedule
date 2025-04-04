# 25年3.29-4.5

整体规划：

首要任务是完成中期报告和中期答辩，复现MMA-Diffusion代码并修正，修正方向考虑两个，一个是替换掉CLIP 的text_encoder为hunyuan的，中途下错了模型，混元github跳转到的HF模型居然是错的(难崩，也可能是我不会用)，其次是构建高质量的Prompt，MMA-Diffusion作为CVPR的文章，在这上面敷衍我也就容忍了，不过这些原文的数据集的prompt质量实在是有点太低了吧。

本周主线是弄明白并实践知乎blog《从啥也不会到DeepSpeed-分布式训练的学习过程总结》https://zhuanlan.zhihu.com/p/688873027。大佬的文章特别好，看完了通信原语，DP，TP，PP的一些基本算法，也复现了ring all-reduce和失败复现了Parameter-Server，搞不懂通信呀搞不懂，一直死锁。

日常是刷了30道leetcode为后续找实习做准备，同时也在手撕一些经典的积木，先手撕了MHA，GQA，RMS这种比较简单的part。其次就是保持健身，体重也从75下降到了74。

这是自己开始记录自己每周并打卡的第一周，下一周希望能多看点paper，开启微调尝试和学会使用VLLM。(加油)

这个BYD数据集真是把我害惨了，太难搞了，找7b的deepseek生成，本来想自动化，但是7b不太聪明，经常回复一些难以自动化的文本，因此只好采用纯粹的人工选取，有些质量也很低。(来自4.4晚上十点的自己)

## 3.29

- [x] 8.40-10.20: leetcode五道题
- [x] 10:30-11:20: 看MMA-Diffusion文本攻击代码(没看完)
- [x] 13:40-14:50: 继续看MMA-Diffusion文本攻击代码(没看完)
- [x] 15:00-16:00: 健身
- [x] 16:30-17:30: 看完MMA-Diffusion文本攻击代码
- [x] 18:30-20:00: 弄明白gradient checkpoint
- [x] 20:20-20:50: 手写MHA代码

## 3.30

- [x] 9.30-11:10: leetcode五道题
- [x] 12:40-14:20: 深入MMA-Diffusion攻击全流程
- [x] 14:30-15:30: 健身
- [x] 15:40-17:00: 尝试并行化MMA-Diffusion攻击(失败)
- [x] 22:30-23:30: 弄明白通信原语并用torch实现

## 3.31

- [x] 9.10-10:00: leetcode五道题
- [x] 10:00-11:00: 并行化MMA-Diffusion攻击
- [x] 12:30-1:30: 健身
- [x] 18:00-19:20: 弄明白Ring All-reduce并用torch实现
- [x] 20:00-20:30: 南洋理工开会(不去了)
- [x] 20:30-21:00: 弄明白Parameter Server架构

## 4.1

- [x] 10.50-11:25: leetcode三道题
- [x] 12:40-13:10: leetcode两道题
- [x] 13:20-14:30: 手搓Parameter Server demo(失败)
- [x] 14:50-16:00: 健身
- [x] 16:10-17:00: 用hunyuan的text_encoder跑起来越狱攻击(下错权重了)
- [x] 17:00-17:30: 弄明白Gpipe
- [x] 19:00-20:00: 用hunyuan的text_encoder跑起来越狱攻击
- [x] 20:25-20:50: 弄明白PipeDream

## 4.2

- [x] All_day: 中期报告

## 4.3

- [x] 10.00-11:40: leetcode五道题
- [x] 14:20-15:00: 弄明白Megatron的横切和纵切
- [x] 15:00-16:20: 健身
- [x] 16:20-17:30: 整理blog
- [x] 18:20-19:00: 弄明白Megatron的三种并行
- [x] 19:00-20:30: 失败的hexo搭建
- [x] 20:30-21:20: 手写RMS，LN，GQA
- [x] 11:30-12:30: 构建毕设数据集

## 4.4

- [x] 9.50-10:50: leetcode五道题
- [x] 12:40-14:30: 弄明白DeepSpeed(DP 和 R)
- [x] 14:30-16:00: 健身
- [x] 16:10-16:50: 弄明白DeepSpeed(offload 和 infinity(看不懂))
- [x] 17:00-17:20: 研究VLLM推理本地deepseek 7b构建prompt
- [x] 18:20-22:00: 利用deepseek 7b构建unsafe 数据集