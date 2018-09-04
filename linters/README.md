# 编码规范对应的ESLint 和 stylelint配置文件

## VSCode 配置方案

1. VSCode搜索ESLint并安装ESLint插件
1. VSCode搜索stylelint并安装stylelint插件
1. 在工作区或者用户区加入如下配置

```
    "javascript.validate.enable": false,
    "eslint.validate": ["javascript", "javascriptreact", { "language": "html", "autoFix": true }],
    "eslint.autoFixOnSave": true,
    "css.validate": false,
    "less.validate": false,
    "scss.validate": false
``` 


## stylelint关闭规则

```
// 在 CSS 中使用特定的注释临时关闭部分代码的所有检验规则
/* stylelint-disable */
a {}
/* stylelint-enable */``
 ```

```
// 在 CSS 中使用特定的注释临时关闭部分代码的指定检验规则
/* stylelint-disable selector-no-id, declaration-no-important  */
#id {
    color: pink !important;
}
/* stylelint-enable */
```

```
#id {
    height: 200px; /* stylelint-disable-line */
    color: pink !important; /* stylelint-disable-line declaration-no-important */
}
```

```
// 注释在下一行上关闭规则
#id {
    /* stylelint-disable-next-line declaration-no-important */
    color: pink !important;
}
```