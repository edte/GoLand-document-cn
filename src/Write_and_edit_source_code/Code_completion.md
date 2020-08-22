## 代码补全

## Hippie 补全

## Postfix code completion﻿

通过使用 Postfix 模板，你可以在表达式后使用 `.` ，选择对应的模板，会根据表达式的 type 和 context 把语句转换为另一个格式。GoLand 已经内置了一些 postfix 补全模板，你也可以使用其他语言的模板。你可以复制，启动，禁用这些模板。(自带的模板有些也能改名字，有的能查看具体的模板语法，都不能删除。)

![img](https://img2020.cnblogs.com/blog/1823594/202007/1823594-20200728184931817-1092003906.png)

> - 要查看所有 postfix 模板，在 `Settings/Preferences/Editor/General/Postfix Completion` 中查看
> - 选择 `Tab`, `Space`, 或 `Enter` 使用 postfix 模板

### 使用 postfix 补全语句

输入一个表达式，然后输入 `.`, 如 `.if:`

```
func m(b bool) {
b.if
}
```

然后在弹出的窗口中选择 if

![img](https://img2020.cnblogs.com/blog/1823594/202007/1823594-20200728185618553-1594248091.gif)

要禁用某个模板，在 `Settings/Preferences/Editor/General/Postfix Completion` 对着对应的模板把勾去掉即可。

你可以编辑自带的一些模板，例如，把模板变短一些，或变长一些（有些不能改，有的只能看，有的能改名）

> postfix 补全选项是 basic completion suggestions list （基本补全）的一种，要查看当前可以使用什么 postfix 模板，可以按 `Ctrl+J`

### 创建自定义的模板

1. 进入 `Settings/Preferences/Editor/General/Postfix Completion`
2. 在工具栏中选择 ![img](https://img2020.cnblogs.com/blog/1823594/202007/1823594-20200728185835379-1794893589.png)
3. 选择适用的语言，这里选择 go
4. 输入 `key`，这个是在 `.` 后调用模板时需要使用的符号，然后选择适用于哪些语句

![img](https://img2020.cnblogs.com/blog/1823594/202007/1823594-20200728190115841-942225835.png)

然后按这个格式输入目标格式 `$EXPR$ <target_expression>`， 例如，`$EXPR$ != nil`

在模板中，可以使用这两个环境变量，`$EXPR$` 和 `$END$`

- `$EXPR$` 捕捉 `.` 前的表达式
- `$END$` 定义使用模板后光标的位置

`Apply to the topmost expression` 这个选择框用来忽略范围，用在表达式整体中。所以你不必要每次都选择模板的范围。

![img](https://img2020.cnblogs.com/blog/1823594/202007/1823594-20200728185549042-1850754258.gif)

> 这里放个私货，笔者也写过一篇文章介绍 postfix completion 的，介绍了所有的模板，和自定义的一些常见模板，可以看看 [address](https://edte.github.io/GoLand-documentation-cn/write_and_edit_source_code/code_completion.html)

## tags 和 attributes 的补全