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
  padding: 40px 52px;
}
h1 { font-size: 38px; }
h2 {
  font-size: 26px;
  color: #0d47a1;
  border-left: 5px solid #1976d2;
  padding-left: 0.5em;
  margin-bottom: 0.7em;
}

/* ===== 封面 ===== */
section.cover {
  background: linear-gradient(135deg, #0d47a1 0%, #1565c0 60%, #1976d2 100%);
  color: white;
  justify-content: center;
  padding: 60px 80px;
}
section.cover h1 {
  color: white; font-size: 46px;
  border: none; margin-bottom: 0.2em;
  line-height: 1.3;
}
section.cover .subtitle { color: #90caf9; font-size: 22px; margin-bottom: 1.5em; }
section.cover .meta     { color: #bbdefb; font-size: 17px; line-height: 2; }
section.cover .tag {
  display: inline-block;
  background: rgba(255,255,255,0.15);
  border: 1px solid rgba(255,255,255,0.3);
  border-radius: 20px;
  padding: 0.2em 0.9em;
  font-size: 15px;
  margin-right: 0.5em;
}

/* ===== 节标题页 ===== */
section.divider {
  background: #e3f2fd;
  justify-content: center;
  padding: 60px 80px;
}
section.divider .num   { font-size: 72px; font-weight: 900; color: #bbdefb; line-height: 1; }
section.divider h2     { font-size: 36px; color: #0d47a1; border: none; padding: 0; }
section.divider .desc  { font-size: 18px; color: #546e7a; margin-top: 0.5em; }

/* ===== KPI 卡片 ===== */
.kpi-row {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.2em;
  margin: 0.5em 0;
}
.kpi-card {
  background: #f8faff;
  border: 1px solid #e3eaff;
  border-top: 4px solid #1976d2;
  border-radius: 8px;
  padding: 1em 1.2em;
  text-align: center;
}
.kpi-card .num   { font-size: 38px; font-weight: 700; color: #1565c0; line-height: 1.2; }
.kpi-card .label { font-size: 14px; color: #78909c; margin-top: 0.2em; }
.kpi-card .delta { font-size: 14px; color: #388e3c; margin-top: 0.3em; }
.kpi-card .delta.down { color: #c62828; }

/* ===== 双栏（图表专用）===== */
.chart-cols {
  display: grid;
  grid-template-columns: 3fr 2fr;
  gap: 1.5em;
  align-items: center;
  flex: 1;
}
.chart-cols-half {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5em;
  align-items: start;
  flex: 1;
}

/* ===== 发现/结论框 ===== */
.finding {
  background: #e8f5e9;
  border-left: 4px solid #388e3c;
  padding: 0.6em 1em;
  border-radius: 0 6px 6px 0;
  margin: 0.4em 0;
  font-size: 19px;
}
.insight {
  background: #fff8e1;
  border-left: 4px solid #f9a825;
  padding: 0.6em 1em;
  border-radius: 0 6px 6px 0;
  margin: 0.4em 0;
  font-size: 19px;
}

/* ===== 底部注释 ===== */
.note {
  font-size: 13px; color: #90a4ae;
  margin-top: auto; padding-top: 0.5em;
  border-top: 1px solid #eceff1;
}
</style>

<!-- _class: cover -->
<!-- _paginate: false -->

# 数据分析报告标题

<div class="subtitle">Data Analysis Report</div>

<div class="meta">
<span class="tag">数据分析</span>
<span class="tag">2024 Q4</span>
<br>
汇报人：姓名　｜　单位：部门/机构　｜　日期：YYYY-MM-DD
</div>

---

<!-- _class: divider -->
<!-- _paginate: false -->

<div class="num">01</div>

## 核心指标概览

<div class="desc">Key Metrics Overview</div>

---

## 核心指标

<div class="kpi-row">
<div class="kpi-card">
<div class="num">3,842</div>
<div class="label">样本量</div>
<div class="delta">↑ 12.3% 较上期</div>
</div>
<div class="kpi-card">
<div class="num">0.823</div>
<div class="label">模型 R²</div>
<div class="delta">↑ 0.041 较基准</div>
</div>
<div class="kpi-card">
<div class="num">18.6%</div>
<div class="label">处理效应</div>
<div class="delta down">↓ 2.1% 较预期</div>
</div>
</div>

<div class="finding">

✅ **核心发现：** 处理效应在 1% 水平显著，经稳健性检验后结论不变。

</div>

<div class="note">数据来源：XXX 数据库。样本期：2010–2022 年。所有变量均经过去极值处理（1%–99% 截尾）。</div>

---

<!-- _class: divider -->
<!-- _paginate: false -->

<div class="num">02</div>

## 描述性分析

<div class="desc">Descriptive Analysis</div>

---

## 变量分布与趋势

<div class="chart-cols">
<div>

<img src="./Figs/trend.png" style="width:100%; border-radius:6px;">

</div>
<div>

**图表解读**

- 被解释变量在样本期内呈上升趋势
- 2015 年后波动明显加大
- 处理组与对照组在政策前趋势平行

<div class="insight">

💡 **平行趋势：** 2015 年前两组趋势高度一致，支持 DID 识别策略。

</div>

</div>
</div>

<div class="note">注：图中实线为处理组，虚线为对照组。阴影区域为 95% 置信区间。</div>

---

## 双图对比

<div class="chart-cols-half">
<div>

**图 1：处理组 vs 对照组**

<img src="./Figs/fig1.png" style="width:100%; border-radius:6px;">

<div class="note">注：图 1 说明文字。</div>

</div>
<div>

**图 2：异质性分析**

<img src="./Figs/fig2.png" style="width:100%; border-radius:6px;">

<div class="note">注：图 2 说明文字。</div>

</div>
</div>

---

<!-- _class: divider -->
<!-- _paginate: false -->

<div class="num">03</div>

## 回归结果

<div class="desc">Regression Results</div>

---

## 基准回归与稳健性

<div class="chart-cols">
<div>

| | (1) | (2) | (3) |
|--|:---:|:---:|:---:|
| **Treat** | 0.231*** | 0.196*** | 0.186*** |
|  | (0.041) | (0.039) | (0.037) |
| 控制变量 | | ✓ | ✓ |
| 固定效应 | | | ✓ |
| 观测值 | 3,842 | 3,842 | 3,842 |
| $R^2$ | 0.214 | 0.381 | 0.523 |

<div class="note">注：*** p<0.01，** p<0.05，* p<0.1。括号内为聚类标准误。</div>

</div>
<div>

<div class="finding">

✅ 处理效应约 **18.6%**，在加入固定效应后依然稳健。

</div>

<div class="insight">

💡 控制变量加入后系数下降 **1.5pp**，说明存在一定混淆但方向不变。

</div>

</div>
</div>

---

<!-- _class: cover -->
<!-- _paginate: false -->

# 谢谢！

<div class="subtitle">Q & A</div>

<div class="meta">
姓名　｜　邮箱：your@email.com
</div>
