[Uploading task3.html…]()
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>雅居专列英语·泉州站</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; -webkit-tap-highlight-color: transparent; }
  body {
    font-family: "Microsoft YaHei", "PingFang SC", sans-serif;
    background-color: #f0f6ff;
    background-image:
      linear-gradient(45deg, #dbe9ff 25%, transparent 25%),
      linear-gradient(-45deg, #dbe9ff 25%, transparent 25%),
      linear-gradient(45deg, transparent 75%, #dbe9ff 75%),
      linear-gradient(-45deg, transparent 75%, #dbe9ff 75%);
    background-size: 40px 40px;
    background-position: 0 0, 0 20px, 20px -20px, -20px 0px;
    color: #333;
    min-height: 100vh;
  }
  
  /* 顶部导航 (移动端适配) */
  .navbar {
    background: linear-gradient(90deg, #8b2e2e, #b83a3a);
    color: #fff; 
    padding: 12px 16px;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.15);
    position: sticky; top: 0; z-index: 100;
  }
  .navbar-left { display: flex; align-items: center; gap: 8px; font-weight: 600; font-size: 15px; }
  .navbar-left .sub { font-weight: 400; font-size: 12px; opacity: 0.8; }
  .navbar-menu { display: flex; gap: 4px; flex-wrap: wrap; width: 100%; order: 3; }
  .navbar-menu a {
    color: #f5e6e6; text-decoration: none; font-size: 12px;
    padding: 6px 10px; border-radius: 20px; cursor: pointer;
    display: flex; align-items: center; gap: 4px; transition: background 0.2s;
    white-space: nowrap;
  }
  .navbar-menu a.active, .navbar-menu a:hover { background: rgba(255,255,255,0.2); color: #fff; }
  .btn-print { background: rgba(255,255,255,0.15); border: none; color: #fff; padding: 6px 12px; border-radius: 20px; cursor: pointer; font-size: 12px; white-space: nowrap; }

  /* 主体容器 */
  .container { max-width: 1150px; margin: 0 auto; padding: 20px 12px 40px; }
  .page-title { font-size: 24px; color: #b83a3a; margin-bottom: 6px; line-height: 1.3; word-break: break-all; }
  .page-subtitle { font-size: 13px; color: #666; font-family: monospace; margin-bottom: 16px; }

  /* 卡片 */
  .card {
    background: #fff; border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.06);
    padding: 16px 14px; margin-bottom: 16px;
    position: relative; overflow: hidden;
  }
  .card::before {
    content: ""; position: absolute; top: 0; left: 0; right: 0; height: 4px;
    background: linear-gradient(90deg, #b83a3a, #d4a017);
  }
  .card-title { font-size: 16px; font-weight: 600; color: #8b2e2e; margin-bottom: 14px; display: flex; align-items: center; gap: 6px; flex-wrap: wrap; }
  .card-title .icon { color: #b83a3a; font-size: 16px; }

  /* 表单栅格 */
  .form-grid { display: grid; grid-template-columns: 1fr; gap: 12px; }
  .form-item { display: flex; flex-direction: column; gap: 6px; }
  .form-item label { font-size: 13px; color: #4a5568; font-weight: 500; display: flex; align-items: center; gap: 4px; }
  .form-item label .tag-icon { color: #b83a3a; font-size: 14px; }
  .form-item input {
    padding: 10px 12px; border: 1px solid #cbd5e0; border-radius: 6px;
    font-size: 14px; outline: none; transition: border-color 0.2s, box-shadow 0.2s;
    width: 100%;
  }
  .form-item input:focus { border-color: #b83a3a; box-shadow: 0 0 0 3px rgba(184,58,58,0.15); }
  .form-item input::placeholder { color: #a0aec0; }
  .form-item input[readonly] { background: #f7fafc; color: #4a5568; }

  .form-actions { margin-top: 16px; display: flex; align-items: center; gap: 12px; flex-wrap: wrap; }
  .btn-save {
    background: #2f855a; color: #fff; border: none; padding: 10px 20px;
    border-radius: 24px; font-size: 14px; cursor: pointer;
    display: flex; align-items: center; gap: 6px; transition: background 0.2s;
  }
  .btn-secondary {
    background: #b83a3a; color: #fff; border: none; padding: 10px 20px;
    border-radius: 24px; font-size: 14px; cursor: pointer;
    display: flex; align-items: center; gap: 6px;
  }
  .hint { font-size: 12px; color: #a0aec0; }

  /* 案例信息 */
  .case-header {
    display: flex; flex-direction: column; align-items: flex-start; gap: 10px;
    padding: 12px 14px; background: #fff8f0; border-radius: 8px; margin-bottom: 14px;
    border-left: 4px solid #d4a017;
  }
  .case-header .badge {
    background: #b83a3a; color: #fff; padding: 6px 12px; border-radius: 6px;
    font-size: 13px; font-weight: 600;
  }
  .case-header .case-info { font-size: 13px; color: #555; line-height: 1.6; }
  .case-header .case-info strong { color: #8b2e2e; }
  .case-desc { font-size: 14px; line-height: 1.8; color: #4a5568; margin-bottom: 14px; }
  .scene-grid { display: grid; grid-template-columns: 1fr; gap: 10px; margin-bottom: 14px; }
  .scene-card {
    background: #fff; border: 1px solid #f0e0d0; border-radius: 8px; padding: 12px 14px;
    border-left: 4px solid #d4a017;
  }
  .scene-card .scene-no { font-size: 12px; color: #b83a3a; font-weight: 600; margin-bottom: 4px; }
  .scene-card .scene-en { font-size: 14px; font-weight: 600; color: #333; margin-bottom: 4px; }
  .scene-card .scene-cn { font-size: 13px; color: #666; }
  .case-note {
    background: #fdf6ec; border-radius: 8px; padding: 12px 14px;
    font-size: 13px; color: #6b4a1f; line-height: 1.7;
  }
  .case-note strong { color: #b83a3a; }
  .quote { text-align: center; font-size: 13px; color: #b83a3a; font-style: italic; margin-top: 16px; }

  /* 词汇卡片 */
  .vocab-grid { display: grid; grid-template-columns: 1fr; gap: 12px; }
  .vocab-card {
    background: #fff; border: 1px solid #f0e0d0; border-radius: 8px;
    padding: 12px 14px;
  }
  .vocab-card .word { font-size: 15px; font-weight: 700; color: #b83a3a; margin-bottom: 2px; }
  .vocab-card .phonetic { font-size: 12px; color: #888; margin-bottom: 4px; }
  .vocab-card .meaning { font-size: 13px; color: #444; margin-bottom: 8px; }
  .vocab-card .actions { display: flex; align-items: center; gap: 8px; flex-wrap: wrap; }
  .vocab-card .actions button {
    background: #f0f6ff; border: 1px solid #cbd5e0; border-radius: 6px;
    padding: 6px 12px; font-size: 12px; cursor: pointer; color: #4a5568;
  }
  .vocab-card .actions button.record-btn { background: #b83a3a; color: #fff; border-color: #b83a3a; }

  /* 评分结果面板 */
  .score-panel {
    margin-top: 10px; padding: 10px; background: #fafafa;
    border-radius: 6px; border: 1px solid #eee;
    display: grid; grid-template-columns: 1fr; gap: 6px;
    font-size: 12px;
  }
  .score-panel .score-item {
    display: flex; justify-content: space-between;
    padding: 4px 8px; background: #fff; border-radius: 4px;
  }
  .score-panel .score-item .label { color: #888; }
  .score-panel .score-item .value { color: #b83a3a; font-weight: 700; }
  .score-panel.total-row { grid-template-columns: 1fr; }
  .score-panel.total-row .score-item { background: #fdf0f0; }
  .score-panel .loading { color: #888; font-style: italic; font-size: 12px; text-align: center; padding: 4px; }

  /* 句型 */
  .sentence-section { margin-bottom: 20px; }
  .sentence-section .section-title {
    font-size: 14px; font-weight: 600; color: #b83a3a;
    padding: 8px 12px; background: #fdf0f0; border-radius: 6px; margin-bottom: 12px;
  }
  .sentence-item {
    background: #fff; border: 1px solid #f0e0d0; border-radius: 8px;
    padding: 12px; margin-bottom: 10px;
  }
  .sentence-item .sentence-main { display: flex; flex-direction: column; gap: 10px; }
  .sentence-item .en { font-size: 14px; color: #333; margin-bottom: 4px; font-weight: 500; line-height: 1.5; }
  .sentence-item .cn { font-size: 13px; color: #777; line-height: 1.5; }
  .sentence-item .btn-group { display: flex; gap: 8px; flex-wrap: wrap; }
  .sentence-item .read-btn, .sentence-item .record-btn {
    border: none; padding: 8px 14px; border-radius: 6px; font-size: 13px; cursor: pointer;
    display: flex; align-items: center; justify-content: center; flex: 1;
  }
  .sentence-item .read-btn { background: #b83a3a; color: #fff; }
  .sentence-item .record-btn { background: #2f855a; color: #fff; }

  /* 对话卡片 */
  .dialog-scene {
    background: #fff; border: 1px solid #f0e0d0; border-radius: 10px;
    padding: 14px; margin-bottom: 16px;
  }
  .dialog-scene .scene-header {
    display: flex; flex-direction: column; gap: 6px; margin-bottom: 12px;
  }
  .dialog-scene .scene-header .scene-name {
    font-size: 14px; font-weight: 600; color: #8b2e2e;
    padding: 6px 12px; background: #fdf0f0; border-radius: 6px;
    display: inline-block;
  }
  .dialog-scene .scene-header .scene-desc { font-size: 12px; color: #888; line-height: 1.5; }
  .dialog-line {
    border-radius: 8px; padding: 10px 12px; margin-bottom: 10px;
  }
  .dialog-line.role-steward { background: #fdf6ec; border-left: 4px solid #d4a017; }
  .dialog-line.role-passenger { background: #f0f7ff; border-left: 4px solid #4a90d9; }
  .dialog-line .role-label { font-size: 13px; font-weight: 600; margin-bottom: 6px; display: flex; align-items: center; gap: 4px; }
  .dialog-line.role-steward .role-label { color: #8b6b1f; }
  .dialog-line.role-passenger .role-label { color: #2a5d9a; }
  .dialog-line .line-en { font-size: 13px; color: #333; margin-bottom: 4px; font-weight: 500; line-height: 1.5; }
  .dialog-line .line-cn { font-size: 12px; color: #777; margin-bottom: 8px; line-height: 1.5; }
  .dialog-line .read-btn {
    background: #b83a3a; color: #fff; border: none; padding: 6px 12px;
    border-radius: 14px; font-size: 12px; cursor: pointer;
    display: inline-flex; align-items: center; gap: 4px;
  }
  .scene-controls {
    display: flex; align-items: center; gap: 6px; flex-wrap: wrap;
    margin-top: 8px; padding-top: 12px; border-top: 1px dashed #eee;
  }
  .scene-controls button {
    background: #fff; border: 1px solid #d0d0d0; border-radius: 16px;
    padding: 6px 10px; font-size: 12px; cursor: pointer; color: #555;
    flex: 1; display: flex; justify-content: center; align-items: center; gap: 4px;
  }
  .scene-controls .status-tag { font-size: 12px; color: #aaa; width: 100%; text-align: center; margin-top: 4px; }
  .scene-controls .status-tag.done { color: #2f855a; }

  /* 角色分工 */
  .role-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .role-item {
    background: #fff; border: 1px solid #f0e0d0; border-radius: 8px;
    padding: 12px 10px; text-align: center;
  }
  .role-item .role-name { font-size: 13px; font-weight: 600; color: #b83a3a; margin-bottom: 4px; }
  .role-item .role-desc { font-size: 11px; color: #888; margin-bottom: 8px; }
  .role-item input { width: 100%; padding: 8px; border: 1px solid #cbd5e0; border-radius: 6px; font-size: 13px; outline: none; text-align: center; }

  /* ===== 多轮对话脚本编辑区 (移动端适配核心) ===== */
  .script-scene {
    background: #fff; border: 1px solid #f0e0d0; border-radius: 10px;
    padding: 14px; margin-bottom: 16px;
  }
  .script-scene .scene-title {
    font-size: 14px; font-weight: 600; color: #8b2e2e;
    padding: 6px 12px; background: #fdf0f0; border-radius: 6px; margin-bottom: 12px;
  }
  .ref-sentences {
    display: flex; flex-wrap: wrap; gap: 6px;
    padding: 10px; background: #fafafa; border-radius: 8px;
    margin-bottom: 14px; max-height: 200px; overflow-y: auto;
  }
  .ref-sentence {
    background: #fff; border: 1px solid #e0c8c8; border-radius: 6px;
    padding: 6px 10px; font-size: 12px; cursor: grab;
    color: #555; line-height: 1.4;
  }
  .ref-sentence .grip { color: #b83a3a; font-size: 11px; margin-right: 4px; }

  /* 轮次列表 (垂直布局) */
  .turns-list { display: flex; flex-direction: column; gap: 12px; margin-bottom: 12px; }
  .turn-item {
    display: flex; flex-direction: column; gap: 8px;
    background: #fffdfd; border: 1px solid #f0e0d0; border-radius: 8px;
    padding: 12px;
  }
  .turn-item .turn-header { display: flex; justify-content: space-between; align-items: center; }
  .turn-item .turn-index { font-size: 13px; font-weight: 700; color: #b83a3a; }
  .turn-item .turn-role-select {
    padding: 6px 10px; border: 1px solid #cbd5e0; border-radius: 6px;
    font-size: 13px; outline: none; background: #fff; width: 120px;
  }
  .turn-item .turn-dropzone {
    min-height: 48px; border: 2px dashed #d0c0c0; border-radius: 6px;
    padding: 8px 10px; font-size: 13px; color: #333;
    background: #fff; line-height: 1.5;
  }
  .turn-item .turn-dropzone .empty-hint { font-size: 12px; color: #bbb; font-style: italic; }
  .turn-item .turn-text { word-break: break-word; white-space: pre-wrap; }
  .turn-item .turn-text.manual { color: #2a5d9a; }
  .turn-item .turn-actions {
    display: flex; gap: 6px; flex-wrap: wrap; justify-content: flex-end;
  }
  .turn-item .turn-actions button {
    background: #fff; border: 1px solid #d0d0d0; border-radius: 6px;
    padding: 6px 10px; font-size: 12px; cursor: pointer; color: #666;
    flex: 1; min-width: 70px;
  }
  .turn-item .turn-actions button.danger { color: #d33; border-color: #f0c0c0; background: #fff5f5; }

  .turn-custom-area { display: none; gap: 6px; align-items: center; flex-wrap: wrap; margin-top: 6px; }
  .turn-custom-area.active { display: flex; }
  .turn-custom-area input {
    flex: 1; min-width: 100%; padding: 8px 10px; border: 1px solid #cbd5e0;
    border-radius: 6px; font-size: 13px; outline: none;
  }
  .turn-custom-area button {
    padding: 8px 12px; border: none; border-radius: 6px;
    font-size: 13px; cursor: pointer; flex: 1;
  }
  .btn-add { background: #2f855a; color: #fff; }
  .btn-cancel { background: #e2e8f0; color: #4a5568; }
  .btn-voice { background: #b83a3a; color: #fff; }

  .scene-add-turn button {
    background: #b83a3a; color: #fff; border: none;
    padding: 10px; border-radius: 20px; font-size: 13px; width: 100%;
    cursor: pointer;
  }

  .preview-box {
    background: #fafafa; border-radius: 8px; padding: 12px;
    font-size: 13px; line-height: 1.6; color: #444;
    max-height: 300px; overflow-y: auto; white-space: pre-wrap;
  }

  /* 评分表 (移动端优化) */
  .score-table-wrap { overflow-x: auto; }
  .score-table { width: 100%; border-collapse: collapse; font-size: 13px; margin-bottom: 12px; min-width: 500px; }
  .score-table th, .score-table td { padding: 10px 8px; text-align: left; border-bottom: 1px solid #eee; }
  .score-table th { background: #fdf0f0; color: #8b2e2e; font-weight: 600; font-size: 12px; }
  .score-table td input {
    width: 60px; padding: 6px; border: 1px solid #cbd5e0;
    border-radius: 4px; font-size: 13px; text-align: center;
  }
  .score-table .weight { color: #b83a3a; font-weight: 600; }

  .total-score {
    display: flex; align-items: center; justify-content: space-between;
    background: #fdf0f0; border-radius: 8px; padding: 12px 14px; margin-top: 10px;
  }
  .total-score .label { font-size: 14px; font-weight: 600; color: #8b2e2e; }
  .total-score .value { font-size: 18px; font-weight: 700; color: #b83a3a; }

  .overview-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 14px; }
  .overview-card { background: #fff; border: 1px solid #f0e0d0; border-radius: 8px; padding: 12px; text-align: center; }
  .overview-card .ov-label { font-size: 12px; color: #888; margin-bottom: 4px; }
  .overview-card .ov-value { font-size: 20px; font-weight: 700; color: #b83a3a; }
  .overview-card .ov-sub { font-size: 11px; color: #aaa; margin-top: 2px; }

  .final-score-card {
    background: linear-gradient(90deg, #b83a3a, #d4a017);
    color: #fff; border-radius: 10px; padding: 16px;
    display: flex; align-items: center; justify-content: space-between;
    margin-top: 14px;
  }
  .final-score-card .label { font-size: 14px; font-weight: 600; }
  .final-score-card .value { font-size: 26px; font-weight: 700; }

  .comment-box textarea {
    width: 100%; min-height: 80px; padding: 10px;
    border: 1px solid #cbd5e0; border-radius: 6px;
    font-size: 14px; font-family: inherit; outline: none; resize: vertical;
  }

  .toast {
    position: fixed; top: 70px; right: 50%; transform: translateX(50%) translateY(-10px);
    background: #2f855a; color: #fff; padding: 10px 20px; border-radius: 6px; font-size: 13px;
    opacity: 0; transition: all 0.3s; pointer-events: none; z-index: 200;
    white-space: nowrap;
  }
  .toast.show { opacity: 1; transform: translateX(50%) translateY(0); }

  .footer { text-align: center; font-size: 12px; color: #aaa; padding: 20px 0; margin-top: 20px; }

  /* PC 端适配（屏幕大于 768px 时生效） */
  @media screen and (min-width: 768px) {
    .navbar { flex-wrap: nowrap; padding: 12px 32px; }
    .navbar-menu { width: auto; order: 0; }
    .navbar-menu a { font-size: 13px; padding: 6px 12px; }
    .container { padding: 36px 24px 60px; }
    .page-title { font-size: 32px; }
    .card { padding: 24px 28px; }
    .form-grid { grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); }
    .case-header { flex-direction: row; align-items: center; padding: 14px 18px; }
    .scene-grid { grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); }
    .vocab-grid { grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); }
    .score-panel { grid-template-columns: repeat(2, 1fr); }
    .role-grid { grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); }
    
    /* PC 端多轮对话：横向排列 */
    .turn-item { flex-direction: row; align-items: flex-start; padding: 10px 12px; }
    .turn-item .turn-header { flex-direction: row; width: 140px; flex-shrink: 0; padding-top: 6px; }
    .turn-item .turn-actions { flex-wrap: wrap; justify-content: flex-start; min-width: 120px; padding-top: 4px; }
    .turn-item .turn-actions button { flex: none; min-width: auto; }
    .turn-item .turn-content { flex: 1; }
    .turn-custom-area input { min-width: 180px; }
    .turn-custom-area button { flex: none; }
    
    .score-table-wrap { overflow-x: visible; }
    .overview-grid { grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); }
    .toast { right: 32px; transform: translateY(-10px); top: 80px; }
    .toast.show { transform: translateY(0); }
  }

  @media print {
    .navbar, .btn-save, .btn-print, .read-btn, .record-btn, .vocab-card .actions button,
    .btn-secondary, .turn-actions, .scene-add-turn, .scene-controls button { display: none !important; }
    body { background: #fff; }
    .card { box-shadow: none; border: 1px solid #ddd; }
  }
</style>
</head>
<body>

<nav class="navbar">
  <div class="navbar-left">
    <span>🏠 雅居专列</span>
    <span class="sub">· 泉州站英语实训</span>
  </div>
  <div class="navbar-menu">
    <a class="active" onclick="showSection('group')">👥 小组</a>
    <a onclick="showSection('case')">📋 案例信息</a>
    <a onclick="showSection('vocab')">📖 词汇</a>
    <a onclick="showSection('sentence')">💬 句型</a>
    <a onclick="showSection('dialog')">🗂 对话卡片</a>
    <a onclick="showSection('perform')">🎭 模拟展演</a>
    <a onclick="showSection('score')">⭐ 师评成绩</a>
  </div>
  <button class="btn-print" onclick="window.print()">🖨 打印</button>
</nav>

<div class="container">
  <h1 class="page-title">English-for-Dwelling-Themed-Train-Quanzhou-Station</h1>
  <p class="page-subtitle">index.html &lt;!DOCTYPE html&gt;</p>

  <!-- ===== 一、小组 ===== -->
  <section id="section-group">
    <div class="card">
      <div class="card-title"><span class="icon">ℹ️</span> 小组基本信息</div>
      <div class="form-grid">
        <div class="form-item">
          <label><span class="tag-icon">🏫</span> 班级</label>
          <input type="text" id="className" placeholder="请输入班级">
        </div>
        <div class="form-item">
          <label><span class="tag-icon">🏷</span> 小组名称</label>
          <input type="text" id="groupName" placeholder="如：第1组 / 闽南雅居乘务组">
        </div>
        <div class="form-item">
          <label><span class="tag-icon">#</span> 小组编号</label>
          <input type="text" id="groupNo" placeholder="如：G01">
        </div>
        <div class="form-item">
          <label><span class="tag-icon">📌</span> 实训任务</label>
          <input type="text" id="task" value="雅居专列·泉州站 高铁乘务英语实训" readonly>
        </div>
        <div class="form-item">
          <label><span class="tag-icon">👤</span> 指导教师</label>
          <input type="text" id="teacher" placeholder="请输入姓名">
        </div>
      </div>
      <div class="form-actions">
        <button class="btn-save" onclick="saveGroup()">💾 保存信息</button>
        <span class="hint">数据自动保存在浏览器</span>
      </div>
    </div>

    <div class="card">
      <div class="card-title"><span class="icon">📋</span> 任务说明</div>
      <p class="case-desc">
        本实训系统基于“雅居专列”北京南-泉州高铁乘务服务真实案例设计。围绕登车迎客、车厢广播、主题特产销售、车厢主题互动四大情境，通过词汇跟读评分、句型逐词学习、对话卡片演练、模拟展演编排四个环节，掌握40个雅居专列与闽南建筑文化核心词汇、4类情境句型、4个完整对话，感悟闽南人居文明。
      </p>
      <p class="case-desc">
        <strong>特色功能：</strong>① 每个单词可单独点击发音；② 每个句子提供“整句朗读”按钮；③ 支持跟读评分与对话录音；④ 词汇聚焦闽南建筑文化（红砖厝、燕尾脊、骑楼、土楼），体现闽南人居文明。
      </p>
    </div>
  </section>

  <!-- ===== 二、案例信息 ===== -->
  <section id="section-case" style="display:none;">
    <div class="card">
      <div class="card-title"><span class="icon">📋</span> 雅居专列·泉州站 乘务服务案例</div>
      <div class="case-header">
        <div class="badge">🏠 雅居专列 泉州站</div>
        <div class="case-info">
          <strong>英文名称：</strong>Dwelling Themed Train · Quanzhou<br>
          <strong>车次：</strong>G72“雅居专列”北京南（VNP）→泉州（QZS）<br>
          <strong>日期：</strong>2025年5月18日｜<strong>车型：</strong>复兴号CR400AF<br>
          <strong>阶段：</strong>全程乘务服务（登车迎客→车厢广播→特产销售→主题互动→到站送别）
        </div>
      </div>
      <h3 style="font-size:15px; color:#8b2e2e; margin-bottom:10px;">案例描述</h3>
      <p class="case-desc">
        在一趟由北京南开往泉州的“雅居专列”高铁上，4人乘务组为旅客提供全程服务。服务内容包括：登车迎客（站台迎客、检票验票、座位指引、行李协助），车厢广播（欢迎词、安全提示、到站提醒，重点介绍闽南建筑文化），主题特产销售（德化白瓷、安溪铁观音、惠安影雕、闽南红砖文创、扫码支付与折扣），车厢主题互动（闽南建筑文化讲解、红砖厝知识问答、南音体验、奖品赠送）。乘务员需用英语专业、礼貌、热情地与旅客沟通，在服务中传递闽南人居文明与海洋文化精髓，让旅客在旅途中感悟“闽南古韵”的魅力。
      </p>
      <h3 style="font-size:15px; color:#8b2e2e; margin:14px 0 10px;">四大情境</h3>
      <div class="scene-grid">
        <div class="scene-card">
          <div class="scene-no">情景一 / Scenario 1</div>
          <div class="scene-en">Boarding &amp; Welcome</div>
          <div class="scene-cn">登车迎客·检票·座位指引</div>
        </div>
        <div class="scene-card">
          <div class="scene-no">情景二 / Scenario 2</div>
          <div class="scene-en">Onboard Announcements</div>
          <div class="scene-cn">车厢广播·闽南建筑文化</div>
        </div>
        <div class="scene-card">
          <div class="scene-no">情景三 / Scenario 3</div>
          <div class="scene-en">Specialty Product Sales</div>
          <div class="scene-cn">主题特产销售·白瓷·铁观音</div>
        </div>
        <div class="scene-card">
          <div class="scene-no">情景四 / Scenario 4</div>
          <div class="scene-en">Onboard Theme Interaction</div>
          <div class="scene-cn">主题互动·红砖厝知识·南音体验</div>
        </div>
      </div>
      <div class="case-note">
        <strong>案例要点：</strong>4人乘务组分工协作，覆盖四大核心情境。乘务员需用英语向旅客提供专业、礼貌、灵活的服务，并具备闽南建筑文化讲解能力，重点呈现闽南人居特色（红砖厝、燕尾脊、骑楼、土楼）。
      </div>
      <p class="quote">“红砖白石双坡曲，出砖入石燕尾脊”——以专业态度，学好高铁乘务英语，讲好闽南故事。</p>
    </div>
  </section>

  <!-- ===== 三、词汇 ===== -->
  <section id="section-vocab" style="display:none;">
    <div class="card">
      <div class="card-title"><span class="icon">📖</span> 雅居专列 &amp; 闽南建筑文化词汇</div>
      <p style="font-size:13px; color:#888; margin-bottom:14px;">
        共40个核心词汇。点击“🔊 发音”听标准发音，点击“🎤 跟读评分”录音并显示评分结果。
      </p>
      <div class="vocab-grid" id="vocabGrid"></div>
    </div>
  </section>

  <!-- ===== 四、句型 ===== -->
  <section id="section-sentence" style="display:none;">
    <div class="card">
      <div class="card-title"><span class="icon">💬</span> 高铁乘务常用句型</div>
      <p style="font-size:13px; color:#888; margin-bottom:14px;">
        点击“🔊 整句朗读”听标准发音，点击“🎤 跟读评分”录音并显示评分结果。
      </p>
      <div id="sentenceContainer"></div>
    </div>
  </section>

  <!-- ===== 五、对话卡片 ===== -->
  <section id="section-dialog" style="display:none;">
    <div class="card">
      <div class="card-title"><span class="icon">🗂</span> 高铁乘务服务对话卡片</div>
      <p style="font-size:13px; color:#888; margin-bottom:14px;">
        点击台词下方按钮可听整句发音。
      </p>
      <div id="dialogContainer"></div>
    </div>
  </section>

  <!-- ===== 六、模拟展演 ===== -->
  <section id="section-perform" style="display:none;">
    <div class="card">
      <div class="card-title"><span class="icon">🎭</span> 1. 角色分工（4人一组）</div>
      <p style="font-size:13px; color:#888; margin-bottom:12px;">4人乘务组，为每个岗位分配成员姓名。</p>
      <div class="role-grid">
        <div class="role-item">
          <div class="role-name">列车长</div>
          <div class="role-desc">Train Chief</div>
          <input type="text" class="role-input" data-role="chief" placeholder="姓名...">
        </div>
        <div class="role-item">
          <div class="role-name">乘务员1</div>
          <div class="role-desc">CA1 · 迎客</div>
          <input type="text" class="role-input" data-role="ca1" placeholder="姓名...">
        </div>
        <div class="role-item">
          <div class="role-name">乘务员2</div>
          <div class="role-desc">CA2 · 销售</div>
          <input type="text" class="role-input" data-role="ca2" placeholder="姓名...">
        </div>
        <div class="role-item">
          <div class="role-name">列车员</div>
          <div class="role-desc">Attendant</div>
          <input type="text" class="role-input" data-role="attendant" placeholder="姓名...">
        </div>
      </div>
    </div>

    <div class="card">
      <div class="card-title"><span class="icon">📝</span> 2. 对话文本编写</div>
      <p style="font-size:13px; color:#888; margin-bottom:12px;">
        按四大情境顺序编排脚本。每一轮可选择角色，拖动参考句到台词框，或点击“+ 自定义台词”手动/语音输入。支持添加多轮。
      </p>
      <div id="scriptContainer"></div>
      <div class="form-actions" style="margin-top:16px;">
        <button class="btn-save" onclick="saveScript()">💾 保存脚本</button>
        <button class="btn-secondary" onclick="previewScript()">👁 预览对话</button>
        <button class="btn-secondary" onclick="downloadScript()">⬇ 下载文本</button>
        <button class="btn-secondary" onclick="resetScript()">↺ 重置</button>
      </div>
      <div id="previewArea" style="margin-top:16px; display:none;">
        <h3 style="font-size:14px; color:#8b2e2e; margin-bottom:10px;">对话预览</h3>
        <div class="preview-box" id="previewBox"></div>
      </div>
    </div>

    <div class="card">
      <div class="card-title"><span class="icon">🎭</span> 模拟展演评分</div>
      <div class="score-table-wrap">
        <table class="score-table">
          <thead>
            <tr><th>评价维度</th><th>说明</th><th>分值</th><th>得分</th></tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>语言</strong></td>
              <td>英语表达自然、连贯，发音准确，无明显卡顿</td>
              <td class="weight">25</td>
              <td><input type="number" min="0" max="25" value="0" onchange="calcPerform()"></td>
            </tr>
            <tr>
              <td><strong>文化</strong></td>
              <td>闽南建筑文化、海洋文化讲解准确、生动，文化传递到位</td>
              <td class="weight">25</td>
              <td><input type="number" min="0" max="25" value="0" onchange="calcPerform()"></td>
            </tr>
            <tr>
              <td><strong>服务</strong></td>
              <td>服务用语规范、得体、有礼貌，流程完整</td>
              <td class="weight">25</td>
              <td><input type="number" min="0" max="25" value="0" onchange="calcPerform()"></td>
            </tr>
            <tr>
              <td><strong>团队</strong></td>
              <td>角色分工明确，配合默契，衔接流畅</td>
              <td class="weight">25</td>
              <td><input type="number" min="0" max="25" value="0" onchange="calcPerform()"></td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="total-score">
        <span class="label">模拟展演总分</span>
        <span class="value" id="performTotal">0 / 100</span>
      </div>
      <div class="form-actions">
        <button class="btn-save" onclick="savePerform()">💾 保存评分</button>
      </div>
    </div>
  </section>

  <!-- ===== 七、师评成绩 ===== -->
  <section id="section-score" style="display:none;">
    <div class="card">
      <div class="card-title"><span class="icon">⭐</span> 教师综合评价</div>
      <div class="score-table-wrap">
        <table class="score-table">
          <thead>
            <tr><th>评价维度</th><th>说明</th><th>分值</th><th>得分</th></tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>语言</strong></td>
              <td>英语表达自然、连贯，发音准确，无明显卡顿</td>
              <td class="weight">25</td>
              <td><input type="number" min="0" max="25" value="0" onchange="calcFinal()"></td>
            </tr>
            <tr>
              <td><strong>文化</strong></td>
              <td>闽南建筑文化、海洋文化讲解准确、生动，文化传递到位</td>
              <td class="weight">25</td>
              <td><input type="number" min="0" max="25" value="0" onchange="calcFinal()"></td>
            </tr>
            <tr>
              <td><strong>服务</strong></td>
              <td>服务用语规范、得体、有礼貌，流程完整</td>
              <td class="weight">25</td>
              <td><input type="number" min="0" max="25" value="0" onchange="calcFinal()"></td>
            </tr>
            <tr>
              <td><strong>团队</strong></td>
              <td>角色分工明确，配合默契，衔接流畅</td>
              <td class="weight">25</td>
              <td><input type="number" min="0" max="25" value="0" onchange="calcFinal()"></td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="total-score">
        <span class="label">师评加权总分</span>
        <span class="value" id="finalTotal">0 / 100</span>
      </div>
      <h3 style="font-size:14px; color:#8b2e2e; margin:16px 0 10px;">教师评语</h3>
      <div class="comment-box">
        <textarea id="teacherComment" placeholder="请输入教师评语..."></textarea>
      </div>
      <div class="form-actions">
        <button class="btn-save" onclick="saveFinal()">💾 保存师评</button>
      </div>
    </div>

    <div class="card">
      <div class="card-title"><span class="icon">📊</span> 成绩总览</div>
      <div class="overview-grid">
        <div class="overview-card"><div class="ov-label">语言</div><div class="ov-value" id="ovLang">0</div><div class="ov-sub">权重 25%</div></div>
        <div class="overview-card"><div class="ov-label">文化</div><div class="ov-value" id="ovCulture">0</div><div class="ov-sub">权重 25%</div></div>
        <div class="overview-card"><div class="ov-label">服务</div><div class="ov-value" id="ovService">0</div><div class="ov-sub">权重 25%</div></div>
        <div class="overview-card"><div class="ov-label">团队</div><div class="ov-value" id="ovTeam">0</div><div class="ov-sub">权重 25%</div></div>
      </div>
      <div class="final-score-card">
        <span class="label">最终成绩（加权总分）</span>
        <span class="value" id="finalScore">0</span>
      </div>
      <h3 style="font-size:14px; color:#8b2e2e; margin:16px 0 10px;">评分明细</h3>
      <div class="score-table-wrap">
        <table class="score-table">
          <thead>
            <tr><th>评价维度</th><th>得分</th><th>权重</th><th>加权得分</th></tr>
          </thead>
          <tbody>
            <tr><td>语言</td><td id="dtLang">0</td><td>25%</td><td id="wtLang">0</td></tr>
            <tr><td>文化</td><td id="dtCulture">0</td><td>25%</td><td id="wtCulture">0</td></tr>
            <tr><td>服务</td><td id="dtService">0</td><td>25%</td><td id="wtService">0</td></tr>
            <tr><td>团队</td><td id="dtTeam">0</td><td>25%</td><td id="wtTeam">0</td></tr>
            <tr style="background:#fdf0f0; font-weight:600;">
              <td>师评加权总分</td><td colspan="3" id="dtTotal">0分（待评定）</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </section>

  <div class="footer">雅居专列英语·泉州站｜高铁乘务英语实训系统｜数据本地存储</div>
</div>

<div class="toast" id="toast">✅ 操作成功</div>

<script>
/* ================= 导航 ================= */
const sections = ['group', 'case', 'vocab', 'sentence', 'dialog', 'perform', 'score'];
function showSection(name) {
  sections.forEach(s => {
    document.getElementById('section-' + s).style.display = (s === name) ? 'block' : 'none';
  });
  document.querySelectorAll('.navbar-menu a').forEach(a => a.classList.remove('active'));
  const idx = sections.indexOf(name);
  if (idx >= 0) document.querySelectorAll('.navbar-menu a')[idx].classList.add('active');
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

/* ================= Toast ================= */
function showToast(msg) {
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), 2000);
}

/* ================= 小组信息 ================= */
const GROUP_KEY = 'dwelling_train_quanzhou_group_v6';
function saveGroup() {
  const ids = ['className', 'groupName', 'groupNo', 'task', 'teacher'];
  const data = {};
  ids.forEach(id => { const el = document.getElementById(id); if (el) data[id] = el.value; });
  const roles = {};
  document.querySelectorAll('.role-input').forEach(inp => { roles[inp.dataset.role] = inp.value; });
  data.roles = roles;
  localStorage.setItem(GROUP_KEY, JSON.stringify(data));
  showToast('✅ 信息已保存到浏览器');
}
function loadGroup() {
  const saved = localStorage.getItem(GROUP_KEY);
  if (!saved) return;
  try {
    const data = JSON.parse(saved);
    ['className', 'groupName', 'groupNo', 'task', 'teacher'].forEach(id => {
      const el = document.getElementById(id);
      if (el && data[id] !== undefined) el.value = data[id];
    });
    if (data.roles) {
      document.querySelectorAll('.role-input').forEach(inp => {
        if (data.roles[inp.dataset.role] !== undefined) inp.value = data.roles[inp.dataset.role];
      });
    }
  } catch (e) {}
}

/* ================= 语音合成 ================= */
function speakEnglish(text, rate = 1.0) {
  if ('speechSynthesis' in window) {
    const u = new SpeechSynthesisUtterance(text);
    u.lang = 'en-US';
    u.rate = rate;
    speechSynthesis.speak(u);
  } else {
    showToast('当前浏览器不支持语音合成');
  }
}

/* ================= 模拟语音评测 ================= */
function mockSpeechAssessment() {
  return new Promise(resolve => {
    setTimeout(() => {
      const accuracy = Math.floor(Math.random() * 20) + 80;
      const fluency  = Math.floor(Math.random() * 20) + 80;
      const integrity = Math.floor(Math.random() * 15) + 85;
      const total = Math.round((accuracy + fluency + integrity) / 3);
      resolve({
        total_score: total,
        accuracy_score: accuracy,
        fluency_score: fluency,
        integrity_score: integrity
      });
    }, 1200);
  });
}
function renderScorePanel(container, result) {
  container.innerHTML = `
    <div class="score-panel total-row">
      <div class="score-item">
        <span class="label">总分</span>
        <span class="value">${result.total_score}</span>
      </div>
    </div>
    <div class="score-panel">
      <div class="score-item"><span class="label">准确度</span><span class="value">${result.accuracy_score}</span></div>
      <div class="score-item"><span class="label">流畅度</span><span class="value">${result.fluency_score}</span></div>
      <div class="score-item"><span class="label">完整度</span><span class="value">${result.integrity_score}</span></div>
    </div>
  `;
}

/* ================= 词汇 ================= */
const vocabData = [
  { en: 'themed train', ph: '/θiːmd treɪn/', cn: 'n. 主题列车' },
  { en: 'Dwelling Themed Train', ph: '/ˈdwelɪŋ θiːmd treɪn/', cn: 'n. 雅居专列' },
  { en: 'steward', ph: '/ˈstjuːəd/', cn: 'n. 乘务员' },
  { en: 'carriage', ph: '/ˈkærɪdʒ/', cn: 'n. 车厢' },
  { en: 'platform', ph: '/ˈplætfɔːm/', cn: 'n. 站台' },
  { en: 'boarding', ph: '/ˈbɔːdɪŋ/', cn: 'n. 登车' },
  { en: 'announcement', ph: '/əˈnaʊnsmənt/', cn: 'n. 广播通知' },
  { en: 'souvenir', ph: '/ˌsuːvəˈnɪə/', cn: 'n. 纪念品' },
  { en: 'passenger', ph: '/ˈpæsɪndʒə/', cn: 'n. 旅客' },
  { en: 'onboard service', ph: '/ˌɒnbɔːd ˈsɜːvɪs/', cn: 'n. 车厢服务' },
  { en: 'Minnan architecture', ph: '/ˌmɪnˈnæn ˈɑːkɪtektʃə/', cn: 'n. 闽南建筑' },
  { en: 'red brick house', ph: '/red brɪk haʊs/', cn: 'n. 红砖厝' },
  { en: 'swallowtail ridge', ph: '/ˈswɒləʊteɪl rɪdʒ/', cn: 'n. 燕尾脊' },
  { en: 'arcade building', ph: '/ɑːˈkeɪd ˈbɪldɪŋ/', cn: 'n. 骑楼' },
  { en: 'tulou', ph: '/ˌtuːˈləʊ/', cn: 'n. 土楼' },
  { en: 'stone carving', ph: '/stəʊn ˈkɑːvɪŋ/', cn: 'n. 石雕' },
  { en: 'wood carving', ph: '/wʊd ˈkɑːvɪŋ/', cn: 'n. 木雕' },
  { en: 'porcelain', ph: '/ˈpɔːsəlɪn/', cn: 'n. 瓷器' },
  { en: 'Dehua white porcelain', ph: '/dəˈhwɑː waɪt ˈpɔːsəlɪn/', cn: 'n. 德化白瓷' },
  { en: 'Tieguanyin tea', ph: '/ˌtiːˈɡwɑːnˈjɪn tiː/', cn: 'n. 安溪铁观音' },
  { en: "Hui'an stone carving", ph: '/ˌhweɪˈæn stəʊn ˈkɑːvɪŋ/', cn: 'n. 惠安影雕' },
  { en: 'Nanyin music', ph: '/ˌnænˈjɪn ˈmjuːzɪk/', cn: 'n. 南音' },
  { en: 'puppet show', ph: '/ˈpʌpɪt ʃəʊ/', cn: 'n. 木偶戏' },
  { en: 'maritime culture', ph: '/ˈmærɪtaɪm ˈkʌltʃə/', cn: 'n. 海洋文化' },
  { en: 'Quanzhou', ph: '/ˌkwɑːnˈdʒəʊ/', cn: 'n. 泉州' },
  { en: 'Maritime Silk Road', ph: '/ˈmærɪtaɪm sɪlk rəʊd/', cn: 'n. 海上丝绸之路' },
  { en: 'Kaiyuan Temple', ph: '/ˌkaɪˈjuːæn ˈtempl/', cn: 'n. 开元寺' },
  { en: 'Qingjing Mosque', ph: '/ˌtʃɪŋˈdʒɪŋ ˈmɒsk/', cn: 'n. 清净寺' },
  { en: 'Luoyang Bridge', ph: '/ˌlʊəˈjɑːŋ brɪdʒ/', cn: 'n. 洛阳桥' },
  { en: 'Anping Bridge', ph: '/ˌænˈpɪŋ brɪdʒ/', cn: 'n. 安平桥' },
  { en: 'tradition', ph: '/trəˈdɪʃn/', cn: 'n. 传统' },
  { en: 'dwelling', ph: '/ˈdwelɪŋ/', cn: 'n. 民居' },
  { en: 'courtyard', ph: '/ˈkɔːtjɑːd/', cn: 'n. 庭院' },
  { en: 'structure', ph: '/ˈstrʌktʃə/', cn: 'n. 结构' },
  { en: 'craftsmanship', ph: '/ˈkrɑːftsmənʃɪp/', cn: 'n. 工艺' },
  { en: 'architect', ph: '/ˈɑːkɪtekt/', cn: 'n. 建筑师' },
  { en: 'craftsman', ph: '/ˈkrɑːftsmən/', cn: 'n. 工匠' },
  { en: 'heritage', ph: '/ˈherɪtɪdʒ/', cn: 'n. 遗产' },
  { en: 'cultural legacy', ph: '/ˈkʌltʃərəl ˈleɡəsi/', cn: 'n. 文化遗产' },
  { en: 'virtue', ph: '/ˈvɜːtʃuː/', cn: 'n. 美德' }
];

function renderVocab() {
  const grid = document.getElementById('vocabGrid');
  grid.innerHTML = vocabData.map((v, i) => `
    <div class="vocab-card">
      <div class="word">${v.en}</div>
      <div class="phonetic">${v.ph}</div>
      <div class="meaning">${v.cn}</div>
      <div class="actions">
        <button onclick="speakEnglish('${v.en.replace(/'/g, "\\'")}')">🔊 发音</button>
        <button class="record-btn" onclick="startVocabRead(${i})">🎤 跟读评分</button>
      </div>
      <div id="vocabScorePanel${i}"></div>
    </div>
  `).join('');
}

async function startVocabRead(i) {
  const panel = document.getElementById('vocabScorePanel' + i);
  panel.innerHTML = `<div class="score-panel"><div class="loading">🎤 录音识别中，请朗读...</div></div>`;
  const result = await mockSpeechAssessment();
  renderScorePanel(panel, result);
  showToast(`总分 ${result.total_score}｜准确 ${result.accuracy_score}｜流利 ${result.fluency_score}｜完整 ${result.integrity_score}`);
}

/* ================= 句型 ================= */
const sentenceData = [
  {
    title: '情境一：登车迎客',
    items: [
      { en: 'Good morning, welcome aboard the Dwelling Themed Train.', cn: '早上好，欢迎乘坐雅居专列。' },
      { en: 'May I see your ticket and ID card, please?', cn: '请出示您的车票和身份证好吗？' },
      { en: 'Your seat is 12A in Car 5. Please go this way.', cn: '您的座位是5号车厢12A，请这边走。' },
      { en: 'Let me help you with your carry-on.', cn: '我来帮您拿随身行李。' },
      { en: 'Please place your suitcase on the overhead rack.', cn: '请把行李箱放在头顶行李架上。' },
      { en: 'Mind your step and hold the handrail, please.', cn: '请小心台阶，扶好扶手。' },
      { en: 'This is a themed train decorated with traditional Minnan architectural patterns.', cn: '这是一列以传统闽南建筑纹样装饰的主题列车。' },
      { en: 'If you need anything, please let me know.', cn: '如果需要什么，请告诉我。' }
    ]
  },
  {
    title: '情境二：车厢广播·闽南建筑文化',
    items: [
      { en: 'Ladies and gentlemen, welcome aboard the Dwelling Themed Train, bound for Quanzhou, the home of Minnan architecture.', cn: '女士们、先生们，欢迎乘坐雅居专列，本次列车开往闽南建筑之乡泉州。' },
      { en: 'Quanzhou is a historic city known for its red brick houses and swallowtail ridges.', cn: '泉州是一座以红砖厝和燕尾脊闻名的历史名城。' },
      { en: 'Minnan architecture is famous for its red bricks, white stone, and curved roofs.', cn: '闽南建筑以红砖、白石和曲线屋顶著称。' },
      { en: 'The swallowtail ridge is a distinctive feature of traditional Minnan houses.', cn: '燕尾脊是传统闽南民居的显著特征。' },
      { en: "Arcade buildings, or qilou, are a unique part of Quanzhou's urban landscape.", cn: '骑楼是泉州城市景观中独特的一部分。' },
      { en: 'Tulou is a traditional communal dwelling of the Hakka people in Fujian.', cn: '土楼是福建客家人的传统民居。' },
      { en: "During today's journey, you will have the chance to learn about Minnan architecture and feel the charm of maritime civilization.", cn: '在今天的旅途中，您将有机会了解闽南建筑，感受海洋文明的魅力。' }
    ]
  },
  {
    title: '情境三：主题特产销售',
    items: [
      { en: 'Would you like to see some local specialties from Quanzhou?', cn: '您想看看泉州的当地特产吗？' },
      { en: 'This is a piece of Dehua white porcelain, a traditional folk art from Quanzhou.', cn: '这是一件德化白瓷，泉州的传统民间工艺。' },
      { en: 'It is carved by a local craftsman with traditional skills.', cn: '它由当地工匠采用传统技艺雕刻而成。' },
      { en: 'This is a box of Tieguanyin tea, a classic flavor of Fujian.', cn: '这是一盒安溪铁观音，福建的经典风味。' },
      { en: 'The price is 180 yuan, and we offer a 10% discount today.', cn: '价格是180元，今天我们有九折优惠。' },
      { en: 'You can scan the QR code to pay.', cn: '您可以扫码支付。' },
      { en: "Would you like a gift box? It's complimentary.", cn: '您需要礼盒吗？是免费赠送的。' },
      { en: 'This is a perfect souvenir for your family and friends.', cn: '这是带给家人朋友的绝佳纪念品。' }
    ]
  },
  {
    title: '情境四：车厢主题互动',
    items: [
      { en: 'Welcome to our Minnan architecture culture corner.', cn: '欢迎来到我们的闽南建筑文化角。' },
      { en: 'Would you like to join our quiz about Minnan architecture and maritime culture?', cn: '您想参加闽南建筑与海洋文化知识问答吗？' },
      { en: 'Quanzhou is known as the "starting point of the Maritime Silk Road."', cn: '泉州被誉为“海上丝绸之路的起点”。' },
      { en: 'What are the most famous features of Minnan architecture?', cn: '闽南建筑最著名的特征有哪些？' },
      { en: 'They are red brick walls, swallowtail ridges, and stone carvings.', cn: '它们是红砖墙、燕尾脊和石雕。' },
      { en: 'Nanyin music is a traditional art form that reflects Minnan culture.', cn: '南音是反映闽南文化的传统艺术形式。' },
      { en: 'This cultural heritage reflects the wisdom of Minnan architects and craftsmen.', cn: '这份文化遗产体现了闽南建筑师和工匠的智慧。' },
      { en: 'Thank you for participating. We hope you had a memorable time.', cn: '感谢您的参与，希望您度过了难忘的时光。' }
    ]
  }
];

function renderSentences() {
  const container = document.getElementById('sentenceContainer');
  let idx = 0;
  container.innerHTML = sentenceData.map(sec => `
    <div class="sentence-section">
      <div class="section-title">${sec.title}</div>
      ${sec.items.map(item => {
        const currentIdx = idx++;
        return `
        <div class="sentence-item">
          <div class="sentence-main">
            <div class="sentence-text">
              <div class="en">${item.en}</div>
              <div class="cn">${item.cn}</div>
            </div>
            <div class="btn-group">
              <button class="read-btn" onclick="speakEnglish('${item.en.replace(/'/g, "\\'")}', 0.9)">🔊 整句朗读</button>
              <button class="record-btn" onclick="startSentenceRead(${currentIdx})">🎤 跟读评分</button>
            </div>
          </div>
          <div id="sentenceScorePanel${currentIdx}"></div>
        </div>
        `;
      }).join('')}
    </div>
  `).join('');
}

async function startSentenceRead(idx) {
  const panel = document.getElementById('sentenceScorePanel' + idx);
  panel.innerHTML = `<div class="score-panel"><div class="loading">🎤 录音识别中，请朗读...</div></div>`;
  const result = await mockSpeechAssessment();
  renderScorePanel(panel, result);
  showToast(`总分 ${result.total_score}｜准确 ${result.accuracy_score}｜流利 ${result.fluency_score}｜完整 ${result.integrity_score}`);
}

/* ================= 对话卡片 ================= */
const dialogScenes = [
  {
    title: '情境 1：登车迎客',
    desc: '站台迎客、检票验票并引导旅客入座，介绍主题列车特色。',
    lines: [
      { role: '列车员', en: 'Good morning, welcome aboard the Dwelling Themed Train.', cn: '早上好，欢迎乘坐雅居专列。' },
      { role: '乘客', en: 'Thank you. Here is my ticket.', cn: '谢谢，这是我的车票。' },
      { role: '列车员', en: 'May I see your ticket and ID card, please? Your seat is 12A in Car 5. Please go this way.', cn: '请出示您的车票和身份证好吗？您的座位是5号车厢12A，请这边走。' },
      { role: '乘客', en: 'Great. This train looks elegant.', cn: '好的，这列车真雅致。' }
    ]
  },
  {
    title: '情境 2：车厢广播·闽南建筑文化',
    desc: '列车发车后，列车员通过车厢广播介绍闽南建筑与红砖厝文化，旅客聆听并互动。',
    lines: [
      { role: '列车员', en: 'Ladies and gentlemen, welcome aboard the Dwelling Themed Train, bound for Quanzhou, the home of Minnan architecture.', cn: '女士们、先生们，欢迎乘坐雅居专列，本次列车开往闽南建筑之乡泉州。' },
      { role: '列车员', en: 'Quanzhou is a historic city known for its red brick houses and swallowtail ridges.', cn: '泉州是一座以红砖厝和燕尾脊闻名的历史名城。' },
      { role: '乘客', en: 'Wow, that sounds amazing! I can\'t wait to learn more.', cn: '哇，太了不起了！我迫不及待想了解更多。' },
      { role: '列车员', en: 'Minnan architecture is famous for its red bricks, white stone, and curved roofs.', cn: '闽南建筑以红砖、白石和曲线屋顶著称。' }
    ]
  },
  {
    title: '情境 3：主题特产销售',
    desc: '乘务员推车售卖泉州的特产，介绍德化白瓷、安溪铁观音、惠安影雕等特产，旅客询问并购买。',
    lines: [
      { role: '列车员', en: 'Good afternoon. Would you like to see some local specialties from Quanzhou?', cn: '下午好，您想看看泉州的当地特产吗？' },
      { role: '乘客', en: 'Sure. What do you have?', cn: '好的，你们有什么？' },
      { role: '列车员', en: 'This is a piece of Dehua white porcelain, a traditional folk art from Quanzhou.', cn: '这是一件德化白瓷，泉州的传统民间工艺。' },
      { role: '乘客', en: 'It\'s beautiful. How much is it?', cn: '很漂亮，多少钱？' }
    ]
  },
  {
    title: '情境 4：车厢主题互动',
    desc: '乘务员组织闽南建筑文化知识问答，讲解燕尾脊与骑楼，展示闽南传统建筑文化。',
    lines: [
      { role: '列车员', en: 'Welcome to our Minnan architecture culture corner. Would you like to join our quiz about Minnan architecture and maritime culture?', cn: '欢迎来到我们的闽南建筑文化角。您想参加闽南建筑与海洋文化知识问答吗？' },
      { role: '乘客', en: 'I\'d love to. What\'s the quiz about?', cn: '我很乐意。问答是关于什么的？' },
      { role: '列车员', en: 'It\'s about Minnan architecture and maritime culture. The swallowtail ridge is a distinctive feature of traditional Minnan houses.', cn: '是关于闽南建筑与海洋文化的。燕尾脊是传统闽南民居的显著特征。' },
      { role: '乘客', en: 'Interesting! What\'s the question?', cn: '有意思！问题是什么？' }
    ]
  }
];

function renderDialogCards() {
  const container = document.getElementById('dialogContainer');
  container.innerHTML = dialogScenes.map((scene, sIdx) => `
    <div class="dialog-scene">
      <div class="scene-header">
        <div class="scene-name">📌 ${scene.title}</div>
        <div class="scene-desc">${scene.desc}</div>
      </div>
      ${scene.lines.map(line => {
        const roleClass = line.role === '乘客' ? 'role-passenger' : 'role-steward';
        const roleIcon = line.role === '乘客' ? '👤' : '🧑‍✈️';
        return `
          <div class="dialog-line ${roleClass}">
            <div class="role-label">${roleIcon} ${line.role}</div>
            <div class="line-en">${line.en}</div>
            <div class="line-cn">${line.cn}</div>
            <button class="read-btn" onclick="speakEnglish('${line.en.replace(/'/g, "\\'")}', 0.9)">🔊 整句朗读</button>
          </div>
        `;
      }).join('')}
      <div class="scene-controls">
        <button onclick="playScene(${sIdx})">▶ 整段播放</button>
        <button onclick="recordScene(${sIdx}, this)">⏺ 录音</button>
        <button onclick="playRecord(${sIdx})">▶ 播放</button>
        <button onclick="deleteRecord(${sIdx}, this)">🗑 删除</button>
        <span class="status-tag" id="sceneStatus${sIdx}">🎙 未录音</span>
      </div>
    </div>
  `).join('');
}

function playScene(sIdx) {
  const scene = dialogScenes[sIdx];
  let i = 0;
  function playNext() {
    if (i >= scene.lines.length) return;
    const line = scene.lines[i];
    const u = new SpeechSynthesisUtterance(line.en);
    u.lang = 'en-US';
    u.rate = 0.9;
    u.onend = () => { i++; playNext(); };
    speechSynthesis.speak(u);
  }
  playNext();
  showToast('▶ 开始整段播放');
}

let sceneRecorders = {};
function recordScene(sIdx, btn) {
  if (sceneRecorders[sIdx] && sceneRecorders[sIdx].recording) {
    sceneRecorders[sIdx].stop();
    btn.classList.remove('recording');
    btn.textContent = '⏺ 录音';
    return;
  }
  if (!navigator.mediaDevices || !window.MediaRecorder) {
    showToast('当前浏览器不支持录音');
    return;
  }
  navigator.mediaDevices.getUserMedia({ audio: true }).then(stream => {
    const recorder = new MediaRecorder(stream);
    const chunks = [];
    recorder.ondataavailable = e => chunks.push(e.data);
    recorder.onstop = () => {
      const blob = new Blob(chunks, { type: 'audio/webm' });
      sceneRecorders[sIdx].blob = blob;
      sceneRecorders[sIdx].recording = false;
      stream.getTracks().forEach(t => t.stop());
      const status = document.getElementById('sceneStatus' + sIdx);
      if (status) { status.textContent = '✅ 已录音'; status.classList.add('done'); }
      showToast('✅ 录音完成');
    };
    recorder.start();
    sceneRecorders[sIdx] = { recorder, recording: true };
    btn.classList.add('recording');
    btn.textContent = '⏹ 停止';
    showToast('🎤 正在录音...');
  }).catch(err => {
    showToast('无法访问麦克风：' + err.message);
  });
}

function playRecord(sIdx) {
  const rec = sceneRecorders[sIdx];
  if (!rec || !rec.blob) { showToast('暂无录音'); return; }
  const url = URL.createObjectURL(rec.blob);
  const audio = new Audio(url);
  audio.play();
  showToast('▶ 播放录音');
}

function deleteRecord(sIdx, btn) {
  if (sceneRecorders[sIdx]) {
    if (sceneRecorders[sIdx].recorder && sceneRecorders[sIdx].recording) {
      sceneRecorders[sIdx].recorder.stop();
    }
    delete sceneRecorders[sIdx];
  }
  const status = document.getElementById('sceneStatus' + sIdx);
  if (status) { status.textContent = '🎙 未录音'; status.classList.remove('done'); }
  showToast('🗑 已删除录音');
}

/* ================= 多轮脚本编排 ================= */
const SCRIPT_KEY = 'dwelling_train_quanzhou_script_v6';

const refSentences = {
  scene1: [
    'Good morning, welcome aboard the Dwelling Themed Train.',
    'May I see your ticket and ID card, please?',
    'Your seat is 12A in Car 5. Please go this way.',
    'Let me help you with your carry-on.',
    'Please place your suitcase on the overhead rack.',
    'Mind your step and hold the handrail, please.',
    'This is a themed train decorated with traditional Minnan architectural patterns.',
    'If you need anything, please let me know.'
  ],
  scene2: [
    'Ladies and gentlemen, welcome aboard the Dwelling Themed Train, bound for Quanzhou, the home of Minnan architecture.',
    'Quanzhou is a historic city known for its red brick houses and swallowtail ridges.',
    'Minnan architecture is famous for its red bricks, white stone, and curved roofs.',
    'The swallowtail ridge is a distinctive feature of traditional Minnan houses.',
    "Arcade buildings, or qilou, are a unique part of Quanzhou's urban landscape.",
    'Tulou is a traditional communal dwelling of the Hakka people in Fujian.',
    "During today's journey, you will have the chance to learn about Minnan architecture and feel the charm of maritime civilization."
  ],
  scene3: [
    'Would you like to see some local specialties from Quanzhou?',
    'This is a piece of Dehua white porcelain, a traditional folk art from Quanzhou.',
    'It is carved by a local craftsman with traditional skills.',
    'This is a box of Tieguanyin tea, a classic flavor of Fujian.',
    'The price is 180 yuan, and we offer a 10% discount today.',
    'You can scan the QR code to pay.',
    "Would you like a gift box? It's complimentary.",
    'This is a perfect souvenir for your family and friends.'
  ],
  scene4: [
    'Welcome to our Minnan architecture culture corner.',
    'Would you like to join our quiz about Minnan architecture and maritime culture?',
    'Quanzhou is known as the "starting point of the Maritime Silk Road."',
    'What are the most famous features of Minnan architecture?',
    'They are red brick walls, swallowtail ridges, and stone carvings.',
    'Nanyin music is a traditional art form that reflects Minnan culture.',
    'This cultural heritage reflects the wisdom of Minnan architects and craftsmen.',
    'Thank you for participating. We hope you had a memorable time.'
  ]
};

const sceneConfig = [
  { id: 'scene1', title: '情境 1：登车迎客' },
  { id: 'scene2', title: '情境 2：车厢广播' },
  { id: 'scene3', title: '情境 3：主题特产销售' },
  { id: 'scene4', title: '情境 4：车厢主题互动' }
];

const ROLE_OPTIONS = ['列车员', '乘客'];
let scriptState = {};

function initScriptState() {
  scriptState = {};
  sceneConfig.forEach(sc => {
    scriptState[sc.id] = [ { role: '列车员', text: '', manual: false } ];
  });
}

function loadScriptState() {
  const saved = localStorage.getItem(SCRIPT_KEY);
  if (!saved) return false;
  try {
    const data = JSON.parse(saved);
    if (data && typeof data === 'object') {
      scriptState = data;
      sceneConfig.forEach(sc => {
        if (!Array.isArray(scriptState[sc.id])) {
          scriptState[sc.id] = [{ role: '列车员', text: '', manual: false }];
        }
      });
      return true;
    }
  } catch (e) {}
  return false;
}

function saveScriptState() {
  localStorage.setItem(SCRIPT_KEY, JSON.stringify(scriptState));
}

function renderScript() {
  const container = document.getElementById('scriptContainer');
  if (!container) return;
  container.innerHTML = sceneConfig.map(sc => `
    <div class="script-scene" data-scene="${sc.id}">
      <div class="scene-title">📌 ${sc.title}</div>
      <div style="font-size:12px; color:#888; margin-bottom:6px;">参考句型（可拖拽到下方任意轮次的台词框）</div>
      <div class="ref-sentences">
        ${refSentences[sc.id].map((s, i) => `
          <div class="ref-sentence" draggable="true"
               data-scene="${sc.id}" data-index="${i}"
               ondragstart="onDragStart(event, '${sc.id}', ${i})"
               ondragend="onDragEnd(event)">
            <span class="grip">⋮⋮</span>
            <span>${s}</span>
          </div>
        `).join('')}
      </div>
      <div class="turns-list" id="turns-${sc.id}">
        ${renderTurns(sc.id)}
      </div>
      <div class="scene-add-turn">
        <button onclick="addTurn('${sc.id}')">+ 添加一轮对话</button>
      </div>
    </div>
  `).join('');
}

function renderTurns(sceneId) {
  const turns = scriptState[sceneId] || [];
  return turns.map((turn, idx) => `
    <div class="turn-item" data-turn-index="${idx}">
      <div class="turn-header">
        <div class="turn-index">#${idx + 1}</div>
        <select class="turn-role-select" onchange="changeTurnRole('${sceneId}', ${idx}, this.value)">
          ${ROLE_OPTIONS.map(r => `<option value="${r}" ${turn.role === r ? 'selected' : ''}>${r}</option>`).join('')}
        </select>
      </div>
      <div class="turn-content">
        <div class="turn-dropzone"
             data-scene="${sceneId}" data-turn-index="${idx}"
             ondragover="onTurnDragOver(event)"
             ondragleave="onTurnDragLeave(event)"
             ondrop="onTurnDrop(event)">
          ${turn.text
            ? `<span class="turn-text ${turn.manual ? 'manual' : ''}">${turn.text}</span>`
            : `<span class="empty-hint">拖拽上方参考句到此处，或点击下方“+ 自定义台词”添加</span>`}
        </div>
        <div class="turn-custom-area" id="turn-custom-${sceneId}-${idx}">
          <input type="text" placeholder="输入自定义台词..."
                 value="${turn.manual ? turn.text.replace(/"/g, '&quot;') : ''}"
                 onkeydown="if(event.key==='Enter'){updateTurnText('${sceneId}',${idx},this.value);this.value='';}">
          <button class="btn-voice" onclick="startVoiceInputTurn('${sceneId}', ${idx})" title="语音输入">🎤 语音</button>
          <button class="btn-add" onclick="updateTurnTextFromInput('${sceneId}', ${idx})">添加</button>
          <button class="btn-cancel" onclick="toggleTurnCustom('${sceneId}', ${idx})">取消</button>
        </div>
      </div>
      <div class="turn-actions">
        <button onclick="toggleTurnCustom('${sceneId}', ${idx})">+ 自定义</button>
        <button onclick="moveTurn('${sceneId}', ${idx}, -1)">↑ 上移</button>
        <button onclick="moveTurn('${sceneId}', ${idx}, 1)">↓ 下移</button>
        <button class="danger" onclick="removeTurn('${sceneId}', ${idx})">✕ 删除</button>
      </div>
    </div>
  `).join('');
}

function refreshTurns(sceneId) {
  const el = document.getElementById(`turns-${sceneId}`);
  if (el) el.innerHTML = renderTurns(sceneId);
}

function addTurn(sceneId) {
  scriptState[sceneId].push({ role: '列车员', text: '', manual: false });
  refreshTurns(sceneId);
  saveScriptState();
}

function removeTurn(sceneId, idx) {
  if (scriptState[sceneId].length <= 1) {
    showToast('至少保留一轮对话');
    return;
  }
  scriptState[sceneId].splice(idx, 1);
  refreshTurns(sceneId);
  saveScriptState();
}

function moveTurn(sceneId, idx, dir) {
  const arr = scriptState[sceneId];
  const newIdx = idx + dir;
  if (newIdx < 0 || newIdx >= arr.length) return;
  [arr[idx], arr[newIdx]] = [arr[newIdx], arr[idx]];
  refreshTurns(sceneId);
  saveScriptState();
}

function changeTurnRole(sceneId, idx, role) {
  scriptState[sceneId][idx].role = role;
  saveScriptState();
}

function toggleTurnCustom(sceneId, idx) {
  const el = document.getElementById(`turn-custom-${sceneId}-${idx}`);
  if (!el) return;
  el.classList.toggle('active');
  if (el.classList.contains('active')) {
    el.querySelector('input').focus();
  }
}

function updateTurnTextFromInput(sceneId, idx) {
  const el = document.getElementById(`turn-custom-${sceneId}-${idx}`);
  const input = el.querySelector('input');
  const val = input.value.trim();
  if (!val) { showToast('请输入内容'); return; }
  updateTurnText(sceneId, idx, val);
  input.value = '';
  el.classList.remove('active');
}

function updateTurnText(sceneId, idx, text) {
  if (!text.trim()) return;
  scriptState[sceneId][idx].text = text.trim();
  scriptState[sceneId][idx].manual = true;
  refreshTurns(sceneId);
  saveScriptState();
  showToast('✅ 已更新台词');
}

/* ===== 拖拽逻辑 ===== */
let dragData = null;
function onDragStart(e, sceneId, index) {
  dragData = { sceneId, index, text: refSentences[sceneId][index] };
  e.target.classList.add('dragging');
  e.dataTransfer.effectAllowed = 'copy';
  e.dataTransfer.setData('text/plain', dragData.text);
}
function onDragEnd(e) {
  e.target.classList.remove('dragging');
  document.querySelectorAll('.turn-dropzone').forEach(s => s.classList.remove('drag-over'));
}

function onTurnDragOver(e) {
  e.preventDefault();
  e.currentTarget.classList.add('drag-over');
  e.dataTransfer.dropEffect = 'copy';
}
function onTurnDragLeave(e) {
  e.currentTarget.classList.remove('drag-over');
}
function onTurnDrop(e) {
  e.preventDefault();
  const zone = e.currentTarget;
  zone.classList.remove('drag-over');
  const sceneId = zone.dataset.scene;
  const turnIdx = Number(zone.dataset.turnIndex);
  let text = '';
  if (dragData) text = dragData.text;
  else text = e.dataTransfer.getData('text/plain');
  if (!text) return;

  const turn = scriptState[sceneId][turnIdx];
  if (turn.text && turn.text.trim()) {
    turn.text = turn.text + '\n' + text;
  } else {
    turn.text = text;
  }
  turn.manual = false;
  refreshTurns(sceneId);
  saveScriptState();
  showToast('✅ 已添加参考句');
  dragData = null;
}

/* ===== 语音输入（每轮） ===== */
let recognition = null;
let isRecording = false;
function startVoiceInputTurn(sceneId, idx) {
  const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
  if (!SpeechRecognition) {
    showToast('当前浏览器不支持语音识别，请用 Chrome 或 Edge');
    return;
  }
  if (isRecording) {
    if (recognition) recognition.stop();
    isRecording = false;
    return;
  }
  recognition = new SpeechRecognition();
  recognition.lang = 'en-US';
  recognition.interimResults = false;
  recognition.maxAlternatives = 1;
  recognition.onstart = () => {
    isRecording = true;
    showToast('🎤 正在录音，请说话...');
  };
  recognition.onresult = (event) => {
    const text = event.results[0][0].transcript;
    const turn = scriptState[sceneId][idx];
    if (turn.text && turn.text.trim()) turn.text += '\n' + text;
    else turn.text = text;
    turn.manual = true;
    refreshTurns(sceneId);
    saveScriptState();
    showToast('✅ 已识别语音');
  };
  recognition.onerror = (event) => {
    showToast('语音识别出错：' + event.error);
    isRecording = false;
  };
  recognition.onend = () => {
    isRecording = false;
  };
  recognition.start();
}

/* ===== 保存 / 预览 / 下载 / 重置 ===== */
function saveScript() {
  saveScriptState();
  showToast('✅ 脚本已保存到浏览器');
}

function previewScript() {
  const box = document.getElementById('previewBox');
  let html = '';
  sceneConfig.forEach(sc => {
    html += `【${sc.title}】\n`;
    const turns = scriptState[sc.id] || [];
    if (turns.length === 0) {
      html += '  （暂无对话）\n';
    } else {
      turns.forEach((t, i) => {
        html += `  #${i + 1} ${t.role}：${t.text || '（暂无台词）'}\n`;
      });
    }
    html += '\n';
  });
  box.textContent = html;
  document.getElementById('previewArea').style.display = 'block';
  box.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
}

function downloadScript() {
  let text = '雅居专列英语·泉州站 — 对话脚本\n\n';
  sceneConfig.forEach(sc => {
    text += `【${sc.title}】\n`;
    const turns = scriptState[sc.id] || [];
    if (turns.length === 0) {
      text += '  （暂无对话）\n';
    } else {
      turns.forEach((t, i) => {
        text += `  #${i + 1} ${t.role}：${t.text || '（暂无台词）'}\n`;
      });
    }
    text += '\n';
  });
  const blob = new Blob([text], { type: 'text/plain;charset=utf-8' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = '雅居专列-对话脚本.txt';
  a.click();
  URL.revokeObjectURL(url);
  showToast('✅ 已下载对话文本');
}

function resetScript() {
  if (!confirm('确定要重置所有情境的脚本内容吗？')) return;
  initScriptState();
  saveScriptState();
  renderScript();
  showToast('✅ 已重置为默认流程');
}

/* ================= 评分 ================= */
function calcPerform() {
  const inputs = document.querySelectorAll('#section-perform input[type="number"]');
  let total = 0;
  inputs.forEach(inp => { total += Number(inp.value) || 0; });
  document.getElementById('performTotal').textContent = total + ' / 100';
}
function savePerform() { showToast('✅ 模拟展演评分已保存'); }

function calcFinal() {
  const inputs = document.querySelectorAll('#section-score input[type="number"]');
  const vals = [];
  inputs.forEach(inp => vals.push(Number(inp.value) || 0));
  const [lang, culture, service, team] = vals;
  document.getElementById('finalTotal').textContent = (lang + culture + service + team) + ' / 100';
  document.getElementById('ovLang').textContent = lang;
  document.getElementById('ovCulture').textContent = culture;
  document.getElementById('ovService').textContent = service;
  document.getElementById('ovTeam').textContent = team;
  document.getElementById('dtLang').textContent = lang;
  document.getElementById('dtCulture').textContent = culture;
  document.getElementById('dtService').textContent = service;
  document.getElementById('dtTeam').textContent = team;
  document.getElementById('wtLang').textContent = (lang * 0.25).toFixed(1);
  document.getElementById('wtCulture').textContent = (culture * 0.25).toFixed(1);
  document.getElementById('wtService').textContent = (service * 0.25).toFixed(1);
  document.getElementById('wtTeam').textContent = (team * 0.25).toFixed(1);
  const total = lang * 0.25 + culture * 0.25 + service * 0.25 + team * 0.25;
  document.getElementById('finalScore').textContent = total.toFixed(1);
  document.getElementById('dtTotal').textContent = total.toFixed(1) + '分' + (total === 0 ? '（待评定）' : '');
}
function saveFinal() { showToast('✅ 师评成绩已保存'); }

/* ================= 初始化 ================= */
document.addEventListener('DOMContentLoaded', () => {
  loadGroup();
  renderVocab();
  renderSentences();
  renderDialogCards();
  initScriptState();
  const hasSaved = loadScriptState();
  if (!hasSaved) {
    scriptState.scene1[0] = { role: '列车员', text: refSentences.scene1[0], manual: false };
    scriptState.scene1.push({ role: '乘客', text: 'Thank you. Here is my ticket.', manual: false });
    scriptState.scene2[0] = { role: '列车员', text: refSentences.scene2[0], manual: false };
    scriptState.scene3[0] = { role: '列车员', text: refSentences.scene3[0], manual: false };
    scriptState.scene4[0] = { role: '列车员', text: refSentences.scene4[0], manual: false };
    saveScriptState();
  }
  renderScript();
});
</script>

</body>
</html>
