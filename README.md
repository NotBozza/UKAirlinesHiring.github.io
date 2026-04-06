# UKAirlinesHiring.github.io

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>UK Pilot Jobs — Hiring Tracker 2026</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=IBM+Plex+Mono:wght@300;400;500&family=IBM+Plex+Sans:wght@300;400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg:       #080c10;
      --surface:  #0d1318;
      --surface2: #111820;
      --border:   rgba(255,255,255,0.07);
      --green:    #22d47a;
      --green-dim:#0d3320;
      --amber:    #f5a623;
      --amber-dim:#2e1e05;
      --red:      #ff5555;
      --red-dim:  #2a0d0d;
      --blue:     #4da6ff;
      --blue-dim: #0a1f35;
      --muted:    #3d4f63;
      --text:     #dde6f0;
      --text-dim: #627080;
      --mono:     'IBM Plex Mono', monospace;
      --sans:     'IBM Plex Sans', sans-serif;
      --display:  'Syne', sans-serif;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }

    body {
      font-family: var(--sans);
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* grid texture */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(255,255,255,0.016) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.016) 1px, transparent 1px);
      background-size: 44px 44px;
      pointer-events: none;
      z-index: 0;
    }

    /* ── HEADER ── */
    header {
      position: relative; z-index: 10;
      padding: 60px 48px 48px;
      max-width: 1200px;
      margin: 0 auto;
      border-bottom: 1px solid var(--border);
    }
    .header-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 16px;
      margin-bottom: 28px;
    }
    .logo-mark {
      font-family: var(--mono);
      font-size: 0.65rem;
      letter-spacing: 0.18em;
      color: var(--muted);
      text-transform: uppercase;
      display: flex;
      align-items: center;
      gap: 12px;
    }
    .logo-mark::before {
      content: '';
      display: block;
      width: 24px; height: 1px;
      background: var(--green);
    }
    .live-tag {
      display: flex;
      align-items: center;
      gap: 7px;
      font-family: var(--mono);
      font-size: 0.65rem;
      color: var(--green);
      letter-spacing: 0.1em;
    }
    .pulse {
      width: 6px; height: 6px;
      border-radius: 50%;
      background: var(--green);
      animation: blink 2s infinite;
    }
    @keyframes blink {
      0%,100% { opacity:1; box-shadow: 0 0 0 0 rgba(34,212,122,.5); }
      50%      { opacity:.6; box-shadow: 0 0 0 5px rgba(34,212,122,0); }
    }

    h1 {
      font-family: var(--display);
      font-size: clamp(3rem, 8vw, 6.5rem);
      font-weight: 800;
      line-height: 0.93;
      letter-spacing: -0.025em;
      color: #fff;
      margin-bottom: 32px;
    }
    h1 .g { color: var(--green); }

    .stats-row {
      display: flex;
      align-items: stretch;
      gap: 0;
      flex-wrap: wrap;
    }
    .stat {
      padding: 0 28px 0 0;
      margin-right: 28px;
      border-right: 1px solid var(--border);
    }
    .stat:last-child { border-right: none; }
    .stat-num {
      font-family: var(--display);
      font-size: 2.2rem;
      font-weight: 800;
      color: #fff;
      line-height: 1;
      letter-spacing: -0.03em;
    }
    .stat-num.green { color: var(--green); }
    .stat-num.amber { color: var(--amber); }
    .stat-num.blue  { color: var(--blue); }
    .stat-label {
      font-family: var(--mono);
      font-size: 0.6rem;
      color: var(--muted);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-top: 4px;
    }

    /* ── FILTER BAR ── */
    .filter-bar {
      position: relative; z-index: 10;
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px 48px;
      display: flex;
      align-items: center;
      gap: 8px;
      flex-wrap: wrap;
      border-bottom: 1px solid var(--border);
    }
    .filter-label {
      font-family: var(--mono);
      font-size: 0.6rem;
      color: var(--muted);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-right: 6px;
    }
    .f-btn {
      font-family: var(--mono);
      font-size: 0.65rem;
      letter-spacing: 0.06em;
      padding: 6px 14px;
      border-radius: 3px;
      border: 1px solid var(--border);
      background: transparent;
      color: var(--text-dim);
      cursor: pointer;
      transition: all 0.18s;
      text-transform: uppercase;
    }
    .f-btn:hover { color: var(--text); border-color: rgba(255,255,255,.18); }
    .f-btn.fa { background: rgba(255,255,255,.05); border-color: rgba(255,255,255,.14); color:#fff; }
    .f-btn.fo { background: var(--green-dim); border-color: var(--green); color: var(--green); }
    .f-btn.fp { background: var(--amber-dim); border-color: var(--amber); color: var(--amber); }
    .f-btn.fw { background: var(--blue-dim);  border-color: var(--blue);  color: var(--blue); }
    .f-btn.fc { background: var(--red-dim);   border-color: var(--red);   color: var(--red); }

    /* ── MAIN ── */
    main {
      position: relative; z-index: 10;
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 48px 80px;
    }

    .sec-head {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 40px 0 18px;
    }
    .sec-head h2 {
      font-family: var(--mono);
      font-size: 0.6rem;
      font-weight: 500;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--muted);
      white-space: nowrap;
    }
    .sec-head::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    /* ── TABLE ── */
    table {
      width: 100%;
      border-collapse: collapse;
    }
    thead tr { border-bottom: 1px solid var(--border); }
    thead th {
      font-family: var(--mono);
      font-size: 0.58rem;
      font-weight: 500;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: var(--muted);
      padding: 0 16px 12px;
      text-align: left;
    }
    thead th:first-child { padding-left: 0; }
    thead th:last-child  { padding-right: 0; }

    tbody tr {
      border-bottom: 1px solid rgba(255,255,255,0.04);
      transition: background .12s;
    }
    tbody tr:hover { background: rgba(255,255,255,.022); }
    tbody tr.hidden { display: none; }

    td {
      padding: 16px;
      vertical-align: middle;
    }
    td:first-child { padding-left: 0; }
    td:last-child  { padding-right: 0; }

    .td-name {
      font-family: var(--display);
      font-size: 0.98rem;
      font-weight: 700;
      color: #fff;
      white-space: nowrap;
    }
    .td-iata {
      font-family: var(--mono);
      font-size: 0.58rem;
      color: var(--muted);
      margin-top: 3px;
      letter-spacing: 0.08em;
    }

    .type-badge {
      display: inline-block;
      font-family: var(--mono);
      font-size: 0.58rem;
      letter-spacing: 0.07em;
      text-transform: uppercase;
      padding: 3px 9px;
      border-radius: 3px;
      white-space: nowrap;
    }
    .t-airline  { background:rgba(77,166,255,.09); color:#5ba8ff; border:1px solid rgba(77,166,255,.2); }
    .t-regional { background:rgba(100,220,160,.07); color:#6ddba6; border:1px solid rgba(100,220,160,.18); }
    .t-cargo    { background:rgba(200,120,255,.07); color:#c97fff; border:1px solid rgba(200,120,255,.18); }
    .t-charter  { background:rgba(255,150,80,.07); color:#ffaa66; border:1px solid rgba(255,150,80,.18); }
    .t-biz      { background:rgba(255,210,80,.07); color:#ffd166; border:1px solid rgba(255,210,80,.18); }
    .t-spec     { background:rgba(180,180,200,.06); color:#9aa0b0; border:1px solid rgba(180,180,200,.15); }

    .status-pill {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-family: var(--mono);
      font-size: 0.65rem;
      font-weight: 500;
      letter-spacing: 0.04em;
      padding: 5px 12px;
      border-radius: 100px;
      white-space: nowrap;
    }
    .status-pill::before {
      content: '';
      width: 5px; height: 5px;
      border-radius: 50%;
      flex-shrink: 0;
    }
    .s-open    { background: var(--green-dim); color: var(--green); border:1px solid rgba(34,212,122,.28); }
    .s-open::before    { background: var(--green); }
    .s-pathway { background: var(--amber-dim); color: var(--amber); border:1px solid rgba(245,166,35,.28); }
    .s-pathway::before { background: var(--amber); }
    .s-closed  { background: var(--red-dim);   color: var(--red);   border:1px solid rgba(255,85,85,.2); }
    .s-closed::before  { background: var(--red); }
    .s-watch   { background: var(--blue-dim);  color: var(--blue);  border:1px solid rgba(77,166,255,.28); }
    .s-watch::before   { background: var(--blue); }

    .td-notes {
      font-size: 0.8rem;
      color: var(--text-dim);
      line-height: 1.6;
      max-width: 400px;
    }
    .td-notes .hi  { color: var(--amber); }
    .td-notes .gr  { color: var(--green); }
    .td-notes .bl  { color: var(--blue); }
    .td-notes .rd  { color: var(--red); opacity:.85; }

    /* ── LEGEND ── */
    .legend {
      position: relative; z-index: 10;
      max-width: 1200px;
      margin: 0 auto;
      padding: 8px 48px 48px;
      display: flex;
      gap: 20px;
      flex-wrap: wrap;
    }
    .leg-item {
      display: flex;
      align-items: center;
      gap: 7px;
      font-family: var(--mono);
      font-size: 0.6rem;
      color: var(--text-dim);
      letter-spacing: 0.05em;
    }
    .leg-dot { width: 7px; height: 7px; border-radius: 50%; }

    /* ── FOOTER ── */
    footer {
      position: relative; z-index: 10;
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px 48px 36px;
      border-top: 1px solid var(--border);
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 8px;
    }
    footer p {
      font-family: var(--mono);
      font-size: 0.6rem;
      color: var(--muted);
      letter-spacing: 0.05em;
    }

    @media (max-width: 800px) {
      header, .filter-bar, main, .legend, footer { padding-left: 20px; padding-right: 20px; }
      h1 { font-size: 2.8rem; }
      thead th:nth-child(2), td:nth-child(2) { display: none; }
      .td-notes { max-width: 180px; font-size: 0.74rem; }
    }
  </style>
</head>
<body>

<header>
  <div class="header-top">
    <div class="logo-mark">UK Pilot Hiring Tracker · April 2026</div>
    <div class="live-tag"><span class="pulse"></span>Live Intel</div>
  </div>
  <h1>UK Airlines<br><span class="g">Hiring Pilots</span></h1>
  <div class="stats-row">
    <div class="stat">
      <div class="stat-num green" id="cnt-open">—</div>
      <div class="stat-label">Open / Pathway</div>
    </div>
    <div class="stat">
      <div class="stat-num blue" id="cnt-watch">—</div>
      <div class="stat-label">Watch List</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="cnt-closed">—</div>
      <div class="stat-label">Not Hiring</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="cnt-total">—</div>
      <div class="stat-label">Total Tracked</div>
    </div>
  </div>
</header>

<div class="filter-bar">
  <span class="filter-label">Filter //</span>
  <button class="f-btn fa" data-f="all">All</button>
  <button class="f-btn"    data-f="open">✦ Open Now</button>
  <button class="f-btn"    data-f="pathway">⟶ Pathway</button>
  <button class="f-btn"    data-f="watch">◎ Watch Soon</button>
  <button class="f-btn"    data-f="closed">✕ Not Hiring</button>
</div>

<main>

  <!-- MAJOR PASSENGER -->
  <div class="sec-head"><h2>Major Passenger Carriers</h2></div>
  <table>
    <thead><tr><th>Airline</th><th>Type</th><th>Status</th><th>Notes</th></tr></thead>
    <tbody>

      <tr data-status="pathway">
        <td><div class="td-name">Ascend Airways</div><div class="td-iata">YD · SYNERGY</div></td>
        <td><span class="type-badge t-charter">Charter</span></td>
        <td><span class="status-pill s-pathway">Recommendation</span></td>
        <td class="td-notes">Hiring through <span class="hi">recommendation only</span>. No direct open applications.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">British Airways</div><div class="td-iata">BA · BAW</div></td>
        <td><span class="type-badge t-airline">Full Service</span></td>
        <td><span class="status-pill s-closed">SSP Not Open</span></td>
        <td class="td-notes"><span class="rd">BA SSP currently not open.</span> Monitor careers page for re-launch.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">BA CityFlyer</div><div class="td-iata">CJ · CFE</div></td>
        <td><span class="type-badge t-regional">Regional</span></td>
        <td><span class="status-pill s-closed">Closed</span></td>
        <td class="td-notes">Was open a few months ago — <span class="hi">currently closed</span>. Worth monitoring.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">BA EuroFlyer</div><div class="td-iata">A0 · EFW</div></td>
        <td><span class="type-badge t-airline">Full Service</span></td>
        <td><span class="status-pill s-closed">SSP Not Open</span></td>
        <td class="td-notes"><span class="rd">BA SSP not open</span> — same pipeline as mainline British Airways.</td>
      </tr>

      <tr data-status="watch">
        <td><div class="td-name">easyJet</div><div class="td-iata">U2 · EZY</div></td>
        <td><span class="type-badge t-airline">Low Cost</span></td>
        <td><span class="status-pill s-watch">Watch — June</span></td>
        <td class="td-notes"><span class="bl">Rumoured to move to integrated ATO pathways in June 2026.</span> Monitor closely.</td>
      </tr>

      <tr data-status="open">
        <td><div class="td-name">Jet2.com</div><div class="td-iata">LS · EXS</div></td>
        <td><span class="type-badge t-airline">Low Cost</span></td>
        <td><span class="status-pill s-open">SFO Open</span></td>
        <td class="td-notes"><span class="gr">SFO open right now.</span> <span class="hi">Highly competitive</span> — strong application essential.</td>
      </tr>

      <tr data-status="pathway">
        <td><div class="td-name">Loganair</div><div class="td-iata">LM · LOG</div></td>
        <td><span class="type-badge t-regional">Regional</span></td>
        <td><span class="status-pill s-pathway">Pathway</span></td>
        <td class="td-notes">Hiring through <span class="hi">Skyborne tagging</span> and <span class="hi">APS MCC Course</span>.</td>
      </tr>

      <tr data-status="pathway">
        <td><div class="td-name">Norse Atlantic UK</div><div class="td-iata">Z0 · UBT</div></td>
        <td><span class="type-badge t-airline">Long Haul LCC</span></td>
        <td><span class="status-pill s-pathway">LE Pathway</span></td>
        <td class="td-notes"><span class="hi">Aurigny LE Pathway</span> — indirect route via Aurigny low-hours scheme.</td>
      </tr>

      <tr data-status="open">
        <td><div class="td-name">Ryanair UK</div><div class="td-iata">RK · RUK</div></td>
        <td><span class="type-badge t-airline">Low Cost</span></td>
        <td><span class="status-pill s-open">Open Now</span></td>
        <td class="td-notes"><span class="gr">Open right now</span> for <span class="hi">UK CAA licence holders</span>. Direct application available.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">Virgin Atlantic</div><div class="td-iata">VS · VIR</div></td>
        <td><span class="type-badge t-airline">Full Service</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not hiring pilots</span> at this time.</td>
      </tr>

      <tr data-status="open">
        <td><div class="td-name">Wizz Air UK</div><div class="td-iata">W9 · WUK</div></td>
        <td><span class="type-badge t-airline">Low Cost</span></td>
        <td><span class="status-pill s-open">Hiring</span></td>
        <td class="td-notes"><span class="gr">Currently hiring.</span> Check Wizz Air careers portal for live vacancies.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">TUI Airways</div><div class="td-iata">BY · TOM</div></td>
        <td><span class="type-badge t-charter">Charter</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not hiring fATPL 250h low hours</span> at this time.</td>
      </tr>

    </tbody>
  </table>

  <!-- CARGO -->
  <div class="sec-head"><h2>Cargo Operators</h2></div>
  <table>
    <thead><tr><th>Airline</th><th>Type</th><th>Status</th><th>Notes</th></tr></thead>
    <tbody>

      <tr data-status="pathway">
        <td><div class="td-name">DHL Air UK</div><div class="td-iata">D0 · DHK</div></td>
        <td><span class="type-badge t-cargo">Cargo</span></td>
        <td><span class="status-pill s-pathway">SO via Skyborne</span></td>
        <td class="td-notes">Hiring <span class="hi">Second Officers through Skyborne</span> pathway scheme.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">West Atlantic UK</div><div class="td-iata">NL · NPT</div></td>
        <td><span class="type-badge t-cargo">Cargo</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">European Cargo</div><div class="td-iata">SE · URO</div></td>
        <td><span class="type-badge t-cargo">Cargo</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">One Air</div><div class="td-iata">HC · HGO</div></td>
        <td><span class="type-badge t-cargo">Cargo</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not hiring low hour fATPL holders.</span></td>
      </tr>

    </tbody>
  </table>

  <!-- REGIONAL & ISLAND -->
  <div class="sec-head"><h2>Regional &amp; Island Operators</h2></div>
  <table>
    <thead><tr><th>Airline</th><th>Type</th><th>Status</th><th>Notes</th></tr></thead>
    <tbody>

      <tr data-status="closed">
        <td><div class="td-name">Aurigny</div><div class="td-iata">GR · AUR</div></td>
        <td><span class="type-badge t-regional">Regional</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes">Not hiring direct — note: <span class="bl">Aurigny LE Pathway feeds Norse Atlantic UK</span>.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">Isles of Scilly Skybus</div><div class="td-iata">IOS · SCILLONIA</div></td>
        <td><span class="type-badge t-regional">Regional</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">Hebridean Air Services</div><div class="td-iata">HBR · HEBRIDEAN</div></td>
        <td><span class="type-badge t-regional">Regional</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="open">
        <td><div class="td-name">Ravenair</div><div class="td-iata">RVR · RAVEN</div></td>
        <td><span class="type-badge t-regional">Regional</span></td>
        <td><span class="status-pill s-open">P2 Role Open</span></td>
        <td class="td-notes"><span class="gr">Hiring for a P2 role.</span> Good low-hours opportunity — apply directly.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">LyddAir</div><div class="td-iata">LYD · LYDDAIR</div></td>
        <td><span class="type-badge t-regional">Regional</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">Woodgate Aviation</div><div class="td-iata">CWY · CAUSEWAY</div></td>
        <td><span class="type-badge t-regional">Regional</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="watch">
        <td><div class="td-name">Silver Aviation</div><div class="td-iata">—</div></td>
        <td><span class="type-badge t-regional">Regional</span></td>
        <td><span class="status-pill s-watch">Hiring Soon</span></td>
        <td class="td-notes">Not now but <span class="bl">will be hiring soon on PC12.</span> Get your CV ready.</td>
      </tr>

    </tbody>
  </table>

  <!-- BIZ / CHARTER / SPECIALIST -->
  <div class="sec-head"><h2>Business Aviation, Charter &amp; Specialist</h2></div>
  <table>
    <thead><tr><th>Airline</th><th>Type</th><th>Status</th><th>Notes</th></tr></thead>
    <tbody>

      <tr data-status="open">
        <td><div class="td-name">2Excel Aviation</div><div class="td-iata">BRO · BROADSWORD</div></td>
        <td><span class="type-badge t-charter">Charter</span></td>
        <td><span class="status-pill s-open">Hiring — 250h</span></td>
        <td class="td-notes"><span class="gr">Hiring at 250 hours.</span> Great low-hours entry point.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">AirTanker</div><div class="td-iata">9L · TOW</div></td>
        <td><span class="type-badge t-spec">Charter / MIL</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">NTR fATPL required.</span> No type rating = no entry currently.</td>
      </tr>

      <tr data-status="watch">
        <td><div class="td-name">BAE Systems</div><div class="td-iata">BAE · FELIX</div></td>
        <td><span class="type-badge t-spec">Specialist</span></td>
        <td><span class="status-pill s-watch">Monitor</span></td>
        <td class="td-notes">Were hiring <span class="bl">via LinkedIn.</span> Keep profile updated and monitor regularly.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">SaxonAir</div><div class="td-iata">SXN · SAXONAIR</div></td>
        <td><span class="type-badge t-biz">Business</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">RVL Aviation</div><div class="td-iata">7M · REV</div></td>
        <td><span class="type-badge t-charter">Charter</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">TAG Aviation UK</div><div class="td-iata">VIP · SOVEREIGN</div></td>
        <td><span class="type-badge t-biz">Business</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="open">
        <td><div class="td-name">Dragonfly Aviation</div><div class="td-iata">CBM · CAMBRIAN</div></td>
        <td><span class="type-badge t-charter">Charter</span></td>
        <td><span class="status-pill s-open">Hiring</span></td>
        <td class="td-notes"><span class="gr">Currently hiring.</span> Apply directly to Dragonfly.</td>
      </tr>

      <tr data-status="watch">
        <td><div class="td-name">Flight Calibration Services</div><div class="td-iata">VOR · FLIGHTCAL</div></td>
        <td><span class="type-badge t-spec">Specialist</span></td>
        <td><span class="status-pill s-watch">CV on File</span></td>
        <td class="td-notes">Not hiring now but <span class="bl">will keep CV on file.</span> Send yours in.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">Flexjet UK</div><div class="td-iata">FLJ · FLEX AIR</div></td>
        <td><span class="type-badge t-biz">Business</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not hiring low hour fATPL holders.</span></td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">Gama Aviation</div><div class="td-iata">GMA · GAMA</div></td>
        <td><span class="type-badge t-biz">Business</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

      <tr data-status="watch">
        <td><div class="td-name">Titan Airways</div><div class="td-iata">ZT · AWC</div></td>
        <td><span class="type-badge t-charter">Charter</span></td>
        <td><span class="status-pill s-watch">CV Sent</span></td>
        <td class="td-notes">Not hiring currently — <span class="bl">email sent,</span> awaiting response. Worth following up.</td>
      </tr>

      <tr data-status="closed">
        <td><div class="td-name">London Executive Aviation</div><div class="td-iata">LNX · LONEX</div></td>
        <td><span class="type-badge t-biz">Business</span></td>
        <td><span class="status-pill s-closed">Not Hiring</span></td>
        <td class="td-notes"><span class="rd">Not currently hiring.</span></td>
      </tr>

    </tbody>
  </table>

</main>

<!-- LEGEND -->
<div class="legend">
  <span class="leg-item"><span class="leg-dot" style="background:var(--green)"></span>Open / Active Hiring</span>
  <span class="leg-item"><span class="leg-dot" style="background:var(--amber)"></span>Pathway / Scheme Required</span>
  <span class="leg-item"><span class="leg-dot" style="background:var(--blue)"></span>Watch — Hiring Soon / Monitor</span>
  <span class="leg-item"><span class="leg-dot" style="background:var(--red)"></span>Not Currently Hiring</span>
</div>

<footer>
  <p>UK Pilot Hiring Tracker — April 2026 · Community intel &amp; airline career pages</p>
  <p>Always verify directly with each airline before applying</p>
</footer>

<script>
  // Compute stats
  const allRows = document.querySelectorAll('tbody tr[data-status]');
  let open=0, watch=0, closed=0;
  allRows.forEach(r => {
    const s = r.dataset.status;
    if (s === 'open' || s === 'pathway') open++;
    else if (s === 'watch') watch++;
    else closed++;
  });
  document.getElementById('cnt-open').textContent   = open;
  document.getElementById('cnt-watch').textContent  = watch;
  document.getElementById('cnt-closed').textContent = closed;
  document.getElementById('cnt-total').textContent  = allRows.length;

  // Filter
  const btns = document.querySelectorAll('.f-btn');
  const classMap = { all:'fa', open:'fo', pathway:'fp', watch:'fw', closed:'fc' };

  btns.forEach(btn => {
    btn.addEventListener('click', () => {
      btns.forEach(b => b.className = 'f-btn');
      const f = btn.dataset.f;
      btn.classList.add(classMap[f]);
      allRows.forEach(row => {
        const s = row.dataset.status;
        let show = false;
        if      (f === 'all')     show = true;
        else if (f === 'open')    show = s === 'open';
        else if (f === 'pathway') show = s === 'pathway';
        else if (f === 'watch')   show = s === 'watch';
        else if (f === 'closed')  show = s === 'closed';
        row.classList.toggle('hidden', !show);
      });
    });
  });
</script>
</body>
</html>
