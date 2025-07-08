---
title: 过去小一年
date: 2025-07-08
category: thoughts
---

## 1. What happened

我深度参与了一个startup, 这个公司想用LLM来做教育咨询,帮助学生申请大学提供全程指导,制定学习计划,帮助撰写申请材料,撰写简历,选择学校等. 在我参与之前,这个公司试图用一个python task build前端和后端, 所有的东西都自己handle. 我重新设计了架构,让这个公司的eng能开始可持续的发展.

我做的是把前后端分离, 用k8s和docker来把所有的feature模块分成micro service, 用一个golang写的gateway负责把http转换成grpc,然后feature service和gateway之间用grpc来通信. 前端用react 和react native来写web和app.数据库从sqllite换成了postgresql. 用户注册和验证用aws cognito, 这是一个比较简单的架构,在prototype p0阶段比较适合不同水平的几个人用适合自己pace的方式快速build一个系统,

这其实是一个比较典型的前后端分离系统,用编译语言golang来写一个相对solid的关键节点,剩下的就糙快猛的搭起来. 这个系统里之前的llm部分是用ReAct实现,我本想在这一部分重新设计一下,但是因为时间没有继续. 

我原来的计划里， 在新系统处于稳定状态后，LLM会从两个方向进行提升，
1. 立足现有系统，提高输出质量
- 使用agent,从2024年底开始,agentic架构证明可以在application层面提供了巨大的灵活性,在提高llm的输出质量上使用agentic framework其实有很多经验性的东西， 比较简单一点的可以用agentic架构来协调既有的feature模块和llm问答，让系统的输出确定性提高，
- 在prompt里面提高质量, 简单的技巧比如说控制promot关键词的质量，如何leverage token数量和质量，aggressively使用few shots从不同维度提高输出质量.
2. 重构系统,积极使用logic reasoning 和memory
- Memory, 让用户体验到application能记住他并定制化建议,需要为每位用户提供长期积极Long Term Memory,记住chat history需要summarize, extraction和embedding.对于特定topic的记忆和使用,要使用Retrieval Augmented Generation.这方面要考虑使用向量数据库,从relationa db里query chat history再发送给llm再使用太过于笨重
- Reasoning. 首先要调整到Multi step reasoning, ReAct agent到CoT, self correction, 用reasoning来协调agent模块.
- 使用local model加入PEFT和RLHF,这里面具体的想法就不在这里提了. 


我决定在架构完成并deliver了一个用户管理和payment系统之后退出这个startup, 没有拿任何cash和equity. 没有对LLM部分提出任何建议.

## 2. What I learned
每次在不同的startup都能得到不同的经验. 这次的经验是, 哪怕是非常信任的朋友,还是应该把comp metric在开始之前说清楚,把退出机制说好并留下trace. 

因为我自己的情况也变化比较多, 从刚开始积极involve希望在三个月内看到效果, 到时间无法平衡, 对项目整体失去兴趣, 时间沉没成本指数增加,和之前的startup朋友聊过之后决定完全放弃1%的equity.

和上一次的startup相比, 觉得养个小朋友之后对时间割裂度比想象中大了2个数量级, 之前对时间管理的经验已经完全不适用现在的情况. 这也是对公司founder expectation management做的不好的地方.

## 3. What next
GenAI在过去的半年有了过去两年中最快速的发展,整个世界又在开始迅速调整了.我下一步会在GenAI方向继续自己的职业,不会再做纯码农. 有很多需要rampup学习和调整的地方,会单开一篇记录一下.
