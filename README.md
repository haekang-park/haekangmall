# haekangmall
박해강
<!DOCTYPE html>
<html>
<head>
    <title>해강몰</title>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
    <header>
        <h1>해강몰</h1>
        <nav>
            <a href="#products">상품 목록</a>
            <a href="#cart">장바구니</a>
        </nav>
    </header>

    <section id="products">
        <h2>상품 목록</h2>
        <div class="product">
            <h3>상품 1</h3>
            <p>가격: $10</p>
            <button onclick="addToCart('상품 1', 10)">장바구니에 추가</button>
        </div>
        <div class="product">
            <h3>상품 2</h3>
            <p>가격: $15</p>
            <button onclick="addToCart('상품 2', 15)">장바구니에 추가</button>
        </div>
    </section>

    <section id="cart">
        <h2>장바구니</h2>
        <ul id="cart-items">
            <!-- 장바구니 아이템이 여기에 추가됩니다. -->
        </ul>
        <p id="total-price">총 가격: $0</p>
    </section>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: #fff;
    padding: 10px;
    text-align: center;
}

nav a {
    color: #fff;
    margin: 0 15px;
    text-decoration: none;
}

section {
    padding: 20px;
}

.product {
    border: 1px solid #ddd;
    margin-bottom: 10px;
    padding: 10px;
}

button {
    background-color: #28a745;
    color: #fff;
    border: none;
    padding: 10px;
    cursor: pointer;
}

button:hover {
    background-color: #218838;
}
let cart = [];
const cartItems = document.getElementById('cart-items');
const totalPrice = document.getElementById('total-price');

function addToCart(name, price) {
    cart.push({ name, price });
    renderCart();
}

function renderCart() {
    cartItems.innerHTML = '';
    let total = 0;

    cart.forEach(item => {
        total += item.price;
        const li = document.createElement('li');
        li.textContent = `${item.name} - $${item.price}`;
        cartItems.appendChild(li);
    });

    totalPrice.textContent = `총 가격: $${total.toFixed(2)}`;
}
