[bund_treasuries_proWWWWWWWWWWW.html](https://github.com/user-attachments/files/26236759/bund_treasuries_proWWWWWWWWWWW.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bund vs Treasuries · Estrategia Macro 2026</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&family=Syne:wght@400;500;600;700;800&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js"></script>
<style>
:root {
  --bg:      #FFFFFF;
  --bg2:     #F5F7FA;
  --bg3:     #EEF1F6;
  --surface: #F0F4F8;
  --border:  rgba(0,0,0,0.11);
  --gold:    #8A6A10;
  --gold2:   #B8902A;
  --gold-dim: rgba(138,106,16,0.10);
  --white:   #000000;
  --dim:     #111111;
  --muted:   #333333;
  --red:     #B01E1E;
  --red-dim: rgba(176,30,30,0.09);
  --green:   #0F6B38;
  --green-dim: rgba(15,107,56,0.09);
  --blue:    #1558A0;
  --blue-dim: rgba(21,88,160,0.09);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;font-size:16px}
body{font-family:'Syne',sans-serif;background:var(--bg);color:var(--white);overflow-x:hidden;cursor:none}

.cursor{width:8px;height:8px;background:var(--gold);border-radius:50%;position:fixed;top:0;left:0;pointer-events:none;z-index:9999;transition:transform .15s ease;mix-blend-mode:difference}
.cursor-ring{width:36px;height:36px;border:1px solid rgba(201,168,76,.4);border-radius:50%;position:fixed;top:0;left:0;pointer-events:none;z-index:9998;transition:transform .4s ease}
#progress{position:fixed;top:0;left:0;height:2px;background:linear-gradient(90deg,var(--gold),var(--gold2));z-index:200;width:0%;transition:width .1s linear}

nav{position:fixed;top:0;left:0;right:0;z-index:100;display:flex;align-items:center;justify-content:space-between;padding:0 64px;height:64px;background:rgba(255,255,255,.96);backdrop-filter:blur(20px);border-bottom:1px solid var(--border);box-shadow:0 1px 12px rgba(0,0,0,.06)}
.nav-logo{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--gold);font-weight:700;letter-spacing:.2em;text-transform:uppercase}
.nav-items{display:flex;gap:0;list-style:none}
.nav-items a{font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:.12em;text-transform:uppercase;color:#000;font-weight:700;text-decoration:none;padding:8px 16px;transition:color .2s;position:relative}
.nav-items a::after{content:'';position:absolute;bottom:0;left:16px;right:16px;height:1px;background:var(--gold);transform:scaleX(0);transition:transform .2s}
.nav-items a:hover{color:var(--gold)}
.nav-items a:hover::after{transform:scaleX(1)}
.nav-cta{font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:.12em;color:var(--gold);border:1px solid rgba(201,168,76,.4);padding:8px 20px;text-transform:uppercase;cursor:none;display:flex;align-items:center;gap:8px;background:rgba(201,168,76,.05)}
.nav-cta .bme-icon{width:18px;height:18px;background:var(--gold);border-radius:2px;display:flex;align-items:center;justify-content:center;font-size:9px;color:var(--bg);font-weight:800;font-family:'Syne',sans-serif;flex-shrink:0}

section{min-height:100vh;display:flex;flex-direction:column;justify-content:center;padding:120px 96px 80px;position:relative;overflow:hidden}
section+section{border-top:1px solid var(--border)}
.sec-num{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--gold);letter-spacing:.25em;text-transform:uppercase;margin-bottom:20px;display:flex;align-items:center;gap:16px}
.sec-num::before{content:'';width:32px;height:1px;background:var(--gold)}
.sec-title{font-family:'Cormorant Garamond',serif;font-size:clamp(40px,5vw,68px);font-weight:300;color:var(--white);line-height:1.05;margin-bottom:16px;letter-spacing:-.01em}
.sec-title em{font-style:italic;color:var(--gold)}
.sec-lead{font-size:15px;font-weight:600;color:#111;max-width:600px;line-height:1.75;margin-bottom:48px}

/* HERO */
#hero{background:var(--bg);min-height:100vh;padding:0 96px;justify-content:center;align-items:center}
.hero-noise{position:absolute;inset:0;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");opacity:.4}
.hero-glow{position:absolute;width:700px;height:700px;border-radius:50%;background:radial-gradient(circle,rgba(184,144,42,.08) 0%,transparent 70%);top:50%;left:50%;transform:translate(-50%,-50%);pointer-events:none}
.hero-inner{position:relative;z-index:1;max-width:860px;width:100%;text-align:center}
.hero-eyebrow{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--gold);letter-spacing:.25em;text-transform:uppercase;margin-bottom:32px;opacity:0;animation:fadeUp .8s .2s forwards}
.hero-h1{font-family:'Cormorant Garamond',serif;font-size:clamp(56px,8vw,108px);font-weight:300;line-height:.95;letter-spacing:-.02em;margin-bottom:40px;opacity:0;animation:fadeUp .9s .4s forwards}
.hero-h1 span{display:block}
.hero-h1 .accent{font-style:italic;color:var(--gold)}
.hero-h1 .vs-word{font-size:.45em;color:var(--muted);font-style:normal;letter-spacing:.1em}
.hero-desc{font-size:16px;color:var(--dim);max-width:560px;line-height:1.7;margin:0 auto 56px;font-weight:300;opacity:0;animation:fadeUp 1s .6s forwards}
.hero-meta{display:flex;gap:48px;flex-wrap:wrap;justify-content:center;border-top:1px solid var(--border);padding-top:32px;opacity:0;animation:fadeUp 1s .8s forwards}
.hmi-label{font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--muted);letter-spacing:.2em;text-transform:uppercase;margin-bottom:4px;text-align:center}
.hmi-val{font-size:13px;font-weight:500;color:var(--white);text-align:center}
.scroll-ind{position:absolute;bottom:40px;left:50%;transform:translateX(-50%);display:flex;align-items:center;gap:14px;opacity:0;animation:fadeIn 1s 1.5s forwards}
.scroll-ind span{font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--muted);letter-spacing:.2em;text-transform:uppercase}
.scroll-line{width:1px;height:40px;background:linear-gradient(to bottom,transparent,var(--gold));animation:scrollPulse 1.5s ease-in-out infinite}
@keyframes scrollPulse{0%,100%{opacity:.3}50%{opacity:1}}

