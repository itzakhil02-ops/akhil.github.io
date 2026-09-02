# akhil.github.io
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>NEET 2027 Dashboard</title>
  <style>
    :root{
      --bg:#0b1220;
      --card:#101b33;
      --card2:#0f1a30;
      --text:#e7eefc;
      --muted:#a9b7d6;
      --accent:#41d17a;
      --accent2:#5aa7ff;
      --danger:#ff5a7a;
      --border:rgba(255,255,255,.08);
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --radius:16px;
      --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      --sans: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif;
    }
    *{box-sizing:border-box}
    body{
      margin:0; font-family:var(--sans);
      color:var(--text);
      background: radial-gradient(900px 500px at 15% 10%, rgba(65,209,122,.18), transparent 50%),
                  radial-gradient(900px 500px at 85% 10%, rgba(90,167,255,.18), transparent 50%),
                  linear-gradient(180deg, #070b14 0%, var(--bg) 60%, #070b14 100%);
      min-height:100vh;
    }
    a{color:inherit; text-decoration:none}
    .wrap{max-width:1100px; margin:0 auto; padding:24px;}
    header{
      display:flex; gap:14px; align-items:flex-start; justify-content:space-between;
      margin-bottom:18px;
    }
    .title h1{margin:0; font-size:28px; letter-spacing:.2px}
    .title p{margin:6px 0 0; color:var(--muted)}
    .pill{
      display:inline-flex; align-items:center; gap:8px;
      background:rgba(65,209,122,.12);
      border:1px solid rgba(65,209,122,.25);
      padding:10px 12px; border-radius:999px;
      box-shadow: var(--shadow);
      font-family:var(--mono); font-size:12px; color:var(--text);
    }
    .grid{
      display:grid;
      grid-template-columns: 1.15fr .85fr;
      gap:16px;
    }
    @media (max-width: 980px){
      .grid{grid-template-columns:1fr}
      header{flex-direction:column}
    }
    .card{
      background:linear-gradient(180deg, rgba(255,255,255,.02), rgba(255,255,255,.01));
      border:1px solid var(--border);
      border-radius:var(--radius);
      box-shadow: var(--shadow);
      overflow:hidden;
    }
    .card .hd{
      padding:14px 16px;
      display:flex; align-items:center; justify-content:space-between; gap:10px;
      border-bottom:1px solid var(--border);
      background: linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,0));
    }
    .card .hd h2{margin:0; font-size:14px; letter-spacing:.4px; text-transform:uppercase; color:var(--muted)}
    .card .bd{padding:16px;}
    .row{display:flex; gap:10px; flex-wrap:wrap; align-items:center}
    .btn{
      border:1px solid var(--border);
      background:rgba(255,255,255,.03);
      color:var(--text);
      padding:10px 12px;
      border-radius:12px;
      cursor:pointer;
      transition:.15s transform, .15s background, .15s border;
      font-weight:600;
    }
    .btn:hover{transform:translateY(-1px); background:rgba(255,255,255,.06); border-color:rgba(255,255,255,.16)}
    .btn.primary{background:rgba(65,209,122,.14); border-color:rgba(65,209,122,.25)}
    .btn.danger{background:rgba(255,90,122,.12); border-color:rgba(255,90,122,.25)}
    .btn.small{padding:8px 10px; border-radius:10px; font-size:13px}
    .links{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap:10px;
    }
    @media (max-width: 520px){
      .links{grid-template-columns:1fr}
    }
    .link{
      padding:12px;
      border-radius:14px;
      border:1px solid var(--border);
      background:rgba(16,27,51,.55);
      transition:.15s transform, .15s border;
    }
    .link:hover{transform:translateY(-1px); border-color:rgba(255,255,255,.18)}
    .link .k{font-weight:700}
    .link .s{color:var(--muted); font-size:13px; margin-top:4px}
    .countdown{
      display:grid;
      grid-template-columns: repeat(4, 1fr);
      gap:10px;
      margin-top:10px;
    }
    .tile{
      border:1px solid var(--border);
      background:rgba(16,27,51,.45);
      border-radius:14px;
      padding:12px;
      text-align:center;
    }
    .tile .n{font-size:26px; font-family:var(--mono); font-weight:800}
    .tile .t{margin-top:6px; color:var(--muted); font-size:12px; text-transform:uppercase; letter-spacing:.6px}
    .muted{color:var(--muted)}
    .sep{height:10px}
    .field{display:flex; flex-direction:column; gap:6px}
    label{font-size:12px; color:var(--muted); letter-spacing:.3px; text-transform:uppercase}
    input[type="text"], input[type="number"], select, textarea{
      width:100%;
      border:1px solid var(--border);
      background:rgba(255,255,255,.03);
      color:var(--text);
      padding:10px 12px;
      border-radius:12px;
      outline:none;
    }
    textarea{min-height:92px; resize:vertical}
    .prog{
      display:grid;
      gap:12px;
    }
    .progItem{
      border:1px solid var(--border);
      background:rgba(16,27,51,.45);
      border-radius:14px;
      padding:12px;
    }
    .progTop{
      display:flex; justify-content:space-between; gap:10px; align-items:center;
      margin-bottom:10px;
    }
    .badge{
      font-family:var(--mono);
      font-size:12px;
      padding:6px 10px;
      border-radius:999px;
      border:1px solid var(--border);
      background:rgba(255,255,255,.03);
    }
    input[type="range"]{width:100%}
    .footerNote{
      margin-top:14px; font-style:italic; color:rgba(231,238,252,.82);
      text-align:center;
    }
  </style>
