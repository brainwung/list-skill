---
name: list-skill
description: 构建适配不同屏幕宽度的移动端数字序号摘要列表 UI。适用于列表样式、序号列表、摘要列表、移动端 H5 列表，以及每条内容以前置数字序号开头、后接简洁摘要文字、末尾跟随 arrow-right-bold 箭头图标的场景。
---

# 列表样式 Skill

按这个 skill 生成移动端摘要列表时，只保留必要结构和样式，不添加未要求的装饰、卡片、渐变、阴影或交互。

## 样式规范

- 页面不限制固定宽度，左右 padding 各 15px。
- 模块标题可选：18px / 1.2 / bold，标题与列表间距 18px。
- 标题下划线：高度 3px，颜色 `#e62828`，最大宽度 36px；标题较短时跟随标题宽度，标题较长时只覆盖前 36px，例如 4 个中文字标题只给前 2 个字下划线。
- 两个模块之间可用 1px 分隔线，颜色 `#eeeeee`；是否使用取决于页面是否有多个大模块。
- 列表项间距 18px。
- 每条结构：两位数字序号 + 摘要文字 + 箭头图标。
- 序号：`01`、`02`、`09`、`10` 格式，`D-DIN-PRO-700-Bold`，16px / 27px / 700，固定 17px 宽，居中。
- 序号与摘要文字间距 9px。
- 摘要文字：15px / 1.8，颜色 `#333333`。
- 箭头：使用 `icons/arrow-right-bold.svg`，16px × 16px，紧跟句尾，`margin-left: -3px`，`vertical-align: -3px`。

## 资源

- 序号字体：`fonts/D-DIN-PRO-700-Bold.otf`
- 箭头图标：`icons/arrow-right-bold.svg`
- 参考模板：`reference.html`

## 实现要点

1. 先定义 `@font-face`，再使用序号字体。
2. 优先使用 `ol`，但重置默认列表样式，自行渲染可见序号。
3. 行布局使用 `grid-template-columns: 17px minmax(0, 1fr)` 和 `column-gap: 9px`。
4. 摘要文字和箭头保持同一段内联流，让箭头跟随最后一行文字。
5. 标题下划线用伪元素实现，例如 `width: min(100%, 36px)`，不要用整段 `border-bottom`。
