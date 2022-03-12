# 格式

## 标题

标题即提交信息的第一行。

标题应**简短**地描述这次**提交的内容**。

与 [FkGitCommitMsgStd](https://github.com/ForkKILLET/FkGitCommitMsgStd) 不同的是，本标准不推荐将描述符写入标题。

关于描述符，详见 [FkGitCommitMsgStd](https://github.com/ForkKILLET/FkGitCommitMsgStd)，这里不加赘述。

~~如果是重大更新，可以考虑把描述符加入标题，并将其放在提交内容之前。~~

~~举例：`VER 1.0.0 Initial`，`VER 2.0.0 Typescript Refactor`，`VER 3.0.0 ISS #7 Xyz Update`。 ~~

Update: 现在不允许 PR 时修改版本号，所有版本均在合并后统一修改。

版本号 `Major.Minor.Release` 修改规则：

1. 公认的大修改改 Major 版本，如 Commit Std Update；
2. 新增模块修改 Minor 版本，如 Virtual Participation；
3. 修复 Bug 修改 Release 版本，如 Fix cdn；
4. 虽然允许，但**非常**不建议刻意将多个 bug 修改 squash 成一个 commit。

## 内容

内容的应当是至少一个**项目**组成的。

每个项目的第 1 个字符是**操作**，如下表。

字符 | 解释
---- | ----
`-`  | 添加特性
`x`  | 删减特性
`!`  | 重大特性
`*`  | 修改
`^`  | 修复
`$`  | 重构

每个项目的第 2 个字符是**类型**，如下表。

字符 | 解释
---- | ----
`-`  | 特性
`?`  | 文档
`#`  | 依赖
`<`  | 代码风格
`>`  | 命令
`M`  | 模块
`H`  | 钩子
`@`  | GitHub Action

每个项目的第 3 个字符是一个空格，随后是描述。

每个项目可以包含子内容。  
子内容可以是：子项目或**具体描述**。

具体描述的第一个字符是**描述类型**，如下表。

描述类型后的内容是**描述内容**，在表意明确的情况下，可以且推荐使用中文。

字符 | 解释
---- | ----
`:`  | 普通说明
`!`  | 已确认的 bug 说明
`&`  | 参考说明。

子内容应当正确缩进，见举例：

```plain
-- 添加一个功能。
 : 这个功能表现为某某某某。
-- 又一个功能。
   *- 改进了某某某某。
   -- 可以这样了。
   -- 可以那样了。
    : 就是那种，很特别的那种。
   $- 某某功能改用某某实现了。  
-> my-cmd qwq
 : 可以这样调用了。
 ! 但是不能 `qvq`。
^> my-cmd qvq
 : 修了个锅。
-< 用空格代替了 tab。
-? 更新了文档
 : 在 Wiki 页面
   -- 中文
   *- English
-# yarn
   -- eslint
   x- commander
```