/* MACRO */
.macro-grid{display:grid;grid-template-columns:1fr 1fr;gap:2px;margin-bottom:2px}
.macro-panel{background:var(--surface);padding:36px;border:1px solid var(--border);position:relative;overflow:hidden;transition:border-color .3s}
.macro-panel:hover{border-color:rgba(201,168,76,.3)}
.macro-panel::before{content:'';position:absolute;top:0;left:0;right:0;height:2px}
.macro-panel.eu::before{background:var(--red)}
.macro-panel.us::before{background:var(--green)}
.mp-flag{font-size:28px;margin-bottom:8px;display:block}
.mp-title{font-size:11px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:#000;margin-bottom:24px}
.mp-points{list-style:none;display:flex;flex-direction:column;gap:10px}
.mp-points li{display:flex;gap:12px;font-size:13.5px;color:#000;font-weight:500;line-height:1.5}
.mp-points li::before{content:'—';color:var(--gold);flex-shrink:0;font-size:12px;margin-top:2px}
.mp-verdict{margin-top:24px;padding:14px 18px;font-family:'Cormorant Garamond',serif;font-size:15px;font-style:italic;font-weight:600;line-height:1.5}
.mp-verdict.eu{background:var(--red-dim);color:var(--red);border-left:2px solid var(--red)}
.mp-verdict.us{background:var(--green-dim);color:var(--green);border-left:2px solid var(--green)}
.macro-impl{margin-top:20px;display:flex;flex-direction:column;gap:0}
.mi-row{display:flex;border-top:1px solid var(--border);padding:8px 0}
.mi-key{font-family:'JetBrains Mono',monospace;font-size:9px;color:#000;font-weight:700;letter-spacing:.12em;text-transform:uppercase;width:120px;flex-shrink:0;padding-top:2px}
.mi-val{font-size:12px;font-weight:700;color:#000}
.mi-val.red{color:var(--red)}
.mi-val.green{color:var(--green)}

.escenario-box{display:grid;grid-template-columns:1fr 1fr;gap:2px;margin-top:2px}
.esc-panel{padding:28px;border:1px solid var(--border);background:var(--surface);position:relative;overflow:hidden}
.esc-panel::before{content:'';position:absolute;top:0;left:0;right:0;height:2px}
.esc-panel.base-eu::before{background:var(--red)}
.esc-panel.base-us::before{background:var(--green)}
.esc-title{font-family:'JetBrains Mono',monospace;font-size:9px;letter-spacing:.18em;text-transform:uppercase;margin-bottom:20px;color:var(--muted)}
.esc-tir-row{display:flex;align-items:center;gap:16px;margin-bottom:10px}
.esc-tir-label{font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--muted);letter-spacing:.1em;width:80px;flex-shrink:0}
.esc-tir-val{font-family:'Cormorant Garamond',serif;font-size:36px;font-weight:600;line-height:1}
.esc-tir-val.red{color:var(--red)}
.esc-tir-val.green{color:var(--green)}
.esc-body{font-size:12.5px;color:var(--dim);line-height:1.65;margin-top:12px}
.esc-body strong{color:var(--white);font-weight:500}

.divergence-bar{background:linear-gradient(135deg,var(--gold-dim),rgba(201,168,76,.06));border:1px solid rgba(201,168,76,.25);padding:20px 28px;display:flex;align-items:center;gap:16px;margin-top:2px}
.db-icon{font-size:20px}
.db-text{font-family:'Cormorant Garamond',serif;font-size:17px;font-style:italic;color:var(--gold2);line-height:1.4}

/* KPI */
.kpi-row{display:grid;grid-template-columns:repeat(4,1fr);gap:2px;margin:40px 0}
.kpi{background:var(--surface);padding:28px 24px;border:1px solid var(--border);position:relative;overflow:hidden;transition:transform .25s,border-color .25s}
.kpi:hover{transform:translateY(-4px);border-color:rgba(201,168,76,.3)}
.kpi-tag{font-family:'JetBrains Mono',monospace;font-size:9px;color:#000;font-weight:700;letter-spacing:.15em;text-transform:uppercase;margin-bottom:10px}
.kpi-val{font-family:'Cormorant Garamond',serif;font-size:38px;font-weight:600;line-height:1;margin-bottom:4px}
.kpi-note{font-size:11px;color:#222;font-weight:600}
.kpi.k-red .kpi-val{color:var(--red)}
.kpi.k-green .kpi-val{color:var(--green)}
.kpi.k-gold .kpi-val{color:var(--gold)}
.kpi.k-blue .kpi-val{color:var(--blue)}
.kpi::after{content:'';position:absolute;top:0;left:0;right:0;height:1px}
.kpi.k-red::after{background:var(--red)}
.kpi.k-green::after{background:var(--green)}
.kpi.k-gold::after{background:var(--gold)}
.kpi.k-blue::after{background:var(--blue)}

/* DATA TABLES */
.data-grid{display:grid;grid-template-columns:1fr 1fr;gap:32px}
.data-block-title{font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);margin-bottom:16px;padding-bottom:12px;border-bottom:1px solid var(--border)}
.dt{width:100%;border-collapse:collapse;font-size:13px}
.dt th{background:rgba(0,0,0,.05);padding:9px 14px;text-align:center;font-family:'JetBrains Mono',monospace;font-size:9px;letter-spacing:.12em;text-transform:uppercase;color:#000;font-weight:700}
.dt th:first-child{text-align:left}
.dt td{padding:9px 14px;border-bottom:1px solid var(--border);color:#000;font-family:'JetBrains Mono',monospace;font-size:12px;text-align:center;font-weight:500}
.dt td:first-child{text-align:left;font-family:'Syne',sans-serif;font-size:12px;color:#000;font-weight:700}
.dt .win{color:var(--green);font-weight:500}
.dt .lose{color:var(--red);font-weight:500}
.dt .warn{color:var(--gold);font-weight:500}
.dt tr:last-child td{border-bottom:none}
.stat-block{display:grid;grid-template-columns:1fr 1fr;gap:2px;margin-bottom:16px}
.stat-cell{background:var(--surface);border:1px solid var(--border);padding:20px;text-align:center}
.stat-cell-label{font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--muted);letter-spacing:.15em;text-transform:uppercase;margin-bottom:8px}
.stat-cell-val{font-family:'Cormorant Garamond',serif;font-size:40px;font-weight:600;color:var(--green);line-height:1}

/* STOP LOSS */
.sl-grid{display:grid;grid-template-columns:1.5fr 1fr;gap:32px;align-items:start}
.sl-chart-box{background:var(--surface);border:1px solid var(--border);padding:28px}
.chart-label{font-family:'JetBrains Mono',monospace;font-size:9px;color:#000;font-weight:700;letter-spacing:.12em;text-transform:uppercase;margin-bottom:20px}
.sl-levels{display:flex;flex-direction:column;gap:2px}
.sl-level{display:flex;align-items:center;justify-content:space-between;padding:16px 20px;background:var(--surface);border:1px solid var(--border);transition:border-color .2s}
.sl-level:hover{border-color:rgba(201,168,76,.3)}
.sl-level-label{font-family:'JetBrains Mono',monospace;font-size:10px;color:#000;font-weight:700;letter-spacing:.1em;text-transform:uppercase}
.sl-level-val{font-family:'Cormorant Garamond',serif;font-size:26px;font-weight:600}
.sl-level-val.gold{color:var(--gold)}
.sl-level-val.red{color:var(--red)}
.sl-level-val.dim{color:var(--dim)}
.sl-analysis{margin-top:2px;background:var(--surface);border:1px solid var(--border);border-top:2px solid var(--red);padding:24px}
.sl-analysis-title{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--gold);letter-spacing:.15em;text-transform:uppercase;margin-bottom:14px}
.sl-analysis p{font-size:13px;color:#000;font-weight:500;line-height:1.75}
.sl-analysis p+p{margin-top:10px}
.sl-analysis strong{color:var(--white);font-weight:500}

/* BUND CARRY MINI */
.bund-carry-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:2px;margin-top:32px}
.bund-carry-cell{background:var(--surface);border:1px solid var(--border);padding:18px 16px;text-align:center}
.bund-carry-lbl{font-family:'JetBrains Mono',monospace;font-size:8px;color:var(--muted);letter-spacing:.12em;text-transform:uppercase;margin-bottom:8px}
.bund-carry-val{font-family:'Cormorant Garamond',serif;font-size:26px;font-weight:600;color:var(--green)}
.bund-carry-val.red{color:var(--red)}
.bund-carry-val.gold{color:var(--gold)}

/* ESTRATEGIA */
.estrategia-grid{display:grid;grid-template-columns:1fr 1fr;gap:2px;margin-top:32px}
.estr-panel{background:var(--surface);border:1px solid var(--border);padding:36px;position:relative;overflow:hidden}
.estr-panel::before{content:'';position:absolute;top:0;left:0;right:0;height:2px}
.estr-panel.treasury::before{background:var(--green)}
.estr-panel.bund::before{background:var(--red)}
.estr-weight{font-family:'Cormorant Garamond',serif;font-size:72px;font-weight:600;line-height:1;margin-bottom:4px}
.estr-weight.green{color:var(--green)}
.estr-weight.red{color:var(--red)}
.estr-name{font-family:'JetBrains Mono',monospace;font-size:10px;color:#000;font-weight:700;letter-spacing:.18em;text-transform:uppercase;margin-bottom:20px}
.estr-rows{display:flex;flex-direction:column;gap:0}
.estr-row{display:flex;justify-content:space-between;align-items:center;padding:10px 0;border-top:1px solid var(--border);font-size:12px}
.estr-row-key{color:#000;font-family:'JetBrains Mono',monospace;font-size:9px;font-weight:700;letter-spacing:.1em;text-transform:uppercase}
.estr-row-val{color:var(--white);font-weight:500}
.estr-row-val.green{color:var(--green)}
.estr-row-val.red{color:var(--red)}
.estr-row-val.gold{color:var(--gold)}

.estrategia-resumen{margin-top:2px;background:linear-gradient(135deg,var(--gold-dim),rgba(201,168,76,.04));border:1px solid rgba(201,168,76,.25);padding:24px 32px;display:grid;grid-template-columns:repeat(3,1fr);gap:32px}
.er-label{font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--muted);letter-spacing:.15em;text-transform:uppercase;margin-bottom:6px}
.er-val{font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:600;color:var(--gold);line-height:1}
.er-sub{font-size:11px;color:var(--dim);margin-top:3px}

/* RISK */
.risk-list{display:flex;flex-direction:column;gap:2px}
.risk-item{display:grid;grid-template-columns:64px 1fr auto;background:var(--surface);border:1px solid var(--border);overflow:hidden;transition:border-color .25s,transform .25s}
.risk-item:hover{border-color:rgba(201,168,76,.25);transform:translateX(4px)}
.risk-n{display:flex;align-items:center;justify-content:center;font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:600}
.risk-n.r1{background:rgba(224,82,82,.2);color:var(--red)}
.risk-n.r2{background:rgba(201,168,76,.12);color:var(--gold)}
.risk-n.r3{background:rgba(74,158,204,.1);color:var(--blue)}
.risk-content{padding:20px 24px;border-left:1px solid var(--border)}
.risk-title{font-size:14px;font-weight:600;color:var(--white);margin-bottom:6px}
.risk-desc{font-size:13px;color:#111;font-weight:500;line-height:1.6}
.risk-badge{align-self:center;margin:0 20px;font-family:'JetBrains Mono',monospace;font-size:9px;letter-spacing:.1em;text-transform:uppercase;padding:5px 12px;white-space:nowrap;border:1px solid}
.risk-badge.rb1{color:var(--red);border-color:rgba(224,82,82,.4)}
.risk-badge.rb2{color:var(--gold);border-color:rgba(201,168,76,.4)}
.risk-badge.rb3{color:var(--blue);border-color:rgba(74,158,204,.4)}
.risk-footer{margin-top:24px;padding:18px 24px;border:1px solid rgba(224,82,82,.2);background:var(--red-dim);font-family:'Cormorant Garamond',serif;font-size:16px;font-style:italic;color:rgba(224,82,82,.9);line-height:1.5}

/* CONCLUSION */
#conclusion{background:var(--bg2)}
.conc-quote{border-left:3px solid var(--gold);padding:24px 32px;margin:0 0 48px;background:var(--gold-dim)}
.conc-quote p{font-family:'Cormorant Garamond',serif;font-size:clamp(17px,2.2vw,24px);font-weight:300;font-style:italic;color:var(--white);line-height:1.65}
.conc-pillars{display:grid;grid-template-columns:repeat(3,1fr);gap:2px;margin-bottom:40px}
.cp{background:var(--surface);border:1px solid var(--border);border-top:2px solid var(--gold);padding:28px;transition:transform .2s}
.cp:hover{transform:translateY(-4px)}
.cp-title{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--gold);letter-spacing:.15em;text-transform:uppercase;margin-bottom:14px}
.cp-body{font-size:13px;color:#111;font-weight:500;line-height:1.75}
.cp-body strong{color:var(--white);font-weight:500}
.conc-tags{display:flex;gap:2px;flex-wrap:wrap}
.ctag{padding:12px 24px;font-family:'JetBrains Mono',monospace;font-size:10px;letter-spacing:.1em;text-transform:uppercase;font-weight:500;color:var(--white)}
.ctag.red{background:rgba(224,82,82,.2);border:1px solid rgba(224,82,82,.3)}
.ctag.green{background:rgba(61,187,127,.15);border:1px solid rgba(61,187,127,.3)}
.ctag.gold{background:var(--gold-dim);border:1px solid rgba(201,168,76,.3);color:var(--gold)}

/* FOOTER */
footer{background:var(--bg);border-top:1px solid var(--border);padding:48px 96px;display:flex;justify-content:space-between;align-items:flex-end}
.footer-brand{font-family:'Cormorant Garamond',serif;font-size:22px;font-style:italic;color:var(--gold);margin-bottom:6px}
.footer-sub{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--muted);letter-spacing:.12em}
.footer-authors{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--dim);line-height:1.8;text-align:right;letter-spacing:.06em}

/* CHART */
.chart-legend{display:flex;gap:20px;flex-wrap:wrap;margin-top:14px}
.cl-item{display:flex;align-items:center;gap:7px;font-family:'JetBrains Mono',monospace;font-size:9px;color:#000;font-weight:700;letter-spacing:.08em;text-transform:uppercase}
.cl-dot{width:20px;height:2px;flex-shrink:0}

/* ANIMATIONS */
@keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:none}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
.reveal{opacity:0;transform:translateY(20px);transition:opacity .75s ease,transform .75s ease}
.reveal.in{opacity:1;transform:none}
.d1{transition-delay:.1s}.d2{transition-delay:.2s}.d3{transition-delay:.3s}.d4{transition-delay:.4s}.d5{transition-delay:.5s}

@media(max-width:960px){
  section{padding:100px 32px 60px}
  .macro-grid,.data-grid,.sl-grid,.conc-pillars,.kpi-row,.escenario-box,.estrategia-grid,.estrategia-resumen{grid-template-columns:1fr}
  nav{padding:0 24px}
  .nav-items{display:none}
  #hero{padding:0 32px}
  footer{flex-direction:column;gap:24px;padding:40px 32px}
  .footer-authors{text-align:left}
  .bund-carry-grid{grid-template-columns:1fr 1fr}
}
</style>
</head>
<body>
<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>
<div id="progress"></div>

<nav>
  <div class="nav-logo">B/T · 2026</div>
  <ul class="nav-items">
    <li><a href="#macro">Macro</a></li>
    <li><a href="#datos">Datos</a></li>
    <li><a href="#treasury">Treasury</a></li>
    <li><a href="#bund">Bund</a></li>
    <li><a href="#estrategia">Estrategia</a></li>
    <li><a href="#riesgos">Riesgos &amp; Conclusión</a></li>
  </ul>
  <div class="nav-cta" style="padding:4px 12px;background:transparent;border:none"><img src="data:image/png;base64,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" alt="Instituto BME" style="height:36px;width:auto;display:block"></div>
</nav>

<!-- ═══ 01 HERO ════════════════════════════════════════════ -->
<section id="hero">
  <div class="hero-noise"></div>
  <div class="hero-glow"></div>
  <div class="hero-inner">
    <div class="hero-eyebrow" style="display:none">Análisis Macro · Renta Fija · 2026</div>
    <h1 class="hero-h1" style="font-size:clamp(48px,7vw,92px);margin-bottom:32px">
      <span>Bund</span>
      <span class="vs-word">vs</span>
      <span class="accent">Treasuries</span>
    </h1>
    <p class="hero-desc">Estrategia de divergencia monetaria — posición corta en el bono alemán y larga en deuda soberana americana para capturar la desincronización entre el BCE y la Reserva Federal.</p>
    <div class="hero-meta">
      <div>
        <div class="hmi-label">Autores</div>
        <div style="display:grid;grid-template-columns:1fr 1fr;gap:6px 32px;margin-top:8px">
          <span class="hmi-val" style="font-size:16px;font-weight:700">Lur Mendibe</span>
          <span class="hmi-val" style="font-size:16px;font-weight:700">Jorge Pulido</span>
          <span class="hmi-val" style="font-size:16px;font-weight:700">Diego Santiago</span>
          <span class="hmi-val" style="font-size:16px;font-weight:700">Gabriel Alarcia</span>
        </div>
      </div>
      <div style="width:1px;background:var(--border);align-self:stretch;margin:0 8px"></div>
      <div>
        <div class="hmi-label">Institución</div>
        <div class="hmi-val" style="font-size:20px;font-weight:700;margin-top:8px">Instituto BME</div>
        <div style="font-family:'JetBrains Mono',monospace;font-size:13px;color:var(--dim);margin-top:6px;letter-spacing:.05em;font-weight:600">Máster en Mercados Financieros · 2026</div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ 02 MACRO ═══════════════════════════════════════════ -->
<section id="macro">
  <div class="sec-num reveal">02 — Análisis Macro</div>
  <h2 class="sec-title reveal d1" style="text-align:center">BCE sube · FED baja —<br><em>dos ciclos opuestos</em></h2>
  <p class="sec-lead reveal d2">El entorno macro de 2026 está definido por una divergencia. La expansión fiscal en EE.UU. con el OBBB y los frentes abiertos en Europa crean una asimetría de tipos que es la base del trade. Sumado al entorno actual de los precios de la energía.</p>

  <div style="display:grid;grid-template-columns:1fr 1fr;grid-template-rows:auto auto auto auto auto auto auto;gap:2px;margin-bottom:24px">

    <!-- Fila 1: cabecera bandera + badge -->
    <div class="macro-panel eu reveal d2" style="border-bottom:none;padding-bottom:0">
      <div style="display:flex;align-items:center;justify-content:space-between">
        <span class="mp-flag" style="margin:0">🇩🇪</span>
        <span style="font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--red);letter-spacing:.12em;padding:5px 12px;border:1px solid rgba(176,30,30,.4);background:var(--red-dim)">SUBIDAS PREVISTAS</span>
      </div>
    </div>
    <div class="macro-panel us reveal d3" style="border-bottom:none;padding-bottom:0">
      <div style="display:flex;align-items:center;justify-content:space-between">
        <span class="mp-flag" style="margin:0">🇺🇸</span>
        <span style="font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--green);letter-spacing:.12em;padding:5px 12px;border:1px solid rgba(15,107,56,.4);background:var(--green-dim)">BAJADAS PREVISTAS</span>
      </div>
    </div>

    <!-- Fila 2: puntos -->
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:16px 36px">
      <ul class="mp-points">
        <li><strong style="color:var(--white)">Inflación:</strong> BCE con política disciplinada — inflación cerca del 2%, con riesgos al alza.</li>
        <li><strong style="color:var(--white)">Frentes abiertos:</strong> varios países con dificultades para aprobar presupuestos y reducir déficit.</li>
      </ul>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:16px 36px">
      <ul class="mp-points">
        <li><strong style="color:var(--white)">OBBB:</strong> expansión fiscal estructural con deuda pública al 120% del PIB y pago de intereses en 3% del PIB.</li>
        <li><strong style="color:var(--white)">Riesgo inflacionario:</strong> aranceles, salarios y expansión fiscal podrían limitar el margen de bajadas.</li>
      </ul>
    </div>

    <!-- Fila 3: veredicto -->
    <div style="background:var(--red-dim);border:1px solid rgba(176,30,30,.25);border-top:none;border-left:3px solid var(--red);padding:14px 24px;font-family:'Cormorant Garamond',serif;font-size:15px;font-style:italic;color:var(--red);font-weight:600;line-height:1.5">"Las TIRes del Bund seguirán presionando al alza."</div>
    <div style="background:var(--green-dim);border:1px solid rgba(15,107,56,.25);border-top:none;border-left:3px solid var(--green);padding:14px 24px;font-family:'Cormorant Garamond',serif;font-size:15px;font-style:italic;color:var(--green);font-weight:600;line-height:1.5">"Las TIRes del Treasury seguirán presionando a la baja."</div>

    <!-- Fila 4: Escenario tipos -->
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:10px 24px;display:flex;gap:0">
      <span class="mi-key">Escenario tipos</span><span class="mi-val red">↑ Subidas de T/I</span>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:10px 24px;display:flex;gap:0">
      <span class="mi-key">Escenario tipos</span><span class="mi-val green">↓ Bajadas de T/I</span>
    </div>

    <!-- Fila 5: Impacto -->
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:10px 24px;display:flex;gap:0">
      <span class="mi-key">Impacto Bund</span><span class="mi-val green">Precio cae · TIR sube</span>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:10px 24px;display:flex;gap:0">
      <span class="mi-key">Impacto Treasury</span><span class="mi-val red">Precio sube · TIR baja</span>
    </div>

    <!-- Fila 6: Nuestra posición -->
    <div style="background:var(--red-dim);border:1px solid rgba(176,30,30,.2);border-top:none;padding:10px 24px;display:flex;gap:0">
      <span class="mi-key" style="color:var(--red)">Nuestra posición</span><span class="mi-val red">CORTA — vendemos Bund</span>
    </div>
    <div style="background:var(--green-dim);border:1px solid rgba(15,107,56,.2);border-top:none;padding:10px 24px;display:flex;gap:0">
      <span class="mi-key" style="color:var(--green)">Nuestra posición</span><span class="mi-val green">LARGA — compramos Treasury</span>
    </div>

  </div>

  <div class="reveal d4" style="display:grid;grid-template-columns:1fr 1fr;grid-template-rows:auto auto auto;gap:2px;margin-top:0;border-top:3px solid var(--border);padding-top:0">
    <div style="background:var(--surface);border:1px solid var(--border);border-top:2px solid var(--red);padding:14px 24px;grid-row:1;grid-column:1">
      <div style="font-family:'JetBrains Mono',monospace;font-size:12px;font-weight:700;color:#000;letter-spacing:.08em">🇩🇪 BUND · 7,5 AÑOS</div>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-top:2px solid var(--green);padding:14px 24px;grid-row:1;grid-column:2">
      <div style="font-family:'JetBrains Mono',monospace;font-size:12px;font-weight:700;color:#000;letter-spacing:.08em">🇺🇸 TREASURY · 1,5 AÑOS</div>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:18px 24px;grid-row:2;grid-column:1;display:flex;align-items:center;gap:12px">
      <span style="font-family:'JetBrains Mono',monospace;font-size:11px;font-weight:700;color:#333;width:100px;flex-shrink:0">TIR actual</span>
      <span style="font-family:'Cormorant Garamond',serif;font-size:56px;font-weight:600;line-height:1;color:var(--red)">2,77%</span>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:18px 24px;grid-row:2;grid-column:2;display:flex;align-items:center;gap:12px">
      <span style="font-family:'JetBrains Mono',monospace;font-size:11px;font-weight:700;color:#333;width:100px;flex-shrink:0">TIR actual</span>
      <span style="font-family:'Cormorant Garamond',serif;font-size:56px;font-weight:600;line-height:1;color:var(--green)">3,67%</span>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:18px 24px;grid-row:3;grid-column:1;display:flex;align-items:center;gap:12px">
      <span style="font-family:'JetBrains Mono',monospace;font-size:11px;font-weight:700;color:#333;width:100px;flex-shrink:0">TIR objetivo</span>
      <span style="font-family:'Cormorant Garamond',serif;font-size:56px;font-weight:600;line-height:1;color:var(--red)">3,15%</span>
    </div>
    <div style="background:var(--surface);border:1px solid var(--border);border-top:none;padding:18px 24px;grid-row:3;grid-column:2;display:flex;align-items:center;gap:12px">
      <span style="font-family:'JetBrains Mono',monospace;font-size:11px;font-weight:700;color:#333;width:100px;flex-shrink:0">TIR objetivo</span>
      <span style="font-family:'Cormorant Garamond',serif;font-size:56px;font-weight:600;line-height:1;color:var(--green)">3,30%</span>
    </div>
  </div>
</section>

<!-- ═══ 03 DATOS EMISIÓN ════════════════════════════════════ -->
<section id="datos">
  <div class="sec-num reveal">03 — Datos de la Emisión</div>
  <h2 class="sec-title reveal d1">Características<br><em>de los bonos</em></h2>

  <div style="display:grid;grid-template-columns:1fr 1fr;gap:24px;margin-top:8px">
    <!-- BUND izquierda -->
    <div class="reveal d2">
      <div style="display:flex;align-items:center;gap:12px;margin-bottom:16px;padding-bottom:14px;border-bottom:2px solid var(--red)">
        <span style="font-size:28px">🇩🇪</span>
        <div>
          <div style="font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--red);letter-spacing:.18em;text-transform:uppercase">Posición Corta</div>
          <div style="font-size:16px;font-weight:700;color:var(--white);margin-top:2px">Bund Alemán · 7,5Y</div>
        </div>
        <div style="margin-left:auto;display:flex;gap:8px">
          <div style="text-align:center;background:var(--surface);border:1px solid var(--border);padding:10px 16px">
            <div style="font-family:'JetBrains Mono',monospace;font-size:8px;color:var(--muted);letter-spacing:.12em;text-transform:uppercase">Duración</div>
            <div style="font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:600;color:var(--red);line-height:1.1">6,558</div>
          </div>
          <div style="text-align:center;background:var(--surface);border:1px solid var(--border);padding:10px 16px">
            <div style="font-family:'JetBrains Mono',monospace;font-size:8px;color:var(--muted);letter-spacing:.12em;text-transform:uppercase">Convexidad</div>
            <div style="font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:600;color:var(--dim);line-height:1.1">0,525</div>
          </div>
        </div>
      </div>
      <table class="dt">
        <tr><th>Campo</th><th>TD 11/03</th><th>SD 30/12</th></tr>
        <tr><td>ISIN</td><td colspan="2" style="color:var(--dim)">DE000BU2Z015</td></tr>
        <tr><td>Vencimiento</td><td colspan="2" style="color:var(--dim)">15/08/2033</td></tr>
        <tr><td>Venc. en años</td><td class="warn">7,44</td><td class="warn">6,63</td></tr>
        <tr><td>Cupón</td><td colspan="2">2,60%</td></tr>
        <tr><td>Rating</td><td colspan="2" class="win">AAA</td></tr>
        <tr><td>Repo 9 meses</td><td colspan="2" class="lose">2,08%</td></tr>
      </table>
    </div>

    <!-- TREASURY derecha -->
    <div class="reveal d3">
      <div style="display:flex;align-items:center;gap:12px;margin-bottom:16px;padding-bottom:14px;border-bottom:2px solid var(--green)">
        <span style="font-size:28px">🇺🇸</span>
        <div>
          <div style="font-family:'JetBrains Mono',monospace;font-size:9px;color:var(--green);letter-spacing:.18em;text-transform:uppercase">Posición Larga</div>
          <div style="font-size:16px;font-weight:700;color:var(--white);margin-top:2px">Treasury · 1,5Y</div>
        </div>
        <div style="margin-left:auto;display:flex;gap:8px">
          <div style="text-align:center;background:var(--surface);border:1px solid var(--border);padding:10px 16px">
            <div style="font-family:'JetBrains Mono',monospace;font-size:8px;color:var(--muted);letter-spacing:.12em;text-transform:uppercase">Duración</div>
            <div style="font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:600;color:var(--green);line-height:1.1">1,205</div>
          </div>
          <div style="text-align:center;background:var(--surface);border:1px solid var(--border);padding:10px 16px">
            <div style="font-family:'JetBrains Mono',monospace;font-size:8px;color:var(--muted);letter-spacing:.12em;text-transform:uppercase">Convexidad</div>
            <div style="font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:600;color:var(--dim);line-height:1.1">0,021</div>
          </div>
        </div>
      </div>
      <table class="dt">
        <tr><th>Campo</th><th>TD 11/03</th><th>SD 30/12</th></tr>
        <tr><td>ISIN</td><td colspan="2" style="color:var(--dim)">US91282CKV27</td></tr>
        <tr><td>Vencimiento</td><td colspan="2" style="color:var(--dim)">15/06/2027</td></tr>
        <tr><td>Venc. en años</td><td class="warn">1,26</td><td class="warn">0,46</td></tr>
        <tr><td>Cupón</td><td colspan="2">4,625%</td></tr>
        <tr><td>Rating</td><td colspan="2" class="win">AA+</td></tr>
      </table>
    </div>
  </div>
</section>

<!-- ═══ 04 TREASURY: CARRY & COBERTURA ═════════════════════ -->
<section id="treasury">
  <div class="sec-num reveal">04 — Análisis del Bono</div>
  <h2 class="sec-title reveal d1"><em>US Treasury</em></h2>

  <div class="kpi-row reveal d2" style="grid-template-columns:repeat(3,1fr);margin-bottom:24px">
    <div class="kpi k-blue">
      <div class="kpi-tag">TIR Inicial</div>
      <div class="kpi-val" style="font-size:32px">3,67%</div>
      <div class="kpi-note">11/03/2026</div>
    </div>
    <div class="kpi k-blue">
      <div class="kpi-tag">Duración</div>
      <div class="kpi-val" style="font-size:32px">294d</div>
      <div class="kpi-note">Horizonte inversión</div>
    </div>
    <div class="kpi k-green">
      <div class="kpi-tag">TIR Previsión</div>
      <div class="kpi-val" style="font-size:32px">3,30%</div>
      <div class="kpi-note">Objetivo 30/12/2026</div>
    </div>
  </div>

  <!-- Precio limpio -->
  <div class="reveal d2" style="margin-bottom:24px">
    <table class="dt" style="width:100%">
      <tr><th>Precio limpio</th><th>11/03/2026</th><th>30/12/2026</th></tr>
      <tr><td style="color:var(--gold);font-weight:500">US Treasury 1,5Y</td><td class="win">101,16%</td><td class="win">100,78%</td></tr>
    </table>
  </div>

  <!-- Tablas retorno + cobertura side by side -->
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:24px" class="reveal d3">
    <div>
      <div class="data-block-title">Retorno — US Treasury</div>
      <table class="dt">
        <tr><th>Componente</th><th>Valor</th></tr>
        <tr><td>Retorno carry</td><td class="win">1,491%</td></tr>
        <tr><td>Retorno TIR</td><td class="win">0,4468%</td></tr>
        <tr><td>Retorno convexidad</td><td class="win">0,0000144%</td></tr>
        <tr style="border-top:1px solid rgba(61,187,127,.3)"><td style="color:var(--green);font-weight:600">Retorno estimado</td><td class="win" style="font-size:14px;font-weight:600">1,938%</td></tr>
      </table>
    </div>
    <div>
      <div class="data-block-title">Cobertura EUR/USD · 9 meses</div>
      <table class="dt">
        <tr><th>Concepto</th><th>11/03/2026</th><th>30/12/2026</th></tr>
        <tr><td>EUR/USD</td><td class="warn">1,1575</td><td class="warn">1,175</td></tr>
        <tr><td>Contratos</td><td>26,50</td><td>27,00</td></tr>
        <tr style="background:rgba(224,82,82,.07)"><td style="color:var(--red);font-weight:500">Coste por contrato</td><td colspan="2" style="color:var(--red);font-weight:600;text-align:center">−266,07</td></tr>
        <tr style="background:rgba(61,187,127,.07)"><td style="color:var(--green);font-weight:500">Rdto. bono USD</td><td colspan="2" style="color:var(--green);font-weight:600;text-align:center">5.945,97 (1,94%)</td></tr>
        <tr style="background:rgba(224,82,82,.07)"><td style="color:var(--red);font-weight:500">Rdto. EUR sin cobertura</td><td colspan="2" style="color:var(--red);font-weight:600;text-align:center">1.117,43 (0,42%)</td></tr>
        <tr style="background:rgba(61,187,127,.07)"><td style="color:var(--green);font-weight:500">Rdto. EUR con cobertura</td><td colspan="2" style="color:var(--green);font-weight:600;text-align:center">5.539,44 (2,09%)</td></tr>
        <tr style="background:rgba(224,82,82,.07)"><td style="color:var(--red);font-weight:500">Cost of carry cobertura</td><td colspan="2" style="color:var(--red);font-weight:600;text-align:center">−7.183,85 (2,71%)</td></tr>
        <tr style="background:rgba(224,82,82,.15)"><td style="color:var(--red);font-weight:700">Resultado neto</td><td colspan="2" style="color:var(--red);font-weight:700;font-size:13px;text-align:center">−1.644,40 (−0,62%)</td></tr>
      </table>
      <div style="margin-top:8px;padding:10px 14px;background:var(--red-dim);border:1px solid rgba(224,82,82,.2)">
        <span style="font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--red)">⚠ El coste de cobertura (2,71%) supera el retorno del bono — posición sin cobertura más eficiente.</span>
      </div>
    </div>
  </div>
</section>

<!-- ═══ 05 BUND: STOP LOSS & CARRY ════════════════════════ -->
<section id="bund">
  <div class="sec-num reveal">05 — Análisis del Bono</div>
  <h2 class="sec-title reveal d1"><em>Bund Alemán</em></h2>

  <div class="kpi-row reveal d2" style="grid-template-columns:repeat(3,1fr);margin-bottom:24px">
    <div class="kpi k-red">
      <div class="kpi-tag">TIR Inicial</div>
      <div class="kpi-val" style="font-size:32px">2,77%</div>
      <div class="kpi-note">11/03/2026</div>
    </div>
    <div class="kpi k-red">
      <div class="kpi-tag">Duración</div>
      <div class="kpi-val" style="font-size:32px">294d</div>
      <div class="kpi-note">Horizonte inversión</div>
    </div>
    <div class="kpi k-red">
      <div class="kpi-tag">TIR Previsión</div>
      <div class="kpi-val" style="font-size:32px">3,15%</div>
      <div class="kpi-note">Objetivo 30/12/2026</div>
    </div>
  </div>

  <div style="display:grid;grid-template-columns:1fr 1.6fr;gap:24px" class="reveal d3">
    <!-- Retorno -->
    <div>
      <div class="data-block-title">Retorno — Bund Alemán</div>
      <table class="dt">
        <tr><th>Componente</th><th>Valor</th></tr>
        <tr><td>Repo 9 meses</td><td style="color:#000;font-weight:600;text-align:center">2,080%</td></tr>
        <tr><td>Retorno carry</td><td style="color:#555;font-weight:600;text-align:center">—</td></tr>
        <tr><td>Retorno TIR</td><td class="win">2,518%</td></tr>
        <tr><td>Retorno convexidad</td><td class="win">0,0004%</td></tr>
        <tr style="border-top:1px solid rgba(61,187,127,.3)"><td style="color:var(--green);font-weight:600">Retorno estimado</td><td class="win" style="font-size:14px;font-weight:600">2,517%</td></tr>
      </table>
    </div>

    <!-- Gráfico -->
    <div>
      <div class="sl-chart-box">
        <div class="chart-label">TIR Bund 7Y · Media y bandas de desviación estándar (Jul 2022 – Mar 2026)</div>
        <canvas id="slChart" height="220"></canvas>
        <div class="chart-legend" style="margin-top:10px">
          <div class="cl-item"><span class="cl-dot" style="background:#4A9ECC"></span>TIR 7Y</div>
          <div class="cl-item"><span class="cl-dot" style="background:var(--gold)"></span>Media 2,35%</div>
          <div class="cl-item"><span class="cl-dot" style="background:var(--red)"></span>Stop Loss 2,55%</div>
          <div class="cl-item"><span class="cl-dot" style="background:#9B59B6"></span>+2σ / +3σ</div>
        </div>
      </div>

      <!-- Stop loss levels debajo del gráfico -->
      <div style="margin-top:16px;display:grid;grid-template-columns:repeat(3,1fr);gap:2px">
        <div class="sl-level"><span class="sl-level-label">Desv. Estándar</span><span class="sl-level-val red" style="font-size:20px">2,55%</span></div>
        <div class="sl-level"><span class="sl-level-label">Media histórica</span><span class="sl-level-val dim" style="font-size:20px">2,36%</span></div>
        <div class="sl-level"><span class="sl-level-label">2ª Desv. Estándar</span><span class="sl-level-val red" style="font-size:20px">2,74%</span></div>
        <div class="sl-level" style="border:1px solid rgba(176,30,30,.5);background:var(--red-dim);grid-column:span 3;justify-content:center;gap:32px">
          <span class="sl-level-label" style="color:var(--red);font-size:11px">Stop Loss fijado</span>
          <span class="sl-level-val red" style="font-size:28px">2,55%</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ 06 ESTRATEGIA 30/70 ═════════════════════════════════ -->
<section id="estrategia">
  <div class="sec-num reveal">06 — Estrategia de Cartera</div>
  <h2 class="sec-title reveal d1">Ponderación<br><em>30% Treasury · 70% Bund</em></h2>
  <p class="sec-lead reveal d2">La cartera concentra el peso en la posición corta de Bund (70%), donde la duración alta y el movimiento esperado de TIR ofrecen mayor impacto. El 30% en Treasury aporta carry positivo y actúa como diversificación.</p>

  <div class="estrategia-grid reveal d3">
    <!-- TREASURY -->
    <div class="estr-panel treasury">
      <div class="estr-weight green">30%</div>
      <div class="estr-name">Treasury · Posición Larga</div>
      <div class="estr-rows">
        <div class="estr-row"><span class="estr-row-key">TIR actual</span><span class="estr-row-val">3,67%</span></div>
        <div class="estr-row"><span class="estr-row-key">TIR objetivo</span><span class="estr-row-val green">3,30%</span></div>
        <div class="estr-row"><span class="estr-row-key">Duración mod.</span><span class="estr-row-val">1,205</span></div>
      </div>
    </div>
    <!-- BUND -->
    <div class="estr-panel" style="background:var(--surface);border:1px solid var(--border);padding:36px;position:relative;overflow:hidden">
      <div style="position:absolute;top:0;left:0;right:0;height:2px;background:var(--blue)"></div>
      <div class="estr-weight" style="color:var(--blue)">70%</div>
      <div class="estr-name">Bund Alemán · Posición Corta</div>
      <div class="estr-rows">
        <div class="estr-row"><span class="estr-row-key">TIR actual</span><span class="estr-row-val">2,77%</span></div>
        <div class="estr-row"><span class="estr-row-key">TIR objetivo</span><span class="estr-row-val" style="color:var(--blue)">3,15%</span></div>
        <div class="estr-row"><span class="estr-row-key">Duración mod.</span><span class="estr-row-val">6,558</span></div>
        <div class="estr-row"><span class="estr-row-key">Repo 9m</span><span class="estr-row-val">2,080%</span></div>
      </div>
    </div>
  </div>

  <!-- TABLA RESULTADOS DE LA IMAGEN -->
  <div class="reveal d4" style="margin-top:24px;overflow-x:auto">
    <div style="font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--gold);letter-spacing:.18em;text-transform:uppercase;margin-bottom:12px;padding-bottom:10px;border-bottom:1px solid var(--border)">Resultados de la Cartera · Escenarios de Cobertura</div>
    <table style="width:100%;border-collapse:collapse;font-size:12px;font-family:'JetBrains Mono',monospace">
      <thead>
        <tr>
          <th colspan="4" style="background:#1A1F2E;color:#fff;padding:8px 12px;text-align:center;font-size:10px;letter-spacing:.1em">11/03/2026</th>
          <th style="background:#fff;border:none;width:16px"></th>
          <th colspan="2" style="background:#1A7A4A;color:#fff;padding:8px 12px;text-align:center;font-size:10px;letter-spacing:.1em">30/12/2026 · Con Cobertura</th>
          <th style="background:#fff;border:none;width:16px"></th>
          <th colspan="2" style="background:#1A7A4A;color:#fff;padding:8px 12px;text-align:center;font-size:10px;letter-spacing:.1em">30/12/2026 · Sin Cobertura</th>
        </tr>
        <tr style="background:var(--surface)">
          <th style="padding:7px 12px;text-align:left;color:var(--muted);font-weight:500;border-bottom:1px solid var(--border)">Nominal</th>
          <th style="padding:7px 12px;text-align:right;color:var(--muted);font-weight:500;border-bottom:1px solid var(--border)">Peso</th>
          <th style="padding:7px 12px;text-align:right;color:var(--muted);font-weight:500;border-bottom:1px solid var(--border)">Efectivo EUR</th>
          <th style="padding:7px 12px;text-align:right;color:var(--muted);font-weight:500;border-bottom:1px solid var(--border)">Efectivo USD</th>
          <th style="border:none"></th>
          <th style="padding:7px 12px;text-align:right;color:var(--muted);font-weight:500;border-bottom:1px solid var(--border)">Efectivo EUR</th>
          <th style="padding:7px 12px;text-align:right;color:var(--muted);font-weight:500;border-bottom:1px solid var(--border)">%</th>
          <th style="border:none"></th>
          <th style="padding:7px 12px;text-align:right;color:var(--muted);font-weight:500;border-bottom:1px solid var(--border)">Efectivo EUR</th>
          <th style="padding:7px 12px;text-align:right;color:var(--muted);font-weight:500;border-bottom:1px solid var(--border)">%</th>
        </tr>
      </thead>
      <tbody>
        <tr style="background:rgba(192,57,43,.08)">
          <td style="padding:8px 12px;font-weight:700;color:var(--red);border-bottom:1px solid var(--border)">300.000,00</td>
          <td style="padding:8px 12px;text-align:right;font-weight:700;border-bottom:1px solid var(--border)">27,4%</td>
          <td style="padding:8px 12px;text-align:right;border-bottom:1px solid var(--border)">265.045,13</td>
          <td style="padding:8px 12px;text-align:right;border-bottom:1px solid var(--border)">306.795,03</td>
          <td style="border:none"></td>
          <td style="padding:8px 12px;text-align:right;border-bottom:1px solid var(--border)">263.400,72</td>
          <td style="padding:8px 12px;text-align:right;color:var(--red);font-weight:600;border-bottom:1px solid var(--border)">−0,62%</td>
          <td style="border:none"></td>
          <td style="padding:8px 12px;text-align:right;border-bottom:1px solid var(--border)">266.162,55</td>
          <td style="padding:8px 12px;text-align:right;color:var(--green);font-weight:600;border-bottom:1px solid var(--border)">0,42%</td>
        </tr>
        <tr style="background:rgba(26,122,74,.08)">
          <td style="padding:8px 12px;font-weight:700;color:var(--green);border-bottom:1px solid var(--border)">700.000,00</td>
          <td style="padding:8px 12px;text-align:right;font-weight:700;border-bottom:1px solid var(--border)">72,6%</td>
          <td style="padding:8px 12px;text-align:right;border-bottom:1px solid var(--border)">702.954,78</td>
          <td style="padding:8px 12px;text-align:right;border-bottom:1px solid var(--border)">702.954,78</td>
          <td style="border:none"></td>
          <td style="padding:8px 12px;text-align:right;border-bottom:1px solid var(--border)">708.469,68</td>
          <td style="padding:8px 12px;text-align:right;color:var(--green);font-weight:600;border-bottom:1px solid var(--border)">0,78%</td>
          <td style="border:none"></td>
          <td style="padding:8px 12px;text-align:right;border-bottom:1px solid var(--border)">708.469,68</td>
          <td style="padding:8px 12px;text-align:right;color:var(--green);font-weight:600;border-bottom:1px solid var(--border)">0,78%</td>
        </tr>
        <tr style="background:rgba(184,144,42,.10);font-weight:700">
          <td style="padding:10px 12px;color:var(--gold)">1.000.000,00</td>
          <td style="padding:10px 12px;text-align:right;color:var(--gold)">100%</td>
          <td style="padding:10px 12px;text-align:right;color:var(--white)">967.999,90</td>
          <td style="padding:10px 12px;text-align:right"></td>
          <td style="border:none"></td>
          <td style="padding:10px 12px;text-align:right;color:var(--white)">971.870,40</td>
          <td style="padding:10px 12px;text-align:right;color:var(--green);font-size:14px">0,40%</td>
          <td style="border:none"></td>
          <td style="padding:10px 12px;text-align:right;color:var(--white)">974.632,24</td>
          <td style="padding:10px 12px;text-align:right;color:var(--green);font-size:14px">0,69%</td>
        </tr>
      </tbody>
    </table>
  </div>
</section>

<!-- ═══ 07 RIESGOS + CONCLUSIÓN ══════════════════════════════ -->
<section id="riesgos">
  <div class="sec-num reveal">07 — Riesgos &amp; Recomendación</div>

  <h2 class="sec-title reveal d1">Escenarios adversos<br><em>&amp; Recomendación final</em></h2>

  <div style="display:grid;grid-template-columns:1fr 1fr;gap:48px;align-items:start">

    <!-- RIESGOS -->
    <div>
      <h3 style="font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:300;color:#000;margin-bottom:20px">Escenarios<br><em style="color:var(--red)">adversos</em></h3>
      <div class="risk-list">
        <div class="risk-item reveal d2">
          <div class="risk-n r1">01</div>
          <div class="risk-content">
            <div class="risk-title">Inflación persistente — tipos altos más tiempo</div>
            <div class="risk-desc">Aranceles, salarios y OBBB mantienen inflación elevada. TIRes de Treasuries repuntan. La posición larga pierde valor.</div>
          </div>
          <div class="risk-badge rb1">Larga</div>
        </div>
        <div class="risk-item reveal d3">
          <div class="risk-n r2">02</div>
          <div class="risk-content">
            <div class="risk-title">Europa en recesión — bajadas de tipos</div>
            <div class="risk-desc">Recesión profunda fuerza al BCE a bajar tipos. Precio del Bund sube, perjudicando la posición corta.</div>
          </div>
          <div class="risk-badge rb2">Corta</div>
        </div>
        <div class="risk-item reveal d4">
          <div class="risk-n r3">03</div>
          <div class="risk-content">
            <div class="risk-title">Convergencia de políticas monetarias</div>
            <div class="risk-desc">BCE y FED actúan coordinadamente. El spread no se mueve. El trade no genera retorno — riesgo principal.</div>
          </div>
          <div class="risk-badge rb3">Trade</div>
        </div>
      </div>
      <div class="risk-footer reveal d5" style="margin-top:8px">
        "El riesgo principal es la convergencia de políticas — neutralizaría el trade por completo."
      </div>
    </div>

    <!-- CONCLUSIÓN -->
    <div class="reveal d2">
      <h3 style="font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:300;color:#000;margin-bottom:20px">Recomendación<br><em style="color:var(--gold)">final</em></h3>
      <div class="conc-quote" style="margin-bottom:20px">
        <p>"La divergencia BCE/FED, amplificada por el OBBB y la expansión fiscal alemana, crea una oportunidad estructural. Una cartera 70% corta en Bund / 30% larga en Treasury ofrece carry atractivo y potencial de plusvalías en el escenario base."</p>
      </div>
      <div class="conc-pillars" style="grid-template-columns:1fr;gap:2px;margin-bottom:16px">
        <div class="cp">
          <div class="cp-title">Soporte Macro</div>
          <div class="cp-body"><strong>Subidas previstas Europa vs bajadas EE.UU.</strong> OBBB + expansión fiscal alemana divergencia estructural confirmada.</div>
        </div>
        <div class="cp">
          <div class="cp-title">Soporte Cuantitativo</div>
          <div class="cp-body"><strong>Rolling Yield Treasury 1,491%.</strong> Stop loss Bund superado (2,55% ✓). TIR objetivo Bund 3,15% (+2σ). Resultados: sin cobertura 0,69% · con cobertura 0,40%.</div>
        </div>
        <div class="cp">
          <div class="cp-title">Perfil Riesgo-Retorno</div>
          <div class="cp-body"><strong>Favorable en escenario base.</strong> 70% Bund corto / 30% Treasury largo. Riesgo acotado y monitorizable.</div>
        </div>
      </div>
      <div class="conc-tags" style="margin-bottom:20px">
        <div class="ctag" style="background:rgba(21,88,160,.1);border:1px solid rgba(21,88,160,.3);color:var(--blue)">🔵 70% Corto Bund</div>
        <div class="ctag green">🟢 30% Largo Treasury</div>
        <div class="ctag gold">⚡ Divergencia BCE/FED</div>
      </div>

      <!-- LINK EXCEL -->
      <div style="margin-top:16px;padding:16px 20px;background:var(--surface);border:1px solid var(--border);display:flex;align-items:center;gap:16px">
        <span style="font-size:22px">📊</span>
        <div>
          <div style="font-family:'JetBrains Mono',monospace;font-size:9px;color:#000;font-weight:700;letter-spacing:.15em;text-transform:uppercase;margin-bottom:4px">Material de trabajo · Hoja de cálculo</div>
          <a href="https://docs.google.com/spreadsheets/d/1ttp-KwlLC4mJygRnJ_rNEJ1XPKO8Dbhn/edit?usp=sharing&ouid=103393855784078189357&rtpof=true&sd=true" target="_blank" rel="noopener" style="font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--blue);font-weight:700;text-decoration:underline;letter-spacing:.04em">Ver Excel en Google Sheets →</a>
        </div>
      </div>
    </div>

  </div>
</section>

<footer>
  <div>
    <div class="footer-brand">Bund vs Treasuries</div>
    <div class="footer-sub">Instituto BME · Máster en Mercados Financieros · 2026</div>
  </div>
  <div class="footer-authors">
    Lur Mendibe<br>
    Jorge Pulido<br>
    Diego Santiago<br>
    Gabriel Alarcia
  </div>
</footer>

<script>
const cursor = document.getElementById('cursor');
const ring   = document.getElementById('cursorRing');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;cursor.style.transform=`translate(${mx-4}px,${my-4}px)`});
(function animRing(){rx+=(mx-rx-18)*.12;ry+=(my-ry-18)*.12;ring.style.transform=`translate(${rx}px,${ry}px)`;requestAnimationFrame(animRing)})();
const prog=document.getElementById('progress');
window.addEventListener('scroll',()=>{const pct=window.scrollY/(document.body.scrollHeight-window.innerHeight)*100;prog.style.width=pct+'%'});
const obs=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('in')})},{threshold:.1});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));

