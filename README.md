<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>FieldOps — Local Service Automation</title>
  <meta name="description" content="FieldOps helps local service pros run jobs, invoices, and follow-ups automatically. Join the early access waitlist." />
  <meta property="og:title" content="FieldOps — Local Service Automation" />
  <meta property="og:description" content="Run jobs, invoices, and follow-ups automatically. Join the early access waitlist." />
  <meta property="og:type" content="website" />
  <style>
    :root {
      --bg: #0b0f17;
      --card: rgba(255,255,255,0.06);
      --card2: rgba(255,255,255,0.09);
      --text: rgba(255,255,255,0.92);
      --muted: rgba(255,255,255,0.65);
      --stroke: rgba(255,255,255,0.10);
      --shadow: 0 18px 60px rgba(0,0,0,0.55);
      --radius: 22px;
      --accent: #9ae6ff;
      --accent2: #b5ffcc;
      --danger: #ff6b6b;
      --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      --sans: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
    }
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: var(--sans);
      color: var(--text);
      background:
        radial-gradient(1200px 700px at 20% 10%, rgba(154,230,255,0.15), transparent 55%),
        radial-gradient(900px 500px at 80% 30%, rgba(181,255,204,0.12), transparent 60%),
        radial-gradient(900px 700px at 40% 90%, rgba(255,255,255,0.06), transparent 60%),
        var(--bg);
      min-height: 100vh;
    }
    a { color: inherit; text-decoration: none; }
    .wrap {
      max-width: 1080px;
      margin: 0 auto;
      padding: 28px 18px 70px;
    }
    .topbar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      padding: 12px 0 22px;
    }
    .brand {
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 800;
      letter-spacing: 0.2px;
    }
    .logo {
      width: 34px;
      height: 34px;
      border-radius: 10px;
      background: linear-gradient(135deg, rgba(154,230,255,0.95), rgba(181,255,204,0.9));
      box-shadow: 0 10px 28px rgba(0,0,0,0.35);
    }
    .pill {
      padding: 8px 12px;
      border-radius: 999px;
      border: 1px solid var(--stroke);
      background: rgba(255,255,255,0.04);
      color: var(--muted);
      font-size: 13px;
    }
    .grid {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      gap: 18px;
      margin-top: 10px;
    }
    @media (max-width: 920px) {
      .grid { grid-template-columns: 1fr; }
    }
    .card {
      border: 1px solid var(--stroke);
      background: var(--card);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      overflow: hidden;
    }
    .hero {
      padding: 34px 26px 28px;
      position: relative;
    }
    .hero h1 {
      margin: 0;
      font-size: clamp(30px, 4vw, 46px);
      line-height: 1.05;
      letter-spacing: -0.5px;
    }
    .hero p {
      margin: 14px 0 0;
      color: var(--muted);
      font-size: 16px;
      line-height: 1.55;
      max-width: 60ch;
    }
    .bullets {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
      margin: 18px 0 0;
    }
    @media (max-width: 520px) { .bullets { grid-template-columns: 1fr; } }
    .bullet {
      border: 1px solid var(--stroke);
      background: rgba(255,255,255,0.035);
      border-radius: 16px;
      padding: 12px 12px;
      display: flex;
      gap: 10px;
      align-items: flex-start;
    }
    .bullet b { display: block; font-size: 13.5px; }
    .bullet span { display: block; margin-top: 2px; font-size: 12.5px; color: var(--muted); }
    .dot {
      width: 10px; height: 10px; border-radius: 99px;
      margin-top: 4px;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      box-shadow: 0 0 0 4px rgba(154,230,255,0.10);
    }
    .ctaRow {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      margin-top: 18px;
      align-items: center;
    }
    .btn {
      border: 1px solid rgba(255,255,255,0.14);
      background: rgba(255,255,255,0.06);
      color: var(--text);
      padding: 11px 14px;
      border-radius: 14px;
      font-weight: 700;
      font-size: 14px;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      cursor: pointer;
    }
    .btnPrimary {
      background: linear-gradient(135deg, rgba(154,230,255,0.32), rgba(181,255,204,0.22));
      border-color: rgba(154,230,255,0.32);
    }
    .btn:hover { background: rgba(255,255,255,0.09); }
    .btnPrimary:hover { filter: brightness(1.06); }
    .fineprint { color: var(--muted); font-size: 12.5px; }
    .side {
      padding: 18px;
      display: grid;
      gap: 14px;
    }
    .side .panel {
      border: 1px solid var(--stroke);
      background: var(--card2);
      border-radius: 18px;
      padding: 14px;
    }
    .panel h3 { margin: 0 0 6px; font-size: 14px; letter-spacing: 0.2px; }
    .panel p { margin: 0; color: var(--muted); font-size: 13px; line-height: 1.5; }
    .metric {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
      margin-top: 12px;
    }
    .metric .m {
      border: 1px solid var(--stroke);
      background: rgba(0,0,0,0.10);
      border-radius: 16px;
      padding: 12px;
    }
    .m .v { font-size: 20px; font-weight: 900; }
    .m .k { font-size: 12px; color: var(--muted); margin-top: 4px; }
    .footer {
      margin-top: 18px;
      color: var(--muted);
      font-size: 12px;
      display: flex;
      justify-content: space-between;
      gap: 10px;
      flex-wrap: wrap;
    }
    .kbd { font-family: var(--mono); font-size: 12px; opacity: .9; }
    /* Embedded form container */
    .embedWrap {
      border-top: 1px solid var(--stroke);
      background: rgba(0,0,0,0.14);
      padding: 14px 14px 18px;
    }
    .embedTitle {
      display:flex; justify-content: space-between; align-items: baseline; gap: 10px;
      padding: 10px 10px 14px;
    }
    .embedTitle b { font-size: 13px; }
    .embedTitle span { color: var(--muted); font-size: 12px; }
    iframe {
      width: 100%;
      height: 520px;
      border: 0;
      border-radius: 18px;
      background: white;
    }
  </style>