</head>

<body>
  <div class="wrap">
    <header>
      <div class="title">
        <h1>NEET 2027 Master Dashboard</h1>
        <p class="muted">Small efforts everyday lead to massive success someday.</p>
      </div>
      <div class="pill" title="All data is saved locally in your browser (localStorage).">
        <span>Local Save:</span>
        <strong id="saveState">ON</strong>
      </div>
    </header>

    <div class="grid">
      <!-- LEFT COLUMN -->
      <div class="card">
        <div class="hd">
          <h2>Countdown + Quick links</h2>
          <div class="row">
            <button class="btn small" id="setExamBtn">Set exam date</button>
            <button class="btn small" id="resetBtn">Reset saved data</button>
          </div>
        </div>
        <div class="bd">
          <div class="field">
            <label>Exam date/time (local)</label>
            <div class="row" style="width:100%">
              <input id="examDate" type="text" placeholder="e.g. 2027-05-02 14:00" />
              <button class="btn primary" id="saveExamBtn">Save</button>
            </div>
            <div class="muted" style="font-size:13px; margin-top:6px">
              Tip: If you’re unsure, keep it as <span style="font-family:var(--mono)">2027-05-02 14:00</span> and adjust later.
            </div>
          </div>

          <div class="sep"></div>

          <div class="countdown" aria-label="Countdown tiles">
            <div class="tile"><div class="n" id="cdDays">—</div><div class="t">Days</div></div>
            <div class="tile"><div class="n" id="cdHours">—</div><div class="t">Hours</div></div>
            <div class="tile"><div class="n" id="cdMins">—</div><div class="t">Minutes</div></div>
            <div class="tile"><div class="n" id="cdSecs">—</div><div class="t">Seconds</div></div>
          </div>

          <div class="sep"></div>

          <div class="links">
            <!-- NOTE: These are Notion URLs you can replace if needed. -->
            <a class="link" href="https://app.notion.com/p/08b26c4871ae836a84e5012f96862c6b" target="_blank" rel="noreferrer">
              <div class="k">Syllabus Tracker</div>
              <div class="s">Track coverage chapter-wise</div>
            </a>
            <a class="link" href="https://app.notion.com/p/6e626c4871ae82d9b6e7819629fb4519" target="_blank" rel="noreferrer">
              <div class="k">Test Performance</div>
              <div class="s">Analyse mocks & errors</div>
            </a>
            <a class="link" href="https://app.notion.com/p/16a26c4871ae83469b07819fec3ed1f7" target="_blank" rel="noreferrer">
              <div class="k">Revision Log</div>
              <div class="s">Revision cycles & spaced repetition</div>
            </a>
            <a class="link" href="https://app.notion.com/p/e4e26c4871ae82f9930a013573939138" target="_blank" rel="noreferrer">
              <div class="k">Doubts Tracker</div>
              <div class="s">Capture & clear doubts fast</div>
            </a>
            <a class="link" href="https://app.notion.com/p/99726c4871ae837288250187728985cd" target="_blank" rel="noreferrer">
              <div class="k">Daily Planner</div>
              <div class="s">Plan today, execute cleanly</div>
            </a>
            <a class="link" href="https://app.notion.com/p/15f26c4871ae8328b6d401194e2ab6f2" target="_blank" rel="noreferrer">
              <div class="k">Wellness</div>
              <div class="s">Sleep, health & consistency</div>
            </a>
          </div>
        </div>
      </div>

      <!-- RIGHT COLUMN -->
      <div class="card">
        <div class="hd">
          <h2>Today’s plan</h2>
          <div class="row">
            <button class="btn small" id="savePlanBtn">Save</button>
            <button class="btn small danger" id="clearPlanBtn">Clear</button>
          </div>
        </div>
        <div class="bd">
          <div class="field">
            <label>Today’s focus</label>
            <select id="todayFocus">
              <option value="Physics">Physics</option>
              <option value="Chemistry">Chemistry</option>
              <option value="Biology">Biology</option>
              <option value="Mixed">Mixed</option>
            </select>
          </div>

          <div class="sep"></div>

          <div class="field">
            <label>Top 3 tasks (do these no matter what)</label>
            <textarea id="top3" placeholder="- e.g. Rotational Motion DPP&#10;- e.g. GOC notes + 30 MCQs&#10;- e.g. Human Physiology NCERT line-by-line"></textarea>
          </div>

          <div class="sep"></div>

          <div class="field">
            <label>Time targets (hours)</label>
            <div class="row" style="width:100%">
              <input id="hrsPhy" type="number" min="0" step="0.25" placeholder="Physics" />
              <input id="hrsChem" type="number" min="0" step="0.25" placeholder="Chemistry" />
              <input id="hrsBio" type="number" min="0" step="0.25" placeholder="Biology" />
            </div>
            <div class="muted" id="totalHrs" style="margin-top:6px; font-family:var(--mono)"></div>
          </div>
        </div>
      </div>

      <!-- FULL WIDTH: PROGRESS -->
      <div class="card" style="grid-column:1 / -1;">
        <div class="hd">
          <h2>Progress sliders (local)</h2>
          <div class="row">
            <button class="btn small" id="saveProgressBtn">Save</button>
            <span class="muted" style="font-size:13px">Set rough progress; update weekly.</span>
          </div>
        </div>
        <div class="bd">
          <div class="prog" id="progRoot"></div>

          <div class="footerNote">
            “Small efforts everyday lead to massive success someday.”
          </div>
        </div>
      </div>
    </div>
  </div>

