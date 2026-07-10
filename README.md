[index.html](https://github.com/user-attachments/files/29872457/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EDUVESA NRP 9.ª Edición (AAP/AHA)</title>
<style>
  :root{
    --petrol:#0d4d5c;      /* primary clinical teal */
    --petrol-d:#093843;
    --petrol-l:#1a6b7d;
    --amber:#e8a33d;       /* newborn warmth / highlight */
    --coral:#d96a4a;       /* attention */
    --crit:#c9433f;        /* HR low / critical */
    --good:#1fa97e;        /* improving vitals */
    --ink:#15242b;
    --muted:#5b6b72;
    --line:#dbe4e7;
    --bg:#f5f8f9;
    --card:#ffffff;
    --chip:#eef4f5;
    --shadow:0 1px 2px rgba(9,56,67,.06),0 6px 18px rgba(9,56,67,.06);
    --mono:ui-monospace,"SF Mono",Menlo,Consolas,"Liberation Mono",monospace;
    --sans:system-ui,-apple-system,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
  }
  *{box-sizing:border-box}
  html{scroll-behavior:smooth}
  body{
    margin:0;font-family:var(--sans);color:var(--ink);background:var(--bg);
    line-height:1.5;-webkit-text-size-adjust:100%;
  }
  /* ---------- Header ---------- */
  header.top{
    background:linear-gradient(160deg,var(--petrol) 0%,var(--petrol-d) 100%);
    color:#fff;padding:22px 18px 18px;
  }
  .brandrow{display:flex;align-items:center;gap:12px;max-width:1040px;margin:0 auto}
  .logo{
    width:44px;height:44px;border-radius:12px;flex:none;
    background:radial-gradient(circle at 32% 30%,var(--amber),var(--coral));
    display:grid;place-items:center;font-weight:800;color:#fff;font-size:19px;
    box-shadow:inset 0 0 0 2px rgba(255,255,255,.25);
  }
  .brandtxt b{font-size:15px;letter-spacing:.14em;text-transform:uppercase;display:block}
  .brandtxt span{font-size:12px;color:#bfe0e6;letter-spacing:.02em}
  h1.title{
    max-width:1040px;margin:16px auto 4px;font-size:clamp(21px,4.6vw,30px);
    font-weight:800;letter-spacing:-.01em;line-height:1.15;
  }
  .subtitle{max-width:1040px;margin:0 auto;color:#cfe6ea;font-size:14px}
  .edition{
    display:inline-block;margin-top:12px;font-family:var(--mono);font-size:11px;
    letter-spacing:.08em;background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.22);
    padding:4px 9px;border-radius:6px;color:#eaf6f8;
  }
  /* ---------- Warning banner ---------- */
  .warn{
    background:#fff8ec;border-top:3px solid var(--amber);color:#6d4a12;
    font-size:12.5px;padding:10px 18px;
  }
  .warn div{max-width:1040px;margin:0 auto}
  .warn b{color:#8a5c10}
  /* ---------- Nav ---------- */
  nav.tabs{
    position:sticky;top:0;z-index:40;background:rgba(255,255,255,.94);
    backdrop-filter:blur(8px);border-bottom:1px solid var(--line);
    overflow-x:auto;-webkit-overflow-scrolling:touch;scrollbar-width:none;
  }
  nav.tabs::-webkit-scrollbar{display:none}
  .tabsrow{display:flex;gap:2px;max-width:1040px;margin:0 auto;padding:0 8px}
  .tab{
    flex:none;border:0;background:none;font-family:var(--sans);cursor:pointer;
    padding:13px 12px 11px;font-size:13px;font-weight:600;color:var(--muted);
    border-bottom:3px solid transparent;white-space:nowrap;letter-spacing:.01em;
  }
  .tab:hover{color:var(--petrol)}
  .tab[aria-selected="true"]{color:var(--petrol);border-color:var(--petrol)}
  .tab:focus-visible{outline:2px solid var(--petrol-l);outline-offset:-3px;border-radius:4px}
  /* ---------- Layout ---------- */
  main{max-width:1040px;margin:0 auto;padding:22px 16px 80px}
  .panel{display:none;animation:fade .25s ease}
  .panel.active{display:block}
  @keyframes fade{from{opacity:0;transform:translateY(6px)}to{opacity:1;transform:none}}
  .lead{color:var(--muted);font-size:15px;max-width:68ch}
  h2.sec{font-size:22px;font-weight:800;letter-spacing:-.01em;margin:6px 0 4px}
  .eyebrow{font-family:var(--mono);font-size:11px;letter-spacing:.16em;text-transform:uppercase;color:var(--petrol-l);font-weight:600;margin-bottom:2px}
  h3.sub{font-size:16px;font-weight:700;margin:26px 0 10px;color:var(--petrol-d)}
  /* ---------- Cards ---------- */
  .grid{display:grid;gap:14px;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));margin-top:16px}
  .card{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:16px;box-shadow:var(--shadow)}
  .card h4{margin:0 0 6px;font-size:15px;color:var(--petrol-d)}
  .card p{margin:0;font-size:13.5px;color:var(--muted)}
  .card .num{font-family:var(--mono);font-size:11px;color:var(--amber);font-weight:700;letter-spacing:.1em}
  /* ---------- Scenario accordion ---------- */
  .lesson{margin-top:14px}
  .lhead{
    display:flex;align-items:center;gap:12px;margin:30px 0 8px;
    padding-bottom:8px;border-bottom:2px solid var(--line);
  }
  .lbadge{
    font-family:var(--mono);font-size:12px;font-weight:700;color:#fff;background:var(--petrol);
    padding:4px 9px;border-radius:7px;letter-spacing:.04em;flex:none;
  }
  .lhead h3{margin:0;font-size:17px;font-weight:800;color:var(--ink)}
  .lhead small{display:block;color:var(--muted);font-size:12.5px;font-weight:500}
  details.scn{
    background:var(--card);border:1px solid var(--line);border-radius:12px;
    margin:10px 0;overflow:hidden;box-shadow:var(--shadow);
  }
  details.scn>summary{
    list-style:none;cursor:pointer;padding:14px 16px;display:flex;align-items:center;gap:11px;
    font-weight:650;font-size:14.5px;user-select:none;
  }
  details.scn>summary::-webkit-details-marker{display:none}
  .chev{width:18px;height:18px;flex:none;transition:transform .2s;color:var(--petrol-l)}
  details.scn[open] .chev{transform:rotate(90deg)}
  .lvl{
    font-family:var(--mono);font-size:10px;letter-spacing:.06em;text-transform:uppercase;
    padding:3px 7px;border-radius:5px;font-weight:700;flex:none;margin-left:auto;
  }
  .lvl.basico{background:#e4f4ef;color:#137a5b}
  .lvl.inter{background:#fdf0dd;color:#9a6a12}
  .lvl.avanz{background:#fbe6df;color:#a5432a}
  .scnbody{padding:2px 16px 18px;border-top:1px solid var(--line)}
  .block{margin:16px 0 0}
  .block>.blabel{
    font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;
    color:var(--petrol-l);font-weight:700;margin-bottom:6px;display:flex;align-items:center;gap:7px;
  }
  .block ol,.block ul{margin:0;padding-left:20px}
  .block li{margin:4px 0;font-size:13.5px}
  .quote{
    background:var(--chip);border-left:3px solid var(--petrol-l);border-radius:0 8px 8px 0;
    padding:10px 13px;font-size:13.5px;font-style:italic;color:#33474e;margin:0;
  }
  /* pre-birth Q table */
  table.pbq{width:100%;border-collapse:collapse;font-size:13px;margin-top:2px}
  table.pbq td{border:1px solid var(--line);padding:7px 9px;vertical-align:top}
  table.pbq td:first-child{font-weight:600;color:var(--petrol-d);width:44%;background:#f9fcfc}
  /* vital chips */
  .vital{font-family:var(--mono);font-size:12px;font-weight:700;padding:2px 7px;border-radius:5px;white-space:nowrap;display:inline-block}
  .v-hr{background:#fbe7e6;color:var(--crit)}
  .v-hr.ok{background:#e2f5ee;color:var(--good)}
  .v-spo2{background:#eaf1fb;color:#2f6bb0}
  .step{font-size:13.5px;margin:5px 0;padding-left:2px}
  .mrsopa{display:flex;flex-wrap:wrap;gap:6px;margin-top:4px}
  .mrsopa span{background:#fff;border:1px solid var(--line);border-radius:7px;padding:6px 9px;font-size:12.5px}
  .mrsopa b{color:var(--coral);font-family:var(--mono)}
  /* ---------- Generic tables ---------- */
  .tblwrap{overflow-x:auto;border:1px solid var(--line);border-radius:12px;margin-top:14px;background:var(--card)}
  table.data{width:100%;border-collapse:collapse;font-size:13px;min-width:520px}
  table.data th{background:var(--petrol);color:#fff;text-align:left;padding:10px 12px;font-weight:600;font-size:12.5px;position:sticky;top:0}
  table.data td{border-bottom:1px solid var(--line);padding:10px 12px;vertical-align:top}
  table.data tr:nth-child(even) td{background:#fafcfc}
  table.data td:first-child{font-weight:600;color:var(--petrol-d)}
  /* ---------- Checklist ---------- */
  .clgroup{background:var(--card);border:1px solid var(--line);border-radius:12px;padding:6px 4px;margin-top:12px;box-shadow:var(--shadow)}
  .clgroup>h4{margin:10px 14px 6px;font-size:14px;color:var(--petrol-d);display:flex;align-items:center;gap:8px}
  .clgroup>h4 .tag{font-family:var(--mono);font-size:10px;background:var(--chip);color:var(--muted);padding:2px 6px;border-radius:4px;letter-spacing:.06em}
  .cli{display:flex;gap:11px;padding:9px 14px;border-top:1px solid #eef3f4;align-items:flex-start;cursor:pointer}
  .cli:first-of-type{border-top:0}
  .cli input{margin-top:3px;width:17px;height:17px;accent-color:var(--petrol);flex:none}
  .cli span{font-size:13.5px}
  .cli.done span{color:var(--muted);text-decoration:line-through}
  .toolbar{display:flex;gap:8px;flex-wrap:wrap;margin-top:14px}
  .btn{
    font-family:var(--sans);font-size:13px;font-weight:600;cursor:pointer;border-radius:9px;
    padding:9px 15px;border:1px solid var(--line);background:#fff;color:var(--petrol-d);
  }
  .btn:hover{border-color:var(--petrol-l);color:var(--petrol)}
  .btn.primary{background:var(--petrol);color:#fff;border-color:var(--petrol)}
  .btn.primary:hover{background:var(--petrol-d)}
  .progress{font-family:var(--mono);font-size:12px;color:var(--muted);margin-top:10px}
  /* ---------- Key behavioral skills ---------- */
  .kbs{display:grid;gap:8px;grid-template-columns:repeat(auto-fill,minmax(210px,1fr));margin-top:12px}
  .kbs div{background:var(--card);border:1px solid var(--line);border-left:3px solid var(--amber);border-radius:8px;padding:9px 12px;font-size:13px;color:var(--petrol-d);font-weight:500}
  /* ---------- Source list ---------- */
  .ref{background:var(--card);border:1px solid var(--line);border-radius:10px;padding:13px 15px;margin-top:10px;font-size:13.5px}
  .ref b{color:var(--petrol-d)}
  .pill{display:inline-block;font-family:var(--mono);font-size:10px;padding:3px 7px;border-radius:5px;letter-spacing:.05em;font-weight:700;margin-left:6px;vertical-align:middle}
  .pill.oficial{background:#e2f5ee;color:#137a5b}
  .pill.pend{background:#fdf0dd;color:#9a6a12}
  .callout{background:#eef4f5;border:1px solid var(--line);border-radius:12px;padding:14px 16px;margin-top:18px;font-size:13.5px;color:#334}
  .callout b{color:var(--petrol-d)}
  footer{max-width:1040px;margin:0 auto;padding:26px 16px 40px;color:var(--muted);font-size:12px;border-top:1px solid var(--line)}
  a{color:var(--petrol-l)}
  @media print{
    nav.tabs,.warn,.toolbar{display:none}
    .panel{display:block!important}
    details.scn{break-inside:avoid}
    details.scn>summary{pointer-events:none}
  }
  @media (max-width:520px){
    table.pbq td:first-child{width:52%}
    h1.title{font-size:22px}
  }
</style>
</head>
<body>

<header class="top">
  <div class="brandrow">
    <div class="logo">E</div>
    <div class="brandtxt"><b>EDUVESA</b><span>Centro de Educación en Reanimación Neonatal</span></div>
  </div>
  <h1 class="title">EDUVESA NRP 9.ª Edición · AAP/AHA<br>Escenarios Clínicos y Herramientas de Instructor</h1>
  <p class="subtitle">Toolkit para curso combinado NRP Essentials y Advanced · formato de práctica y evaluación secuencial</p>
  <span class="edition">NRP · 9th Edition · Guías AHA/AAP 2025</span>
</header>

<div class="warn"><div><b>Aviso:</b> Material de apoyo educativo. No sustituye el curso oficial NRP, el <i>Textbook of Neonatal Resuscitation</i> (9.ª ed.), la NRP Learning Platform ni la certificación AAP/AHA. Todo el contenido clínico procede de los documentos oficiales del Instructor Toolkit NRP 9.ª edición cargados en este proyecto.</div></div>

<nav class="tabs" aria-label="Secciones">
  <div class="tabsrow" role="tablist">
    <button class="tab" role="tab" aria-selected="true" data-p="inicio">Inicio</button>
    <button class="tab" role="tab" aria-selected="false" data-p="escenarios">Escenarios clínicos</button>
    <button class="tab" role="tab" aria-selected="false" data-p="cambios">Cambios 9.ª ed.</button>
    <button class="tab" role="tab" aria-selected="false" data-p="equipo">Checklist de equipo</button>
    <button class="tab" role="tab" aria-selected="false" data-p="debrief">Debriefing</button>
    <button class="tab" role="tab" aria-selected="false" data-p="constructor">Constructor</button>
    <button class="tab" role="tab" aria-selected="false" data-p="agenda">Agenda modelo</button>
    <button class="tab" role="tab" aria-selected="false" data-p="fuentes">Fuentes</button>
  </div>
</nav>

<main>

<!-- ============ INICIO ============ -->
<section class="panel active" id="inicio" role="tabpanel">
  <div class="eyebrow">Panel de inicio</div>
  <h2 class="sec">Toolkit de instructor NRP 9.ª edición</h2>
  <p class="lead">Plataforma modular para consultar los escenarios de práctica oficiales (Lecciones 2–7), los cambios científicos de la 9.ª edición y las herramientas de apoyo del Instructor Toolkit. Diseñada para consulta rápida en el aula y en la estación de simulación, desde el teléfono o la tablet.</p>

  <div class="grid">
    <div class="card"><div class="num">01</div><h4>Escenarios clínicos</h4><p>Los escenarios de práctica oficiales de las Lecciones 2 a 7, con objetivos, guion de apertura, 4 preguntas prebirth, pasos críticos con FC/SpO₂ y debriefing.</p></div>
    <div class="card"><div class="num">02</div><h4>Cambios de la 9.ª edición</h4><p>Tabla comparativa 8.ª vs 9.ª edición basada en el documento oficial <i>NRP 9th Edition Practice Changes</i>.</p></div>
    <div class="card"><div class="num">03</div><h4>Checklist de equipo</h4><p>El <i>Quick Equipment Checklist</i> interactivo, organizado por la nemotecnia Warm–Clear–Auscultate–Ventilate–Oxygenate–Intubate–Medicate.</p></div>
    <div class="card"><div class="num">04</div><h4>Debriefing</h4><p><i>Debrief the Debriefer Checklist</i>, preguntas modelo por lección y las 10 NRP Key Behavioral Skills.</p></div>
    <div class="card"><div class="num">05</div><h4>Constructor de escenarios</h4><p>El <i>Scenario Builder</i> oficial: habilidades por lección, factores de riesgo sugeridos y tabla de peso por edad gestacional.</p></div>
    <div class="card"><div class="num">06</div><h4>Agenda modelo</h4><p>Agenda del curso combinado Essentials/Advanced en formato de práctica y evaluación secuencial (proporción 1 instructor : 3–4 alumnos).</p></div>
  </div>

  <h3 class="sub">Público objetivo</h3>
  <p class="lead">Instructores y candidatos a instructor NRP, facilitadores de simulación, proveedores Essentials y Advanced, y equipos interprofesionales de sala de partos en hospitales, universidades y centros de simulación.</p>

  <h3 class="sub">Cómo usar este toolkit</h3>
  <ul class="block" style="padding-left:20px">
    <li>Usa las pestañas superiores para moverte entre módulos; en móvil se desplazan lateralmente.</li>
    <li>En <b>Escenarios clínicos</b>, toca cada tarjeta para desplegar el escenario completo.</li>
    <li>Los valores de <span class="vital v-hr">FC 40</span> y <span class="vital v-spo2">SpO₂ 68%</span> se muestran como lecturas de monitor; el rojo indica frecuencia cardíaca baja o crítica, el verde indica mejoría.</li>
    <li>El checklist de equipo y el de debriefing guardan tu progreso en el mismo dispositivo (almacenamiento local del navegador).</li>
    <li>Usa <b>Imprimir</b> (Ctrl/Cmd + P) para generar un PDF de cualquier sección; los escenarios se expanden automáticamente al imprimir.</li>
  </ul>

  <div class="callout">
    <b>Estado de actualización de fuentes.</b> Contenido alineado con los documentos oficiales del <b>NRP Instructor Toolkit, 9.ª edición</b> y las <b>Guías AHA/AAP 2025</b>. Última revisión de fuentes: verifica siempre contra la NRP Learning Platform y el <i>Textbook of Neonatal Resuscitation</i> (9.ª ed.) vigente antes de cada curso. Cualquier dato no confirmado por fuente oficial se marca como <span class="pill pend">pendiente de verificación</span>.
  </div>
</section>

<!-- ============ ESCENARIOS ============ -->
<section class="panel" id="escenarios" role="tabpanel">
  <div class="eyebrow">Escenarios de práctica oficiales</div>
  <h2 class="sec">Escenarios clínicos · Lecciones 2 a 7</h2>
  <p class="lead">Escenarios de práctica y evaluación del NRP Instructor Toolkit 9.ª edición. Cada uno inicia con las 4 preguntas prebirth; las respuestas del proveedor obstétrico, los valores de signos vitales y los pasos críticos se reproducen de los documentos oficiales. Contenido <span class="pill oficial">oficial NRP</span>.</p>
  <div id="scnroot"></div>
</section>

<!-- ============ CAMBIOS ============ -->
<section class="panel" id="cambios" role="tabpanel">
  <div class="eyebrow">NRP 9th Edition Practice Changes</div>
  <h2 class="sec">Cambios de la 8.ª a la 9.ª edición</h2>
  <p class="lead">Comparativa de las prácticas modificadas, del documento oficial <i>NRP 9th Edition Practice Changes</i>. <span class="pill oficial">oficial NRP</span></p>
  <div class="tblwrap">
    <table class="data">
      <thead><tr><th style="width:26%">Tema</th><th>Recomendación previa (8.ª ed.)</th><th>Recomendación 9.ª edición</th></tr></thead>
      <tbody>
        <tr><td>Algoritmo</td><td>—</td><td>Se añaden «Nacimiento» e «Iniciar plan de manejo del cordón» como acciones en el primer minuto. Se elimina la aspiración de «Calentar, secar, estimular, posicionar la vía aérea, aspirar si es necesario».</td></tr>
        <tr><td>Terminología</td><td>Se refiere a Ventilación con Presión Positiva (VPP).</td><td>Se refiere a «Ventilación», para consistencia con las guías AHA/AAP.</td></tr>
        <tr><td>Pinzamiento diferido del cordón</td><td>Diferir al menos 30–60 s en la mayoría de prematuros vigorosos; retraso similar razonable en RN de término vigorosos.</td><td>En la mayoría de RN que no requieren reanimación inmediata, diferir el pinzamiento al menos 60 segundos.</td></tr>
        <tr><td>Ordeño del cordón (milking)</td><td>Alternativa razonable a pinzamiento temprano en RN de término y pretérmino tardío no vigorosos (35–42 sem). No recomendado &lt;28 sem por riesgo de HIV.</td><td>Término/pretérmino tardío (35–42 sem) no vigorosos: alternativa razonable. Pretérmino 28–34 sem no vigorosos: evidencia insuficiente para recomendarlo de rutina. &lt;28 sem: no recomendado (riesgo de HIV grave).</td></tr>
        <tr><td>Tabla de SpO₂ objetivo</td><td>Comienza a 1 min: 1&nbsp;min 60–65%, 2&nbsp;min 65–70%, 3&nbsp;min 70–75%, 4&nbsp;min 75–80%, 5&nbsp;min 80–85%, 10&nbsp;min 85–95%.</td><td>Comienza a 2 min: 2&nbsp;min 65–70%, 3&nbsp;min 70–75%, 4&nbsp;min 75–80%, 5&nbsp;min 80–85%, 10&nbsp;min 85–95%.</td></tr>
        <tr><td>FiO₂ inicial en pretérmino</td><td>—</td><td>≥35 sem: 21%. 32–34 sem: 21–30%. &lt;29 sem (&lt;32): ≥30%.</td></tr>
        <tr><td>Frecuencia de ventilación</td><td>40 a 60 respiraciones/min.</td><td>30 a 60 respiraciones/min.</td></tr>
        <tr><td>PIP inicial</td><td>Iniciar con PIP 20–25 cm H₂O.</td><td>PIP inicial sugerida 25 cm H₂O. Rango aceptable: ≥32 sem 25–30 cm H₂O; &lt;32 sem 20–25 cm H₂O.</td></tr>
        <tr><td>Tiempo antes de pasos correctivos</td><td>Si la FC no aumenta en 15 s de VPP y no hay movimiento torácico, iniciar pasos correctivos.</td><td>Si la FC no aumenta en 15 a 30 s de ventilación y no hay movimiento torácico, iniciar pasos correctivos.</td></tr>
        <tr><td>Orden de pasos correctivos (MR SOPA)</td><td>Realizar los pasos de forma secuencial hasta lograr movimiento torácico.</td><td>Según la evaluación del RN y la situación clínica, elegir y priorizar los pasos con mayor probabilidad de ser útiles.</td></tr>
        <tr><td>Mascarilla laríngea</td><td>Vía aérea de rescate si la mascarilla facial falla y la intubación es inviable/fallida.</td><td>Puede usarse como dispositivo primario de ventilación (mascarilla facial o laríngea), no solo como vía aérea alternativa.</td></tr>
        <tr><td>Tamaño de tubo endotraqueal</td><td>&lt;1 kg / &lt;28 sem → 2.5; 1–2 kg / 28–34 sem → 3.0; &gt;2 kg / &gt;34 sem → 3.5.</td><td>Ajustada, con recomendación para RN &lt;800 g. Corte para tubo 2.5 mm hasta 1200 g y para 3.0 mm hasta 2200 g. Tubo 2.0 mm ID (opcional) puede considerarse.</td></tr>
        <tr><td>Profundidad del tubo endotraqueal</td><td>Marca de inserción adyacente al labio del RN (punta-a-labio).</td><td>Marca adyacente al borde anterior de la encía superior (maxilar) en la línea media (punta-a-encía).</td></tr>
      </tbody>
    </table>
  </div>
  <div class="callout"><b>Regla de la tabla.</b> No completar con supuestos. Cualquier cambio sin fuente oficial disponible debe registrarse como <span class="pill pend">pendiente de verificación</span> contra material oficial AAP/AHA NRP 9.ª edición.</div>
</section>

<!-- ============ EQUIPO ============ -->
<section class="panel" id="equipo" role="tabpanel">
  <div class="eyebrow">Quick Equipment Checklist</div>
  <h2 class="sec">Checklist rápido de equipo</h2>
  <p class="lead">Suministros y equipo esenciales en la cuna de calor radiante para la mayoría de las reanimaciones neonatales. Adáptalo a las necesidades de tu unidad y verifica antes de cada nacimiento. <span class="pill oficial">oficial NRP</span></p>
  <div id="equiproot"></div>
  <div class="toolbar">
    <button class="btn" id="eq-reset">Reiniciar checklist</button>
    <button class="btn primary" onclick="window.print()">Imprimir / PDF</button>
  </div>
  <div class="progress" id="eq-prog"></div>
</section>

<!-- ============ DEBRIEF ============ -->
<section class="panel" id="debrief" role="tabpanel">
  <div class="eyebrow">Debrief the Debriefer</div>
  <h2 class="sec">Debriefing y habilidades conductuales</h2>
  <p class="lead">Checklist para reflexionar sobre tu facilitación y debriefing tras una experiencia de coenseñanza, y para dar retroalimentación a otro instructor. <span class="pill oficial">oficial NRP</span></p>
  <div id="debriefroot"></div>
  <div class="toolbar">
    <button class="btn" id="db-reset">Reiniciar checklist</button>
    <button class="btn primary" onclick="window.print()">Imprimir / PDF</button>
  </div>
  <div class="progress" id="db-prog"></div>

  <h3 class="sub">NRP Key Behavioral Skills</h3>
  <p class="lead">Las 10 habilidades conductuales clave que aparecen en cada escenario de práctica.</p>
  <div class="kbs">
    <div>Conoce tu entorno</div>
    <div>Usa la información disponible</div>
    <div>Anticípate y planifica</div>
    <div>Identifica claramente a un líder de equipo</div>
    <div>Comunícate con eficacia</div>
    <div>Delega la carga de trabajo de forma óptima</div>
    <div>Distribuye la atención con criterio</div>
    <div>Usa los recursos disponibles</div>
    <div>Pide ayuda adicional cuando se necesite</div>
    <div>Mantén un comportamiento profesional</div>
  </div>

  <h3 class="sub">Preguntas de debriefing frecuentes (documentos oficiales)</h3>
  <ul class="block" style="padding-left:20px">
    <li>¿Cuál es el tema más importante a discutir en este debriefing?</li>
    <li>¿Qué salió bien durante esta reanimación?</li>
    <li>¿Qué harías diferente ante esta situación en un escenario futuro?</li>
    <li>¿Tienes comentarios o sugerencias para tus compañeros de equipo? ¿Para el líder?</li>
    <li>Da un ejemplo de cómo usaste al menos una de las NRP Key Behavioral Skills.</li>
    <li><i>Si hubo errores significativos:</i> ¿Qué pasó? ¿Qué debió pasar? ¿Qué pudiste hacer para que ocurriera lo correcto?</li>
  </ul>
</section>

<!-- ============ CONSTRUCTOR ============ -->
<section class="panel" id="constructor" role="tabpanel">
  <div class="eyebrow">NRP Scenario Builder</div>
  <h2 class="sec">Constructor de escenarios</h2>
  <p class="lead">Habilidades objetivo por lección y factores de riesgo sugeridos para elaborar escenarios propios. Los escenarios se basan en objetivos de aprendizaje; «Demostrar las NRP Key Behavioral Skills» siempre es un objetivo. Los alumnos inician con las 4 preguntas prebirth. <span class="pill oficial">oficial NRP</span></p>

  <div class="tblwrap">
    <table class="data">
      <thead><tr><th style="width:20%">Lección</th><th>Habilidades objetivo</th><th>Factores de riesgo adicionales (ejemplos)</th></tr></thead>
      <tbody>
        <tr><td>L3 · Pasos iniciales</td><td>Evaluación rápida (¿término? ¿tono? ¿respira?), pasos iniciales (con la madre / en cuna), oximetría y manejo de O₂, O₂ de flujo libre.</td><td>Sin factores aparentes · hipertensión materna · sin control prenatal · EG &lt;36 0/7 sem.</td></tr>
        <tr><td>L4 · Ventilación</td><td>Pasos iniciales, ventilación + MR SOPA (sin vía aérea alternativa aún), oximetría y SpO₂, CPAP y/o O₂ suplementario, sonda orogástrica.</td><td>Preeclampsia · terapia con magnesio · RCIU · líquido meconial.</td></tr>
        <tr><td>L5 · Intubación endotraqueal</td><td>Pasos iniciales + ventilación y MR SOPA, oximetría y manejo de O₂, intubación y/o mascarilla laríngea.</td><td>Patrón categoría III de FCF · madre febril con feto taquicárdico · presentación anómala (podálica).</td></tr>
        <tr><td>L6 · Compresiones torácicas</td><td>Pasos iniciales + ventilación y MR SOPA, intubación/mascarilla laríngea, compresiones torácicas, monitor cardíaco y electrodos.</td><td>Convulsiones maternas (eclampsia) · extracción por vacío fallida · bradicardia fetal.</td></tr>
        <tr><td>L7 · Medicamentos (con CVU)</td><td>Todo lo anterior + colocación de catéter venoso umbilical y epinefrina, administración de volumen (SSN / concentrado eritrocitario O Rh−), acceso intraóseo si procede.</td><td>Cesárea de emergencia con anestesia general. Para volumen: trauma materno/fetal · prolapso o circular apretada de cordón · sangrado vaginal extenso · hemorragia feto-materna · vasa previa sangrante · laceración placentaria.</td></tr>
        <tr><td>Vía aérea obstruida</td><td>Sin movimiento torácico hasta intubar y aspirar con catéter o aspirador de meconio.</td><td>Factores de riesgo de L3, incluida la ausencia de riesgo.</td></tr>
      </tbody>
    </table>
  </div>

  <h3 class="sub">Peso aproximado según edad gestacional</h3>
  <div class="tblwrap">
    <table class="data">
      <thead><tr><th>Edad gestacional</th><th>Peso aprox.</th><th>Edad gestacional</th><th>Peso aprox.</th></tr></thead>
      <tbody>
        <tr><td>23–24 sem</td><td>500–600 g</td><td>33–34 sem</td><td>1500–1800 g</td></tr>
        <tr><td>25–26 sem</td><td>700–800 g</td><td>35–37 sem</td><td>1900–2400 g</td></tr>
        <tr><td>27–29 sem</td><td>900–1000 g</td><td>38–40 sem</td><td>2500–3100 g</td></tr>
        <tr><td>30–32 sem</td><td>1100–1400 g</td><td>41–43 sem</td><td>3200–4200 g</td></tr>
      </tbody>
    </table>
  </div>

  <div class="callout"><b>Las 4 preguntas prebirth.</b> 1) ¿Edad gestacional? · 2) ¿Líquido amniótico claro? (usar meconial solo en término/postérmino) · 3) ¿Factores de riesgo adicionales? · 4) ¿Plan de manejo del cordón umbilical? (acordar con el proveedor obstétrico).</div>
</section>

<!-- ============ AGENDA ============ -->
<section class="panel" id="agenda" role="tabpanel">
  <div class="eyebrow">Sample Course Agenda</div>
  <h2 class="sec">Agenda modelo · Essentials + Advanced</h2>
  <p class="lead">Curso combinado NRP Essentials y Advanced en formato de práctica y evaluación secuencial. Proporción recomendada <b>1 instructor : 3–4 alumnos</b>. La duración depende del alcance de los roles, el número de participantes y de instructores. <span class="pill oficial">oficial NRP</span></p>

  <h3 class="sub">Objetivos de aprendizaje del curso</h3>
  <ul class="block" style="padding-left:20px">
    <li>Localizar suministros y equipo de reanimación neonatal, incluido el material para reanimación compleja.</li>
    <li>Preparar un nacimiento y evaluar el riesgo perinatal preguntando al equipo obstétrico las 4 preguntas prebirth; indicar cuándo, según protocolo, una persona calificada puede atender un nacimiento.</li>
    <li>Realizar un chequeo estandarizado de equipo, preparando los dispositivos de ventilación para su uso.</li>
    <li>Asumir la responsabilidad única de un RN al nacer: oximetría, O₂ de flujo libre, ventilación, mascarilla laríngea si se requiere y activación de ayuda de emergencia.</li>
    <li><b>Advanced:</b> usar las NRP Key Behavioral Skills en reanimación compleja; iniciar CPAP, intubar (o asistir), realizar compresiones, colocar CVU de emergencia (o asistir) y administrar epinefrina y volumen, en la secuencia del algoritmo 9.ª edición.</li>
  </ul>

  <div class="tblwrap">
    <table class="data">
      <thead><tr><th style="width:16%">Horario</th><th>Actividad</th></tr></thead>
      <tbody>
        <tr><td>8:00–8:05</td><td>Bienvenida, presentaciones y aspectos administrativos (créditos, acuerdo de confidencialidad, expectativas post-curso).</td></tr>
        <tr><td>8:05–8:10</td><td>Cómo funciona el curso y expectativas para su aprobación; reglas básicas y confidencialidad.</td></tr>
        <tr><td>8:10–8:20</td><td>Los instructores demuestran un escenario de simulación (desde las 4 preguntas prebirth hasta después de la ventilación) y el debriefing.</td></tr>
        <tr><td>8:20–8:30</td><td>Los equipos van a su estación de aprendizaje/habilidades: orientación al entorno, localización de material y forma en que el maniquí transmite sus signos vitales.</td></tr>
        <tr><td>8:30–9:00</td><td><b>Lecciones 2 y 3.</b> Knowledge Check; el instructor demuestra las 4 preguntas prebirth, chequeo de equipo, evaluación rápida, pasos iniciales, oximetría y O₂ de flujo libre. Los alumnos practican y lideran los escenarios de práctica de L3.</td></tr>
        <tr><td>9:00–9:30</td><td><b>Lección 4 · Parte 1: Ventilación asistida</b> (en parejas). MR SOPA, solicitud de ayuda, reporte de FC y movimiento torácico, sonda orogástrica y CPAP si aplica.</td></tr>
        <tr><td>9:30–10:00</td><td><b>Lección 4 · Parte 2: Mascarilla laríngea</b> (en parejas). Colocación, fijación, ventilación, sonda OG por el puerto si existe, y retiro. <i>Segundo y último punto de evaluación del curso Essentials.</i></td></tr>
        <tr><td>10:00–10:30</td><td><b>Simulación y debriefing</b> (componente obligatorio). Repetir escenarios o crear nuevos con el Scenario Builder.</td></tr>
        <tr><td>10:30–10:40</td><td>Descanso. Los alumnos Advanced se reportan a su estación.</td></tr>
        <tr><td>10:40–11:15</td><td><b>Lecciones 5 y 6 · Intubación endotraqueal y compresiones.</b> La práctica puede combinar intubación y compresiones; incluye el uso del aspirador traqueal en sospecha de vía aérea obstruida.</td></tr>
        <tr><td>(continúa)</td><td><b>Lección 7 · Medicamentos y CVU.</b> Epinefrina y volumen, colocación de catéter venoso umbilical de emergencia, y escenario integrador como Comprehensive Skills Test para proveedores Advanced.</td></tr>
      </tbody>
    </table>
  </div>
  <p class="lead" style="margin-top:14px">Cuando el alumno puede liderar al equipo en la secuencia correcta del algoritmo 9.ª edición y ejecutar las habilidades con técnica apropiada, avanza a la siguiente sección de práctica y evaluación.</p>
</section>

<!-- ============ FUENTES ============ -->
<section class="panel" id="fuentes" role="tabpanel">
  <div class="eyebrow">Control de fuentes</div>
  <h2 class="sec">Bibliografía y control de fuentes</h2>
  <p class="lead">Fuentes primarias empleadas para este toolkit. Amplíalas únicamente con documentos oficiales AAP/AHA, guías ILCOR/AHA-AAP o literatura revisada por pares.</p>

  <div class="ref"><b>American Academy of Pediatrics.</b> Neonatal Resuscitation Program, 9th Edition. AAP, 2025. <span class="pill oficial">oficial</span></div>
  <div class="ref"><b>American Academy of Pediatrics.</b> Textbook of Neonatal Resuscitation, 9th Edition. AAP, 2025. <span class="pill oficial">oficial</span></div>
  <div class="ref"><b>AHA / AAP.</b> 2025 Guidelines for CPR and Emergency Cardiovascular Care: Part 5, Neonatal Resuscitation. <i>Circulation</i>, 2025. <span class="pill oficial">oficial</span></div>
  <div class="ref"><b>American Heart Association.</b> Neonatal Resuscitation Program, NRP Provider Course. AHA International, 2025. <span class="pill oficial">oficial</span></div>

  <h3 class="sub">Documentos del Instructor Toolkit usados en este toolkit</h3>
  <div class="ref">NRP 9th Edition — Practice Scenarios, Lecciones 2 a 7 <span class="pill oficial">oficial</span></div>
  <div class="ref">NRP 9th Edition — Quick Equipment Checklist <span class="pill oficial">oficial</span></div>
  <div class="ref">NRP 9th Edition — Debrief the Debriefer Checklist <span class="pill oficial">oficial</span></div>
  <div class="ref">NRP 9th Edition — Practice Changes Table (8.ª vs 9.ª ed.) <span class="pill oficial">oficial</span></div>
  <div class="ref">NRP 9th Edition — Scenario Builder <span class="pill oficial">oficial</span></div>
  <div class="ref">NRP 9th Edition — ITK Agenda, Instructor-led (formato secuencial) <span class="pill oficial">oficial</span></div>

  <div class="callout">
    <b>Diferenciación de contenido.</b>
    <span class="pill oficial">oficial NRP</span> contenido tomado de los documentos oficiales del toolkit ·
    <span class="pill pend">pendiente de verificación</span> cualquier dato aún no confirmado contra material oficial AAP/AHA NRP 9.ª edición.
    Este material es de apoyo educativo y no sustituye el curso oficial NRP, el manual oficial, la NRP Learning Platform ni la certificación AAP/AHA.
  </div>
</section>

</main>

<footer>
  EDUVESA · Centro de Educación en Reanimación Neonatal — Toolkit de instructor NRP 9.ª edición (AAP/AHA). Material de apoyo educativo. No sustituye el curso oficial, el manual, la plataforma ni la certificación AAP/AHA. Página autónoma sin dependencias externas.
</footer>

<script>
/* ---------------- Data: Practice Scenarios (official NRP 9th ed.) ---------------- */
const V = {
  hr:(n,ok)=>`<span class="vital v-hr${ok?' ok':''}">FC ${n}</span>`,
  sp:(n)=>`<span class="vital v-spo2">SpO₂ ${n}</span>`
};

const lessons = [
 {
  n:"L2", title:"Anticipación y preparación para la reanimación",
  sub:"Evaluación de riesgo, briefing pre-reanimación y chequeo de equipo",
  scenarios:[
   {
    name:"Variante A — 38 semanas, sin factores de riesgo conocidos",
    level:"basico", levelLabel:"Básico",
    objectives:[
     "Determinar el proceso para identificar factores de riesgo antepartum e intrapartum y decidir quién atiende el nacimiento.",
     "Demostrar un briefing de equipo pre-reanimación.",
     "Demostrar un método organizado de chequeo de equipo previo al nacimiento.",
     "Identificar el proceso para llamar por ayuda adicional si se requiere."
    ],
    intro:"«Se le notifica que una persona gestante ingresó al hospital en trabajo de parto activo. Prepare a su equipo para el nacimiento y verifique sus suministros y equipo. Diga en voz alta sus pensamientos y acciones para que yo sepa qué está pensando y haciendo.»",
    pbq:[
     ["¿Edad gestacional esperada?","«38 semanas de gestación.»"],
     ["¿Líquido amniótico claro?","«Líquido claro.»"],
     ["¿Factores de riesgo adicionales?","«Sin factores de riesgo conocidos.»"],
     ["¿Plan de manejo del cordón?","«60 s de pinzamiento diferido, salvo que el RN requiera reanimación inmediata; entonces pinzo y corto.»"]
    ],
    steps:[
     "Ensamblar el equipo según los factores de riesgo. Con baja probabilidad de reanimación, 1 persona calificada puede atender el nacimiento.",
     "Si asiste 1 sola persona: conoce las respuestas a las 4 preguntas, determina el equipo necesario y sabe cómo pedir ayuda.",
     "Chequeo de equipo con rutina organizada (Warm–Clear–Auscultate–Ventilate–Oxygenate–Intubate–Medicate)."
    ],
    debrief:[
     "¿Qué factores determinaron tu decisión sobre quién atendería el nacimiento?",
     "Si todo el equipo está presente, ¿cuánto tardas en confirmar que todo está listo? ¿Cómo reducir ese tiempo?",
     "¿Cuáles NRP Behavioral Skills se demuestran durante la preparación?"
    ]
   },
   {
    name:"Variante B — 29 semanas, con factores de riesgo",
    level:"inter", levelLabel:"Intermedio",
    objectives:["Mismos objetivos de L2, con equipo completo por prematuridad y preeclampsia."],
    intro:"Mismo guion de apertura; cambian las respuestas prebirth.",
    pbq:[
     ["¿Edad gestacional esperada?","«29 semanas de gestación.»"],
     ["¿Líquido amniótico claro?","«Líquido claro.»"],
     ["¿Factores de riesgo adicionales?","«Preeclampsia.»"],
     ["¿Plan de manejo del cordón?","«60 s de pinzamiento diferido, salvo que requiera reanimación inmediata.»"]
    ],
    steps:[
     "Con factores de riesgo presentes, al menos 2 personas calificadas deben estar presentes únicamente para el RN.",
     "Realizar briefing pre-reanimación: identificar líder, valorar riesgos, discutir complicaciones y plan, delegar tareas, designar quién documenta.",
     "Chequeo de equipo. Extras para <32 sem: bolsa/plástico y colchón térmico; temperatura de la sala 23–25 °C. FiO₂ inicial 21–30% (32–34 sem) o >30% (<32 sem). T-piece: PIP 20–25 cm H₂O y PEEP 5 cm H₂O para <32 sem."
    ],
    debrief:["Mismas preguntas de debriefing de la Lección 2."]
   }
  ]
 },
 {
  n:"L3", title:"Pasos iniciales del cuidado del recién nacido",
  sub:"4 opciones · evaluación rápida, pasos iniciales, oximetría y O₂ de flujo libre",
  scenarios:[
   {
    name:"Opción 1 — RN de término vigoroso, puede quedarse con el progenitor",
    level:"basico", levelLabel:"Básico",
    objectives:["Evaluación rápida (¿término? ¿tono? ¿respira/llora?).","Pasos iniciales piel con piel.","Aplicar NRP Key Behavioral Skills."],
    intro:"«Le llaman a atender un parto vaginal. La persona gestante está en trabajo de parto activo con membranas rotas. ¿Cómo se prepara y realiza los pasos iniciales? Diga sus pensamientos y acciones en voz alta.»",
    pbq:[
     ["¿Edad gestacional?","«39 semanas.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«Sin factores adicionales.»"],
     ["¿Plan del cordón?","«Al menos 60 s de pinzamiento diferido, salvo que requiera reanimación.»"]
    ],
    steps:[
     "Evaluación rápida: ¿Término? Sí · ¿Tono? Sí · ¿Respira/llora? Sí (está llorando).",
     "El RN se queda con el progenitor para los pasos iniciales: piel con piel, secar, posicionar la vía aérea; limpiar secreciones con paño solo si es necesario.",
     "Fin: evaluación continua de respiración, FC, tono, actividad, color y temperatura."
    ],
    vitals:"", debrief:[
     "¿Qué factores determinaron quién atendería estos nacimientos?",
     "¿Cómo supiste si el RN requería pasos iniciales en la cuna, oximetría o O₂ suplementario?",
     "Da un ejemplo de uso de una NRP Key Behavioral Skill."
    ]
   },
   {
    name:"Opción 2 — Término vigoroso, líquido meconial y cianosis persistente (equipo de 2)",
    level:"inter", levelLabel:"Intermedio",
    objectives:["Oximetría y manejo de O₂ de flujo libre.","Trabajo en equipo de 2 personas."],
    intro:"Mismo guion; nacimiento con líquido meconial.",
    pbq:[
     ["¿Edad gestacional?","«41 semanas.»"],
     ["¿Líquido claro?","«Líquido con meconio.»"],
     ["¿Factores de riesgo?","«Ninguno además del meconio.»"],
     ["¿Plan del cordón?","«Al menos 60 s de pinzamiento diferido, salvo que requiera reanimación.»"]
    ],
    steps:[
     "Con meconio como único factor: al menos 2 personas calificadas presentes solo para el RN, con alguien con habilidad de intubación disponible de inmediato.",
     "Evaluación inicial: Término Sí · Tono Sí · Respira/llora Sí. Puede quedarse con el progenitor para pasos iniciales.",
     "A los 4 minutos el RN está notablemente cianótico. Respira sin dificultad. Ausculta FC.",
     `Auscultación: ${V.hr(140,true)}. Coloca sensor de oximetría en mano/muñeca derecha → ${V.sp("68%")}.`,
     `Administra O₂ de flujo libre: ajusta blender a 30% con técnica correcta. Monitoriza y ajusta según oximetría dentro del rango objetivo; intenta destetar el O₂.`,
     "Fin: comunica con el equipo neonatal según protocolo; actualiza a los padres y plan de cuidado post-reanimación."
    ],
    debrief:["Mismas preguntas de debriefing de la Lección 3."]
   },
   {
    name:"Opción 3 — Término requiere pasos iniciales en cuna, regresa a piel con piel",
    level:"inter", levelLabel:"Intermedio",
    objectives:["Reconocer necesidad de pasos iniciales en cuna de calor radiante."],
    intro:"Mismo guion; desaceleraciones repetidas de FCF.",
    pbq:[
     ["¿Edad gestacional?","«Término.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«Desaceleraciones repetidas de FCF en los últimos 15 minutos.»"],
     ["¿Plan del cordón?","«Al menos 60 s de pinzamiento diferido, salvo que requiera reanimación.»"]
    ],
    steps:[
     "Al menos 2 personas calificadas por presencia de factores de riesgo. Briefing pre-reanimación.",
     "Evaluación rápida: Término Sí · Tono No · Respira/llora No.",
     "Pasos iniciales en cuna: recibe, calienta, seca y retira ropa húmeda, posiciona la vía aérea, estimula y aspira si es necesario.",
     `Verifica respiración: el RN llora. Ausculta ${V.hr(120,true)}.`,
     "Fin: envuelve, regresa al progenitor piel con piel; monitoriza respiración, tono, actividad, color y temperatura."
    ],
    debrief:["Mismas preguntas de debriefing de la Lección 3."]
   },
   {
    name:"Opción 4 — Pretérmino tardío, líquido claro, permanece apneico",
    level:"avanz", levelLabel:"Avanzado",
    objectives:["Reconocer necesidad de ventilación asistida y activar ayuda."],
    intro:"Mismo guion; madre con fiebre.",
    pbq:[
     ["¿Edad gestacional?","«36 semanas.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«La madre tiene fiebre.»"],
     ["¿Plan del cordón?","«Al menos 60 s de pinzamiento diferido, salvo que requiera reanimación.»"]
    ],
    steps:[
     "Al menos 2 personas calificadas. Briefing pre-reanimación.",
     "Evaluación rápida: Término No (aparenta 36 sem) · Tono No · Respira/llora No.",
     "Pasos iniciales en cuna: calienta, seca, posiciona, estimula, aspira si es necesario.",
     `Verifica respiración: «apneico». ${V.hr(70)} si se evalúa. Indica necesidad de ventilación asistida y usa el método estandarizado para pedir ayuda.`,
     "Fin de escenario."
    ],
    debrief:["Mismas preguntas de debriefing de la Lección 3."]
   }
  ]
 },
 {
  n:"L4", title:"Ventilación asistida, mascarilla laríngea, sonda OG y CPAP",
  sub:"3 opciones · Comprehensive Skills Test para proveedores NRP Essentials",
  scenarios:[
   {
    name:"Opción 1 — Término con factores de riesgo requiere ventilación asistida",
    level:"inter", levelLabel:"Intermedio",
    objectives:["Identificar necesidad de ventilación y demostrar técnica correcta.","Evaluar respuesta y realizar MR SOPA.","Suspender ventilación; CPAP y sonda OG (opcional).","Aplicar NRP Key Behavioral Skills."],
    intro:"«Le llaman a atender un parto vaginal. El trabajo de parto progresa rápido. Demuestre cómo se prepara. Diga sus pensamientos y acciones en voz alta.»",
    pbq:[
     ["¿Edad gestacional?","«38 semanas.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«Hipertensión inducida por el embarazo; parto inducido a las 38 sem; varias desaceleraciones tardías de FCF.»"],
     ["¿Plan del cordón?","«60 s de pinzamiento diferido, salvo que requiera reanimación.»"]
    ],
    steps:[
     "≥2 personas calificadas. Briefing pre-reanimación. Chequeo de equipo.",
     "Evaluación inicial: Término Sí · Tono No · Respira/llora No.",
     `Pasos iniciales en cuna. ¿Respira? No (${V.hr(60)} si se evalúa). Indica necesidad de ventilación.`,
     "Inicia ventilación antes de los 60 s: mascarilla correcta, 21% O₂ (aire ambiente), PIP inicial 25 cm H₂O (PEEP 5 con T-piece/bolsa), frecuencia 30–60/min. Coloca oximetría (sin señal). Monitor cardíaco (opcional).",
     `A los 30 s de ventilación verifica FC: ${V.hr(40)}, no aumenta. «Sin movimiento torácico.»`
    ],
    mrsopa:true,
    afterMrsopa:[
     "«El tórax se mueve AHORA. Continúa la ventilación 30 s.» Coloca electrodos si aún no.",
     `A los 30 s de ventilación efectiva: ${V.hr(120,true)} · ${V.sp("64%")} · «esfuerzo respiratorio ocasional». Continúa y ajusta O₂ por oximetría.`,
     `${V.hr(140,true)} · ${V.sp("74%")} · esfuerzo respiratorio en aumento y mejor tono. Suspende gradualmente la ventilación.`,
     `${V.hr(140,true)} · ${V.sp("70%")} → evalúa necesidad de O₂ de flujo libre; inícialo con técnica correcta.`,
     `${V.hr(140,true)} · ${V.sp("90%")} → destetar y suspender O₂ manteniendo SpO₂ objetivo. Planifica cuidado post-reanimación.`
    ],
    optional:"Opcional (CPAP + sonda OG): tras suspender ventilación, respiración laboriosa y quejido, SpO₂ 80%. Aplica CPAP 5 cm H₂O, ajusta O₂ por oximetría. Mide e inserta sonda orogástrica (puente nasal→lóbulo→punto medio entre xifoides y ombligo), aspira contenido gástrico, deja abierta como respiradero y fija a la mejilla.",
    debrief:["¿Cuál es el tema más importante a discutir?","¿Qué salió bien?","¿Qué harías diferente en un escenario futuro?","¿Comentarios para el equipo o el líder?","Da un ejemplo de una NRP Key Behavioral Skill."]
   },
   {
    name:"Opción 2 — Término sin factores de riesgo requiere ventilación inesperada (1 persona)",
    level:"inter", levelLabel:"Intermedio",
    objectives:["Asumir responsabilidad única del RN y activar al equipo de reanimación."],
    intro:"Diseñado para 1 persona asignada al cuidado del RN al nacer.",
    pbq:[
     ["¿Edad gestacional?","«39 semanas.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«Sin factores adicionales.»"],
     ["¿Plan del cordón?","«Al menos 60 s de pinzamiento diferido, salvo que requiera reanimación.»"]
    ],
    steps:[
     "Atendido por 1 persona calificada. Chequeo de equipo.",
     "Evaluación inicial: Término Sí · Tono No · Respira/llora No.",
     `Pasos iniciales. ¿Respira? No (${V.hr(70)}). Indica ventilación y usa proceso estandarizado para llamar al equipo.`,
     "Inicia ventilación en 60 s: posición de olfateo, mascarilla correcta, 21% O₂, PIP 25 cm H₂O (PEEP 5), 30–60/min. Pide ayuda hasta que llegue el equipo. Coloca oximetría; monitor opcional.",
     `En 30 s verifica FC: ${V.hr(70)}, no aumenta · ${V.sp("66%")}. «Sin movimiento torácico.»`
    ],
    mrsopa:true,
    afterMrsopa:[
     "«El tórax se mueve AHORA. Continúa 30 s.»",
     `A los 30 s: ${V.hr(120,true)} · ${V.sp("72%")} · esfuerzo respiratorio en aumento. Suspende gradualmente.`,
     `${V.hr(140,true)} · ${V.sp("75%")} y en aumento · respira con regularidad, mejor tono.`,
     "Fin: suspende ventilación, monitoriza signos, comunica con el equipo que llega y actualiza a los padres."
    ],
    debrief:["Mismas preguntas de debriefing de la Lección 4."]
   },
   {
    name:"Opción 3 — Difícil de ventilar con mascarilla facial, requiere mascarilla laríngea",
    level:"avanz", levelLabel:"Avanzado",
    objectives:["Reconocer usos y límites de la mascarilla laríngea.","Insertar y retirar la mascarilla laríngea con técnica correcta."],
    intro:"Mismo guion de apertura.",
    pbq:[
     ["¿Edad gestacional?","«40 semanas.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«Algunas desaceleraciones de FCF en los últimos 20 minutos.»"],
     ["¿Plan del cordón?","«Al menos 60 s de pinzamiento diferido, salvo que requiera reanimación.»"]
    ],
    steps:[
     "Ensamblar equipo según riesgo; briefing si es un equipo.",
     "Evaluación inicial: Término Sí · Tono No · Respira/llora No.",
     `Pasos iniciales. ¿Respira? No (${V.hr(70)}). Ventilación en 60 s con 21% O₂, PIP 25 cm H₂O (PEEP 5), 30–60/min. Oximetría; monitor opcional.`,
     `En 30 s: ${V.hr(70)}, no aumenta · ${V.sp("67%")}. «Sin movimiento torácico.»`
    ],
    mrsopa:true,
    afterMrsopa:[
     `Tras MR SOPA sin movimiento torácico y ${V.hr(60)} que no aumenta → prepara mascarilla laríngea. Coloca electrodos y monitor.`,
     "Obtiene mascarilla laríngea neonatal (y jeringa de 5 mL si requiere inflado) y sonda 5F/6F si tiene puerto. Si requiere inflado: prueba el borde con ≤4 mL de aire y retíralo.",
     "Inserción: de pie a la cabecera, posición de olfateo. El fondo cerrado hacia el paladar y el tazón abierto hacia el mentón; desliza siguiendo el contorno del paladar hasta resistencia definitiva. Infla el borde con 2–4 mL si aplica. Conecta detector de CO₂ y dispositivo de ventilación.",
     "Confirma inserción: movimiento torácico simétrico, ruidos bilaterales y cambio de color del detector de CO₂ en 8–10 ventilaciones. Ventila 30 s y fija con cinta.",
     `A los 30 s: ${V.hr(120,true)} · ${V.sp("74%")} · respiraciones espontáneas ocasionales. Disminuye frecuencia y presión; estimula.`,
     `${V.hr(140,true)} · ${V.sp("78%")} y en aumento · «el bebé llora». Retira la mascarilla laríngea (aspira, desinfla el borde si aplica). Fin: monitoriza y actualiza a los padres.`
    ],
    debrief:["Mismas preguntas de debriefing de la Lección 4."]
   }
  ]
 },
 {
  n:"L5", title:"Intubación endotraqueal",
  sub:"2 opciones · roles de operador y asistente, confirmación y aspiración traqueal",
  scenarios:[
   {
    name:"Opción 1 — Término con factores de riesgo requiere intubación endotraqueal",
    level:"avanz", levelLabel:"Avanzado",
    objectives:["Identificar necesidad de intubación y elegir tubo por peso.","Técnica del operador y rol del asistente.","Confirmar posición traqueal: FC en aumento, cambio de color de CO₂, ruidos bilaterales y movimiento torácico."],
    intro:"«Le llaman a un nacimiento complicado por patrón categoría III de FCF. Primigesta de 28 años a las 39 sem. Demuestre cómo se prepara.»",
    pbq:[
     ["¿Edad gestacional?","«39 semanas.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«La persona gestante tiene fiebre.»"],
     ["¿Plan del cordón?","«60 s de pinzamiento diferido, salvo que requiera reanimación.»"]
    ],
    steps:[
     "≥2 personas calificadas. Briefing. Chequeo de equipo (incluye material de intubación).",
     "Evaluación rápida: aparenta término · sin tono · no respira.",
     `Pasos iniciales: recibe, seca, estimula frotando la espalda, posiciona, aspira. ¿Respira? No (${V.hr(40)}).`,
     "Ventilación en 60 s: olfateo, mascarilla correcta, 21% O₂, PIP 25 (PEEP 5), 30–60/min. Oximetría; monitor opcional.",
     `En 15–30 s: ${V.hr(40)}, no aumenta, sin señal de oximetría. «Sin movimiento torácico.» Realiza MR SOPA priorizando los pasos más útiles. Coloca electrodos anticipando intubación.`
    ],
    intubation:true,
    afterIntub:[
     `Si NO se inserta: sin cambio de color, tórax no se mueve, ${V.hr(60)} → retira tubo, reanuda ventilación con mascarilla, repite intento o indica mascarilla laríngea.`,
     `Si se inserta bien: cambia el color del CO₂; ${V.hr(70,true)} en ascenso. Continúa ventilación 30–60 s. El asistente verifica profundidad por tabla peso/EG o NTL (profundidad cm = NTL + 1) medida al borde anterior de la encía superior; fija el tubo.`,
     `A los 30 s: apneico, ${V.hr(70,true)} en aumento, ${V.sp("67%")}. Ajusta O₂ por oximetría.`,
     `A los 30 s más: ${V.hr(">100",true)} en aumento, ${V.sp("72%")}. Fin: soporte ventilatorio y O₂ por tabla objetivo; actualiza a los padres.`
    ],
    debrief:[
     "¿Qué salió bien? ¿Cuál es el tema más importante a discutir?",
     "¿Cuándo decidiste usar el monitor cardíaco y cómo te ayudó?",
     "¿Qué harías diferente ante una intubación futura?",
     "Da un ejemplo de una NRP Key Behavioral Skill."
    ]
   },
   {
    name:"Opción 2 — 37 semanas, intubación y aspiración traqueal por sospecha de obstrucción",
    level:"avanz", levelLabel:"Avanzado",
    objectives:["Usar el aspirador traqueal para secreciones espesas.","Interpretar detector de CO₂ sin cambio de color pese a otros signos de inflación."],
    intro:"«Nacimiento complicado por patrón categoría III de FCF. Primigesta de 39 años a las 37 sem.»",
    pbq:[
     ["¿Edad gestacional?","«37 semanas.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«Patrón categoría III de FCF e hipertensión crónica materna.»"],
     ["¿Plan del cordón?","«Al menos 60 s de pinzamiento diferido, salvo que requiera reanimación.»"]
    ],
    steps:[
     "≥2 personas calificadas. Briefing. Chequeo de equipo.",
     "Evaluación rápida: ~37 sem · sin tono · no respira.",
     `Pasos iniciales; ¿respira? No (${V.hr(40)}). Ventilación en 60 s con 21% O₂, PIP 25 (PEEP 5). En 15–30 s ${V.hr(40)} sin aumento, sin señal. MR SOPA priorizando pasos útiles. Electrodos.`
    ],
    intubation:true,
    afterIntub:[
     `Tras inserción correcta pero sin movimiento torácico ni ruidos ni cambio de color, ${V.hr(40)}: «el tubo está bien colocado pero el tórax no se mueve. ¿Cuál es tu siguiente paso?» → Sospecha obstrucción de vía aérea.`,
     "Conecta aspirador traqueal a succión (80–100 mm Hg) directo al tubo; ocluye el puerto y retira el tubo en 3–5 s mientras aspira secreciones de la tráquea.",
     "Reintuba con tubo limpio (o reanuda ventilación con mascarilla / mascarilla laríngea).",
     `Si reintubación exitosa: cambia color del CO₂, ${V.hr(60,true)} en aumento; señal de oximetría al superar 60. Verifica profundidad (tabla o NTL) y fija.`,
     `A los 30–60 s: ${V.hr(70,true)} en aumento, apneico, ${V.sp("68%")}. Luego ${V.hr(">100",true)}, ${V.sp("72%")}. Fin: soporte y O₂ por tabla objetivo.`
    ],
    debrief:[
     "Tras la vía aérea alternativa seguía sin haber movimiento torácico: ¿cómo se apoyó el equipo?",
     "¿Qué si un miembro sugería iniciar compresiones antes de lograr movimiento torácico con la ventilación?",
     "Da un ejemplo de una NRP Key Behavioral Skill."
    ]
   }
  ]
 },
 {
  n:"L6", title:"Compresiones torácicas",
  sub:"Cesárea de emergencia por bradicardia fetal · coordinación 3:1",
  scenarios:[
   {
    name:"Escenario — Cesárea de emergencia por bradicardia fetal",
    level:"avanz", levelLabel:"Avanzado",
    objectives:["Identificar al RN que requiere compresiones.","Interpretar detector de CO₂ sin cambio de color pese a signos de inflación pulmonar.","Técnica correcta de compresiones y signo para suspenderlas.","Comunicación y trabajo en equipo en este componente crítico."],
    intro:"«Le llaman a una cesárea de emergencia por bradicardia fetal. ¿Cómo se prepara? Diga sus pensamientos y acciones en voz alta.»",
    pbq:[
     ["¿Edad gestacional?","«Término.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«Bradicardia fetal en los últimos 3 minutos.»"],
     ["¿Plan del cordón?","«60 s de pinzamiento diferido, salvo que requiera reanimación inmediata.»"]
    ],
    steps:[
     "≥2 personas calificadas. Briefing. Chequeo de equipo (prepara intubación, CVU y medicación).",
     "Evaluación rápida: aparenta término · sin tono · no respira.",
     `Pasos iniciales. «Apneico» (${V.hr(40)}). Ventilación en 60 s con 21% O₂. En 15–30 s ${V.hr(40)} sin aumento, sin señal. Monitor opcional.`,
     "Evalúa movimiento torácico. Si no hay, MR SOPA hasta lograrlo; la FC permanecerá <60. Si no se logra tras M-R, S-O, P → indica vía aérea alternativa (intubación o mascarilla laríngea).",
     `A los 60 s de ventilación efectiva: ${V.hr(40)}, no aumenta → indica vía aérea alternativa. Intuba (hoja 1, tubo 3.5) o mascarilla laríngea; confirma FC, CO₂, ruidos y movimiento. Verifica profundidad y fija.`,
     `Dispositivo colocado: el color puede no cambiar por FC baja. ${V.hr(40)}, «el tórax se mueve, sin señal de oximetría». Ventila 30–60 s.`,
     `A los 30–60 s: ${V.hr(40)}, no aumenta → inicia compresiones.`
    ],
    compressions:true,
    afterComp:[
     `A los 60 s de compresiones+ventilación: ${V.hr(70,true)} en ascenso, señal de oximetría, sin respiraciones espontáneas → suspende compresiones. Continúa ventilación 30–60/min y ajusta O₂ por SpO₂.`,
     `${V.hr(">100",true)} en aumento · ${V.sp("78%")} · sin respiraciones espontáneas.`,
     `${V.hr(">100",true)} · ${V.sp("90%")} · mejora el tono, algunas respiraciones espontáneas. Fin: soporte, O₂ por tabla objetivo, actualiza a los padres.`
    ],
    debrief:["¿Qué salió bien?","¿Cuál es el tema más importante?","¿Qué harías diferente ante compresiones futuras?","¿Comentarios para el equipo o el líder?","Si hubo errores: ¿qué pasó, qué debió pasar, qué pudiste hacer?"]
   }
  ]
 },
 {
  n:"L7", title:"Medicamentos (con colocación de CVU)",
  sub:"Prolapso de cordón · epinefrina, catéter venoso umbilical y expansor de volumen",
  scenarios:[
   {
    name:"Escenario — Cesárea de emergencia por prolapso de cordón con bradicardia fetal",
    level:"avanz", levelLabel:"Avanzado",
    objectives:["Identificar cuándo se requiere epinefrina y expansor de volumen.","Preparar y administrar epinefrina y volumen.","Colocar/asistir un CVU de emergencia y fijarlo.","Comunicación de circuito cerrado y trabajo en equipo."],
    intro:"«Le llaman a una cesárea de emergencia por prolapso de cordón con bradicardia fetal. ¿Cómo se prepara para la reanimación?»",
    pbq:[
     ["¿Edad gestacional?","«Término.»"],
     ["¿Líquido claro?","«Líquido claro.»"],
     ["¿Factores de riesgo?","«Prolapso de cordón y bradicardia fetal en los últimos 3 minutos.»"],
     ["¿Plan del cordón?","«60 s de pinzamiento diferido, salvo que requiera reanimación inmediata.»"]
    ],
    steps:[
     "≥2 personas calificadas. Briefing. Chequeo de equipo.",
     "Evaluación rápida: aparenta término · sin tono · no respira.",
     `Pasos iniciales. «Apneico» (${V.hr(50)}). Ventilación en 60 s con 21% O₂. En 15–30 s ${V.hr(40)}, no aumenta.`,
     "Evalúa movimiento torácico; si no hay, MR SOPA hasta lograrlo; si no, vía aérea alternativa.",
     `A los 30 s de ventilación efectiva: ${V.hr(30)}, no aumenta → vía aérea alternativa (tubo ET preferido; la epinefrina NO se recomienda por mascarilla laríngea). Intuba (hoja 1, tubo 3.5); confirma color, FC, ruidos, movimiento; verifica profundidad y fija.`,
     `Dispositivo colocado: ${V.hr(30)}, tórax se mueve, ruidos iguales, sin señal. Ventila 30 s.`,
     `A los 30 s con vía aérea alternativa: ${V.hr(30)}, sin señal → inicia compresiones. Pide ayuda, O₂ al 100%, compresiones desde la cabecera coordinadas 3:1 cada 2 s.`,
     `A los 60 s de compresiones: ${V.hr(30)}, no aumenta → prepara acceso vascular de emergencia.`
    ],
    meds:true,
    afterMeds:[
     `Tras epinefrina IV, a los 60 s: ${V.hr(50)}, sin señal, «el bebé está pálido» → continúa ventilación y compresiones.`,
     "Administra expansor de volumen: 30 mL (10 mL/kg) de SSN por CVU en 5–10 min con comunicación de circuito cerrado; numera las jeringas (#1, #2, #3).",
     `El instructor puede comprimir el tiempo: «se administró la infusión de 30 mL de SSN». ${V.hr(80,true)} en aumento · ${V.sp("68%")} · cambia color del CO₂, señal confiable.`,
     `Suspende compresiones; continúa ventilación 30–60/min. ${V.hr(">100",true)} · ${V.sp("80%")} · sin respiraciones espontáneas.`,
     `${V.hr(">100",true)} · ${V.sp("90%")} · tono aceptable, algunas respiraciones espontáneas. Fin: soporte, O₂ por tabla objetivo, actualiza a los padres.`
    ],
    debrief:["¿Qué salió bien?","¿Qué harías diferente ante esta reanimación compleja?","¿Comentarios para el equipo o el líder?","¿Por qué recibió este bebé expansor de volumen?","Da un ejemplo de una NRP Key Behavioral Skill."]
   }
  ]
 }
];

const mrsopaHTML = `
 <div class="block"><div class="blabel">MR SOPA · pasos correctivos de la ventilación</div>
 <div class="mrsopa">
   <span><b>M</b> · Ajuste de la <b>M</b>áscara</span>
   <span><b>R</b> · <b>R</b>eposicionar cabeza y cuello</span>
   <span><b>S</b> · <b>S</b>uccionar boca y nariz</span>
   <span><b>O</b> · <b>O</b>pen: abrir la boca</span>
   <span><b>P</b> · Aumentar la <b>P</b>resión (5–10 cm H₂O, máx. 40 en término)</span>
   <span><b>A</b> · <b>A</b>lternativa: vía aérea (tubo ET o mascarilla laríngea)</span>
 </div>
 <div class="step" style="color:var(--muted);margin-top:8px">Da 5 respiraciones y reevalúa el movimiento torácico tras cada paso. En la 9.ª edición, prioriza el orden de los pasos según tu evaluación clínica.</div></div>`;

const intubHTML = `
 <div class="block"><div class="blabel">Preparación e intubación · operador y asistente</div>
 <ul>
  <li><b>Operador:</b> pide tubo y hoja correctos, comunica preferencia de estilete, sostiene el laringoscopio en la mano izquierda, abre la boca, inserta la hoja a la base de la lengua y la eleva sin balanceo, pide presión cricoidea si la necesita, identifica reparos, inserta el tubo desde la derecha (no por el centro de la hoja), alinea la guía de cuerdas y sostiene el tubo contra el paladar al retirar el laringoscopio.</li>
  <li><b>Asistente:</b> succión a 80–100 mm Hg, elige tubo y hoja (1 término, 0 pretérmino), verifica la luz del laringoscopio, inserta estilete (opcional), obtiene detector de CO₂, posiciona la cabeza en olfateo, aplica presión cricoidea si se solicita, anuncia si el intento supera 30 s, conecta el detector de CO₂ y el dispositivo de ventilación.</li>
  <li><b>Confirmación:</b> movimiento torácico simétrico, ruidos bilaterales, FC en aumento y cambio de color del detector de CO₂.</li>
 </ul></div>`;

const compHTML = `
 <div class="block"><div class="blabel">Compresiones torácicas · técnica</div>
 <ul>
  <li>Pide ayuda; el asistente aumenta el O₂ al 100%. Pide preparar CVU y epinefrina.</li>
  <li>El compresor se mueve a la cabecera; el ventilador al costado.</li>
  <li>Pulgares sobre el tercio inferior del esternón (bajo la línea intermamilar); dedos bajo la espalda sosteniendo la columna.</li>
  <li>Comprime un tercio del diámetro anteroposterior del tórax, recto arriba-abajo.</li>
  <li>Cadencia «uno-y-dos-y-tres-y-ventila-y»: un ciclo de 3 compresiones + 1 ventilación cada 2 s.</li>
  <li>Verifica FC después de 60 s de compresiones y ventilaciones coordinadas.</li>
 </ul></div>`;

const medsHTML = `
 <div class="block"><div class="blabel">Medicamentos · epinefrina, CVU y volumen</div>
 <ul>
  <li><b>Epinefrina (concentración 0.1 mg/mL = 1 mg/10 mL).</b></li>
  <li><b>Vía endotraqueal (opcional, mientras se establece el CVU):</b> dosis sugerida 0.1 mg/kg (= 1 mL/kg). Para 3 kg → 0.3 mg (3 mL). Adminístrala directo al tubo, seguida de varias ventilaciones. Anuncia «epinefrina ET administrada».</li>
  <li><b>Vía CVU (preferida):</b> dosis IV sugerida 0.02 mg/kg (0.2 mL/kg) cada 3–5 min. Para 3 kg → 0.06 mg (0.6 mL). Comunicación de circuito cerrado; lava el CVU con 3 mL de SSN. Anuncia «epinefrina IV administrada».</li>
  <li><b>CVU de emergencia:</b> jeringa con SSN, llave de 3 vías, purga, limpia el cordón con antiséptico, liga floja en la base, corta 1–2 cm sobre la base, inserta en la vena y avanza ~3–4 cm hasta retorno de sangre; fija con apósito adhesivo transparente.</li>
  <li><b>Expansor de volumen:</b> SSN 10 mL/kg (para 3 kg → 30 mL) en 5–10 min por CVU con circuito cerrado.</li>
 </ul></div>`;

function renderScenarios(){
  const root=document.getElementById('scnroot');
  lessons.forEach(L=>{
    const lh=document.createElement('div'); lh.className='lhead';
    lh.innerHTML=`<span class="lbadge">${L.n}</span><div><h3>${L.title}</h3><small>${L.sub}</small></div>`;
    root.appendChild(lh);
    L.scenarios.forEach(s=>{
      const d=document.createElement('details'); d.className='scn';
      let body=`<div class="scnbody">`;
      body+=`<div class="block"><div class="blabel">Objetivos de aprendizaje</div><ol>${s.objectives.map(o=>`<li>${o}</li>`).join('')}</ol></div>`;
      if(s.intro) body+=`<div class="block"><div class="blabel">Guion de apertura</div><p class="quote">${s.intro}</p></div>`;
      body+=`<div class="block"><div class="blabel">4 preguntas prebirth · respuesta del proveedor obstétrico</div><table class="pbq"><tbody>${s.pbq.map(r=>`<tr><td>${r[0]}</td><td>${r[1]}</td></tr>`).join('')}</tbody></table></div>`;
      body+=`<div class="block"><div class="blabel">Pasos críticos de desempeño</div>${s.steps.map(st=>`<div class="step">• ${st}</div>`).join('')}</div>`;
      if(s.mrsopa) body+=mrsopaHTML;
      if(s.intubation) body+=intubHTML;
      if(s.compressions) body+=compHTML;
      if(s.meds) body+=medsHTML;
      if(s.afterMrsopa) body+=`<div class="block"><div class="blabel">Evolución esperada</div>${s.afterMrsopa.map(st=>`<div class="step">• ${st}</div>`).join('')}</div>`;
      if(s.afterIntub) body+=`<div class="block"><div class="blabel">Evolución esperada</div>${s.afterIntub.map(st=>`<div class="step">• ${st}</div>`).join('')}</div>`;
      if(s.afterComp) body+=`<div class="block"><div class="blabel">Evolución esperada</div>${s.afterComp.map(st=>`<div class="step">• ${st}</div>`).join('')}</div>`;
      if(s.afterMeds) body+=`<div class="block"><div class="blabel">Evolución esperada</div>${s.afterMeds.map(st=>`<div class="step">• ${st}</div>`).join('')}</div>`;
      if(s.optional) body+=`<div class="block"><div class="blabel">Componente opcional</div><div class="step">${s.optional}</div></div>`;
      body+=`<div class="block"><div class="blabel">Preguntas de debriefing</div><ul>${s.debrief.map(q=>`<li>${q}</li>`).join('')}</ul></div>`;
      body+=`</div>`;
      d.innerHTML=`<summary><svg class="chev" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4"><path d="M9 6l6 6-6 6"/></svg><span>${s.name}</span><span class="lvl ${s.level}">${s.levelLabel}</span></summary>${body}`;
      root.appendChild(d);
    });
  });
}

/* ---------------- Checklists ---------------- */
const equipData=[
 ["Warm — Calentar",["Cuna de calor radiante precalentada","Toallas o mantas tibias","Gorro","Bolsa o envoltura plástica (<32 sem)","Colchón térmico (<32 sem)"]],
 ["Clear airway — Despejar vía aérea",["Perilla de succión","Catéter de succión 10F o 12F a succión de pared, 80–100 mm Hg","Aspirador traqueal"]],
 ["Auscultate — Auscultar",["Estetoscopio"]],
 ["Ventilate — Ventilar",["Flujómetro a 10 L/min","Dispositivo de ventilación","Máscaras de tamaño término y pretérmino","Sonda orogástrica (5/6F u 8F) y jeringa de 20 mL","Mascarilla laríngea (neonatal) y jeringa de 5 mL si requiere inflado"]],
 ["Oxygenate — Oxigenar",["Blender de O₂ en la concentración inicial deseada","Oxímetro de pulso con sensor y cubierta","Tabla de SpO₂ objetivo","Equipo para O₂ de flujo libre"]],
 ["Intubate — Intubar",["Laringoscopio con hojas rectas 0 y 1 (00 opcional)","Tubos endotraqueales (2.5, 3.0, 3.5)","Estilete (opcional)","Detector de CO₂","Cinta métrica y/o tabla de profundidad del tubo","Cinta impermeable o dispositivo de fijación","Tijeras"]],
 ["Medicate — Medicar (acceso a)",["Epinefrina (0.1 mg/mL = 1 mg/10 mL)","Solución salina normal (bolsa 100/250 mL o jeringas precargadas)","Material para CVU de emergencia y administración de medicamentos","Tabla de dosis precalculadas para 0.5 a 4 kg"]]
];
const debriefData=[
 ["Desarrollo del escenario",["El escenario se basa en objetivos de aprendizaje adaptados a las necesidades del alumno","El escenario es plausible","Los suministros y el equipo están presentes y funcionan"]],
 ["Durante la orientación",["Permite a los alumnos presentarse y describir sus roles","Orienta sobre las capacidades del maniquí","Orienta sobre ubicación y operación de suministros","Muestra cómo se transmite la fisiología del maniquí","Revisa responsabilidades (suspender incredulidad, pensar en voz alta, actuar, actitud seria)","Da unos minutos para manejar el equipo antes de iniciar","Indica la señal de inicio y recuerda que el instructor termina el escenario","Ofrece un escenario breve de calentamiento"]],
 ["Durante el escenario",["Filma el escenario para el debriefing","No interrumpe, guía ni sugiere a los alumnos","Registra habilidades cognitivas, técnicas y conductuales","Termina el escenario sin juicio ni retroalimentación"]],
 ["Durante el debriefing",["Inicia con una pregunta para crear un modelo mental compartido","Ayuda a crear una agenda en escenarios complejos","Promueve discutir qué salió bien y qué mejorar","Usa más preguntas que afirmaciones y preguntas abiertas","Usa el silencio para dar tiempo a pensar","Involucra a los alumnos callados","Mantiene la discusión positiva y centrada en los objetivos","Fomenta que los alumnos hablen entre sí","Vincula el escenario con la experiencia real","Muestra segmentos de video para discusión","Es sincero y usa escucha activa","Cierra pidiendo un resumen y plan de seguimiento"]]
];

function buildChecklist(rootId,data,storeKey){
  const root=document.getElementById(rootId); root.innerHTML='';
  data.forEach((g,gi)=>{
    const grp=document.createElement('div'); grp.className='clgroup';
    grp.innerHTML=`<h4>${g[0]}<span class="tag">${g[1].length}</span></h4>`;
    g[1].forEach((item,ii)=>{
      const id=`${storeKey}-${gi}-${ii}`;
      const lab=document.createElement('label'); lab.className='cli';
      lab.innerHTML=`<input type="checkbox" data-k="${id}"><span>${item}</span>`;
      grp.appendChild(lab);
    });
    root.appendChild(grp);
  });
  restore(storeKey,root);
  root.addEventListener('change',e=>{
    if(e.target.type==='checkbox'){
      e.target.closest('.cli').classList.toggle('done',e.target.checked);
      persist(storeKey,root);
    }
  });
  updateProg(storeKey,root);
}
function persist(key,root){
  try{const s={};root.querySelectorAll('input[type=checkbox]').forEach(c=>s[c.dataset.k]=c.checked);
    localStorage.setItem(key,JSON.stringify(s));}catch(e){}
  updateProg(key,root);
}
function restore(key,root){
  try{const s=JSON.parse(localStorage.getItem(key)||'{}');
    root.querySelectorAll('input[type=checkbox]').forEach(c=>{if(s[c.dataset.k]){c.checked=true;c.closest('.cli').classList.add('done');}});
  }catch(e){}
}
function updateProg(key,root){
  const all=root.querySelectorAll('input[type=checkbox]');
  const done=[...all].filter(c=>c.checked).length;
  const pid=key==='eduvesa-equip'?'eq-prog':'db-prog';
  const el=document.getElementById(pid); if(el) el.textContent=`Progreso: ${done} / ${all.length} elementos completados`;
}
function resetChecklist(key,rootId){
  try{localStorage.removeItem(key);}catch(e){}
  const root=document.getElementById(rootId);
  root.querySelectorAll('input[type=checkbox]').forEach(c=>{c.checked=false;c.closest('.cli').classList.remove('done');});
  updateProg(key,root);
}

/* ---------------- Tabs ---------------- */
const tabs=[...document.querySelectorAll('.tab')];
const panels=[...document.querySelectorAll('.panel')];
tabs.forEach(t=>t.addEventListener('click',()=>{
  tabs.forEach(x=>x.setAttribute('aria-selected','false'));
  t.setAttribute('aria-selected','true');
  panels.forEach(p=>p.classList.toggle('active',p.id===t.dataset.p));
  window.scrollTo({top:0,behavior:'smooth'});
}));

/* ---------------- Init ---------------- */
renderScenarios();
buildChecklist('equiproot',equipData,'eduvesa-equip');
buildChecklist('debriefroot',debriefData,'eduvesa-debrief');
document.getElementById('eq-reset').addEventListener('click',()=>{if(confirm('¿Reiniciar el checklist de equipo?'))resetChecklist('eduvesa-equip','equiproot');});
document.getElementById('db-reset').addEventListener('click',()=>{if(confirm('¿Reiniciar el checklist de debriefing?'))resetChecklist('eduvesa-debrief','debriefroot');});
</script>
</body>
</html>