</head>
<body>
  <div class="wrap">
    <div class="topbar">
      <div class="brand">
        <div class="logo"></div>
        <div>FieldOps</div>
      </div>
      <div class="pill">Early access • iOS-first • Built for local service pros</div>
    </div>

    <div class="grid">
      <div class="card">
        <div class="hero">
          <h1>Run jobs, invoices, and follow-ups on autopilot.</h1>
          <p>
            FieldOps is a simple operations app for local service businesses:
            schedule jobs, send invoice reminders, and automate follow-ups—without
            messy spreadsheets.
          </p>

          <div class="bullets">
            <div class="bullet"><div class="dot"></div><div><b>Automations that matter</b><span>Reminders, review requests, overdue nudges.</span></div></div>
            <div class="bullet"><div class="dot"></div><div><b>Invoices that don’t get ignored</b><span>Clear totals + due dates + one-tap message.</span></div></div>
            <div class="bullet"><div class="dot"></div><div><b>Built for the field</b><span>Fast, minimal taps, works great on iPhone.</span></div></div>
            <div class="bullet"><div class="dot"></div><div><b>Private by default</b><span>No ads. Your data stays yours.</span></div></div>
          </div>

          <div class="ctaRow">
            <a class="btn btnPrimary" href="#waitlist">Join the waitlist →</a>
            <a class="btn" href="#what">What’s included</a>
            <span class="fineprint">No spam. Early access invites only.</span>
          </div>
        </div>

        <div class="embedWrap" id="waitlist">
          <div class="embedTitle">
            <b>Get early access</b>
            <span>Drop your email. We’ll invite you first.</span>
          </div>

          <!-- ✅ Paste your Google Form embed iframe below (replace the src) -->
          <iframe
            src="P<iframe src="https://docs.google.com/forms/d/e/1FAIpQLSeffuMaEtbwTIugLU6B5U0CaNrig9kPN2n6GhiRPy8IMEaL5A/viewform?embedded=true" width="640" height="694" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>"
            loading="lazy"
          ></iframe>

          <div class="footer">
            <div>© <span id="year"></span> FieldOps</div>
            <div class="kbd">Built for: HVAC • Cleaning • Electrical • Handyman</div>
          </div>
        </div>
      </div>
