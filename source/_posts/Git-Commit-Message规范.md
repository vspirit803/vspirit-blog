---
title: Git Commit Message规范
date: 2020-03-23 22:38:37
categories:
- git
tags: 
- 规范
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
Commit Message包括空行分隔的三个部分：header，body和footer。

### Revert (特殊情况)
若此commit回滚此前的commit，则header部分必须以**revert:** 开头，后跟回滚commit的header。
Body部分格式为```This reverts commit <hash>.```hash为回滚commit的sha标识。

### Header
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

### Body
body是对此commit的详细描述，有两点要注意
1. 跟**subject**部分一样，使用第一人称现在时态
2. 要写明改动的原因以及与此前行为的对比

### Footer
* **breaking changes**
若有与此前不兼容的变动，需要以**BREAKING CHANGE:** 开头，写明变动描述、原因与迁移方法。如：
```
BREAKING CHANGE: isolate scope bindings definition has changed and
    the inject option for the directive controller injection was removed.
    
    To migrate the code follow the example below:
    
    Before:
    
    scope: {
      myAttr: 'attribute',
      myBind: 'bind',
      myExpression: 'expression',
      myEval: 'evaluate',
      myAccessor: 'accessor'
    }
    
    After:
    
    scope: {
      myAttr: '@',
      myBind: '@',
      myExpression: '&',
      // myEval - usually not useful, but in cases where the expression is assignable, you can use '='
      myAccessor: '=' // in directive's template change myAccessor() to myAccessor
    }
```
* **关闭Issue**
若修复了某个issue提出的bug，则需以**Closes** 开头列出issue，例如
```
Closes #234
```
或者关闭多个issue
```
Closes #123, #245, #992
```
## 参考文献
1. [AngularJS Git Commit Message Conventions](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#heading=h.uyo6cb12dt6w)
2. [Commit message 和 Change log 编写指南](https://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html) By 阮一峰