Chart.defaults.color='rgba(26,31,46,.45)';
Chart.defaults.font.family="'JetBrains Mono',monospace";
Chart.defaults.font.size=10;
const gc='rgba(0,0,0,.07)';

new Chart(document.getElementById('plChart'),{
  type:'bar',
  data:{
    labels:['+100 pb','+50 pb','Sin mov.','−50 pb','−100 pb'],
    datasets:[
      {label:'P&L Bund (corta)',data:[3.5,2.0,0,-1.5,-3.0],backgroundColor:ctx=>ctx.parsed.y>=0?'rgba(26,122,74,.6)':'rgba(192,57,43,.6)',borderRadius:3,order:2},
      {label:'P&L Treasury (larga)',data:[-0.8,0,0,1.8,3.2],backgroundColor:ctx=>ctx.parsed.y>=0?'rgba(26,122,74,.35)':'rgba(192,57,43,.35)',borderRadius:3,order:2},
      {label:'P&L Total spread',data:[2.7,2.0,0,0.3,0.2],type:'line',borderColor:'rgba(184,144,42,.9)',borderWidth:2,pointRadius:5,pointBackgroundColor:'#B8902A',tension:.4,fill:false,order:1}
    ]
  },
  options:{responsive:true,plugins:{legend:{labels:{boxWidth:12}},tooltip:{callbacks:{label:ctx=>` ${ctx.dataset.label}: ${ctx.parsed.y>0?'+':''}${ctx.parsed.y.toFixed(1)}`}}},scales:{x:{grid:{color:gc}},y:{grid:{color:gc},ticks:{callback:v=>(v>0?'+':'')+v.toFixed(1)}}}}
});

