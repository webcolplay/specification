# CSS编码规范

## 通用约定

- 使用Class选择器，不使用ID选择器
- 类命名使用 "-" 作为单词界定符，命名中不含大写，不使用驼峰和下划线
- 不使用原子类定义样式 （eg: .ft14, .mr20）
- 涉及引用资源样式、字符串界定，采用单引号
```css
@import url('./common.css');
font-family: 'Hiragino Sans GB';
background-image: url('../img/a.jpg');
.input[type='text'] {}
```

## 属性书写顺序

1. Positioning (position/left/right/top/bottom/z-index)
2. Float (float)
3. Box Model (display/box-sizing/margin/width/height/padding/border/border-radius/overflow)
4. Transition/Animation/Transform
5. Typography (font/line-height/text-align/color/text-indent/text-shadow/text-overflow/text-transform/white-space/word-break/word-spacing)
6. Visual & Others (background/opacity/cursor)


## 代码格式化

| 描述 | 对应styleLint规则 | 结果 |
|------|------|------|
|缩进|indentation|2制表符长度|
|限制允许嵌套的深度|max-nesting-depth|4|
|禁止低优先级的选择器出现在高优先级的选择器之后|no-descending-specificity||
|禁止出现重复的选择器|||
|禁止行尾空白|no-eol-whitespace||
|禁止多余的分号|no-extra-semicolons||

## 注释
| 描述 | 对应styleLint规则 | 结果 |
|------|------|------|
|禁用CSS双斜线注释| no-invalid-double-slash-comments||
|注释之前有空行|comment-empty-line-before||
|禁止空注释|comment-no-empty||


## Value

| 描述 | 对应styleLint规则 | 结果 |
|------|------|------|
|禁止给值添加浏览器引擎前缀|value-no-vendor-prefix||

## Color

| 描述 | 对应styleLint规则 | 结果 |
|------|------|------|
|十六进制颜色大小写|color-hex-case|大写|
|十六进制颜色使用缩写|color-hex-length||


## Font

| 描述 | 对应styleLint规则 | 结果 |
|------|------|------|
|字体名称使用引号引起来|font-family-name-quotes||
|使用数字font-weight值|font-weight-notation||


## Number

| 描述 | 对应styleLint规则 | 结果 |
|------|------|------|
|禁止小于 1 的小数的前导0|number-leading-zero||
|禁止数字中的拖尾0|number-no-trailing-zeros||


## String

| 描述 | 对应styleLint规则 | 结果 |
|------|------|------|
|字符串使用单引号|string-quotes||

## Length

| 描述 | 对应styleLint规则 | 结果 |
|------|------|------|
|长度为0时，禁止使用单位|length-zero-no-unit||

## property

| 描述 | 对应styleLint规则 | 结果 |
|------|------|------|
|禁止在简写属性中使用冗余值|shorthand-property-no-redundant-values||
|禁止属性使用浏览器引擎前缀|property-no-vendor-prefix||
