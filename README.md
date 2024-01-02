E - COMMERCE WEP APP
 HTML:
 index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="styles.css">
    <title>E-Commerce Web App</title>
</head>
<body>
    <header>
        <h1>E-Commerce Store</h1>
    </header>

    <main id="product-list">
        <!-- Product cards will be dynamically added here -->
    </main>

    <script src="script.js"></script>
</body>
</html>


CSS:
style.css

body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 1em;
}

#product-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    padding: 2em;
}

.product-card {
    border: 1px solid #ddd;
    border-radius: 8px;
    margin: 1em;
    padding: 1em;
    width: 300px;
}

.product-img {
    max-width: 100%;
    height: auto;
}

.button {
    background-color: #4CAF50;
    color: white;
    padding: 0.5em 1em;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    border-radius: 4px;
}

JAVASCRIPT:
script.jss

// Sample product data (replace with your actual data)
const products = [
    { id: 1, name: 'Product 1', price: 19.99, image: 'product1.jpg' },
    { id: 2, name: 'Product 2', price: 29.99, image: 'product2.jpg' },
    // Add more products as needed
];

// Function to render product cards
function renderProducts() {
    const productList = document.getElementById('product-list');

    products.forEach(product => {
        const card = document.createElement('div');
        card.classList.add('product-card');

        const img = document.createElement('img');
        img.src = product.image;
        img.alt = product.name;
        img.classList.add('product-img');

        const name = document.createElement('h2');
        name.textContent = product.name;

        const price = document.createElement('p');
        price.textContent = `$${product.price.toFixed(2)}`;

        const buyButton = document.createElement('a');
        buyButton.href = '#'; // Add actual link or use onClick event
        buyButton.textContent = 'Buy';
        buyButton.classList.add('button');

        card.appendChild(img);
        card.appendChild(name);
        card.appendChild(price);
        card.appendChild(buyButton);

        productList.appendChild(card);
    });
}

// Call the function to render products when the page loads
window.onload = renderProducts;