const slL=['Jul 22','Oct 22','Ene 23','Abr 23','Jul 23','Oct 23','Ene 24','Abr 24','Jul 24','Oct 24','Ene 25','Abr 25','Jul 25','Oct 25','Ene 26','Mar 26'];
const slT=[1.18,2.10,2.57,2.34,2.62,2.78,2.19,2.58,2.41,2.18,2.35,2.21,2.44,2.61,2.70,2.78];
const n=slL.length;
new Chart(document.getElementById('slChart'),{
  type:'line',
  data:{labels:slL,datasets:[
    {label:'TIR 7Y',data:slT,borderColor:'#1D6FA4',borderWidth:2,pointRadius:2.5,pointBackgroundColor:'#1D6FA4',tension:.35,fill:false},
    {label:'Media 2,35%',data:Array(n).fill(2.35),borderColor:'rgba(184,144,42,.8)',borderWidth:1.5,pointRadius:0,fill:false},
    {label:'Stop Loss 2,55%',data:Array(n).fill(2.55),borderColor:'rgba(192,57,43,.7)',borderWidth:1.5,borderDash:[6,4],pointRadius:0,fill:false},
    {label:'+1σ',data:Array(n).fill(2.57),borderColor:'rgba(184,144,42,.3)',borderWidth:1,borderDash:[3,4],pointRadius:0,fill:false},
    {label:'+2σ',data:Array(n).fill(2.78),borderColor:'rgba(128,0,128,.5)',borderWidth:1.5,borderDash:[4,3],pointRadius:0,fill:false},
    {label:'+3σ',data:Array(n).fill(3.00),borderColor:'rgba(192,57,43,.4)',borderWidth:1,borderDash:[2,5],pointRadius:0,fill:false},
    {label:'-1σ',data:Array(n).fill(2.18),borderColor:'rgba(26,122,74,.4)',borderWidth:1,borderDash:[3,4],pointRadius:0,fill:false},
    {label:'-2σ',data:Array(n).fill(2.00),borderColor:'rgba(26,122,74,.25)',borderWidth:1,borderDash:[2,5],pointRadius:0,fill:false},
  ]},
  options:{responsive:true,plugins:{legend:{display:false},tooltip:{callbacks:{label:ctx=>` ${ctx.dataset.label}: ${typeof ctx.parsed.y==='number'?ctx.parsed.y.toFixed(2)+'%':''}`}}},scales:{x:{grid:{color:gc},ticks:{maxRotation:0}},y:{min:1.7,max:3.2,grid:{color:gc},ticks:{callback:v=>v.toFixed(2)+'%'}}}}
});
</script>
</body>
</html>
