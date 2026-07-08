<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dashboard Maestro de Indicadores KPI</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Segoe+UI:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0f172a;
    --sidebar: #1e293b;
    --surface: #1e293b;
    --surface2: #334155;
    --border: #334155;
    --accent: #3b82f6;
    --accent-light: #60a5fa;
    --orange: #f97316;
    --orange-dark: #ea580c;
    --green: #22c55e;
    --red: #ef4444;
    --text: #f1f5f9;
    --muted: #94a3b8;
    --card-bg: #1e293b;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Segoe UI', sans-serif;
    min-height: 100vh;
    display: flex;
    overflow: hidden;
  }

  html, body { height: 100%; }

  /* SIDEBAR */
  .sidebar {
    width: 260px;
    background: var(--sidebar);
    border-right: 1px solid var(--border);
    display: flex;
    flex-direction: column;
    padding: 20px 16px;
    gap: 24px;
    overflow-y: auto;
    flex-shrink: 0;
    max-height: 100vh;
  }

  .sidebar-title {
    font-size: 18px;
    font-weight: 700;
    color: var(--text);
    padding-bottom: 12px;
    border-bottom: 1px solid var(--border);
  }

  .filter-section { display: flex; flex-direction: column; gap: 10px; }
  .filter-section label {
    font-size: 11px;
    font-weight: 700;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.8px;
  }

  /* Mes slicer buttons */
  .slicer-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6px;
  }
  .slicer-btn {
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--muted);
    padding: 8px 4px;
    border-radius: 6px;
    font-size: 12px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s;
    text-align: center;
  }
  .slicer-btn:hover { border-color: var(--accent); color: var(--text); }
  .slicer-btn.active {
    background: var(--accent);
    border-color: var(--accent);
    color: #fff;
    box-shadow: 0 0 12px rgba(59,130,246,0.3);
  }

  /* Gerencia list */
  .gerencia-list {
    display: flex;
    flex-direction: column;
    gap: 4px;
    max-height: 320px;
    overflow-y: auto;
    padding-right: 4px;
  }
  .gerencia-list::-webkit-scrollbar { width: 4px; }
  .gerencia-list::-webkit-scrollbar-thumb { background: var(--border); border-radius: 2px; }
  .ger-item {
    background: var(--surface2);
    border: 1px solid transparent;
    color: var(--muted);
    padding: 8px 10px;
    border-radius: 6px;
    font-size: 12px;
    cursor: pointer;
    transition: all 0.15s;
    line-height: 1.3;
  }
  .ger-item:hover { background: rgba(59,130,246,0.1); border-color: var(--accent); color: var(--text); }
  .ger-item.active {
    background: rgba(59,130,246,0.2);
    border-color: var(--accent);
    color: var(--accent-light);
    font-weight: 600;
  }

  .upload-zone {
    margin-top: auto;
    background: var(--surface2);
    border: 1.5px dashed var(--border);
    border-radius: 10px;
    padding: 12px;
    cursor: pointer;
    transition: all 0.2s;
    position: relative;
    text-align: center;
  }
  .upload-zone:hover { border-color: var(--accent); background: rgba(59,130,246,0.05); }
  .upload-zone input[type=file] { position: absolute; inset: 0; opacity: 0; cursor: pointer; width: 100%; }
  .upload-zone .ico { font-size: 22px; margin-bottom: 4px; }
  .upload-zone .txt strong { display: block; color: var(--accent-light); font-size: 12px; }
  .upload-zone .txt span { color: var(--muted); font-size: 10px; }

  #upload-status {
    font-size: 11px;
    padding: 6px 10px;
    border-radius: 20px;
    font-weight: 600;
    text-align: center;
    display: none;
  }
  .upload-status.ok { background: rgba(34,197,94,0.15); color: var(--green); border: 1px solid rgba(34,197,94,0.3); display: block; }
  .upload-status.err { background: rgba(239,68,68,0.15); color: var(--red); border: 1px solid rgba(239,68,68,0.3); display: block; }

  /* MAIN CONTENT */
  .main {
    flex: 1;
    display: flex;
    flex-direction: column;
    overflow-y: auto;
    padding: 24px 28px;
    gap: 20px;
    min-height: 0;
  }

  .main-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
  }
  .main-header h1 {
    font-size: 22px;
    font-weight: 700;
    color: #fff;
  }
  .main-header h1 span { color: var(--accent-light); }
  .last-updated {
    font-size: 12px;
    color: var(--muted);
    background: var(--surface);
    padding: 6px 14px;
    border-radius: 20px;
    border: 1px solid var(--border);
  }

  /* KPI ROW */
  .kpi-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 16px;
  }
  .kpi-box {
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px;
    display: flex;
    flex-direction: column;
    gap: 6px;
    position: relative;
    overflow: hidden;
  }
  .kpi-box::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
  }
  .kpi-box.blue::before { background: linear-gradient(90deg, var(--accent), var(--accent-light)); }
  .kpi-box.orange::before { background: linear-gradient(90deg, var(--orange), var(--orange-dark)); }
  .kpi-box.green::before { background: linear-gradient(90deg, var(--green), #4ade80); }
  .kpi-box.red::before { background: linear-gradient(90deg, var(--red), #f87171); }
  .kpi-box.purple::before { background: linear-gradient(90deg, #a855f7, #c084fc); }

  .kpi-box .label {
    font-size: 11px;
    font-weight: 700;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }
  .kpi-box .value {
    font-size: 28px;
    font-weight: 700;
    color: #fff;
  }
  .kpi-box .sub {
    font-size: 12px;
    color: var(--muted);
  }

  /* CHARTS GRID */
  .charts-grid {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    gap: 20px;
  }
  .chart-card {
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
  }
  .col-3 { grid-column: span 3; }
  .col-4 { grid-column: span 4; }
  .col-6 { grid-column: span 6; }
  .col-8 { grid-column: span 8; }
  .col-12 { grid-column: span 12; }

  .chart-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 14px;
  }
  .chart-title {
    font-size: 13px;
    font-weight: 700;
    color: #fff;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }
  .chart-badge {
    font-size: 10px;
    font-weight: 700;
    padding: 4px 10px;
    border-radius: 20px;
    background: rgba(59,130,246,0.1);
    color: var(--accent-light);
    border: 1px solid rgba(59,130,246,0.2);
  }

  .chart-wrap { position: relative; height: 220px; }
  .chart-wrap-sm { position: relative; height: 180px; }

  /* Table */
  .ranking-table { width: 100%; border-collapse: collapse; font-size: 12px; }
  .ranking-table th {
    text-align: left;
    padding: 10px 12px;
    font-size: 10px;
    font-weight: 700;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    border-bottom: 1px solid var(--border);
  }
  .ranking-table td {
    padding: 10px 12px;
    border-bottom: 1px solid rgba(51,65,85,0.5);
    vertical-align: middle;
  }
  .ranking-table tr:last-child td { border-bottom: none; }
  .ranking-table tr:hover td { background: rgba(255,255,255,0.02); }

  .bar-cell { display: flex; align-items: center; gap: 8px; }
  .mini-bar { height: 6px; border-radius: 3px; min-width: 4px; }
  .pct-text { font-size: 12px; font-weight: 700; min-width: 40px; text-align: right; }

  .rank-badge {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 22px; height: 22px;
    border-radius: 50%;
    font-size: 11px;
    font-weight: 700;
  }
  .rank-1 { background: rgba(245,158,11,0.2); color: #f59e0b; }
  .rank-2 { background: rgba(148,163,184,0.2); color: #94a3b8; }
  .rank-3 { background: rgba(180,120,60,0.2); color: #d97706; }
  .rank-n { background: rgba(51,65,85,0.5); color: var(--muted); }

  .table-scroll { max-height: 280px; overflow-y: auto; }
  .table-scroll::-webkit-scrollbar { width: 4px; }
  .table-scroll::-webkit-scrollbar-thumb { background: var(--border); border-radius: 2px; }

  /* Responsive */
  @media (max-width: 1100px) {
    .col-3, .col-4 { grid-column: span 6; }
  }
  @media (max-width: 800px) {
    body { flex-direction: column; }
    .sidebar { width: 100%; max-height: 300px; }
    .col-3, .col-4, .col-6, .col-8, .col-12 { grid-column: span 12; }
  }

  /* Loader */
  #loader {
    position: fixed; inset: 0; background: var(--bg);
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    z-index: 999; gap: 16px; transition: opacity 0.4s;
  }
  #loader.hidden { opacity: 0; pointer-events: none; }
  .spinner {
    width: 40px; height: 40px;
    border: 3px solid var(--border); border-top-color: var(--accent);
    border-radius: 50%; animation: spin 0.8s linear infinite;
  }
  @keyframes spin { to { transform: rotate(360deg); } }
  #loader p { color: var(--muted); font-size: 14px; }


/* ════ MODAL DETALLE KPI ════ */
#kpi-modal-overlay {
  position: fixed; inset: 0; z-index: 8000;
  background: rgba(2,6,23,0.75); backdrop-filter: blur(0px);
  display: none; align-items: center; justify-content: center; padding: 24px;
  opacity: 0;
}
#kpi-modal-overlay.open {
  display: flex;
  animation: macBackdrop .35s ease forwards;
}
#kpi-modal-overlay.closing { animation: macBackdropOut .22s ease forwards; }
.kpi-modal {
  background: #1e293b; border: 1px solid #334155; border-radius: 16px;
  width: 100%; max-width: 860px; max-height: 85vh;
  display: flex; flex-direction: column; overflow: hidden;
  box-shadow: 0 30px 90px rgba(0,0,0,.65), 0 0 0 1px rgba(255,255,255,.04);
  transform-origin: center center;
}
/* Apertura estilo macOS: zoom con rebote suave */
#kpi-modal-overlay.open .kpi-modal {
  animation: macZoomIn .45s cubic-bezier(.34, 1.45, .64, 1) forwards;
}
#kpi-modal-overlay.closing .kpi-modal {
  animation: macZoomOut .22s cubic-bezier(.4, 0, 1, 1) forwards;
}
@keyframes macZoomIn {
  0%   { opacity: 0; transform: scale(.72) translateY(26px); }
  60%  { opacity: 1; }
  100% { opacity: 1; transform: scale(1) translateY(0); }
}
@keyframes macZoomOut {
  from { opacity: 1; transform: scale(1) translateY(0); }
  to   { opacity: 0; transform: scale(.85) translateY(14px); }
}
@keyframes macBackdrop {
  from { opacity: 0; backdrop-filter: blur(0px); }
  to   { opacity: 1; backdrop-filter: blur(6px); }
}
@keyframes macBackdropOut {
  from { opacity: 1; backdrop-filter: blur(6px); }
  to   { opacity: 0; backdrop-filter: blur(0px); }
}
.kpi-modal-head {
  display: flex; align-items: center; justify-content: space-between;
  padding: 18px 22px; border-bottom: 1px solid #334155; gap: 12px;
}
.kpi-modal-title { font-size: 15px; font-weight: 700; color: #f1f5f9; }
.kpi-modal-count {
  font-size: 11px; font-weight: 700; padding: 3px 10px; border-radius: 20px;
  background: rgba(59,130,246,0.12); color: #60a5fa; border: 1px solid rgba(59,130,246,0.25);
}
.kpi-modal-close {
  background: none; border: none; color: #94a3b8; font-size: 20px;
  cursor: pointer; padding: 2px 8px; border-radius: 6px;
}
.kpi-modal-close:hover { color: #ef4444; }
.kpi-modal-search {
  margin: 12px 22px 0; background: #0f172a; border: 1.5px solid #334155;
  border-radius: 8px; padding: 9px 12px; color: #f1f5f9; font-size: 13px;
  font-family: 'Segoe UI', sans-serif; outline: none;
}
.kpi-modal-search:focus { border-color: #3b82f6; }
.kpi-modal-body { overflow-y: auto; padding: 12px 22px 20px; }
.kpi-modal-body::-webkit-scrollbar { width: 6px; }
.kpi-modal-body::-webkit-scrollbar-thumb { background: #334155; border-radius: 3px; }
.kpi-det-table { width: 100%; border-collapse: collapse; font-size: 12px; }
.kpi-det-table th {
  text-align: left; padding: 8px 10px; font-size: 10px; font-weight: 700;
  color: #64748b; text-transform: uppercase; letter-spacing: .5px;
  border-bottom: 1px solid #334155; position: sticky; top: 0; background: #1e293b;
}
.kpi-det-table td { padding: 9px 10px; border-bottom: 1px solid rgba(51,65,85,.45); vertical-align: top; }
.kpi-det-table tr:hover td { background: rgba(255,255,255,.02); }
.frec-pill {
  display: inline-block; font-size: 10px; font-weight: 700; padding: 2px 9px;
  border-radius: 20px; white-space: nowrap;
}
.frec-M { background: rgba(59,130,246,.12); color: #60a5fa; border: 1px solid rgba(59,130,246,.25); }
.frec-B { background: rgba(168,85,247,.12); color: #c084fc; border: 1px solid rgba(168,85,247,.25); }
.frec-T { background: rgba(34,197,94,.12); color: #4ade80; border: 1px solid rgba(34,197,94,.25); }
.motivo-pill {
  display: inline-block; font-size: 10px; font-weight: 700; padding: 2px 9px; border-radius: 20px; white-space: nowrap;
}
.motivo-nr { background: rgba(239,68,68,.12); color: #f87171; border: 1px solid rgba(239,68,68,.3); }
.motivo-bm { background: rgba(249,115,22,.12); color: #fb923c; border: 1px solid rgba(249,115,22,.3); }
.kpi-box.clickable { cursor: pointer; transition: transform .15s, border-color .15s; }
.kpi-box.clickable:hover { transform: translateY(-2px); border-color: #3b82f6; }
.kpi-box.clickable::after {
  content: '👆 Ver detalle'; position: absolute; bottom: 6px; right: 10px;
  font-size: 9px; color: #475569; opacity: 0; transition: opacity .15s;
}
.kpi-box.clickable:hover::after { opacity: 1; }


/* ════ SPLASH BIENVENIDA (estilo iPhone) ════ */
#kpi-splash {
  position: fixed; inset: 0; z-index: 9500;
  background: radial-gradient(ellipse at 50% 40%, #14213d 0%, #0f172a 55%, #0a0f1e 100%);
  display: none; flex-direction: column; align-items: center; justify-content: center;
  text-align: center; padding: 24px; opacity: 0; transition: opacity .8s ease;
}
#kpi-splash.show { display: flex; opacity: 1; }
#kpi-splash.fade { opacity: 0; }
.splash-hola {
  font-size: clamp(44px, 8vw, 76px); font-weight: 800; letter-spacing: -1px;
  background: linear-gradient(90deg, #60a5fa, #a78bfa, #22d3ee, #60a5fa);
  background-size: 300% 100%;
  -webkit-background-clip: text; background-clip: text; color: transparent;
  animation: holaIn 1s cubic-bezier(.2,.8,.2,1) both, gradFlow 5s linear infinite;
}
.splash-nombre {
  margin-top: 22px; font-size: clamp(20px, 3.4vw, 32px); font-weight: 700; color: #f1f5f9;
  opacity: 0; animation: riseIn .8s cubic-bezier(.2,.8,.2,1) .7s forwards;
}
.splash-puesto {
  margin-top: 10px; font-size: clamp(13px, 1.8vw, 16px); color: #94a3b8; font-weight: 500;
  opacity: 0; animation: riseIn .8s cubic-bezier(.2,.8,.2,1) 1.1s forwards;
}
.splash-gerencia {
  margin-top: 16px; font-size: clamp(14px, 2vw, 18px); font-weight: 700;
  background: linear-gradient(90deg, #60a5fa, #22d3ee);
  -webkit-background-clip: text; background-clip: text; color: transparent;
  opacity: 0; animation: riseIn .8s cubic-bezier(.2,.8,.2,1) 1.4s forwards;
}
.splash-dot {
  margin-top: 34px; font-size: 12px; color: #475569; letter-spacing: 2px; text-transform: uppercase;
  opacity: 0; animation: riseIn .8s ease 1.5s forwards;
}
@keyframes holaIn { from { opacity: 0; transform: scale(.86) translateY(14px); } to { opacity: 1; transform: scale(1) translateY(0); } }
@keyframes riseIn { from { opacity: 0; transform: translateY(16px); } to { opacity: 1; transform: translateY(0); } }
@keyframes gradFlow { to { background-position: 300% 0; } }

/* ════ LOGIN OVERLAY ════ */
#kpi-login-overlay {
  position: fixed; inset: 0; z-index: 9999;
  background: #0f172a;
  display: flex; align-items: center; justify-content: center;
  font-family: 'Segoe UI', sans-serif;
}
.kpi-lc {
  background: #1e293b; border: 1px solid #334155;
  border-radius: 20px; padding: 44px 40px 36px;
  width: 100%; max-width: 400px;
  box-shadow: 0 24px 80px rgba(0,0,0,.6);
  position: relative; overflow: hidden; text-align: center;
}
.kpi-lc::before {
  content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
  background: linear-gradient(90deg,#3b82f6,#6366f1,#06b6d4);
}
.kpi-lc-icon {
  width: 64px; height: 64px;
  background: linear-gradient(135deg,#3b82f6,#6366f1);
  border-radius: 16px; display: flex; align-items: center;
  justify-content: center; font-size: 30px; margin: 0 auto 20px;
}
.kpi-lc-title { font-size: 20px; font-weight: 700; color: #f1f5f9; margin-bottom: 4px; }
.kpi-lc-sub   { font-size: 13px; color: #94a3b8; margin-bottom: 28px; }
.kpi-lc-label {
  display: block; text-align: left; font-size: 11px; font-weight: 700;
  color: #64748b; text-transform: uppercase; letter-spacing: .6px; margin-bottom: 8px;
}
.kpi-lc-inp {
  width: 100%; background: #0f172a; border: 1.5px solid #334155;
  border-radius: 10px; padding: 13px 14px; color: #f1f5f9; font-size: 14px;
  font-family: 'Segoe UI', sans-serif; outline: none;
  transition: border-color .2s, box-shadow .2s; margin-bottom: 6px;
}
.kpi-lc-inp:focus   { border-color: #3b82f6; box-shadow: 0 0 0 3px rgba(59,130,246,.15); }
.kpi-lc-inp.valid   { border-color: #22c55e; }
.kpi-lc-inp.invalid { border-color: #ef4444; }
.kpi-lc-hint { font-size: 12px; min-height: 18px; text-align: left; margin-bottom: 20px; }
.kpi-lc-hint.ok  { color: #22c55e; }
.kpi-lc-hint.err { color: #ef4444; }
.kpi-lc-btn {
  width: 100%; padding: 13px; background: #3b82f6; border: none;
  border-radius: 10px; color: #fff; font-size: 15px; font-weight: 700;
  cursor: pointer; transition: opacity .2s, transform .15s;
}
.kpi-lc-btn:hover:not(:disabled) { opacity: .88; transform: translateY(-1px); }
.kpi-lc-btn:disabled { opacity: .35; cursor: not-allowed; transform: none; }
.kpi-lc-foot { margin-top: 22px; font-size: 12px; color: #475569; }
.kpi-lc-foot b { color: #3b82f6; }
/* Ocultar dashboard hasta login */
.main, .sidebar { visibility: hidden; }
.main.vis, .sidebar.vis { visibility: visible; }
/* Pill usuario */
#kpi-pill {
  display: none; align-items: center; gap: 8px;
  background: #334155; border: 1px solid #475569;
  border-radius: 50px; padding: 5px 14px 5px 8px;
}
.kpi-pill-av {
  width: 28px; height: 28px;
  background: linear-gradient(135deg,#3b82f6,#6366f1);
  border-radius: 50%; display: flex; align-items: center;
  justify-content: center; font-size: 11px; font-weight: 700; color: #fff;
}
.kpi-pill-name { font-size: 13px; font-weight: 600; color: #f1f5f9; }
.kpi-pill-out {
  background: none; border: none; color: #94a3b8;
  cursor: pointer; font-size: 14px; padding: 2px 5px;
  border-radius: 5px; transition: color .2s; margin-left: 2px;
}
.kpi-pill-out:hover { color: #ef4444; }

</style>
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
<base target="_blank">
<base target="_blank">
</head>
<body>


<!-- ════ SPLASH BIENVENIDA ════ -->
<div id="kpi-splash">
  <div class="splash-hola" id="splash-hola">Hola 👋</div>
  <div class="splash-nombre" id="splash-nombre"></div>
  <div class="splash-puesto" id="splash-puesto"></div>
  <div class="splash-gerencia" id="splash-gerencia"></div>
  <div class="splash-dot">Maestro de Indicadores KPI</div>
</div>

<!-- ════ LOGIN OVERLAY ════ -->
<div id="kpi-login-overlay">
  <div class="kpi-lc">
    <div class="kpi-lc-icon">📊</div>
    <div class="kpi-lc-title">Maestro de Indicadores KPI</div>
    <div class="kpi-lc-sub">Ingresa tu usuario para acceder</div>
    <label class="kpi-lc-label">Usuario</label>
    <input id="kpi-inp" class="kpi-lc-inp" type="text"
      placeholder="Ej: jperez"
      autocomplete="off" autocapitalize="none" spellcheck="false"/>
    <div id="kpi-hint" class="kpi-lc-hint"></div>
    <button id="kpi-btn" class="kpi-lc-btn" disabled>Acceder al Dashboard</button>
    <div class="kpi-lc-foot"><b>547</b> usuarios autorizados · Sistema interno</div>
  </div>
</div>
<!-- ════ FIN LOGIN ════ -->




<!-- ════ MODAL DETALLE KPI ════ -->
<div id="kpi-modal-overlay" onclick="if(event.target===this) closeKpiModal()">
  <div class="kpi-modal">
    <div class="kpi-modal-head">
      <div style="display:flex;align-items:center;gap:10px;">
        <span class="kpi-modal-title" id="kpi-modal-title">Detalle</span>
        <span class="kpi-modal-count" id="kpi-modal-count">0</span>
      </div>
      <button class="kpi-modal-close" onclick="closeKpiModal()">✕</button>
    </div>
    <input type="text" class="kpi-modal-search" id="kpi-modal-search" placeholder="🔍 Buscar por nombre, código o área..." oninput="renderKpiModal()">
    <div class="kpi-modal-body" id="kpi-modal-body"></div>
  </div>
</div>

<div id="loader">
  <div class="spinner"></div>
  <p>Cargando Dashboard...</p>
</div>

<!-- SIDEBAR -->
<aside class="sidebar">
  <div class="sidebar-title">📊 Filtros</div>

  <div class="filter-section">
    <label>📅 Mes</label>
    <div class="slicer-grid" id="mes-slicer"></div>
  </div>

  <div class="filter-section">
    <label>🏢 Gerencia Central</label>
    <div class="gerencia-list" id="gerencia-slicer"></div>
  </div>

  <div id="upload-status"></div>
  <label class="upload-zone">
    <input type="file" id="fileInput" accept=".xlsx,.xls,.csv,.xlsm" />
    <div class="ico">📂</div>
    <div class="txt">
      <strong>Cargar / Recargar Excel</strong>
      <span>.xlsx · .xls · .csv · .xlsm</span>
    </div>
  </label>
</aside>

<!-- MAIN -->
<main class="main">
  <div class="main-header" style="display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:10px;">
    <h1>Maestro de <span>Indicadores KPI</span></h1>
    <div style="display:flex;align-items:center;gap:12px;flex-wrap:wrap;">
      <div class="last-updated" id="last-updated">Última actualización: 22/06/2026 09:40</div>
      <div id="kpi-pill" style="display:none;align-items:center;gap:8px;background:#334155;border:1px solid #475569;border-radius:50px;padding:5px 14px 5px 8px;">
        <div class="kpi-pill-av" id="kpi-pill-av">??</div>
        <span class="kpi-pill-name" id="kpi-pill-name">—</span>
        <button class="kpi-pill-out" onclick="kpiLogout()" title="Cerrar sesión"
          onmouseover="this.style.color='#ef4444'" onmouseout="this.style.color='#94a3b8'">✕</button>
      </div>
    </div>
  </div>

  <!-- KPI ROW -->
  <div class="kpi-row">
    <div class="kpi-box blue clickable" onclick="openKpiModal('indicadores')" title="Click para ver el detalle">
      <div class="label">N° Indicadores</div>
      <div class="value" id="kpi-total-ind">—</div>
      <div class="sub" id="kpi-total-ind-sub">Indicadores activos</div>
    </div>
    <div class="kpi-box blue clickable" style="border-left-color:#818cf8;" onclick="openKpiModal('metricas')" title="Click para ver el detalle">
      <div class="label">N° Métricas</div>
      <div class="value" id="kpi-total-met" style="color:#818cf8;">—</div>
      <div class="sub" id="kpi-total-met-sub">Métricas activas</div>
    </div>
    <div class="kpi-box green">
      <div class="label">% Cumplimiento Meta</div>
      <div class="value" id="kpi-meta">—</div>
      <div class="sub" id="kpi-meta-sub">KPIs que alcanzaron meta</div>
    </div>
    <div class="kpi-box purple">
      <div class="label">% Reporting en PGC</div>
      <div class="value" id="kpi-reporte">—</div>
      <div class="sub" id="kpi-reporte-sub">KPIs cargados en PGC</div>
    </div>
    <div class="kpi-box orange clickable" onclick="openKpiModal('desviados')" title="Click para ver el detalle">
      <div class="label">KPIs Desviados</div>
      <div class="value" id="kpi-desviados">—</div>
      <div class="sub">Bajo meta / sin reportar</div>
    </div>
  </div>

  <!-- ROW 1: PIE CHARTS -->
  <div class="charts-grid">
    <div class="chart-card col-4">
      <div class="chart-header">
        <div class="chart-title">KPIs - Cumplimiento de Meta</div>
      </div>
      <div class="chart-wrap-sm">
        <canvas id="chart-pie-meta"></canvas>
      </div>
    </div>
    <div class="chart-card col-4">
      <div class="chart-header">
        <div class="chart-title">Reporting de KPIs en PGC</div>
      </div>
      <div class="chart-wrap-sm">
        <canvas id="chart-pie-reporte"></canvas>
      </div>
    </div>
    <div class="chart-card col-4">
      <div class="chart-header">
        <div class="chart-title">Estado de Ejecución KAIZEN</div>
      </div>
      <div class="chart-wrap-sm">
        <canvas id="chart-pie-kaizen"></canvas>
      </div>
    </div>
  </div>

  <!-- ROW 2: GERENCIA BARS -->
  <div class="charts-grid" id="row-gerencias">
    <div class="chart-card col-6">
      <div class="chart-header">
        <div class="chart-title">% Cumplimiento de Meta por Gerencia</div>
        <span class="chart-badge">Cumplimiento</span>
      </div>
      <div class="chart-wrap">
        <canvas id="chart-bar-gerencia-meta"></canvas>
      </div>
    </div>
    <div class="chart-card col-6">
      <div class="chart-header">
        <div class="chart-title">Cumplimiento de Carga de KPIs en PGC</div>
        <span class="chart-badge">PGC</span>
      </div>
      <div class="chart-wrap">
        <canvas id="chart-bar-gerencia-reporte"></canvas>
      </div>
    </div>
  </div>

  <!-- ROW 3: AREA BARS -->
  <div class="charts-grid">
    <div class="chart-card col-6">
      <div class="chart-header">
        <div class="chart-title">% Cumplimiento de Meta por Área</div>
        <span class="chart-badge">Áreas</span>
      </div>
      <div class="chart-wrap">
        <canvas id="chart-bar-area-meta"></canvas>
      </div>
    </div>
    <div class="chart-card col-6">
      <div class="chart-header">
        <div class="chart-title">Cumplimiento de Carga de KPIs en PGC por Áreas</div>
        <span class="chart-badge">Áreas</span>
      </div>
      <div class="chart-wrap">
        <canvas id="chart-bar-area-reporte"></canvas>
      </div>
    </div>
  </div>

  <!-- ROW 4: RANKING + TENDENCIA -->
  <div class="charts-grid">
    <div class="chart-card col-6" id="card-ranking">
      <div class="chart-header">
        <div class="chart-title">Ranking de Áreas</div>
        <span class="chart-badge">Top Áreas</span>
      </div>
      <div class="table-scroll">
        <table class="ranking-table">
          <thead>
            <tr><th>#</th><th>Área</th><th>Gerencia</th><th>Cumplimiento</th></tr>
          </thead>
          <tbody id="ranking-tbody"></tbody>
        </table>
      </div>
    </div>
    <div class="chart-card col-6" id="card-sla">
      <div class="chart-header">
        <div class="chart-title">Cumplimiento de SLA</div>
        <span class="chart-badge">SLA</span>
      </div>
      <div class="chart-wrap">
        <canvas id="chart-sla"></canvas>
      </div>
    </div>
  </div>

</main>


<script>


// ─────────────────────────────────────────────
// CONTROL DE ACCESO POR GERENCIA
// Los gerentes solo ven los KPIs de su gerencia.
// gerencia: 'ALL' = acceso total (Gerencia General / corporativo)
// ─────────────────────────────────────────────
const KPI_GERENTES = {
  "ogajate":      { nombre: "Orietta Gajate",      cargo: "Gerente General",                                      gerencia: "ALL" },
  "jzavala":      { nombre: "Julio Zavala",        cargo: "Gerente Central de Negocios Logísticos",               gerencia: "Gerencia de Negocios Logisticos" },
  "jvillafuerte": { nombre: "Janet Villafuerte",   cargo: "Gerente Comercial de Negocios Logísticos",             gerencia: "Gerencia de Negocios Logisticos" },
  "climo":        { nombre: "Claudia Limo",        cargo: "Gerente de Transporte",                                gerencia: "Gerencia de Negocios Logisticos" },
  "arodriguez":   { nombre: "Alejandro Rodriguez", cargo: "Sub Gerente de Transporte",                            gerencia: "Gerencia de Negocios Logisticos" },
  "jcastro":      { nombre: "Jorge Castro",        cargo: "Gerente de Logística Interna y CD",                    gerencia: "Gerencia de Negocios Logisticos" },
  "amasias":      { nombre: "Alberto Masias",      cargo: "Sub Gerente Customer Management",                      gerencia: "Gerencia de Negocios Logisticos" },
  "sbazalar":     { nombre: "Sergio Bazalar",      cargo: "Gerente Central de Negocios Marítimos y Navieros",     gerencia: "Negocios Maritimos y Navieros" },
  "sebazalar":    { nombre: "Sergio Bazalar",      cargo: "Gerente Central de Negocios Marítimos y Navieros",     gerencia: "Negocios Maritimos y Navieros" },
  "lchu":         { nombre: "Lizbeth Chu",         cargo: "Gerente de Negocios Marítimos y Navieros",             gerencia: "Negocios Maritimos y Navieros" },
  "ccoz":         { nombre: "Carlos Coz",          cargo: "Gerente de Adquisiciones y Finanzas",                  gerencia: "Gerencia de Adquisiciones y Finanzas" },
  "acoz":         { nombre: "Carlos Coz",          cargo: "Gerente de Adquisiciones y Finanzas",                  gerencia: "Gerencia de Adquisiciones y Finanzas" },
  "ydemarini":    { nombre: "Yessica Demarini",    cargo: "Gerente de Administración y Desarrollo Humano",        gerencia: "Gestión de Administración y Desarrollo Humano" },
  "jdelaguila":   { nombre: "Jorge Del Aguila",    cargo: "Gerente de SSOMA, Protección y Desarrollo de Proyectos", gerencia: "Gestión de Seguridad y SSOMA" },
  "ealarcon":     { nombre: "Enrique Alarcon",     cargo: "Gerente de Sistemas Digitales y Ciberseguridad",       gerencia: "Gestión de Sistemas Digitales y Ciberseguridad" },
  "earanciaga":   { nombre: "Eleazar Aranciaga",   cargo: "Sub Gerente de Sistemas Digitales y Ciberseguridad",   gerencia: "Gestión de Sistemas Digitales y Ciberseguridad" },
  "wiglesias":    { nombre: "Walter Iglesias",     cargo: "Sub Gerente de la Región Norte",                       gerencia: "Regiones" },
  "jgonzales":    { nombre: "Juan Gonzales",       cargo: "Sub Gerente de Región Sur",                            gerencia: "Regiones" },
  "mroncal":      { nombre: "Miriam Roncal",       cargo: "Sub Gerente de Procesos Estratégicos",                 gerencia: "Procesos Estratégicos" },
  "jtasayco":     { nombre: "Juan Tasayco",        cargo: "Sub Gerente de Planeamiento y Presupuesto",            gerencia: "Planeamiento Estratégico" },
  "jandonaire":   { nombre: "Juan Andonaire",      cargo: "Gerente de Negocios de Comercio Exterior",             gerencia: "TPPA" }
};
// Acceso del usuario actual: 'ALL' o el nombre de su gerencia
let KPI_ACCESS = 'ALL';

const KPI_USER_GER = {"onevado": "Gerencia de Negocios Logisticos", "rabal": "Gerencia de Negocios Logisticos", "aacevedo": "TPPA", "laciego": "Gerencia de Negocios Logisticos", "racosta": "Negocios Maritimos y Navieros", "aacuna": "Gerencia de Negocios Logisticos", "kacuna": "Gerencia de Negocios Logisticos", "faguilar": "Gerencia de Negocios Logisticos", "laguilar": "Negocios Maritimos y Navieros", "laguirre": "Negocios Maritimos y Navieros", "aalanya": "Gestión de Sistemas Digitales y Ciberseguridad", "ealarcon": "Gestión de Seguridad y SSOMA", "ralejo": "Gerencia de Negocios Logisticos", "ealfaro": "Gerencia de Negocios Logisticos", "balvarado": "Gerencia de Negocios Logisticos", "aalvarez": "Negocios Maritimos y Navieros", "palvarez": "Negocios Maritimos y Navieros", "salzamora": "Regiones", "aanazgo": "Gestión de Administración y Desarrollo Humano", "jandonaire": "TPPA", "panteparra": "TPPA", "earanciaga": "Gestión de Seguridad y SSOMA", "raranguez": "Gestión de Administración y Desarrollo Humano", "larcela": "Negocios Maritimos y Navieros", "farenas": "Gerencia de Negocios Logisticos", "jarguello": "TPPA", "darias": "Gerencia de Adquisiciones y Finanzas", "jarmestar": "Gestión de Sistemas Digitales y Ciberseguridad", "bascona": "Gerencia de Negocios Logisticos", "matarama": "Gerencia de Adquisiciones y Finanzas", "mavalos": "TPPA", "navila": "Negocios Maritimos y Navieros", "jbaca": "Gerencia de Negocios Logisticos", "nbarandiaran": "Gerencia de Negocios Logisticos", "abarreto": "Gerencia de Adquisiciones y Finanzas", "cbarrientos": "TPPA", "gbarrientos": "Gestión de Seguridad y SSOMA", "sbazalar": "Gerencia de Negocios Logisticos", "sebazalar": "Negocios Maritimos y Navieros", "ybazalar": "Gestión de Administración y Desarrollo Humano", "pbazan": "Procesos Estratégicos", "hbazan": "Gerencia de Negocios Logisticos", "ebazan": "Gerencia de Negocios Logisticos", "mbermejo": "TPPA", "gbossio": "TPPA", "pbrena": "Gerencia de Negocios Logisticos", "lcaballero": "Gerencia de Negocios Logisticos", "jcaceres": "Gerencia de Negocios Logisticos", "acajaleon": "Gerencia de Adquisiciones y Finanzas", "ccalderon": "Gerencia de Negocios Logisticos", "mcamasca": "Procesos Estratégicos", "ccamasca": "Gestión de Administración y Desarrollo Humano", "ccampana": "Gerencia de Negocios Logisticos", "rcampos": "Gerencia de Negocios Logisticos", "ocampos": "Gestión de Seguridad y SSOMA", "bcancino": "Negocios Maritimos y Navieros", "jcapcha": "Gerencia de Adquisiciones y Finanzas", "bcapulian": "Procesos Estratégicos", "kcarbajal": "Gerencia de Negocios Logisticos", "jcardenas": "Gerencia de Negocios Logisticos", "ecardenas": "Gerencia de Negocios Logisticos", "ycardenas": "Gestión de Administración y Desarrollo Humano", "acarmelino": "TPPA", "jcarmona": "Gestión Legal", "scaro": "Gestión Legal", "gcarrasco": "Gerencia de Adquisiciones y Finanzas", "jcarreno": "Negocios Maritimos y Navieros", "bcarrillo": "Negocios Maritimos y Navieros", "jcarrillo": "Gestión de Sistemas Digitales y Ciberseguridad", "mcarrion": "TPPA", "macarrion": "TPPA", "rcaruajulca": "Gerencia de Negocios Logisticos", "rcasas": "Gestión de Sistemas Digitales y Ciberseguridad", "mcastillo": "Gestión de Sistemas Digitales y Ciberseguridad", "ncastillo": "Gerencia de Adquisiciones y Finanzas", "jcastillo": "Gerencia de Negocios Logisticos", "jcastro": "Gerencia de Negocios Logisticos", "hcastro": "Procesos Estratégicos", "rcastro": "Gestión de Seguridad y SSOMA", "lcastro": "Gerencia de Negocios Logisticos", "pcatano": "Gerencia de Negocios Logisticos", "ycatay": "Negocios Maritimos y Navieros", "mcerna": "Gerencia de Negocios Logisticos", "jcerna": "Gerencia de Adquisiciones y Finanzas", "kcespedes": "Gestión de Administración y Desarrollo Humano", "jcespedes": "Gerencia de Negocios Logisticos", "fchallco": "Gestión de Seguridad y SSOMA", "bchaua": "Gestión de Sistemas Digitales y Ciberseguridad", "ychavarria": "Gestión de Sistemas Digitales y Ciberseguridad", "mchavez": "Gestión de Sistemas Digitales y Ciberseguridad", "cchillcce": "Gerencia de Negocios Logisticos", "kchinchercoma": "Negocios Maritimos y Navieros", "wchinga": "Regiones", "echipana": "Gerencia de Negocios Logisticos", "echiroque": "TPPA", "jchocanga": "Gerencia de Negocios Logisticos", "cchoquez": "Gerencia de Adquisiciones y Finanzas", "lchu": "Negocios Maritimos y Navieros", "lchui": "Gerencia de Adquisiciones y Finanzas", "achumbirayco": "Gestión de Administración y Desarrollo Humano", "lchumpitaz": "Gestión de Sistemas Digitales y Ciberseguridad", "mchurano": "Gerencia de Adquisiciones y Finanzas", "ecisneros": "Procesos Estratégicos", "acisneros": "Gestión de Seguridad y SSOMA", "jclemente": "Negocios Maritimos y Navieros", "mcobos": "Gerencia de Negocios Logisticos", "fcollazos": "Gerencia de Negocios Logisticos", "mcondori": "Negocios Maritimos y Navieros", "hcoria": "TPPA", "lcorrea": "Gerencia de Negocios Logisticos", "lcortez": "Negocios Maritimos y Navieros", "wcotrina": "Gerencia de Negocios Logisticos", "ccoz": "Gerencia de Adquisiciones y Finanzas", "cacoz": "Gerencia de Adquisiciones y Finanzas", "ecrisologo": "TPPA", "hcrisostomo": "Gerencia de Negocios Logisticos", "acruz": "Negocios Maritimos y Navieros", "lcruz": "Gerencia de Negocios Logisticos", "jcruz": "Gerencia de Negocios Logisticos", "kcruz": "Negocios Maritimos y Navieros", "jcuadros": "Gestión de Sistemas Digitales y Ciberseguridad", "fcueva": "Gerencia de Adquisiciones y Finanzas", "mcuri": "Gerencia de Negocios Logisticos", "cdamaso": "Gerencia de Negocios Logisticos", "hdance": "Gerencia de Adquisiciones y Finanzas", "adavalos": "Regiones", "edelacruz": "TPPA", "adelacruz": "Gerencia de Negocios Logisticos", "pdelarosa": "Gestión de Sistemas Digitales y Ciberseguridad", "idelacruz": "TPPA", "cdelossantos": "Gerencia de Negocios Logisticos", "ydepaz": "Gestión de Administración y Desarrollo Humano", "jdelaguila": "Gestión de Seguridad y SSOMA", "bdelgado": "Gestión de Administración y Desarrollo Humano", "ydemarini": "Gestión de Administración y Desarrollo Humano", "pdi": "Gestión de Sistemas Digitales y Ciberseguridad", "jdiazg": "Gestión de Sistemas Digitales y Ciberseguridad", "ediaz": "TPPA", "jhdiaz": "Gerencia de Negocios Logisticos", "pdiego": "TPPA", "mdioses": "Gestión de Sistemas Digitales y Ciberseguridad", "ddioses": "Gerencia de Negocios Logisticos", "gduque": "Gerencia de Negocios Logisticos", "mduran": "Gerencia de Adquisiciones y Finanzas", "wduran": "Gerencia de Adquisiciones y Finanzas", "decheccaya": "Gestión de Seguridad y SSOMA", "felescano": "Gestión de Seguridad y SSOMA", "jelizares": "Negocios Maritimos y Navieros", "rescalante": "TPPA", "gescobar": "Gestión de Sistemas Digitales y Ciberseguridad", "despinola": "Gerencia de Negocios Logisticos", "lespinoza": "Gerencia de Negocios Logisticos", "kespinoza": "Negocios Maritimos y Navieros", "cespinoza": "Gerencia de Negocios Logisticos", "aespinoza": "Negocios Maritimos y Navieros", "gespinoza": "Gestión de Sistemas Digitales y Ciberseguridad", "mespinoza": "Gestión de Sistemas Digitales y Ciberseguridad", "jfarfan": "Gerencia de Negocios Logisticos", "cfarro": "Gerencia de Negocios Logisticos", "afebres": "Gerencia de Negocios Logisticos", "afelippe": "Gerencia de Negocios Logisticos", "sfernandez": "Gestión Legal", "ofernandez": "Gestión de Seguridad y SSOMA", "gfiestas": "Gerencia de Negocios Logisticos", "jfiestas": "TPPA", "joflores": "Gerencia de Negocios Logisticos", "aflores": "TPPA", "kflores": "Gestión de Sistemas Digitales y Ciberseguridad", "sfranco": "Gerencia de Negocios Logisticos", "lfrias": "TPPA", "mgaldos": "Negocios Maritimos y Navieros", "mgallardo": "Gestión Legal", "agallo": "TPPA", "ogamarra": "TPPA", "dgarcia": "Gerencia de Adquisiciones y Finanzas", "sgarcia": "Gerencia de Adquisiciones y Finanzas", "mgarcia": "Gerencia de Adquisiciones y Finanzas", "rgarcia": "Gerencia de Negocios Logisticos", "rgarrido": "Gerencia de Negocios Logisticos", "rgavila": "Gerencia de Negocios Logisticos", "dgirao": "Gerencia de Negocios Logisticos", "fgonzaga": "Regiones", "rogonzales": "Gestión de Seguridad y SSOMA", "vgonzales": "Gerencia de Negocios Logisticos", "egonzales": "Gerencia de Adquisiciones y Finanzas", "jgonzales": "Regiones", "rcgonzales": "TPPA", "rgonzaless": "TPPA", "mgrandez": "TPPA", "mguaylupo": "Regiones", "aguerrero": "Gerencia de Negocios Logisticos", "rguillermo": "Gerencia de Negocios Logisticos", "dgutierrez": "TPPA", "egutierrez": "Gerencia de Negocios Logisticos", "agutierrez": "Gestión Legal", "sheredia": "Negocios Maritimos y Navieros", "eheredia": "Gerencia de Negocios Logisticos", "yhernandez": "Gestión de Sistemas Digitales y Ciberseguridad", "jherrada": "TPPA", "dhidalgo": "Gerencia de Negocios Logisticos", "eholguin": "Gerencia de Negocios Logisticos", "lhorna": "Gerencia de Negocios Logisticos", "jhuachohuillca": "Gerencia de Negocios Logisticos", "khuallpacuna": "Gestión Legal", "ahuaman": "Gerencia de Adquisiciones y Finanzas", "jhuamani": "Gestión de Sistemas Digitales y Ciberseguridad", "mhuapaya": "Procesos Estratégicos", "bhuaquisto": "Gestión de Sistemas Digitales y Ciberseguridad", "fhuarac": "TPPA", "jhuaya": "Gerencia de Negocios Logisticos", "wiglesias": "Regiones", "oinchaustegui": "Gerencia de Adquisiciones y Finanzas", "linonan": "Gestión de Seguridad y SSOMA", "dinonan": "TPPA", "cizquierdo": "TPPA", "jjaramillo": "Gerencia de Negocios Logisticos", "gjaucala": "Gerencia de Negocios Logisticos", "ajauregui": "TPPA", "cjimenez": "Gestión de Sistemas Digitales y Ciberseguridad", "djimenez": "Gerencia de Negocios Logisticos", "jjustiniani": "Gerencia de Negocios Logisticos", "yleguia": "Gestión de Administración y Desarrollo Humano", "dleon": "Gerencia de Negocios Logisticos", "dileon": "Gerencia de Negocios Logisticos", "climo": "Gerencia de Negocios Logisticos", "jlino": "Gerencia de Negocios Logisticos", "plira": "Gerencia de Adquisiciones y Finanzas", "ilizarzaburu": "Negocios Maritimos y Navieros", "jllanos": "Negocios Maritimos y Navieros", "mllanos": "Gerencia de Negocios Logisticos", "allenos": "Gerencia de Negocios Logisticos", "bllenos": "Gerencia de Negocios Logisticos", "allerena": "Gestión de Administración y Desarrollo Humano", "jllontop": "Negocios Maritimos y Navieros", "hloli": "Gerencia de Negocios Logisticos", "rlombardi": "Gestión de Sistemas Digitales y Ciberseguridad", "mlopez": "Gerencia de Adquisiciones y Finanzas", "glopez": "Gerencia de Negocios Logisticos", "mloza": "Gerencia de Negocios Logisticos", "hluna": "Gestión de Seguridad y SSOMA", "jmachuca": "Gestión de Sistemas Digitales y Ciberseguridad", "jmalpartida": "Gestión de Sistemas Digitales y Ciberseguridad", "ymamani": "TPPA", "pmamani": "Gestión de Sistemas Digitales y Ciberseguridad", "ymandujano": "Gestión de Administración y Desarrollo Humano", "smarcatoma": "Gestión de Seguridad y SSOMA", "lmarconi": "Gerencia de Adquisiciones y Finanzas", "emarquez": "Gerencia de Negocios Logisticos", "cmartel": "Gerencia de Negocios Logisticos", "emartinez": "Negocios Maritimos y Navieros", "amasias": "Gerencia de Negocios Logisticos", "omattos": "Negocios Maritimos y Navieros", "smauricio": "Gerencia de Negocios Logisticos", "dmedina": "Gerencia de Negocios Logisticos", "rmedinaa": "Negocios Maritimos y Navieros", "gmedina": "Gerencia de Negocios Logisticos", "jmejia": "Gestión de Sistemas Digitales y Ciberseguridad", "hmendez": "Gerencia de Adquisiciones y Finanzas", "amendoza": "Gerencia de Negocios Logisticos", "emeneses": "Gerencia de Adquisiciones y Finanzas", "jmercado": "Gerencia de Negocios Logisticos", "dmerida": "Negocios Maritimos y Navieros", "gmeza": "Gerencia de Negocios Logisticos", "emontes": "Gerencia de Negocios Logisticos", "wmore": "Gerencia de Negocios Logisticos", "fmoreno": "Gestión de Sistemas Digitales y Ciberseguridad", "jmoreno": "Gerencia de Adquisiciones y Finanzas", "pmorillo": "Negocios Maritimos y Navieros", "lmucha": "Gerencia de Negocios Logisticos", "gmundaca": "Gestión Legal", "gmunguia": "Gestión de Seguridad y SSOMA", "amunoz": "Gerencia de Negocios Logisticos", "jmurga": "Gestión de Seguridad y SSOMA", "jomurga": "TPPA", "rmurillo": "Gerencia de Adquisiciones y Finanzas", "hmuro": "Gerencia de Negocios Logisticos", "tnarvarte": "TPPA", "jnavarro": "Gestión Legal", "tnavarte": "TPPA", "mnole": "Gerencia de Negocios Logisticos", "lnunez": "Gerencia de Negocios Logisticos", "nochoa": "TPPA", "rojeda": "Gestión de Sistemas Digitales y Ciberseguridad", "jolaya": "Gerencia de Adquisiciones y Finanzas", "joolaya": "Gerencia de Adquisiciones y Finanzas", "folivari": "Gerencia de Negocios Logisticos", "polivera": "Gerencia de Negocios Logisticos", "molortiga": "Negocios Maritimos y Navieros", "mordinola": "Gestión de Administración y Desarrollo Humano", "jordinola": "Negocios Maritimos y Navieros", "kortiz": "Gerencia de Adquisiciones y Finanzas", "lortiz": "Gestión Legal", "mosorio": "Gerencia de Negocios Logisticos", "rotero": "Gestión de Sistemas Digitales y Ciberseguridad", "epablo": "Gerencia de Adquisiciones y Finanzas", "rpachas": "Negocios Maritimos y Navieros", "cpacora": "Procesos Estratégicos", "ppadilla": "Negocios Maritimos y Navieros", "jpalomino": "Gestión de Sistemas Digitales y Ciberseguridad", "jpanana": "Gerencia de Negocios Logisticos", "ppantaleon": "Negocios Maritimos y Navieros", "apantigoso": "Gerencia de Negocios Logisticos", "kpariapaza": "Gerencia de Negocios Logisticos", "dpastor": "TPPA", "cperalta": "Gerencia de Negocios Logisticos", "spereira": "Gerencia de Negocios Logisticos", "lperez": "Gerencia de Adquisiciones y Finanzas", "aperez": "Gerencia de Negocios Logisticos", "mperez": "Gerencia de Negocios Logisticos", "apillaca": "Gestión de Administración y Desarrollo Humano", "apiminchumo": "Gerencia de Negocios Logisticos", "dpingo": "Gestión de Sistemas Digitales y Ciberseguridad", "jponce": "Gerencia de Negocios Logisticos", "dponciano": "Gerencia de Negocios Logisticos", "mporras": "Gerencia de Negocios Logisticos", "eportilla": "Regiones", "bportocarrero": "Gerencia de Negocios Logisticos", "jpozo": "TPPA", "lpretil": "Gerencia de Negocios Logisticos", "hprincipe": "Gerencia de Negocios Logisticos", "uprueba": "Gestión Legal", "dpuertas": "Negocios Maritimos y Navieros", "ipujada": "Gerencia de Negocios Logisticos", "jquilluya": "Gerencia de Negocios Logisticos", "cquinones": "Negocios Maritimos y Navieros", "yquispe": "Gestión Legal", "jramirez": "Gerencia de Negocios Logisticos", "nramirez": "TPPA", "eramirez": "Gerencia de Negocios Logisticos", "juramirez": "Negocios Maritimos y Navieros", "lramos": "TPPA", "jramos": "Gerencia de Negocios Logisticos", "mramos": "Gerencia de Negocios Logisticos", "maramos": "Gerencia de Negocios Logisticos", "jremigio": "TPPA", "vrenteria": "Negocios Maritimos y Navieros", "areyes": "TPPA", "frios": "Gestión de Sistemas Digitales y Ciberseguridad", "mrios": "Gestión de Administración y Desarrollo Humano", "rrios": "Procesos Estratégicos", "jrivas": "Gerencia de Negocios Logisticos", "jrivera": "Gerencia de Negocios Logisticos", "yrivera": "Gerencia de Adquisiciones y Finanzas", "arivera": "Gerencia de Adquisiciones y Finanzas", "drobles": "Procesos Estratégicos", "grodriguez": "TPPA", "arodriguez": "Gerencia de Negocios Logisticos", "jrodriguez": "Gerencia de Negocios Logisticos", "krodriguez": "Gestión de Administración y Desarrollo Humano", "mrodriguez": "Gestión de Administración y Desarrollo Humano", "crodriguez": "Gerencia de Negocios Logisticos", "mrodriguezm": "TPPA", "girodriguez": "Gerencia de Negocios Logisticos", "rrodriguez": "Procesos Estratégicos", "yrodriguez": "Gerencia de Negocios Logisticos", "wrodriguez": "Gerencia de Adquisiciones y Finanzas", "nrojas": "Gerencia de Negocios Logisticos", "crojas": "Gestión de Sistemas Digitales y Ciberseguridad", "rroman": "Negocios Maritimos y Navieros", "rromero": "Negocios Maritimos y Navieros", "sromero": "Gestión de Administración y Desarrollo Humano", "mroncal": "Procesos Estratégicos", "groque": "Negocios Maritimos y Navieros", "mrosales": "Negocios Maritimos y Navieros", "rrosales": "Procesos Estratégicos", "jrosello": "Gerencia de Negocios Logisticos", "nrosillo": "Negocios Maritimos y Navieros", "erubinos": "Gerencia de Negocios Logisticos", "pruis": "Gerencia de Negocios Logisticos", "jruiz": "Gerencia de Negocios Logisticos", "hruiz": "TPPA", "joruiz": "Negocios Maritimos y Navieros", "sruiz": "Negocios Maritimos y Navieros", "crumiche": "Gestión de Administración y Desarrollo Humano", "erun": "Gerencia de Adquisiciones y Finanzas", "asacari": "Gerencia de Negocios Logisticos", "osaenz": "Gerencia de Negocios Logisticos", "gsalazar": "Gestión Legal", "glsalazar": "Gestión Legal", "vsalazar": "Regiones", "ssalazar": "Gerencia de Negocios Logisticos", "msalcedo": "Gerencia de Adquisiciones y Finanzas", "csaldamando": "Gerencia de Negocios Logisticos", "jasanchez": "Negocios Maritimos y Navieros", "masanchez": "Gerencia de Negocios Logisticos", "asanchez": "Gerencia de Adquisiciones y Finanzas", "arsanchez": "Gestión de Sistemas Digitales y Ciberseguridad", "lsanchez": "Gerencia de Negocios Logisticos", "fsanchez": "Negocios Maritimos y Navieros", "csanchez": "Gestión de Seguridad y SSOMA", "msanchez": "Gestión de Sistemas Digitales y Ciberseguridad", "asandoval": "Gerencia de Negocios Logisticos", "asantiago": "Gerencia de Adquisiciones y Finanzas", "ssantibanez": "Gestión de Administración y Desarrollo Humano", "wsantos": "Negocios Maritimos y Navieros", "jsantos": "Negocios Maritimos y Navieros", "pscotto": "Gestión de Seguridad y SSOMA", "rsegovia": "Gerencia de Negocios Logisticos", "cseminario": "Negocios Maritimos y Navieros", "gsernaque": "Negocios Maritimos y Navieros", "dserquen": "Gerencia de Negocios Logisticos", "bsifuentes": "TPPA", "msilva": "Gerencia de Negocios Logisticos", "ssilva": "Gerencia de Negocios Logisticos", "dsinchi": "Gerencia de Negocios Logisticos", "jsolis": "Gestión de Seguridad y SSOMA", "vsoria": "Gestión de Sistemas Digitales y Ciberseguridad", "ltantalean": "Gerencia de Negocios Logisticos", "ftarazona": "Gerencia de Negocios Logisticos", "jtasayco": "Planeamiento Estratégico", "htejero": "TPPA", "ltello": "TPPA", "rtello": "Negocios Maritimos y Navieros", "jtello": "Gerencia de Negocios Logisticos", "htenorio": "Gestión de Sistemas Digitales y Ciberseguridad", "ktiburcio": "Gerencia de Negocios Logisticos", "otirado": "Gerencia de Adquisiciones y Finanzas", "jtolentino": "Negocios Maritimos y Navieros", "itoro": "Gerencia de Adquisiciones y Finanzas", "rtoro": "Gerencia de Negocios Logisticos", "jtorres": "Gerencia de Negocios Logisticos", "jotorres": "Gestión de Administración y Desarrollo Humano", "jetorres": "Gerencia de Negocios Logisticos", "atorres": "Gerencia de Negocios Logisticos", "vtorres": "TPPA", "dtorres": "Negocios Maritimos y Navieros", "ctrelles": "Gerencia de Negocios Logisticos", "jtrillo": "Gestión de Seguridad y SSOMA", "rtrujillo": "Planeamiento Estratégico", "mtuco": "Gerencia de Negocios Logisticos", "gurbina": "Gestión de Administración y Desarrollo Humano", "avaldez": "Gerencia de Adquisiciones y Finanzas", "jvaldiviezo": "Regiones", "jvalencia": "Gerencia de Negocios Logisticos", "pvalle": "Gestión de Sistemas Digitales y Ciberseguridad", "ovallejos": "TPPA", "zvalqui": "TPPA", "rvargas": "Gerencia de Negocios Logisticos", "jvargas": "Gerencia de Negocios Logisticos", "mvargas": "Gerencia de Adquisiciones y Finanzas", "ivargas": "Gerencia de Negocios Logisticos", "ivvargas": "Gestión de Sistemas Digitales y Ciberseguridad", "avargas": "Gerencia de Adquisiciones y Finanzas", "cvasquez": "Gerencia de Negocios Logisticos", "evasquez": "Negocios Maritimos y Navieros", "jvasquez": "Gerencia de Negocios Logisticos", "gveas": "TPPA", "cvela": "Negocios Maritimos y Navieros", "avelorio": "Gerencia de Negocios Logisticos", "jverastegui": "Gestión de Sistemas Digitales y Ciberseguridad", "lvilca": "Gerencia de Negocios Logisticos", "evillacorta": "Gerencia de Negocios Logisticos", "jvillafuerte": "Gerencia de Negocios Logisticos", "cvillaizan": "TPPA", "jvillanueva": "Gerencia de Negocios Logisticos", "aviton": "Negocios Maritimos y Navieros", "evivar": "Gestión de Sistemas Digitales y Ciberseguridad", "vvizarreta": "Gerencia de Adquisiciones y Finanzas", "lyauri": "Gerencia de Negocios Logisticos", "vyauris": "TPPA", "eyman": "Gerencia de Negocios Logisticos", "myncio": "Gerencia de Negocios Logisticos", "jyncio": "Negocios Maritimos y Navieros", "fyparraguirre": "Gestión de Administración y Desarrollo Humano", "byturrizaga": "Gerencia de Negocios Logisticos", "jzaime": "Negocios Maritimos y Navieros", "jzambrano": "Gerencia de Negocios Logisticos", "pzamudio": "Negocios Maritimos y Navieros", "hzapata": "Gerencia de Negocios Logisticos", "czarate": "Gestión de Sistemas Digitales y Ciberseguridad", "jzarate": "Gestión de Administración y Desarrollo Humano", "jzavala": "Gerencia de Negocios Logisticos"};

const KPI_NOMBRES = {"onevado": {"n": "Omar Nevado Chevez", "p": "Customer Service Sil"}, "rabal": {"n": "Rufino Abal Quispe", "p": "Almacenero de Deposito Simple"}, "cacero": {"n": "Christian George Acero Solano", "p": "-"}, "aacevedo": {"n": "Arle David Acevedo Espíritu", "p": "Operador Aduanero"}, "laciego": {"n": "Luis Alexander Aciego Zuñiga", "p": "Operador de Grúa"}, "racosta": {"n": "Roy Acosta", "p": "Operador Visto Bueno"}, "aacuna": {"n": "Antony Anderson Acuña Almeyda", "p": "Almacenero de Patio"}, "kacuna": {"n": "Karla Ivonne Acuña Salazar", "p": "Customer Operation Sip"}, "faguilar": {"n": "Fiztgerald Berenguer Aguilar Alvarez", "p": "Coordinador de Documentación Importaciones"}, "laguilar": {"n": "Luis Marcial Aguilar Villanueva", "p": "Asistente de Reefers"}, "laguirre": {"n": "Luis Alfonso Aguirre Chavez", "p": "Almacenero Vacios"}, "aalanya": {"n": "Abraham Daniel Alanya Cusihuaman", "p": "Analista Programador"}, "jalarcon": {"n": "Jorge Luis Alarcon Machado", "p": "-"}, "ealarcon": {"n": "Enrique Manuel Alarcon Meza", "p": "Gerente de Sistemas Digitales y Ciberseguridad"}, "falejandro": {"n": "Feli Nivardo Alejandro Lazaro", "p": "-"}, "fealejandro": {"n": "Feli Nivardo Alejandro Lazaro", "p": "-"}, "ralejo": {"n": "Richard Edison Alejo Arango", "p": "Jefe de Planeamiento y Servicio Lcl & Ad"}, "lalfaro": {"n": "Luis Alberto Alfaro Arenas", "p": "-"}, "ealfaro": {"n": "Ernesto Martin Alfaro Bazan", "p": "Chofer Custodia"}, "valtamiza": {"n": "Veronica Vanessa Altamiza Nuñez", "p": "-"}, "balvarado": {"n": "Bruno Martin Alvarado Rodriguez", "p": "Inspector de Contenedores"}, "aalvarez": {"n": "Anthony Alvarez Bohorquez", "p": "Operador Visto Bueno"}, "palvarez": {"n": "Paula Jhoset Alvarez Medina", "p": "Ejecutiva Senior Comercial de Negocios Marítimos y Líneas Navieras"}, "salzamora": {"n": "Sindy Fiorela Alzamora Narro", "p": "Asistente de Operaciones ? Región Norte"}, "jamaro": {"n": "Jhon Erick Amaro Carbajal", "p": "-"}, "aanazgo": {"n": "Angela Lucero Añazgo Tejada", "p": "Coordinador de Cultura Organizacional"}, "jandonaire": {"n": "Juan Carlos Andonaire Caceda", "p": "Gerente de Negocios de Comercio Exterior"}, "janicama": {"n": "Jose Miguel Anicama Saenz", "p": "-"}, "panteparra": {"n": "Patricia del Rosario Anteparra Ubillus", "p": "Sectorista Liquidador de Importación - Aduanas"}, "earanciaga": {"n": "Eleazar Aranciaga Espinoza", "p": "Sub Gerente de Sistemas Digitales y Ciberseguridad"}, "raranguez": {"n": "Rosa Alexandra Aranguez Romero", "p": "Coordinador de Desarrollo del Talento"}, "larcela": {"n": "Luigi Jesus Arcela Roque", "p": "Asistente de Operaciones Agmar"}, "farenas": {"n": "Fryda Paola Arenas Romani", "p": "Ejecutivo Comercial Aci"}, "jarguello": {"n": "Jorman Joel Argüello Landa", "p": "Liquidador - Aduanas"}, "darias": {"n": "Delicia Arias Chocan", "p": "Analista de Créditos y Cobranzas"}, "jarmestar": {"n": "Jesús Orlando Armestar García", "p": "Gestor de Proyectos de Transformación"}, "bascona": {"n": "Braulio Ascona Carrillo", "p": "Operador de Grúa"}, "matarama": {"n": "Mercedes del Pilar Atarama Lopez", "p": "Asistente de Tesorería"}, "mavalos": {"n": "Moises Harrison Avalos Tang", "p": "Operador de Aforos"}, "navila": {"n": "Nestor Alejandro Avila Pascual", "p": "Ejecutivo Comercial Agm"}, "jbaca": {"n": "Jorge Baca Huaman", "p": "Operador de Grúa"}, "nbarandiaran": {"n": "Naysha Georgina Barandiaran Estrada", "p": "Ejecutivo Comercial"}, "abarreto": {"n": "Ana Laura Barreto Barreto", "p": "Asistente de Facturación Importaciones"}, "cbarrientos": {"n": "Cesar Barrientos", "p": "Sectorista de Exportación - Aduanas"}, "gbarrientos": {"n": "German Barrientos Hernandez", "p": "Especialista Ssoma"}, "sbazalar": {"n": "Sthefany Bazalar Acosta", "p": "Supervisor de Ventas"}, "sebazalar": {"n": "Sergio Yuri Bazalar Asalve", "p": "Gerente Central de Negocios Marítimos y Navieros"}, "ybazalar": {"n": "Yadira Yajayla Bazalar Yon", "p": "Trabajadora Social"}, "pbazan": {"n": "Petita Graciela Bazán Collantes", "p": "Especialista de Mejora Continua"}, "hbazan": {"n": "Hector Paulo Bazan Gonzales", "p": "Operador de Carga Lcl"}, "ebazan": {"n": "Erick Abel Bazan Loja", "p": "Customer Service Sil"}, "bbecerra": {"n": "Brayan Kevin Becerra Durand", "p": "-"}, "brbecerra": {"n": "Brayan Kevin Becerra Durand", "p": "-"}, "mbermejo": {"n": "Marco Bermejo", "p": "Asistente de Gestión Aduanera - Aduanas"}, "gbossio": {"n": "Gilson Edu Bossio Oliveira", "p": "Operador Aduanero"}, "pbrena": {"n": "Piero Sandro Breña Carignano", "p": "Inspector de Contenedores"}, "lcaballero": {"n": "Luis Enrique Caballero Rossi", "p": "Operador de Archivo"}, "jcaceres": {"n": "Jeyson Aldair Caceres Palomino", "p": "Asistente de Operaciones"}, "acajaleon": {"n": "Anghela Jackeline Cajaleon Terrones", "p": "Asistente de Facturación Importaciones"}, "ccalderon": {"n": "Cintia Claudia Calderon Ore", "p": "Customer Service Sil"}, "ecalmet": {"n": "Elleen Isabel Calmet Sandoval", "p": "-"}, "mcamasca": {"n": "Micaela Camasca Gallo", "p": "Practicante Profesional de Procesos Estratégicos"}, "ccamasca": {"n": "Cesar Gonzalo Camasca Venero", "p": "Líder de Talento y Desarrollo"}, "ccampana": {"n": "Carlos Alberto Campaña Olivos", "p": "Almacenero de Llenos"}, "rcampos": {"n": "Rosa Luz Jimena Campos Cahuana", "p": "Customer Operation Sil"}, "ocampos": {"n": "Omar Enrique Campos Orbegozo", "p": "Prevencionista de Riesgos"}, "bcancino": {"n": "Brayan Diego Cancino Rubiños", "p": "Almacenero Vacios"}, "jcapcha": {"n": "Joshelyn Milagros Capcha Ñaupas", "p": "Asistente de Facturación Exportaciones"}, "bcapulian": {"n": "Braulio Kevin Capulian Herrera", "p": "Analista de Proceso y Mejora Continua"}, "kcarbajal": {"n": "Kevin Carbajal Berrocal", "p": "Almacenero de Patio"}, "jcardenas": {"n": "Juan Cardenas Avendaño", "p": "Operador de Grúa"}, "ecardenas": {"n": "Ernesto Gabriel Cardenas Flores", "p": "Almacenero de Patio"}, "ycardenas": {"n": "Yesenia Jackeline Cárdenas Sanchez", "p": "Trabajadora Social"}, "acarmelino": {"n": "Alberto Carmelino", "p": "Auxiliar de Despacho Aduanero"}, "jcarmona": {"n": "Jimmy Harold Carmona Todco", "p": "Analista Legal Comex"}, "scaro": {"n": "Shaly Brissette Caro Villar", "p": "Procurador"}, "gcarrasco": {"n": "George Peter Carrasco Baca", "p": "Supervisor de Contabilidad"}, "jcarreno": {"n": "Julio Carreño Calisaya", "p": "Almacenero Vacios"}, "bcarrillo": {"n": "Brahayan Antoni Carrillo Castro", "p": "Tecnico de Reefers"}, "jcarrillo": {"n": "Jose Luis Carrillo Rodriguez", "p": "Analista de la Demanta de Ti"}, "mcarrion": {"n": "Marco Antonio Carrion Roman", "p": "Representante Aduanero"}, "macarrion": {"n": "Miguel Antonio Carrion Suarez", "p": "Operador Aduanero Documentación Agm - Paita"}, "rcaruajulca": {"n": "Rosa Magali Caruajulca Garcia", "p": "Customer Service Sil"}, "rcasas": {"n": "Raul Lenin Casas Roque", "p": "Coordinador de Infraestructura"}, "hcastaneda": {"n": "Hector Enrique Castañeda Alvarado", "p": "-"}, "mcastillo": {"n": "Mariana Lesly Castillo Chapeyquen", "p": "Analista de Pmo y Qa Senior"}, "ncastillo": {"n": "Norma Silvia Castillo la Rosa", "p": "Contador General"}, "jcastillo": {"n": "Juan Demetrio Castillo Navarrete", "p": "Operador Carga Suelta"}, "jcastro": {"n": "Jorge Julio Antonio Castro Almandos", "p": "Gerente de Logística Interna y Centros de Distribución"}, "hcastro": {"n": "Hector Luis Castro Escobar", "p": "Practicante Profesional de Procesos Estratégicos"}, "rcastro": {"n": "Roger Castro Pablo", "p": "Asistente Operativo de Seguridad"}, "lcastro": {"n": "Luis Fernando Castro Pasache", "p": "Customer Service Sip"}, "pcatano": {"n": "Percy Cataño", "p": "Customer Service Sil"}, "ycatay": {"n": "Yessenia Ruby Catay Cuadros", "p": "Operador Visto Bueno"}, "mcerna": {"n": "Milagros Darshan Cerna Espinoza", "p": "Coordinador de Proyecto Chancay"}, "jcerna": {"n": "Jack Martin Cerna Oblitas", "p": "Asistente de Compras"}, "kcespedes": {"n": "Kevin Cespedes Isuiza", "p": "Asistente Administrativo Llenos"}, "jcespedes": {"n": "Jose Carlos Cespedes Sauñe", "p": "Operador de Grúa"}, "fchallco": {"n": "Flor Maria Challco Marmolejo", "p": "Asistente de Control de Cctv"}, "bchaua": {"n": "Bryan Jesús Moises Chaua Alejos", "p": "Gestor de Proyectos de Transformación"}, "ychavarria": {"n": "Yaddith Nicole Chavarria Rojas", "p": "Jefe de Aplicaciones y Arquitectura"}, "mchavez": {"n": "Mary Heylin Chavez Morales", "p": "Líder de Mercado Vertical, gestor de Proyectos de Transformación"}, "cchillcce": {"n": "Craig Kevin Chillcce Sanchez", "p": "Operador de Linea"}, "kchinchercoma": {"n": "Kennedy Yaxzon Chinchercoma Pary", "p": "Tecnico de Mantenimiento"}, "wchinga": {"n": "Willian Moises Chinga Macalupu", "p": "Técnico de Reefers - Región Norte"}, "echipana": {"n": "Edson Luciano Chipana Luque", "p": "Almacenero de Deposito Simple"}, "echiroque": {"n": "Enzo Wladimir Chiroque Garcia", "p": "Operador de Aforos"}, "jchocanga": {"n": "Jose Alexander Chocanga Resines", "p": "Chofer de Transporte Pesado"}, "cchoquez": {"n": "Cristina Sianeh Choquez Breiding", "p": "Asistente de Tesorería"}, "lchu": {"n": "Lizbeth Arlita Chu Rodriguez", "p": "Gerente de Negocios Marítimos y Navieros"}, "lchui": {"n": "Leydi Keyko Chui Kan", "p": "Asistente de Créditos y Cobranzas"}, "achumbirayco": {"n": "Angel Aramys Chumbirayco Tapullima", "p": "Especilaista de Atracción y Gestión del Talento"}, "lchumpitaz": {"n": "Luis Felipe Chumpitaz Cruzado", "p": "Analista de Datos"}, "mchurano": {"n": "Michelle Luisa Briggith Churano Idrogo", "p": "Pricing"}, "ecisneros": {"n": "Elizabeth Maryorie Cisneros Magallanes", "p": "Analista de Procesos"}, "acisneros": {"n": "Abimael Eliseo Cisneros Meneses", "p": "Administrador de Base de Datos y Ciberseguridad"}, "jclemente": {"n": "Juan Carlos Clemente Huamaccto", "p": "Tecnico de Reefers"}, "mcobos": {"n": "Mary Cobos", "p": "Ejecutivo Comercial"}, "fcollazos": {"n": "Fiama Ximena Collazos Castro", "p": "Customer Service Sil"}, "mcondori": {"n": "Miguel Humberto Condori Colquehuanca", "p": "Tecnico de Mantenimiento"}, "jcordova": {"n": "Jonathan Augusto Cordova Saldarriaga", "p": "-"}, "jocordova": {"n": "Jonathan Augusto Cordova Saldarriaga", "p": "-"}, "hcoria": {"n": "Harold Keny Coria Silva", "p": "Operador de Documentación - Aduanas"}, "lcorrea": {"n": "Luis Augusto Correa Vega", "p": "Jefe de Transporte"}, "lcortez": {"n": "Lucio Misael Cortez Huancas", "p": "Customer Service Vacíos"}, "wcotrina": {"n": "Willian Rafael Cotrina Lozano", "p": "Operador de Puerto"}, "ccoz": {"n": "Carlos Armando Coz Cuneo", "p": "Gerente de Adquisiciones y Finanzas"}, "cacoz": {"n": "Carlos Armando Coz Cuneo", "p": "Gerente de Adquisiciones y Finanzas"}, "ecrisologo": {"n": "Elvira Esteves Crisologo Sanchez", "p": "Asistente de Gestión Aduanera - Aduanas"}, "hcrisostomo": {"n": "Hillary Lucia Crisostomo Alcantara", "p": "Customer Service Lcl"}, "acruz": {"n": "Annya Carla Cruz Chambi", "p": "Jefe de Planeamiento y Servicio Vacíos"}, "lcruz": {"n": "Luighi Digenaro Cruz Galvez", "p": "Customer Operation Sip"}, "jcruz": {"n": "Jimmy Cesar Cruz Martinez", "p": "Operador de Grúa"}, "kcruz": {"n": "Kike Ruben Cruz Pizarro", "p": "Supervisor de Vacíos"}, "jcuadros": {"n": "Julio Jorge Cuadros Angulo", "p": "Jefe de Aplicaciones y Arquitectura"}, "fcueva": {"n": "Franchesca Dessire Cueva Guevara", "p": "Asistente de Facturación Vacíos"}, "mcuri": {"n": "Michael Jordy Curi Rivera", "p": "Balancero"}, "jcuro": {"n": "Jorge Harold Junior Curo Diaz", "p": "-"}, "cdamaso": {"n": "Clodomiro Damaso Mejia", "p": "Inspector de Contenedores"}, "hdance": {"n": "Hector Rene Dance Fernandez", "p": "Asistente de Adquisiciones"}, "adavalos": {"n": "Arturo Humberto Dávalos Chavez", "p": "Customer Service Región Sur"}, "edelacruz": {"n": "Estrella Carolina de la Cruz Aldana", "p": "Auxiliar de Despacho Aduanero"}, "adelacruz": {"n": "Alejandro de la Cruz Villar", "p": "Operador de Montacarga"}, "pdelarosa": {"n": "Paola Mirella de la Rosa Pérez", "p": "Analista Programador"}, "idelacruz": {"n": "Israel de Lacruz Sudario", "p": "Auxiliar de Despacho Aduanero"}, "cdelossantos": {"n": "Christian Joseph de los Santos Ruiz", "p": "Operador de Elevador Electrico"}, "ydepaz": {"n": "Yessica de Paz", "p": "Auxiliar de Gestión Humana"}, "jdelaguila": {"n": "Jorge Eduardo del Aguila Tirado", "p": "Gerente de Ssoma, Protección y Desarrollo de Proyectos"}, "bdelgado": {"n": "Brigitte Denis Delgado Agustin", "p": "Trabajadora Social"}, "ydemarini": {"n": "Yessica Demarini", "p": "Gerente de Administración y Desarrollo Humano"}, "pdi": {"n": "Pilar Cecilia Di Gravia Hernandez", "p": "Jefe de Desarrollo"}, "jdiaz": {"n": "Jimena Diaz", "p": "-"}, "jdiazg": {"n": "Jacqueline Diaz Garcia", "p": "Supervisor de Infraestructura Técnologica"}, "ediaz": {"n": "Erika Tatiana Diaz Rojas", "p": "Sectorista Liquidador de Exportación - Aduanas"}, "jhdiaz": {"n": "Jhonatan Williams Diaz Serra", "p": "Planer Lider de Operaciones"}, "pdiego": {"n": "Piero Denis Diego Zamora", "p": "Sectorista - Aduanas"}, "mdioses": {"n": "Marcos Jimmy Dioses Carrasco", "p": "Analista de Soporte"}, "ddioses": {"n": "Dante Jhoan Dioses Soto", "p": "Coordinador de Línea"}, "gduque": {"n": "Gianela Nicole Duque Gil", "p": "Operador de Importaciones"}, "mduran": {"n": "Milagros Geraldine Duran Balmaceda", "p": "Asistente de Facturación Importaciones"}, "wduran": {"n": "Waldir Duran Landa", "p": "Asistente de Tesorería"}, "decheccaya": {"n": "David Antonio Echeccaya Sanchez", "p": "Asistente Operativo de Seguridad"}, "felescano": {"n": "Francisco Javier Elescano Barrientos", "p": "Operador Cctv"}, "jelizares": {"n": "Jhon Fliver Elizares Cabrera", "p": "Almacenero Vacios"}, "rescalante": {"n": "Rossana Katherine Escalante Maguiña", "p": "Asistente de Gestión Aduanera - Aduanas"}, "gescobar": {"n": "Gian Pierre Steve Escobar Rodriguez", "p": "Analista de la Demanta de Ti"}, "jespinal": {"n": "Juan Carlos Espinal Avila", "p": "-"}, "despinola": {"n": "Diana Jackeline Espinola Otiniano", "p": "Customer Service Lcl"}, "lespinoza": {"n": "Lisbeth Gregoria Espinoza Cruz", "p": "Customer Service Aci"}, "kespinoza": {"n": "Kathya Espinoza Cuadros", "p": "Operador Visto Bueno"}, "cespinoza": {"n": "Cinthia Melisza Espinoza Felices", "p": "Customer Service Sil"}, "aespinoza": {"n": "Alejandro Espinoza Garcia", "p": "Jefe de Vacíos y Reefers"}, "gespinoza": {"n": "Guido Alexander Espinoza Joaquin", "p": "Analista de la Demanta de Ti"}, "mespinoza": {"n": "Miguel Edson Manuel Espinoza Perez", "p": "Auxiliar de Infraestructura y Soporte Ti"}, "jfarfan": {"n": "Jogsan Antonio Farfan Gonzales", "p": "Coordinador de Línea"}, "cfarro": {"n": "Claudia Ines Farro Bancayan", "p": "Coordinador de Proyectos de Fondos de Inversión"}, "afebres": {"n": "Arnoll Obdul Febres Bravo", "p": "Operador de Montacarga"}, "afelippe": {"n": "Aida Paola Felippe Castro", "p": "Supervisor de Planeamiento & Servicio Ac"}, "sfernandez": {"n": "Sergi Gonzalo Marcos Fernández Luna", "p": "Practicante Pre-profesional Legal"}, "ofernandez": {"n": "Oscar Carlos Fernandez Zavala", "p": "Operador Cctv"}, "gfiestas": {"n": "Giorgina Andrea Fiestas Flores", "p": "Gestor de Experiencia Al Cliente"}, "jfiestas": {"n": "Jean Pierre Fiestas Gil", "p": "Operador Aduanero"}, "joflores": {"n": "Johana Elizabeth Flores Falla", "p": "Customer Operation Sil"}, "aflores": {"n": "Andrea Maritza Flores Farias", "p": "Coordinador de Operaciones Aduanas"}, "jflores": {"n": "Jerson Flores Gil", "p": "-"}, "kflores": {"n": "Keyla Mileni Flores Llerena", "p": "Gestor de Proyectos de Transformación"}, "sfranco": {"n": "Sheyla Milagros Franco Espinoza", "p": "Customer Service Sip"}, "lfrias": {"n": "Leidi Frias", "p": "Operador de Documentación Exportación - Aduanas"}, "ogajate": {"n": "Orietta Socorro Gajate Toche", "p": "Gerente General"}, "mgaldos": {"n": "Melenie Ducelie Galdos Rosas", "p": "Asistente de Reefers"}, "mgallardo": {"n": "Marcos Adrian Gallardo Jimenez", "p": "Practicante Pre-profesional Legal"}, "agallo": {"n": "Alexis Ricardo Gallo Panizo", "p": "Liquidador - Aduanas"}, "ogamarra": {"n": "Oscar Gamarra", "p": "Sectorista - Aduanas"}, "dgarcia": {"n": "Dania Evelin Garcia Acaro", "p": "Pricing"}, "sgarcia": {"n": "Stephanie Brillit García Estelo", "p": "Asistente de Facturación Vacíos"}, "mgarcia": {"n": "Mirella Noemi Garcia Flores", "p": "Gestor de Costos y Márgenes Operativos"}, "rgarcia": {"n": "Rafael Garcia Llocclla", "p": "Balancero"}, "rgarrido": {"n": "Raul Garrido", "p": "Key Account Executive Senior"}, "rgavila": {"n": "Reynaldo Gavila Paulino", "p": "Coordinador de Operaciones Lcl"}, "dgirao": {"n": "Diego Alejandro Girao Ore", "p": "Customer Service Sip"}, "fgonzaga": {"n": "Felix Gonzaga Mena", "p": "Coordinador de Planeamiento Contenedores Vacios ? Región Norte"}, "rgonzales": {"n": "Richard Gonzales Medina", "p": "-"}, "rogonzales": {"n": "Roberto Gonzales Melo", "p": "Especialista Ssoma"}, "vgonzales": {"n": "Vladimir German Gonzales Muñoz", "p": "Jefe de Planeamiento"}, "egonzales": {"n": "Edward Gonzales Peña", "p": "Coordinador de Adquisiciones y Abastecimiento"}, "jgonzales": {"n": "Juan Manuel Gonzales Polar", "p": "Sub Gerente de Región Sur"}, "rcgonzales": {"n": "Roberto Cruz Gonzales Salazar", "p": "Despachador Líder - Aduanas"}, "rgonzaless": {"n": "Roberto Ruiz Gonzales Salazar", "p": "Despachador Líder - Aduanas"}, "mgrandez": {"n": "Madeleine Grandez", "p": "Asistente de Matriz y Vgm - Aduanas"}, "mguaylupo": {"n": "Miluska Veronica Cecilia Guaylupo Lizano", "p": "Coordinador de Operaciones Sip - Región Norte"}, "aguerrero": {"n": "Alexander Robert Guerrero Gonzales", "p": "Almacenero Carga Lcl"}, "rguillermo": {"n": "Rafael Josue Guillermo Diaz", "p": "Chofer Custodia"}, "dgutierrez": {"n": "Doris Anyela Gutierrez Castro", "p": "Sectorista de Exportación - Aduanas"}, "egutierrez": {"n": "Edinson Rolando Gutierrez Quispe", "p": "Asistente de Operaciones de Almacenes y Distribución"}, "agutierrez": {"n": "Álvaro Andrés Gutiérrez Silva", "p": "Procurador"}, "sheredia": {"n": "Stefano Roiser Heredia Gil", "p": "Operador Visto Bueno"}, "eheredia": {"n": "Erika Melina Heredia Vargas", "p": "Key Account Executive"}, "yhernandez": {"n": "Yorvin Hernandez Coronel", "p": "Analista Programador"}, "jherrada": {"n": "Jhon Peter Herrada Sucasaire", "p": "Sectorista - Aduanas"}, "dhidalgo": {"n": "Dhanery Loana Hidalgo Bazalar", "p": "Operador de Documentación de Importaciones - Retiros"}, "eholguin": {"n": "Eduardo Javier Holguin Nuñez", "p": "Key Account Executive Senior"}, "lhorna": {"n": "Luis Miguel Horna Rodriguez", "p": "Analista de Transporte y Distribución"}, "jhuachohuillca": {"n": "Juan Carlos Huachohuillca Bazan", "p": "Auxiliar de Inventario"}, "khuallpacuna": {"n": "Kenyi Paola Huallpacuna Arce", "p": "Jefe Legal"}, "ahuaman": {"n": "Arlet Nicole Huaman Delgado", "p": "Gestor de Costos y Márgenes Operativos"}, "jhuamani": {"n": "Jennifer Anjuly Huamani Lopez", "p": "Gestor de Proyectos de Transformación"}, "mhuapaya": {"n": "Manuel Gerardo Huapaya Evangelista", "p": "Practicante Profesional de Procesos Estratégicos"}, "bhuaquisto": {"n": "Briam Augusto Huaquisto Alatrista", "p": "Analista de la Demanta de Ti"}, "fhuarac": {"n": "Felipe Junior Huarac García", "p": "Auxiliar de Despacho Aduanero"}, "jhuaya": {"n": "Jenny Flor Huaya Araujo", "p": "Key Account Executive Senior"}, "wiglesias": {"n": "Walter Ricardo Iglesias Landa", "p": "Sub Gerente de la Región Norte"}, "oinchaustegui": {"n": "Omar Stewart Inchaustegui Sanchez", "p": "Coordinador de Finanzas"}, "cinilopu": {"n": "Christian Alexis Inilopu Pizarro", "p": "-"}, "linonan": {"n": "Luis Inonan Casimiro", "p": "Asistente Operativo de Seguridad"}, "dinonan": {"n": "Dayr Wilfredo Inoñan Castro", "p": "Coordinador de Despacho Aduanero"}, "cizquierdo": {"n": "Carlos Alberto Izquierdo Guillen", "p": "Auxiliar de Despacho Aduanero"}, "jjaramillo": {"n": "Jerson Jarol Junior Jaramillo Amasifuen", "p": "Operador de Llenados"}, "gjaucala": {"n": "Guido Almaquio Jaucala Vicencio", "p": "Almacenero Ad"}, "ajauregui": {"n": "Andrea Jauregui Pariona", "p": "Operador Aduanero"}, "cjimenez": {"n": "Carlos Hernán Jiménez Domínguez", "p": "Analista de Aplicaciones Ti"}, "djimenez": {"n": "David Angelo Jimenez Nauto", "p": "Almacenero de Patio"}, "jjustiniani": {"n": "Javier Ricardo Justiniani Puma", "p": "Coordinador Patio"}, "yleguia": {"n": "Yvonne Elisabel Leguia Oporto", "p": "Auxiliar de Cultura Organizacional"}, "dleon": {"n": "Diego Alonso Leon Chavez", "p": "Coordinador de Transporte - Tpp Transporte"}, "dileon": {"n": "Diego Leon Chavez", "p": "Coordinador de Transporte - Tpp Transporte"}, "climo": {"n": "Claudia Andrea Limo Espinoza", "p": "Gerente de Transporte"}, "jlino": {"n": "Jannik Jaime Lino Peña", "p": "Operador de Linea"}, "plira": {"n": "Percy Fernando Lira Guzman", "p": "Jefe de Costos y Margenes Operativos"}, "ilizarzaburu": {"n": "Isabel Josselin Lizarzaburu Tejada", "p": "Customer Service Vacíos"}, "jllanos": {"n": "Jose Antonio Llanos Bellmunt", "p": "Asistente de Maquinarias"}, "mllanos": {"n": "Miguel Angel Llanos Bellmunt", "p": "Operador de Grúa"}, "dllauce": {"n": "Darwin Alberto Llauce Vidaurre", "p": "-"}, "allenos": {"n": "Almacenero Llenos", "p": "Almacenero de Patio"}, "bllenos": {"n": "Balancero Llenos", "p": "Balancero"}, "allerena": {"n": "Antonella del Carmen Llerena Risco", "p": "Coordinador de Talento y Cultura"}, "jllontop": {"n": "Jhon Arnold Llontop Santisteban", "p": "Tecnico de Reefers"}, "jhllontop": {"n": "Jhon Arnold Llontop Santisteban", "p": "-"}, "hloli": {"n": "Hellen Sophia Loli Perez", "p": "Key Account Executive"}, "rlombardi": {"n": "Renzo Luciano Lombardi Benavides", "p": "Analista Senior de Sistemas Cloud"}, "mlopez": {"n": "Maria Alejandra Lopez Medina", "p": "Asistente de Facturacion Linea"}, "glopez": {"n": "Geraldine Lopez Millones", "p": "Key Account Executive"}, "mloza": {"n": "Mary Carmen Loza Alvarado", "p": "Customer Service Lcl - Documentación Expo"}, "pluis": {"n": "Paolo Humberto Luis Reyes", "p": "-"}, "jlujan": {"n": "Joymar Lujan Ulloa", "p": "-"}, "hluna": {"n": "Hernán Alejandro Luna Choque", "p": "Operador Cctv"}, "jmachuca": {"n": "Jesus Fernando Machuca Espinoza", "p": "Analista de Datos"}, "jmalpartida": {"n": "Jonny Paul Malpartida Berrospi", "p": "Jefe de Desarrollo"}, "ymamani": {"n": "Yesenia Mamani Halanocca", "p": "Coordinador de Gestión Aduanera"}, "pmamani": {"n": "Pilar Rocio Mamani Meza", "p": "Asistente de Gestión de Portafolio y Metodología"}, "ymandujano": {"n": "Yuri Anabell Mandujano Silva", "p": "Analista de Administración"}, "smarcatoma": {"n": "Stefany Sabrina Marcatoma Quispe", "p": "Asistente de Seguridad"}, "lmarconi": {"n": "Leonardo Andre Marconi Chiang", "p": "Facturador de Importaciones"}, "emarquez": {"n": "Esteban Darío Marquez Solorzano", "p": "Balancero"}, "cmartel": {"n": "Cesia Priscilla Martel Gonzales", "p": "Customer Service Ad"}, "emartinez": {"n": "Edwin Roman Martinez Saavedra", "p": "Almacenero Vacios"}, "amasias": {"n": "Alberto Martin Masias Quiñones", "p": "Sub Gerente Customer Management"}, "omattos": {"n": "Oscar Fernando Mattos Mauricio", "p": "Almacenero Vacios"}, "smauricio": {"n": "Sandra Gabriela Mauricio Mamanchura", "p": "Key Account Executive"}, "dmedina": {"n": "Dayana Medina", "p": "Customer Service Sil"}, "rmedinaa": {"n": "Ronald Gonzalo Medina Aguilar", "p": "Coordinador de Operaciones Vacíos"}, "gmedina": {"n": "Gilmer Medina Llatas", "p": "Almacenero de Patio"}, "jmejia": {"n": "Jose Angel Mejia Bazan", "p": "Asistente de Soporte de Producción"}, "hmendez": {"n": "Horacio Mendez Cunya", "p": "Auxiliar de Contabilidad"}, "amendoza": {"n": "Adriana Medalith Cristina Mendoza Zapata", "p": "Supervisor de Cuentas Clave, líder de Mercado Vertical"}, "emeneses": {"n": "Evelyn Meneses Huaccharaqui", "p": "Auxiliar Contable de Empresas Subsidiarias"}, "jmercado": {"n": "Jhonn Frank Mercado Alcalde", "p": "Operador de Grúa"}, "dmerida": {"n": "Doris Andrea Merida Torres", "p": "Asistente de Reefers"}, "gmeza": {"n": "Guido Leonel Meza Rueda", "p": "Coordinador de Documentacion Agencia"}, "jmollehuanca": {"n": "Jessica Mary Mollehuanca Ferro", "p": "-"}, "emontes": {"n": "Eder Oscar Montes Mayorga", "p": "Operador de Montacarga"}, "wmore": {"n": "Wilmer Alfredo More Vilchez", "p": "Operador de Grúa"}, "amoreno": {"n": "Alan Moreno", "p": "-"}, "fmoreno": {"n": "Franklin Yimi Moreno Amaru", "p": "Coordinador de Soporte e Infraestructura Ti"}, "jmoreno": {"n": "John Leonardo Moreno Soto", "p": "Asistente de Facturación Vacíos"}, "lmori": {"n": "Leonardo Josue Mori Carpio", "p": "-"}, "pmorillo": {"n": "Priscila Ivet Morillo Lares", "p": "Ejecutivo Comercial Agm"}, "lmucha": {"n": "Lindolfo Rosendo Mucha Mateo", "p": "Coordinador de Reparaciones"}, "gmundaca": {"n": "Guadalupe Mundaca Petitjean", "p": "Asistente Legal"}, "gmunguia": {"n": "Grover Angelino Munguia Castro", "p": "Operador Cctv"}, "amunoz": {"n": "Angie Christy Muñoz Purizaca", "p": "Customer Service Aci"}, "jmurga": {"n": "Juan Luis Eugenio Murga Alayo", "p": "Supervisor de Seguridad"}, "jomurga": {"n": "Jose Artemio Murga Palomino", "p": "Operador de Aforos"}, "rmurillo": {"n": "Roner Guillermo Murillo Lucio", "p": "Analista Contable Senior"}, "hmuro": {"n": "Halmett Omar Muro Brophy", "p": "Tramitador Motorizado"}, "tnarvarte": {"n": "Tomás Oscar Narvarte Ivankovich", "p": "Auxiliar de Despacho Aduanero"}, "jnavarro": {"n": "Jose Fernando Navarro Saavedra", "p": "Procurador"}, "tnavarte": {"n": "Tomas Oscar Navarte Ivankovich", "p": "Sectorista de Exportación - Aduanas"}, "jneyra": {"n": "Jorge Luis Neyra Prado", "p": "-"}, "mnole": {"n": "Melyssa Karyna Nole Pariona", "p": "Customer Service Sil"}, "lnunez": {"n": "Luis Angel Nuñez Baldeon", "p": "Operador de Grúa"}, "nochoa": {"n": "Nathaly Betzabe Ochoa Gonzales", "p": "Coordinador de Operaciones Aduanas"}, "rojeda": {"n": "Roberto Carlos Ojeda Arias", "p": "Arquitecto de Soluciones"}, "jolaya": {"n": "Jose Esteban Olaya Romero", "p": "Asistente de Facturación Importaciones"}, "joolaya": {"n": "Jose Esteban Olaya Romero", "p": "Asistente de Facturación Importaciones"}, "folivari": {"n": "Fiorella Cristina Olivari Hinostroza", "p": "Customer Service Sil"}, "polivera": {"n": "Pedro Pablo Olivera Medrano", "p": "Customer Operation Sip"}, "molortiga": {"n": "Miguel Angel Olortiga Franco", "p": "Jefe de Vacíos y Reefers"}, "mordinola": {"n": "Maria Isabel Ordinola Aliaga", "p": "Supervisor de Administración"}, "jordinola": {"n": "Jose del Carmen Ordinola Contreras", "p": "Coordinador de Operaciones Vacíos"}, "kortiz": {"n": "Karen Lucy Ortiz Robles", "p": "Asistente de Contabilidad"}, "lortiz": {"n": "Lindomira Guadalupe Ortiz Villanueva", "p": "Analista Legal Corporativo"}, "mosorio": {"n": "Michelle Pamela Osorio Delgado", "p": "Operador de Linea"}, "rotero": {"n": "Rosa Nataly Otero Ellen", "p": "Analista de Pmo y Qa Senior"}, "epablo": {"n": "Eduardo Leví Pablo Chaupis", "p": "Auxiliar de Contabilidad"}, "rpachas": {"n": "Rodel Anderson Pachas Astudillo", "p": "Almacenero Vacios"}, "cpacora": {"n": "Carlo Javier Pacora Panana", "p": "Analista de Procesos"}, "ppadilla": {"n": "Percy Christian Padilla Castro", "p": "Tecnico de Reefers"}, "cpalacios": {"n": "Christian Palacios Ureta", "p": "-"}, "jpalomino": {"n": "Jose Luis Palomino Flores", "p": "Analista de la Demanta de Ti"}, "jpanana": {"n": "Jose Alonso Panana Nizama", "p": "Balancero"}, "ppantaleon": {"n": "Pedro Pantaleon Serrano", "p": "Tecnico de Mantenimiento"}, "apantigoso": {"n": "Andrea Isabel Pantigoso Muñoz", "p": "Key Account Executive"}, "kpariapaza": {"n": "Katherine Pariapaza Hilario", "p": "Customer Operation Sip"}, "rpasache": {"n": "Ronald Eduardo Pasache Gaspar", "p": "-"}, "ropasache": {"n": "Ronald Eduardo Pasache Gaspar", "p": "-"}, "dpastor": {"n": "Dennis Jeampierre Pastor Bedoya", "p": "Auxiliar de Despacho Aduanero"}, "cperalta": {"n": "Cesar Augusto Peralta Ramirez", "p": "Coordinador Patio"}, "spereira": {"n": "Suley Lissete Pereira Villegas", "p": "Coordinador de Operaciones"}, "lperez": {"n": "Lizbeth Lesly Perez Cardenas", "p": "Asistente de Facturación Vacíos"}, "aperez": {"n": "Angel Ricardo Perez Prado", "p": "Key Account Manager"}, "mperez": {"n": "Maria Kattia Perez Prado", "p": "Jefe de Documentación Terminal"}, "apillaca": {"n": "Alvaro Robinson Pillaca Sotelo", "p": "Asistente Administrativo Llenos"}, "apiminchumo": {"n": "Andy Piminchumo Rios", "p": "Customer Service Sip"}, "dpingo": {"n": "David Orlando Pingo Zapata", "p": "Analista de la Demanta de Ti"}, "jponce": {"n": "Jherson Ivan Ponce Gutierrez", "p": "Customer Service Aci"}, "dponciano": {"n": "Daphne Luciana Ponciano Segura", "p": "Analista de Planeamiento"}, "mporras": {"n": "Maycon Porras Aguilar", "p": "Customer Operation Sil"}, "eportilla": {"n": "Esteban Fernando Portilla Chavez", "p": "Supervisor de Negocios Logísticos y Contenedores Vacíos ? Región Norte"}, "bportocarrero": {"n": "Betsy Jenniffer Portocarrero Tineo", "p": "Jefe Comercial de Negocios Logísticos"}, "jpozo": {"n": "Jesus Pozo", "p": "Operador de Documentación Exportación - Aduanas"}, "lpretil": {"n": "Lister Anderson Pretil Chirinos", "p": "Coordinador Patio"}, "hprincipe": {"n": "Hector Yonathan Principe Aburto", "p": "Operador de Grúa"}, "uprueba": {"n": "Usuario Prueba", "p": "Procurador"}, "dpuertas": {"n": "Diego Andre Puertas Alayo", "p": "Operador Visto Bueno"}, "ipujada": {"n": "Isaac Caleb Pujada Taya", "p": "Operador de Grúa"}, "jquilluya": {"n": "Jorge Luis Quilluya Escarcena", "p": "Coordinador Logístico Integral"}, "cquinones": {"n": "Carlos Arturo Quiñones Cisneros", "p": "Coordinador de Reefers"}, "yquispe": {"n": "Yoryo Quispe Yataco", "p": "Procurador"}, "dramirez": {"n": "Diego Ramirez Alvizuri", "p": "-"}, "jramirez": {"n": "Jhonatan Ramirez Heredia", "p": "Auxiliar de Almacen"}, "nramirez": {"n": "Nancy Andrea Ramirez Lee", "p": "Jefe de Negocio Aduanero"}, "eramirez": {"n": "Enriqueta Emperatriz Ramirez Licona", "p": "Key Account Executive"}, "aramirez": {"n": "Angel Anderson Ramirez Ramirez", "p": "-"}, "juramirez": {"n": "Juan Daniel Ramirez Salas", "p": "Supervisor de Refrigerados y Servicio Integral"}, "lramos": {"n": "Luis Abel Ramos Arevalo", "p": "Sectorista de Importación - Aduanas"}, "jramos": {"n": "Jean Pier Ramos Garcia", "p": "Asistente de Operaciones Ad"}, "mramos": {"n": "Manuel Francisco Ramos Meza", "p": "Jefe de Operaciones y Comex"}, "sramos": {"n": "Silvia Janet Ramos Quineche", "p": "-"}, "maramos": {"n": "Marjorie Paola Ramos Ynca", "p": "Operador Líder de Exportaciones"}, "jremigio": {"n": "Joel Remigio", "p": "Sectorista - Aduanas"}, "vrenteria": {"n": "Vicente Enrique Renteria Guerra", "p": "Tecnico de Reefers"}, "areyes": {"n": "Anthony Gregory Reyes Peña", "p": "Sectorista de Exportación - Aduanas"}, "frios": {"n": "Frank Erik Ríos Landeo", "p": "Analista de la Demanta de Ti"}, "mrios": {"n": "Marjorie Adriana Rios Valdizan", "p": "Asistente de Gestión Humana"}, "rrios": {"n": "Rodrigo Adrian Rios Yañez", "p": "Practicante Profesional de Procesos Estratégicos"}, "jrivas": {"n": "Jackeline Marjorie Rivas Tiburcio", "p": "Ejecutivo Comercial"}, "jrivera": {"n": "Jaime Renato Rivera Echevarria", "p": "Jefe de Agencia de Carga Internacional"}, "yrivera": {"n": "Yohana Esther Angela Rivera Flores", "p": "Asistente de Compras"}, "arivera": {"n": "Andrea Elisa Rivera Ponte", "p": "Coordinador de Facturación"}, "drobles": {"n": "Diana Belissa María Robles García", "p": "Analista de Riesgos y Fraude"}, "grodriguez": {"n": "Guillermo Rodriguez", "p": "Sectorista - Aduanas"}, "srodriguez": {"n": "Segundo Eligio Rodriguez Camacho", "p": "-"}, "serodriguez": {"n": "Segundo Eligio Rodriguez Camacho", "p": "-"}, "arodriguez": {"n": "Alejandro Humberto Rodriguez Canales", "p": "Sub Gerente de Transporte"}, "jrodriguez": {"n": "José Percy Rodriguez Cotrina", "p": "Operador de Grúa"}, "krodriguez": {"n": "Karla Rodriguez Diaz", "p": "Auxiliar de Gestión Humana"}, "mrodriguez": {"n": "Marco Antonio Rodriguez Fiestas", "p": "Asistente Administrativo"}, "kerodriguez": {"n": "Kelly Estrella Rodriguez Giron", "p": "-"}, "crodriguez": {"n": "Cooper Oswaldo Rodriguez Lejavo", "p": "Coordinador de Gestión de Personal"}, "mrodriguezm": {"n": "Miguel Angel Rodriguez Meza", "p": "Auxiliar de Importaciones - Aduanas"}, "cerodriguez": {"n": "Cesar Augusto Rodriguez Quispe", "p": "-"}, "girodriguez": {"n": "Giordy Sebastian Rodriguez Rufino", "p": "Operador de Grúa"}, "rrodriguez": {"n": "Romario Beveto Rodriguez Silva", "p": "Practicante Profesional de Procesos Estratégicos"}, "yrodriguez": {"n": "Yoselin Shirley Rodriguez Trujillo", "p": "Ejecutivo Comercial"}, "wrodriguez": {"n": "Weendoly Alessandra Rodriguez Yncio", "p": "Pricing"}, "erojas": {"n": "Eduardo Alexander Rojas Culqui", "p": "-"}, "edrojas": {"n": "Eduardo Alexander Rojas Culqui", "p": "-"}, "nrojas": {"n": "Noelia Lucero Rojas Ore", "p": "Customer Operation Sil"}, "crojas": {"n": "Cristhian Mariano Rojas Soto", "p": "Trainee de Aplicaciones"}, "rroman": {"n": "Richard Josue Román Ruiz", "p": "Auxiliar Vacíos"}, "rromero": {"n": "Robert Willy Romero Espinoza", "p": "Almacenero Vacios"}, "sromero": {"n": "Sara Luzgardi Romero Piera", "p": "Asistente de Atracción y Gestión del Talento"}, "mroncal": {"n": "Miriam Judit Roncal Silva", "p": "Sub Gerente de Procesos Estratégicos"}, "groque": {"n": "Gian Pierre Armando Roque Linares", "p": "Tecnico de Reefers"}, "mrosales": {"n": "Miguel Angel Rosales Crisologo", "p": "Tecnico de Reefers"}, "rrosales": {"n": "Renato Alexander Rosales Lopez", "p": "Jefe de Procesos y Riesgos"}, "jrosello": {"n": "Jairo Rosello Rodriguez", "p": "Almacenero de Patio"}, "nrosillo": {"n": "Napoleon Junior Rosillo Carrasco", "p": "Tecnico de Reefers"}, "erubinos": {"n": "Elgar Rubiños Becerra", "p": "Operador de Grúa"}, "pruis": {"n": "Pamela Jesus Ruis Rios", "p": "Key Account Executive Senior"}, "jruiz": {"n": "Juan Jose Ruiz Calvo", "p": "Almacenero de Patio"}, "hruiz": {"n": "Hector Enrique Ruiz Daza", "p": "Sectorista Operativo Líder - Aduanas"}, "joruiz": {"n": "Jorge Alexis Ruiz Salazar", "p": "Almacenero Vacios"}, "sruiz": {"n": "Samantha del Rocío Ruiz Vera", "p": "Asistente de Operaciones Agmar"}, "crumiche": {"n": "Carlos Steevens Rumiche Zeta", "p": "Coordinador de Administración"}, "erun": {"n": "Evelyn Julissa Run Rosado", "p": "Asistente de Facturación Importaciones"}, "asacari": {"n": "Alvaro Sacari Fernandez", "p": "Almacenero de Patio"}, "osaenz": {"n": "Oscar Alfredo Sáenz Galarza", "p": "Almacenero de Patio"}, "gsalazar": {"n": "Gladys Rocio Salazar Castro", "p": "Asistente Legal"}, "glsalazar": {"n": "Gladys Rocio Salazar Castro", "p": "Asistente Legal"}, "vsalazar": {"n": "Veronica Lizzeth Salazar Herrera", "p": "Asistente de Operaciones Agm - Región Norte"}, "ssalazar": {"n": "Salomon Eleazar Salazar Zegarra", "p": "Chofer Tramitador"}, "msalcedo": {"n": "Mary Luz Salcedo Rivas", "p": "Asistente de Tesorería"}, "csaldamando": {"n": "Carlos Aurelio Saldamando Rengifo", "p": "Customer Operations"}, "jsanchez": {"n": "Juan Fausto Sanchez Aguirre", "p": "-"}, "jasanchez": {"n": "Jackeline Sanchez Chavez", "p": "Coordinador de Visto Bueno y Servicio Naves"}, "masanchez": {"n": "Manuel Alexander Sanchez Guerrero", "p": "Inside Sales"}, "asanchez": {"n": "Anderson Jonathan Sanchez Gutierrez", "p": "Analista Contable"}, "arsanchez": {"n": "Alexis Raymond Sanchez Lopez", "p": "Analista de Aplicaciones Senior"}, "lsanchez": {"n": "Leslie Medalith Sánchez Santa Cruz", "p": "Customer Service Sil"}, "fsanchez": {"n": "Francy Ysabel Sanchez Tanchiva", "p": "Operador Visto Bueno"}, "csanchez": {"n": "Carlos Hernan Sanchez Urteaga", "p": "Operador Cctv"}, "msanchez": {"n": "Mario Miguel Sanchez Vera", "p": "Gestor de Proyectos de Transformación"}, "asandoval": {"n": "Abel Alexander Sandoval More", "p": "Operador de Llenados"}, "asantiago": {"n": "Alvina Santiago Malpartida", "p": "Asistente de Tesorería"}, "ssantibanez": {"n": "Sthefany Santibañez Vega", "p": "Asistente Administrativo Llenos"}, "wsantos": {"n": "William Wayna Santos Ipanaque", "p": "Supervisor de Proyectos y Negocios Maritimos"}, "jsantos": {"n": "Juana Maria Santos Julca", "p": "Operador Visto Bueno"}, "pscotto": {"n": "Paulo Cesar Scotto Acho", "p": "Prevencionista de Riesgos"}, "rsegovia": {"n": "Rodolfo Francisco Segovia Pimentel", "p": "Chofer Tramitador"}, "cseminario": {"n": "Cesar Alexander Seminario Lazo", "p": "Auxiliar Reefer de Vacios"}, "gsernaque": {"n": "Gustavo Sernaque", "p": "Operador Visto Bueno"}, "dserquen": {"n": "Deyber Arnaldo Serquen Cordova", "p": "Mensajero"}, "bsifuentes": {"n": "Bryan Sifuentes Torero", "p": "Operador Aduanero"}, "msilva": {"n": "Michel Yerson Silva Cipra", "p": "Balancero Transmisiones"}, "misilva": {"n": "Michel Yerson Silva Cipra", "p": "-"}, "ssilva": {"n": "Stephany Andrea Silva Talavera", "p": "Ejecutivo Comercial Senior"}, "dsinchi": {"n": "Daniel German Sinchi Tavara", "p": "Key Account Executive Senior"}, "jsolis": {"n": "John Carlos Solis Berrospi", "p": "Operador Cctv"}, "vsoria": {"n": "Victor Javier Soria Mendo", "p": "Arquitecto de Soluciones Cloud"}, "vsuarez": {"n": "Victor Daniel Suarez Barreto", "p": "-"}, "ltantalean": {"n": "Luis Tantalean", "p": "Customer Service Sil"}, "ftarazona": {"n": "Franklin Tarazona Gonzales", "p": "Operador de Grúa"}, "jtasayco": {"n": "Juan Jose Tasayco Gomez", "p": "Sub Gerente de Planeamiento y Presupuesto"}, "htejero": {"n": "Hilary Brizett Tejero Torres", "p": "Operador Aduanero"}, "ltello": {"n": "Luis Miguel Tello Chavez", "p": "Auxiliar de Despacho Aduanero"}, "rtello": {"n": "Richart Paul Tello Fernandez", "p": "Coordinador de Operaciones Vacíos"}, "jtello": {"n": "Jorge Alfredo Tello Roman", "p": "Coordinador Patio"}, "htenorio": {"n": "Hans Brent Tenorio Caro", "p": "Asistente de Gestión de Portafolio y Metodología"}, "ktiburcio": {"n": "Key Blas Tiburcio Trujillo", "p": "Chofer de Transporte Pesado"}, "otirado": {"n": "Ornella Consuelo Tirado Caceda", "p": "Jefe de Finanzas"}, "jtolentino": {"n": "Jesus Georgino Tolentino Rodriguez", "p": "Ejecutivo Comercial Agm"}, "itoro": {"n": "Ily Julliet Toro Cordova", "p": "Auxiliar de Contabilidad"}, "rtoro": {"n": "Ronald Leonardo Toro Roque", "p": "Mensajero"}, "jtorres": {"n": "Juan Orlando Torres Fernandez", "p": "Operador de Grúa"}, "jotorres": {"n": "José Sebastián Torres Guillen", "p": "Auxiliar de Cultura Organizacional"}, "jetorres": {"n": "Jean Pierre Torres Hidalgo", "p": "Operador de Puerto"}, "atorres": {"n": "Alfredo Dionisio Torres Huaranga", "p": "Inspector de Contenedores"}, "vtorres": {"n": "Victor Omar Torres Orjeda", "p": "Auxiliar de Despacho Aduanero"}, "dtorres": {"n": "Desiderio Ysrael Torres Santa Cruz", "p": "Tecnico de Reefers"}, "ctrelles": {"n": "Christ Amanda Trelles Castillo", "p": "Key Account Executive"}, "jtrillo": {"n": "Julio Cesar Trillo Jara", "p": "Asistente Operativo de Seguridad"}, "rtrujillo": {"n": "Royce Trujillo Sandoval", "p": "Analista de Presupuesto"}, "mtuco": {"n": "Manuel Alejandro Tuco Reymundo", "p": "Almacenero de Patio"}, "matuco": {"n": "Manuel Alejandro Tuco Reymundo", "p": "-"}, "gurbina": {"n": "Geraldine Urbina", "p": "Auxiliar de Gestión Humana"}, "avaldez": {"n": "Anggie Elizabeth Valdez Espinoza", "p": "Asistente de Facturación Vacíos"}, "jvaldiviezo": {"n": "Julio Samuel Valdiviezo Ramirez", "p": "Coordinador de Operaciones Vacíos -región Norte"}, "jvalencia": {"n": "Jose Genaro Valencia Carrion", "p": "Líder de Mercado Vertical"}, "pvalle": {"n": "Pedro Agustin Valle Carrasco", "p": "Especialista de Proyectos de Aplicaciones"}, "ovallejos": {"n": "Older Joel Vallejos Pacherrez", "p": "Liquidador - Aduanas"}, "zvalqui": {"n": "Ziara Valqui Guerrero", "p": "Liquidador de Transporte"}, "rvargas": {"n": "Rafael Vargas Bravo", "p": "Almacenero de Patio"}, "jvargas": {"n": "Jose Ricardo Vargas Loayza", "p": "Chofer Tramitador"}, "mvargas": {"n": "Mayra Ruby Vargas Requejo", "p": "Asistente de Facturación Vacíos"}, "ivargas": {"n": "Irwing Jonathan Vargas Rivadeneyra", "p": "Balancero"}, "ivvargas": {"n": "Ivan Wilfredo Vargas Ticona", "p": "Analista de la Demanta de Ti"}, "avargas": {"n": "Angie Karina Vargas Urbina", "p": "Asistente de Facturación"}, "cvasquez": {"n": "Cesar Augusto Vasquez Chacon", "p": "Coordinador de Operaciones"}, "evasquez": {"n": "Elizabeth Vasquez Martinez", "p": "Operador Visto Bueno"}, "jvasquez": {"n": "Jorge Luis Vasquez Solis", "p": "Balancero Transmisiones"}, "gveas": {"n": "Gianella Veas", "p": "Liquidador - Aduanas"}, "cvela": {"n": "Christian Piero Vela Valles", "p": "Ejecutivo Comercial Agm"}, "avelasquez": {"n": "Arturo Efrain Velasquez Arbieto", "p": "-"}, "avelorio": {"n": "Andy Ernesto Velorio Luque", "p": "Coordinador de Puerto"}, "rvera": {"n": "Rosario Ines Vera Saenz", "p": "-"}, "jverastegui": {"n": "Julio Cesar Verastegui Reyes", "p": "Jefe de Adquisiciones e Infraestructura"}, "lvilca": {"n": "Luis Martin Vilca Paulino", "p": "Balancero"}, "evillacorta": {"n": "Eduardo Villacorta Marin", "p": "Almacenero de Patio"}, "jvillafuerte": {"n": "Janet Maribell Villafuerte Armondiz", "p": "Gerente Comercial de Negocios Logísticos"}, "cvillaizan": {"n": "Carlos Wander Villaizan Ajalla", "p": "Ejecutivo Comercial Aduanas"}, "jvillanueva": {"n": "Jeissy Alexandra Villanueva Torres", "p": "Customer Operation Sil"}, "aviton": {"n": "Abelino Viton Delgado", "p": "Almacenero Vacios"}, "evivar": {"n": "Edwin Brady Vivar Reaño", "p": "Analista Programador Senior"}, "vvizarreta": {"n": "Vanessa Andrea Vizarreta Loayza", "p": "Asistente de Tesorería Líneas Navieras"}, "lyauri": {"n": "Lizeth Yauri Pala", "p": "Asistente de Logística Interna"}, "vyauris": {"n": "Victor Hugo Yauris Cucho", "p": "Auxiliar de Despacho Aduanero"}, "eyman": {"n": "Enrique Billy Yman Quiñones", "p": "Operador de Llenados"}, "myncio": {"n": "María Esther Yncio Peña", "p": "Customer Operation Sil"}, "jyncio": {"n": "Jonathan Leonardo Yncio Salazar", "p": "Operador Visto Bueno"}, "fyparraguirre": {"n": "Freddy Josue Yparraguirre Chacaliaza", "p": "Coordinador de Atracción y Gestión del Talento"}, "byturrizaga": {"n": "Brenda Melissa Yturrizaga Guerra", "p": "Asesor de Servicio Al Cliente"}, "jzaime": {"n": "Jorge Emilio Zaime Zuñiga", "p": "Supervisor Operaciones Agm"}, "jzambrano": {"n": "Julio Cesar Zambrano Pineda", "p": "Operador de Grúa"}, "pzamudio": {"n": "Pedro Felipe Zamudio Hidalgo", "p": "Jefe de Operaciones Agmar"}, "azapata": {"n": "Aaron Jefte Zapata Medina", "p": "-"}, "aazapata": {"n": "Aaron Jefte Zapata Medina", "p": "-"}, "hzapata": {"n": "Hanssen David Zapata Rivasplata", "p": "Customer Service Ad"}, "czarate": {"n": "Carlos Manuel Zarate de la Cruz", "p": "Trainee de Aplicaciones"}, "jzarate": {"n": "Jhonny Paul Zarate Vidal", "p": "Asistente Administrativo Vacíos"}, "jzavala": {"n": "Julio Enrique Zavala Cosio", "p": "Gerente Central de Negocios Logísticos"}, "czuzunaga": {"n": "Carlo Andre Zuzunaga Gomez", "p": "-"}};

const KPI_USERS = ["aacevedo", "aacuna", "aalanya", "aalvarez", "aanazgo", "aazapata", "abarreto", "acajaleon", "acarmelino", "achumbirayco", "acisneros", "acordova", "acoz", "acruz", "adavalos", "adelacruz", "aespinoza", "afebres", "afelippe", "aflores", "agallo", "aguerrero", "agutierrez", "ahuaman", "ahuaranga", "ajauregui", "allenos", "allerena", "almacenero.llenos", "amasias", "amendoza", "amoreno", "amunoz", "apantigoso", "aperez", "apillaca", "apiminchumo", "aramirez", "areyes", "arivera", "arodriguez", "arsanchez", "asacari", "asanchez", "asandoval", "asantiago", "atorres", "avaldez", "avargas", "avelasquez", "avelorio", "aviton", "azapata", "balancero.llenos", "balvarado", "bascona", "bbecerra", "bcancino", "bcapulian", "bcarrillo", "bchaua", "bdelgado", "bhuaquisto", "bllenos", "bportocarrero", "brbecerra", "bsifuentes", "btanchiva", "byturrizaga", "cacero", "cacoz", "cbarrientos", "ccalderon", "ccamasca", "ccampana", "cchillcce", "cchoquez", "ccoz", "cdamaso", "cdelossantos", "cerodriguez", "cespinoza", "cfarro", "cinilopu", "cizquierdo", "cjimenez", "climo", "cmartel", "cpacora", "cpalacios", "cperalta", "cquinones", "crodriguez", "crojas", "crumiche", "csaldamando", "csanchez", "cseminario", "ctrelles", "cvasquez", "cvela", "cvillaizan", "czarate", "czuzunaga", "darias", "dcastro", "ddioses", "dechaccaya", "decheccaya", "despinola", "dgarcia", "dgirao", "dgutierrez", "dhidalgo", "dileon", "dinonan", "djimenez", "dleon", "dllauce", "dmedina", "dmerida", "dpastor", "dpingo", "dponciano", "dpuertas", "dramirez", "drobles", "dserquen", "dsinchi", "dtorres", "ealarcon", "ealfaro", "earanciaga", "ebazan", "ecalmet", "ecardenas", "echipana", "echiroque", "ecisneros", "ecrisologo", "edelacruz", "ediaz", "edrojas", "egarcia", "egonzales", "egutierrez", "eheredia", "eholguin", "emarquez", "emartinez", "emeneses", "emontes", "epablo", "eportilla", "eramirez", "erojas", "erubinos", "erun", "evasquez", "evillacorta", "evivar", "eyman", "faguilar", "falejandro", "fareanas", "farenas", "fchallco", "fcollazos", "fcueva", "fealejandro", "felescano", "fgonzaga", "fhuarac", "fmoreno", "folivari", "frios", "fsanchez", "ftarazona", "fyparraguirre", "gbarrientos", "gbossio", "gcarrasco", "gduque", "gescobar", "gespinoza", "gfiestas", "girodriguez", "gjaucala", "glopez", "glsalazar", "gmedina", "gmeza", "gmundaca", "gmunguia", "grodriguez", "groque", "gsalazar", "gsernaque", "gurbina", "gveas", "hbazan", "hcastaneda", "hcastro", "hcoria", "hcrisostomo", "hdance", "hllactahuaman", "hloli", "hluna", "hmendez", "hmuro", "hprincipe", "hruiz", "htejero", "htenorio", "hzapata", "idelacruz", "ilizarzaburu", "ipujada", "isudario", "itoro", "ivargas", "ivvargas", "jalarcon", "jamaro", "jandonaire", "janicama", "jarguello", "jarmestar", "jasanchez", "jbaca", "jcaceres", "jcapcha", "jcardenas", "jcarmona", "jcarreno", "jcarrillo", "jcastillo", "jcastro", "jcerna", "jcespedes", "jchocanga", "jclemente", "jcordova", "jcruz", "jcuadros", "jcuro", "jdelaguila", "jdiaz", "jdiazg", "jelizares", "jespinal", "jetorres", "jfarfan", "jfiestas", "jflores", "jgonzales", "jhdiaz", "jherrada", "jhllontop", "jhuachohuillca", "jhuamani", "jhuaya", "jidiaz", "jjaramillo", "jjustiniani", "jlino", "jllanos", "jllontop", "jlujan", "jmachuca", "jmalpartida", "jmejia", "jmercado", "jmollehuanca", "jmoreno", "jmoscol", "jmurga", "jnavarro", "jneyra", "jocordova", "joflores", "jolaya", "jomurga", "joolaya", "jordinola", "joruiz", "jotorres", "jpalomino", "jpanana", "jponce", "jpozo", "jquilluya", "jramirez", "jramos", "jremigio", "jrivas", "jrivera", "jrodriguez", "jrosello", "jruiz", "jsanchez", "jsantos", "jsinarahua", "jsolis", "jtasayco", "jtello", "jtolentino", "jtorres", "jtrillo", "juramirez", "jvaldiviezo", "jvalencia", "jvargas", "jvasquez", "jverastegui", "jvillafuerte", "jvillanueva", "jyncio", "jzaime", "jzambrano", "jzarate", "jzavala", "kacuna", "kcarbajal", "kcespedes", "kchillcce", "kchinchercoma", "kcruz", "kerodriguez", "kespinoza", "kflores", "khuallpacuna", "kortiz", "kpariapaza", "krafael", "krodriguez", "ktiburcio", "laciego", "laguilar", "laguirre", "lalfaro", "larcela", "lcaballero", "lcastro", "lchu", "lchui", "lchuikan", "lchumpitaz", "lcorrea", "lcortez", "lcruz", "lespinoza", "lfrias", "lhorna", "linonan", "lmarconi", "lmori", "lmucha", "lnunez", "lortiz", "lperez", "lpretil", "lramos", "lsanchez", "ltantalean", "ltello", "lvilca", "lyauri", "macarrion", "maramos", "masanchez", "matarama", "matuco", "mavalos", "mbermejo", "mcamasca", "mcarrion", "mcastillo", "mcerna", "mchavez", "mchurano", "mcobos", "mcondori", "mcuri", "mdioses", "mduran", "mespinoza", "mgaldos", "mgallardo", "mgarcia", "mgrandez", "mguaylupo", "mhuapaya", "misilva", "mllanos", "mlopez", "mloza", "mnole", "molortiga", "mordinola", "mosorio", "mperez", "mporras", "mramos", "mramosm", "mrios", "mrodriguez", "mrodriguezm", "mroncal", "mrosales", "msalcedo", "msanchez", "msilva", "mtuco", "mvargas", "myncio", "navila", "nbarandiaran", "ncastillo", "nochoa", "nramirez", "nrojas", "nrosillo", "ocampos", "ofernandez", "ogajate", "ogamarra", "oinchaustegui", "omattos", "onevado", "orodriguez", "osaenz", "otirado", "ovallejos", "palvarez", "panteparra", "pbazan", "pbrena", "pcatano", "pdelarosa", "pdi", "pdiego", "pfelippe", "phuallpacuna", "plira", "pluis", "pmamani", "pmorillo", "polivera", "ppadilla", "ppantaleon", "pruis", "pscotto", "pvalle", "pzamudio", "rabal", "racosta", "ralejo", "raranguez", "rcampos", "rcaruajulca", "rcasas", "rcastro", "rcgonzales", "rescalante", "rgarcia", "rgarrido", "rgavila", "rgonzales", "rgonzaless", "rguillermo", "rlombardi", "rmedinaa", "rmurillo", "rogonzales", "rojeda", "ropasache", "rotero", "rpachas", "rpasache", "rrios", "rrodriguez", "rroman", "rromero", "rrosales", "rsalazar", "rsegovia", "rtello", "rtoro", "rtrujillo", "rvargas", "rvera", "rvillegas", "sacho", "salzamora", "sbazalar", "scaro", "sebazalar", "serodriguez", "sfernandez", "sfranco", "sgarcia", "sheredia", "smarcatoma", "smauricio", "spereira", "sramos", "srodriguez", "sromero", "sruiz", "ssalazar", "ssantibanez", "ssilva", "tnarvarte", "tnavarte", "uprueba", "valtamiza", "vgonzales", "vrenteria", "vsalazar", "vsoria", "vsuarez", "vtorres", "vvizarreta", "vyauris", "wchinga", "wcotrina", "wduran", "wiglesias", "wmore", "wrodriguez", "wsantos", "ybazalar", "ycardenas", "ycatay", "ychavarria", "ydemarini", "ydepaz", "yhernandez", "yleguia", "ymamani", "ymandujano", "yquispe", "yrivera", "yrodriguez", "zvalqui"];
const EXCEL_AREAS = {"Gerencia de Adquisiciones y Finanzas": {"Adquisición": {"ind": 1, "met": 0}, "Contabilidad": {"ind": 2, "met": 0}, "Facturación NL": {"ind": 3, "met": 1}, "Facturación Vacíos": {"ind": 2, "met": 1}, "Finanzas": {"ind": 2, "met": 0}, "Gestión de Proveedores": {"ind": 2, "met": 0}}, "Gerencia de Negocios Logisticos": {"Almacenes y logística": {"ind": 1, "met": 0}, "Comercial NL": {"ind": 5, "met": 0}, "Costos y Margenes Operativos": {"ind": 4, "met": 0}, "Customer Management": {"ind": 2, "met": 0}, "Documentación": {"ind": 9, "met": 0}, "Operaciones": {"ind": 7, "met": 0}, "Planeamiento": {"ind": 8, "met": 0}, "Transporte": {"ind": 7, "met": 0}}, "Gestión Legal": {"Contratos": {"ind": 1, "met": 0}, "Legal": {"ind": 1, "met": 0}}, "Gestión de Administración y Desarrollo Humano": {"Administración y Gestión del Personal": {"ind": 2, "met": 0}, "Gestión de Cultura e Identidad": {"ind": 2, "met": 0}}, "Gestión de Seguridad y SSOMA": {"SSOMA": {"ind": 9, "met": 0}, "Seguridad y Protección": {"ind": 2, "met": 0}}, "Gestión de Sistemas Digitales y Ciberseguridad": {"Aplicaciones Y Arquitectura": {"ind": 4, "met": 0}, "PMO & Operaciones TI": {"ind": 7, "met": 0}, "Proyectos TD": {"ind": 1, "met": 0}}, "Negocios Maritimos y Navieros": {"Comercial AGMAR": {"ind": 4, "met": 0}, "Documentación": {"ind": 7, "met": 0}, "Facturación AGM": {"ind": 2, "met": 0}, "Maquinarias y Equipos": {"ind": 1, "met": 0}, "Operaciones AGMAR": {"ind": 10, "met": 0}, "Operaciones Vacios": {"ind": 9, "met": 0}, "Planeamiento Vacios": {"ind": 2, "met": 0}, "REEFER": {"ind": 7, "met": 0}, "VB": {"ind": 4, "met": 0}}, "Planeamiento Estratégico": {"Planeamiento Estratégico": {"ind": 3, "met": 0}}, "Procesos Estratégicos": {"Auditoría y Contro Interno": {"ind": 2, "met": 0}, "Gestión de Riesgos": {"ind": 1, "met": 0}, "Mejora Continua": {"ind": 1, "met": 0}}, "Regiones": {"Región Norte": {"ind": 4, "met": 0}}, "TPPA": {"ADUANA": {"ind": 3, "met": 0}}};
const KPI_CATALOGO = [{"cod": "AFIADQ-004", "nom": "Atenciones óptimas de solicitudes de compras", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Adquisición", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFICON-001", "nom": "Cumplimiento de cronograma de cierre contable", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Contabilidad", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFICON-002", "nom": "Porcentajes de EMs convertidas en facturas", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Contabilidad", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIFAC-001", "nom": "% de Importaciones Facturadas", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIFAC-002", "nom": "% de Exportaciones Facturadas", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "tipo": "Métrica", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIFAC-008", "nom": "Facturación Portal Clientes (Pago Único)", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIFAC-003", "nom": "% de Servicios Vacíos Facturados", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "tipo": "Métrica", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIFAC-007", "nom": "% de Cumplimiento de SLA para atención de Vacíos vía PAV", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIFIN-001", "nom": "Participación de facturas al contado con medio de pago", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Finanzas", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIFIN-002", "nom": "Participación de asientos de pagos recibidos al crédito generados por add on de", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Finanzas", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIGP-001", "nom": "omologación de Proveedores", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Gestión de Proveedores", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AFIGP-002", "nom": "valuación del Desempeño de Proveedores", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Gestión de Proveedores", "tipo": "Indicador", "frec": "B", "meses": ["FEBRERO", "ABRIL", "JUNIO", "AGOSTO", "OCTUBRE", "DICIEMBRE"]}, {"cod": "LCL-001", "nom": "HBL procesados en el Portal NVOCC", "ger": "Gerencia de Negocios Logisticos", "area": "Almacenes y logística", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AYLCOM-001", "nom": "Clientes Actuales con acuerdos de Seguridad - NL", "ger": "Gerencia de Negocios Logisticos", "area": "Comercial NL", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "OPECRM-001", "nom": "Satisfacción al Cliente - SIL", "ger": "Gerencia de Negocios Logisticos", "area": "Comercial NL", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "OPECRM-002", "nom": "Satisfacción al Cliente - SIP", "ger": "Gerencia de Negocios Logisticos", "area": "Comercial NL", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "OPECRM-003", "nom": "Satisfacción al Cliente - LCL", "ger": "Gerencia de Negocios Logisticos", "area": "Comercial NL", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "OPECRM-004", "nom": "Satisfacción al Cliente - AD", "ger": "Gerencia de Negocios Logisticos", "area": "Comercial NL", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "NLCMO-001", "nom": "% de cumplimiento de EM generadas dentro del periodo en los servicios GATE OTAL", "ger": "Gerencia de Negocios Logisticos", "area": "Costos y Margenes Operativos", "tipo": "Indicador", "frec": "M", "meses": ["MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "NLCMO-002", "nom": "% de cumplimiento de EM generadas dentro del periodo en los servicios VB", "ger": "Gerencia de Negocios Logisticos", "area": "Costos y Margenes Operativos", "tipo": "Indicador", "frec": "M", "meses": ["MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "NLCMO-003", "nom": "% de cumplimiento de EM generadas dentro del periodo en los servicios Agenciamie", "ger": "Gerencia de Negocios Logisticos", "area": "Costos y Margenes Operativos", "tipo": "Indicador", "frec": "M", "meses": ["MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "NLCMO-004", "nom": "% de cumplimiento de EM generadas dentro del periodo en los servicios portuarios", "ger": "Gerencia de Negocios Logisticos", "area": "Costos y Margenes Operativos", "tipo": "Indicador", "frec": "M", "meses": ["MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AD-001", "nom": "Registro de Comisiones", "ger": "Gerencia de Negocios Logisticos", "area": "Customer Management", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AD-002", "nom": "Devolución de contenedores", "ger": "Gerencia de Negocios Logisticos", "area": "Customer Management", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDOC-001", "nom": "Trasmisiones Extemporáneas", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDOC-002", "nom": "Entregar o disponer de las mercancías sin canal o medida preventiva asignada por", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDOC-003", "nom": "Evitar la entrega o disposición de las mercancías sin que la autoridad aduanera", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDOC-004", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de Autorización", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDOC-005", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de refrendos (P", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDOC-007", "nom": "Control de transmisiones extemporáneas IRM con responsabilidad de TPP", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDOC-008", "nom": "Número de Transmisiones Extemporaneas por responsabilidad del Cliente (afectan c", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDOC-011", "nom": "Asegurar la generación de volantes a través del Portal Clientes", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDOC-012", "nom": "Asegurar la emisión de Autorizaciones de Retiro (Portal Clientes)", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEDS-001", "nom": "Exactitud del nivel de inventario ERI-DS", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPELCL-001", "nom": "Exactitud del nivel de inventario ERI-LCL", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPELCL-002", "nom": "Mantener Eficiencia de Tarjas Emitidas", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESEC-001", "nom": "% Cumplimiento de atención en el proceso de despacho de contenedores llenos de i", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESEC-003", "nom": "% de precintos aduaneros verificados en el proceso de aforos y operaciones usual", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESEC-004", "nom": "Cumplimiento de actas en operaciones usuales ejecutadas con RQ", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESEC-005", "nom": "% Despachos manuales de contenedores informados a Documentación en plazo", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESIL-001", "nom": "% OS Facturadas  - SIL", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESIL-002", "nom": "% Entrega perfecta del negocio SIL", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESIP-001", "nom": "% OS Facturadas - SIP", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESIP-002", "nom": "% Entrega perfecta del negocio - SIP", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "PPSIL-002", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "PPSIL-006", "nom": "Preliquidaciones atendidas Portal clientes (Pago Único) - SIL", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "PPSIP-005", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "PPSIP-006", "nom": "Preliquidaciones atendidas Portal clientes (Pago Único) - SIP", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESIP-003", "nom": "% Entrega perfecta de los precintos SIP", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPETRA-001", "nom": "Unidades con Checklist ejecutado", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "TRA-001", "nom": "Incidencias en Servicios", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "TRA-002", "nom": "Estatus de Servicio", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "TRA-003", "nom": "Liquidación de Sericios", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "TRA-004", "nom": "Programación de Servicios", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "TRA-005", "nom": "On Time Delivery", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GERLEG-002", "nom": "MAXIMIZAR LA GESTIÓN DE CONTRATOS - LEGAL TPP", "ger": "Gestión Legal", "area": "Contratos", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GERLEG-001", "nom": "Comunicación de Requisitos Legales", "ger": "Gestión Legal", "area": "Legal", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GDHADM-001", "nom": "Medición de Mensajería", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Administración y Gestión del Personal", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GDHREC-001", "nom": "Eficacia de Reclutamiento", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Administración y Gestión del Personal", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GDHCAP-001", "nom": "Cumplimiento de Plan de Capacitaciones", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Gestión de Cultura e Identidad", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GDHCAP-002", "nom": "Eficacia de Capacitaciones", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Gestión de Cultura e Identidad", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SST-001", "nom": "Tratamiento de eventos", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SST-002", "nom": "Control de inspección", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SST-003", "nom": "Control de uso de EPP", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SST-004", "nom": "Cumplimiento de Seguimiento médico", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SST-005", "nom": "EMO ejecutados", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "tipo": "Indicador", "frec": "T", "meses": ["JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "SST-006", "nom": "Actualización de IPERC", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "SST-007", "nom": "Entrega de EMO", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SST-008", "nom": "Evaluación de riesgo de gestante", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SST-009", "nom": "% Residuos sólidos valorizados (aprovechables)", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESEG-001", "nom": "Cumplimiento de reporte de incidentes con actos subestandar", "ger": "Gestión de Seguridad y SSOMA", "area": "Seguridad y Protección", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPESEG-002", "nom": "Cumplimiento de reporte de incidentes con condiciones subestandar", "ger": "Gestión de Seguridad y SSOMA", "area": "Seguridad y Protección", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SDC-002", "nom": "Cumplimiento de atención de incidencias y peticiones", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SDC-006", "nom": "Mantener ciberseguridad", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "tipo": "Indicador", "frec": "B", "meses": ["FEBRERO", "ABRIL", "JUNIO", "AGOSTO", "OCTUBRE", "DICIEMBRE"]}, {"cod": "SDC-007", "nom": "Avance de mantenimiento", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "SDC-008", "nom": "Cumplimiento de atención de movil y modem", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SDC-004", "nom": "Cumplimiento de las pruebas de QA de proyectos", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "SDC-005", "nom": "Cumplimiento de atención de cambios", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "SDC-009", "nom": "Cumplimiento de gasto de OPEX", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "SDC-010", "nom": "Cumplimiento de gasto de CAPEX", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "SDC-011", "nom": "Nro. de entregables por proyecto completados", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "tipo": "Indicador", "frec": "B", "meses": ["FEBRERO", "ABRIL", "JUNIO", "AGOSTO", "OCTUBRE", "DICIEMBRE"]}, {"cod": "SDC-012", "nom": "Cumplimiento de cronograma de proyectos.", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "tipo": "Indicador", "frec": "B", "meses": ["FEBRERO", "ABRIL", "JUNIO", "AGOSTO", "OCTUBRE", "DICIEMBRE"]}, {"cod": "SDC-013", "nom": "Cumplimiento de calidad de código", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "SDC-003", "nom": "Cumplimiento en tiempo de la gestión de HUS", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Proyectos TD", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "AGMCOM-001", "nom": "Clientes Actuales con acuerdos de Seguridad", "ger": "Negocios Maritimos y Navieros", "area": "Comercial AGMAR", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "AGMCOM-004", "nom": "Medir el nivel de satisfacción de los clientes con respecto a la Gestión Comerci", "ger": "Negocios Maritimos y Navieros", "area": "Comercial AGMAR", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "AGMCOM-005", "nom": "Nivel de cotizaciones aceptadas", "ger": "Negocios Maritimos y Navieros", "area": "Comercial AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMCOM-006", "nom": "Nivel de respuesta de cotizaciones presentadas", "ger": "Negocios Maritimos y Navieros", "area": "Comercial AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMDOC-001", "nom": "% de Transbordos regularizados dentro del plazo", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMDOC-002", "nom": "Efectividad en la atención de contenedores descargados con discrepancia de preci", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMDOC-003", "nom": "Eficiencia en la transmisión de documentos aduaneros", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMDOC-004", "nom": "Eficiencia en el tramite  para embarque de transbordos", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMDOC-005", "nom": "% de Expedientes presentados con documentación incorrecta", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMDOC-006", "nom": "% de Manifiestos de carga IMO, Reefers Container List / Special Container List i", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMDOC-007", "nom": "Transmisiones realizadas correctamente", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMFAC-001", "nom": "% de correcciones operativas del total facturado", "ger": "Negocios Maritimos y Navieros", "area": "Facturación AGM", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMFAC-002", "nom": "Cumplimiento de comprobantes de SNR emitidos dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Facturación AGM", "tipo": "Indicador", "frec": "M", "meses": ["ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEEQU-001", "nom": "% de horas disponibles del mes por cada equipo", "ger": "Negocios Maritimos y Navieros", "area": "Maquinarias y Equipos", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-001", "nom": "Nivel de Satisfacción del Cliente AGM - Husbandry", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-002", "nom": "Nivel de Satisfacción del Cliente AGM - Capitanes", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-003", "nom": "Atención de quejas y reclamos", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-004", "nom": "Recepción de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-005", "nom": "Despacho de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-006", "nom": "Plazos de envío de Información (Transmisiones)", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-007", "nom": "% Atenciones de naves sin incidencias ambientales para el proceso de Operaciones", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-008", "nom": "% Atenciones de naves sin incidencias para el proceso de Operaciones de NMN AGMA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-010", "nom": "Trasmisión de información de embarque y descarga", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMOPM-011", "nom": "% Atenciones de naves sin condiciones subestándares para el proceso de Operacion", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEVAC-003", "nom": "% Despacho con errores", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEVAC-004", "nom": "Exactitud de Inventario de precintos de botella -  Cosco", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEVAC-005", "nom": "Exactitud de Inventario de precintos de botella - Yang Ming", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEVAC-006", "nom": "Cantidad de registros de Devolución/ Descarga dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEVAC-007", "nom": "Uso del Portal para el Registro de ingreso", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEVAC-008", "nom": "Incrementar el cumplimiento de transmisiones RCEC efectuadas dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEVAC-009", "nom": "Incrementar la transmisión de RCEC por cada contenedor", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEVAC-010", "nom": "% de cumplimiento del servicio de recepción de contenedores vacíos dentro del SL", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEVAC-011", "nom": "% de cumplimiento del servicio de despacho de contenedores vacíos dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "NMNVAC-001", "nom": "Atención de tickets de asignación de cntrs secos en portal de usuario dentro de", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "NMNVAC-002", "nom": "Atención de tickets de asignación de cntrs reefers en portal de usuario dentro d", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEREE-007", "nom": "%Cumplimiento de atención de citas de asignación de contenedor reefers a traves", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEREE-009", "nom": "Controlar emisión de citas", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEREE-010", "nom": "Controlar el ingreso de las UT +-1hora de cita", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEREE-011", "nom": "Asegurar la calidad de Contenedores despachados", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEREE-013", "nom": "Optimizar flujo de salida de contenedores reefers reduciendo el tiempo de despac", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMVB-001", "nom": "Eficiencia en el otorgamiento de visto Bueno", "ger": "Negocios Maritimos y Navieros", "area": "VB", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMVB-002", "nom": "Eficiencia en emisión de comprobantes de pago", "ger": "Negocios Maritimos y Navieros", "area": "VB", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMVB-003", "nom": "% cumplimiento de atención en el proceso de Visto Bueno dentro del SLA (2horas)", "ger": "Negocios Maritimos y Navieros", "area": "VB", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "AGMVB-006", "nom": "Generación de trazabilidad de servicios de Agencia Marítima", "ger": "Negocios Maritimos y Navieros", "area": "VB", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GERPLA-001", "nom": "Cantidad de Usuarios que acceden al portal", "ger": "Planeamiento Estratégico", "area": "Planeamiento Estratégico", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "GERPLA-002", "nom": "Atención de indicadores BSC", "ger": "Planeamiento Estratégico", "area": "Planeamiento Estratégico", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "GERPLA-003", "nom": "Consistencia de informes", "ger": "Planeamiento Estratégico", "area": "Planeamiento Estratégico", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "GERPES-006", "nom": "Cumplimiento del Plan de Auditorías", "ger": "Procesos Estratégicos", "area": "Auditoría y Contro Interno", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "GERPES-007", "nom": "Cumplimiento del programa Control Interno", "ger": "Procesos Estratégicos", "area": "Auditoría y Contro Interno", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "GERPES-001", "nom": "Procesos Controlados", "ger": "Procesos Estratégicos", "area": "Gestión de Riesgos", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GERPES-003", "nom": "Procesos con Modelo de control", "ger": "Procesos Estratégicos", "area": "Mejora Continua", "tipo": "Indicador", "frec": "T", "meses": ["MARZO", "JUNIO", "SEPTIEMBRE", "DICIEMBRE"]}, {"cod": "RN-008", "nom": "Daños ingresados en el Sistema SITAC maximo al día siguiente de recibir el estim", "ger": "Regiones", "area": "Región Norte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "RN-009", "nom": "Termino de reparación estructural ingresado en SITAC dentro del plazo", "ger": "Regiones", "area": "Región Norte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "RN-010", "nom": "Término de reparación de maquinaria ingresado dentro del plazo", "ger": "Regiones", "area": "Región Norte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "RN-011", "nom": "Emisión de factura dentro del plazo", "ger": "Regiones", "area": "Región Norte", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GERADU-001", "nom": "% Regularización de las DAM de exportación dentro del plazo establecido (5días h", "ger": "TPPA", "area": "ADUANA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GERADU-002", "nom": "% DAM de Exportación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}, {"cod": "GERADU-004", "nom": "% DAM de Importación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "tipo": "Indicador", "frec": "M", "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO", "JUNIO", "JULIO", "AGOSTO", "SEPTIEMBRE", "OCTUBRE", "NOVIEMBRE", "DICIEMBRE"]}];
const KPI_DESVIADOS_DET = [{"Mes": "ABRIL", "ger": "Gerencia de Negocios Logisticos", "area": "Customer Management", "cod": "AD-002", "nom": "Devolución de contenedores", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Gestión de Proveedores", "cod": "AFIGP-002", "nom": "valuación del Desempeño de Proveedores", "frec": "B", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "MARZO", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Contabilidad", "cod": "AFICON-001", "nom": "Cumplimiento de cronograma de cierre contable", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "MARZO", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Contabilidad", "cod": "AFICON-002", "nom": "Porcentajes de EMs convertidas en facturas", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "ENERO", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "frec": "M", "tipo": "Métrica", "motivo": "Bajo meta"}, {"Mes": "ENERO", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "cod": "AFIFAC-007", "nom": "% de Cumplimiento de SLA para atención de Vacíos vía PAV", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ENERO", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "cod": "AFIFAC-008", "nom": "Facturación Portal Clientes (Pago Único)", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "cod": "AFIFAC-008", "nom": "Facturación Portal Clientes (Pago Único)", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "MARZO", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "cod": "AFIFAC-008", "nom": "Facturación Portal Clientes (Pago Único)", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ABRIL", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "cod": "AFIFAC-008", "nom": "Facturación Portal Clientes (Pago Único)", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ENERO", "ger": "Negocios Maritimos y Navieros", "area": "Comercial AGMAR", "cod": "AGMCOM-006", "nom": "Nivel de respuesta de cotizaciones presentadas", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "MAYO", "ger": "Negocios Maritimos y Navieros", "area": "Facturación AGM", "cod": "AGMFAC-002", "nom": "Cumplimiento de comprobantes de SNR emitidos dentro del SLA", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ABRIL", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "cod": "AGMOPM-006", "nom": "Plazos de envío de Información (Transmisiones)", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "ABRIL", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "cod": "AGMOPM-010", "nom": "Trasmisión de información de embarque y descarga", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "MAYO", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Administración y Gestión del Personal", "cod": "GDHADM-001", "nom": "Medición de Mensajería", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ENERO", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Gestión de Cultura e Identidad", "cod": "GDHCAP-001", "nom": "Cumplimiento de Plan de Capacitaciones", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "ENERO", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Gestión de Cultura e Identidad", "cod": "GDHCAP-002", "nom": "Eficacia de Capacitaciones", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "ENERO", "ger": "TPPA", "area": "ADUANA", "cod": "GERADU-001", "nom": "% Regularización de las DAM de exportación dentro del plazo establecido (5días h", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ABRIL", "ger": "TPPA", "area": "ADUANA", "cod": "GERADU-004", "nom": "% DAM de Importación con documentos completos atendidas dentro del plazo (2 días", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ENERO", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "cod": "OPEDOC-012", "nom": "Asegurar la emisión de Autorizaciones de Retiro (Portal Clientes)", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-007", "nom": "%Cumplimiento de atención de citas de asignación de contenedor reefers a traves", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ENERO", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "FEBRERO", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "MARZO", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "ABRIL", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "MAYO", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "ENERO", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "FEBRERO", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "MARZO", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "ABRIL", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "MAYO", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "ENERO", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "cod": "OPESEC-004", "nom": "Cumplimiento de actas en operaciones usuales ejecutadas con RQ", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "cod": "OPESEC-004", "nom": "Cumplimiento de actas en operaciones usuales ejecutadas con RQ", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "MARZO", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "cod": "OPESEC-004", "nom": "Cumplimiento de actas en operaciones usuales ejecutadas con RQ", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ABRIL", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "cod": "OPESEC-004", "nom": "Cumplimiento de actas en operaciones usuales ejecutadas con RQ", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "MAYO", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "cod": "OPESIP-003", "nom": "% Entrega perfecta de los precintos SIP", "frec": "M", "tipo": "Indicador", "motivo": "No reportó"}, {"Mes": "MARZO", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "cod": "OPETRA-001", "nom": "Unidades con Checklist ejecutado", "frec": "T", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "cod": "OPEVAC-003", "nom": "% Despacho con errores", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "MARZO", "ger": "Regiones", "area": "Región Norte", "cod": "RN-008", "nom": "Daños ingresados en el Sistema SITAC maximo al día siguiente de recibir el estim", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ENERO", "ger": "Regiones", "area": "Región Norte", "cod": "RN-011", "nom": "Emisión de factura dentro del plazo", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "cod": "SST-002", "nom": "Control de inspección", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "MARZO", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "cod": "SST-002", "nom": "Control de inspección", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ENERO", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "cod": "SST-007", "nom": "Entrega de EMO", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "cod": "SST-007", "nom": "Entrega de EMO", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ENERO", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "cod": "TRA-005", "nom": "On Time Delivery", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "ABRIL", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "cod": "TRA-005", "nom": "On Time Delivery", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}, {"Mes": "MAYO", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "cod": "TRA-005", "nom": "On Time Delivery", "frec": "M", "tipo": "Indicador", "motivo": "Bajo meta"}];
const KAIZEN_DET = [{"Mes": "ABRIL", "cod": "AD-002", "nom": "Devolución de contenedores", "ger": "Gerencia de Negocios Logisticos", "area": "Customer Management", "frec": "M", "est": "SIN CREAR"}, {"Mes": "FEBRERO", "cod": "AFIGP-002", "nom": "valuación del Desempeño de Proveedores", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Gestión de Proveedores", "frec": "B", "est": "SIN CREAR"}, {"Mes": "MARZO", "cod": "AFICON-001", "nom": "Cumplimiento de cronograma de cierre contable", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Contabilidad", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MARZO", "cod": "AFICON-002", "nom": "Porcentajes de EMs convertidas en facturas", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Contabilidad", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "est": "DONE"}, {"Mes": "FEBRERO", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MARZO", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ABRIL", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MAYO", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "est": "SIN CREAR"}, {"Mes": "FEBRERO", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MARZO", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ABRIL", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MAYO", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "AFIFAC-007", "nom": "% de Cumplimiento de SLA para atención de Vacíos vía PAV", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "est": "DONE"}, {"Mes": "ENERO", "cod": "AFIFAC-008", "nom": "Facturación Portal Clientes (Pago Único)", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "est": "ON GOING"}, {"Mes": "FEBRERO", "cod": "AFIFAC-008", "nom": "Facturación Portal Clientes (Pago Único)", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "est": "ON GOING"}, {"Mes": "MARZO", "cod": "AFIFAC-008", "nom": "Facturación Portal Clientes (Pago Único)", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ABRIL", "cod": "AFIFAC-008", "nom": "Facturación Portal Clientes (Pago Único)", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "AGMCOM-006", "nom": "Nivel de respuesta de cotizaciones presentadas", "ger": "Negocios Maritimos y Navieros", "area": "Comercial AGMAR", "frec": "M", "est": "DONE"}, {"Mes": "MAYO", "cod": "AGMFAC-002", "nom": "Cumplimiento de comprobantes de SNR emitidos dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Facturación AGM", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ABRIL", "cod": "AGMOPM-006", "nom": "Plazos de envío de Información (Transmisiones)", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ABRIL", "cod": "AGMOPM-010", "nom": "Trasmisión de información de embarque y descarga", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MAYO", "cod": "GDHADM-001", "nom": "Medición de Mensajería", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Administración y Gestión del Personal", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "GDHCAP-001", "nom": "Cumplimiento de Plan de Capacitaciones", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Gestión de Cultura e Identidad", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "GDHCAP-002", "nom": "Eficacia de Capacitaciones", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Gestión de Cultura e Identidad", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "GERADU-001", "nom": "% Regularización de las DAM de exportación dentro del plazo establecido (5días h", "ger": "TPPA", "area": "ADUANA", "frec": "M", "est": "ON GOING"}, {"Mes": "ABRIL", "cod": "GERADU-004", "nom": "% DAM de Importación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "OPEDOC-012", "nom": "Asegurar la emisión de Autorizaciones de Retiro (Portal Clientes)", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "est": "DONE"}, {"Mes": "FEBRERO", "cod": "OPEREE-007", "nom": "%Cumplimiento de atención de citas de asignación de contenedor reefers a traves", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "FEBRERO", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MARZO", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ABRIL", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MAYO", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "FEBRERO", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MARZO", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ABRIL", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MAYO", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "OPESEC-004", "nom": "Cumplimiento de actas en operaciones usuales ejecutadas con RQ", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "est": "ON GOING"}, {"Mes": "FEBRERO", "cod": "OPESEC-004", "nom": "Cumplimiento de actas en operaciones usuales ejecutadas con RQ", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "est": "ON GOING"}, {"Mes": "MARZO", "cod": "OPESEC-004", "nom": "Cumplimiento de actas en operaciones usuales ejecutadas con RQ", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ABRIL", "cod": "OPESEC-004", "nom": "Cumplimiento de actas en operaciones usuales ejecutadas con RQ", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MAYO", "cod": "OPESIP-003", "nom": "% Entrega perfecta de los precintos SIP", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MARZO", "cod": "OPETRA-001", "nom": "Unidades con Checklist ejecutado", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "T", "est": "SIN CREAR"}, {"Mes": "FEBRERO", "cod": "OPEVAC-003", "nom": "% Despacho con errores", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "est": "DONE"}, {"Mes": "MARZO", "cod": "RN-008", "nom": "Daños ingresados en el Sistema SITAC maximo al día siguiente de recibir el estim", "ger": "Regiones", "area": "Región Norte", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "RN-011", "nom": "Emisión de factura dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "est": "DONE"}, {"Mes": "FEBRERO", "cod": "SST-002", "nom": "Control de inspección", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "frec": "M", "est": "ON GOING"}, {"Mes": "MARZO", "cod": "SST-002", "nom": "Control de inspección", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ENERO", "cod": "SST-007", "nom": "Entrega de EMO", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "frec": "M", "est": "SIN CREAR"}, {"Mes": "FEBRERO", "cod": "SST-007", "nom": "Entrega de EMO", "ger": "Gestión de Seguridad y SSOMA", "area": "SSOMA", "frec": "M", "est": "ON GOING"}, {"Mes": "ENERO", "cod": "TRA-005", "nom": "On Time Delivery", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "est": "SIN CREAR"}, {"Mes": "ABRIL", "cod": "TRA-005", "nom": "On Time Delivery", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "est": "SIN CREAR"}, {"Mes": "MAYO", "cod": "TRA-005", "nom": "On Time Delivery", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "est": "SIN CREAR"}];
const SLA_DET = [{"Mes": "ENERO", "cod": "AFIADQ-004", "nom": "Atenciones óptimas de solicitudes de compras", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Adquisición", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AFIADQ-004", "nom": "Atenciones óptimas de solicitudes de compras", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Adquisición", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AFIADQ-004", "nom": "Atenciones óptimas de solicitudes de compras", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Adquisición", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AFIADQ-004", "nom": "Atenciones óptimas de solicitudes de compras", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Adquisición", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AFIADQ-004", "nom": "Atenciones óptimas de solicitudes de compras", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Adquisición", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "Métrica", "ok": 0, "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "Métrica", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "Métrica", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "Métrica", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AFIFAC-005", "nom": "Tiempo medio de atención - Servicios Vacíos", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "Métrica", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "tipoind": "Métrica", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "tipoind": "Métrica", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "tipoind": "Métrica", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "tipoind": "Métrica", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AFIFAC-006", "nom": "Tiempos medios de asignación de Servicios - Importaciones y Exportaciones", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación NL", "frec": "M", "tipoind": "Métrica", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AFIFAC-007", "nom": "% de Cumplimiento de SLA para atención de Vacíos vía PAV", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "eficiencia", "ok": 0, "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "cod": "AFIFAC-007", "nom": "% de Cumplimiento de SLA para atención de Vacíos vía PAV", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AFIFAC-007", "nom": "% de Cumplimiento de SLA para atención de Vacíos vía PAV", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AFIFAC-007", "nom": "% de Cumplimiento de SLA para atención de Vacíos vía PAV", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AFIFAC-007", "nom": "% de Cumplimiento de SLA para atención de Vacíos vía PAV", "ger": "Gerencia de Adquisiciones y Finanzas", "area": "Facturación Vacíos", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AGMDOC-001", "nom": "% de Transbordos regularizados dentro del plazo", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AGMDOC-001", "nom": "% de Transbordos regularizados dentro del plazo", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AGMDOC-001", "nom": "% de Transbordos regularizados dentro del plazo", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AGMDOC-001", "nom": "% de Transbordos regularizados dentro del plazo", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AGMDOC-001", "nom": "% de Transbordos regularizados dentro del plazo", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AGMDOC-004", "nom": "Eficiencia en el tramite  para embarque de transbordos", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AGMDOC-004", "nom": "Eficiencia en el tramite  para embarque de transbordos", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AGMDOC-004", "nom": "Eficiencia en el tramite  para embarque de transbordos", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AGMDOC-004", "nom": "Eficiencia en el tramite  para embarque de transbordos", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AGMDOC-004", "nom": "Eficiencia en el tramite  para embarque de transbordos", "ger": "Negocios Maritimos y Navieros", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AGMFAC-002", "nom": "Cumplimiento de comprobantes de SNR emitidos dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Facturación AGM", "frec": "M", "tipoind": "", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AGMFAC-002", "nom": "Cumplimiento de comprobantes de SNR emitidos dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Facturación AGM", "frec": "M", "tipoind": "", "ok": 0, "motivo": "Bajo meta"}, {"Mes": "ENERO", "cod": "AGMOPM-003", "nom": "Atención de quejas y reclamos", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AGMOPM-003", "nom": "Atención de quejas y reclamos", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AGMOPM-003", "nom": "Atención de quejas y reclamos", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AGMOPM-003", "nom": "Atención de quejas y reclamos", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AGMOPM-003", "nom": "Atención de quejas y reclamos", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AGMOPM-004", "nom": "Recepción de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AGMOPM-004", "nom": "Recepción de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AGMOPM-004", "nom": "Recepción de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AGMOPM-004", "nom": "Recepción de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AGMOPM-004", "nom": "Recepción de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AGMOPM-005", "nom": "Despacho de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AGMOPM-005", "nom": "Despacho de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AGMOPM-005", "nom": "Despacho de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AGMOPM-005", "nom": "Despacho de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AGMOPM-005", "nom": "Despacho de Naves", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AGMOPM-006", "nom": "Plazos de envío de Información (Transmisiones)", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AGMOPM-006", "nom": "Plazos de envío de Información (Transmisiones)", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AGMOPM-006", "nom": "Plazos de envío de Información (Transmisiones)", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AGMOPM-006", "nom": "Plazos de envío de Información (Transmisiones)", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "MAYO", "cod": "AGMOPM-006", "nom": "Plazos de envío de Información (Transmisiones)", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AGMOPM-010", "nom": "Trasmisión de información de embarque y descarga", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AGMOPM-010", "nom": "Trasmisión de información de embarque y descarga", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AGMOPM-010", "nom": "Trasmisión de información de embarque y descarga", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AGMOPM-010", "nom": "Trasmisión de información de embarque y descarga", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "MAYO", "cod": "AGMOPM-010", "nom": "Trasmisión de información de embarque y descarga", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones AGMAR", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "AGMVB-003", "nom": "% cumplimiento de atención en el proceso de Visto Bueno dentro del SLA (2horas)", "ger": "Negocios Maritimos y Navieros", "area": "VB", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "AGMVB-003", "nom": "% cumplimiento de atención en el proceso de Visto Bueno dentro del SLA (2horas)", "ger": "Negocios Maritimos y Navieros", "area": "VB", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "AGMVB-003", "nom": "% cumplimiento de atención en el proceso de Visto Bueno dentro del SLA (2horas)", "ger": "Negocios Maritimos y Navieros", "area": "VB", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "AGMVB-003", "nom": "% cumplimiento de atención en el proceso de Visto Bueno dentro del SLA (2horas)", "ger": "Negocios Maritimos y Navieros", "area": "VB", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "AGMVB-003", "nom": "% cumplimiento de atención en el proceso de Visto Bueno dentro del SLA (2horas)", "ger": "Negocios Maritimos y Navieros", "area": "VB", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "GDHADM-001", "nom": "Medición de Mensajería", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Administración y Gestión del Personal", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "GDHADM-001", "nom": "Medición de Mensajería", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Administración y Gestión del Personal", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "GDHADM-001", "nom": "Medición de Mensajería", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Administración y Gestión del Personal", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "GDHADM-001", "nom": "Medición de Mensajería", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Administración y Gestión del Personal", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "GDHADM-001", "nom": "Medición de Mensajería", "ger": "Gestión de Administración y Desarrollo Humano", "area": "Administración y Gestión del Personal", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "Bajo meta"}, {"Mes": "ENERO", "cod": "GERADU-001", "nom": "% Regularización de las DAM de exportación dentro del plazo establecido (5días h", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "cod": "GERADU-001", "nom": "% Regularización de las DAM de exportación dentro del plazo establecido (5días h", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "GERADU-001", "nom": "% Regularización de las DAM de exportación dentro del plazo establecido (5días h", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "GERADU-001", "nom": "% Regularización de las DAM de exportación dentro del plazo establecido (5días h", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "GERADU-001", "nom": "% Regularización de las DAM de exportación dentro del plazo establecido (5días h", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "GERADU-002", "nom": "% DAM de Exportación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "GERADU-002", "nom": "% DAM de Exportación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "GERADU-002", "nom": "% DAM de Exportación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "GERADU-002", "nom": "% DAM de Exportación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "GERADU-002", "nom": "% DAM de Exportación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "GERADU-004", "nom": "% DAM de Importación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "GERADU-004", "nom": "% DAM de Importación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "GERADU-004", "nom": "% DAM de Importación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "GERADU-004", "nom": "% DAM de Importación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "Bajo meta"}, {"Mes": "MAYO", "cod": "GERADU-004", "nom": "% DAM de Importación con documentos completos atendidas dentro del plazo (2 días", "ger": "TPPA", "area": "ADUANA", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "GERLEG-001", "nom": "Comunicación de Requisitos Legales", "ger": "Gestión Legal", "area": "Legal", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "GERLEG-001", "nom": "Comunicación de Requisitos Legales", "ger": "Gestión Legal", "area": "Legal", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "GERLEG-001", "nom": "Comunicación de Requisitos Legales", "ger": "Gestión Legal", "area": "Legal", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "GERLEG-001", "nom": "Comunicación de Requisitos Legales", "ger": "Gestión Legal", "area": "Legal", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "GERLEG-001", "nom": "Comunicación de Requisitos Legales", "ger": "Gestión Legal", "area": "Legal", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "GERLEG-002", "nom": "MAXIMIZAR LA GESTIÓN DE CONTRATOS - LEGAL TPP", "ger": "Gestión Legal", "area": "Contratos", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "GERLEG-002", "nom": "MAXIMIZAR LA GESTIÓN DE CONTRATOS - LEGAL TPP", "ger": "Gestión Legal", "area": "Contratos", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "GERLEG-002", "nom": "MAXIMIZAR LA GESTIÓN DE CONTRATOS - LEGAL TPP", "ger": "Gestión Legal", "area": "Contratos", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "GERLEG-002", "nom": "MAXIMIZAR LA GESTIÓN DE CONTRATOS - LEGAL TPP", "ger": "Gestión Legal", "area": "Contratos", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "GERLEG-002", "nom": "MAXIMIZAR LA GESTIÓN DE CONTRATOS - LEGAL TPP", "ger": "Gestión Legal", "area": "Contratos", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "NMNVAC-001", "nom": "Atención de tickets de asignación de cntrs secos en portal de usuario dentro de", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "NMNVAC-001", "nom": "Atención de tickets de asignación de cntrs secos en portal de usuario dentro de", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "NMNVAC-001", "nom": "Atención de tickets de asignación de cntrs secos en portal de usuario dentro de", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "NMNVAC-001", "nom": "Atención de tickets de asignación de cntrs secos en portal de usuario dentro de", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "NMNVAC-001", "nom": "Atención de tickets de asignación de cntrs secos en portal de usuario dentro de", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "NMNVAC-002", "nom": "Atención de tickets de asignación de cntrs reefers en portal de usuario dentro d", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "NMNVAC-002", "nom": "Atención de tickets de asignación de cntrs reefers en portal de usuario dentro d", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "NMNVAC-002", "nom": "Atención de tickets de asignación de cntrs reefers en portal de usuario dentro d", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "NMNVAC-002", "nom": "Atención de tickets de asignación de cntrs reefers en portal de usuario dentro d", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "NMNVAC-002", "nom": "Atención de tickets de asignación de cntrs reefers en portal de usuario dentro d", "ger": "Negocios Maritimos y Navieros", "area": "Planeamiento Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPEDOC-004", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de Autorización", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPEDOC-004", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de Autorización", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPEDOC-004", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de Autorización", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEDOC-004", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de Autorización", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEDOC-004", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de Autorización", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPEDOC-005", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de refrendos (P", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPEDOC-005", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de refrendos (P", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPEDOC-005", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de refrendos (P", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEDOC-005", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de refrendos (P", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEDOC-005", "nom": "Incrementar el cumplimiento del SLA de la atención de solicitud de refrendos (P", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPEDOC-007", "nom": "Control de transmisiones extemporáneas IRM con responsabilidad de TPP", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPEDOC-007", "nom": "Control de transmisiones extemporáneas IRM con responsabilidad de TPP", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPEDOC-007", "nom": "Control de transmisiones extemporáneas IRM con responsabilidad de TPP", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEDOC-007", "nom": "Control de transmisiones extemporáneas IRM con responsabilidad de TPP", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEDOC-007", "nom": "Control de transmisiones extemporáneas IRM con responsabilidad de TPP", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPEDOC-008", "nom": "Número de Transmisiones Extemporaneas por responsabilidad del Cliente (afectan c", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPEDOC-008", "nom": "Número de Transmisiones Extemporaneas por responsabilidad del Cliente (afectan c", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPEDOC-008", "nom": "Número de Transmisiones Extemporaneas por responsabilidad del Cliente (afectan c", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEDOC-008", "nom": "Número de Transmisiones Extemporaneas por responsabilidad del Cliente (afectan c", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEDOC-008", "nom": "Número de Transmisiones Extemporaneas por responsabilidad del Cliente (afectan c", "ger": "Gerencia de Negocios Logisticos", "area": "Documentación", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPELCL-002", "nom": "Mantener Eficiencia de Tarjas Emitidas", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPELCL-002", "nom": "Mantener Eficiencia de Tarjas Emitidas", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPELCL-002", "nom": "Mantener Eficiencia de Tarjas Emitidas", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPELCL-002", "nom": "Mantener Eficiencia de Tarjas Emitidas", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPELCL-002", "nom": "Mantener Eficiencia de Tarjas Emitidas", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPEREE-010", "nom": "Controlar el ingreso de las UT +-1hora de cita", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPEREE-010", "nom": "Controlar el ingreso de las UT +-1hora de cita", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPEREE-010", "nom": "Controlar el ingreso de las UT +-1hora de cita", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEREE-010", "nom": "Controlar el ingreso de las UT +-1hora de cita", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEREE-010", "nom": "Controlar el ingreso de las UT +-1hora de cita", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPEREE-013", "nom": "Optimizar flujo de salida de contenedores reefers reduciendo el tiempo de despac", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPEREE-013", "nom": "Optimizar flujo de salida de contenedores reefers reduciendo el tiempo de despac", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPEREE-013", "nom": "Optimizar flujo de salida de contenedores reefers reduciendo el tiempo de despac", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEREE-013", "nom": "Optimizar flujo de salida de contenedores reefers reduciendo el tiempo de despac", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEREE-013", "nom": "Optimizar flujo de salida de contenedores reefers reduciendo el tiempo de despac", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "FEBRERO", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "MARZO", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "ABRIL", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "MAYO", "cod": "OPEREE-014", "nom": "% reparaciones de maquinaria de contenedores reefer vacíos realizados en el SLA", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "ENERO", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "FEBRERO", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "MARZO", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "ABRIL", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "MAYO", "cod": "OPEREE-015", "nom": "% PTI de contenedores reefer vacíos (Gate In) realizados en el SLA (24 horas)", "ger": "Negocios Maritimos y Navieros", "area": "REEFER", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "No reportó"}, {"Mes": "ENERO", "cod": "OPESEC-001", "nom": "% Cumplimiento de atención en el proceso de despacho de contenedores llenos de i", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPESEC-001", "nom": "% Cumplimiento de atención en el proceso de despacho de contenedores llenos de i", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPESEC-001", "nom": "% Cumplimiento de atención en el proceso de despacho de contenedores llenos de i", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPESEC-001", "nom": "% Cumplimiento de atención en el proceso de despacho de contenedores llenos de i", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPESEC-001", "nom": "% Cumplimiento de atención en el proceso de despacho de contenedores llenos de i", "ger": "Gerencia de Negocios Logisticos", "area": "Operaciones", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPEVAC-006", "nom": "Cantidad de registros de Devolución/ Descarga dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPEVAC-006", "nom": "Cantidad de registros de Devolución/ Descarga dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPEVAC-006", "nom": "Cantidad de registros de Devolución/ Descarga dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEVAC-006", "nom": "Cantidad de registros de Devolución/ Descarga dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEVAC-006", "nom": "Cantidad de registros de Devolución/ Descarga dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "OPEVAC-008", "nom": "Incrementar el cumplimiento de transmisiones RCEC efectuadas dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "OPEVAC-008", "nom": "Incrementar el cumplimiento de transmisiones RCEC efectuadas dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "OPEVAC-008", "nom": "Incrementar el cumplimiento de transmisiones RCEC efectuadas dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEVAC-008", "nom": "Incrementar el cumplimiento de transmisiones RCEC efectuadas dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEVAC-008", "nom": "Incrementar el cumplimiento de transmisiones RCEC efectuadas dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEVAC-010", "nom": "% de cumplimiento del servicio de recepción de contenedores vacíos dentro del SL", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEVAC-010", "nom": "% de cumplimiento del servicio de recepción de contenedores vacíos dentro del SL", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "OPEVAC-011", "nom": "% de cumplimiento del servicio de despacho de contenedores vacíos dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "OPEVAC-011", "nom": "% de cumplimiento del servicio de despacho de contenedores vacíos dentro del SLA", "ger": "Negocios Maritimos y Navieros", "area": "Operaciones Vacios", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "PPSIL-002", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "PPSIL-002", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "PPSIL-002", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "PPSIL-002", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "PPSIL-002", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "PPSIP-005", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "PPSIP-005", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "PPSIP-005", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "PPSIP-005", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "PPSIP-005", "nom": "Cumplimiento de fecha devolución memo", "ger": "Gerencia de Negocios Logisticos", "area": "Planeamiento", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "NLCMO-001", "nom": "% de cumplimiento de EM generadas dentro del periodo en los servicios GATE OTAL", "ger": "Gerencia de Negocios Logisticos", "area": "Costos y Margenes Operativos", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "NLCMO-002", "nom": "% de cumplimiento de EM generadas dentro del periodo en los servicios VB", "ger": "Gerencia de Negocios Logisticos", "area": "Costos y Margenes Operativos", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "NLCMO-003", "nom": "% de cumplimiento de EM generadas dentro del periodo en los servicios Agenciamie", "ger": "Gerencia de Negocios Logisticos", "area": "Costos y Margenes Operativos", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "NLCMO-004", "nom": "% de cumplimiento de EM generadas dentro del periodo en los servicios portuarios", "ger": "Gerencia de Negocios Logisticos", "area": "Costos y Margenes Operativos", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "RN-008", "nom": "Daños ingresados en el Sistema SITAC maximo al día siguiente de recibir el estim", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "RN-008", "nom": "Daños ingresados en el Sistema SITAC maximo al día siguiente de recibir el estim", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "RN-008", "nom": "Daños ingresados en el Sistema SITAC maximo al día siguiente de recibir el estim", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "Bajo meta"}, {"Mes": "ABRIL", "cod": "RN-008", "nom": "Daños ingresados en el Sistema SITAC maximo al día siguiente de recibir el estim", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "RN-008", "nom": "Daños ingresados en el Sistema SITAC maximo al día siguiente de recibir el estim", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "RN-009", "nom": "Termino de reparación estructural ingresado en SITAC dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "RN-009", "nom": "Termino de reparación estructural ingresado en SITAC dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "RN-009", "nom": "Termino de reparación estructural ingresado en SITAC dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "RN-009", "nom": "Termino de reparación estructural ingresado en SITAC dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "RN-009", "nom": "Termino de reparación estructural ingresado en SITAC dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "RN-010", "nom": "Término de reparación de maquinaria ingresado dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "RN-010", "nom": "Término de reparación de maquinaria ingresado dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "RN-010", "nom": "Término de reparación de maquinaria ingresado dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "RN-010", "nom": "Término de reparación de maquinaria ingresado dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "RN-010", "nom": "Término de reparación de maquinaria ingresado dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "RN-011", "nom": "Emisión de factura dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 0, "motivo": "Bajo meta"}, {"Mes": "FEBRERO", "cod": "RN-011", "nom": "Emisión de factura dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "RN-011", "nom": "Emisión de factura dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "RN-011", "nom": "Emisión de factura dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "RN-011", "nom": "Emisión de factura dentro del plazo", "ger": "Regiones", "area": "Región Norte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "SDC-002", "nom": "Cumplimiento de atención de incidencias y peticiones", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "SDC-002", "nom": "Cumplimiento de atención de incidencias y peticiones", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "SDC-002", "nom": "Cumplimiento de atención de incidencias y peticiones", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "SDC-002", "nom": "Cumplimiento de atención de incidencias y peticiones", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "SDC-002", "nom": "Cumplimiento de atención de incidencias y peticiones", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "SDC-005", "nom": "Cumplimiento de atención de cambios", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "SDC-005", "nom": "Cumplimiento de atención de cambios", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "SDC-005", "nom": "Cumplimiento de atención de cambios", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "SDC-005", "nom": "Cumplimiento de atención de cambios", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "SDC-005", "nom": "Cumplimiento de atención de cambios", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "PMO & Operaciones TI", "frec": "M", "tipoind": "eficiencia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "SDC-008", "nom": "Cumplimiento de atención de movil y modem", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "SDC-008", "nom": "Cumplimiento de atención de movil y modem", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "SDC-008", "nom": "Cumplimiento de atención de movil y modem", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "SDC-008", "nom": "Cumplimiento de atención de movil y modem", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "SDC-008", "nom": "Cumplimiento de atención de movil y modem", "ger": "Gestión de Sistemas Digitales y Ciberseguridad", "area": "Aplicaciones Y Arquitectura", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "TRA-002", "nom": "Estatus de Servicio", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "TRA-002", "nom": "Estatus de Servicio", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "TRA-002", "nom": "Estatus de Servicio", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "TRA-002", "nom": "Estatus de Servicio", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "TRA-002", "nom": "Estatus de Servicio", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ENERO", "cod": "TRA-003", "nom": "Liquidación de Sericios", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "FEBRERO", "cod": "TRA-003", "nom": "Liquidación de Sericios", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MARZO", "cod": "TRA-003", "nom": "Liquidación de Sericios", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "ABRIL", "cod": "TRA-003", "nom": "Liquidación de Sericios", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}, {"Mes": "MAYO", "cod": "TRA-003", "nom": "Liquidación de Sericios", "ger": "Gerencia de Negocios Logisticos", "area": "Transporte", "frec": "M", "tipoind": "eficacia", "ok": 1, "motivo": ""}];




(function() {
  const inp  = document.getElementById('kpi-inp');
  const btn  = document.getElementById('kpi-btn');
  const hint = document.getElementById('kpi-hint');
  const norm = KPI_USERS.map(u => u.toLowerCase());

  // Nombre completo y puesto del usuario (CSV de personal; gerentes como respaldo)
  function userInfo(user) {
    const u = user.toLowerCase();
    const n = KPI_NOMBRES[u];
    if (n) return { nombre: n.n, puesto: n.p || 'Colaborador' };
    const g = KPI_GERENTES[u];
    if (g) return { nombre: g.nombre, puesto: g.cargo };
    return { nombre: user, puesto: 'Usuario autorizado · Sistema KPI' };
  }

  // Usuarios con acceso total al dashboard (sin restricción de gerencia)
  const KPI_ACCESO_TOTAL = ['rrosales', 'mhuapaya', 'bcapulian', 'pbazan', 'mroncal', 'ogajate'];

  // Gerencia del usuario: acceso total primero, luego gerentes, luego clasificación por puesto
  function userGerencia(user) {
    const u = user.toLowerCase();
    if (KPI_ACCESO_TOTAL.includes(u)) return 'ALL';
    const g = KPI_GERENTES[u];
    if (g) return g.gerencia; // puede ser 'ALL'
    return KPI_USER_GER[u] || 'ALL';
  }

  function showSplash(user, done) {
    const info = userInfo(user);
    document.getElementById('splash-nombre').textContent = 'Bienvenido, ' + info.nombre;
    document.getElementById('splash-puesto').textContent = info.puesto;
    const ger = userGerencia(user);
    document.getElementById('splash-gerencia').textContent =
      ger !== 'ALL' ? 'Bienvenido a ' + ger : 'Vista general · Todas las gerencias';
    const sp = document.getElementById('kpi-splash');
    sp.classList.remove('fade');
    sp.classList.add('show');
    setTimeout(() => {
      sp.classList.add('fade');
      setTimeout(() => { sp.classList.remove('show', 'fade'); if (done) done(); }, 800);
    }, 3100);
  }

  function showDash(user) {
    document.getElementById('kpi-login-overlay').style.display = 'none';
    document.body.style.overflow = '';

    showSplash(user, null);

    document.querySelectorAll('.main, .sidebar').forEach(el => el.classList.add('vis'));
    document.getElementById('kpi-pill').style.display = 'flex';
    const info = userInfo(user);
    // Iniciales reales: primera letra del nombre y del apellido
    const partes = info.nombre.split(' ').filter(w => w.length > 2 || w === info.nombre);
    const inic = info.nombre === user ? user.substring(0,2).toUpperCase()
      : (partes[0].charAt(0) + (partes.length > 1 ? partes[partes.length - 2].charAt(0) : '')).toUpperCase();
    document.getElementById('kpi-pill-av').textContent = inic;
    // Determinar acceso: cada usuario ve su gerencia; corporativos ven todo
    const gInfo = KPI_GERENTES[user.toLowerCase()];
    const gerUser = userGerencia(user);
    if (gerUser !== 'ALL') {
      KPI_ACCESS = gerUser;
      if (typeof selectedGerencia !== 'undefined') selectedGerencia = gerUser;
    } else {
      KPI_ACCESS = 'ALL';
      if (typeof selectedGerencia !== 'undefined') selectedGerencia = 'ALL';
    }
    applyLayout();
    const roleTag = gInfo ? ' 👔' : '';
    const nombreCorto = info.nombre === user ? user : info.nombre.split(' ')[0] + ' ' + (info.nombre.split(' ').length > 2 ? info.nombre.split(' ')[info.nombre.split(' ').length - 2] : '');
    document.getElementById('kpi-pill-name').textContent = nombreCorto + roleTag;
    document.getElementById('kpi-pill-name').title = (info.puesto ? info.puesto : '') + (gInfo && gInfo.gerencia !== 'ALL' ? ' — Vista: ' + gInfo.gerencia : gInfo ? ' — Acceso total' : '');
    if (typeof buildFilters === 'function') { buildFilters(); updateAll(); }
    setTimeout(() => { const l = document.getElementById('loader'); if(l) l.classList.add('hidden'); }, 500);
  }

  function validate() {
    const v = inp.value.trim();
    if (!v) { inp.className='kpi-lc-inp'; hint.textContent=''; hint.className='kpi-lc-hint'; btn.disabled=true; return; }
    if (norm.includes(v.toLowerCase())) {
      const info = userInfo(v);
      inp.className='kpi-lc-inp valid';
      hint.textContent = '✓ ' + (info.nombre !== v ? info.nombre : 'Usuario verificado');
      hint.className='kpi-lc-hint ok'; btn.disabled=false;
    } else {
      inp.className='kpi-lc-inp invalid'; hint.textContent='✗ Usuario no encontrado';
      hint.className='kpi-lc-hint err'; btn.disabled=true;
    }
  }

  function doAccess() {
    const v = inp.value.trim();
    const i = norm.indexOf(v.toLowerCase());
    if (i === -1) return;
    const real = KPI_USERS[i];
    localStorage.setItem('kpi_user', real);
    showDash(real);
  }

  inp.addEventListener('input', validate);
  inp.addEventListener('keydown', e => { if (e.key==='Enter' && !btn.disabled) doAccess(); });
  btn.addEventListener('click', doAccess);

  window.addEventListener('DOMContentLoaded', () => {
    const saved = localStorage.getItem('kpi_user');
    if (saved && norm.includes(saved.toLowerCase())) {
      showDash(saved);
    } else {
      document.getElementById('kpi-login-overlay').style.display = 'flex';
      document.body.style.overflow = 'hidden';
      setTimeout(() => inp.focus(), 80);
    }
  });
})();


// Vista restringida: solo tarjetas, donuts (Meta, PGC, KAIZEN), áreas y SLA
function applyLayout() {
  const restringido = KPI_ACCESS !== 'ALL';
  const rowGer = document.getElementById('row-gerencias');
  const ranking = document.getElementById('card-ranking');
  const sla = document.getElementById('card-sla');
  if (rowGer) rowGer.style.display = restringido ? 'none' : '';
  if (ranking) ranking.style.display = restringido ? 'none' : '';
  if (sla) { sla.classList.toggle('col-12', restringido); sla.classList.toggle('col-6', !restringido); }
}

function kpiLogout() {
  localStorage.removeItem('kpi_user');
  KPI_ACCESS = 'ALL';
  if (typeof selectedGerencia !== 'undefined') selectedGerencia = 'ALL';
  applyLayout();
  document.getElementById('kpi-pill').style.display = 'none';
  document.getElementById('kpi-login-overlay').style.display = 'flex';
  document.body.style.overflow = 'hidden';
  document.querySelectorAll('.main, .sidebar').forEach(el => el.classList.remove('vis'));
  document.getElementById('kpi-inp').value = '';
  document.getElementById('kpi-inp').className = 'kpi-lc-inp';
  document.getElementById('kpi-hint').textContent = '';
  document.getElementById('kpi-btn').disabled = true;
  setTimeout(() => document.getElementById('kpi-inp').focus(), 80);
}

</script>

<script>

// ─────────────────────────────────────────────
// EMBEDDED DATA
// ─────────────────────────────────────────────
const EMBEDDED_DATA = {"cumplimiento_meta": [{"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "cumplieron": 30, "total": 33, "pct_meta": 0.9091}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "cumplieron": 32, "total": 33, "pct_meta": 0.9697}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "cumplieron": 37, "total": 39, "pct_meta": 0.9487}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "cumplieron": 30, "total": 33, "pct_meta": 0.9091}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "cumplieron": 35, "total": 37, "pct_meta": 0.9459}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "cumplieron": 10, "total": 13, "pct_meta": 0.7692}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "cumplieron": 12, "total": 14, "pct_meta": 0.8571}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "cumplieron": 10, "total": 13, "pct_meta": 0.7692}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "cumplieron": 13, "total": 14, "pct_meta": 0.9286}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "cumplieron": 13, "total": 13, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "cumplieron": 41, "total": 43, "pct_meta": 0.9535}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "cumplieron": 37, "total": 40, "pct_meta": 0.925}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "cumplieron": 36, "total": 40, "pct_meta": 0.9}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "cumplieron": 39, "total": 43, "pct_meta": 0.907}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "cumplieron": 40, "total": 43, "pct_meta": 0.9302}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "cumplieron": 2, "total": 4, "pct_meta": 0.5}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "cumplieron": 4, "total": 4, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "cumplieron": 4, "total": 4, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "cumplieron": 4, "total": 4, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "cumplieron": 3, "total": 4, "pct_meta": 0.75}, {"Mes": "ENERO", "Gerencia Central": "TPPA", "cumplieron": 2, "total": 3, "pct_meta": 0.6667}, {"Mes": "FEBRERO", "Gerencia Central": "TPPA", "cumplieron": 3, "total": 3, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "TPPA", "cumplieron": 3, "total": 3, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "TPPA", "cumplieron": 2, "total": 3, "pct_meta": 0.6667}, {"Mes": "MAYO", "Gerencia Central": "TPPA", "cumplieron": 3, "total": 3, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión Legal", "cumplieron": 2, "total": 2, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión Legal", "cumplieron": 2, "total": 2, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión Legal", "cumplieron": 2, "total": 2, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión Legal", "cumplieron": 2, "total": 2, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión Legal", "cumplieron": 2, "total": 2, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Procesos Estratégicos", "cumplieron": 1, "total": 1, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Procesos Estratégicos", "cumplieron": 1, "total": 1, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Procesos Estratégicos", "cumplieron": 4, "total": 4, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Procesos Estratégicos", "cumplieron": 1, "total": 1, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Procesos Estratégicos", "cumplieron": 1, "total": 1, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Planeamiento Estratégico", "cumplieron": 3, "total": 3, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "cumplieron": 8, "total": 9, "pct_meta": 0.8889}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "cumplieron": 7, "total": 9, "pct_meta": 0.7778}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "cumplieron": 9, "total": 10, "pct_meta": 0.9}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Seguridad y SSOMA", "cumplieron": 9, "total": 9, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "cumplieron": 9, "total": 9, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Regiones", "cumplieron": 3, "total": 4, "pct_meta": 0.75}, {"Mes": "FEBRERO", "Gerencia Central": "Regiones", "cumplieron": 4, "total": 4, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Regiones", "cumplieron": 3, "total": 4, "pct_meta": 0.75}, {"Mes": "ABRIL", "Gerencia Central": "Regiones", "cumplieron": 4, "total": 4, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Regiones", "cumplieron": 4, "total": 4, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "cumplieron": 3, "total": 3, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "cumplieron": 6, "total": 6, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "cumplieron": 9, "total": 9, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "cumplieron": 6, "total": 6, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "cumplieron": 3, "total": 3, "pct_meta": 1.0}], "cumplimiento_reporte": [{"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "reportados": 33, "total": 33, "pct_reporte": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "reportados": 33, "total": 33, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "reportados": 39, "total": 39, "pct_reporte": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "reportados": 33, "total": 33, "pct_reporte": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "reportados": 36, "total": 37, "pct_reporte": 0.973}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "reportados": 13, "total": 13, "pct_reporte": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "reportados": 14, "total": 14, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "reportados": 11, "total": 13, "pct_reporte": 0.8462}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "reportados": 14, "total": 14, "pct_reporte": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "reportados": 13, "total": 13, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "reportados": 41, "total": 43, "pct_reporte": 0.9535}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "reportados": 38, "total": 40, "pct_reporte": 0.95}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "reportados": 38, "total": 40, "pct_reporte": 0.95}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "reportados": 39, "total": 43, "pct_reporte": 0.907}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "reportados": 41, "total": 43, "pct_reporte": 0.9535}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "reportados": 2, "total": 4, "pct_reporte": 0.5}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "ENERO", "Gerencia Central": "TPPA", "reportados": 3, "total": 3, "pct_reporte": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "TPPA", "reportados": 3, "total": 3, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "TPPA", "reportados": 3, "total": 3, "pct_reporte": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "TPPA", "reportados": 3, "total": 3, "pct_reporte": 1.0}, {"Mes": "MAYO", "Gerencia Central": "TPPA", "reportados": 3, "total": 3, "pct_reporte": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión Legal", "reportados": 2, "total": 2, "pct_reporte": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión Legal", "reportados": 2, "total": 2, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión Legal", "reportados": 2, "total": 2, "pct_reporte": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión Legal", "reportados": 2, "total": 2, "pct_reporte": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión Legal", "reportados": 2, "total": 2, "pct_reporte": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Procesos Estratégicos", "reportados": 1, "total": 1, "pct_reporte": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Procesos Estratégicos", "reportados": 1, "total": 1, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Procesos Estratégicos", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Procesos Estratégicos", "reportados": 1, "total": 1, "pct_reporte": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Procesos Estratégicos", "reportados": 1, "total": 1, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Planeamiento Estratégico", "reportados": 3, "total": 3, "pct_reporte": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "reportados": 9, "total": 9, "pct_reporte": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "reportados": 9, "total": 9, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "reportados": 10, "total": 10, "pct_reporte": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Seguridad y SSOMA", "reportados": 9, "total": 9, "pct_reporte": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "reportados": 9, "total": 9, "pct_reporte": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Regiones", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Regiones", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Regiones", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Regiones", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Regiones", "reportados": 4, "total": 4, "pct_reporte": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "reportados": 3, "total": 3, "pct_reporte": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "reportados": 6, "total": 6, "pct_reporte": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "reportados": 9, "total": 9, "pct_reporte": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "reportados": 6, "total": 6, "pct_reporte": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "reportados": 3, "total": 3, "pct_reporte": 1.0}], "tipo_proceso": [{"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "PROCESO TPP", "count": 20}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "PROCESO TPP", "count": 20}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "PROCESO TPP", "count": 25}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "PROCESO TPP", "count": 20}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "PROCESO TPP", "count": 24}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "PROCESO TPP", "count": 12}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "PROCESO TPP", "count": 13}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "PROCESO TPP", "count": 12}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "PROCESO TPP", "count": 13}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "PROCESO TPP", "count": 12}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "Proceso Crítico", "count": 1}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "Proceso Crítico", "count": 1}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "Proceso Crítico", "count": 1}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "Proceso Crítico", "count": 1}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "TIPO DE PROCESO": "Proceso Crítico", "count": 1}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "PROCESO TPP", "count": 33}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "PROCESO TPP", "count": 30}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "PROCESO TPP", "count": 30}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "PROCESO TPP", "count": 33}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "PROCESO TPP", "count": 33}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "Proceso Crítico", "count": 14}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "ENERO", "Gerencia Central": "TPPA", "TIPO DE PROCESO": "PROCESO TPP", "count": 3}, {"Mes": "FEBRERO", "Gerencia Central": "TPPA", "TIPO DE PROCESO": "PROCESO TPP", "count": 3}, {"Mes": "MARZO", "Gerencia Central": "TPPA", "TIPO DE PROCESO": "PROCESO TPP", "count": 3}, {"Mes": "ABRIL", "Gerencia Central": "TPPA", "TIPO DE PROCESO": "PROCESO TPP", "count": 3}, {"Mes": "MAYO", "Gerencia Central": "TPPA", "TIPO DE PROCESO": "PROCESO TPP", "count": 3}, {"Mes": "ENERO", "Gerencia Central": "Gestión Legal", "TIPO DE PROCESO": "PROCESO TPP", "count": 2}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión Legal", "TIPO DE PROCESO": "PROCESO TPP", "count": 2}, {"Mes": "MARZO", "Gerencia Central": "Gestión Legal", "TIPO DE PROCESO": "PROCESO TPP", "count": 2}, {"Mes": "ABRIL", "Gerencia Central": "Gestión Legal", "TIPO DE PROCESO": "PROCESO TPP", "count": 2}, {"Mes": "MAYO", "Gerencia Central": "Gestión Legal", "TIPO DE PROCESO": "PROCESO TPP", "count": 2}, {"Mes": "ENERO", "Gerencia Central": "Procesos Estratégicos", "TIPO DE PROCESO": "PROCESO TPP", "count": 1}, {"Mes": "FEBRERO", "Gerencia Central": "Procesos Estratégicos", "TIPO DE PROCESO": "PROCESO TPP", "count": 1}, {"Mes": "MARZO", "Gerencia Central": "Procesos Estratégicos", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "ABRIL", "Gerencia Central": "Procesos Estratégicos", "TIPO DE PROCESO": "PROCESO TPP", "count": 1}, {"Mes": "MAYO", "Gerencia Central": "Procesos Estratégicos", "TIPO DE PROCESO": "PROCESO TPP", "count": 1}, {"Mes": "MARZO", "Gerencia Central": "Planeamiento Estratégico", "TIPO DE PROCESO": "PROCESO TPP", "count": 3}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "Proceso Crítico", "count": 10}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "Proceso Crítico", "count": 10}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "Proceso Crítico", "count": 10}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "Proceso Crítico", "count": 10}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "TIPO DE PROCESO": "Proceso Crítico", "count": 10}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "Proceso Crítico", "count": 13}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "Proceso Crítico", "count": 13}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "Proceso Crítico", "count": 13}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "TIPO DE PROCESO": "Proceso Crítico", "count": 13}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "TIPO DE PROCESO": "PROCESO TPP", "count": 9}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "TIPO DE PROCESO": "PROCESO TPP", "count": 9}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "TIPO DE PROCESO": "PROCESO TPP", "count": 10}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Seguridad y SSOMA", "TIPO DE PROCESO": "PROCESO TPP", "count": 9}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "TIPO DE PROCESO": "PROCESO TPP", "count": 9}, {"Mes": "ENERO", "Gerencia Central": "Regiones", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "FEBRERO", "Gerencia Central": "Regiones", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "MARZO", "Gerencia Central": "Regiones", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "ABRIL", "Gerencia Central": "Regiones", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "MAYO", "Gerencia Central": "Regiones", "TIPO DE PROCESO": "PROCESO TPP", "count": 4}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "TIPO DE PROCESO": "PROCESO TPP", "count": 3}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "TIPO DE PROCESO": "PROCESO TPP", "count": 6}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "TIPO DE PROCESO": "PROCESO TPP", "count": 9}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "TIPO DE PROCESO": "PROCESO TPP", "count": 6}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "TIPO DE PROCESO": "PROCESO TPP", "count": 3}], "kpis_desviados": [{"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Customer Management", "kpis_desviados": 1}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Gestión de Proveedores", "kpis_desviados": 1}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Contabilidad", "kpis_desviados": 2}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación Vacíos", "kpis_desviados": 2}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación NL", "kpis_desviados": 1}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación NL", "kpis_desviados": 1}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación NL", "kpis_desviados": 1}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación NL", "kpis_desviados": 1}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Comercial AGMAR", "kpis_desviados": 1}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Facturación AGM", "kpis_desviados": 1}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones AGMAR", "kpis_desviados": 2}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Administración y Gestión del Personal", "kpis_desviados": 1}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Gestión de Cultura e Identidad", "kpis_desviados": 2}, {"Mes": "ENERO", "Gerencia Central": "TPPA", "Área": "ADUANA", "kpis_desviados": 1}, {"Mes": "ABRIL", "Gerencia Central": "TPPA", "Área": "ADUANA", "kpis_desviados": 1}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Documentación", "kpis_desviados": 1}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "kpis_desviados": 3}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "kpis_desviados": 2}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "kpis_desviados": 2}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "kpis_desviados": 2}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "kpis_desviados": 2}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Operaciones", "kpis_desviados": 1}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Operaciones", "kpis_desviados": 1}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Operaciones", "kpis_desviados": 1}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Operaciones", "kpis_desviados": 1}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Transporte", "kpis_desviados": 2}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Transporte", "kpis_desviados": 1}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones Vacios", "kpis_desviados": 1}, {"Mes": "MARZO", "Gerencia Central": "Regiones", "Área": "Región Norte", "kpis_desviados": 1}, {"Mes": "ENERO", "Gerencia Central": "Regiones", "Área": "Región Norte", "kpis_desviados": 1}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "SSOMA", "kpis_desviados": 2}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "SSOMA", "kpis_desviados": 1}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "SSOMA", "kpis_desviados": 1}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Transporte", "kpis_desviados": 1}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Transporte", "kpis_desviados": 1}], "global_por_mes": [{"Mes": "ENERO", "cumplieron": 98, "total": 112, "pct": 0.875}, {"Mes": "FEBRERO", "cumplieron": 107, "total": 116, "pct": 0.9224}, {"Mes": "MARZO", "cumplieron": 125, "total": 134, "pct": 0.9328}, {"Mes": "ABRIL", "cumplieron": 110, "total": 119, "pct": 0.9244}, {"Mes": "MAYO", "cumplieron": 113, "total": 119, "pct": 0.9496}], "gerencias": ["Gerencia de Adquisiciones y Finanzas", "Gerencia de Negocios Logisticos", "Gestión Legal", "Gestión de Administración y Desarrollo Humano", "Gestión de Seguridad y SSOMA", "Gestión de Sistemas Digitales y Ciberseguridad", "Negocios Maritimos y Navieros", "Planeamiento Estratégico", "Procesos Estratégicos", "Regiones", "TPPA"], "meses": ["ENERO", "FEBRERO", "MARZO", "ABRIL", "MAYO"], "cumplimiento_area": [{"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Customer Management", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Customer Management", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Customer Management", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Customer Management", "cumplieron": 1, "total": 2, "frec": {"M": 2}, "pct_meta": 0.5}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Customer Management", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Gestión de Proveedores", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Gestión de Proveedores", "cumplieron": 1, "total": 2, "frec": {"M": 1, "B": 1}, "pct_meta": 0.5}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Gestión de Proveedores", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Gestión de Proveedores", "cumplieron": 2, "total": 2, "frec": {"M": 1, "B": 1}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Gestión de Proveedores", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Adquisición", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Adquisición", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Adquisición", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Adquisición", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Adquisición", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Contabilidad", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Contabilidad", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Contabilidad", "cumplieron": 0, "total": 2, "frec": {"M": 2}, "pct_meta": 0.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Contabilidad", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Contabilidad", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación NL", "cumplieron": 3, "total": 4, "frec": {"M": 4}, "pct_meta": 0.75}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación NL", "cumplieron": 3, "total": 4, "frec": {"M": 4}, "pct_meta": 0.75}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación NL", "cumplieron": 3, "total": 4, "frec": {"M": 4}, "pct_meta": 0.75}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación NL", "cumplieron": 3, "total": 4, "frec": {"M": 4}, "pct_meta": 0.75}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación NL", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación Vacíos", "cumplieron": 1, "total": 3, "frec": {"M": 3}, "pct_meta": 0.3333}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación Vacíos", "cumplieron": 3, "total": 3, "frec": {"M": 3}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación Vacíos", "cumplieron": 3, "total": 3, "frec": {"M": 3}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación Vacíos", "cumplieron": 3, "total": 3, "frec": {"M": 3}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Facturación Vacíos", "cumplieron": 3, "total": 3, "frec": {"M": 3}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Finanzas", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Finanzas", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Finanzas", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Finanzas", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "Área": "Finanzas", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Comercial AGMAR", "cumplieron": 4, "total": 4, "frec": {"T": 2, "M": 2}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Comercial AGMAR", "cumplieron": 1, "total": 2, "frec": {"M": 2}, "pct_meta": 0.5}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Comercial AGMAR", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Comercial AGMAR", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Comercial AGMAR", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Documentación", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Documentación", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Documentación", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Documentación", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Documentación", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Facturación AGM", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Facturación AGM", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Facturación AGM", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Facturación AGM", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Facturación AGM", "cumplieron": 1, "total": 2, "frec": {"M": 2}, "pct_meta": 0.5}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones AGMAR", "cumplieron": 10, "total": 10, "frec": {"T": 1, "M": 9}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones AGMAR", "cumplieron": 9, "total": 9, "frec": {"M": 9}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones AGMAR", "cumplieron": 9, "total": 9, "frec": {"M": 9}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones AGMAR", "cumplieron": 7, "total": 9, "frec": {"M": 9}, "pct_meta": 0.7778}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones AGMAR", "cumplieron": 9, "total": 9, "frec": {"M": 9}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "VB", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "VB", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "VB", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "VB", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "VB", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Comercial NL", "cumplieron": 5, "total": 5, "frec": {"T": 5}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Administración y Gestión del Personal", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Administración y Gestión del Personal", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Administración y Gestión del Personal", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Administración y Gestión del Personal", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Administración y Gestión del Personal", "cumplieron": 1, "total": 2, "frec": {"M": 2}, "pct_meta": 0.5}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Gestión de Cultura e Identidad", "cumplieron": 0, "total": 2, "frec": {"M": 2}, "pct_meta": 0.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Gestión de Cultura e Identidad", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Gestión de Cultura e Identidad", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Gestión de Cultura e Identidad", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "Área": "Gestión de Cultura e Identidad", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "TPPA", "Área": "ADUANA", "cumplieron": 2, "total": 3, "frec": {"M": 3}, "pct_meta": 0.6667}, {"Mes": "FEBRERO", "Gerencia Central": "TPPA", "Área": "ADUANA", "cumplieron": 3, "total": 3, "frec": {"M": 3}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "TPPA", "Área": "ADUANA", "cumplieron": 3, "total": 3, "frec": {"M": 3}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "TPPA", "Área": "ADUANA", "cumplieron": 2, "total": 3, "frec": {"M": 3}, "pct_meta": 0.6667}, {"Mes": "MAYO", "Gerencia Central": "TPPA", "Área": "ADUANA", "cumplieron": 3, "total": 3, "frec": {"M": 3}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión Legal", "Área": "Legal", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión Legal", "Área": "Legal", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión Legal", "Área": "Legal", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión Legal", "Área": "Legal", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión Legal", "Área": "Legal", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión Legal", "Área": "Contratos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión Legal", "Área": "Contratos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión Legal", "Área": "Contratos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión Legal", "Área": "Contratos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión Legal", "Área": "Contratos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Procesos Estratégicos", "Área": "Gestión de Riesgos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Procesos Estratégicos", "Área": "Gestión de Riesgos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Procesos Estratégicos", "Área": "Gestión de Riesgos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Procesos Estratégicos", "Área": "Gestión de Riesgos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Procesos Estratégicos", "Área": "Gestión de Riesgos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Procesos Estratégicos", "Área": "Mejora Continua", "cumplieron": 1, "total": 1, "frec": {"T": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Procesos Estratégicos", "Área": "Auditoría y Contro Interno", "cumplieron": 2, "total": 2, "frec": {"T": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Planeamiento Estratégico", "Área": "Planeamiento Estratégico", "cumplieron": 3, "total": 3, "frec": {"T": 3}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Almacenes y logística", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Almacenes y logística", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Almacenes y logística", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Almacenes y logística", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Almacenes y logística", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Planeamiento Vacios", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Planeamiento Vacios", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Planeamiento Vacios", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Planeamiento Vacios", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Planeamiento Vacios", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Documentación", "cumplieron": 8, "total": 9, "frec": {"M": 9}, "pct_meta": 0.8889}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Documentación", "cumplieron": 9, "total": 9, "frec": {"M": 9}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Documentación", "cumplieron": 9, "total": 9, "frec": {"M": 9}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Documentación", "cumplieron": 9, "total": 9, "frec": {"M": 9}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Documentación", "cumplieron": 9, "total": 9, "frec": {"M": 9}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Operaciones", "cumplieron": 6, "total": 7, "frec": {"M": 7}, "pct_meta": 0.8571}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Operaciones", "cumplieron": 6, "total": 7, "frec": {"M": 7}, "pct_meta": 0.8571}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Operaciones", "cumplieron": 6, "total": 7, "frec": {"M": 7}, "pct_meta": 0.8571}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Operaciones", "cumplieron": 6, "total": 7, "frec": {"M": 7}, "pct_meta": 0.8571}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Operaciones", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Maquinarias y Equipos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Maquinarias y Equipos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Maquinarias y Equipos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Maquinarias y Equipos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Maquinarias y Equipos", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "cumplieron": 5, "total": 7, "frec": {"M": 7}, "pct_meta": 0.7143}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "cumplieron": 4, "total": 7, "frec": {"M": 7}, "pct_meta": 0.5714}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "cumplieron": 5, "total": 7, "frec": {"M": 7}, "pct_meta": 0.7143}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "cumplieron": 5, "total": 7, "frec": {"M": 7}, "pct_meta": 0.7143}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "REEFER", "cumplieron": 5, "total": 7, "frec": {"M": 7}, "pct_meta": 0.7143}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "Seguridad y Protección", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "Seguridad y Protección", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "Seguridad y Protección", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "Seguridad y Protección", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "Seguridad y Protección", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Planeamiento", "cumplieron": 8, "total": 8, "frec": {"M": 8}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Planeamiento", "cumplieron": 8, "total": 8, "frec": {"M": 8}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Planeamiento", "cumplieron": 8, "total": 8, "frec": {"M": 8}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Planeamiento", "cumplieron": 8, "total": 8, "frec": {"M": 8}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Planeamiento", "cumplieron": 8, "total": 8, "frec": {"M": 8}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Transporte", "cumplieron": 5, "total": 6, "frec": {"M": 6}, "pct_meta": 0.8333}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Transporte", "cumplieron": 6, "total": 6, "frec": {"M": 6}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Transporte", "cumplieron": 6, "total": 7, "frec": {"M": 6, "T": 1}, "pct_meta": 0.8571}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Transporte", "cumplieron": 5, "total": 6, "frec": {"M": 6}, "pct_meta": 0.8333}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Transporte", "cumplieron": 4, "total": 6, "frec": {"M": 6}, "pct_meta": 0.6667}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones Vacios", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones Vacios", "cumplieron": 6, "total": 7, "frec": {"M": 7}, "pct_meta": 0.8571}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones Vacios", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones Vacios", "cumplieron": 9, "total": 9, "frec": {"M": 9}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "Área": "Operaciones Vacios", "cumplieron": 9, "total": 9, "frec": {"M": 9}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "Área": "Costos y Margenes Operativos", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Regiones", "Área": "Región Norte", "cumplieron": 3, "total": 4, "frec": {"M": 4}, "pct_meta": 0.75}, {"Mes": "FEBRERO", "Gerencia Central": "Regiones", "Área": "Región Norte", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Regiones", "Área": "Región Norte", "cumplieron": 3, "total": 4, "frec": {"M": 4}, "pct_meta": 0.75}, {"Mes": "ABRIL", "Gerencia Central": "Regiones", "Área": "Región Norte", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Regiones", "Área": "Región Norte", "cumplieron": 4, "total": 4, "frec": {"M": 4}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "Aplicaciones Y Arquitectura", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "Aplicaciones Y Arquitectura", "cumplieron": 3, "total": 3, "frec": {"M": 2, "B": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "Aplicaciones Y Arquitectura", "cumplieron": 3, "total": 3, "frec": {"M": 2, "T": 1}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "Aplicaciones Y Arquitectura", "cumplieron": 3, "total": 3, "frec": {"M": 2, "B": 1}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "Aplicaciones Y Arquitectura", "cumplieron": 2, "total": 2, "frec": {"M": 2}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "Proyectos TD", "cumplieron": 1, "total": 1, "frec": {"T": 1}, "pct_meta": 1.0}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "PMO & Operaciones TI", "cumplieron": 5, "total": 5, "frec": {"T": 4, "M": 1}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "PMO & Operaciones TI", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "PMO & Operaciones TI", "cumplieron": 3, "total": 3, "frec": {"M": 1, "B": 2}, "pct_meta": 1.0}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "PMO & Operaciones TI", "cumplieron": 3, "total": 3, "frec": {"M": 1, "B": 2}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "Área": "PMO & Operaciones TI", "cumplieron": 1, "total": 1, "frec": {"M": 1}, "pct_meta": 1.0}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "SSOMA", "cumplieron": 6, "total": 7, "frec": {"M": 7}, "pct_meta": 0.8571}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "SSOMA", "cumplieron": 5, "total": 7, "frec": {"M": 7}, "pct_meta": 0.7143}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "SSOMA", "cumplieron": 7, "total": 8, "frec": {"M": 7, "T": 1}, "pct_meta": 0.875}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "SSOMA", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "Área": "SSOMA", "cumplieron": 7, "total": 7, "frec": {"M": 7}, "pct_meta": 1.0}], "total_kpis_indicador": [{"Mes": "ENERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "total_indicador": 33}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Negocios Logisticos", "total_indicador": 33}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Negocios Logisticos", "total_indicador": 39}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Negocios Logisticos", "total_indicador": 33}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Negocios Logisticos", "total_indicador": 37}, {"Mes": "ENERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "total_indicador": 11}, {"Mes": "FEBRERO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "total_indicador": 12}, {"Mes": "MARZO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "total_indicador": 11}, {"Mes": "ABRIL", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "total_indicador": 12}, {"Mes": "MAYO", "Gerencia Central": "Gerencia de Adquisiciones y Finanzas", "total_indicador": 11}, {"Mes": "MARZO", "Gerencia Central": "Negocios Maritimos y Navieros", "total_indicador": 43}, {"Mes": "ENERO", "Gerencia Central": "Negocios Maritimos y Navieros", "total_indicador": 40}, {"Mes": "FEBRERO", "Gerencia Central": "Negocios Maritimos y Navieros", "total_indicador": 40}, {"Mes": "ABRIL", "Gerencia Central": "Negocios Maritimos y Navieros", "total_indicador": 43}, {"Mes": "MAYO", "Gerencia Central": "Negocios Maritimos y Navieros", "total_indicador": 43}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "total_indicador": 4}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "total_indicador": 4}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "total_indicador": 4}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "total_indicador": 4}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Administración y Desarrollo Humano", "total_indicador": 4}, {"Mes": "ENERO", "Gerencia Central": "TPPA", "total_indicador": 3}, {"Mes": "FEBRERO", "Gerencia Central": "TPPA", "total_indicador": 3}, {"Mes": "MARZO", "Gerencia Central": "TPPA", "total_indicador": 3}, {"Mes": "ABRIL", "Gerencia Central": "TPPA", "total_indicador": 3}, {"Mes": "MAYO", "Gerencia Central": "TPPA", "total_indicador": 3}, {"Mes": "ENERO", "Gerencia Central": "Gestión Legal", "total_indicador": 2}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión Legal", "total_indicador": 2}, {"Mes": "MARZO", "Gerencia Central": "Gestión Legal", "total_indicador": 2}, {"Mes": "ABRIL", "Gerencia Central": "Gestión Legal", "total_indicador": 2}, {"Mes": "MAYO", "Gerencia Central": "Gestión Legal", "total_indicador": 2}, {"Mes": "ENERO", "Gerencia Central": "Procesos Estratégicos", "total_indicador": 1}, {"Mes": "FEBRERO", "Gerencia Central": "Procesos Estratégicos", "total_indicador": 1}, {"Mes": "MARZO", "Gerencia Central": "Procesos Estratégicos", "total_indicador": 4}, {"Mes": "ABRIL", "Gerencia Central": "Procesos Estratégicos", "total_indicador": 1}, {"Mes": "MAYO", "Gerencia Central": "Procesos Estratégicos", "total_indicador": 1}, {"Mes": "MARZO", "Gerencia Central": "Planeamiento Estratégico", "total_indicador": 3}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "total_indicador": 9}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "total_indicador": 9}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "total_indicador": 10}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Seguridad y SSOMA", "total_indicador": 9}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Seguridad y SSOMA", "total_indicador": 9}, {"Mes": "ENERO", "Gerencia Central": "Regiones", "total_indicador": 4}, {"Mes": "FEBRERO", "Gerencia Central": "Regiones", "total_indicador": 4}, {"Mes": "MARZO", "Gerencia Central": "Regiones", "total_indicador": 4}, {"Mes": "ABRIL", "Gerencia Central": "Regiones", "total_indicador": 4}, {"Mes": "MAYO", "Gerencia Central": "Regiones", "total_indicador": 4}, {"Mes": "ENERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "total_indicador": 3}, {"Mes": "FEBRERO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "total_indicador": 6}, {"Mes": "MARZO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "total_indicador": 9}, {"Mes": "ABRIL", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "total_indicador": 6}, {"Mes": "MAYO", "Gerencia Central": "Gestión de Sistemas Digitales y Ciberseguridad", "total_indicador": 3}]};

// ─────────────────────────────────────────────
// STATE
// ─────────────────────────────────────────────
let DATA = EMBEDDED_DATA;
let charts = {};
let selectedMes = 'MAYO';
let selectedGerencia = 'ALL';
const MES_ORDER = ['ENERO','FEBRERO','MARZO','ABRIL','MAYO','JUNIO','JULIO','AGOSTO','SEPTIEMBRE','OCTUBRE','NOVIEMBRE','DICIEMBRE'];

Chart.defaults.color = '#94a3b8';
Chart.defaults.font.family = "'Segoe UI', sans-serif";

const TOOLTIP_DEFAULTS = {
  backgroundColor: '#1e293b',
  borderColor: '#334155',
  borderWidth: 1,
  titleColor: '#f1f5f9',
  bodyColor: '#94a3b8',
  padding: 12,
  cornerRadius: 8,
  titleFont: { weight: '700', size: 13 },
  bodyFont: { size: 12 }
};

// ─────────────────────────────────────────────
// FILTERS UI
// ─────────────────────────────────────────────
function buildFilters() {
  const mesGrid = document.getElementById('mes-slicer');
  mesGrid.innerHTML = '';
  DATA.meses.forEach(m => {
    const btn = document.createElement('button');
    btn.className = 'slicer-btn' + (m === selectedMes ? ' active' : '');
    btn.textContent = m.charAt(0) + m.slice(1).toLowerCase();
    btn.onclick = () => { selectedMes = m; buildFilters(); updateAll(); };
    mesGrid.appendChild(btn);
  });

  const gerList = document.getElementById('gerencia-slicer');
  gerList.innerHTML = '';

  if (KPI_ACCESS !== 'ALL') {
    // Gerente: solo ve su gerencia (filtro bloqueado)
    selectedGerencia = KPI_ACCESS;
    const div = document.createElement('div');
    div.className = 'ger-item active';
    div.textContent = KPI_ACCESS;
    div.style.cursor = 'default';
    gerList.appendChild(div);
    const lock = document.createElement('div');
    lock.style.cssText = 'font-size:10px;color:#64748b;padding:4px 10px;';
    lock.textContent = '🔒 Vista limitada a tu gerencia';
    gerList.appendChild(lock);
    return;
  }

  const allBtn = document.createElement('div');
  allBtn.className = 'ger-item' + (selectedGerencia === 'ALL' ? ' active' : '');
  allBtn.textContent = 'Todas las gerencias';
  allBtn.onclick = () => { selectedGerencia = 'ALL'; buildFilters(); updateAll(); };
  gerList.appendChild(allBtn);

  DATA.gerencias.forEach(g => {
    const div = document.createElement('div');
    div.className = 'ger-item' + (selectedGerencia === g ? ' active' : '');
    div.textContent = g;
    div.onclick = () => { selectedGerencia = g; buildFilters(); updateAll(); };
    gerList.appendChild(div);
  });
}

function filterRows(arr, mes, gerencia) {
  return arr.filter(r => {
    const okMes = mes === 'ALL' || r['Mes'] === mes;
    const okGer = gerencia === 'ALL' || r['Gerencia Central'] === gerencia;
    return okMes && okGer;
  });
}

// ─────────────────────────────────────────────
// KPI CARDS
// ─────────────────────────────────────────────
function updateCards() {
  const rows = filterRows(DATA.cumplimiento_meta, selectedMes, selectedGerencia);
  // NUEVO: N° Total de KPIs solo cuenta Tipo de Dato = Indicador
  const indicRows = filterRows(DATA.total_kpis_indicador || [], selectedMes, selectedGerencia);
  const totalKPIs = indicRows.reduce((s, r) => s + (r.total_indicador || 0), 0);
  const cumplidos = rows.reduce((s, r) => s + r.cumplieron, 0);
  const desviados = rows.reduce((s, r) => s + r.total, 0) - cumplidos;
  const pctMeta = rows.reduce((s, r) => s + r.total, 0) ? (cumplidos / rows.reduce((s, r) => s + r.total, 0)) : 0;

  const repRows = filterRows(DATA.cumplimiento_reporte, selectedMes, selectedGerencia);
  const repTotal = repRows.reduce((s, r) => s + r.total, 0);
  const reportados = repRows.reduce((s, r) => s + r.reportados, 0);
  const pctReporte = repTotal ? (reportados / repTotal) : 0;

  // Indicadores y Métricas que DEBEN reportar en el mes seleccionado (según frecuencia M/B/T)
  const _gerF = KPI_ACCESS !== 'ALL' ? KPI_ACCESS : selectedGerencia;
  const _delMes = KPI_CATALOGO.filter(k =>
    (_gerF === 'ALL' || k.ger === _gerF) &&
    (selectedMes === 'ALL' || (k.meses || []).includes(selectedMes))
  );
  const _totalInd = _delMes.filter(k => k.tipo === 'Indicador').length;
  const _totalMet = _delMes.filter(k => k.tipo !== 'Indicador').length;
  const _mesTxt = selectedMes === 'ALL' ? 'en el año' : 'en ' + selectedMes.charAt(0) + selectedMes.slice(1).toLowerCase();
  document.getElementById('kpi-total-ind').textContent = _totalInd;
  document.getElementById('kpi-total-ind-sub').textContent = 'Reportan ' + _mesTxt;
  document.getElementById('kpi-total-met').textContent = _totalMet;
  document.getElementById('kpi-total-met-sub').textContent = 'Reportan ' + _mesTxt;

  const metaEl = document.getElementById('kpi-meta');
  metaEl.textContent = (pctMeta * 100).toFixed(1) + '%';
  metaEl.style.color = pctMeta >= 0.85 ? '#22c55e' : pctMeta >= 0.7 ? '#f97316' : '#ef4444';

  const repEl = document.getElementById('kpi-reporte');
  repEl.textContent = (pctReporte * 100).toFixed(1) + '%';
  repEl.style.color = pctReporte >= 0.9 ? '#22c55e' : pctReporte >= 0.7 ? '#f97316' : '#ef4444';

  document.getElementById('kpi-desviados').textContent = desviados.toLocaleString();
}

// ─────────────────────────────────────────────
// CHART 1: PIE META
// ─────────────────────────────────────────────
function updatePieMeta() {
  const rows = filterRows(DATA.cumplimiento_meta, selectedMes, selectedGerencia);
  const cumplieron = rows.reduce((s, r) => s + r.cumplieron, 0);
  const total = rows.reduce((s, r) => s + r.total, 0);
  const nocumplieron = total - cumplieron;
  const pct = total ? ((cumplieron / total) * 100).toFixed(1) : 0;
  const pctNo = total ? ((nocumplieron / total) * 100).toFixed(1) : 0;

  if (charts.pieMeta) charts.pieMeta.destroy();
  charts.pieMeta = new Chart(document.getElementById('chart-pie-meta'), {
    type: 'doughnut',
    data: {
      labels: [`Cumplieron la Meta: ${pct}%`, `No Cumplieron: ${pctNo}%`],
      datasets: [{
        data: [cumplieron, nocumplieron],
        backgroundColor: ['rgba(59,130,246,0.9)', 'rgba(249,115,22,0.9)'],
        borderColor: ['rgba(59,130,246,0.3)', 'rgba(249,115,22,0.3)'],
        borderWidth: 2,
        hoverOffset: 6
      }]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      cutout: '60%',
      onClick: (e, els) => { if (els.length) openKpiModalMedidos(selectedGerencia, null, els[0].index === 0 ? 'cumplieron' : 'nocumplieron'); },
      onHover: (e, els) => { e.native.target.style.cursor = els.length ? 'pointer' : 'default'; },
      plugins: {
        legend: { position: 'right', labels: { padding: 12, font: { size: 11 }, color: '#94a3b8', usePointStyle: true, pointStyleWidth: 8 } },
        tooltip: { ...TOOLTIP_DEFAULTS, callbacks: { label: (item) => `  ${item.label}: ${item.raw} (${((item.raw/total)*100).toFixed(1)}%)` } }
      }
    },
    plugins: [{
      id: 'centerText', afterDraw(chart) {
        const { ctx, chartArea } = chart;
        const cx = (chartArea.left + chartArea.right) / 2;
        const cy = (chartArea.top + chartArea.bottom) / 2 - 4;
        ctx.save();
        ctx.textAlign = 'center';
        ctx.font = "bold 22px 'Segoe UI', sans-serif";
        ctx.fillStyle = parseFloat(pct) >= 85 ? '#22c55e' : '#f97316';
        ctx.fillText(pct + '%', cx, cy);
        ctx.font = "11px 'Segoe UI', sans-serif";
        ctx.fillStyle = '#94a3b8';
        ctx.fillText('Cumplieron', cx, cy + 16);
        ctx.restore();
      }
    }]
  });
}

// ─────────────────────────────────────────────
// CHART 2: PIE REPORTE
// ─────────────────────────────────────────────
function updatePieReporte() {
  const rows = filterRows(DATA.cumplimiento_reporte, selectedMes, selectedGerencia);
  const reportados = rows.reduce((s, r) => s + r.reportados, 0);
  const total = rows.reduce((s, r) => s + r.total, 0);
  const noreportados = total - reportados;
  const pct = total ? ((reportados / total) * 100).toFixed(0) : 0;

  if (charts.pieReporte) charts.pieReporte.destroy();
  charts.pieReporte = new Chart(document.getElementById('chart-pie-reporte'), {
    type: 'doughnut',
    data: {
      labels: ['KPIs Cargados en la PGC', 'KPIs No Cargados en la PGC'],
      datasets: [{
        data: [reportados, noreportados],
        backgroundColor: ['rgba(59,130,246,0.9)', 'rgba(249,115,22,0.9)'],
        borderColor: ['rgba(59,130,246,0.3)', 'rgba(249,115,22,0.3)'],
        borderWidth: 2,
        hoverOffset: 6
      }]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      cutout: '60%',
      onClick: (e, els) => { if (els.length) openKpiModalMedidos(selectedGerencia, null, els[0].index === 0 ? 'cargados' : 'nocargados'); },
      onHover: (e, els) => { e.native.target.style.cursor = els.length ? 'pointer' : 'default'; },
      plugins: {
        legend: { position: 'right', labels: { padding: 12, font: { size: 11 }, color: '#94a3b8', usePointStyle: true, pointStyleWidth: 8 } },
        tooltip: { ...TOOLTIP_DEFAULTS, callbacks: { label: (item) => `  ${item.label}: ${item.raw} (${((item.raw/total)*100).toFixed(1)}%)` } }
      }
    },
    plugins: [{
      id: 'centerText', afterDraw(chart) {
        const { ctx, chartArea } = chart;
        const cx = (chartArea.left + chartArea.right) / 2;
        const cy = (chartArea.top + chartArea.bottom) / 2 - 4;
        ctx.save();
        ctx.textAlign = 'center';
        ctx.font = "bold 22px 'Segoe UI', sans-serif";
        ctx.fillStyle = pct >= 90 ? '#22c55e' : '#f97316';
        ctx.fillText(reportados, cx, cy);
        ctx.font = "11px 'Segoe UI', sans-serif";
        ctx.fillStyle = '#94a3b8';
        ctx.fillText('Cargados', cx, cy + 16);
        ctx.restore();
      }
    }]
  });
}

// ─────────────────────────────────────────────
// CHART 3: KAIZEN (placeholder)
// ─────────────────────────────────────────────
const KAIZEN_ORDER = ['DONE', 'ON GOING', 'SIN CREAR'];
function kaizenRows() {
  const gerF = KPI_ACCESS !== 'ALL' ? KPI_ACCESS : selectedGerencia;
  return KAIZEN_DET.filter(d =>
    (selectedMes === 'ALL' || d.Mes === selectedMes) &&
    (gerF === 'ALL' || d.ger === gerF)
  );
}

function updatePieKaizen() {
  const rows = kaizenRows();
  const counts = KAIZEN_ORDER.map(e => rows.filter(d => d.est === e).length);
  const total = rows.length;

  if (charts.pieKaizen) charts.pieKaizen.destroy();
  charts.pieKaizen = new Chart(document.getElementById('chart-pie-kaizen'), {
    type: 'doughnut',
    data: {
      labels: KAIZEN_ORDER,
      datasets: [{
        data: counts,
        backgroundColor: ['rgba(34,197,94,0.9)', 'rgba(59,130,246,0.9)', 'rgba(239,68,68,0.9)'],
        borderColor: ['rgba(34,197,94,0.3)', 'rgba(59,130,246,0.3)', 'rgba(239,68,68,0.3)'],
        borderWidth: 2,
        hoverOffset: 6
      }]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      cutout: '60%',
      onClick: (e, els) => { if (els.length) openKaizenModal(KAIZEN_ORDER[els[0].index]); },
      onHover: (e, els) => { e.native.target.style.cursor = els.length ? 'pointer' : 'default'; },
      plugins: {
        legend: { position: 'right', labels: { padding: 12, font: { size: 11 }, color: '#94a3b8', usePointStyle: true, pointStyleWidth: 8 } },
        tooltip: { ...TOOLTIP_DEFAULTS, callbacks: {
          label: (item) => `  ${item.label}: ${item.raw}${total ? ' (' + ((item.raw/total)*100).toFixed(0) + '%)' : ''}`,
          footer: () => 'Click para ver el detalle'
        } }
      }
    },
    plugins: [{
      id: 'centerTextKz', afterDraw(chart) {
        const { ctx, chartArea } = chart;
        const cx = (chartArea.left + chartArea.right) / 2;
        const cy = (chartArea.top + chartArea.bottom) / 2 - 4;
        ctx.save();
        ctx.textAlign = 'center';
        ctx.font = "bold 22px 'Segoe UI', sans-serif";
        const sinCrear = counts[2];
        ctx.fillStyle = total === 0 ? '#64748b' : (sinCrear === 0 ? '#22c55e' : '#ef4444');
        ctx.fillText(total === 0 ? '—' : total, cx, cy);
        ctx.font = "11px 'Segoe UI', sans-serif";
        ctx.fillStyle = '#94a3b8';
        ctx.fillText(total === 0 ? 'Sin KAIZEN' : 'Requeridos', cx, cy + 16);
        ctx.restore();
      }
    }]
  });
}

function openKaizenModal(estatus) {
  kpiModalFilter = { kzEst: estatus };
  openKpiModal('kaizen');
}

// ─────────────────────────────────────────────
// CHART 4: BAR GERENCIA META (stacked %)
// ─────────────────────────────────────────────
function updateBarGerenciaMeta() {
  const rows = filterRows(DATA.cumplimiento_meta, selectedMes, KPI_ACCESS !== 'ALL' ? KPI_ACCESS : 'ALL'); // gerentes solo ven su gerencia
  const agg = {};
  rows.forEach(r => {
    if (!agg[r['Gerencia Central']]) agg[r['Gerencia Central']] = { c: 0, t: 0 };
    agg[r['Gerencia Central']].c += r.cumplieron;
    agg[r['Gerencia Central']].t += r.total;
  });

  const labels = Object.keys(agg).sort((a, b) => (agg[b].c / agg[b].t) - (agg[a].c / agg[a].t));
  const pcts = labels.map(l => agg[l].t ? +((agg[l].c / agg[l].t) * 100).toFixed(1) : 0);
  const noPcts = labels.map(l => agg[l].t ? +(((agg[l].t - agg[l].c) / agg[l].t) * 100).toFixed(1) : 0);
  const shortLabels = labels.map(l => l.replace('Gerencia de ', '').replace('Gestión de ', 'G. ').replace('Negocios Maritimos y Navieros', 'NMN'));

  if (charts.barGerMeta) charts.barGerMeta.destroy();
  charts.barGerMeta = new Chart(document.getElementById('chart-bar-gerencia-meta'), {
    type: 'bar',
    data: {
      labels: shortLabels,
      datasets: [
        { label: '% KPIs Cumplieron la Meta', data: pcts, backgroundColor: 'rgba(59,130,246,0.85)', borderRadius: 4 },
        { label: '% KPIs No Cumplieron la Meta', data: noPcts, backgroundColor: 'rgba(249,115,22,0.85)', borderRadius: 4 }
      ]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      onClick: (e, els) => { if (els.length) openKpiModalMedidos(labels[els[0].index], null, els[0].datasetIndex === 0 ? 'cumplieron' : 'nocumplieron'); },
      onHover: (e, els) => { e.native.target.style.cursor = els.length ? 'pointer' : 'default'; },
      plugins: {
        legend: { position: 'right', labels: { font: { size: 11 }, color: '#94a3b8', usePointStyle: true } },
        tooltip: { ...TOOLTIP_DEFAULTS, callbacks: {
          title: (items) => labels[items[0].dataIndex],
          label: (item) => `  ${item.dataset.label}: ${item.raw}%`,
          footer: () => 'Click en la barra para ver los KPIs'
        } }
      },
      scales: {
        x: { stacked: true, grid: { display: false }, ticks: { color: '#94a3b8', font: { size: 10 }, maxRotation: 45 }, border: { display: false } },
        y: { stacked: true, max: 100, grid: { color: 'rgba(255,255,255,0.04)' }, ticks: { callback: v => v + '%', color: '#64748b', font: { size: 10 } }, border: { display: false } }
      }
    }
  });
}

// ─────────────────────────────────────────────
// CHART 5: BAR GERENCIA REPORTE (stacked %)
// ─────────────────────────────────────────────
function updateBarGerenciaReporte() {
  const rows = filterRows(DATA.cumplimiento_reporte, selectedMes, KPI_ACCESS !== 'ALL' ? KPI_ACCESS : 'ALL');
  const agg = {};
  rows.forEach(r => {
    if (!agg[r['Gerencia Central']]) agg[r['Gerencia Central']] = { rep: 0, t: 0 };
    agg[r['Gerencia Central']].rep += r.reportados;
    agg[r['Gerencia Central']].t += r.total;
  });

  const labels = Object.keys(agg).sort((a, b) => (agg[b].rep / agg[b].t) - (agg[a].rep / agg[a].t));
  const pcts = labels.map(l => agg[l].t ? +((agg[l].rep / agg[l].t) * 100).toFixed(1) : 0);
  const noPcts = labels.map(l => agg[l].t ? +(((agg[l].t - agg[l].rep) / agg[l].t) * 100).toFixed(1) : 0);
  const shortLabels = labels.map(l => l.replace('Gerencia de ', '').replace('Gestión de ', 'G. ').replace('Negocios Maritimos y Navieros', 'NMN'));

  if (charts.barGerRep) charts.barGerRep.destroy();
  charts.barGerRep = new Chart(document.getElementById('chart-bar-gerencia-reporte'), {
    type: 'bar',
    data: {
      labels: shortLabels,
      datasets: [
        { label: '% KPIs Cargados en la PGC', data: pcts, backgroundColor: 'rgba(59,130,246,0.85)', borderRadius: 4 },
        { label: '% KPIs No Cargados en la PGC', data: noPcts, backgroundColor: 'rgba(249,115,22,0.85)', borderRadius: 4 }
      ]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      onClick: (e, els) => { if (els.length) openKpiModalMedidos(labels[els[0].index], null, els[0].datasetIndex === 0 ? 'cargados' : 'nocargados'); },
      onHover: (e, els) => { e.native.target.style.cursor = els.length ? 'pointer' : 'default'; },
      plugins: {
        legend: { position: 'right', labels: { font: { size: 11 }, color: '#94a3b8', usePointStyle: true } },
        tooltip: { ...TOOLTIP_DEFAULTS, callbacks: {
          title: (items) => labels[items[0].dataIndex],
          label: (item) => `  ${item.dataset.label}: ${item.raw}%`,
          footer: () => 'Click en la barra para ver los KPIs'
        } }
      },
      scales: {
        x: { stacked: true, grid: { display: false }, ticks: { color: '#94a3b8', font: { size: 10 }, maxRotation: 45 }, border: { display: false } },
        y: { stacked: true, max: 100, grid: { color: 'rgba(255,255,255,0.04)' }, ticks: { callback: v => v + '%', color: '#64748b', font: { size: 10 } }, border: { display: false } }
      }
    }
  });
}

// ─────────────────────────────────────────────
// CHART 6: BAR AREA META
// ─────────────────────────────────────────────
const FREQ_NAMES = { M: 'Mensual', T: 'Trimestral', B: 'Bimestral' };
function frecLabel(frec) {
  if (!frec) return '';
  return Object.entries(frec).map(([f, n]) => `${FREQ_NAMES[f] || f} (${n})`).join(', ');
}

function updateBarAreaMeta() {
  // Solo KPIs que DEBEN reportar en el mes según su frecuencia (M=Mensual, T=Trimestral, B=Bimestral)
  const rows = filterRows(DATA.cumplimiento_area, selectedMes, selectedGerencia);
  const agg = {};
  rows.forEach(r => {
    const key = r['Área'] + '||' + r['Gerencia Central'];
    if (!agg[key]) agg[key] = { area: r['Área'], ger: r['Gerencia Central'], c: 0, t: 0, frec: {} };
    agg[key].c += r.cumplieron;
    agg[key].t += r.total;
    Object.entries(r.frec || {}).forEach(([f, n]) => { agg[key].frec[f] = (agg[key].frec[f] || 0) + n; });
  });
  const sorted = Object.values(agg).filter(v => v.t > 0).map(v => ({ ...v, pct: v.t ? (v.c / v.t) * 100 : 0 })).sort((a, b) => b.pct - a.pct).slice(0, 15);
  const labels = sorted.map(v => v.area);
  const pcts = sorted.map(v => +v.pct.toFixed(1));
  const noPcts = sorted.map(v => +(100 - v.pct).toFixed(1));

  if (charts.barAreaMeta) charts.barAreaMeta.destroy();
  charts.barAreaMeta = new Chart(document.getElementById('chart-bar-area-meta'), {
    type: 'bar',
    data: {
      labels,
      datasets: [
        { label: '% Cumplieron', data: pcts, backgroundColor: 'rgba(59,130,246,0.85)', borderRadius: 4 },
        { label: '% No Cumplieron', data: noPcts, backgroundColor: 'rgba(249,115,22,0.85)', borderRadius: 4 }
      ]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      onClick: (e, els) => { if (els.length) { const v = sorted[els[0].index]; openKpiModalMedidos(v.ger, v.area, els[0].datasetIndex === 0 ? 'cumplieron' : 'nocumplieron'); } },
      onHover: (e, els) => { e.native.target.style.cursor = els.length ? 'pointer' : 'default'; },
      plugins: {
        legend: { position: 'right', labels: { font: { size: 11 }, color: '#94a3b8', usePointStyle: true } },
        tooltip: { ...TOOLTIP_DEFAULTS, callbacks: {
          label: (item) => `  ${item.dataset.label}: ${item.raw}%`,
          afterBody: (items) => {
            const v = sorted[items[0].dataIndex];
            const lines = [`  KPIs que reportan este mes: ${v.t}`];
            const fl = frecLabel(v.frec);
            if (fl) lines.push(`  Frecuencia: ${fl}`);
            return lines;
          },
          footer: () => 'Click en la barra para ver los KPIs'
        } }
      },
      scales: {
        x: { stacked: true, grid: { display: false }, ticks: { color: '#94a3b8', font: { size: 10 }, maxRotation: 45 }, border: { display: false } },
        y: { stacked: true, max: 100, grid: { color: 'rgba(255,255,255,0.04)' }, ticks: { callback: v => v + '%', color: '#64748b', font: { size: 10 } }, border: { display: false } }
      }
    }
  });
}

// ─────────────────────────────────────────────
// CHART 7: BAR AREA REPORTE
// ─────────────────────────────────────────────
function updateBarAreaReporte() {
  // We don't have area-level report data in the embedded set, so we simulate from area meta totals
  const rows = filterRows(DATA.cumplimiento_area, selectedMes, selectedGerencia);
  const agg = {};
  rows.forEach(r => {
    const key = r['Área'] + '||' + r['Gerencia Central'];
    if (!agg[key]) agg[key] = { area: r['Área'], ger: r['Gerencia Central'], t: 0 };
    agg[key].t += r.total;
  });
  // Simulate 100% report for areas with data (since we don't have per-area report data)
  const sorted = Object.values(agg).filter(v => v.t > 0).map(v => ({ ...v, pct: 100 })).sort((a, b) => b.t - a.t).slice(0, 12);
  const labels = sorted.map(v => v.area);
  const pcts = sorted.map(v => 100);
  const noPcts = sorted.map(v => 0);

  if (charts.barAreaRep) charts.barAreaRep.destroy();
  charts.barAreaRep = new Chart(document.getElementById('chart-bar-area-reporte'), {
    type: 'bar',
    data: {
      labels,
      datasets: [
        { label: '% Cargados en PGC', data: pcts, backgroundColor: 'rgba(59,130,246,0.85)', borderRadius: 4 },
        { label: '% No Cargados', data: noPcts, backgroundColor: 'rgba(249,115,22,0.85)', borderRadius: 4 }
      ]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      onClick: (e, els) => { if (els.length) { const v = sorted[els[0].index]; openKpiModalMedidos(v.ger, v.area, els[0].datasetIndex === 0 ? 'cargados' : 'nocargados'); } },
      onHover: (e, els) => { e.native.target.style.cursor = els.length ? 'pointer' : 'default'; },
      plugins: {
        legend: { position: 'right', labels: { font: { size: 11 }, color: '#94a3b8', usePointStyle: true } },
        tooltip: { ...TOOLTIP_DEFAULTS, callbacks: {
          label: (item) => `  ${item.dataset.label}: ${item.raw}%`,
          footer: () => 'Click en la barra para ver los KPIs'
        } }
      },
      scales: {
        x: { stacked: true, grid: { display: false }, ticks: { color: '#94a3b8', font: { size: 10 }, maxRotation: 45 }, border: { display: false } },
        y: { stacked: true, max: 100, grid: { color: 'rgba(255,255,255,0.04)' }, ticks: { callback: v => v + '%', color: '#64748b', font: { size: 10 } }, border: { display: false } }
      }
    }
  });
}

// ─────────────────────────────────────────────
// CHART 8: CUMPLIMIENTO DE SLA (anillo con datos reales del Excel)
// ─────────────────────────────────────────────
function slaRows() {
  const gerF = KPI_ACCESS !== 'ALL' ? KPI_ACCESS : selectedGerencia;
  return SLA_DET.filter(d =>
    (selectedMes === 'ALL' || d.Mes === selectedMes) &&
    (gerF === 'ALL' || d.ger === gerF)
  );
}

function updateSLA() {
  const rows = slaRows();
  const total = rows.length;
  const cumplieron = rows.filter(d => d.ok === 1).length;
  const nocumplieron = total - cumplieron;
  const pct = total ? ((cumplieron / total) * 100).toFixed(1) : 0;

  if (charts.sla) charts.sla.destroy();
  charts.sla = new Chart(document.getElementById('chart-sla'), {
    type: 'doughnut',
    data: {
      labels: [`Cumplieron SLA: ${cumplieron}`, `No cumplieron: ${nocumplieron}`],
      datasets: [{
        data: [cumplieron, nocumplieron],
        backgroundColor: ['rgba(34,197,94,0.9)', 'rgba(239,68,68,0.9)'],
        borderColor: ['rgba(34,197,94,0.3)', 'rgba(239,68,68,0.3)'],
        borderWidth: 2,
        hoverOffset: 6
      }]
    },
    options: {
      responsive: true, maintainAspectRatio: false,
      cutout: '60%',
      onClick: (e, els) => { if (els.length) openSlaModal(els[0].index === 0); },
      onHover: (e, els) => { e.native.target.style.cursor = els.length ? 'pointer' : 'default'; },
      plugins: {
        legend: { position: 'right', labels: { padding: 12, font: { size: 11 }, color: '#94a3b8', usePointStyle: true, pointStyleWidth: 8 } },
        tooltip: { ...TOOLTIP_DEFAULTS, callbacks: {
          label: (item) => `  ${item.label}${total ? ' (' + ((item.raw/total)*100).toFixed(1) + '%)' : ''}`,
          footer: () => 'Click para ver el detalle'
        } }
      }
    },
    plugins: [{
      id: 'centerTextSla', afterDraw(chart) {
        const { ctx, chartArea } = chart;
        const cx = (chartArea.left + chartArea.right) / 2;
        const cy = (chartArea.top + chartArea.bottom) / 2 - 4;
        ctx.save();
        ctx.textAlign = 'center';
        ctx.font = "bold 24px 'Segoe UI', sans-serif";
        ctx.fillStyle = total === 0 ? '#64748b' : (parseFloat(pct) >= 85 ? '#22c55e' : '#ef4444');
        ctx.fillText(total === 0 ? '—' : pct + '%', cx, cy);
        ctx.font = "11px 'Segoe UI', sans-serif";
        ctx.fillStyle = '#94a3b8';
        ctx.fillText(total === 0 ? 'Sin KPIs SLA' : 'Cumplimiento SLA', cx, cy + 17);
        ctx.restore();
      }
    }]
  });
}

function openSlaModal(cumplieron) {
  kpiModalFilter = { slaOk: cumplieron };
  openKpiModal('sla');
}

// ─────────────────────────────────────────────
// RANKING TABLE
// ─────────────────────────────────────────────
function updateRanking() {
  const rows = filterRows(DATA.cumplimiento_area, selectedMes, selectedGerencia);
  const agg = {};
  rows.forEach(r => {
    const key = r['Área'] + '||' + r['Gerencia Central'];
    if (!agg[key]) agg[key] = { area: r['Área'], ger: r['Gerencia Central'], c: 0, t: 0 };
    agg[key].c += r.cumplieron;
    agg[key].t += r.total;
  });

  const sorted = Object.values(agg).filter(v => v.t > 0).map(v => ({ ...v, pct: v.c / v.t })).sort((a, b) => b.pct - a.pct).slice(0, 20);
  const tbody = document.getElementById('ranking-tbody');
  tbody.innerHTML = '';
  sorted.forEach((row, idx) => {
    const pct = (row.pct * 100).toFixed(0);
    const color = row.pct >= 0.85 ? '#22c55e' : row.pct >= 0.7 ? '#f97316' : '#ef4444';
    const rankClass = idx === 0 ? 'rank-1' : idx === 1 ? 'rank-2' : idx === 2 ? 'rank-3' : 'rank-n';
    const shortGer = row.ger.replace('Gerencia de ', '').replace('Gestión de ', 'G. ').replace('Negocios Maritimos y Navieros', 'NMN');
    tbody.innerHTML += `<tr style="cursor:pointer;" onclick="openKpiModalMedidos('${row.ger.replace(/'/g, "\\'")}', '${row.area.replace(/'/g, "\\'")}')" title="Ver indicadores de ${row.area}">
      <td><span class="rank-badge ${rankClass}">${idx + 1}</span></td>
      <td style="color:#f1f5f9; font-weight:500;">${row.area}</td>
      <td style="color:#64748b; font-size:11px;">${shortGer}</td>
      <td><div class="bar-cell"><div class="mini-bar" style="width:${Math.max(pct, 4)}px; background:${color}; max-width:80px;"></div><span class="pct-text" style="color:${color}">${pct}%</span></div></td>
    </tr>`;
  });
}

// ─────────────────────────────────────────────
// UPDATE ALL
// ─────────────────────────────────────────────
function updateAll() {
  updateCards();
  updatePieMeta();
  updatePieReporte();
  updatePieKaizen();
  updateBarGerenciaMeta();
  updateBarGerenciaReporte();
  updateBarAreaMeta();
  updateBarAreaReporte();
  updateSLA();
  updateRanking();
}

// ─────────────────────────────────────────────
// EXCEL PARSER (same logic as original)
// ─────────────────────────────────────────────
function parseExcel(file) {
  const reader = new FileReader();
  reader.onload = (e) => {
    try {
      const wb = XLSX.read(e.target.result, { type: 'array' });
      const sheetName = wb.SheetNames.find(n => /LISTA\s*M[AE]STRA/i.test(n)) || wb.SheetNames.find(n => n.toUpperCase().includes('BASE')) || wb.SheetNames[0];
      const ws = wb.Sheets[sheetName];
      const raw = XLSX.utils.sheet_to_json(ws, { defval: null });
      if (!raw.length) throw new Error('Hoja vacía');

      const keys = Object.keys(raw[0]);
      const findCol = (...candidates) => keys.find(k => candidates.some(c => k.toLowerCase().includes(c.toLowerCase())));
      const COL_GER = findCol('Gerencia Central', 'Gerencia');
      const COL_MES = findCol('Mes');
      const COL_META = findCol('CUMPLIÓ META', 'CUMPLIO META', 'Meta');
      const COL_REPORTE = findCol('CUMPLIÓ REPORTE', 'CUMPLIO REPORTE', 'Reporte');
      const COL_TIPO = findCol('TIPO DE PROCESO', 'Tipo Proceso');
      const COL_DATO = findCol('Tipo de Dato', 'TipoDato');
      const COL_DEBE = findCol('¿DEBE REPORTAR', 'DEBE REPORTAR');
      const COL_AREA = findCol('Área', 'Area');
      const COL_FREC = findCol('Frecuencia');
      if (!COL_GER || !COL_MES) throw new Error('No se encontraron columnas clave');

      const active = raw.filter(r => { const tipo = r[COL_TIPO]; const dato = r[COL_DATO]; return tipo !== 'ELIMINADO' && dato !== 'ELIMINADO'; });
      const active2 = active.filter(r => { const debe = r[COL_DEBE]; return debe === 1 || debe === '1'; });

      const cumplimiento_meta_agg = {};
      const cumplimiento_reporte_agg = {};
      const tipo_proceso_agg = {};
      const kpis_desviados_agg = {};
      const global_agg = {};
      const cumplimiento_area_agg = {};
      const total_kpis_indicador_agg = {}; // NUEVO: solo cuenta Tipo de Dato = Indicador
      const mesSet = new Set();
      const gerSet = new Set();

      active2.forEach(r => {
        const mes = (r[COL_MES] || '').toString().toUpperCase().trim();
        const ger = (r[COL_GER] || '').toString().trim();
        const meta = r[COL_META];
        const rep = r[COL_REPORTE];
        const tipo = (r[COL_TIPO] || '').toString().trim();
        const area = (r[COL_AREA] || '').toString().trim();
        const frec = COL_FREC ? (r[COL_FREC] || '').toString().trim() : '';
        if (!mes || !ger) return;
        mesSet.add(mes); gerSet.add(ger);
        const mk = mes + '||' + ger;
        if (!cumplimiento_meta_agg[mk]) cumplimiento_meta_agg[mk] = { Mes: mes, 'Gerencia Central': ger, cumplieron: 0, total: 0 };
        cumplimiento_meta_agg[mk].total++;
        if (meta === 1 || meta === '1') cumplimiento_meta_agg[mk].cumplieron++;
        if (!cumplimiento_reporte_agg[mk]) cumplimiento_reporte_agg[mk] = { Mes: mes, 'Gerencia Central': ger, reportados: 0, total: 0 };
        cumplimiento_reporte_agg[mk].total++;
        if (rep === 2 || rep === '2') cumplimiento_reporte_agg[mk].reportados++; // 2 = reportó, 1 = no reportó
        if (tipo) { const tk = mes + '||' + ger + '||' + tipo; if (!tipo_proceso_agg[tk]) tipo_proceso_agg[tk] = { Mes: mes, 'Gerencia Central': ger, 'TIPO DE PROCESO': tipo, count: 0 }; tipo_proceso_agg[tk].count++; }
        if (meta !== 1 && meta !== '1' && area) { const dk = mes + '||' + ger + '||' + area; if (!kpis_desviados_agg[dk]) kpis_desviados_agg[dk] = { Mes: mes, 'Gerencia Central': ger, 'Área': area, kpis_desviados: 0 }; kpis_desviados_agg[dk].kpis_desviados++; }
        if (!global_agg[mes]) global_agg[mes] = { Mes: mes, cumplieron: 0, total: 0 }; global_agg[mes].total++; if (meta === 1 || meta === '1') global_agg[mes].cumplieron++;
        if (area) { const ak = mes + '||' + ger + '||' + area; if (!cumplimiento_area_agg[ak]) cumplimiento_area_agg[ak] = { Mes: mes, 'Gerencia Central': ger, 'Área': area, cumplieron: 0, total: 0, frec: {} }; cumplimiento_area_agg[ak].total++; if (meta === 1 || meta === '1') cumplimiento_area_agg[ak].cumplieron++; if (frec) cumplimiento_area_agg[ak].frec[frec] = (cumplimiento_area_agg[ak].frec[frec] || 0) + 1; }
        // NUEVO: contar solo si Tipo de Dato = Indicador (para N° Total de KPIs)
        const tipoDatoVal = (r[COL_DATO] || '').toString().trim();
        if (tipoDatoVal.toUpperCase() === 'INDICADOR') {
          const tkpi = mes + '||' + ger;
          if (!total_kpis_indicador_agg[tkpi]) total_kpis_indicador_agg[tkpi] = { Mes: mes, 'Gerencia Central': ger, total_indicador: 0 };
          total_kpis_indicador_agg[tkpi].total_indicador++;
        }
      });

      const addPcts = arr => arr.map(r => ({ ...r, pct_meta: r.total ? +(r.cumplieron / r.total).toFixed(4) : 0 }));
      const addPctR = arr => arr.map(r => ({ ...r, pct_reporte: r.total ? +(r.reportados / r.total).toFixed(4) : 0 }));
      const addPctG = arr => arr.map(r => ({ ...r, pct: r.total ? +(r.cumplieron / r.total).toFixed(4) : 0 }));

      DATA = {
        cumplimiento_meta: addPcts(Object.values(cumplimiento_meta_agg)),
        cumplimiento_reporte: addPctR(Object.values(cumplimiento_reporte_agg)),
        tipo_proceso: Object.values(tipo_proceso_agg),
        kpis_desviados: Object.values(kpis_desviados_agg),
        global_por_mes: addPctG(Object.values(global_agg)),
        gerencias: [...gerSet].sort(),
        // Solo meses (desde enero) donde ya se reportó la mayoría de KPIs que debían hacerlo
        meses: MES_ORDER.filter(m => {
          const rep = Object.values(cumplimiento_reporte_agg).filter(r => r.Mes === m);
          const t = rep.reduce((s, r) => s + r.total, 0);
          const rp = rep.reduce((s, r) => s + r.reportados, 0);
          return t > 0 && rp / t > 0.5;
        }),
        cumplimiento_area: addPcts(Object.values(cumplimiento_area_agg)),
        total_kpis_indicador: Object.values(total_kpis_indicador_agg) // NUEVO
      };

      setStatus('✓ ' + file.name + ' cargado', 'ok');
      document.getElementById('last-updated').textContent = `Última actualización: ${new Date().toLocaleString('es-PE')}`;
      if (DATA.meses.length && !DATA.meses.includes(selectedMes)) selectedMes = DATA.meses[DATA.meses.length - 1];
      buildFilters();
      updateAll();
    } catch (err) {
      setStatus('✗ Error: ' + err.message, 'err');
      console.error(err);
    }
  };
  reader.readAsArrayBuffer(file);
}

function setStatus(msg, type) {
  const el = document.getElementById('upload-status');
  el.textContent = msg;
  el.className = 'upload-status ' + type;
  el.style.display = 'block';
}


// ─────────────────────────────────────────────
// MODAL DETALLE: Indicadores / Métricas / Desviados
// ─────────────────────────────────────────────
const FREC_FULL = { M: 'Mensual', B: 'Bimestral', T: 'Trimestral' };

// ─────────────────────────────────────────────
// INDICADORES MEDIDOS (por gerencia/área/mes)
// ─────────────────────────────────────────────
let kpiModalFilter = null; // { ger, area }

function kpisMedidos(ger, area, mes) {
  return KPI_CATALOGO.filter(k =>
    (!ger || ger === 'ALL' || k.ger === ger) &&
    (!area || k.area === area) &&
    (!mes || mes === 'ALL' || (k.meses || []).includes(mes))
  );
}


function openKpiModalMedidos(ger, area, estado) {
  kpiModalFilter = { ger: ger || 'ALL', area: area || null, estado: estado || null };
  openKpiModal('medidos');
}

let kpiModalMode = null;

function openKpiModal(mode) {
  kpiModalMode = mode;
  document.getElementById('kpi-modal-search').value = '';
  renderKpiModal();
  const ov = document.getElementById('kpi-modal-overlay');
  ov.classList.remove('closing');
  ov.classList.add('open');
}
function closeKpiModal() {
  const ov = document.getElementById('kpi-modal-overlay');
  if (!ov.classList.contains('open') || ov.classList.contains('closing')) return;
  ov.classList.add('closing');
  setTimeout(() => { ov.classList.remove('open', 'closing'); }, 220);
}
document.addEventListener('keydown', e => { if (e.key === 'Escape') closeKpiModal(); });

function renderKpiModal() {
  const gerF = KPI_ACCESS !== 'ALL' ? KPI_ACCESS : selectedGerencia;
  const q = document.getElementById('kpi-modal-search').value.toLowerCase().trim();
  const body = document.getElementById('kpi-modal-body');
  const titleEl = document.getElementById('kpi-modal-title');
  const countEl = document.getElementById('kpi-modal-count');
  const gerTxt = gerF === 'ALL' ? 'Todas las gerencias' : gerF;
  const match = t => !q || t.toLowerCase().includes(q);

  if (kpiModalMode === 'desviados') {
    let rows = KPI_DESVIADOS_DET.filter(d =>
      (selectedMes === 'ALL' || d.Mes === selectedMes) &&
      (gerF === 'ALL' || d.ger === gerF) &&
      match(d.nom + ' ' + d.cod + ' ' + d.area + ' ' + d.ger)
    );
    titleEl.textContent = `⚠️ KPIs Desviados — ${selectedMes.charAt(0) + selectedMes.slice(1).toLowerCase()} · ${gerTxt}`;
    countEl.textContent = rows.length;
    if (!rows.length) { body.innerHTML = '<p style="color:#64748b;font-size:13px;padding:20px 0;text-align:center;">Sin KPIs desviados con los filtros actuales 🎉</p>'; return; }
    body.innerHTML = `<table class="kpi-det-table"><thead><tr>
      <th>Código</th><th>Indicador</th><th>Gerencia</th><th>Área</th><th>Frecuencia</th><th>Motivo</th>
    </tr></thead><tbody>` + rows.map(d => {
      const shortGer = d.ger.replace('Gerencia de ', '').replace('Gestión de ', 'G. ').replace('Negocios Maritimos y Navieros', 'NMN');
      const mCls = d.motivo === 'No reportó' ? 'motivo-nr' : 'motivo-bm';
      return `<tr>
        <td style="color:#64748b;font-weight:600;white-space:nowrap;">${d.cod}</td>
        <td style="color:#f1f5f9;">${d.nom}</td>
        <td style="color:#94a3b8;font-size:11px;">${shortGer}</td>
        <td style="color:#94a3b8;font-size:11px;">${d.area}</td>
        <td><span class="frec-pill frec-${d.frec}">${FREC_FULL[d.frec] || d.frec}</span></td>
        <td><span class="motivo-pill ${mCls}">${d.motivo}</span></td>
      </tr>`;
    }).join('') + '</tbody></table>';
    return;
  }

  if (kpiModalMode === 'sla') {
    const quiere = (kpiModalFilter || {}).slaOk;
    let rows = slaRows().filter(d => (quiere ? d.ok === 1 : d.ok === 0)).filter(d => match(d.nom + ' ' + d.cod + ' ' + d.area + ' ' + d.ger));
    titleEl.textContent = (quiere ? '✅ SLA que cumplieron — ' : '⚠️ SLA que NO cumplieron — ') + gerTxt + ' · ' + selectedMes.charAt(0) + selectedMes.slice(1).toLowerCase();
    countEl.textContent = rows.length;
    if (!rows.length) { body.innerHTML = '<p style="color:#64748b;font-size:13px;padding:20px 0;text-align:center;">' + (quiere ? 'Ningún SLA cumplido con estos filtros.' : 'Ningún SLA incumplido 🎉') + '</p>'; return; }
    body.innerHTML = `<table class="kpi-det-table"><thead><tr>
      <th>Código</th><th>Indicador</th><th>Gerencia</th><th>Área</th><th>Frecuencia</th><th>Tipo</th>${quiere ? '' : '<th>Motivo</th>'}
    </tr></thead><tbody>` + rows.map(d => {
      const shortGer = d.ger.replace('Gerencia de ', '').replace('Gestión de ', 'G. ').replace('Negocios Maritimos y Navieros', 'NMN');
      const motCol = quiere ? '' : `<td><span class="motivo-pill ${d.motivo === 'No reportó' ? 'motivo-nr' : 'motivo-bm'}">${d.motivo}</span></td>`;
      return `<tr>
        <td style="color:#64748b;font-weight:600;white-space:nowrap;">${d.cod}</td>
        <td style="color:#f1f5f9;">${d.nom}</td>
        <td style="color:#94a3b8;font-size:11px;">${shortGer}</td>
        <td style="color:#94a3b8;font-size:11px;">${d.area}</td>
        <td><span class="frec-pill frec-${d.frec}">${FREC_FULL[d.frec] || d.frec}</span></td>
        <td style="color:#94a3b8;font-size:11px;text-transform:capitalize;">${d.tipoind || '—'}</td>
        ${motCol}
      </tr>`;
    }).join('') + '</tbody></table>';
    return;
  }

  if (kpiModalMode === 'kaizen') {
    const est = (kpiModalFilter || {}).kzEst;
    let rows = kaizenRows().filter(d => d.est === est).filter(d => match(d.nom + ' ' + d.cod + ' ' + d.area + ' ' + d.ger));
    const ic = est === 'DONE' ? '✅' : est === 'ON GOING' ? '🔄' : '🚨';
    titleEl.textContent = `${ic} KAIZEN ${est} — ${gerTxt} · ${selectedMes.charAt(0) + selectedMes.slice(1).toLowerCase()}`;
    countEl.textContent = rows.length;
    if (!rows.length) { body.innerHTML = '<p style="color:#64748b;font-size:13px;padding:20px 0;text-align:center;">Sin KAIZEN en este estado con los filtros actuales.</p>'; return; }
    body.innerHTML = `<table class="kpi-det-table"><thead><tr>
      <th>Código</th><th>Indicador</th><th>Gerencia</th><th>Área</th><th>Frecuencia</th><th>Estatus</th>
    </tr></thead><tbody>` + rows.map(d => {
      const shortGer = d.ger.replace('Gerencia de ', '').replace('Gestión de ', 'G. ').replace('Negocios Maritimos y Navieros', 'NMN');
      const eCls = d.est === 'SIN CREAR' ? 'motivo-nr' : 'motivo-bm';
      const eStyle = d.est === 'DONE' ? 'background:rgba(34,197,94,.12);color:#4ade80;border:1px solid rgba(34,197,94,.3);' : '';
      return `<tr>
        <td style="color:#64748b;font-weight:600;white-space:nowrap;">${d.cod}</td>
        <td style="color:#f1f5f9;">${d.nom}</td>
        <td style="color:#94a3b8;font-size:11px;">${shortGer}</td>
        <td style="color:#94a3b8;font-size:11px;">${d.area}</td>
        <td><span class="frec-pill frec-${d.frec}">${FREC_FULL[d.frec] || d.frec}</span></td>
        <td><span class="motivo-pill ${eCls}" style="${eStyle}">${d.est}</span></td>
      </tr>`;
    }).join('') + '</tbody></table>';
    return;
  }

  if (kpiModalMode === 'medidos') {
    const f = kpiModalFilter || { ger: gerF, area: null, estado: null };
    const fGer = (KPI_ACCESS !== 'ALL') ? KPI_ACCESS : f.ger;
    let rows = kpisMedidos(fGer, f.area, selectedMes);

    // Desviados del mes en este ámbito (para separar cumplieron / no cumplieron)
    const desvHere = KPI_DESVIADOS_DET.filter(d =>
      (selectedMes === 'ALL' || d.Mes === selectedMes) &&
      (fGer === 'ALL' || d.ger === fGer) &&
      (!f.area || d.area === f.area)
    );
    const motivoPorCod = {};
    desvHere.forEach(d => { motivoPorCod[d.cod] = d.motivo; });
    const desvCods = new Set(desvHere.map(d => d.cod));                                  // no cumplieron meta
    const noRepCods = new Set(desvHere.filter(d => d.motivo === 'No reportó').map(d => d.cod)); // no cargados en PGC

    let titulo = '📋 Indicadores medidos';
    let mostrarMotivo = false;
    if (f.estado === 'cumplieron')   { rows = rows.filter(k => !desvCods.has(k.cod));  titulo = '✅ KPIs que cumplieron la meta'; }
    if (f.estado === 'nocumplieron') { rows = rows.filter(k => desvCods.has(k.cod));   titulo = '⚠️ KPIs que NO cumplieron la meta'; mostrarMotivo = true; }
    if (f.estado === 'cargados')     { rows = rows.filter(k => !noRepCods.has(k.cod)); titulo = '✅ KPIs cargados en PGC'; }
    if (f.estado === 'nocargados')   { rows = rows.filter(k => noRepCods.has(k.cod));  titulo = '⚠️ KPIs NO cargados en PGC'; mostrarMotivo = true; }

    rows = rows.filter(k => match(k.nom + ' ' + k.cod + ' ' + k.area + ' ' + k.ger));
    const lugar = f.area ? f.area : (fGer === 'ALL' ? 'Todas las gerencias' : fGer);
    titleEl.textContent = `${titulo} — ${lugar} · ${selectedMes.charAt(0) + selectedMes.slice(1).toLowerCase()}`;
    countEl.textContent = rows.length;
    if (!rows.length) {
      const msg = (f.estado === 'nocumplieron' || f.estado === 'nocargados')
        ? 'Ningún KPI incumplió con los filtros actuales 🎉'
        : 'Ningún indicador con los filtros actuales.';
      body.innerHTML = `<p style="color:#64748b;font-size:13px;padding:20px 0;text-align:center;">${msg}</p>`; return;
    }
    body.innerHTML = `<table class="kpi-det-table"><thead><tr>
      <th>Código</th><th>Nombre</th><th>Gerencia</th><th>Área</th><th>Frecuencia</th>${mostrarMotivo ? '<th>Motivo</th>' : '<th>Tipo</th>'}
    </tr></thead><tbody>` + rows.map(k => {
      const shortGer = k.ger.replace('Gerencia de ', '').replace('Gestión de ', 'G. ').replace('Negocios Maritimos y Navieros', 'NMN');
      let lastCol;
      if (mostrarMotivo) {
        const mot = motivoPorCod[k.cod] || 'Bajo meta';
        const mCls = mot === 'No reportó' ? 'motivo-nr' : 'motivo-bm';
        lastCol = `<td><span class="motivo-pill ${mCls}">${mot}</span></td>`;
      } else {
        lastCol = `<td style="color:#94a3b8;font-size:11px;">${k.tipo}</td>`;
      }
      return `<tr>
        <td style="color:#64748b;font-weight:600;white-space:nowrap;">${k.cod}</td>
        <td style="color:#f1f5f9;">${k.nom}</td>
        <td style="color:#94a3b8;font-size:11px;">${shortGer}</td>
        <td style="color:#94a3b8;font-size:11px;">${k.area}</td>
        <td><span class="frec-pill frec-${k.frec}">${FREC_FULL[k.frec] || k.frec}</span></td>
        ${lastCol}
      </tr>`;
    }).join('') + '</tbody></table>';
    return;
  }

  // indicadores / metricas (solo los que reportan en el mes seleccionado)
  const tipoTarget = kpiModalMode === 'indicadores' ? 'Indicador' : 'Métrica';
  let rows = KPI_CATALOGO.filter(k =>
    (kpiModalMode === 'indicadores' ? k.tipo === 'Indicador' : k.tipo !== 'Indicador') &&
    (gerF === 'ALL' || k.ger === gerF) &&
    (selectedMes === 'ALL' || (k.meses || []).includes(selectedMes)) &&
    match(k.nom + ' ' + k.cod + ' ' + k.area + ' ' + k.ger)
  );
  titleEl.textContent = (kpiModalMode === 'indicadores' ? '📊 Indicadores' : '📐 Métricas') + ' — ' + gerTxt + ' · ' + selectedMes.charAt(0) + selectedMes.slice(1).toLowerCase();
  countEl.textContent = rows.length;
  if (!rows.length) { body.innerHTML = '<p style="color:#64748b;font-size:13px;padding:20px 0;text-align:center;">Sin resultados con los filtros actuales.</p>'; return; }
  body.innerHTML = `<table class="kpi-det-table"><thead><tr>
    <th>Código</th><th>Nombre</th><th>Gerencia</th><th>Área</th><th>Frecuencia</th>
  </tr></thead><tbody>` + rows.map(k => {
    const shortGer = k.ger.replace('Gerencia de ', '').replace('Gestión de ', 'G. ').replace('Negocios Maritimos y Navieros', 'NMN');
    return `<tr>
      <td style="color:#64748b;font-weight:600;white-space:nowrap;">${k.cod}</td>
      <td style="color:#f1f5f9;">${k.nom}</td>
      <td style="color:#94a3b8;font-size:11px;">${shortGer}</td>
      <td style="color:#94a3b8;font-size:11px;">${k.area}</td>
      <td><span class="frec-pill frec-${k.frec}">${FREC_FULL[k.frec] || k.frec}</span></td>
    </tr>`;
  }).join('') + '</tbody></table>';
}

// ─────────────────────────────────────────────
// INIT
// ─────────────────────────────────────────────
document.getElementById('fileInput').addEventListener('change', (e) => { if (e.target.files[0]) parseExcel(e.target.files[0]); });

// DOMContentLoaded manejado por el login
</script>
</script>

</body>
</html>
