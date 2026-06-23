# DalveenLeandor.github.io
Web
index.html
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no"/>
<meta name="theme-color" content="#07080f"/>
<meta name="apple-mobile-web-app-capable" content="yes"/>
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent"/>
<meta name="apple-mobile-web-app-title" content="Precio Luz"/>
<title>⚡ Precio Luz PVPC</title>
<style>
  *{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent}
  :root{
    --bg:#07080f;--card:#0d0e1e;--card2:#0a0b18;
    --border:#12142a;--border2:#1a1e30;
    --txt:#dde3ef;--txt2:#8899bb;--txt3:#3d4566;--txt4:#272d50;
    --punta:#ff4560;--llano:#ffc300;--valle:#00e396;
    --punta-bg:#180508;--llano-bg:#161200;--valle-bg:#021510;
    --font:-apple-system,BlinkMacSystemFont,'Inter',system-ui,sans-serif;
    --mono:'SF Mono','Fira Code','Courier New',monospace;
  }
  html,body{background:var(--bg);color:var(--txt);font-family:var(--font);min-height:100dvh;overscroll-behavior:none}
  body{max-width:480px;margin:0 auto;padding-bottom:env(safe-area-inset-bottom,24px)}

  /* ── HEADER ── */
  .header{display:flex;justify-content:space-between;align-items:center;padding:14px 16px 12px;border-bottom:1px solid var(--border)}
  .header-left h1{font-size:18px;font-weight:800;letter-spacing:-0.4px;color:#f0f4ff}
  .header-left p{font-size:9px;color:var(--txt4);letter-spacing:2.5px;margin-top:2px}
  .clock{text-align:right}
  .clock-time{font-size:26px;font-weight:700;font-family:var(--mono);line-height:1;letter-spacing:-1px}
  .clock-label{font-size:9px;color:var(--txt4);letter-spacing:1px;margin-top:2px}

  /* ── HERO ── */
  .hero{margin:12px 14px 0;padding:16px 18px 14px;background:var(--card);border-radius:14px;border:1px solid transparent;transition:border-color .3s,box-shadow .3s}
  .hero-top{display:flex;justify-content:space-between;align-items:flex-start}
  .hero-label{font-size:10px;color:var(--txt4);letter-spacing:2px;margin-bottom:8px}
  .hero-price{display:flex;align-items:baseline;gap:7px}
  .hero-price-num{font-size:44px;font-weight:800;font-family:var(--mono);letter-spacing:-2px;line-height:1}
  .hero-price-unit{font-size:16px;color:var(--txt3)}
  .badge{padding:5px 13px;border-radius:20px;font-size:11px;font-weight:800;letter-spacing:1.5px;border:1px solid transparent;margin-top:4px;flex-shrink:0}
  .hero-footer{display:flex;margin-top:12px;padding-top:11px;border-top:1px solid var(--border);font-size:11px}
  .hero-foot-item{flex:1}
  .hero-foot-item:last-child{text-align:right}
  .hero-foot-item .flabel{font-size:9px;color:var(--txt4);letter-spacing:1.5px;margin-bottom:3px}
  .hero-foot-item .fval{font-family:var(--mono);font-weight:700}

  /* ── TABS ── */
  .tabs{display:flex;margin:10px 14px 8px;background:var(--card);border-radius:11px;padding:3px;gap:2px}
  .tab{flex:1;padding:9px 6px;border-radius:9px;border:none;cursor:pointer;background:transparent;color:var(--txt3);font-size:11px;font-weight:700;letter-spacing:1px;transition:all .15s;font-family:var(--font)}
  .tab.active{background:var(--card2);color:#f0f4ff;box-shadow:0 1px 8px #00000040}

  /* ── STATS ── */
  .stats{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px;margin:0 14px 8px}
  .stat{background:var(--card);border-radius:10px;padding:10px 8px;text-align:center;border:1px solid transparent}
  .stat-label{font-size:9px;color:var(--txt4);letter-spacing:1.5px;margin-bottom:4px}
  .stat-val{font-size:15px;font-weight:700;font-family:var(--mono)}
  .stat-unit{font-size:9px;color:var(--border2);margin-top:2px}

  /* ── CHART ── */
  .chart-wrap{margin:0 14px 8px;background:var(--card);border-radius:10px;border:1px solid var(--border);padding:12px 10px 6px}
  .chart-title{font-size:9px;color:var(--txt4);letter-spacing:2px;margin-bottom:8px}
  .chart{display:flex;align-items:flex-end;gap:2px;height:60px}
  .bar-col{flex:1;display:flex;flex-direction:column;align-items:center;gap:3px}
  .bar{width:100%;border-radius:2px 2px 0 0;min-height:2px;transition:height .4s ease}
  .bar-lbl{font-size:7px;color:var(--txt4)}

  /* ── LEGEND ── */
  .legend{display:flex;justify-content:center;gap:16px;margin:0 14px 6px;font-size:10px;color:var(--txt3)}
  .legend-item{display:flex;align-items:center;gap:5px}
  .legend-dot{width:7px;height:7px;border-radius:2px}

  /* ── TABLE ── */
  .table-wrap{margin:0 14px;border-radius:12px;overflow:hidden;border:1px solid var(--border)}
  .table-head{display:grid;grid-template-columns:52px 64px 20px 1fr 74px;padding:7px 14px;background:var(--card2);font-size:9px;color:var(--txt4);letter-spacing:1.5px;border-bottom:1px solid var(--border)}
  .row{display:grid;grid-template-columns:52px 64px 20px 1fr 74px;align-items:center;padding:8px 14px;border-bottom:1px solid var(--card2);transition:background .15s}
  .row.current{box-shadow:inset 3px 0 0 currentColor}
  .row-hour{font-family:var(--mono);font-size:13px;color:var(--txt2)}
  .row-hour.cur{color:#f0f4ff;font-weight:700}
  .period-badge{display:flex;align-items:center;gap:5px}
  .period-dot{width:6px;height:6px;border-radius:50%;flex-shrink:0}
  .period-name{font-size:9px;font-weight:800;letter-spacing:.5px}
  .bar-h{height:2px;background:var(--border);border-radius:2px;overflow:hidden;width:100%}
  .bar-h-fill{height:100%;border-radius:2px;opacity:.65}
  .row-price{text-align:right;font-family:var(--mono);font-size:13px;color:inherit}
  .row-price.cur{font-size:15px;font-weight:700;color:#f0f4ff}

  /* ── ESTADOS ── */
  .loading,.error,.no-data{padding:50px 20px;text-align:center;color:var(--txt4)}
  .loading-icon{font-size:28px;margin-bottom:10px;animation:pulse 1.2s ease-in-out infinite}
  .loading-txt{font-size:11px;letter-spacing:2.5px}
  .error-title{color:var(--punta);font-weight:700;margin-bottom:6px}
  .error-body{color:var(--txt3);font-size:12px;line-height:1.7}
  @keyframes pulse{0%,100%{opacity:.4}50%{opacity:1}}

  /* ── FOOTER ── */
  .footer{padding:14px 16px 0;font-size:9px;color:var(--txt4);text-align:center;line-height:2}
  .install-tip{display:none;margin:8px 14px;padding:10px 14px;background:var(--card);border:1px solid var(--border2);border-radius:10px;font-size:11px;color:var(--txt3);line-height:1.6}
  .install-tip.visible{display:block}
  .install-tip strong{color:var(--txt2)}
</style>
</head>
<body>

<!-- HEADER -->
<div class="header">
  <div class="header-left">
    <h1>⚡ Precio Luz</h1>
    <p>PVPC · BONO SOCIAL · ESPAÑA</p>
  </div>
  <div class="clock">
    <div class="clock-time" id="clock">--:--</div>
    <div class="clock-label">HORA ESPAÑA</div>
  </div>
</div>

<!-- HERO (solo tab HOY) -->
<div class="hero" id="hero" style="display:none">
  <div class="hero-top">
    <div>
      <div class="hero-label" id="hero-label">AHORA · --:-- – --:--</div>
      <div class="hero-price">
        <span class="hero-price-num" id="hero-price">--</span>
        <span class="hero-price-unit">€/kWh</span>
      </div>
    </div>
    <div class="badge" id="hero-badge">--</div>
  </div>
  <div class="hero-footer">
    <div class="hero-foot-item">
      <div class="flabel">HORA MÁS BARATA</div>
      <div class="fval" id="hero-cheap" style="color:var(--valle)">--</div>
    </div>
    <div class="hero-foot-item">
      <div class="flabel">HORA MÁS CARA</div>
      <div class="fval" id="hero-exp" style="color:var(--punta)">--</div>
    </div>
  </div>
</div>

<!-- TABS -->
<div class="tabs">
  <button class="tab active" id="tab-hoy" onclick="switchTab('hoy')">HOY</button>
  <button class="tab" id="tab-manana" onclick="switchTab('manana')">MAÑANA</button>
</div>

<!-- INSTALL TIP -->
<div class="install-tip" id="install-tip">
  📱 <strong>Añadir al escritorio:</strong> iOS Safari → Compartir → "Añadir a pantalla de inicio" · Android Chrome → Menú ⋮ → "Añadir a pantalla de inicio"
</div>

<!-- CONTENIDO -->
<div id="content-hoy">
  <div class="loading" id="loading-hoy"><div class="loading-icon">⚡</div><div class="loading-txt">CARGANDO PRECIOS...</div></div>
  <div id="data-hoy" style="display:none">
    <div class="stats" id="stats-hoy"></div>
    <div class="chart-wrap"><div class="chart-title">CURVA DEL DÍA</div><div class="chart" id="chart-hoy"></div></div>
    <div class="legend"><div class="legend-item"><div class="legend-dot" style="background:var(--valle)"></div>VALLE</div><div class="legend-item"><div class="legend-dot" style="background:var(--llano)"></div>LLANO</div><div class="legend-item"><div class="legend-dot" style="background:var(--punta)"></div>PUNTA</div></div>
    <div class="table-wrap">
      <div class="table-head"><span>HORA</span><span>PERIODO</span><span></span><span></span><span style="text-align:right">€/kWh</span></div>
      <div id="rows-hoy"></div>
    </div>
  </div>
  <div class="error" id="error-hoy" style="display:none"><div class="error-title">Sin conexión</div><div class="error-body">No se pudo cargar el precio de la luz.<br/>Comprueba tu conexión e inténtalo de nuevo.</div></div>
</div>

<div id="content-manana" style="display:none">
  <div class="loading" id="loading-man"><div class="loading-icon">⚡</div><div class="loading-txt">CARGANDO PRECIOS...</div></div>
  <div id="data-man" style="display:none">
    <div class="stats" id="stats-man"></div>
    <div class="chart-wrap"><div class="chart-title">CURVA DEL DÍA</div><div class="chart" id="chart-man"></div></div>
    <div class="legend"><div class="legend-item"><div class="legend-dot" style="background:var(--valle)"></div>VALLE</div><div class="legend-item"><div class="legend-dot" style="background:var(--llano)"></div>LLANO</div><div class="legend-item"><div class="legend-dot" style="background:var(--punta)"></div>PUNTA</div></div>
    <div class="table-wrap">
      <div class="table-head"><span>HORA</span><span>PERIODO</span><span></span><span></span><span style="text-align:right">€/kWh</span></div>
      <div id="rows-man"></div>
    </div>
  </div>
  <div class="no-data" id="nodata-man" style="display:none">
    <div style="font-size:28px;margin-bottom:10px">🕐</div>
    <div style="font-weight:700;color:var(--llano);margin-bottom:8px">Precios no disponibles aún</div>
    <div style="font-size:12px;color:var(--txt3);line-height:1.8">Los precios de mañana se publican<br/>cada día alrededor de las <strong style="color:var(--txt2)">20:15h</strong>.<br/>Vuelve esta noche.</div>
  </div>
  <div class="error" id="error-man" style="display:none"><div class="error-title">Sin conexión</div><div class="error-body">No se pudo cargar el precio de la luz.<br/>Comprueba tu conexión e inténtalo de nuevo.</div></div>
</div>

<!-- FOOTER -->
<div class="footer">
  Precios en €/kWh · Sin IVA (21%) ni impuesto eléctrico (5,11%)<br/>
  PVPC 2.0TD · Fuente: preciodelaluz.org / REE · Festivos estatales 2026<br/>
  Periodos válidos para Península · Mañana disponible tras las 20:15h
</div>

<script>
// ── CONFIG ─────────────────────────────────────────────────────────────
const FESTIVOS = new Set(['01-01','01-06','04-03','04-06','05-01','08-15','10-12','11-01','12-06','12-08','12-25']);
const PC = {
  punta: { name:'PUNTA', color:'#ff4560', bg:'#180508', dim:'#ff456025' },
  llano: { name:'LLANO', color:'#ffc300', bg:'#161200', dim:'#ffc30025' },
  valle: { name:'VALLE', color:'#00e396', bg:'#021510', dim:'#00e39625' },
};

// ── HORA ESPAÑA ──────────────────────────────────────────────────────
function spainNow() {
  const n = new Date();
  const jan = new Date(n.getFullYear(),0,1).getTimezoneOffset();
  const jul = new Date(n.getFullYear(),6,1).getTimezoneOffset();
  const isDST = n.getTimezoneOffset() < Math.max(jan,jul);
  return new Date(n.getTime() + ((isDST?2:1)*60 + n.getTimezoneOffset())*60000);
}

function getPeriod(h, dateObj) {
  const day = dateObj.getDay();
  const mmdd = `${String(dateObj.getMonth()+1).padStart(2,'0')}-${String(dateObj.getDate()).padStart(2,'0')}`;
  if (day===0||day===6||FESTIVOS.has(mmdd)) return 'valle';
  if ((h>=10&&h<14)||(h>=18&&h<22)) return 'punta';
  if (h<8) return 'valle';
  return 'llano';
}

function fmtDate(d) {
  return d.toLocaleDateString('es-ES',{weekday:'short',day:'numeric',month:'short'}).replace(',','·').toUpperCase();
}

function eur(mwh) { return (mwh/1000).toFixed(4); }

// ── ESTADO ───────────────────────────────────────────────────────────
let hoyData=null, manData=null;
let activeTab='hoy';

// ── RELOJ ────────────────────────────────────────────────────────────
let colonOn = true;
function tickClock() {
  const n = spainNow();
  const h = String(n.getHours()).padStart(2,'0');
  const m = String(n.getMinutes()).padStart(2,'0');
  const c = colonOn ? ':' : '<span style="opacity:.15">:</span>';
  document.getElementById('clock').innerHTML = `${h}${c}${m}`;
  document.getElementById('clock').style.color = hoyData
    ? PC[getPeriod(n.getHours(), n)].color
    : '#dde3ef';
  colonOn = !colonOn;
}
setInterval(tickClock, 900);
tickClock();

// ── TABS ─────────────────────────────────────────────────────────────
function switchTab(t) {
  activeTab = t;
  document.getElementById('tab-hoy').className = 'tab'+(t==='hoy'?' active':'');
  document.getElementById('tab-manana').className = 'tab'+(t==='manana'?' active':'');
  document.getElementById('content-hoy').style.display = t==='hoy'?'block':'none';
  document.getElementById('content-manana').style.display = t==='manana'?'block':'none';
  document.getElementById('hero').style.display = t==='hoy'&&hoyData?'block':'none';
}

// ── PARSEAR API ───────────────────────────────────────────────────────
function parseApi(raw, refDate) {
  const entries = Object.entries(raw);
  if (!entries.length) return null;
  return entries.map(([key, val]) => {
    const h = parseInt(key.split(' ')[1], 10);
    return {
      hour: h,
      price: val.price,
      period: getPeriod(h, refDate),
      cheap: val['is-cheap'],
    };
  }).sort((a,b) => a.hour - b.hour);
}

// ── RENDER HERO ───────────────────────────────────────────────────────
function renderHero(data) {
  const now = spainNow();
  const ch = now.getHours();
  const cur = data.find(d => d.hour === ch) || data[ch] || data[0];
  if (!cur) return;
  const p = PC[cur.period];
  const hero = document.getElementById('hero');
  hero.style.borderColor = p.color+'35';
  hero.style.boxShadow = `0 4px 40px ${p.dim}`;
  hero.style.display = 'block';
  document.getElementById('hero-label').textContent = `AHORA · ${String(ch).padStart(2,'0')}:00 – ${String(ch+1).padStart(2,'00')}:00`;
  document.getElementById('hero-price').textContent = eur(cur.price);
  document.getElementById('hero-price').style.color = p.color;
  const badge = document.getElementById('hero-badge');
  badge.textContent = p.name;
  badge.style.color = p.color;
  badge.style.borderColor = p.color+'55';
  badge.style.background = `${p.color}18`;
  const cheap = data.reduce((a,b) => a.price<b.price?a:b);
  const exp   = data.reduce((a,b) => a.price>b.price?a:b);
  document.getElementById('hero-cheap').textContent = `${String(cheap.hour).padStart(2,'0')}:00 · ${eur(cheap.price)} €`;
  document.getElementById('hero-exp').textContent   = `${eur(exp.price)} € · ${String(exp.hour).padStart(2,'0')}:00`;
}

// ── RENDER STATS ──────────────────────────────────────────────────────
function renderStats(data, id) {
  const min = Math.min(...data.map(d=>d.price));
  const max = Math.max(...data.map(d=>d.price));
  const avg = data.reduce((s,d)=>s+d.price,0)/data.length;
  document.getElementById(id).innerHTML = [
    ['↓ MÍN', min, '#00e396'],
    ['≈ MEDIA', avg, '#ffc300'],
    ['↑ MÁX', max, '#ff4560'],
  ].map(([l,v,c]) => `
    <div class="stat" style="border-color:${c}20">
      <div class="stat-label">${l}</div>
      <div class="stat-val" style="color:${c}">${eur(v)}</div>
      <div class="stat-unit">€/kWh</div>
    </div>`).join('');
}

// ── RENDER CHART ──────────────────────────────────────────────────────
function renderChart(data, id, currentHour) {
  const max = Math.max(...data.map(d=>d.price));
  const min = Math.min(...data.map(d=>d.price));
  const range = max - min || 1;
  // show every 4th label (0,4,8,12,16,20,23)
  const showLabels = new Set([0,4,8,12,16,20,23]);
  document.getElementById(id).innerHTML = data.map(d => {
    const pct = Math.max(8, ((d.price-min)/range)*100);
    const p = PC[d.period];
    const isCur = d.hour === currentHour;
    return `<div class="bar-col">
      <div class="bar" style="height:${pct}%;background:${p.color};opacity:${isCur?1:.5};${isCur?'box-shadow:0 0 8px '+p.color:''}"></div>
      <div class="bar-lbl">${showLabels.has(d.hour)?d.hour+'h':''}</div>
    </div>`;
  }).join('');
}

// ── RENDER ROWS ───────────────────────────────────────────────────────
function renderRows(data, id, currentHour) {
  const max = Math.max(...data.map(d=>d.price));
  const min = Math.min(...data.map(d=>d.price));
  const range = max-min||1;
  document.getElementById(id).innerHTML = data.map((d,i) => {
    const p = PC[d.period];
    const isCur = d.hour === currentHour;
    const pct = ((d.price-min)/range)*100;
    const bg = isCur ? p.bg : (i%2===0?'#09091a':'#07080f');
    return `<div class="row ${isCur?'current':''}" style="background:${bg};color:${p.color}">
      <div class="row-hour ${isCur?'cur':''}">${String(d.hour).padStart(2,'0')}:00${isCur?'<span style="font-size:8px;margin-left:2px">◀</span>':''}</div>
      <div class="period-badge">
        <div class="period-dot" style="background:${p.color};${isCur?'box-shadow:0 0 8px '+p.color:''}"></div>
        <div class="period-name" style="color:${p.color}">${p.name}</div>
      </div>
      <div></div>
      <div class="bar-h"><div class="bar-h-fill" style="width:${pct}%;background:${p.color}"></div></div>
      <div class="row-price ${isCur?'cur':''}" style="${isCur?'':'color:'+p.color}">${eur(d.price)}</div>
    </div>`;
  }).join('');
}

// ── RENDER DAY ────────────────────────────────────────────────────────
function renderDay(data, prefix, currentHour) {
  const statsId  = prefix==='hoy'?'stats-hoy':'stats-man';
  const chartId  = prefix==='hoy'?'chart-hoy':'chart-man';
  const rowsId   = prefix==='hoy'?'rows-hoy':'rows-man';
  const dataEl   = document.getElementById(prefix==='hoy'?'data-hoy':'data-man');
  renderStats(data, statsId);
  renderChart(data, chartId, prefix==='hoy'?currentHour:-1);
  renderRows(data, rowsId, prefix==='hoy'?currentHour:-1);
  dataEl.style.display = 'block';
}

// ── FETCH CON FALLBACK CORS ───────────────────────────────────────────
// Cuando se abre como file:// el navegador bloquea fetch directo.
// Si falla, reintenta automáticamente por proxy CORS público.

const API_BASE = 'https://api.preciodelaluz.org/v1/prices/all?zone=PCB';
const PROXIES  = [
  url => `https://api.allorigins.win/raw?url=${encodeURIComponent(url)}`,
  url => `https://corsproxy.io/?${encodeURIComponent(url)}`,
];

async function apiFetch(url) {
  // 1️⃣ Intento directo
  try {
    const r = await fetch(url, { signal: AbortSignal.timeout(6000) });
    if (r.ok) { const j = await r.json(); if (Object.keys(j).length) return j; }
  } catch(_) {}

  // 2️⃣ Fallback: proxies en orden
  for (const proxy of PROXIES) {
    try {
      const r = await fetch(proxy(url), { signal: AbortSignal.timeout(8000) });
      if (!r.ok) continue;
      const text = await r.text();
      const j = JSON.parse(text);
      if (Object.keys(j).length) return j;
    } catch(_) {}
  }

  throw new Error('Sin respuesta de ninguna fuente');
}

async function fetchHoy() {
  const loadEl = document.getElementById('loading-hoy');
  const errEl  = document.getElementById('error-hoy');
  loadEl.style.display = 'block';
  errEl.style.display  = 'none';
  try {
    const raw = await apiFetch(API_BASE);
    const now = spainNow();
    const data = parseApi(raw, now);
    if (!data) throw new Error('Sin datos');
    hoyData = data;
    loadEl.style.display = 'none';
    document.getElementById('tab-hoy').textContent = fmtDate(now);
    renderHero(data);
   
