---
marp: true
theme: default
size: 16:9
paginate: true
math: katex
---

<style>
/* ===== 全局 ===== */
section {
  font-size: 21px;
  display: flex;
  flex-direction: column;
}

h1 { font-size: 38px; }
h2 { font-size: 26px; color: #1565c0; border-bottom: 2px solid #1565c0; padding-bottom: 0.15em; margin-bottom: 0.6em; }
h3 { font-size: 22px; color: #333; }

/* ===== 封面 ===== */
section.cover {
  background: linear-gradient(135deg, #107df97f 0%, #17216e 100%);
  color: white;
  justify-content: center;
  align-items: center;
  text-align: center;
}
section.cover h1 { color: white; font-size: 44px; border: none; margin-bottom: 0.3em; }
section.cover h2 { color: #90caf9; font-size: 34px; border: none; font-weight: normal; }
section.cover p  { color: #bbdefb; font-size: 24px; }

/* ===== 节标题页 ===== */
section.section-title {
  background: #e3f2fd;
  justify-content: center;
  align-items: center;
  text-align: center;
}
section.section-title h2 { font-size: 36px; color: #1565c0; border: none; }

/* ===== 双栏 ===== */
.cols { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5em; align-items: start; }
.cols-64 { display: grid; grid-template-columns: 3fr 2fr; gap: 1.5em; align-items: center; }

/* ===== 提示框 ===== */
.box-find  { background:#e8f5e9; border-left:4px solid #388e3c; padding:0.6em 1em; border-radius:4px; margin:0.5em 0; }
.box-note  { background:#e8f4fd; border-left:4px solid #1976d2; padding:0.6em 1em; border-radius:4px; margin:0.5em 0; }
.box-limit { background:#fff3e0; border-left:4px solid #f57c00; padding:0.6em 1em; border-radius:4px; margin:0.5em 0; }

/* ===== 底部注释 ===== */
.note { font-size:13px; color:#888; margin-top:auto; padding-top:0.4em; border-top:1px solid #e0e0e0; }

/* ===== 页码 ===== */
section::after { font-size: 14px; color: #aaa; }
</style>

<!-- _class: cover -->
<!-- _paginate: false -->

# 论文标题

## A Subtitle in English

作者姓名 · 单位名称

会议/期刊 · 年份

---

<!-- _class: section-title -->
<!-- _paginate: false -->

## 01 · 引言

---

## 研究背景与问题

**研究背景**

- 背景一：简要说明
- 背景二：简要说明

**研究问题**

> 本文试图回答：……在多大程度上影响了……？

<div class="box-note">

💡 **研究贡献：** 本文的三点贡献……

</div>

---

<!-- _class: section-title -->
<!-- _paginate: false -->

## 02 · 数据与方法

---

## 计量模型

**基准模型：**

$$
y_{it} = \alpha + \beta \cdot \text{Treat}_{it} + \gamma X_{it} + \mu_i + \lambda_t + \varepsilon_{it}
$$

其中：
- $y_{it}$：被解释变量
- $\text{Treat}_{it}$：处理变量
- $X_{it}$：控制变量向量
- $\mu_i$、$\lambda_t$：个体和时间固定效应

---

## 数据说明

<div class="cols">
<div>

**数据来源**

- 数据集一：简要说明
- 数据集二：简要说明
- 样本期：XXXX–XXXX 年
- 样本量：N = XXXX

</div>
<div>

**关键变量描述性统计**

| 变量 | 均值 | 标准差 | 观测值 |
|------|------|--------|--------|
| y    | 0.42 | 0.18   | 1,200  |
| x1   | 3.21 | 1.05   | 1,200  |
| x2   | 0.58 | 0.23   | 1,200  |

</div>
</div>

---

<!-- _class: section-title -->
<!-- _paginate: false -->

## 03 · 实证结果

---

## 基准回归结果

<div class="cols-64">
<div>

**表 1：基准回归**

| | (1) | (2) | (3) |
|--|-----|-----|-----|
| Treat | 0.23*** | 0.19*** | 0.18*** |
|       | (0.04)  | (0.04)  | (0.04)  |
| 控制变量 | 否 | 是 | 是 |
| 固定效应 | 否 | 否 | 是 |
| $R^2$  | 0.21 | 0.38 | 0.52 |

<div class="note">注：括号内为聚类标准误（个体层面）。*** p<0.01。</div>

</div>
<div>

<div class="box-find">

✅ **核心发现：** 处理效应在控制固定效应后仍显著为正，系数约为 0.18。

</div>

<div class="box-limit">

⚠️ **稳健性：** 已通过安慰剂检验和平行趋势检验。

</div>

</div>
</div>

---

<!-- _class: section-title -->
<!-- _paginate: false -->

## 04 · 结论

---

## 结论与政策含义

**主要结论**

1. 结论一：简要说明
2. 结论二：简要说明
3. 结论三：简要说明

**政策含义**

- 含义一
- 含义二

**局限与展望**

- 当前局限
- 未来研究方向

---

<!-- _class: cover -->
<!-- _paginate: false -->

# 谢谢！

欢迎批评指正

作者邮箱：your@email.com
