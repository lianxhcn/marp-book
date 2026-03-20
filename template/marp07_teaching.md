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
  font-size: 22px;
  display: flex;
  flex-direction: column;
  background: #fafafa;
  padding: 44px 56px;
}
h1 { font-size: 36px; color: #212121; }
h2 {
  font-size: 27px;
  color: #ffffff;
  background: #1565c0;
  margin: -44px -56px 1em -56px;
  padding: 0.45em 56px;
  letter-spacing: 0.02em;
}

/* ===== 封面 ===== */
section.cover {
  background: #1565c0;
  color: white;
  justify-content: flex-end;
  padding: 60px 80px;
}
section.cover h1 { color: white; font-size: 44px; border: none; line-height: 1.3; }
section.cover .course { font-size: 18px; color: #90caf9; margin-bottom: 2em; }
section.cover .info   { font-size: 17px; color: #bbdefb; line-height: 2.2; border-top: 1px solid rgba(255,255,255,0.2); padding-top: 1em; }

/* ===== 板书区域 ===== */
.board {
  background: #1b2631;
  color: #e8f5e9;
  border-radius: 8px;
  padding: 1em 1.4em;
  font-family: "Courier New", monospace;
  font-size: 19px;
  line-height: 1.8;
  margin: 0.5em 0;
}
.board .comment { color: #546e7a; font-style: italic; }
.board .hl      { color: #80cbc4; font-weight: bold; }
.board .result  { color: #ffcc02; }

/* ===== 逐步揭示（Step）===== */
.step-row {
  display: grid;
  grid-template-columns: 40px 1fr;
  gap: 0.3em 0.8em;
  align-items: start;
  margin: 0.3em 0;
}
.step-num {
  width: 36px; height: 36px;
  background: #1565c0;
  color: white;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-weight: bold; font-size: 16px;
  flex-shrink: 0; margin-top: 2px;
}
.step-num.done  { background: #388e3c; }
.step-num.now   { background: #e65100; }

/* ===== 对比框（左错右对）===== */
.compare {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1em;
}
.wrong { background:#fce4ec; border-left:4px solid #c62828; padding:0.7em 1em; border-radius:0 6px 6px 0; }
.right { background:#e8f5e9; border-left:4px solid #388e3c; padding:0.7em 1em; border-radius:0 6px 6px 0; }
.wrong strong { color: #c62828; }
.right strong { color: #388e3c; }

/* ===== 知识点框 ===== */
.def {
  background: #e3f2fd;
  border: 1px solid #90caf9;
  border-radius: 6px;
  padding: 0.7em 1.1em;
  margin: 0.5em 0;
}
.def .label { font-size: 13px; color: #1565c0; font-weight: bold; letter-spacing: 0.05em; margin-bottom: 0.3em; }

/* ===== 小字注释 ===== */
.note { font-size: 13px; color: #90a4ae; margin-top: auto; padding-top: 0.5em; border-top: 1px solid #e0e0e0; }
</style>

<!-- _class: cover -->
<!-- _paginate: false -->

<div class="course">计量经济学 · 第 5 讲</div>

# 工具变量法

<div class="info">
主讲：姓名　｜　单位：某某大学<br>
学期：2024 年秋
</div>

---

## 本讲内容

<div class="step-row">
<div class="step-num done">✓</div>
<div>**内生性问题回顾**：为什么 OLS 会失效？</div>
</div>

<div class="step-row">
<div class="step-num done">✓</div>
<div>**工具变量的直觉**：找一个"替代"变量</div>
</div>

<div class="step-row">
<div class="step-num now">→</div>
<div>**IV 的两个条件**：相关性 + 外生性（本讲重点）</div>
</div>

<div class="step-row">
<div class="step-num">4</div>
<div>**2SLS 估计步骤**：两阶段最小二乘</div>
</div>

<div class="step-row">
<div class="step-num">5</div>
<div>**弱工具变量检验**：F 统计量规则</div>
</div>

---

## 问题：为什么 OLS 会失效？

**考虑如下模型：**

$$
\ln w_i = \alpha + \beta \cdot \text{edu}_i + \varepsilon_i
$$

<div class="compare">
<div class="wrong">

❌ **OLS 的假设**

$\text{Cov}(\text{edu}_i,\ \varepsilon_i) = 0$

即"教育年限与误差项不相关"

</div>
<div class="right">

✅ **现实问题**

个人能力 $a_i$ 既影响教育年限，又影响工资，但 $a_i$ 不可观测，被归入 $\varepsilon_i$

$$\Rightarrow \text{Cov}(\text{edu}_i,\ \varepsilon_i) \neq 0
$$

</div>
</div>

<div class="note">注：此处 $\ln w_i$ 为对数工资，$\text{edu}_i$ 为教育年限（年）。</div>

---

## 工具变量的两个条件

<div class="def">
<div class="label">📌 定义：有效工具变量</div>

变量 $z_i$ 是 $\text{edu}_i$ 的有效工具变量，当且仅当同时满足：

</div>

<br>

**条件一：相关性（Relevance）**

$$\text{Cov}(z_i,\ \text{edu}_i) \neq 0$$

工具变量必须与内生变量**相关**，可用第一阶段 F 检验验证（$F > 10$）。

<br>

**条件二：外生性（Exogeneity）**

$$\text{Cov}(z_i,\ \varepsilon_i) = 0$$

工具变量只通过 $\text{edu}_i$ 影响 $\ln w_i$，**不能直接影响**被解释变量。此条件**不可检验**，需依赖经济逻辑。

---

## 经典案例：出生季度作为工具变量

<div class="board">
<span class="comment"># Angrist & Krueger (1991)</span>
<br>
内生变量：<span class="hl">教育年限</span>（edu）
<br>
工具变量：<span class="hl">出生季度</span>（Q1/Q2/Q3/Q4）
<br><br>
<span class="comment"># 逻辑链条：</span>
<br>
出生季度 → 入学时间 → <span class="hl">教育年限</span> → <span class="result">工资</span>
<br><br>
<span class="comment"># 出生季度与工资无直接关系（外生性成立）</span>
</div>

<div class="note">注：此处假设义务教育截止年龄固定，出生在不同季度的孩子被迫在不同时间点辍学，从而导致教育年限差异。</div>

---

## 2SLS 两阶段估计

<div class="step-row">
<div class="step-num">1</div>
<div>

**第一阶段：**用工具变量 $z_i$ 对内生变量回归

$$\text{edu}_i = \pi_0 + \pi_1 z_i + \eta_i$$

得到拟合值 $\widehat{\text{edu}}_i$（已"净化"掉内生性部分）

</div>
</div>

<div class="step-row">
<div class="step-num">2</div>
<div>

**第二阶段：**用 $\widehat{\text{edu}}_i$ 代替原变量，重新做 OLS

$$\ln w_i = \alpha + \beta \cdot \widehat{\text{edu}}_i + \varepsilon_i$$

此时 $\hat{\beta}_{2SLS}$ 是一致估计量

</div>
</div>

<div class="def">
<div class="label">💻 Stata 命令</div>

`ivregress 2sls lnw (edu = z), robust`

</div>

---

<!-- _class: cover -->
<!-- _paginate: false -->

<div class="course">计量经济学 · 第 5 讲</div>

# 本讲小结

<div class="info">
下一讲：弱工具变量检验与过度识别检验<br>
作业：Angrist & Krueger (1991) 复现练习
</div>
