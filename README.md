# hansexperiment
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Hans — A 10-Year Experiment</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #f7f4ef;
      --ink: #1a1814;
      --muted: #6b6760;
      --border: #dedad3;
      --accent: #b5451b;
      --accent-light: #f0ebe4;
      --max: 720px;
      --serif: 'Libre Baskerville', Georgia, serif;
      --sans: 'DM Sans', system-ui, sans-serif;
    }

    body {
      background: var(--cream);
      color: var(--ink);
      font-family: var(--sans);
      font-size: 16px;
      line-height: 1.7;
    }

    /* ── HEADER ── */
    header {
      border-bottom: 1px solid var(--border);
      padding: 2rem 1.5rem 1.5rem;
      text-align: center;
    }
    .site-label {
      font-family: var(--sans);
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 0.6rem;
    }
    .site-title {
      font-family: var(--serif);
      font-size: clamp(2rem, 5vw, 3rem);
      font-weight: 700;
      line-height: 1.15;
      color: var(--ink);
      margin-bottom: 0.5rem;
    }
    .site-subtitle {
      font-size: 15px;
      color: var(--muted);
      font-style: italic;
      font-family: var(--serif);
    }

    /* ── NAV ── */
    nav {
      display: flex;
      justify-content: center;
      gap: 2rem;
      padding: 0.9rem 1.5rem;
      border-bottom: 1px solid var(--border);
      font-size: 13px;
      font-weight: 500;
      letter-spacing: 0.05em;
    }
    nav a {
      text-decoration: none;
      color: var(--muted);
      transition: color 0.15s;
    }
    nav a:hover { color: var(--accent); }
    nav a.active { color: var(--ink); border-bottom: 1.5px solid var(--ink); padding-bottom: 2px; }

    /* ── LAYOUT ── */
    .container {
      max-width: var(--max);
      margin: 0 auto;
      padding: 0 1.5rem;
    }

    /* ── FEATURED POST ── */
    .featured {
      padding: 3rem 0 2.5rem;
      border-bottom: 1px solid var(--border);
    }
    .featured .tag {
      display: inline-block;
      font-size: 10px;
      font-weight: 500;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--accent);
      background: var(--accent-light);
      padding: 3px 10px;
      border-radius: 2px;
      margin-bottom: 1rem;
    }
    .featured h2 {
      font-family: var(--serif);
      font-size: clamp(1.5rem, 3.5vw, 2.1rem);
      font-weight: 700;
      line-height: 1.2;
      margin-bottom: 0.9rem;
      color: var(--ink);
    }
    .featured h2 a { text-decoration: none; color: inherit; }
    .featured h2 a:hover { color: var(--accent); }
    .featured .excerpt {
      font-size: 16px;
      color: var(--muted);
      max-width: 60ch;
      margin-bottom: 1.2rem;
    }
    .meta {
      font-size: 12px;
      color: var(--muted);
      letter-spacing: 0.03em;
    }
    .meta span + span::before { content: ' · '; }

    /* ── POST LIST ── */
    .post-list {
      padding: 2.5rem 0;
    }
    .section-heading {
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 1.5rem;
      padding-bottom: 0.6rem;
      border-bottom: 1px solid var(--border);
    }
    .post-item {
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 0.5rem 1.5rem;
      align-items: baseline;
      padding: 1.1rem 0;
      border-bottom: 1px solid var(--border);
      text-decoration: none;
      color: inherit;
      transition: opacity 0.15s;
    }
    .post-item:hover { opacity: 0.75; }
    .post-item:first-of-type { border-top: none; }
    .post-item-title {
      font-family: var(--serif);
      font-size: 17px;
      font-weight: 400;
      line-height: 1.35;
      color: var(--ink);
    }
    .post-item-title em {
      font-style: normal;
      color: var(--accent);
    }
    .post-item-date {
      font-size: 12px;
      color: var(--muted);
      white-space: nowrap;
    }

    /* ── ABOUT STRIP ── */
    .about-strip {
      background: var(--accent-light);
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      padding: 2rem 1.5rem;
      margin: 0 0 2.5rem;
    }
    .about-strip .container {
      display: flex;
      gap: 1.5rem;
      align-items: flex-start;
    }
    .avatar {
      width: 52px;
      height: 52px;
      border-radius: 50%;
      background: var(--accent);
      color: #fff;
      font-family: var(--serif);
      font-size: 1.3rem;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
    }
    .about-text { font-size: 14px; color: var(--muted); line-height: 1.65; }
    .about-text strong { color: var(--ink); font-weight: 500; }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid var(--border);
      padding: 1.5rem;
      text-align: center;
      font-size: 12px;
      color: var(--muted);
    }
    footer a { color: var(--accent); text-decoration: none; }
    footer a:hover { text-decoration: underline; }

    /* ── RESPONSIVE ── */
    @media (max-width: 500px) {
      .post-item { grid-template-columns: 1fr; }
      .post-item-date { margin-top: -0.4rem; }
      .about-strip .container { flex-direction: column; gap: 1rem; }
      nav { gap: 1.2rem; flex-wrap: wrap; }
    }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header>
    <p class="site-label">A Personal Blog</p>
    <h1 class="site-title">Hans</h1>
    <p class="site-subtitle">A 10-Year Experiment</p>
  </header>

  <!-- NAV -->
  <nav>
    <a href="#" class="active">Home</a>
    <a href="#">Essays</a>
    <a href="#">Notes</a>
    <a href="#">About</a>
  </nav>

  <!-- FEATURED POST -->
  <div class="container">
    <section class="featured">
      <span class="tag">Latest</span>
      <h2><a href="#">Why I'm Treating the Next Decade as One Big Experiment</a></h2>
      <p class="excerpt">
        I didn't set out to plan 10 years of my life. It started with a single question: what would I do differently if I weren't afraid of being wrong? This is the answer I'm still writing.
      </p>
      <p class="meta">
        <span>Hans</span>
        <span>March 26, 2025</span>
        <span>7 min read</span>
      </p>
    </section>
  </div>

  <!-- POST LIST -->
  <div class="container">
    <section class="post-list">
      <p class="section-heading">All Posts</p>

      <a class="post-item" href="#">
        <span class="post-item-title">The Rules I Set for Myself — and the Ones I Already Broke</span>
        <span class="post-item-date">Mar 12, 2025</span>
      </a>

      <a class="post-item" href="#">
        <span class="post-item-title">On Learning French at 22: <em>Embarrassing</em>, Useful, Necessary</span>
        <span class="post-item-date">Feb 28, 2025</span>
      </a>

      <a class="post-item" href="#">
        <span class="post-item-title">What a GPA Actually Measures (And What It Doesn't)</span>
        <span class="post-item-date">Feb 14, 2025</span>
      </a>

      <a class="post-item" href="#">
        <span class="post-item-title">Europe, Eventually: Notes on Researching Master's Programs Abroad</span>
        <span class="post-item-date">Jan 30, 2025</span>
      </a>

      <a class="post-item" href="#">
        <span class="post-item-title">The Spreadsheet That Runs My Life (For Now)</span>
        <span class="post-item-date">Jan 15, 2025</span>
      </a>

      <a class="post-item" href="#">
        <span class="post-item-title">Year Zero: What I'm Starting With, and What I'm Starting From</span>
        <span class="post-item-date">Jan 1, 2025</span>
      </a>

    </section>
  </div>

  <!-- ABOUT STRIP -->
  <div class="about-strip">
    <div class="container">
      <div class="avatar">H</div>
      <p class="about-text">
        <strong>Hi, I'm Hans.</strong> This blog is a public record of a private experiment. I'm a university student studying Business Information Systems, learning French, planning a Master's somewhere in Europe, and trying to figure out what kind of person I want to be by the time the decade is up. I write to think — and occasionally to embarrass my future self.
      </p>
    </div>
  </div>

  <!-- FOOTER -->
  <footer>
    <p>© 2025 Hans · <a href="#">RSS</a> · <a href="#">Email me</a></p>
  </footer>

</body>
</html>
