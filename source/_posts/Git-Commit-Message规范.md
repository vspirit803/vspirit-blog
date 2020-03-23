---
title: Git Commit Message规范
date: 2020-03-23 22:38:37
tags:
---

## 规范Git Commit Message的作用
* 自动生成Change Log
* 便于略过不重要的commit，快速获取信息
* 浏览提交历史的时候提供更多信息

## Commit Message的格式
```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```
为了便于阅读，保持美观，Commit Message每行长度不得超过100个字。
Commit Message包括空行分隔的三个部分：header，body和footer
### header
header包括三个部分type、scope和subject
* **type（必填）**
表示commit的类型，只允许以下7个
  - feat：新功能
  - fix：bug修复
  - docs：文档修改
  - style：代码格式
  - refactor：重构
  - test：增加测试
  - chore：构建或相关工具链改动

* **scope（选填）**
表示commit影响的范围，如逻辑层，数据层、表现层等等。 

* **subject（必填）**
关于commit的简短描述
  - 动词开头，第一人称现在时态
  - 首字母小写
  - 不要以.结尾