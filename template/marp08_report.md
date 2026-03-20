---
marp: true
theme: default
size: 16:9
paginate: true
---

<style>
/* ===== 全局 ===== */
section {
  font-size: 21px;
  display: flex;
  flex-direction: column;
  padding: 44px 60px;
  background: #ffffff;
}
h1 { font-size: 36px; color: #212121; }
h2 {
  font-size: 25px;
  color: #212121;
  border-bottom: 3px solid #00897b;
  padding-bottom: 0.25em;
  margin-bottom: 0.8em;
}

/* ===== 封面 ===== */
section.cover {
  background: #00695c;
  color: white;
  padding: 0;
  flex-direction: row;
}
.cover-left {
  background: #004d40;
  width: 38%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 60px 44px;
}
.cover-right {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 60px 56px;
}
.cover-left .org  { font-size: 14px; color: #80cbc4; letter-spacing: 0.1em; margin-bottom: 2em; }
.cover-left .date { font-size: 15px; color: #80cbc4; margin-top: 2em; }
.cover-left .tag  {
  display: inline-block;
  background: rgba(255,255,255,0.12);
  border-radius: 4px;
  padding: 0.2em 0.7em;
  font-size: 13px;
  margin-bottom: 0.4em;
  color: #b2dfdb;
}
.cover-right h1   { color: white; font-size: 40px; line-height: 1.4; border: none; }
.cover-right .sub { color: #b2dfdb; font-size: 18px; margin-top: 0.8em; }
.cover-right .author { color: #e0f2f1; font-size: 16px; margin-top: 2em; border-top: 1px solid rgba(255,255,255,0.2); padding-top: 1em; }

/* ===== 节标题页 ===== */
section.divider {
  background: #e0f2f1;
  justify-content: center;
}
section.divider .num  { font-size: 80px; font-weight: 900; color: #b2dfdb; line-height: 1; }
section.divider h2    { font-size: 38px; color: #00695c; border-color: #00897b; }
section.divider .desc { font-size: 18px; color: #546e7a; }

/* ===== 要点列表增强 ===== */
.bullet-list { list-style: none; padding: 0; margin: 0; }
.bullet-list li {
  padding: 0.4em 0 0.4em 1.6em;
  position: relative;
  border-bottom: 1px solid #f5f5f5;
}
.bullet-list li::before {
  content: "";
  position: absolute;
  left: 0; top: 0.85em;
  width: 8px; height: 8px;
  background: #00897b;
  border-radius: 50%;
}

/* ===== 双栏 ===== */
.cols     { display: grid; grid-template-columns: 1fr 1fr;   gap: 1.5em; align-items: start; }
.cols-64  { display: grid; grid-template-columns: 3fr 2fr;   gap: 1.5em; align-items: start; }
.cols-37  { display: grid; grid-template-columns: 1fr 2.3fr; gap: 1.5em; align-items: start; }

/* ===== 建议卡片 ===== */
.rec-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1em;
}
.rec-card {
  border: 1px solid #e0e0e0;
  border-top: 4px solid #00897b;
  border-radius: 6px;
  padding: 0.9em 1.1em;
}
.rec-card h3 { font-size: 18px; color: #00695c; margin: 0 0 0.5em; }
.rec-card p  { font-size: 17px; color: #424242; margin: 0; }

/* ===== 引用框 ===== */
.quote {
  background: #f1f8f7;
  border-left: 5px solid #00897b;
  padding: 0.7em 1.1em;
  border-radius: 0 6px 6px 0;
  font-style: italic;
  color: #37474f;
  margin: 0.6em 0;
}

/* ===== 数字亮点 ===== */
.highlight-num { color: #00695c; font-weight: 700; font-size: 1.15em; }

/* ===== 标签 ===== */
.label-tag {
  display: inline-block;
  background: #e0f2f1;
  color: #00695c;
  border-radius: 4px;
  padding: 0.1em 0.6em;
  font-size: 14px;
  font-weight: bold;
  margin-right: 0.4em;
}

/* ===== 底部注释 ===== */
.note { font-size: 13px; color: #90a4ae; margin-top: auto; padding-top: 0.5em; border-top: 1px solid #eceff1; }
</style>

<!-- _class: cover -->
<!-- _paginate: false -->

<div class="cover-left">
<div class="org">单位名称 · 部门</div>
<div class="tag">政策研究</div>
<div class="tag">2024 年度</div>
<div class="date">汇报日期：YYYY-MM-DD</div>
</div>

<div class="cover-right">

# 报告标题

# 第二行标题

<div class="sub">Report Subtitle</div>

<div class="author">
汇报人：姓名　职务：职位
</div>

</div>

---

<!-- _class: divider -->
<!-- _paginate: false -->

<div class="num">01</div>

## 背景与问题

<div class="desc">Background & Problem Statement</div>

---

## 政策背景

<div class="cols-64">
<div>

**主要背景**

- <span class="label-tag">背景一</span> 简要说明，不超过两行，重点突出关键数据
- <span class="label-tag">背景二</span> 简要说明，不超过两行
- <span class="label-tag">背景三</span> 简要说明，不超过两行

<div class="quote">
"核心引言或政策表述，来自权威文件或领导讲话。"
<br><span style="font-size:13px;color:#78909c;">—— 来源文件名称，年份</span>
</div>

</div>
<div>

**关键数据**

| 指标 | 数值 | 较上期 |
|------|------|--------|
| 指标一 | <span class="highlight-num">12.3%</span> | ↑ 1.2pp |
| 指标二 | <span class="highlight-num">8,420</span> | ↑ 6.8% |
| 指标三 | <span class="highlight-num">0.76</span> | — |

</div>
</div>

<div class="note">数据来源：XXX 统计公报（2024 年）。</div>

---

## 核心问题

<div class="cols-37">
<div style="background:#e0f2f1;border-radius:8px;padding:1.2em;text-align:center;">
<div style="font-size:13px;color:#00695c;font-weight:bold;margin-bottom:0.5em;">核心问题</div>
<div style="font-size:20px;color:#004d40;font-weight:bold;line-height:1.5;">如何在……条件下，实现……目标？</div>
</div>
<div>

**问题的三个维度**

<ul class="bullet-list">
<li>维度一：简要说明当前困境或挑战</li>
<li>维度二：简要说明数据或证据支撑</li>
<li>维度三：简要说明与政策目标的差距</li>
</ul>

</div>
</div>

---

<!-- _class: divider -->
<!-- _paginate: false -->

<div class="num">02</div>

## 主要发现

<div class="desc">Key Findings</div>

---

## 发现一：标题简洁有力

<div class="cols">
<div>

<img src="./Figs/fig1.png" style="width:100%; border-radius:6px;">

<div class="note">图注：说明图表内容，数据来源。</div>

</div>
<div>

**数据说明**

核心数据：<span class="highlight-num">X.X%</span>，较上年提升 X.X 个百分点。

**主要解读**

<ul class="bullet-list">
<li>解读要点一：具体说明</li>
<li>解读要点二：具体说明</li>
<li>解读要点三：具体说明</li>
</ul>

<div class="quote">
这一发现表明……，与……研究结论一致。
</div>

</div>
</div>

---

<!-- _class: divider -->
<!-- _paginate: false -->

<div class="num">03</div>

## 政策建议

<div class="desc">Policy Recommendations</div>

---

## 建议

<div class="rec-grid">
<div class="rec-card">
<h3>建议一：标题</h3>
<p>具体措施说明，2–3 句话，突出可操作性和预期效果。</p>
</div>
<div class="rec-card">
<h3>建议二：标题</h3>
<p>具体措施说明，2–3 句话，突出可操作性和预期效果。</p>
</div>
<div class="rec-card">
<h3>建议三：标题</h3>
<p>具体措施说明，2–3 句话，突出可操作性和预期效果。</p>
</div>
<div class="rec-card">
<h3>建议四：标题</h3>
<p>具体措施说明，2–3 句话，突出可操作性和预期效果。</p>
</div>
</div>

<div class="note">注：以上建议基于 XX 数据分析，具体实施需结合地方实际情况。</div>

---

<!-- _class: cover -->
<!-- _paginate: false -->

<div class="cover-left">
<div class="org">单位名称 · 部门</div>
<div class="date">YYYY-MM-DD</div>
</div>

<div class="cover-right">

# 谢谢！

<div class="sub">欢迎批评指正</div>

<div class="author">
联系方式：your@email.com
</div>

</div>