<script>
  // ====== Simple localStorage model ======
  const KEY = "neet2027_dashboard_v1";

  const defaultState = {
    exam: "2027-05-02 14:00",
    plan: {
      focus: "Physics",
      top3: "",
      hrsPhy: "",
      hrsChem: "",
      hrsBio: ""
    },
    progress: {
      physics: 0,
      chemistry: 0,
      biology: 0,
      revision: 0,
      tests: 0,
      doubts: 0,
      wellness: 0
    }
  };

  function loadState(){
    try{
      const raw = localStorage.getItem(KEY);
      if(!raw) return structuredClone(defaultState);
      const parsed = JSON.parse(raw);
      return {
        ...structuredClone(defaultState),
        ...parsed,
        plan: { ...defaultState.plan, ...(parsed.plan || {}) },
        progress: { ...defaultState.progress, ...(parsed.progress || {}) },
      };
    }catch(e){
      return structuredClone(defaultState);
    }
  }

  function saveState(state){
    localStorage.setItem(KEY, JSON.stringify(state));
  }

  let state = loadState();

  // ====== UI wiring ======
  const examDate = document.getElementById("examDate");
  const saveExamBtn = document.getElementById("saveExamBtn");
  const setExamBtn = document.getElementById("setExamBtn");
  const resetBtn = document.getElementById("resetBtn");

  const todayFocus = document.getElementById("todayFocus");
  const top3 = document.getElementById("top3");
  const hrsPhy = document.getElementById("hrsPhy");
  const hrsChem = document.getElementById("hrsChem");
  const hrsBio = document.getElementById("hrsBio");
  const totalHrs = document.getElementById("totalHrs");

  const savePlanBtn = document.getElementById("savePlanBtn");
  const clearPlanBtn = document.getElementById("clearPlanBtn");

  const saveProgressBtn = document.getElementById("saveProgressBtn");
  const progRoot = document.getElementById("progRoot");

  function parseExamLocal(s){
    // Accept "YYYY-MM-DD HH:mm"
    const m = s.trim().match(/^(\d{4})-(\d{2})-(\d{2})(?:\s+(\d{2}):(\d{2}))?$/);
    if(!m) return null;
    const y = Number(m[1]), mo = Number(m[2]) - 1, d = Number(m[3]);
    const hh = m[4] ? Number(m[4]) : 0;
    const mm = m[5] ? Number(m[5]) : 0;
    const dt = new Date(y, mo, d, hh, mm, 0, 0);
    if(Number.isNaN(dt.getTime())) return null;
    return dt;
  }

  function pad2(n){ return String(n).padStart(2,"0"); }

  function renderExam(){
    examDate.value = state.exam;
  }

  function updateCountdown(){
    const dt = parseExamLocal(state.exam);
    const now = new Date();
    if(!dt){
      setCountdown("—","—","—","—");
      return;
    }
    let diff = dt.getTime() - now.getTime();
    if(diff <= 0){
      setCountdown("0","0","0","0");
      return;
    }
    const sec = Math.floor(diff/1000);
    const days = Math.floor(sec/86400);
    const hrs = Math.floor((sec%86400)/3600);
    const mins = Math.floor((sec%3600)/60);
    const secs = sec%60;
    setCountdown(days, hrs, mins, secs);
  }

  function setCountdown(d,h,m,s){
    document.getElementById("cdDays").textContent = d;
    document.getElementById("cdHours").textContent = h;
    document.getElementById("cdMins").textContent = m;
    document.getElementById("cdSecs").textContent = s;
  }

  function renderPlan(){
    todayFocus.value = state.plan.focus;
    top3.value = state.plan.top3;
    hrsPhy.value = state.plan.hrsPhy;
    hrsChem.value = state.plan.hrsChem;
    hrsBio.value = state.plan.hrsBio;
    renderTotalHours();
  }

  function renderTotalHours(){
    const a = Number(hrsPhy.value || 0);
    const b = Number(hrsChem.value || 0);
    const c = Number(hrsBio.value || 0);
    const total = a+b+c;
    totalHrs.textContent = `Total target: ${total.toFixed(2)} hours`;
  }

  const progressItems = [
    { key:"physics", label:"Physics", color:"var(--accent)" },
    { key:"chemistry", label:"Chemistry", color:"var(--accent2)" },
    { key:"biology", label:"Biology", color:"var(--accent)" },
    { key:"revision", label:"Revision system", color:"var(--accent2)" },
    { key:"tests", label:"Test practice", color:"var(--accent)" },
    { key:"doubts", label:"Doubts cleared", color:"var(--accent2)" },
    { key:"wellness", label:"Wellness consistency", color:"var(--accent)" },
  ];

  function renderProgress(){
    progRoot.innerHTML = "";
    for(const item of progressItems){
      const val = Number(state.progress[item.key] ?? 0);

      const wrap = document.createElement("div");
      wrap.className = "progItem";

      const top = document.createElement("div");
      top.className = "progTop";

      const left = document.createElement("div");
      left.innerHTML = `<div style="font-weight:800">${item.label}</div>
                        <div class="muted" style="font-size:13px;margin-top:2px">Estimate % (0–100)</div>`;

      const badge = document.createElement("div");
      badge.className = "badge";
      badge.textContent = `${val}%`;

      top.appendChild(left);
      top.appendChild(badge);

      const range = document.createElement("input");
      range.type = "range";
      range.min = "0";
      range.max = "100";
      range.value = String(val);
      range.addEventListener("input", () => {
        badge.textContent = `${range.value}%`;
      });

      const bar = document.createElement("div");
      bar.style.marginTop = "10px";
      bar.style.height = "10px";
      bar.style.borderRadius = "999px";
      bar.style.border = "1px solid var(--border)";
      bar.style.background = "rgba(255,255,255,.03)";
      bar.innerHTML = `<div style="height:100%; width:${val}%; border-radius:999px; background:${item.color}; opacity:.9"></div>`;

      range.addEventListener("input", () => {
        bar.firstChild.style.width = `${range.value}%`;
      });

      wrap.appendChild(top);
      wrap.appendChild(range);
      wrap.appendChild(bar);

      progRoot.appendChild(wrap);
    }
  }

  function savePlan(){
    state.plan.focus = todayFocus.value;
    state.plan.top3 = top3.value;
    state.plan.hrsPhy = hrsPhy.value;
    state.plan.hrsChem = hrsChem.value;
    state.plan.hrsBio = hrsBio.value;
    saveState(state);
  }

  function saveProgress(){
    // Read current sliders from DOM order
    const ranges = progRoot.querySelectorAll('input[type="range"]');
    ranges.forEach((r, idx) => {
      const key = progressItems[idx].key;
      state.progress[key] = Number(r.value);
    });
    saveState(state);
    renderProgress(); // re-render to sync bars precisely
  }

  // Buttons
  saveExamBtn.addEventListener("click", () => {
    const v = examDate.value.trim();
    if(!parseExam
