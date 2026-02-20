# sandwich-shoppe 
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Sandwich Shoppe | Gallatin, TN</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #f5f0e8;
    --dark: #1a1208;
    --mustard: #d4961a;
    --red: #b83228;
    --tan: #c9b48a;
    --light-tan: #e8dcc8;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--cream);
    color: var(--dark);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.2rem 4rem;
    background: var(--dark);
    border-bottom: 3px solid var(--mustard);
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    color: var(--cream);
    letter-spacing: 0.05em;
  }
  .nav-links { display: flex; gap: 2.5rem; }
  .nav-links a {
    color: var(--tan);
    text-decoration: none;
    font-size: 0.85rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--mustard); }

  /* HERO */
  .hero {
    min-height: 100vh;
    background: var(--dark);
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }
  .hero-texture {
    position: absolute;
    inset: 0;
    background-image: radial-gradient(circle at 20% 50%, rgba(212,150,26,0.08) 0%, transparent 60%),
                      radial-gradient(circle at 80% 20%, rgba(184,50,40,0.06) 0%, transparent 50%);
  }
  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 8rem 4rem 4rem 6rem;
    position: relative;
    z-index: 2;
  }
  .hero-eyebrow {
    font-size: 0.75rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--mustard);
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 1rem;
  }
  .hero-eyebrow::before {
    content: '';
    display: block;
    width: 40px;
    height: 1px;
    background: var(--mustard);
  }
  h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3.5rem, 6vw, 6rem);
    line-height: 1.0;
    color: var(--cream);
    margin-bottom: 1.8rem;
  }
  h1 em {
    font-style: italic;
    color: var(--mustard);
  }
  .hero-desc {
    color: var(--tan);
    font-size: 1.05rem;
    line-height: 1.8;
    max-width: 420px;
    margin-bottom: 3rem;
  }
  .hero-cta {
    display: flex;
    gap: 1.2rem;
    flex-wrap: wrap;
  }
  .btn-primary {
    background: var(--mustard);
    color: var(--dark);
    padding: 0.9rem 2.2rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    text-decoration: none;
    transition: background 0.2s, transform 0.2s;
  }
  .btn-primary:hover { background: #e8a820; transform: translateY(-2px); }
  .btn-outline {
    border: 1px solid var(--tan);
    color: var(--tan);
    padding: 0.9rem 2.2rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.85rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    text-decoration: none;
    transition: border-color 0.2s, color 0.2s;
  }
  .btn-outline:hover { border-color: var(--cream); color: var(--cream); }

  .hero-right {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .hero-visual {
    position: relative;
    width: 420px;
    height: 420px;
  }
  .hero-circle {
    width: 380px;
    height: 380px;
    border-radius: 50%;
    background: radial-gradient(circle at 40% 40%, #2a1f0e, #0f0a04);
    border: 2px solid rgba(212,150,26,0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 10rem;
    position: relative;
  }
  .hero-badge {
    position: absolute;
    bottom: 30px;
    right: 0;
    background: var(--red);
    color: var(--cream);
    padding: 1rem 1.4rem;
    font-family: 'Playfair Display', serif;
    font-size: 0.85rem;
    text-align: center;
    line-height: 1.4;
  }
  .hero-badge strong { font-size: 1.2rem; display: block; }

  /* INFO STRIP */
  .info-strip {
    background: var(--mustard);
    padding: 1rem 4rem;
    display: flex;
    justify-content: center;
    gap: 4rem;
    flex-wrap: wrap;
  }
  .info-item {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--dark);
    letter-spacing: 0.05em;
  }
  .info-item .icon { font-size: 1.1rem; }

  /* SECTION COMMON */
  section { padding: 6rem 6rem; }
  .section-label {
    font-size: 0.7rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 0.8rem;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.2rem, 4vw, 3.5rem);
    line-height: 1.1;
    margin-bottom: 1rem;
  }
  .divider {
    width: 60px;
    height: 3px;
    background: var(--mustard);
    margin: 1.5rem 0 3rem;
  }

  /* STORY */
  .story {
    background: var(--light-tan);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: center;
  }
  .story-text p {
    font-size: 1.05rem;
    line-height: 1.9;
    color: #3a2e1e;
    margin-bottom: 1.2rem;
  }
  .story-card {
    background: var(--dark);
    padding: 3rem;
    color: var(--cream);
    position: relative;
  }
  .story-card::before {
    content: '"';
    font-family: 'Playfair Display', serif;
    font-size: 8rem;
    color: var(--mustard);
    opacity: 0.3;
    position: absolute;
    top: -1rem;
    left: 2rem;
    line-height: 1;
  }
  .story-card blockquote {
    font-family: 'Playfair Display', serif;
    font-style: italic;
    font-size: 1.3rem;
    line-height: 1.7;
    position: relative;
    z-index: 1;
  }
  .story-card cite {
    display: block;
    margin-top: 1.5rem;
    font-family: 'DM Sans', sans-serif;
    font-style: normal;
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--mustard);
  }

  /* MENU */
  .menu { background: var(--cream); }
  .menu-header { text-align: center; margin-bottom: 4rem; }
  .menu-header .divider { margin: 1.5rem auto 3rem; }
  .menu-note {
    display: inline-block;
    background: var(--dark);
    color: var(--tan);
    padding: 0.5rem 1.2rem;
    font-size: 0.8rem;
    letter-spacing: 0.08em;
    margin-top: -1rem;
  }

  .menu-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
    gap: 1.5rem;
  }
  .menu-category {
    border: 1px solid var(--tan);
    overflow: hidden;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .menu-category:hover {
    transform: translateY(-4px);
    box-shadow: 0 12px 40px rgba(0,0,0,0.12);
  }
  .category-header {
    background: var(--dark);
    padding: 1.2rem 1.8rem;
    display: flex;
    align-items: center;
    gap: 1rem;
  }
  .category-icon { font-size: 1.6rem; }
  .category-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    color: var(--cream);
  }
  .category-items { padding: 1.5rem 1.8rem; }
  .menu-item {
    padding: 0.8rem 0;
    border-bottom: 1px dashed var(--light-tan);
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 1rem;
  }
  .menu-item:last-child { border-bottom: none; }
  .item-name {
    font-size: 0.95rem;
    font-weight: 500;
    color: var(--dark);
  }
  .item-desc {
    font-size: 0.8rem;
    color: #7a6a50;
    margin-top: 0.2rem;
    line-height: 1.5;
  }
  .item-price {
    font-family: 'Playfair Display', serif;
    font-size: 1rem;
    color: var(--red);
    white-space: nowrap;
    font-weight: 700;
  }
  .item-popular {
    display: inline-block;
    background: var(--mustard);
    color: var(--dark);
    font-size: 0.6rem;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 0.15rem 0.4rem;
    margin-left: 0.4rem;
    vertical-align: middle;
  }

  /* SIDES */
  .sides-note {
    background: var(--dark);
    color: var(--cream);
    padding: 2rem 3rem;
    margin-top: 2rem;
    display: flex;
    align-items: center;
    gap: 2rem;
    flex-wrap: wrap;
  }
  .sides-note .icon { font-size: 2.5rem; }
  .sides-note h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    margin-bottom: 0.3rem;
  }
  .sides-note p { color: var(--tan); font-size: 0.9rem; line-height: 1.6; }

  /* HOURS & LOCATION */
  .info-section {
    background: var(--dark);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
  }
  .info-col {
    padding: 5rem 5rem;
    position: relative;
  }
  .info-col:first-child {
    border-right: 1px solid rgba(255,255,255,0.08);
  }
  .info-col .section-label { color: var(--mustard); }
  .info-col .section-title { color: var(--cream); }
  .info-col .divider { background: var(--red); }

  .hours-list { list-style: none; }
  .hours-list li {
    display: flex;
    justify-content: space-between;
    padding: 0.7rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.07);
    font-size: 0.95rem;
    color: var(--tan);
  }
  .hours-list li:last-child { border-bottom: none; }
  .hours-list .day { color: var(--cream); font-weight: 500; }
  .hours-list .open { color: var(--mustard); }
  .hours-list .closed { color: #666; }

  .contact-item {
    display: flex;
    align-items: center;
    gap: 1rem;
    padding: 1rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.07);
    color: var(--tan);
    font-size: 0.95rem;
    text-decoration: none;
    transition: color 0.2s;
  }
  .contact-item:hover { color: var(--mustard); }
  .contact-item:last-child { border-bottom: none; }
  .contact-item .icon { font-size: 1.3rem; width: 24px; }

  /* FOOTER */
  footer {
    background: #0d0901;
    padding: 2rem 6rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid rgba(255,255,255,0.06);
    flex-wrap: wrap;
    gap: 1rem;
  }
  .footer-logo {
    font-family: 'Playfair Display', serif;
    color: var(--tan);
    font-size: 1.1rem;
  }
  .footer-copy {
    font-size: 0.75rem;
    color: #5a4e38;
    letter-spacing: 0.08em;
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .hero-eyebrow { animation: fadeUp 0.6s ease both; }
  h1 { animation: fadeUp 0.6s 0.15s ease both; }
  .hero-desc { animation: fadeUp 0.6s 0.3s ease both; }
  .hero-cta { animation: fadeUp 0.6s 0.45s ease both; }
  .hero-right { animation: fadeUp 0.8s 0.2s ease both; }

  @media (max-width: 900px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .hero { grid-template-columns: 1fr; }
    .hero-right { display: none; }
    .hero-left { padding: 6rem 2rem 4rem; }
    section { padding: 4rem 2rem; }
    .story { grid-template-columns: 1fr; gap: 2rem; }
    .info-section { grid-template-columns: 1fr; }
    .info-col { padding: 3rem 2rem; }
    .info-col:first-child { border-right: none; border-bottom: 1px solid rgba(255,255,255,0.08); }
    .info-strip { gap: 1.5rem; padding: 1rem 1.5rem; }
    footer { padding: 1.5rem 2rem; }
  }
</style>
</head>
<body>

<nav>
  <div class="nav-logo">The Sandwich Shoppe</div>
  <div class="nav-links">
    <a href="#menu">Menu</a>
    <a href="#story">Our Story</a>
    <a href="#visit">Visit Us</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-texture"></div>
  <div class="hero-left">
    <div class="hero-eyebrow">Downtown Gallatin, Tennessee</div>
    <h1>Hand-Crafted<br><em>Sandwiches</em><br>Done Right.</h1>
    <p class="hero-desc">
      Fresh, made-to-order creations served with care. Every sandwich packed with 6 inches of quality meat and bold, craveable flavor — right in the heart of historic downtown Gallatin.
    </p>
    <div class="hero-cta">
      <a href="#menu" class="btn-primary">See the Menu</a>
      <a href="#visit" class="btn-outline">Find Us</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-visual">
      <div class="hero-circle">🥪</div>
      <div class="hero-badge">
        <strong>All Sandwiches</strong>
        Include a side<br>& drink
      </div>
    </div>
  </div>
</section>

<!-- INFO STRIP -->
<div class="info-strip">
  <div class="info-item"><span class="icon">🕙</span> Mon–Sat: 10 AM – 3 PM &nbsp;|&nbsp; Sun: Closed</div>
  <div class="info-item"><span class="icon">📍</span> 134 E Main St, Gallatin, TN</div>
  <div class="info-item"><span class="icon">📞</span> (615) 390-4729</div>
  <div class="info-item"><span class="icon">🏡</span> Family Owned &amp; Operated</div>
</div>

<!-- STORY -->
<section class="story" id="story">
  <div class="story-text">
    <p class="section-label">Our Story</p>
    <h2 class="section-title">A Hidden Lunch Gem in Downtown Gallatin</h2>
    <div class="divider"></div>
    <p>The Sandwich Shoppe is a family-owned lunch spot tucked across from the courthouse on East Main Street. Founded by Tracy Sayles with her daughter Alex and longtime friend Ximena Hernandez, the shop opened in late 2024 and has been winning over the community ever since.</p>
    <p>Every sandwich is hand-crafted with six inches of quality meat and made fresh to order. From our signature wraps to hearty classics, every bite is made with love and local pride.</p>
  </div>
  <div class="story-card">
    <blockquote>"A hidden lunch gem in the heart of Gallatin — fresh, generous, and made with care."</blockquote>
    <cite>— Local Customer Review</cite>
  </div>
</section>

<!-- MENU -->
<section class="menu" id="menu">
  <div class="menu-header">
    <p class="section-label">What We Serve</p>
    <h2 class="section-title">Our Menu</h2>
    <div class="divider"></div>
    <span class="menu-note">★ All sandwiches include a side & drink ★</span>
  </div>

  <div class="menu-grid">

    <!-- Deli Sandwiches -->
    <div class="menu-category">
      <div class="category-header">
        <span class="category-icon">🥪</span>
        <span class="category-name">Deli Sandwiches</span>
      </div>
      <div class="category-items">
        <div class="menu-item">
          <div>
            <div class="item-name">Turkey Bacon Avocado <span class="item-popular">Fan Fave</span></div>
            <div class="item-desc">Sliced turkey, crispy bacon, fresh avocado</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Reuben</div>
            <div class="item-desc">Corned beef, sauerkraut, Swiss, Thousand Island</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Club</div>
            <div class="item-desc">Turkey, ham, bacon, lettuce, tomato, mayo</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Italian</div>
            <div class="item-desc">Ham, salami, pepperoni, provolone, peppers</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Pastrami</div>
            <div class="item-desc">Thin-sliced pastrami with mustard & Swiss</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">BLT <span class="item-popular">Popular</span></div>
            <div class="item-desc">Thick-cut smoky bacon, fresh lettuce & tomato</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Veggie</div>
            <div class="item-desc">Fresh garden vegetables, hummus, choice of cheese</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Wraps -->
    <div class="menu-category">
      <div class="category-header">
        <span class="category-icon">🌯</span>
        <span class="category-name">Wraps</span>
      </div>
      <div class="category-items">
        <div class="menu-item">
          <div>
            <div class="item-name">French Dip Wrap <span class="item-popular">New</span></div>
            <div class="item-desc">Tender roast beef, Swiss, au jus dipping sauce</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Chicken Pesto Wrap</div>
            <div class="item-desc">Grilled chicken, fresh basil pesto, mozzarella</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Turkey Club Wrap</div>
            <div class="item-desc">Turkey, bacon, avocado, lettuce, tomato</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Caesar Chicken Wrap</div>
            <div class="item-desc">Grilled chicken, romaine, parmesan, Caesar dressing</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Egg Sandwiches -->
    <div class="menu-category">
      <div class="category-header">
        <span class="category-icon">🍳</span>
        <span class="category-name">Egg Sandwiches</span>
      </div>
      <div class="category-items">
        <div class="menu-item">
          <div>
            <div class="item-name">Classic Egg & Cheese</div>
            <div class="item-desc">Scrambled eggs, American cheese, toasted bread</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Bacon Egg & Cheese</div>
            <div class="item-desc">Crispy bacon, egg, melted cheese</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Veggie Egg Sandwich</div>
            <div class="item-desc">Egg, spinach, tomato, Swiss cheese</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Ham Egg & Cheese</div>
            <div class="item-desc">Sliced ham, egg, your choice of cheese</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Bagels -->
    <div class="menu-category">
      <div class="category-header">
        <span class="category-icon">🥯</span>
        <span class="category-name">Bagels</span>
      </div>
      <div class="category-items">
        <div class="menu-item">
          <div>
            <div class="item-name">Classic Bagel & Cream Cheese</div>
            <div class="item-desc">Toasted bagel with whipped cream cheese</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Lox Bagel</div>
            <div class="item-desc">Smoked salmon, cream cheese, capers, red onion</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Bagel Egg Sandwich</div>
            <div class="item-desc">Toasted bagel with egg and your choice of toppings</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Salads -->
    <div class="menu-category">
      <div class="category-header">
        <span class="category-icon">🥗</span>
        <span class="category-name">Salads</span>
      </div>
      <div class="category-items">
        <div class="menu-item">
          <div>
            <div class="item-name">Garden Salad</div>
            <div class="item-desc">Fresh greens, cucumber, tomato, carrots, croutons</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Grilled Chicken Salad</div>
            <div class="item-desc">Seasoned grilled chicken over crisp greens</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Caesar Salad</div>
            <div class="item-desc">Romaine, parmesan, croutons, Caesar dressing</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Chef Salad</div>
            <div class="item-desc">Ham, turkey, egg, cheese over garden greens</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Sides & Soups -->
    <div class="menu-category">
      <div class="category-header">
        <span class="category-icon">🍵</span>
        <span class="category-name">Sides & Soups</span>
      </div>
      <div class="category-items">
        <div class="menu-item">
          <div>
            <div class="item-name">Soup of the Day <span class="item-popular">Homemade</span></div>
            <div class="item-desc">Ask your server — made fresh daily in-house</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Potato Salad</div>
            <div class="item-desc">House-made classic potato salad</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Pasta Salad</div>
            <div class="item-desc">House-made pasta salad with fresh veggies</div>
          </div>
        </div>
        <div class="menu-item">
          <div>
            <div class="item-name">Chips</div>
            <div class="item-desc">Classic snack-size bag of chips</div>
          </div>
        </div>
      </div>
    </div>

  </div>

  <div class="sides-note">
    <span class="icon">🎉</span>
    <div>
      <h3>Everything Included</h3>
      <p>All of our deli and classic sandwiches come with your choice of side and a drink. We believe a great lunch should be complete — no hidden extras.</p>
    </div>
  </div>
</section>

<!-- HOURS & CONTACT -->
<section class="info-section" id="visit">
  <div class="info-col">
    <p class="section-label">When to Visit</p>
    <h2 class="section-title">Hours</h2>
    <div class="divider"></div>
    <ul class="hours-list">
      <li><span class="day">Monday</span><span class="open">10:00 AM – 3:00 PM</span></li>
      <li><span class="day">Tuesday</span><span class="open">10:00 AM – 3:00 PM</span></li>
      <li><span class="day">Wednesday</span><span class="open">10:00 AM – 3:00 PM</span></li>
      <li><span class="day">Thursday</span><span class="open">10:00 AM – 3:00 PM</span></li>
      <li><span class="day">Friday</span><span class="open">10:00 AM – 3:00 PM</span></li>
      <li><span class="day">Saturday</span><span class="open">10:00 AM – 3:00 PM</span></li>
      <li><span class="day">Sunday</span><span class="closed">Closed</span></li>
    </ul>
  </div>
  <div class="info-col">
    <p class="section-label">Come Find Us</p>
    <h2 class="section-title">Location</h2>
    <div class="divider"></div>
    <a href="https://maps.apple.com/?address=134%20E%20Main%20St,%20Gallatin,%20TN%2037066" class="contact-item">
      <span class="icon">📍</span>
      134 E Main St, Gallatin, TN 37066<br>Across from the Courthouse
    </a>
    <a href="tel:6153904729" class="contact-item">
      <span class="icon">📞</span>(615) 390-4729
    </a>
    <a href="https://www.instagram.com/sandwichshoppe615/" class="contact-item" target="_blank">
      <span class="icon">📸</span>@sandwichshoppe615 on Instagram
    </a>
    <a href="https://www.facebook.com/thesandwichshoppemp" class="contact-item" target="_blank">
      <span class="icon">👍</span>The Sandwich Shoppe on Facebook
    </a>
  </div>
</section>

<footer>
  <div class="footer-logo">The Sandwich Shoppe</div>
  <div class="footer-copy">134 E Main St · Gallatin, TN 37066 · (615) 390-4729</div>
  <div class="footer-copy">© 2025 The Sandwich Shoppe. All rights reserved.</div>
</footer>

</body>
</html>
