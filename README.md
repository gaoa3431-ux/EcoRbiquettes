# EcoBriquettes

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Eco Briquettes | Fueling Change with Every Briquette</title>
  <style>
    :root {
      --forest: #3f5f26;
      --forest-dark: #2d421d;
      --leaf: #d7dfc6;
      --light-green: #d7dfc6;
      --moss: #78805b;
      --beige: #fff4eb;
      --brown: #806344;
      --dark-brown: #4f3b2b;
      --cream: #f1eadf;
    }
    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: var(--forest-dark);
      color: var(--cream);
      line-height: 1.65;
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      background:
        linear-gradient(rgba(36,72,5,0.80), rgba(36,72,5,0.84)),
        url("https://images.unsplash.com/photo-1448375240586-882707db888b?auto=format&fit=crop&w=1800&q=80") center/cover no-repeat;
      z-index: -3;
    }

    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      z-index: 100;
      padding: 18px 7%;
      background: var(--light-green);
      border-bottom: 3px solid rgba(74,45,24,0.18);
      box-shadow: 0 8px 24px rgba(36,72,5,0.18);
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 24px;
    }

    .logo {
      font-size: 1.22rem;
      font-weight: 900;
      letter-spacing: 0.5px;
      color: var(--forest-dark);
    }

    .nav-links {
      display: flex;
      gap: 22px;
      flex-wrap: wrap;
    }

    .nav-links a {
      color: var(--forest-dark);
      text-decoration: none;
      font-size: 0.95rem;
      font-weight: 900;
      opacity: 0.9;
    }

    .nav-links a:hover { opacity: 1; text-decoration: underline; }

    section {
      scroll-margin-top: 86px;
      position: relative;
      min-height: 100vh;
      padding: 110px 7% 90px;
      display: flex;
      align-items: center;
      overflow: hidden;
      background: var(--forest);
    }

    .section-bg {
      position: absolute;
      inset: 0;
      background-size: cover;
      background-position: center;
      z-index: -2;
      transform: scale(1.04);
      filter: saturate(1.18);
    }

    .section-bg::after {
      content: "";
      position: absolute;
      inset: 0;
      background:
        linear-gradient(90deg, rgba(49,95,8,0.86), rgba(49,95,8,0.38), rgba(49,95,8,0.76)),
        radial-gradient(circle at 18% 20%, rgba(220,234,196,0.24), transparent 32%),
        radial-gradient(circle at 82% 72%, rgba(217,198,183,0.22), transparent 34%);
      z-index: 1;
    }

    .home-bg { background-image: url("https://images.unsplash.com/photo-1425913397330-cf8af2ff40a1?auto=format&fit=crop&w=1800&q=90"); filter: saturate(1.22) brightness(1.08) contrast(1.03); }
    .impact-bg { background-image: url("https://images.unsplash.com/photo-1473773508845-188df298d2d1?auto=format&fit=crop&w=1800&q=80"); filter: saturate(1.18); }
    .experiment-bg { background-image: url("https://images.unsplash.com/photo-1518495973542-4542c06a5843?auto=format&fit=crop&w=1800&q=80"); filter: saturate(1.18); }
    .location-bg { background-image: url("https://images.unsplash.com/photo-1542601906990-b4d3fb778b09?auto=format&fit=crop&w=1800&q=80"); filter: saturate(1.18); }

    .content {
      width: min(1180px, 100%);
      margin: 0 auto;
      position: relative;
      z-index: 2;
    }

    .split {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 34px;
      align-items: center;
    }

    .floating-title {
      max-width: 820px;
      animation: titleFloatIn 1.1s ease both, slowDrift 6s ease-in-out infinite 1.2s;
    }

    .eyebrow {
      display: inline-block;
      padding: 8px 14px;
      border-radius: 999px;
      background: #fff4eb;
      border: 1px solid rgba(74,45,24,0.18);
      color: var(--forest-dark);
      font-size: 0.9rem;
      font-weight: 900;
      letter-spacing: 0.4px;
      margin-bottom: 20px;
    }

    h1, h2 {
      font-size: clamp(2.8rem, 6vw, 6.2rem);
      line-height: 0.96;
      letter-spacing: -2px;
      margin-bottom: 24px;
      color: var(--beige);
      text-shadow: 0 10px 30px rgba(36,72,5,0.45);
    }

    h3 {
      font-size: 1.35rem;
      margin-bottom: 8px;
      color: var(--forest-dark);
    }

    .lead {
      font-size: clamp(1.1rem, 2vw, 1.35rem);
      max-width: 780px;
      color: rgba(244,234,219,0.95);
      margin-bottom: 26px;
    }

    .button-row { display: flex; gap: 14px; flex-wrap: wrap; }

    .button {
      display: inline-block;
      padding: 13px 24px;
      border-radius: 999px;
      background: var(--beige);
      color: var(--forest-dark);
      text-decoration: none;
      font-weight: 900;
      box-shadow: 0 12px 30px rgba(36,72,5,0.28);
      border: 1px solid rgba(244,234,219,0.35);
      transition: transform 0.25s ease, box-shadow 0.25s ease, background 0.25s ease;
      animation: softPulse 3.8s ease-in-out infinite;
    }

    .button:hover {
      transform: translateY(-4px) scale(1.03);
      box-shadow: 0 18px 42px rgba(36,72,5,0.34);
    }

    .button.dark {
      background: var(--brown);
      color: var(--cream);
    }

    .floating-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px;
      margin-top: 34px;
    }

    .floating-card {
      background: #fff4eb;
      border: 1px solid rgba(74,45,24,0.18);
      border-radius: 26px;
      padding: 26px;
      color: var(--forest-dark);
      box-shadow: 0 22px 50px rgba(36,72,5,0.28);
      transform: translateY(28px);
      opacity: 0;
      animation: floatUp 800ms ease both, cardBreath 5.5s ease-in-out infinite;
      transition: transform 0.28s ease, box-shadow 0.28s ease;
    }

    .floating-card:hover {
      transform: translateY(-8px) scale(1.025);
      box-shadow: 0 30px 70px rgba(36,72,5,0.34);
    }

    .floating-card:nth-child(1) { animation-delay: 180ms; }
    .floating-card:nth-child(2) { animation-delay: 360ms; }
    .floating-card:nth-child(3) { animation-delay: 540ms; }
    .floating-card:nth-child(4) { animation-delay: 720ms; }
    .floating-card:nth-child(5) { animation-delay: 900ms; }
    .floating-card:nth-child(6) { animation-delay: 1080ms; }

    .floating-card p, .mini-card p { color: var(--forest-dark); }

    .stat-strip {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 16px;
      margin-top: 30px;
    }

    .stat {
      padding: 22px;
      border-radius: 22px;
      background: #fff4eb;
      border: 1px solid rgba(74,45,24,0.18);
      color: var(--forest-dark);
      box-shadow: 0 18px 40px rgba(36,72,5,0.22);
      animation: floatUp 900ms ease both, gentleBob 4.8s ease-in-out infinite;
      transition: transform 0.25s ease;
    }

    .stat:hover {
      transform: translateY(-6px) rotate(-0.5deg);
    }

    .stat strong {
      display: block;
      font-size: 2rem;
      margin-bottom: 4px;
    }

    .process {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 16px;
      margin-top: 34px;
    }

    .mini-card {
      background: #fff4eb;
      border: 1px solid rgba(74,45,24,0.18);
      border-radius: 24px;
      padding: 22px;
      color: var(--forest-dark);
      box-shadow: 0 18px 40px rgba(36,72,5,0.22);
      animation: floatUp 900ms ease both, gentleBob 5.2s ease-in-out infinite;
      transition: transform 0.25s ease, box-shadow 0.25s ease;
    }

    .mini-card:hover {
      transform: translateY(-7px) scale(1.02);
      box-shadow: 0 26px 58px rgba(36,72,5,0.30);
    }

    .number {
      width: 40px;
      height: 40px;
      border-radius: 50%;
      background: var(--forest);
      color: var(--cream);
      display: grid;
      place-items: center;
      font-weight: 900;
      margin-bottom: 14px;
    }

    .product-panel {
      background: #fff4eb;
      color: var(--forest-dark);
      border-radius: 30px;
      overflow: hidden;
      box-shadow: 0 25px 70px rgba(36,72,5,0.36);
      animation: floatInRight 1000ms ease both, imagePanelFloat 6s ease-in-out infinite 1s;
      transition: transform 0.3s ease;
    }

    .product-panel:hover {
      transform: translateY(-8px) rotate(0.5deg);
    }

    .product-photo {
      height: 330px;
      margin: 24px;
      border-radius: 50% 50% 46% 46%;
      background: url("https://images.unsplash.com/photo-1425913397330-cf8af2ff40a1?auto=format&fit=crop&w=1200&q=90") center/cover no-repeat;
      filter: saturate(1.22) brightness(1.08) contrast(1.03);
    }

    .product-info { padding: 26px; }
    .product-info h3 { color: var(--forest-dark); font-size: 1.7rem; }
    .product-info p { color: var(--dark-brown); }

    .data-table {
      width: 100%;
      border-collapse: collapse;
      overflow: hidden;
      border-radius: 24px;
      background: #fff4eb;
      color: var(--forest-dark);
      box-shadow: 0 20px 45px rgba(36,72,5,0.28);
      margin-top: 26px;
      animation: floatUp 900ms ease both;
    }

    .data-table th {
      background: var(--brown);
      color: var(--cream);
      padding: 14px;
      text-align: left;
    }

    .data-table td {
      padding: 14px;
      border-bottom: 1px solid var(--light-brown);
    }

    .location-card {
      background: #fff4eb;
      color: var(--forest-dark);
      border-radius: 30px;
      padding: 32px;
      box-shadow: 0 25px 70px rgba(36,72,5,0.36);
      animation: floatInRight 1000ms ease both, imagePanelFloat 6s ease-in-out infinite 1s;
      transition: transform 0.3s ease;
    }

    .location-card:hover {
      transform: translateY(-8px) rotate(0.4deg);
    }

    .location-card h3 { color: var(--forest-dark); font-size: 2rem; }
    .location-card p { color: var(--dark-brown); margin-bottom: 12px; }

    .photo-row {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
      margin-top: 18px;
    }

    .photo-tile {
      min-height: 130px;
      border-radius: 50% 50% 44% 44%;
      background-size: cover;
      background-position: center;
      border: 8px solid rgba(255,244,235,0.78);
      filter: saturate(1.18);
      animation: photoFloat 5.4s ease-in-out infinite;
      transition: transform 0.28s ease;
    }

    .photo-tile:nth-child(2) { animation-delay: 0.6s; }
    .photo-tile:nth-child(3) { animation-delay: 1.2s; }

    .photo-tile:hover {
      transform: scale(1.06) rotate(1deg);
    }

    .photo-1 { background-image: url("https://images.unsplash.com/photo-1604187351574-c75ca79f5807?auto=format&fit=crop&w=800&q=80"); }
    .photo-2 { background-image: url("https://images.unsplash.com/photo-1556761175-b413da4baf72?auto=format&fit=crop&w=800&q=80"); }
    .photo-3 { background-image: url("https://images.unsplash.com/photo-1500534314209-a25ddb2bd429?auto=format&fit=crop&w=800&q=80"); }

    .footer-note {
      position: relative;
      background: var(--forest-dark);
      padding: 28px 7%;
      text-align: center;
      color: var(--beige);
    }

    @keyframes floatUp {
      from { opacity: 0; transform: translateY(34px) scale(0.98); }
      to { opacity: 1; transform: translateY(0) scale(1); }
    }

    @keyframes titleFloatIn {
      from { opacity: 0; transform: translateY(34px) scale(0.98); filter: blur(4px); }
      to { opacity: 1; transform: translateY(0) scale(1); filter: blur(0); }
    }

    @keyframes slowDrift {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-8px); }
    }

    @keyframes gentleBob {
      0%, 100% { translate: 0 0; }
      50% { translate: 0 -6px; }
    }

    @keyframes cardBreath {
      0%, 100% { scale: 1; }
      50% { scale: 1.012; }
    }

    @keyframes imagePanelFloat {
      0%, 100% { translate: 0 0; }
      50% { translate: 0 -10px; }
    }

    @keyframes photoFloat {
      0%, 100% { translate: 0 0; }
      50% { translate: 0 -7px; }
    }

    @keyframes softPulse {
      0%, 100% { box-shadow: 0 12px 30px rgba(36,72,5,0.24); }
      50% { box-shadow: 0 18px 44px rgba(36,72,5,0.36); }
    }

    @keyframes floatIn {
      from { opacity: 0; transform: translateY(22px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes floatInRight {
      from { opacity: 0; transform: translateX(36px) translateY(18px); }
      to { opacity: 1; transform: translateX(0) translateY(0); }
    }

    .word-float {
      display: inline-block;
      animation: wordRise 900ms ease both;
    }

    .word-float.delay-1 { animation-delay: 120ms; }
    .word-float.delay-2 { animation-delay: 240ms; }
    .word-float.delay-3 { animation-delay: 360ms; }

    @keyframes wordRise {
      from { opacity: 0; transform: translateY(24px) rotate(-1deg); }
      to { opacity: 1; transform: translateY(0) rotate(0); }
    }

    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        scroll-behavior: auto !important;
      }
    }

    @media (max-width: 980px) {
      section { padding-top: 130px; }
      .split, .floating-grid, .stat-strip, .process, .photo-row { grid-template-columns: 1fr; }
      nav { align-items: flex-start; }
      .nav-links { gap: 12px; }
      h1, h2 { letter-spacing: -1px; }
    }
  </style>
</head>
<body>
  <header>
    <nav>
      <div class="logo">Eco Briquettes</div>
      <div class="nav-links">
        <a href="#home">Home</a>
        <a href="#impact">Impact</a>
        <a href="#experiment">Experiment</a>
        <a href="#location">Location</a>
      </div>
    </nav>
  </header>

  <main>
    <section id="home" aria-label="Home page">
      <div class="section-bg home-bg"></div>
      <div class="content split">
        <div class="floating-title">
          <span class="eyebrow">Online Store • Education • Sustainability</span>
          <h1><span class="word-float">Fueling</span> <span class="word-float delay-1">Change</span> <span class="word-float delay-2">with Every</span> <span class="word-float delay-3">Briquette</span></h1>
          <p class="lead">This website introduces and sells environmentally friendly briquettes made from recycled waste. It also educates people about reducing landfill waste, lowering deforestation, and choosing cleaner fuel for a more sustainable future.</p>
          <div class="button-row">
            <a class="button" href="#experiment">View the Investigation</a>
            <a class="button dark" href="#impact">See the Impact</a>
          </div>
          <div class="stat-strip">
            <div class="stat"><strong>3</strong><span>Main waste materials: cardboard, sawdust, coffee grounds.</span></div>
            <div class="stat"><strong>48h</strong><span>Drying time before testing each briquette.</span></div>
            <div class="stat"><strong>3x</strong><span>Repeated tests for more reliable results.</span></div>
          </div>
        </div>

        <div class="product-panel">
          <div class="product-photo"></div>
          <div class="product-info">
            <h3>Store and learning platform</h3>
            <p>Customers can purchase sustainable briquettes while learning about our mission to turn everyday waste into renewable heat and support environmental protection.</p>
          </div>
        </div>
      </div>
    </section>

    <section id="impact" aria-label="Impact page">
      <div class="section-bg impact-bg"></div>
      <div class="content">
        <div class="floating-title">
          <span class="eyebrow">Impact Page</span>
          <h2><span class="word-float">Real Impact</span> <span class="word-float delay-1">for Community,</span> <span class="word-float delay-2">New Zealand,</span> <span class="word-float delay-3">and Beyond</span></h2>
          <p class="lead">Eco briquettes are more than a product idea. They connect science, economics, waste management, heating costs, and environmental responsibility.</p>
        </div>

        <div class="floating-grid">
          <div class="floating-card">
            <h3>Small Community</h3>
            <p>Local cafes, schools, workshops, and families can collect coffee grounds, cardboard, and sawdust instead of sending them to landfill. Waste becomes a shared local resource.</p>
          </div>
          <div class="floating-card">
            <h3>New Zealand</h3>
            <p>Many homes still use fireplaces or wood burners in winter. Briquettes could reduce pressure on firewood supply while encouraging practical recycling habits.</p>
          </div>
          <div class="floating-card">
            <h3>Lower-Income Families</h3>
            <p>If produced safely and cheaply, briquettes could become a lower-cost heating option for households struggling with winter energy bills.</p>
          </div>
          <div class="floating-card">
            <h3>Traditional Heating</h3>
            <p>Briquettes do not need to replace traditional heating immediately. They can work alongside fireplaces and wood burners while using recycled materials.</p>
          </div>
          <div class="floating-card">
            <h3>Environmental Impact</h3>
            <p>Reusing cardboard, sawdust, and coffee grounds reduces landfill waste and gives discarded materials a second life as useful heat energy.</p>
          </div>
          <div class="floating-card">
            <h3>Global Potential</h3>
            <p>The idea can be adapted in many countries where biomass waste is common and affordable heating is needed. A small local experiment can become a global model.</p>
          </div>
        </div>
      </div>
    </section>

    <section id="experiment" aria-label="Experiment page">
      <div class="section-bg experiment-bg"></div>
      <div class="content">
        <div class="floating-title">
          <span class="eyebrow">Experiment Page</span>
          <h2><span class="word-float">The Thinking</span> <span class="word-float delay-1">and Investigation</span> <span class="word-float delay-2">Process</span></h2>
          <p class="lead">This project belongs to the physical and material world because it studies how different materials burn and produce heat energy. By compressing cardboard, dry coffee grounds, and wood-cutting residues into briquettes, we investigate combustion, energy release, and material properties.</p>
        </div>

        <div class="floating-grid">
          <div class="floating-card">
            <h3>Research Question</h3>
            <p>Can compressed cardboard and sawdust produce enough heat to become an alternative to firewood during winter?</p>
          </div>
          <div class="floating-card">
            <h3>Hypothesis</h3>
            <p>If sawdust, dry coffee grounds, and discarded cardboard are combined and compressed into briquettes, they will burn for a comparable duration and produce heat output comparable to traditional firewood.</p>
          </div>
          <div class="floating-card">
            <h3>Fair Testing</h3>
            <p>Compression must be consistent. If briquettes are not the same size or density as normal firewood-style blocks, the experiment will not be fair.</p>
          </div>
        </div>

        <div class="process">
          <div class="mini-card"><div class="number">1</div><h3>Collect</h3><p>Gather sawdust, clean cardboard, and dry coffee grounds.</p></div>
          <div class="mini-card"><div class="number">2</div><h3>Mix</h3><p>Mix cardboard with water, then combine with sawdust and coffee grounds.</p></div>
          <div class="mini-card"><div class="number">3</div><h3>Compress</h3><p>Use a briquette press and weight to squeeze out water and shape the briquette.</p></div>
          <div class="mini-card"><div class="number">4</div><h3>Test</h3><p>Measure burning time and temperature increase using repeated trials.</p></div>
        </div>

        <table class="data-table">
          <thead>
            <tr><th>Mixture</th><th>Sawdust</th><th>Cardboard</th><th>Coffee Grounds</th><th>Expected Result</th></tr>
          </thead>
          <tbody>
            <tr><td>Mix A</td><td>80%</td><td>20%</td><td>10g</td><td>Higher heat, weaker structure</td></tr>
            <tr><td>Mix B</td><td>70%</td><td>30%</td><td>10g</td><td>Balanced structure and efficient burning</td></tr>
            <tr><td>Mix C</td><td>60%</td><td>40%</td><td>10g</td><td>Strongest structure, slightly lower heat</td></tr>
          </tbody>
        </table>
      </div>
    </section>

    <section id="location" aria-label="Location page">
      <div class="section-bg location-bg"></div>
      <div class="content split">
        <div class="floating-title">
          <span class="eyebrow">Location Page</span>
          <h2><span class="word-float">Visit,</span> <span class="word-float delay-1">Contact,</span> <span class="word-float delay-2">and Get Involved</span></h2>
          <p class="lead">This page is for customers, judges, and community members who want to learn more about the briquettes, see the product, or contact the team.</p>
          <div class="button-row">
            <a class="button" href="#home">Back to Home</a>
            <a class="button dark" href="#experiment">View Experiment</a>
          </div>
        </div>

        <div class="location-card">
          <h3>Eco Briquettes Project Stall</h3>
          <p><strong>Location:</strong> Auckland, New Zealand</p>
          <p><strong>Phone:</strong> 021 000 0000</p>
          <p><strong>Product:</strong> Recycled cardboard, sawdust, and coffee-ground briquettes</p>
          <p><strong>Purpose:</strong> Online store and educational platform for sustainable briquettes made from recycled waste.</p>
          <div class="photo-row">
            <div class="photo-tile photo-1"></div>
            <div class="photo-tile photo-2"></div>
            <div class="photo-tile photo-3"></div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <div class="footer-note">Eco Briquettes Science Project | Turning everyday waste into cleaner winter warmth</div>
</body>
</html>
