---
title: border-bottom-color
slug: Web/CSS/border-bottom-color
---
{{CSSRef}}

## 概述

**`border-bottom-color`** 属性设置一个元素底部边框的颜色。应当指出，在多数情况下，CSS 简写属性 {{cssxref("border-color")}} 或 {{cssxref("border-bottom")}} 更方便实用。

{{cssinfo}}

## 语法

```css
border-bottom-color: yellow;
border-bottom-color: #F5F6F7;
```

### 值

- `<color>`
  - : 一个描绘底边的颜色的 CSS {{cssxref("&lt;color&gt;")}} 值。
- `inherit`
  - : 一个代表父元素底边颜色的关键字（可能和 `border-bottom-color` 默认值不同）

### 正式语法

{{csssyntax}}

## 示例

### 一个带有边框的简单 div

#### HTML 内容

```html
<div class="mybox">
  <p>This is a box with a border around it.
     Note which side of the box is
     <span class="redtext">red</span>.</p>
</div>
```

#### CSS 内容

```css
.mybox {
  border: solid 0.3em gold;
  border-bottom-color: red;
  width: auto;
}

.redtext {
  color: red;
}
```

#### 结果

{{EmbedLiveSample('A_simple_div_with_a_border')}}

## 规范

{{Specifications}}

## 浏览器兼容性

{{Compat("css.properties.border-bottom-color")}}

## 另见

- 边框相关的 CSS 简写属性 {{Cssxref("border")}}, {{Cssxref("border-bottom")}} 和 {{Cssxref("border-color")}} 。
- 用于其它边框颜色相关的 CSS 属性： {{Cssxref("border-right-color")}}, {{Cssxref("border-top-color")}}, 和 {{Cssxref("border-left-color")}} 。
- 同样用于底边的其它边框相关的 CSS 属性： {{cssxref("border-bottom-style")}} 和 {{cssxref("border-bottom-width")}} 。
