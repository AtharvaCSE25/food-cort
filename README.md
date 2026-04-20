# food-cort
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chaska Foodcourt – Desi Swad, Dil Se</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Poppins:wght@300;400;600;700&family=Pacifico&display=swap" rel="stylesheet">
<style>
  :root {
    --saffron: #FF6B00;
    --turmeric: #FFC107;
    --chilli: #D62828;
    --mint: #2D6A4F;
    --cream: #FFF8F0;
    --dark: #1A0A00;
    --card-bg: #FFFAF4;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Poppins', sans-serif;
    background: var(--cream);
    color: var(--dark);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; width: 100%; z-index: 100;
    background: rgba(26,10,0,0.92);
    backdrop-filter: blur(10px);
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 5%;
    height: 64px;
  }
  .logo {
    font-family: 'Pacifico', cursive;
    font-size: 1.6rem;
    color: var(--saffron);
    letter-spacing: 1px;
  }
  .logo span { color: var(--turmeric); }
  nav ul { list-style: none; display: flex; gap: 2rem; }
  nav ul li a {
    color: #fff;
    text-decoration: none;
    font-weight: 600;
    font-size: 0.85rem;
    letter-spacing: 1px;
    text-transform: uppercase;
    transition: color .2s;
  }
  nav ul li a:hover { color: var(--saffron); }

  /* ── HERO BANNER ── */
  .hero {
    min-height: 100vh;
    position: relative;
    display: flex; align-items: center; justify-content: center;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse at 20% 50%, rgba(255,107,0,0.35) 0%, transparent 60%),
      radial-gradient(ellipse at 80% 30%, rgba(214,40,40,0.25) 0%, transparent 50%),
      radial-gradient(ellipse at 60% 80%, rgba(255,193,7,0.2) 0%, transparent 50%),
      url('https://images.unsplash.com/photo-1601050690597-df0568f70950?w=1600&q=80') center/cover no-repeat;
    filter: brightness(0.45);
  }
  .hero-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(to bottom, rgba(26,10,0,0.3) 0%, rgba(26,10,0,0.7) 100%);
  }
  .hero-content {
    position: relative; z-index: 2;
    text-align: center;
    animation: fadeUp 1s ease both;
  }
  .hero-tag {
    display: inline-block;
    background: var(--saffron);
    color: #fff;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 6px 20px;
    border-radius: 50px;
    margin-bottom: 1.2rem;
    animation: fadeUp 0.8s ease 0.2s both;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 8vw, 7rem);
    font-weight: 900;
    color: #fff;
    line-height: 1.05;
    animation: fadeUp 0.8s ease 0.4s both;
  }
  .hero h1 span { color: var(--turmeric); }
  .hero-sub {
    font-size: 1.15rem;
    color: rgba(255,255,255,0.8);
    margin-top: 1rem;
    font-weight: 300;
    letter-spacing: 1px;
    animation: fadeUp 0.8s ease 0.6s both;
  }
  .hero-btns {
    display: flex; gap: 1rem; justify-content: center;
    margin-top: 2.5rem;
    animation: fadeUp 0.8s ease 0.8s both;
  }
  .btn-primary {
    background: var(--saffron);
    color: #fff;
    padding: 14px 36px;
    border-radius: 50px;
    font-weight: 700;
    font-size: 0.95rem;
    text-decoration: none;
    letter-spacing: 1px;
    transition: transform .2s, box-shadow .2s;
    box-shadow: 0 6px 24px rgba(255,107,0,0.45);
  }
  .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 10px 30px rgba(255,107,0,0.55); }
  .btn-outline {
    border: 2px solid #fff;
    color: #fff;
    padding: 14px 36px;
    border-radius: 50px;
    font-weight: 700;
    font-size: 0.95rem;
    text-decoration: none;
    letter-spacing: 1px;
    transition: background .2s, color .2s;
  }
  .btn-outline:hover { background: #fff; color: var(--dark); }

  /* Scroll indicator */
  .scroll-hint {
    position: absolute; bottom: 2.5rem; left: 50%; transform: translateX(-50%);
    color: rgba(255,255,255,0.6);
    font-size: 0.75rem; letter-spacing: 2px; text-transform: uppercase;
    display: flex; flex-direction: column; align-items: center; gap: 8px;
    animation: bounce 2s infinite;
  }
  .scroll-hint::after {
    content: '↓'; font-size: 1.2rem; color: var(--saffron);
  }

  /* ── MARQUEE STRIP ── */
  .marquee-strip {
    background: var(--saffron);
    color: #fff;
    padding: 12px 0;
    overflow: hidden;
    white-space: nowrap;
  }
  .marquee-track {
    display: inline-block;
    animation: marquee 20s linear infinite;
    font-weight: 700;
    font-size: 0.85rem;
    letter-spacing: 2px;
    text-transform: uppercase;
  }
  .marquee-track span { margin: 0 2rem; }
  .marquee-track .dot { color: var(--turmeric); }

  /* ── SECTION TITLES ── */
  .section-title {
    text-align: center;
    margin-bottom: 3.5rem;
  }
  .section-title .label {
    display: inline-block;
    color: var(--saffron);
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 0.6rem;
  }
  .section-title h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4vw, 3.2rem);
    font-weight: 900;
    color: var(--dark);
    line-height: 1.15;
  }
  .section-title h2 em { color: var(--saffron); font-style: normal; }
  .section-title p {
    color: #777;
    margin-top: 0.8rem;
    font-size: 0.95rem;
    max-width: 480px;
    margin-left: auto;
    margin-right: auto;
  }

  /* ── MENU SECTION ── */
  #menu {
    padding: 100px 5%;
    background: var(--cream);
  }
  .filter-bar {
    display: flex; gap: 0.8rem; justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 3rem;
  }
  .filter-btn {
    padding: 9px 22px;
    border-radius: 50px;
    border: 2px solid #ddd;
    background: transparent;
    font-family: 'Poppins', sans-serif;
    font-size: 0.82rem;
    font-weight: 600;
    cursor: pointer;
    transition: all .2s;
    letter-spacing: 0.5px;
  }
  .filter-btn:hover, .filter-btn.active {
    background: var(--saffron);
    border-color: var(--saffron);
    color: #fff;
  }

  .menu-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 2rem;
    max-width: 1300px;
    margin: 0 auto;
  }
  .menu-card {
    background: var(--card-bg);
    border-radius: 20px;
    overflow: hidden;
    box-shadow: 0 4px 20px rgba(0,0,0,0.06);
    transition: transform .3s, box-shadow .3s;
    position: relative;
  }
  .menu-card:hover { transform: translateY(-8px); box-shadow: 0 16px 40px rgba(255,107,0,0.15); }
  .card-img-wrap {
    position: relative;
    height: 200px;
    overflow: hidden;
  }
  .card-img-wrap img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform .4s;
  }
  .menu-card:hover .card-img-wrap img { transform: scale(1.07); }
  .card-badge {
    position: absolute; top: 12px; left: 12px;
    background: var(--saffron);
    color: #fff;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    padding: 4px 12px;
    border-radius: 50px;
  }
  .card-veg {
    position: absolute; top: 12px; right: 12px;
    width: 24px; height: 24px;
    border: 2px solid #2D6A4F;
    border-radius: 4px;
    background: #fff;
    display: flex; align-items: center; justify-content: center;
  }
  .card-veg::after {
    content: ''; width: 10px; height: 10px;
    border-radius: 50%;
    background: #2D6A4F;
  }
  .card-body { padding: 1.3rem; }
  .card-body h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.25rem;
    font-weight: 700;
    margin-bottom: 0.4rem;
  }
  .card-body p {
    font-size: 0.82rem;
    color: #888;
    line-height: 1.5;
    margin-bottom: 1.1rem;
  }
  .card-footer {
    display: flex; align-items: center; justify-content: space-between;
  }
  .price {
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--saffron);
  }
  .price span { font-size: 0.8rem; font-weight: 400; color: #aaa; }
  .add-btn {
    background: var(--dark);
    color: #fff;
    border: none;
    padding: 9px 20px;
    border-radius: 50px;
    font-family: 'Poppins', sans-serif;
    font-size: 0.82rem;
    font-weight: 600;
    cursor: pointer;
    transition: background .2s, transform .15s;
    display: flex; align-items: center; gap: 6px;
  }
  .add-btn:hover { background: var(--saffron); transform: scale(1.05); }
  .add-btn.added { background: var(--mint); }

  /* ── ABOUT STRIP ── */
  .about-strip {
    background: var(--dark);
    color: #fff;
    padding: 80px 5%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
  }
  .about-strip h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3.5vw, 3rem);
    font-weight: 900;
    line-height: 1.2;
    margin-bottom: 1.2rem;
  }
  .about-strip h2 em { color: var(--saffron); font-style: normal; }
  .about-strip p { color: rgba(255,255,255,0.7); line-height: 1.8; font-size: 0.95rem; margin-bottom: 1.5rem; }
  .stats { display: flex; gap: 2.5rem; margin-top: 2rem; }
  .stat h3 {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    color: var(--turmeric);
    font-weight: 900;
  }
  .stat p { font-size: 0.8rem; color: rgba(255,255,255,0.6); letter-spacing: 1px; text-transform: uppercase; }
  .about-img {
    border-radius: 24px;
    overflow: hidden;
    height: 420px;
    position: relative;
  }
  .about-img img { width: 100%; height: 100%; object-fit: cover; }
  .about-img::before {
    content: '';
    position: absolute; inset: 0;
    border: 3px solid var(--saffron);
    border-radius: 24px;
    transform: translate(12px, 12px);
    z-index: -1;
  }

  /* ── GALLERY ── */
  #gallery {
    padding: 100px 5%;
    background: #fff;
  }
  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 220px);
    gap: 1rem;
    max-width: 1100px;
    margin: 0 auto;
    border-radius: 20px;
    overflow: hidden;
  }
  .gallery-grid .g-item { overflow: hidden; position: relative; }
  .gallery-grid .g-item:first-child { grid-row: 1 / 3; }
  .gallery-grid img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform .4s;
    display: block;
  }
  .gallery-grid .g-item:hover img { transform: scale(1.08); }
  .g-item::after {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(to top, rgba(255,107,0,0.4), transparent);
    opacity: 0; transition: opacity .3s;
  }
  .g-item:hover::after { opacity: 1; }

  /* ── ORDER SECTION ── */
  #order {
    padding: 100px 5%;
    background: var(--cream);
  }
  .order-wrap {
    max-width: 700px;
    margin: 0 auto;
    background: #fff;
    border-radius: 24px;
    padding: 3rem;
    box-shadow: 0 10px 50px rgba(0,0,0,0.07);
  }
  .order-wrap h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.8rem;
    margin-bottom: 1.8rem;
    text-align: center;
  }
  .order-wrap h3 span { color: var(--saffron); }
  .cart-items { list-style: none; }
  .cart-items li {
    display: flex; align-items: center; justify-content: space-between;
    padding: 14px 0;
    border-bottom: 1px dashed #eee;
    font-size: 0.9rem;
  }
  .cart-items li:last-child { border-bottom: none; }
  .cart-items .ci-name { font-weight: 600; }
  .cart-items .ci-qty {
    display: flex; align-items: center; gap: 12px;
  }
  .qty-btn {
    width: 28px; height: 28px;
    border-radius: 50%;
    border: 2px solid var(--saffron);
    background: transparent;
    color: var(--saffron);
    font-size: 1rem; font-weight: 700;
    cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    transition: all .2s;
  }
  .qty-btn:hover { background: var(--saffron); color: #fff; }
  .ci-total { font-weight: 700; color: var(--saffron); min-width: 55px; text-align: right; }
  .cart-total {
    background: var(--cream);
    border-radius: 12px;
    padding: 1.2rem 1.5rem;
    margin-top: 1.5rem;
    display: flex; justify-content: space-between; align-items: center;
    font-size: 1.1rem;
    font-weight: 700;
  }
  .cart-total .amount { color: var(--saffron); font-size: 1.4rem; }
  .place-order-btn {
    width: 100%;
    margin-top: 1.5rem;
    background: var(--saffron);
    color: #fff;
    border: none;
    padding: 16px;
    border-radius: 12px;
    font-family: 'Poppins', sans-serif;
    font-size: 1rem; font-weight: 700;
    cursor: pointer;
    letter-spacing: 1px;
    transition: background .2s, transform .2s;
  }
  .place-order-btn:hover { background: #e55a00; transform: translateY(-2px); }
  .empty-cart {
    text-align: center;
    color: #bbb;
    padding: 2rem;
    font-size: 0.9rem;
  }

  /* ── FOOTER ── */
  footer {
    background: var(--dark);
    color: rgba(255,255,255,0.6);
    text-align: center;
    padding: 2.5rem 5%;
  }
  footer .logo { display: block; margin-bottom: 0.5rem; }
  footer p { font-size: 0.82rem; }
  footer span { color: var(--saffron); }

  /* ── FLOATING CART ── */
  .float-cart {
    position: fixed; bottom: 2rem; right: 2rem;
    background: var(--saffron);
    color: #fff;
    width: 60px; height: 60px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.5rem;
    box-shadow: 0 6px 24px rgba(255,107,0,0.5);
    cursor: pointer;
    z-index: 999;
    transition: transform .2s;
    text-decoration: none;
  }
  .float-cart:hover { transform: scale(1.1); }
  .float-cart-badge {
    position: absolute; top: -4px; right: -4px;
    background: var(--chilli);
    color: #fff;
    font-size: 0.65rem;
    font-weight: 700;
    width: 20px; height: 20px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    border: 2px solid #fff;
  }

  /* ── TOAST ── */
  .toast {
    position: fixed; bottom: 6rem; right: 2rem;
    background: var(--dark);
    color: #fff;
    padding: 12px 22px;
    border-radius: 50px;
    font-size: 0.85rem;
    font-weight: 600;
    z-index: 1000;
    transform: translateY(20px);
    opacity: 0;
    transition: all .3s;
    pointer-events: none;
  }
  .toast.show { transform: translateY(0); opacity: 1; }
  .toast span { color: var(--turmeric); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }
  @keyframes bounce {
    0%, 100% { transform: translateX(-50%) translateY(0); }
    50% { transform: translateX(-50%) translateY(8px); }
  }

  /* Responsive */
  @media (max-width: 768px) {
    nav ul { display: none; }
    .about-strip { grid-template-columns: 1fr; }
    .about-img { height: 280px; }
    .gallery-grid { grid-template-columns: 1fr 1fr; grid-template-rows: auto; }
    .gallery-grid .g-item:first-child { grid-row: auto; }
    .stats { gap: 1.5rem; }
    .order-wrap { padding: 1.5rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">Chaska <span>🍛</span></div>
  <ul>
    <li><a href="#menu">Menu</a></li>
    <li><a href="#gallery">Gallery</a></li>
    <li><a href="#order">Order</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-overlay"></div>
  <div class="hero-content">
    <div class="hero-tag">✦ Pure Desi Flavours ✦</div>
    <h1>Taste the <span>Desi</span><br>Difference</h1>
    <p class="hero-sub">Hot Samosa · Fluffy Poha · Crispy Vada Pav · Masala Chai & more</p>
    <div class="hero-btns">
      <a href="#menu" class="btn-primary">🍽 Order Now</a>
      <a href="#gallery" class="btn-outline">View Gallery</a>
    </div>
  </div>
  <div class="scroll-hint">Scroll</div>
</section>

<!-- MARQUEE -->
<div class="marquee-strip">
  <div class="marquee-track">
    <span>🥟 Samosa</span><span class="dot">✦</span>
    <span>🍚 Poha</span><span class="dot">✦</span>
    <span>🍔 Vada Pav</span><span class="dot">✦</span>
    <span>☕ Masala Chai</span><span class="dot">✦</span>
    <span>🥜 Chivda</span><span class="dot">✦</span>
    <span>🧆 Misal Pav</span><span class="dot">✦</span>
    <span>🌶 Bhel Puri</span><span class="dot">✦</span>
    <span>🍩 Jalebi</span><span class="dot">✦</span>
    <!-- repeat for seamless loop -->
    <span>🥟 Samosa</span><span class="dot">✦</span>
    <span>🍚 Poha</span><span class="dot">✦</span>
    <span>🍔 Vada Pav</span><span class="dot">✦</span>
    <span>☕ Masala Chai</span><span class="dot">✦</span>
    <span>🥜 Chivda</span><span class="dot">✦</span>
    <span>🧆 Misal Pav</span><span class="dot">✦</span>
    <span>🌶 Bhel Puri</span><span class="dot">✦</span>
    <span>🍩 Jalebi</span><span class="dot">✦</span>
  </div>
</div>

<!-- MENU -->
<section id="menu">
  <div class="section-title">
    <div class="label">✦ Our Menu</div>
    <h2>What's <em>Cooking</em> Today</h2>
    <p>Fresh, hot, and full of desi love — every plate made from scratch daily.</p>
  </div>

  <div class="filter-bar">
    <button class="filter-btn active" data-cat="all">All Items</button>
    <button class="filter-btn" data-cat="snacks">Snacks</button>
    <button class="filter-btn" data-cat="breakfast">Breakfast</button>
    <button class="filter-btn" data-cat="drinks">Drinks</button>
    <button class="filter-btn" data-cat="sweets">Sweets</button>
  </div>

  <div class="menu-grid" id="menuGrid"></div>
</section>

<!-- ABOUT -->
<div class="about-strip">
  <div>
    <h2>Made with <em>Love,</em><br>Served with Pride</h2>
    <p>At Chaska Foodcourt, every dish tells the story of our grandmothers' kitchens — the smoky tadka, the perfectly spiced masala, the warmth of freshly brewed chai.</p>
    <p>We use local produce, traditional recipes, and zero shortcuts. Because you deserve food that actually tastes like home.</p>
    <div class="stats">
      <div class="stat"><h3>15+</h3><p>Menu Items</p></div>
      <div class="stat"><h3>500+</h3><p>Happy Guests/Day</p></div>
      <div class="stat"><h3>5★</h3><p>Avg. Rating</p></div>
    </div>
  </div>
  <div class="about-img">
    <img src="https://images.unsplash.com/photo-1585937421612-70a008356fbe?w=800&q=80" alt="Desi Food">
  </div>
</div>

<!-- GALLERY -->
<section id="gallery">
  <div class="section-title">
    <div class="label">✦ Gallery</div>
    <h2>A Feast for <em>the Eyes</em></h2>
    <p>Because great food deserves to be seen before it's savoured.</p>
  </div>
  <div class="gallery-grid">
    <div class="g-item"><img src="https://images.unsplash.com/photo-1601050690597-df0568f70950?w=800&q=80" alt="Food spread"></div>
    <div class="g-item"><img src="https://images.unsplash.com/photo-1567188040759-fb8a883dc6d8?w=600&q=80" alt="Chai"></div>
    <div class="g-item"><img src="https://images.unsplash.com/photo-1606755456206-b25206cde27e?w=600&q=80" alt="Indian snack"></div>
    <div class="g-item"><img src="https://images.unsplash.com/photo-1571091718767-18b5b1457add?w=600&q=80" alt="Street food"></div>
    <div class="g-item"><img src="https://images.unsplash.com/photo-1630383249896-424e482df921?w=600&q=80" alt="Sweets"></div>
  </div>
</section>

<!-- ORDER / CART -->
<section id="order">
  <div class="section-title">
    <div class="label">✦ Your Order</div>
    <h2>Ready to <em>Place</em> Your Order?</h2>
    <p>Add items from the menu above and checkout below.</p>
  </div>
  <div class="order-wrap">
    <h3>Your <span>Cart 🛒</span></h3>
    <ul class="cart-items" id="cartList">
      <li class="empty-cart">Your cart is empty. Add items from the menu above! 🍽</li>
    </ul>
    <div class="cart-total" id="cartTotal" style="display:none">
      <span>Total Amount</span>
      <span class="amount" id="totalAmt">₹0</span>
    </div>
    <button class="place-order-btn" id="placeOrderBtn" style="display:none" onclick="placeOrder()">✅ Place Order</button>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="logo">Chaska 🍛</div>
  <p>Made with <span>♥</span> in India · © 2026 Chaska Foodcourt</p>
</footer>

<!-- Floating cart button -->
<a href="#order" class="float-cart" id="floatCart" style="display:none">
  🛒
  <span class="float-cart-badge" id="cartBadge">0</span>
</a>

<!-- Toast -->
<div class="toast" id="toast">Added <span id="toastItem"></span> to cart!</div>

<script>
const menuData = [
  { id: 1, name: "Samosa", cat: "snacks", price: 15, desc: "Crispy golden pastry stuffed with spiced aloo & peas. Served with green chutney.", img: "https://images.unsplash.com/photo-1601050690597-df0568f70950?w=500&q=80", badge: "Bestseller" },
  { id: 2, name: "Poha", cat: "breakfast", price: 40, desc: "Fluffy flattened rice tempered with mustard, curry leaves, peanuts & onion.", img: "https://images.unsplash.com/photo-1567188040759-fb8a883dc6d8?w=500&q=80", badge: "Fresh" },
  { id: 3, name: "Vada Pav", cat: "snacks", price: 25, desc: "Mumbai's favourite — spicy potato vada in a soft pav with dry garlic chutney.", img: "https://images.unsplash.com/photo-1630383249896-424e482df921?w=500&q=80", badge: "🔥 Spicy" },
  { id: 4, name: "Masala Chai", cat: "drinks", price: 20, desc: "Strong, aromatic tea brewed with ginger, cardamom, and secret masala blend.", img: "https://images.unsplash.com/photo-1563805042-7684c019e1cb?w=500&q=80", badge: "Hot" },
  { id: 5, name: "Misal Pav", cat: "breakfast", price: 60, desc: "Spicy sprouted moth curry topped with farsan, onion & lemon. A Nashik legend.", img: "https://images.unsplash.com/photo-1585937421612-70a008356fbe?w=500&q=80", badge: "Nashik Special" },
  { id: 6, name: "Bhel Puri", cat: "snacks", price: 35, desc: "Puffed rice mixed with tamarind chutney, onions, tomatoes & crunchy sev.", img: "https://images.unsplash.com/photo-1606755456206-b25206cde27e?w=500&q=80", badge: "Tangy" },
  { id: 7, name: "Cold Coffee", cat: "drinks", price: 55, desc: "Thick, frothy cold coffee blended with milk & ice cream. Pure bliss.", img: "https://images.unsplash.com/photo-1461023058943-07fcbe16d735?w=500&q=80", badge: "Chilled" },
  { id: 8, name: "Jalebi", cat: "sweets", price: 30, desc: "Crispy spirals soaked in saffron sugar syrup. Best served hot & fresh.", img: "https://images.unsplash.com/photo-1571091718767-18b5b1457add?w=500&q=80", badge: "Sweet" },
];

let cart = {};

function renderMenu(cat) {
  const grid = document.getElementById('menuGrid');
  const items = cat === 'all' ? menuData : menuData.filter(m => m.cat === cat);
  grid.innerHTML = items.map(item => `
    <div class="menu-card" data-cat="${item.cat}">
      <div class="card-img-wrap">
        <img src="${item.img}" alt="${item.name}" loading="lazy">
        <div class="card-badge">${item.badge}</div>
        <div class="card-veg"></div>
      </div>
      <div class="card-body">
        <h3>${item.name}</h3>
        <p>${item.desc}</p>
        <div class="card-footer">
          <div class="price">₹${item.price} <span>/ plate</span></div>
          <button class="add-btn" id="btn-${item.id}" onclick="addToCart(${item.id})">
            + Add
          </button>
        </div>
      </div>
    </div>
  `).join('');
}

function addToCart(id) {
  const item = menuData.find(m => m.id === id);
  cart[id] = cart[id] ? { ...cart[id], qty: cart[id].qty + 1 } : { ...item, qty: 1 };
  updateCartUI();
  showToast(item.name);
  const btn = document.getElementById(`btn-${id}`);
  if (btn) { btn.textContent = `✔ Added (${cart[id].qty})`; btn.classList.add('added'); }
}

function updateQty(id, delta) {
  if (!cart[id]) return;
  cart[id].qty += delta;
  if (cart[id].qty <= 0) delete cart[id];
  updateCartUI();
  // update add buttons
  menuData.forEach(item => {
    const btn = document.getElementById(`btn-${item.id}`);
    if (!btn) return;
    if (cart[item.id]) {
      btn.textContent = `✔ Added (${cart[item.id].qty})`;
      btn.classList.add('added');
    } else {
      btn.textContent = `+ Add`;
      btn.classList.remove('added');
    }
  });
}

function updateCartUI() {
  const list = document.getElementById('cartList');
  const totalDiv = document.getElementById('cartTotal');
  const totalAmt = document.getElementById('totalAmt');
  const orderBtn = document.getElementById('placeOrderBtn');
  const floatCart = document.getElementById('floatCart');
  const badge = document.getElementById('cartBadge');

  const keys = Object.keys(cart);
  const totalQty = keys.reduce((s, k) => s + cart[k].qty, 0);
  const total = keys.reduce((s, k) => s + cart[k].price * cart[k].qty, 0);

  if (keys.length === 0) {
    list.innerHTML = '<li class="empty-cart">Your cart is empty. Add items from the menu above! 🍽</li>';
    totalDiv.style.display = 'none';
    orderBtn.style.display = 'none';
    floatCart.style.display = 'none';
  } else {
    list.innerHTML = keys.map(k => {
      const c = cart[k];
      return `
        <li>
          <span class="ci-name">${c.name}</span>
          <span class="ci-qty">
            <button class="qty-btn" onclick="updateQty(${c.id}, -1)">−</button>
            <span>${c.qty}</span>
            <button class="qty-btn" onclick="updateQty(${c.id}, 1)">+</button>
          </span>
          <span class="ci-total">₹${c.price * c.qty}</span>
        </li>`;
    }).join('');
    totalDiv.style.display = 'flex';
    orderBtn.style.display = 'block';
    totalAmt.textContent = `₹${total}`;
    floatCart.style.display = 'flex';
    badge.textContent = totalQty;
  }
}

function showToast(name) {
  const t = document.getElementById('toast');
  document.getElementById('toastItem').textContent = name;
  t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), 2500);
}

function placeOrder() {
  const total = Object.keys(cart).reduce((s, k) => s + cart[k].price * cart[k].qty, 0);
  const names = Object.values(cart).map(c => c.name).join(', ');
  cart = {};
  updateCartUI();
  menuData.forEach(item => {
    const btn = document.getElementById(`btn-${item.id}`);
    if (btn) { btn.textContent = '+ Add'; btn.classList.remove('added'); }
  });
  const t = document.getElementById('toast');
  document.getElementById('toastItem').textContent = `order placed! Total: ₹${total} 🎉`;
  t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), 3500);
}

// Filter buttons
document.querySelectorAll('.filter-btn').forEach(btn => {
  btn.addEventListener('click', () => {
    document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    renderMenu(btn.dataset.cat);
  });
});

renderMenu('all');
</script>
</body>
</html>
