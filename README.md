# orderme
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sany's Bakery</title>
  <style>
    * {
      margin: 0; padding: 0; box-sizing: border-box;
      scroll-behavior: smooth;
    }
    body {
      font-family: 'Segoe UI', sans-serif;
      color: #333;
      line-height: 1.6;
    }
    header {
      background: #f8b400;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    nav a {
      margin-left: 1rem;
      text-decoration: none;
      color: white;
      font-weight: bold;
    }
    .hero {
      background: url('https://images.unsplash.com/photo-1600891963935-c900c1b7b03e') no-repeat center/cover;
      height: 90vh;
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      text-align: center;
    }
    .hero h1 {
      font-size: 3rem;
      background: rgba(0, 0, 0, 0.5);
      padding: 1rem 2rem;
      border-radius: 10px;
    }
    section {
      padding: 4rem 2rem;
    }
    .about, .services, .contact {
      max-width: 800px;
      margin: auto;
    }
    .services ul {
      list-style: none;
      padding: 0;
    }
    .services li {
      background: #f0f0f0;
      margin-bottom: 1rem;
      padding: 1rem;
      border-radius: 8px;
    }
    .contact a {
      display: inline-block;
      margin-top: 1rem;
      padding: 0.75rem 1.5rem;
      background: #f8b400;
      color: white;
      text-decoration: none;
      border-radius: 5px;
    }
    footer {
      background: #333;
      color: white;
      text-align: center;
      padding: 1rem;
    }
    @media (max-width: 600px) {
      .hero h1 { font-size: 2rem; }
      nav a { margin: 0 0.5rem; }
    }
  </style>
  <script>
  function openOrderForm(itemName) {
    document.getElementById('orderItem').value = itemName;
    document.getElementById('orderTitle').innerText = `Order: ${itemName}`;
    document.getElementById('orderModal').style.display = 'flex';
  }

  function closeForm() {
    document.getElementById('orderModal').style.display = 'none';
  }
</script>

</head>
<body>

  <header>
    <h2>Sunny's Bakery</h2>
    <nav>
      <a href="#about">About</a>
      <a href="#services">Menu</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <div class="hero">
    <h1>Freshly Baked, Daily Joy</h1>
  </div>

  <section id="about" class="about">
    <h2>About Us</h2>
    <p>We are a small, family-run bakery serving fresh bread, cakes, and pastries every day. From our oven to your heart!</p>
  </section>

  <section id="services" class="services">
  <h2>Our Menu</h2>
  <ul>
    <li onclick="openOrderForm('Croissant')">🥐 Croissant</li>
    <li onclick="openOrderForm('Cheesecake')">🍰 Cheesecake</li>
    <li onclick="openOrderForm('Artisan Bread')">🍞 Artisan Bread</li>
    <li onclick="openOrderForm('Birthday Cake')">🎂 Custom Cake</li>
  </ul>
</section>

<!-- Hidden Order Form Modal -->
<div id="orderModal" style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.5); justify-content:center; align-items:center;">
  <div style="background:white; padding:2rem; border-radius:10px; max-width:400px; width:90%; position:relative;">
    <span style="position:absolute; top:10px; right:15px; cursor:pointer; font-weight:bold;" onclick="closeForm()">✖</span>
    <h3 id="orderTitle">Order</h3>
    <form action="https://formspree.io/f/mrbqjpzq" method="POST">
      <input type="hidden" name="Item" id="orderItem">
      <label>Name:</label><br>
      <input type="text" name="Name" required style="width:100%; margin-bottom:10px;"><br>
      <label>Email:</label><br>
      <input type="email" name="Email" required style="width:100%; margin-bottom:10px;"><br>
      <label>Quantity:</label><br>
      <input type="number" name="Quantity" min="1" value="1" style="width:100%; margin-bottom:10px;"><br>
      <button type="submit" style="background:#f8b400; color:white; border:none; padding:0.5rem 1rem; border-radius:5px;">Place Order</button>
    </form>
  </div>
</div>

  <section id="contact" class="contact">
    <h2>Get in Touch</h2>
    <p>Visit us at 123 Main Street, or email us with your order.</p>
    <a href="mailto:sanydirghangi84@gmail.com">Email Us</a>
  </section>

  <footer>
    <p>&copy; 2025 Sany's Bakery</p>
  </footer>

</body>
</html>
