<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ร้านค้าออนไลน์</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>ยินดีต้อนรับสู่ร้านค้าออนไลน์</h1>
    <div id="products"></div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
}

#products {
    display: flex;
    flex-wrap: wrap;
}

.product {
    border: 1px solid #ccc;
    margin: 10px;
    padding: 10px;
    width: 200px;
}

.product h2 {
    font-size: 20px;
}

.product p {
    font-size: 16px;
}

button {
    background-color: #28a745;
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
}
const products = [
    { id: 1, name: 'สินค้า A', price: 100 },
    { id: 2, name: 'สินค้า B', price: 200 },
    { id: 3, name: 'สินค้า C', price: 300 },
];

function displayProducts() {
    const productContainer = document.getElementById('products');
    products.forEach(product => {
        const productDiv = document.createElement('div');
        productDiv.className = 'product';
        productDiv.innerHTML = `
            <h2>${product.name}</h2>
            <p>ราคา: ${product.price} บาท</p>
            <button onclick="addToCart(${product.id})">เพิ่มในตะกร้า</button>
        `;
        productContainer.appendChild(productDiv);
    });
}

function addToCart(productId) {
    const product = products.find(p => p.id === productId);
    alert(`${product.name} ถูกเพิ่มในตะกร้า`);
}

displayProducts();
