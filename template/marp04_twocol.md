---
marp: true
theme: default
size: 16:9
paginate: true
header: "实证研究方法"
footer: "姓名  ·  日期"
math: katex
---

<style>
section {
  font-size: 22px;
}
h1 { font-size: 40px; color: #1a237e; }
h2 { font-size: 28px; color: #283593; border-bottom: 2px solid #3949ab; padding-bottom: 0.2em; }

/* 双栏布局 */
.cols {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5em;
  align-items: start;
}
.cols-6040 { display: grid; grid-template-columns: 3fr 2fr; gap: 1.5em; align-items: start; }
.cols-4060 { display: grid; grid-template-columns: 2fr 3fr; gap: 1.5em; align-items: start; }

/* 代码字号 */
pre, code { font-size: 17px; }

/* 提示框 */
.box-note { background:#e8f4fd; border-left:4px solid #2196F3; padding:0.6em 1em; border-radius:4px; margin:0.4em 0; }
.box-tip  { background:#e8f5e9; border-left:4px solid #4CAF50; padding:0.6em 1em; border-radius:4px; margin:0.4em 0; }

/* 小字注释 */
.note { font-size:14px; color:#888; margin-top:auto; padding-top:0.4em; border-top:1px solid #e0e0e0; }
</style>

<!-- _paginate: false -->
<!-- _header: "" -->
<!-- _footer: "" -->

# 实证研究方法

## Empirical Research Methods

姓名 · 单位 · 日期

---

## 左文右图

<div class="cols">
<div>

**核心发现**

- 要点一：简要说明
- 要点二：简要说明
- 要点三：简要说明

<div class="box-note">

💡 替换右边的图片路径 `./Figs/result.png`

</div>

</div>
<div>

<img src="./Figs/result.png" style="width:100%;">

</div>
</div>

---

## 左代码右结果

<div class="cols">
<div>

**Python 代码**

```python
import pandas as pd
import statsmodels.formula.api as smf

df = pd.read_csv("data.csv")
model = smf.ols("y ~ x1 + x2", data=df)
result = model.fit()
print(result.summary())
```

</div>
<div>

**输出结果**

```text
OLS Regression Results
======================
Dep. Variable:        y
R-squared:        0.823
No. Observations:   500
----------------------
        coef   std err
x1     0.452     0.031
x2    -0.218     0.044
======================
```

</div>
</div>

---

## 三栏对比

<style scoped>
.cols3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.2em; }
.col-card { background: #f5f7ff; border-radius: 8px; padding: 1em; }
.col-card h3 { color: #3949ab; margin-top: 0; font-size: 20px; }
</style>

<div class="cols3">
<div class="col-card">

### OLS

**适用：** 无内生性

**假设：** 严格外生

$\hat{\beta}_{OLS} = (X'X)^{-1}X'y$

</div>
<div class="col-card">

### IV / 2SLS

**适用：** 存在内生性

**假设：** 工具变量有效

$\hat{\beta}_{IV} = (Z'X)^{-1}Z'y$

</div>
<div class="col-card">

### DID

**适用：** 政策评估

**假设：** 平行趋势

$\hat{\tau} = \Delta\bar{Y}_{treat} - \Delta\bar{Y}_{ctrl}$

</div>
</div>

<div class="note">注：以上为三种常用因果推断方法的简要对比。</div>
