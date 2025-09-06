# Geethika
my project 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Simple Shopping App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0; padding: 0;
      background: #f9f9f9;
    }
    header {
      background: #333;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    .container {
      display: flex;
      padding: 1rem;
    }
    .products, .cart {
      flex: 1;
      padding: 1rem;
    }
    .product {
      background: white;
      padding: 1rem;
      margin-bottom: 1rem;
      border: 1px solid #ddd;
    }
    .product h3 {
      margin-top: 0;
    }
    button {
      background: #28a745;
      color: white;
      border: none;
      padding: 0.5rem 1rem;
      cursor: pointer;
    }
    button:hover {
      background: #218838;
    }
    .cart {
      background: #fff8dc;
    }
    .cart h2 {
      border-bottom: 1px solid #ccc;
    }
    .cart-item {
      margin-bottom: 0.5rem;
    }
  </style>
</head>
<body>

<header>
  <h1>My Shopping App</h1>
</header>

<div class="container">
  <div class="products">
    <h2>Products</h2>
    <div class="product">
      <h3>Product 1</h3>
      <p>Price: $10</p>
      <button onclick="addToCart('Product 1', 10)">Add to Cart</button>
    </div>
    <div class="product">
      <h3>Product 2</h3>
      <p>Price: $15</p>
      <button onclick="addToCart('Product 2', 15)">Add to Cart</button>
    </div>
    <div class="product">
      <h3>Product 3</h3>
      <p>Price: $20</p>
      <button onclick="addToCart('Product 3', 20)">Add to Cart</button>
    </div>
  </div>

  <div class="cart">
    <h2>Shopping Cart</h2>
    <div id="cart-items"></div>
    <p><strong>Total: $<span id="cart-total">0</span></strong></p>
  </div>
</div>

<script>
  const cart = [];
  const cartItemsContainer = document.getElementById("cart-items");
  const cartTotalDisplay = document.getElementById("cart-total");

  function addToCart(productName, price) {
    cart.push({ name: productName, price: price });
    renderCart();
  }

  function renderCart() {
    cartItemsContainer.innerHTML = "";
    let total = 0;
    cart.forEach(item => {
      const div = document.createElement("div");
      div.className = "cart-item";
      div.textContent = `${item.name} - $${item.price}`;
      cartItemsContainer.appendChild(div);
      total += item.price;
    });
    cartTotalDisplay.textContent = total.toFixed(2);
  }
</script>

</body>
</html>
