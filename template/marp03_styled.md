---
marp: true
theme: default
size: 16:9
paginate: true
header: "课程名称"
footer: "姓名  ·  日期"
math: katex
---

<style>
section {
  font-size: 22px;
}
h1 {
  font-size: 40px;
  color: #1a237e;
}
h2 {
  font-size: 30px;
  color: #283593;
  border-bottom: 2px solid #3949ab;
  padding-bottom: 0.2em;
}
/* 提示框 */
.box-note  { background:#e8f4fd; border-left:4px solid #2196F3; padding:0.7em 1em; border-radius:4px; margin:0.5em 0; }
.box-warn  { background:#fff8e1; border-left:4px solid #FFC107; padding:0.7em 1em; border-radius:4px; margin:0.5em 0; }
.box-tip   { background:#e8f5e9; border-left:4px solid #4CAF50; padding:0.7em 1em; border-radius:4px; margin:0.5em 0; }
/* 小字注释 */
.note {
  font-size: 14px;
  color: #888;
  margin-top: auto;
  padding-top: 0.4em;
  border-top: 1px solid #e0e0e0;
}
</style>

<!-- _paginate: false -->
<!-- _header: "" -->
<!-- _footer: "" -->

# 课程标题

## 副标题

姓名 · 单位 · 日期

---

## 带样式的内容页

正文字号已调整为 22px，标题有颜色和下划线。

<div class="box-note">

💡 **提示：** 这是一个蓝色提示框，用 `<div class="box-note">` 调用。

</div>

<div class="box-warn">

⚠️ **注意：** 这是一个黄色警告框，用 `<div class="box-warn">` 调用。

</div>

---

## 数学公式示例

行内公式：质能方程 $E = mc^2$

独立公式块：

$$
\hat{\beta} = (X'X)^{-1}X'y
$$

多行推导：

$$
\begin{aligned}
\text{SSR} &= \sum_{i=1}^n (y_i - \hat{y}_i)^2 \\
           &= (y - X\hat{\beta})'(y - X\hat{\beta})
\end{aligned}
$$

---

## 带底部注释的页面

主要内容写在这里。

- 数据结论一
- 数据结论二

<div class="note">
注：数据来源于《中国统计年鉴》（2023）。样本期：2000–2022 年。
</div>
