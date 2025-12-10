# My-web<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <meta name="description" content="Crypto portfolio — projects, holdings, performance and contact." />
  <title>Your Name — Crypto Portfolio</title>

  <!-- Favicons / Theme -->
  <meta name="theme-color" content="#0b1220" />
  <link rel="icon" href="data:;base64,iVBORw0KGgo=">

  <!-- Google font (optional) -->
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

  <link rel="stylesheet" href="styles.css" />
</head>
<body class="light">
  <header class="site-header">
    <div class="container header-inner">
      <a class="brand" href="#hero">Your Name</a>

      <nav id="nav" class="nav">
        <a href="#about">About</a>
        <a href="#projects">Projects</a>
        <a href="#portfolio">Holdings</a>
        <a href="#blog">Blog</a>
        <a href="#contact">Contact</a>
        <button id="themeToggle" class="btn-ghost" aria-pressed="false" title="Toggle dark/light">🌙</button>
      </nav>

      <button id="mobileToggle" class="mobile-toggle" aria-expanded="false" aria-label="Open menu">
        ☰
      </button>
    </div>
  </header>

  <main>
    <!-- HERO -->
    <section id="hero" class="hero container">
      <div class="hero-left">
        <h1>I'm <span class="accent">Your Name</span> — crypto investor & builder</h1>
        <p class="lead">
          I research tokens, build smart contracts, and manage liquidity & yield strategies.
          This site shows projects, holdings, and live performance.
        </p>
        <div class="hero-ctas">
          <a class="btn-primary" href="#portfolio">View Holdings</a>
          <a class="btn-outline" href="#projects">My Projects</a>
        </div>
        <div class="wallet-area">
          <button id="connectWallet" class="btn-ghost">Connect Wallet</button>
          <div id="walletAddress" class="mono small muted"></div>
        </div>
      </div>
      <div class="hero-right">
        <div class="card stats-card">
          <h3>Portfolio snapshot</h3>
          <div class="grid">
            <div>
              <div class="muted small">Total value</div>
              <div id="totalValue" class="big mono">—</div>
            </div>
            <div>
              <div class="muted small">24h change</div>
              <div id="dayChange" class="big mono">—</div>
            </div>
            <div>
              <div class="muted small">Positions</div>
              <div id="positionsCount" class="big mono">—</div>
            </div>
            <div>
              <div class="muted small">Updated</div>
              <div id="lastUpdated" class="big mono">—</div>
            </div>
          </div>
        </div>
        <div class="card pricefeed" aria-live="polite">
          <h4>Live prices</h4>
          <ul id="priceList" class="price-list">
            <!-- filled by JS -->
          </ul>
        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about" class="container section">
      <div class="section-grid">
        <div>
          <h2>About me</h2>
          <p>I’m a crypto investor and developer focused on DeFi, NFTs and infrastructure. I research tokenomics, audit contracts at an initial level, and build experiments in Solidity & web3.js/ethers.js.</p>

          <ul class="bullets">
            <li>Smart contracts: Solidity, Hardhat</li>
            <li>Frontend: React, Next.js</li>
            <li>On-chain analytics & research</li>
          </ul>
        </div>
        <div class="card">
          <h4>Quick facts</h4>
          <dl>
            <dt>Location</dt><dd>City, Country</dd>
            <dt>Availability</dt><dd>Open for consulting</dd>
            <dt>Email</dt><dd><a href="mailto:youremail@example.com">youremail@example.com</a></dd>
          </dl>
        </div>
      </div>
    </section>

    <!-- PROJECTS -->
    <section id="projects" class="container section">
      <h2>Selected projects</h2>
      <div id="projectsGrid" class="projects-grid">
        <!-- JS will fill cards with sample projects - replace with yours -->
      </div>
    </section>

    <!-- PORTFOLIO / HOLDINGS -->
    <section id="portfolio" class="container section">
      <h2>Holdings</h2>
      <p class="muted">This portfolio is client-side demo data. Replace with your real holdings or integrate with wallet for dynamic view.</p>

      <div class="card table-card">
        <table class="table" aria-describedby="portfolioDesc">
          <caption id="portfolioDesc">Current holdings and value (USD)</caption>
          <thead>
            <tr>
              <th>Token</th>
              <th>Symbol</th>
              <th>Amount</th>
              <th>Price (USD)</th>
              <th>Value (USD)</th>
              <th>24h</th>
            </tr>
          </thead>
          <tbody id="portfolioTable">
            <!-- filled by JS -->
          </tbody>
        </table>
      </div>
    </section>

    <!-- BLOG -->
    <section id="blog" class="container section">
      <h2>Notes & research</h2>
      <div class="card">
        <p class="muted">A blog or thread embeds go here (Markdown/Notion/Medium embed). Replace with your posts or connect an RSS feed.</p>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="container section">
      <h2>Contact</h2>
      <div class="section-grid">
        <div>
          <p>Interested in collaborating or consulting? Email me or connect on Twitter/X.</p>
          <p><strong>Email</strong>: <a href="mailto:youremail@example.com">youremail@example.com</a></p>
          <p><strong>Twitter</strong>: <a href="https://twitter.com/yourhandle" target="_blank" rel="noopener">@yourhandle</a></p>
        </div>
        <form id="contactForm" class="card contact-form" onsubmit="handleContact(event)">
          <label>
            Name
            <input name="name" required />
          </label>
          <label>
            Email
            <input name="email" type="email" required />
          </label>
          <label>
            Message
            <textarea name="message" rows="4" required></textarea>
          </label>
          <div class="form-row">
            <button type="submit" class="btn-primary">Send</button>
            <a class="btn-outline" href="resume.pdf" download>Download resume</a>
          </div>
          <div id="contactResult" role="status" aria-live="polite"></div>
        </form>
      </div>
    </section>
  </main>

  <footer class="site-footer">
    <div class="container footer-inner">
      <div>© <span id="year"></span> Your Name — Built with ❤️</div>
      <div class="muted">Privacy · Terms</div>
    </div>
  </footer>

  <!-- Ethers.js for wallet connect (optional) -->
  <script src="https://cdn.jsdelivr.net/npm/ethers@6.9.0/dist/ethers.umd.min.js"></script>
  <script src="script.js" type="module"></script>
</body>
</html>
