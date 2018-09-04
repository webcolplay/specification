# JavaScript 编码规范

## 变量

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 禁止删除变量 | no-delete-var ||
| 禁止变量声明覆盖外层作用域的变量 | no-shadow ||
| 禁止多次声明同一变量 | no-redeclare ||
| 变量名不允许是js关键字/保留字 | no-shadow-restricted-names ||
| 禁用未声明的变量 | no-undef ||
| 不允许初始化变量值为undefined | no-undef-init ||
| 禁止未使用过的变量 | no-unused-vars ||
| 禁止变量定义前使用 | no-use-before-define ||
| 使用 let 或 const | no-var ||
| const定义不会被重新赋值的变量 | prefer-const ||
| 不允许改变用const声明的变量 | no-const-assign ||
| 不允许修改类声明的变量 | no-class-assign ||

## 分号

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 禁用不必要的分号 | no-extra-semi ||
| 分号前后是否有空格 | semi-spacing ||
| 总是使用分号 | 无 ||

## 函数

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 禁止在嵌套的语句块中出现 function 声明 | no-inner-declarations ||
| 禁止对 function 声明重新赋值 | no-func-assign ||
| 禁止 function 定义中出现重名参数 | no-dupe-args ||
| 禁止在RegExp构造函数中出现无效的正则表达式 | no-invalid-regexp ||
| 禁止将全局对象当作函数进行调用 | no-obj-calls ||
| 调用无参构造函数时带括号 | new-parens ||

## 异常

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 禁止对catch子句中的异常重新赋值,但可以自定义异常 | no-ex-assign ||

## eval

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 禁用 eval() | no-eval ||
| 禁止使用类似eval的方法 | no-implied-eval ||

## with

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 禁用 with 语句 | no-with ||

## this

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 禁止 this 关键字在类或类对象之外出现 | no-invalid-this ||
| 当获取当前执行环境的上下文时，强制使用一致的命名 | consistent-this ||
| 禁止在构造函数中，在调用 super() 之前使用 this 或 super | no-this-before-super ||

## Array 和 Object 直接量

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 禁用稀疏数组 | no-sparse-arrays ||
| 禁用Array构造函数 | no-array-constructor ||
| 禁用 Object 的构造函数 | no-new-object ||


## 修改内置对象的原型

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 不要修改内置对象，如 Object.prototype 和 Array.prototype 的原型 | 无 ||


## === 和 !==

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 使用 === 和 !== | eqeqeq ||


## ES6、7、8


| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
|构造函数中有super()的调用|constructor-super||
|禁止修改类声明的变量|no-class-assign||
|类成员中出现重复的名称|no-dupe-class-members||
|使用模板字面量而非字符串连接|prefer-template||
|对象字面量中方法和属性使用简写语法|object-shorthand||


## 命名

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 常量使用大写字母定义，单词之间使用下划线"_"连接 | 无 ||
| 私有属性,变量和方法名应该以下划线"_"开头 | 无 ||
| 构造函数首字母大写 | new-cap ||


## 代码格式化

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 禁止在字符串和注释之外不规则的空白 | no-irregular-whitespace ||
| 使用一致的缩进 | indent ||
| 在对象字面量的属性中键和值之间使用一致的间距 | key-spacing ||
|在关键字前后使用一致的空格|keyword-spacing||
|使用一致的换行风格|linebreak-style||
| 在注释周围有空行 | lines-around-comment ||
|操作符周围有空格|space-infix-ops||
|一元操作符前后使用一致的空格|space-unary-ops||
|圆括号内使用一致的空格|space-before-function-paren||
|块之前使用一致的空格|space-before-blocks||
|强制分号的位置|semi-style||
|禁用行尾空格|no-trailing-spaces||
| 箭头函数体使用大括号 | arrow-body-style ||
|箭头函数的参数使用圆括号|arrow-parens||
|箭头函数的箭头前后使用一致的空格|arrow-spacing||



## 注释

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 强制在注释中 // 或 /* 使用一致的空格 | space-before-function-paren ||
|推荐使用JSDOC注释|||


## 引号

| 描述 | 对应ESLint规则 | 结果 |
|------|------|------|
| 使用 ' 优于 " | quotes ||
|对象字面量属性名称用引号括起来|quote-props||
