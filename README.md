<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TodoModa - Tienda Online</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
html, body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    color: #333;
    background-color: #f9f9f9;
}

/* Header styles */
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 20px;
    border-bottom: 1px solid #ddd;
    width: 100%;
    box-sizing: border-box;
    background: white;
    position: sticky;
    top: 0;
    z-index: 100;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
.header .logo img {
    height: 60px;
    width: auto;
}

@media (max-width: 768px) {
    .header img {
        width: 100px !important;
        height: auto !important;
    }
}

.header nav ul {
    list-style: none;
    display: flex;
    gap: 20px;
    margin: 0;
    padding: 0;
}
.header nav ul li a {
    text-decoration: none;
    color: #333;
    font-weight: bold;
    transition: color 0.3s;
}
.header nav ul li a:hover {
    color: #d81b60;
}
.header-icons {
    display: flex;
    gap: 15px;
}
.cart-icon {
    position: relative;
    cursor: pointer;
    font-size: 1.4rem;
}
.cart-count {
    position: absolute;
    top: -8px;
    right: -10px;
    background: #d81b60;
    color: white;
    border-radius: 50%;
    width: 20px;
    height: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.7rem;
    font-weight: bold;
}

/* Carousel styles */
.carousel {
    width: 100%;
    margin: auto;
    padding: 10px;
    overflow: hidden;
    border-radius: 20px;
}
.carousel-inner img {
    width: 100%;
    height: 100%;
    padding: 10px;
    object-fit: cover;
    border-radius: 20px;
}
.carousel-item {
    aspect-ratio: 16 / 9;
    height: auto;
}
.carousel .banner-text {
    position: absolute;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 1.2em;
    font-weight: bold;
    color: #fff;
    background: rgba(0,0,0,0.3);
    padding: 12px;
    border-radius: 30px;
    cursor: pointer;
    transition: all 0.3s;
    text-transform: uppercase;
}
.carousel .banner-text:hover {
    background: rgba(0,0,0,0.8);
    transform: translateX(-50%) scale(1.05);
}
.carousel .dots {
    position: absolute;
    bottom: 15px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 10px;
}
.carousel .dots span {
    width: 12px;
    height: 12px;
    background-color: rgba(255,255,255,0.6);
    border-radius: 50%;
    cursor: pointer;
    transition: all 0.3s;
}
.carousel .dots span.active {
    background-color: white;
    transform: scale(1.2);
}
.carousel-controls {
    position: absolute;
    top: 50%;
    width: 100%;
    display: flex;
    justify-content: space-between;
    transform: translateY(-50%);
    padding: 0 10px;
    box-sizing: border-box;
}
.carousel-controls button {
    background: rgba(0,0,0,0.5);
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
    font-size: 1.2rem;
    border-radius: 50%;
    transition: background 0.3s;
}
.carousel-controls button:hover {
    background: rgba(0,0,0,0.8);
}

/* Categories styles */
.categories {
    display: flex;
    overflow-x: auto;
    padding: 20px 10px;
    gap: 15px;
    justify-content: center;
    align-items: flex-start;
    scrollbar-width: none;
    -ms-overflow-style: none;
}
.categories::-webkit-scrollbar {
    display: none;
}
.category {
    flex: 0 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    cursor: pointer;
    width: 80px;
}
.category-image {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    overflow: hidden;
    border: 2px solid transparent;
    transition: box-shadow 0.3s ease, border-color 0.3s ease;
}
.category.active .category-image {
    border: 2px solid #ff5722;
    box-shadow: 0 0 15px 4px #e39ed9, 0 0 30px 6px #d85c9f88;
}
.category:hover .category-image {
    box-shadow: 0 0 15px 4px #e39ed9, 0 0 30px 6px #d85c9f;
    border-color: #d85c9f;
}
.category-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.category-title {
    text-align: center;
    color: #333;
    font-size: 12px;
    margin-top: 10px;
    font-weight: 600;
    max-width: 80px;
    line-height: 1.2;
    word-wrap: break-word;
}
@media (max-width: 768px) {
    .categories {
        padding: 15px 5px;
        justify-content: center;
        flex-wrap: nowrap;
        margin: 0 auto;
    }
    .category {
        width: 70px;
    }
    .category-image {
        width: 70px;
        height: 70px;
    }
    .category-title {
        font-size: 11px;
        margin-top: 8px;
        max-width: 70px;
    }
}
@media (max-width: 480px) {
    .categories {
        padding: 10px 5px;
        justify-content: center;
    }
    .category {
        width: 60px;
    }
    .category-image {
        width: 60px;
        height: 60px;
    }
    .category-title {
        font-size: 10px;
        margin-top: 6px;
        max-width: 60px;
    }
}

/* Model section styles */
.model-section {
    display: flex;
    justify-content: space-between;
    margin: 40px 0;
    width: 100%;
    flex-wrap: nowrap;
    padding: 0 20px;
    gap: 20px;
    box-sizing: border-box;
}
.model-item {
    position: relative;
    text-align: center;
    width: 50%;
    max-width: none;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}
.model-item img {
    width: 100%;
    height: 280px;
    object-fit: cover;
    display: block;
    cursor: pointer;
    transition: transform 0.5s;
    loading: lazy;
}
.model-item:hover img {
    transform: scale(1.05);
}
.model-btn {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    background: rgba(0, 0, 0, 0.7);
    color: white;
    border: none;
    padding: 10px 25px;
    border-radius: 30px;
    font-size: 1.1rem;
    font-weight: bold;
    cursor: pointer;
    transition: all 0.3s;
    width: 80%;
    max-width: 250px;
    text-align: center;
    backdrop-filter: blur(2px);
}
.model-btn:hover {
    background: rgba(0, 0, 0, 0.9);
    transform: translateX(-50%) scale(1.05);
}

/* Products container styles */
.products-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
    gap: 18px;
    padding: 0 20px 30px 20px;
    max-width: 1200px;
    margin: 0 auto;
}
.product-item {
    background: white;
    border-radius: 14px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    overflow: hidden;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    position: relative;
}
.product-item:hover {
    transform: translateY(-6px);
    box-shadow: 0 10px 18px rgba(0,0,0,0.15);
}
.product-item img {
    width: 100%;
    height: auto;
    object-fit: contain;
}
.badge-offer {
    position: absolute;
    top: 12px;
    left: 12px;
    background: #ff4d4f;
    color: white;
    font-size: 12px;
    font-weight: 700;
    padding: 3px 8px;
    border-radius: 4px;
    text-transform: uppercase;
    z-index: 10;
    user-select: none;
}
.product-info {
    padding: 5px 5px;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
.product-info h3 {
    margin: 0 0 2px 0;
    color: #333;
    min-height: 48px;
}
.product-info p.price {
    margin: 0;
    font-size: 18px;
    color: #ff5722;
    font-weight: 700;
}
.products-container .product-item .rating,
.products-container .product-item .color-palette,
.products-container .product-item .product-info p:not(.price) {
    display: none;
}
#all-products-container .product-item .rating,
#all-products-container .product-item .color-palette,
#all-products-container .product-item .product-info p:not(.price) {
    display: none;
}
#modal-product-rating {
    margin-bottom: 10px;
    color: #ff9800;
    font-size: 14px;
}
.btn-add-cart {
    margin-top: 12px;
    background-color: #ff5722;
    color: white;
    border: none;
    border-radius: 20px;
    padding: 9px 0;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.3s ease;
    width: 100%;
    letter-spacing: 0.03em;
}
.btn-add-cart:hover {
    background-color: #e64a19;
}
.color-palette {
    margin-top: 8px;
    display: flex;
    justify-content: center;
    gap: 8px;
}
.color-circle {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    border: 1px solid #ccc;
    cursor: default;
    transition: transform 0.2s;
}
.color-circle:hover {
    transform: scale(1.3);
    border-color: #ff5722;
}
#modal-color-palette .color-circle.selected {
    outline: 3px solid #ff5722;
    transform: scale(1.3);
    border-color: #ff5722;
}

/* Cart styles */
#cart {
    display: none;
    position: fixed;
    top: 0;
    right: 0;
    width: 100%;
    height: 100%;
    background: white;
    background-size: cover;
    background-position: center;
    box-shadow: -5px 0px 15px rgba(0, 0, 0, 0.1);
    z-index: 1000;
    padding: 0px;
    overflow-y: auto;
}
.cart h2 {
    font-size: 24px;
    margin-bottom: 20px;
    color: #333;
    text-align: center;
}
.cart-item {
    display: flex;
    flex-direction: column;
    background-color: #f9f9f9;
    margin-bottom: 10px;
    padding: 10px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
.cart-item .product-info {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
}
.cart-item .product-info img {
    width: 70px;
    height: 70px;
    border-radius: 8px;
    margin-right: 15px;
}
.cart-item .product-details {
    flex: 1;
}
.cart-item .actions {
    display: flex;
    gap: 8px;
    justify-content: flex-end;
}
#cart .cart-item .actions button {
    font-size: 12px;
    padding: 5px 8px;
    background-color: #f5f5f5;
    border: 1px solid #ccc;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}
#cart .cart-item .actions button:hover {
    background-color: #e1e1e1;
}
#cart-total {
    font-size: 22px;
    font-weight: bold;
    color: #333;
    margin: 20px;
    text-align: center;
}
#order-button {
    width: 90%;
    padding: 15px;
    background-color: #ff5722;
    color: white;
    border: none;
    font-size: 18px;
    border-radius: 20px;
    cursor: pointer;
    transition: background-color 0.3s;
    display: block;
    margin: 0 auto 30px;
}
#order-button:hover {
    background-color: #e64a19;
}
#cart-button {
    position: fixed;
    top: 20px;
    right: 20px;
    background-color: #ff5722;
    color: white;
    padding: 15px;
    border-radius: 50%;
    cursor: pointer;
    z-index: 2000;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    font-size: 24px;
}
#cart-button:hover {
    background-color: #e64a19;
}

/* Product modal styles */
.product-modal {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    z-index: 3000;
    justify-content: center;
    align-items: center;
}
.modal-content {
    background: #fff;
    padding: 15px;
    border-radius: 10px;
    max-width: 500px;
    width: 90%;
    text-align: center;
    position: relative;
    box-shadow: 0 5px 30px rgba(0,0,0,0.3);
    max-height: 95vh;
    overflow-y: auto;
}
.modal-content img {
    width: 100%;
    max-height: 200px;
    object-fit: contain;
    border-radius: 5px;
    margin-bottom: 10px;
    loading: lazy;
}
.modal-content h3 {
    margin: 0 0 8px;
    font-size: 1.3em;
}
.modal-content .description {
    margin: 10px 0;
    font-size: 0.9em;
    color: #555;
}
.modal-content .rating {
    margin: 10px 0;
    color: #f1c40f;
    font-size: 1em;
}
.modal-content .price {
    font-weight: bold;
    margin: 10px 0;
    font-size: 1.2em;
    color: #d81b60;
}
.modal-content .color-palette {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
    margin: 15px 0;
}
.modal-content .color-circle {
    width: 35px;
    height: 35px;
    border-radius: 50%;
    border: 1px solid #ddd;
    cursor: pointer;
    transition: transform 0.2s;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
.modal-content .color-circle.selected {
    transform: scale(1.2);
    border: 2px solid #d81b60;
}
.modal-content .quantity {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    margin: 15px 0;
}
.modal-content .quantity-btn {
    background: #d81b60;
    color: #fff;
    border: none;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 1em;
    display: flex;
    align-items: center;
    justify-content: center;
}
.modal-content .quantity-btn:hover {
    background: #ad1457;
}
.modal-content .quantity-input {
    width: 50px;
    height: 35px;
    text-align: center;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-size: 1em;
}
.modal-content .close-btn {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 1.3em;
    cursor: pointer;
    color: #333;
    background: none;
    border: none;
}
.modal-content .btn-add-cart {
    background: #d81b60;
    color: #fff;
    border: none;
    padding: 10px;
    border-radius: 5px;
    cursor: pointer;
    width: 100%;
    margin-top: 10px;
    font-size: 1em;
    font-weight: 600;
    transition: background 0.3s;
}
.modal-content .btn-add-cart:hover {
    background: #ad1457;
}

/* Updated product modal styles */
#product-modal {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.7);
    z-index: 3000;
    display: flex;
    align-items: center;
    justify-content: center;
}
#product-modal > div {
    background: #fff;
    border-radius: 10px;
    width: 90%;
    max-width: 500px;
    height: auto;
    max-height: 100vh;
    padding: 20px;
    position: relative;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    overflow-y: auto;
}
#close-product-modal {
    position: absolute;
    top: 10px;
    right: 15px;
    font-size: 20px;
    background: none;
    border: none;
    cursor: pointer;
    z-index: 3100;
}
#modal-product-image {
    width: 100%;
    max-height: 250px;
    object-fit: contain;
    border-radius: 10px;
    margin-bottom: 15px;
}
#modal-color-palette {
    margin-bottom: 15px;
    display: flex;
    justify-content: center;
    gap: 10px;
    flex-wrap: wrap;
}
#modal-quantity-decrease,
#modal-quantity-increase {
    width: 30px;
    height: 30px;
    cursor: pointer;
    background: #d81b60;
    color: #fff;
    border: none;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
}
#modal-quantity-decrease:hover,
#modal-quantity-increase:hover {
    background: #ad1457;
}
#modal-quantity {
    width: 50px;
    height: 35px;
    text-align: center;
    border: 1px solid #ddd;
    border-radius: 5px;
    pointer-events: none;
}
#modal-add-to-cart {
    width: 100%;
    padding: 10px;
    background: #d81b60;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 1em;
    font-weight: 600;
}
#modal-add-to-cart:hover {
    background: #ad1457;
}

/* Updated all-products-modal styles */
#all-products-modal {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #f9f9f9;
    z-index: 3000;
    overflow-y: auto;
}
#all-products-modal > div {
    background: #f9f9f9;
    width: 100%;
    max-width: 1200px;
    min-height: 100vh;
    padding: 08px;
    box-sizing: border-box;
    margin: 0 auto;
}
#close-all-products-modal {
    position: fixed;
    top: 10px;
    right: 15px;
    font-size: 20px;
    background: none;
    border: none;
    cursor: pointer;
    z-index: 3100;
}
#all-products-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
    gap: 18px;
    padding: 0 20px 30px 20px;
    max-width: 1200px;
    margin: 0 auto;
}
#all-products-container .product-item {
    background: white;
    border-radius: 14px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    overflow: hidden;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    position: relative;
}
#all-products-container .product-item:hover {
    transform: translateY(-6px);
    box-shadow: 0 10px 18px rgba(0,0,0,0.15);
}
#all-products-container .product-item img {
    width: 100%;
    height: auto;
    object-fit: contain;
}
#all-products-container .product-info {
    padding: 5px 5px;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
#all-products-container .product-info h3 {
    margin O: 0 0 6px 0;
    color: #333;
    min-height: 48px;
}
#all-products-container .product-info p.price {
    margin: 0;
    font-size: 18px;
    color: #ff5722;
    font-weight: 700;
}
#all-products-container .rating {
    font-size: 14px;
    color: #ff9800;
    margin-top: 6px;
    user-select: none;
}
#all-products-container .btn-add-cart {
    margin-top: 12px;
    background-color: #ff5722;
    color: white;
    border: none;
    border-radius: 20px;
    padding: 9px 0;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.3s ease;
    width: 100%;
    letter-spacing: 0.03em;
}
#all-products-container .btn-add-cart:hover {
    background-color: #e64a19;
}
#all-products-container .color-palette {
    margin-top: 8px;
    display: flex;
    justify-content: center;
    gap: 8px;
}
#all-products-container .color-circle {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    border: 1px solid #ccc;
    cursor: default;
    transition: transform 0.2s;
}
#all-products-container .color-circle:hover {
    transform: scale(1.3);
    border-color: #ff5722;
}
#all-products-search {
    width: 100%;
    padding: 8px;
    margin-bottom: 20px;
    border-radius: 8px;
    border: 1px solid #ddd;
    box-sizing: border-box;
}

/* Responsive styles */
@media (max-width: 768px) {
    .header {
        flex-wrap: wrap;
    }
    .header nav ul {
        width: 100%;
        justify-content: center;
        margin-top: 10px;
    }
    .header .logo img {
        height: 50px;
    }
    .product {
        width: 160px;
        min-width: 160px;
    }
    .model-section {
        flex-direction: column;
        gap: 15px;
    }
    .model-item {
        width: 100%;
    }
    .model-item img {
        height: 220px;
    }
    .cart-content {
        max-width: 100%;
    }
    #product-modal > div {
        width: 100%;
        height: 100%;
        max-height: 100vh;
        padding: 15px;
        overflow-y: auto;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    #product-modal > div img {
        max-height: 200px;
    }
    #product-modal > div h3 {
        font-size: 1.2em;
        margin-bottom: 6px;
    }
    #product-modal > div .description {
        font-size: 0.85em;
        margin: 8px 0;
    }
    #product-modal > div .rating {
        font-size: 0.9em;
        margin: 8px 0;
    }
    #product-modal > div .price {
        font-size: 1.1em;
        margin: 8px 0;
    }
    #product-modal > div .color-palette {
        gap: 8px;
        margin: 10px 0;
    }
    #product-modal > div .color-circle {
        width: 30px;
        height: 30px;
    }
    #product-modal > div .quantity {
        gap: 8px;
        margin: 10px 0;
    }
    #product-modal > div .quantity-btn {
        width: 28px;
        height: 28px;
        font-size: 0.9em;
    }
    #product-modal > div .quantity-input {
        width: 45px;
        height: 32px;
        font-size: 0.9em;
    }
    #product-modal > div .btn-add-cart {
        padding: 8px;
        font-size: 0.9em;
        margin-top: 8px;
    }
    #all-products-modal > div {
        width: 100%;
        max-width: 1200px;
        min-height: 100vh;
        padding: 15px;
    }
    #all-products-container {
        grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
        padding: 0 15px 20px 15px;
    }
    .product-info h3 {
        font-size: 0.9em;
    }
}
@media (max-width: 480px) {
    .header nav ul {
        gap: 10px;
        font-size: 0.9rem;
    }
    .carousel .banner-text {
        font-size: 0.9em;
        padding: 8px 15px;
    }
    .product {
        width: 140px;
        min-width: 140px;
    }
    .product img {
        height: 150px;
    }
    .product-info h3 {
        margin: 0;
        font-size: 0.9em;
    }
    .add-to-cart {
        top: 150px;
    }
    .section-title {
        font-size: 1.5rem;
    }
    .view-all-products, .clips-damas-products, .clips-ninas-products {
        grid-template-columns: 1fr;
    }
    #product-modal > div {
        width: 100%;
        height: 100%;
        max-height: 100vh;
        padding: 10px;
        border-radius: 8px;
        overflow-y: auto;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    #product-modal > div img {
        max-height: 180px;
        margin-bottom: 8px;
    }
    #product-modal > div h3 {
        font-size: 1.1em;
        margin-bottom: 5px;
    }
    #product-modal > div .description {
        font-size: 0.8em;
        margin: 6px 0;
    }
    #product-modal > div .rating {
        font-size: 0.85em;
        margin: 6px 0;
    }
    #product-modal > div .price {
        font-size: 1em;
        margin: 6px 0;
    }
    #product-modal > div .color-palette {
        gap: 6px;
        margin: 8px 0;
    }
    #product-modal > div .color-circle {
        width: 28px;
        height: 28px;
    }
    #product-modal > div .quantity {
        gap: 6px;
        margin: 8px 0;
    }
    #product-modal > div .quantity-btn {
        width: 26px;
        height: 26px;
        font-size: 0.85em;
    }
    #product-modal > div .quantity-input {
        width: 40px;
        height: 30px;
        font-size: 0.85em;
    }
    #product-modal > div .btn-add-cart {
        padding: 7px;
        font-size: 0.85em;
        margin-top: 6px;
    }
    #all-products-modal > div {
        width: 100%;
        max-width: 1200px;
        min-height: 100vh;
        padding: 10px;
    }
    #all-products-container {
        grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
        padding: 0 10px 15px 10px;
    }
}
    </style>
    <link href='https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css' rel='stylesheet'/>
    <script src='https://code.jquery.com/jquery-3.6.0.min.js'/>
    <script src='https://cdn.jsdelivr.net/npm/@popperjs/core@2.5.4/dist/umd/popper.min.js'/>
    <script src='https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js'/>
    <script src='https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js'/>
</head>
<body>
     <header class='header'>
    <img alt='Logo de la tienda de cervezas' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUOK1y_heZD6_UmmHTc9KTq4o6s2AzES1vSi6W5i0WvonBd3-Ts-DXS0eKOqtgT_1e5e4H_NGSezIvujiKdxxOEcYgeTap-tfwuQItGSZrinwaFKubdFlg-4PmJQ2UGe-Pj7rcdWiYhqMPw=w1500-h1000-p-k-no' style='width: 150px; height: auto;'/>
     </header>

  <section class='carousel slide' data-ride='carousel' id='carouselExampleIndicators'>
  <div class='carousel-inner'>
        <div class='carousel-item active'>
            <img alt='Promoción de cerveza 1' class='d-block w-100' src='https://pe.todomoda.com/media/wysiwyg/TM_DISNEY_STITCH_-_BANNERS_Desk_new_1.jpg'/>
        </div>
        <div class='carousel-item'>
            <img alt='Promoción de cerveza 2' class='d-block w-100' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUd2bofobsLtUl3qONXRSiTNou1a9W74yTaVYEr6h64PAuOOqQ-g_w6Ifs8arhOVjWboOrUFEcEDZlmtSBZkgS1YjEnSIw1f3w4IZRdMBwxibVChvNz2c93C78bOxNsx68MuBmN-4iYNCg=w2000-h2000-p-k-no'/>
        </div>
    </div>
    <div aria-label='Ver todos los productos' class='banner-text' id='viewAllBtn' role='button'>VER TODO</div>
    <div class='dots'>
    </div>
    <a class='carousel-control-prev' data-slide='prev' href='#carouselExampleIndicators' role='button'>
        <span aria-hidden='true' class='carousel-control-prev-icon'/>
        <span class='sr-only'>Previous</span>
    </a>
    <a class='carousel-control-next' data-slide='next' href='#carouselExampleIndicators' role='button'>
        <span aria-hidden='true' class='carousel-control-next-icon'/>
        <span class='sr-only'>Next</span>
    </a>
</section>

         <section class='categories'>
 <div class='category active' onclick='filterProducts("category1")'>
        <div class='category-image'>
            <img alt='Ganchos' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUGuPXaSC1mPGUKkOYa5z7JyvELvbIy0B4-WtB3tMHIKm2D6Sbg1cTWwU0MsxRJR_5lKb5t1MnVOStZk-tNPdUudQ6-h7M7ueR4l8N5IgmuOrhlNRMi0B_uohBDRomdzQUIHP7y244Zc150=w1024-h1024-p-k-no'/>
        </div>
        <div class='category-title'>Ganchos</div>
    </div>
    <div class='category' onclick='filterProducts("category2")'>
        <div class='category-image'>
            <img alt='Ganchos Niñas' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUDER3L7ISerfG6uiIU8ISdgKkibO-SXwGGNL1azb_TJ0qYIN3T7LsJyU-qc9-kQtucnOkLr5rPYtWt0fW0UL8-7RDD46bg_0JnGLkD8RSfQvGydDvq6L_ZLBoj4hnIhwHB3CEx1fPtJ58O=w1024-h1024-p-k-no'/>
        </div>
        <div class='category-title'>Ganchos Niñas</div>
    </div>
    <div class='category' onclick='filterProducts("category3")'>
        <div class='category-image'>
            <img alt='Cerveza Cusqueña' src='https://lh5.googleusercontent.com/p/AF1QipPTv840Ia5cUZM77OFrOKfiEpKJgbf_5bX-50WC=w1000-h1000-p-k-no'/>
        </div>
        <div class='category-title'>Cusqueña</div>
    </div>
    <div class='category' onclick='filterProducts("category4")'>
        <div class='category-image'>
            <img alt='Cerveza Corona' src='https://lh5.googleusercontent.com/p/AF1QipMKukYDijPnCrcbfRTUVW5c8DPfagwxBg5C4P_A=w1000-h1000-p-k-no'/>
        </div>
        <div class='category-title'>Corona</div>
    </div>
</section>     

<main>
<section class='products-container' id='products'>

<!-- Categoría 1: Pilsen -->

<div class='product-item category1'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Maxilazos' src='https://lh3.googleusercontent.com/gps-cs/AIky0YXdnjCFtJm5EhEvClhpsqjsYwwH2Xdqql3H45tWmgLdhiRX--KLwloCAl85SxTImNaOYYbS1MOrlGYrDwH31YoIyFBBn7KapQIKbAHVfoyNmbRBjjgmF0_SefXWn6udgSSaO19kdNtmnQBd=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Maxilazos - 5 Colores</h3>
        <p class='description'>Maxilazos vibrantes y duraderos, ideales para peinados versátiles. Disponibles en cinco colores llamativos que añaden un toque de estilo a cualquier look.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.2)</div>
        <p class='price'>S/ 7.00</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #ffeb3b;' title='Amarillo'/>
            <span class='color-circle' style='background-color: #d32f2f;' title='Rojo'/>
            <span class='color-circle' style='background-color: #e1bee7;' title='Lila'/>
            <span class='color-circle' style='background-color: #145a32;' title='Verde'/>
            <span class='color-circle' style='background-color: #d6eaf8;' title='Celeste'/>
        </div>
        <button class='btn-add-cart' data-id='1' data-name='Maxilazos - 5 Colores' data-price='7.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category1'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Mini Gancho Corazón' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUd2bofobsLtUl3qONXRSiTNou1a9W74yTaVYEr6h64PAuOOqQ-g_w6Ifs8arhOVjWboOrUFEcEDZlmtSBZkgS1YjEnSIw1f3w4IZRdMBwxibVChvNz2c93C78bOxNsx68MuBmN-4iYNCg=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Mini Gancho Corazón</h3>
        <p class='description'>Pequeños ganchos con diseño en forma de corazón, perfectos para detalles delicados en el cabello. Disponibles en tonos elegantes y neutros.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.2)</div>
        <p class='price'>S/ 2.50</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #17202a;' title='Negro'/>
            <span class='color-circle' style='background-color: #fff9c4;' title='Crema'/>
            <span class='color-circle' style='background-color: #fdebd0;' title='Piel'/>
            <span class='color-circle' style='background-color: #fdfefe;' title='Crema'/>
        </div>
        <button class='btn-add-cart' data-id='2' data-name='Mini Gancho Corazón' data-price='2.50'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category1'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Ganchos Navideños' src='https://lh3.googleusercontent.com/gps-cs/AIky0YV8A_P0YjCC6AIfC2B6HFvCKobK0UJZjVWMnzr6lfYPVXUk0gsszvJXojCK_ycIVH0cOD1-Qw3ICj1Bi9eLIf2TH0ZFaL14TuisJOWESznCPwqs2AAn_lgVOo2yGLhrKuG1yjgsGrWPIZ0k=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Ganchos Navideños</h3>
        <p class='description'>Ganchos festivos con temática navideña, ideales para celebraciones. Colores clásicos que combinan con cualquier estilo navideño.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#11088; (5.0)</div>
        <p class='price'>S/ 4.00</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #FFFFFF;' title='Blanco'/>
            <span class='color-circle' style='background-color: #FF0000;' title='Rojo'/>
            <span class='color-circle' style='background-color: #008000;' title='Verde'/>
        </div>
        <button class='btn-add-cart' data-id='3' data-name='Ganchos Navideños' data-price='4.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category1'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Gancho Hawaiano' src='https://lh3.googleusercontent.com/gps-cs/AIky0YVaD4OrbInMGPZXKiKtKplaYEn2Ck-9KCl8p9FJbJIXPMWFCDw9Dd5lrbO-8FfXeJZKvIEr-K5UpFwrCnofwtR30imdZTojz2gxrHqZLSM3qody1gDhWdXAm_C4le7hQ4zKL3imga1TIh_j=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Gancho Hawaiano</h3>
        <p class='description'>Ganchos inspirados en la vibrante cultura hawaiana, con un diseño alegre en color amarillo que evoca el sol y la playa.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.0)</div>
        <p class='price'>S/ 5.00</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #FFD700;' title='Amarillo'/>
        </div>
        <button class='btn-add-cart' data-id='4' data-name='Gancho Hawaiano' data-price='5.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category1'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Ganchos Acrílicos Color Celeste' src='https://lh3.googleusercontent.com/gps-cs/AIky0YXULCa-2ZSbLgwDDlphVpkyxIs_jH2pp8AIHp25rY65c3VTGPdLnesGcrtuCiDtLbovSHvwiSUpzfWiwyle1UmqeO6d0OEvhBLqp_6k4YBo2QzMGd9aduXbKMXqGVHIB0FKSWvBYE1FNgj_=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Ganchos Acrílicos Color Celeste</h3>
        <p class='description'>Ganchos acrílicos en tonos celestes y blancos, perfectos para un look fresco y moderno. Ligeros y resistentes.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.0)</div>
        <p class='price'>S/ 5.00</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #5dade2;' title='Celeste'/>
            <span class='color-circle' style='background-color: #ebf5fb;' title='Agua'/>
            <span class='color-circle' style='background-color: #FFFFFF;' title='Blanco'/>
        </div>
        <button class='btn-add-cart' data-id='5' data-name='Ganchos Acrílicos Color Celeste' data-price='5.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category1'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Ganchos' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUepENF6loS0sqfXxEEZlTcAEQ7R-6iS6rmphnT9YjPc9whL2WIk8tCzVNnHDeaj6AaV3e6-k4yeUx9j6nSHq-l2Tc_t0dGMQLhBQrbdREDnxR65_tbipCAL3NCKmRQYWk5geU5V_jn3EiW=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Ganchos</h3>
        <p class='description'>Ganchos clásicos en tonos marrón y crema, ideales para un estilo sobrio y elegante. Perfectos para uso diario.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.1)</div>
        <p class='price'>S/ 4.50</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #8d6e63;' title='Marrón'/>
            <span class='color-circle' style='background-color: #fef9e7;' title='Crema'/>
        </div>
        <button class='btn-add-cart' data-id='6' data-name='Ganchos' data-price='4.50'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category1'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Ganchos Torna Sol en forma de Flor' src='https://lh3.googleusercontent.com/gps-cs/AIky0YX2NRiy9kc9B9F5EY9kAoTjy699I8L7qzIaAFyN6ktzntZDbknG5_v1B6_JgD_hJDZQ7pAonmz2ynxpJqX4tYXVpt2EJISwaxV7Vd5er2HXevBcfzH_2KoEuxffPMG6wVLrMxkXZaJcUGxc=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Ganchos Torna Sol en forma de Flor</h3>
        <p class='description'>Ganchos con diseño de flor en forma de tornasol, con reflejos brillantes que cambian según la luz. Añaden un toque único a tu estilo.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.1)</div>
        <p class='price'>S/ 6.00</p>
        <button class='btn-add-cart' data-id='7' data-name='Ganchos Torna Sol en forma de Flor' data-price='6.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category1'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Ganchos Kawai en forma de Flor' src='https://lh3.googleusercontent.com/gps-cs/AIky0YXzdeSiF8Ekcd_sbWEkePfXIFlDCt8BeIvwjgW0_jHy1u9d3KWkRPGKY0IPp8ADAmGFn46hFm8U5vXqhoZ738QBNnwuwb-UXng4k1wKXRwyarfw7ST9PYntIH_SA_XEF0lDF6STVaLz16z2=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Ganchos Kawai en forma de Flor</h3>
        <p class='description'>Ganchos adorables con diseño de flor en colores vivos como amarillo, verde y anaranjado. Perfectos para un estilo kawaii y juvenil.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.5)</div>
        <p>Colores: Amarillo, Verde y Anaranjado</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #FFFF66;' title='Amarillo'/>
            <span class='color-circle' style='background-color: #CCFF00;' title='Verde'/>
            <span class='color-circle' style='background-color: #FF8C00;' title='Anaranjado'/>
        </div>
        <p class='price'>S/ 4.50</p>
        <button class='btn-add-cart' data-id='8' data-name='Ganchos Kawai en forma de Flor' data-price='4.50'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category1'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Ganchos de Flores' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUem5vYUL5I1PM57jknLifOO7yf5kSVMtMghU4lP6w0ZMUkV2L9UYoqFLTR_8PcGATvSRKyf0IVg5IYHBQzc5_aND9V8BvtQS47MAT--YXhLlrk645yFo2vaWRADuVRrnbiL5rs4ubhXvU=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Ganchos de Flores</h3>
        <p class='description'>Ganchos con diseño floral en tonos melón y amarillo, ideales para un look romántico y veraniego. Cómodos y ligeros.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.0)</div>
        <p>Colores: Melón y Amarillo</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #FFB347;' title='Melón'/>
            <span class='color-circle' style='background-color: #FFD700;' title='Amarillo'/>
        </div>
        <p class='price'>S/ 5.00</p>
        <button class='btn-add-cart' data-id='9' data-name='Ganchos de Flores' data-price='5.00'>Agregar al carrito</button>
    </div>
</div>

<!-- Categoría 2: Cristal -->

<div class='product-item category2'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Par de mini ganchitos en forma de flor' src='https://lh3.googleusercontent.com/gps-cs/AIky0YVcDqGO_EKNry0Eb-BkdsNH0V0lOhwW7AM5WEqz8IiNlbpTs2U3Io9_kt4yCGgt5haYI5RgwRDHv-LMBqc5bvmX245QMyriwIoyJyniPQH9cJJ9iCC2fC8hY06M9BU9nFd6NhCLGVGCC34N=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Par de mini ganchitos en forma de flor</h3>
        <p class='description'>Mini ganchitos con forma de flor, perfectos para detalles sutiles en peinados. Ideales para niños o looks minimalistas.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.0)</div>
        <p class='price'>S/ 3.00</p>
        <p>Color: -</p>
        <button class='btn-add-cart' data-id='14' data-name='Par de mini ganchitos en forma de flor' data-price='3.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category2'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Mini ganchitos en forma de mariposa' src='https://lh3.googleusercontent.com/gps-cs/AIky0YW1eFtqiwT_PM-xOZnd2iVogh-XQVJclLEtgsh0i5wUGm9NvOCot9LJLfDmZE58abznArTin0EgjEMw3HuKeK9_9hoODK0kla3nM-GYGSvA8_xXCBmu_qiSuoHzgpSaO_2EtqXLAjnCs34l=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Mini ganchitos en forma de mariposa</h3>
        <p class='description'>Encantadores ganchitos con forma de mariposa, ideales para añadir un toque juguetón a cualquier peinado.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.5)</div>
        <p class='price'>S/ 2.00</p>
        <p>Color: -</p>
        <button class='btn-add-cart' data-id='15' data-name='Mini ganchitos en forma de mariposa' data-price='2.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category2'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Mini ganchitos' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUgnWieVRURnUHds0U4E5FROmRmvztpc0ynONqB5wFO-tvCmbrBn0-E971IAl2YG7r7cobC9Hx-g0AbDpTP71ukEEb6n20lHQz-aPBoI5xDWtVwABfSJFIbqdRT6_YJzOT7x8uhaX-KBSLE=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Mini ganchitos</h3>
        <p class='description'>Ganchitos pequeños y discretos, perfectos para sujetar mechones finos o detalles en peinados elaborados.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.3)</div>
        <p class='price'>S/ 1.50</p>
        <p>Color: -</p>
        <button class='btn-add-cart' data-id='16' data-name='Mini ganchitos' data-price='1.50'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category2'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Ligas colores pasteles y fuertes' src='https://lh3.googleusercontent.com/gps-cs/AIky0YVwhLWhfaBVh3ChmdRjktxd6WCi7W6fTmz2_7TvWPHTT_-3tX1zci-DGspLNMmn3SpAYgh9RN5G_lHRBehTbWzF16lZ9CNiBbjgj5-EVSXMU3aVjCsYaPQ5Maahznx9Fi79zzSnwLxM_nkC=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Ligas colores pasteles y fuertes</h3>
        <p class='description'>Ligas elásticas en una variedad de colores pasteles y vibrantes, perfectas para cualquier estilo de peinado. Resistentes y cómodas.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.0)</div>
        <p class='price'>S/ 1.00</p>
        <p>Color: Varios</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #FFC0CB;' title='Rosa Pastel'/>
            <span class='color-circle' style='background-color: #FFD700;' title='Amarillo'/>
            <span class='color-circle' style='background-color: #00BFFF;' title='Azul'/>
            <span class='color-circle' style='background-color: #FF4500;' title='Naranja'/>
            <span class='color-circle' style='background-color: #008000;' title='Verde'/>
        </div>
        <button class='btn-add-cart' data-id='17' data-name='Ligas colores pasteles y fuertes' data-price='1.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category2'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Colets negros' src='https://lh3.googleusercontent.com/gps-cs/AIky0YWE3Z0a1qVkSdmBI9RQzayKeT8bgvXn5RTJNXmMJjHG9uzg5VUrwt4-PKEq6AdcYPITi3LkJvKtdxDXq6PucsAOpzZGm2J8QGEYCR4Ff59f3YXXaKQ_Ww8lgm4vOYlRuyCNXxPuyWPFWf23=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Colets negros</h3>
        <p class='description'>Colets negros clásicos y versátiles, ideales para cualquier tipo de cabello y estilo. Proporcionan un agarre firme y duradero.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.3)</div>
        <p class='price'>S/ 1.00</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #000000;' title='Negro'/>
        </div>
        <button class='btn-add-cart' data-id='18' data-name='Colets negros' data-price='1.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category2'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Colets colores pasteles' src='https://lh3.googleusercontent.com/gps-cs/AIky0YVVXgYaHEulEuraO7tX6LShXlnoogs6cvwc7jryv8vOVwEt2wCEPWyj0ihUEHTjGMKv0HpL3uglAD96vZsANfdnMrLB4hRI1quw3OaPX-ewOFjUY9eF2ggyG4sMZLcBfJ8amsKoKsAgOXPG=w2000-h2000-p-k-no'/>
    <div class='product-info'>
        <h3>Colets colores pasteles</h3>
        <p class='description'>Colets en suaves tonos pasteles, perfectos para un look delicado y femenino. Cómodos y fáciles de usar.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.4)</div>
        <p class='price'>S/ 1.00</p>
        <div aria-label='Paleta de colores' class='color-palette'>
            <span class='color-circle' style='background-color: #FFB6C1;' title='Rosa Pastel'/>
            <span class='color-circle' style='background-color: #87CEFA;' title='Azul Pastel'/>
            <span class='color-circle' style='background-color: #98FB98;' title='Verde Pastel'/>
        </div>
        <button class='btn-add-cart' data-id='19' data-name='Colets colores pasteles' data-price='1.00'>Agregar al carrito</button>
    </div>
</div>

<!-- Categoría 3: Cusqueña -->

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Dorada 12 unidades botella 620ml' src='https://lh5.googleusercontent.com/p/AF1QipNoTsJrETd6q5R_4NE-3J7NFqBZ2_lDVDz_qgFP=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>12UND</h3>
        <p class='description'>Pack de 12 botellas de Cusqueña Dorada de 620ml, una cerveza premium con sabor suave y refrescante, ideal para compartir.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.1)</div>
        <p class='price'>S/ 38.00</p>
        <button class='btn-add-cart' data-id='13' data-name='CUSQUEÑA DORADA BOTELLA 12UND 620ML' data-price='38.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Dorada 6 unidades lata 355ml' src='https://lh5.googleusercontent.com/p/AF1QipPxFbOmsmYehzvFwrsgO7n7sYIVmGNIhbyIkTfB=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>6UND</h3>
        <p class='description'>Pack de 6 latas de Cusqueña Dorada de 355ml, perfectas para disfrutar de una cerveza ligera y equilibrada en cualquier momento.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.0)</div>
        <p class='price'>S/ 40.00</p>
        <button class='btn-add-cart' data-id='14' data-name='CUSQUEÑA DORADA LATA 6UND 355ML' data-price='40.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Dorada 6 unidades botella 310ml' src='https://lh5.googleusercontent.com/p/AF1QipNwwrJABQhcpzwphwpj65nWj5mOzy8UkcEXEs-J=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>6UND</h3>
        <p class='description'>Pack de 6 botellas de Cusqueña Dorada de 310ml, con un sabor suave y refrescante, ideal para reuniones o momentos especiales.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.0)</div>
        <p class='price'>S/ 45.00</p>
        <button class='btn-add-cart' data-id='15' data-name='CUSQUEÑA DORADA BOTELLA 310ML 6UND' data-price='45.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Dorada 1 unidad botella 620ml' src='https://lh5.googleusercontent.com/p/AF1QipNgCBjfQQwmp2D6M1GW7CNcVbI4Z1chuRiB4A4a=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>1UND</h3>
        <p class='description'>Botella individual de Cusqueña Dorada de 620ml, perfecta para disfrutar de una cerveza premium con un sabor único.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.7)</div>
        <p class='price'>S/ 50.00</p>
        <button class='btn-add-cart' data-id='16' data-name='CUSQUEÑA DORADA BOTELLA 620ML 1UND' data-price='50.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Negra 12 unidades botella 620ml' src='https://lh5.googleusercontent.com/p/AF1QipP0tdefcLaVakf85cGytfRKC1KZlc1b4NmhF4Ah=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>12UND</h3>
        <p class='description'>Pack de 12 botellas de Cusqueña Negra de 620ml, una cerveza robusta con notas tostadas y un sabor profundo.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#11088; (5.0)</div>
        <p class='price'>S/ 55.00</p>
        <button class='btn-add-cart' data-id='17' data-name='CUSQUEÑA NEGRA BOTELLA 620ML 12UND' data-price='55.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Negra 6 unidades lata 355ml' src='https://lh5.googleusercontent.com/p/AF1QipPAuHP_o-OlN8_h7ckQOA7FLivnddGWzW9Qd4W0=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>6UND</h3>
        <p class='description'>Pack de 6 latas de Cusqueña Negra de 355ml, ideal para quienes buscan un sabor intenso y distintivo.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.6)</div>
        <p class='price'>S/ 38.00</p>
        <button class='btn-add-cart' data-id='18' data-name='CUSQUEÑA NEGRA LATA 355ML 6UND' data-price='38.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Negra 6 unidades botella 310ml' src='https://lh5.googleusercontent.com/p/AF1QipNek4gSJN5hB1ZsFgHeb_Sncfcevv-PGJRzjV2f=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>6UND</h3>
        <p class='description'>Pack de 6 botellas de Cusqueña Negra de 310ml, con un sabor robusto y notas tostadas para una experiencia única.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.7)</div>
        <p class='price'>S/ 40.00</p>
        <button class='btn-add-cart' data-id='19' data-name='CUSQUEÑA NEGRA BOTELLA 310ML 6UND' data-price='40.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Negra 1 unidad botella 620ml' src='https://lh3.googleusercontent.com/gps-cs/ADgaOlqzhG9TUv81NyUehZcMYJAyyULJ8N0oQECaipB79kewLW5fVvAZbNkSe8wG2Gk8Y0PYgPBScdnDHUzGmDE5ZVL8SIIN-a2jNPz50RLV6IFm_nN_cj0dWiDCbe_mbdCr3p5z9wNlPnVK0cc=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>1UND</h3>
        <p class='description'>Botella individual de Cusqueña Negra de 620ml, perfecta para disfrutar de una cerveza intensa y llena de carácter.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.0)</div>
        <p class='price'>S/ 45.00</p>
        <button class='btn-add-cart' data-id='20' data-name='CUSQUEÑA NEGRA BOTELLA 620ML 1UND' data-price='45.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Trigo 12 unidades botella 620ml' src='https://lh5.googleusercontent.com/p/AF1QipM4Nx30hCWjzmP-xBj8g25xnOPTdyGnaYQh3w7Z=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>12UND</h3>
        <p class='description'>Pack de 12 botellas de Cusqueña Trigo de 620ml, una cerveza de trigo con un sabor suave y ligeramente afrutado.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.1)</div>
        <p class='price'>S/ 50.00</p>
        <button class='btn-add-cart' data-id='21' data-name='CUSQUEÑA TRIGO BOTELLA 620ML 12UND' data-price='50.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Trigo 6 unidades lata 355ml' src='https://lh5.googleusercontent.com/p/AF1QipO4iyindkHDjnUINGJQq6qvPhbwKopod8HAqpCk=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>6UND</h3>
        <p class='description'>Pack de 6 latas de Cusqueña Trigo de 355ml, ideal para disfrutar de una cerveza ligera con notas cítricas.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.8)</div>
        <p class='price'>S/ 55.00</p>
        <button class='btn-add-cart' data-id='22' data-name='CUSQUEÑA TRIGO LATA 355ML 6UND' data-price='55.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Trigo 6 unidades botella 310ml' src='https://lh5.googleusercontent.com/p/AF1QipMMdiCbLWstSI1zorN9ORMoOwRMEkISgX5LMTVA=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>6UND</h3>
        <p class='description'>Pack de 6 botellas de Cusqueña Trigo de 310ml, una cerveza refrescante con un toque afrutado, perfecta para cualquier ocasión.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.7)</div>
        <p class='price'>S/ 38.00</p>
        <button class='btn-add-cart' data-id='23' data-name='CUSQUEÑA TRIGO BOTELLA 310ML 6UND' data-price='38.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category3'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Cusqueña Trigo 1 unidad botella 620ml' src='https://lh5.googleusercontent.com/p/AF1QipN0hF8bRUE_5xFtWuNK7tBoEjwte5qvAkO6azO_=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>1UND</h3>
        <p class='description'>Botella individual de Cusqueña Trigo de 620ml, ideal para disfrutar de una cerveza de trigo suave y refrescante.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.1)</div>
        <p class='price'>S/ 40.00</p>
        <button class='btn-add-cart' data-id='24' data-name='CUSQUEÑA TRIGO BOTELLA 620ML 1UND' data-price='40.00'>Agregar al carrito</button>
    </div>
</div>

<!-- Categoría 4: Corona -->

<div class='product-item category4'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Corona 6 unidades botella 330ml' src='https://lh5.googleusercontent.com/p/AF1QipOb0rNDzoT3u3yvvnUzNfaEnxZTQrjGLQe76nVO=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>6UND</h3>
        <p class='description'>Pack de 6 botellas de Corona de 330ml, una cerveza ligera y refrescante, perfecta para disfrutar con un toque de limón.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#11088;&#9734; (4.0)</div>
        <p class='price'>S/ 38.00</p>
        <button class='btn-add-cart' data-id='25' data-name='CORONA BOTELLA 330ML 6UND' data-price='38.00'>Agregar al carrito</button>
    </div>
</div>

<div class='product-item category4'>
    <div class='badge-offer'>Oferta</div>
    <img alt='Corona 6 unidades lata 355ml' src='https://lh5.googleusercontent.com/p/AF1QipNpxGslUgp2AU6xtgihRkNiMoOHI9olKgj7D22d=w1000-h1000-p-k-no'/>
    <div class='product-info'>
        <h3>6UND</h3>
        <p class='description'>Pack de 6 latas de Corona de 355ml, ideal para disfrutar de una cerveza fresca y ligera en cualquier momento.</p>
        <div class='rating'>&#11088;&#11088;&#11088;&#9734;&#9734; (3.7)</div>
        <p class='price'>S/ 40.00</p>
        <button class='btn-add-cart' data-id='26' data-name='CORONA LATA 355ML 6UND' data-price='40.00'>Agregar al carrito</button>
    </div>
</div>

</section>
<main>
<section class='model-section'>
    <div class='model-item'>
        <img alt='Modelo de cerveza 1' src='https://lh5.googleusercontent.com/p/AF1QipPTv840Ia5cUZM77OFrOKfiEpKJgbf_5bX-50WC=w1000-h1000-p-k-no'/>
        <button class='model-btn' onclick='filterProducts("category3")'>Cerveza Cusqueña</button>
    </div>
    <div class='model-item'>
        <img alt='Modelo de cerveza 2' src='https://lh5.googleusercontent.com/p/AF1QipMKukYDijPnCrcbfRTUVW5c8DPfagwxBg5C4P_A=w1000-h1000-p-k-no'/>
        <button class='model-btn' onclick='filterProducts("category4")'>Cerveza Corona</button>
    </div>
</section>

<div id='cart-button'>🛒<span class='cart-count' id='cart-count'>0</span></div>

<div id='cart'>
    <button id='cart-button' style='display: none;'>🛒</button>
    <h2>Carrito de Compras</h2>
    <div id='cart-items'></div>
    <div id='cart-total'>Total: S/ 0.00</div>
    <button id='order-button'>Realizar Pedido</button>
</div>

<div id='product-modal'>
    <div>
        <button id='close-product-modal'>✕</button>
        <img id='modal-product-image' alt='Producto seleccionado'/>
        <h3 id='modal-product-name'></h3>
        <p id='modal-product-description'></p>
        <div id='modal-product-rating'></div>
        <p id='modal-product-price'></p>
        <div id='modal-color-palette'></div>
        <div class='quantity'>
            <button id='modal-quantity-decrease'>-</button>
            <input id='modal-quantity' readonly type='number' value='1'/>
            <button id='modal-quantity-increase'>+</button>
        </div>
        <button id='modal-add-to-cart'>Agregar al carrito</button>
    </div>
</div>

<div id='all-products-modal'>
    <div>
        <button id='close-all-products-modal'>✕</button>
        <input id='all-products-search' placeholder='Buscar productos...' type='text'/>
        <div id='all-products-container'></div>
    </div>
</div>

<div id='boleta-modal'>
    <div class='modal-content'>
        <button class='close-btn' id='close-boleta-modal'>✕</button>
        <h2>Boleta de Compra</h2>
        <div id='boleta-items'></div>
        <div id='boleta-total'>Total: S/ 0.00</div>
        <button id='download-boleta'>Descargar Boleta</button>
    </div>
</div>
</main>
<script>

let cart = [];
let currentProduct = null;
let currentCategory = 'category1';
let currentColor = null;

const products = [
    { id: 1, name: 'Maxilazos - 5 Colores', price: 7.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YXdnjCFtJm5EhEvClhpsqjsYwwH2Xdqql3H45tWmgLdhiRX--KLwloCAl85SxTImNaOYYbS1MOrlGYrDwH31YoIyFBBn7KapQIKbAHVfoyNmbRBjjgmF0_SefXWn6udgSSaO19kdNtmnQBd=w2000-h2000-p-k-no', description: 'Maxilazos vibrantes y duraderos, ideales para peinados versátiles.', rating: '⭐⭐⭐⭐☆ (4.2)', category: 'category1', colors: ['#ffeb3b', '#d32f2f', '#e1bee7', '#145a32', '#d6eaf8'] },
    { id: 2, name: 'Mini Gancho Corazón', price: 2.50, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YUd2bofobsLtUl3qONXRSiTNou1a9W74yTaVYEr6h64PAuOOqQ-g_w6Ifs8arhOVjWboOrUFEcEDZlmtSBZkgS1YjEnSIw1f3w4IZRdMBwxibVChvNz2c93C78bOxNsx68MuBmN-4iYNCg=w2000-h2000-p-k-no', description: 'Pequeños ganchos con diseño en forma de corazón.', rating: '⭐⭐⭐☆☆ (3.2)', category: 'category1', colors: ['#17202a', '#fff9c4', '#fdebd0', '#fdfefe'] },
    { id: 3, name: 'Ganchos Navideños', price: 4.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YV8A_P0YjCC6AIfC2B6HFvCKobK0UJZjVWMnzr6lfYPVXUk0gsszvJXojCK_ycIVH0cOD1-Qw3ICj1Bi9eLIf2TH0ZFaL14TuisJOWESznCPwqs2AAn_lgVOo2yGLhrKuG1yjgsGrWPIZ0k=w2000-h2000-p-k-no', description: 'Ganchos festivos con temática navideña.', rating: '⭐⭐⭐⭐⭐ (5.0)', category: 'category1', colors: ['#FFFFFF', '#FF0000', '#008000'] },
    { id: 4, name: 'Gancho Hawaiano', price: 5.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YVaD4OrbInMGPZXKiKtKplaYEn2Ck-9KCl8p9FJbJIXPMWFCDw9Dd5lrbO-8FfXeJZKvIEr-K5UpFwrCnofwtR30imdZTojz2gxrHqZLSM3qody1gDhWdXAm_C4le7hQ4zKL3imga1TIh_j=w2000-h2000-p-k-no', description: 'Ganchos inspirados en la vibrante cultura hawaiana.', rating: '⭐⭐⭐⭐☆ (4.0)', category: 'category1', colors: ['#FFD700'] },
    { id: 5, name: 'Ganchos Acrílicos Color Celeste', price: 5.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YXULCa-2ZSbLgwDDlphVpkyxIs_jH2pp8AIHp25rY65c3VTGPdLnesGcrtuCiDtLbovSHvwiSUpzfWiwyle1UmqeO6d0OEvhBLqp_6k4YBo2QzMGd9aduXbKMXqGVHIB0FKSWvBYE1FNgj_=w2000-h2000-p-k-no', description: 'Ganchos acrílicos en tonos celestes y blancos.', rating: '⭐⭐⭐⭐☆ (4.0)', category: 'category1', colors: ['#5dade2', '#ebf5fb', '#FFFFFF'] },
    { id: 6, name: 'Ganchos', price: 4.50, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YUepENF6loS0sqfXxEEZlTcAEQ7R-6iS6rmphnT9YjPc9whL2WIk8tCzVNnHDeaj6AaV3e6-k4yeUx9j6nSHq-l2Tc_t0dGMQLhBQrbdREDnxR65_tbipCAL3NCKmRQYWk5geU5V_jn3EiW=w2000-h2000-p-k-no', description: 'Ganchos clásicos en tonos marrón y crema.', rating: '⭐⭐⭐☆☆ (3.1)', category: 'category1', colors: ['#8d6e63', '#fef9e7'] },
    { id: 7, name: 'Ganchos Torna Sol en forma de Flor', price: 6.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YX2NRiy9kc9B9F5EY9kAoTjy699I8L7qzIaAFyN6ktzntZDbknG5_v1B6_JgD_hJDZQ7pAonmz2ynxpJqX4tYXVpt2EJISwaxV7Vd5er2HXevBcfzH_2KoEuxffPMG6wVLrMxkXZaJcUGxc=w2000-h2000-p-k-no', description: 'Ganchos con diseño de flor en forma de tornasol.', rating: '⭐⭐⭐⭐☆ (4.1)', category: 'category1', colors: [] },
    { id: 8, name: 'Ganchos Kawai en forma de Flor', price: 4.50, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YXzdeSiF8Ekcd_sbWEkePfXIFlDCt8BeIvwjgW0_jHy1u9d3KWkRPGKY0IPp8ADAmGFn46hFm8U5vXqhoZ738QBNnwuwb-UXng4k1wKXRwyarfw7ST9PYntIH_SA_XEF0lDF6STVaLz16z2=w2000-h2000-p-k-no', description: 'Ganchos adorables con diseño de flor en colores vivos.', rating: '⭐⭐⭐☆☆ (3.5)', category: 'category1', colors: ['#FFFF66', '#CCFF00', '#FF8C00'] },
    { id: 9, name: 'Ganchos de Flores', price: 5.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YUem5vYUL5I1PM57jknLifOO7yf5kSVMtMghU4lP6w0ZMUkV2L9UYoqFLTR_8PcGATvSRKyf0IVg5IYHBQzc5_aND9V8BvtQS47MAT--YXhLlrk645yFo2vaWRADuVRrnbiL5rs4ubhXvU=w2000-h2000-p-k-no', description: 'Ganchos con diseño floral en tonos melón y amarillo.', rating: '⭐⭐⭐⭐☆ (4.0)', category: 'category1', colors: ['#FFB347', '#FFD700'] },
    { id: 10, name: 'Par de mini ganchitos en forma de flor', price: 3.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YVcDqGO_EKNry0Eb-BkdsNH0V0lOhwW7AM5WEqz8IiNlbpTs2U3Io9_kt4yCGgt5haYI5RgwRDHv-LMBqc5bvmX245QMyriwIoyJyniPQH9cJJ9iCC2fC8hY06M9BU9nFd6NhCLGVGCC34N=w2000-h2000-p-k-no', description: 'Mini ganchitos con forma de flor.', rating: '⭐⭐⭐⭐☆ (4.0)', category: 'category2', colors: [] },
    { id: 11, name: 'Mini ganchitos en forma de mariposa', price: 2.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YW1eFtqiwT_PM-xOZnd2iVogh-XQVJclLEtgsh0i5wUGm9NvOCot9LJLfDmZE58abznArTin0EgjEMw3HuKeK9_9hoODK0kla3nM-GYGSvA8_xXCBmu_qiSuoHzgpSaO_2EtqXLAjnCs34l=w2000-h2000-p-k-no', description: 'Encantadores ganchitos con forma de mariposa.', rating: '⭐⭐⭐☆☆ (3.5)', category: 'category2', colors: [] },
    { id: 12, name: 'Mini ganchitos', price: 1.50, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YUgnWieVRURnUHds0U4E5FROmRmvztpc0ynONqB5wFO-tvCmbrBn0-E971IAl2YG7r7cobC9Hx-g0AbDpTP71ukEEb6n20lHQz-aPBoI5xDWtVwABfSJFIbqdRT6_YJzOT7x8uhaX-KBSLE=w2000-h2000-p-k-no', description: 'Ganchitos pequeños y discretos.', rating: '⭐⭐⭐☆☆ (3.3)', category: 'category2', colors: [] },
    { id: 13, name: 'Ligas colores pasteles y fuertes', price: 1.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YVwhLWhfaBVh3ChmdRjktxd6WCi7W6fTmz2_7TvWPHTT_-3tX1zci-DGspLNMmn3SpAYgh9RN5G_lHRBehTbWzF16lZ9CNiBbjgj5-EVSXMU3aVjCsYaPQ5Maahznx9Fi79zzSnwLxM_nkC=w2000-h2000-p-k-no', description: 'Ligas elásticas en una variedad de colores.', rating: '⭐⭐⭐⭐☆ (4.0)', category: 'category2', colors: ['#FFC0CB', '#FFD700', '#00BFFF', '#FF4500', '#008000'] },
    { id: 14, name: 'Colets negros', price: 1.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YWE3Z0a1qVkSdmBI9RQzayKeT8bgvXn5RTJNXmMJjHG9uzg5VUrwt4-PKEq6AdcYPITi3LkJvKtdxDXq6PucsAOpzZGm2J8QGEYCR4Ff59f3YXXaKQ_Ww8lgm4vOYlRuyCNXxPuyWPFWf23=w2000-h2000-p-k-no', description: 'Colets negros clásicos y versátiles.', rating: '⭐⭐⭐☆☆ (3.3)', category: 'category2', colors: ['#000000'] },
    { id: 15, name: 'Colets colores pasteles', price: 1.00, image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YVVXgYaHEulEuraO7tX6LShXlnoogs6cvwc7jryv8vOVwEt2wCEPWyj0ihUEHTjGMKv0HpL3uglAD96vZsANfdnMrLB4hRI1quw3OaPX-ewOFjUY9eF2ggyG4sMZLcBfJ8amsKoKsAgOXPG=w2000-h2000-p-k-no', description: 'Colets en suaves tonos pasteles.', rating: '⭐⭐⭐☆☆ (3.4)', category: 'category2', colors: ['#FFB6C1', '#87CEFA', '#98FB98'] },
    { id: 16, name: 'CUSQUEÑA DORADA BOTELLA 12UND 620ML', price: 38.00, image: 'https://lh5.googleusercontent.com/p/AF1QipNoTsJrETd6q5R_4NE-3J7NFqBZ2_lDVDz_qgFP=w1000-h1000-p-k-no', description: 'Pack de 12 botellas de Cusqueña Dorada de 620ml.', rating: '⭐⭐⭐⭐☆ (4.1)', category: 'category3', colors: [] },
    { id: 17, name: 'CUSQUEÑA DORADA LATA 6UND 355ML', price: 40.00, image: 'https://lh5.googleusercontent.com/p/AF1QipPxFbOmsmYehzvFwrsgO7n7sYIVmGNIhbyIkTfB=w1000-h1000-p-k-no', description: 'Pack de 6 latas de Cusqueña Dorada de 355ml.', rating: '⭐⭐⭐⭐☆ (4.0)', category: 'category3', colors: [] },
    { id: 18, name: 'CUSQUEÑA DORADA BOTELLA 310ML 6UND', price: 45.00, image: 'https://lh5.googleusercontent.com/p/AF1QipNwwrJABQhcpzwphwpj65nWj5mOzy8UkcEXEs-J=w1000-h1000-p-k-no', description: 'Pack de 6 botellas de Cusqueña Dorada de 310ml.', rating: '⭐⭐⭐⭐☆ (4.0)', category: 'category3', colors: [] },
    { id: 19, name: 'CUSQUEÑA DORADA BOTELLA 620ML 1UND', price: 50.00, image: 'https://lh5.googleusercontent.com/p/AF1QipNgCBjfQQwmp2D6M1GW7CNcVbI4Z1chuRiB4A4a=w1000-h1000-p-k-no', description: 'Botella individual de Cusqueña Dorada de 620ml.', rating: '⭐⭐⭐☆☆ (3.7)', category: 'category3', colors: [] },
    { id: 20, name: 'CUSQUEÑA NEGRA BOTELLA 620ML 12UND', price: 55.00, image: 'https://lh5.googleusercontent.com/p/AF1QipP0tdefcLaVakf85cGytfRKC1KZlc1b4NmhF4Ah=w1000-h1000-p-k-no', description: 'Pack de 12 botellas de Cusqueña Negra de 620ml.', rating: '⭐⭐⭐⭐⭐ (5.0)', category: 'category3', colors: [] },
    { id: 21, name: 'CUSQUEÑA NEGRA LATA 355ML 6UND', price: 38.00, image: 'https://lh5.googleusercontent.com/p/AF1QipPAuHP_o-OlN8_h7ckQOA7FLivnddGWzW9Qd4W0=w1000-h1000-p-k-no', description: 'Pack de 6 latas de Cusqueña Negra de 355ml.', rating: '⭐⭐⭐☆☆ (3.6)', category: 'category3', colors: [] },
    { id: 22, name: 'CUSQUEÑA NEGRA BOTELLA 310ML 6UND', price: 40.00, image: 'https://lh5.googleusercontent.com/p/AF1QipNek4gSJN5hB1ZsFgHeb_Sncfcevv-PGJRzjV2f=w1000-h1000-p-k-no', description: 'Pack de 6 botellas de Cusqueña Negra de 310ml.', rating: '⭐⭐⭐☆☆ (3.7)', category: 'category3', colors: [] },
    { id: 23, name: 'CUSQUEÑA NEGRA BOTELLA 620ML 1UND', price: 45.00, image: 'https://lh3.googleusercontent.com/gps-cs/ADgaOlqzhG9TUv81NyUehZcMYJAyyULJ8N0oQECaipB79kewLW5fVvAZbNkSe8wG2Gk8Y0PYgPBScdnDHUzGmDE5ZVL8SIIN-a2jNPz50RLV6IFm_nN_cj0dWiDCbe_mbdCr3p5z9wNlPnVK0cc=w1000-h1000-p-k-no', description: 'Botella individual de Cusqueña Negra de 620ml.', rating: '⭐⭐⭐⭐☆ (4.0)', category: 'category3', colors: [] },
    { id: 24, name: 'CUSQUEÑA TRIGO BOTELLA 620ML 12UND', price: 50.00, image: 'https://lh5.googleusercontent.com/p/AF1QipM4Nx30hCWjzmP-xBj8g25xnOPTdyGnaYQh3w7Z=w1000-h1000-p-k-no', description: 'Pack de 12 botellas de Cusqueña Trigo de 620ml.', rating: '⭐⭐⭐⭐☆ (4.1)', category: 'category3', colors: [] },
    { id: 25, name: 'CUSQUEÑA TRIGO LATA 355ML 6UND', price: 55.00, image: 'https://lh5.googleusercontent.com/p/AF1QipO4iyindkHDjnUINGJQq6qvPhbwKopod8HAqpCk=w1000-h1000-p-k-no', description: 'Pack de 6 latas de Cusqueña Trigo de 355ml.', rating: '⭐⭐⭐☆☆ (3.8)', category: 'category3', colors: [] },
    { id: 26, name: 'CORONA BOTELLA 355ML 6UND', price: 36.00, image: 'https://lh5.googleusercontent.com/p/AF1QipMKukYDijPnCrcbfRTUVW5c8DPfagwxBg5C4P_A=w1000-h1000-p-k-no', description: 'Pack de 6 botellas de Corona de 355ml.', rating: '⭐⭐⭐⭐☆ (4.0)', category: 'category4', colors: [] },
    { id: 27, name: 'CORONA BOTELLA 355ML 12UND', price: 70.00, image: 'https://lh5.googleusercontent.com/p/AF1QipMKukYDijPnCrcbfRTUVW5c8DPfagwxBg5C4P_A=w1000-h1000-p-k-no', description: 'Pack de 12 botellas de Corona de 355ml.', rating: '⭐⭐⭐⭐☆ (4.2)', category: 'category4', colors: [] }
];

function updateCartCount() {
    const cartCount = cart.reduce((sum, item) => sum + item.quantity, 0);
    document.getElementById('cart-count').textContent = cartCount;
}

function updateCart() {
    const cartItems = document.getElementById('cart-items');
    cartItems.innerHTML = '';
    let total = 0;

 cart.forEach(item => {
        total += item.price * item.quantity;
        const cartItem = document.createElement('div');
        cartItem.className = 'cart-item';
        cartItem.innerHTML = `
<div class="product-info">
                <img src="${item.image}" alt="${item.name}">
                <div class="product-details">
                    <h3>${item.name}</h3>
                    <p>Color: ${item.color || 'N/A'}</p>
                    <p>Precio: S/ ${item.price.toFixed(2)}</p>
                    <p>Cantidad: ${item.quantity}</p>
                </div>
            </div>
            <div class="actions">
                <button onclick="changeQuantity(${item.id}, '${item.color}', -1)">-</button>
                <button onclick="changeQuantity(${item.id}, '${item.color}', 1)">+</button>
                <button onclick="removeFromCart(${item.id}, '${item.color}')">Eliminar</button>
            </div>
        `;
        cartItems.appendChild(cartItem);
    });

 document.getElementById('cart-total').textContent = `Total: S/ ${total.toFixed(2)}`;
    updateCartCount();
}

function addToCart(productId, quantity, color = null) {
    const product = products.find(p => p.id === productId);
    if (!product) return;

const existingItem = cart.find(item => item.id === productId && item.color === color);
    if (existingItem) {
        existingItem.quantity += quantity;
    } else {
        cart.push({
            id: productId,
            name: product.name,
            price: product.price,
            image: product.image,
            quantity: quantity,
            color: color
        });
    }
    updateCart();
}

function removeFromCart(productId, color) {
    cart = cart.filter(item => !(item.id === productId && item.color === color));
    updateCart();
}

function changeQuantity(productId, color, change) {
    const item = cart.find(item => item.id === productId && item.color === color);
    if (item) {
        item.quantity += change;
        if (item.quantity <= 0) {
            removeFromCart(productId, color);
        } else {
            updateCart();
        }
    }
}

function openProductModal(productId) {
    const product = products.find(p => p.id === productId);
    if (!product) return;

currentProduct = product;
    currentColor = product.colors && product.colors.length > 0 ? product.colors[0] : null;

document.getElementById('modal-product-image').src = product.image;
    document.getElementById('modal-product-name').textContent = product.name;
    document.getElementById('modal-product-description').textContent = product.description;
    document.getElementById('modal-product-rating').textContent = product.rating;
    document.getElementById('modal-product-price').textContent = `S/ ${product.price.toFixed(2)}`;
    document.getElementById('modal-quantity').value = 1;

 const colorPalette = document.getElementById('modal-color-palette');
    colorPalette.innerHTML = '';
    if (product.colors && product.colors.length > 0) {
        product.colors.forEach(color => {
            const colorCircle = document.createElement('span');
            colorCircle.className = 'color-circle';
            colorCircle.style.backgroundColor = color;
            colorCircle.title = color;
            if (color === currentColor) colorCircle.classList.add('selected');
            colorCircle.addEventListener('click', () => {
                document.querySelectorAll('#modal-color-palette .color-circle').forEach(c => c.classList.remove('selected'));
                colorCircle.classList.add('selected');
                currentColor = color;
            });
            colorPalette.appendChild(colorCircle);
        });
    }

const modal = document.getElementById('product-modal');
    modal.style.display = 'flex';
    history.pushState({ modal: 'product' }, '', '#product');
}

function closeProductModal() {
    document.getElementById('product-modal').style.display = 'none';
}

function filterProducts(category) {
    currentCategory = category;
    const productsContainer = document.getElementById('products');
    productsContainer.innerHTML = '';
    document.querySelectorAll('.category').forEach(cat => cat.classList.remove('active'));
    document.querySelector(`.category[onclick="filterProducts('${category}')"]`).classList.add('active');

const filteredProducts = products.filter(p => p.category === category);
    filteredProducts.forEach(product => {
        const productItem = document.createElement('div');
        productItem.className = `product-item ${product.category}`;
        productItem.innerHTML = `
<div class="badge-offer">Oferta</div>
            <img src="${product.image}" alt="${product.name}">
            <div class="product-info">
                <h3>${product.name}</h3>
                <p class="description">${product.description}</p>
                <div class="rating">${product.rating}</div>
                <p class="price">S/ ${product.price.toFixed(2)}</p>
                <div class="color-palette">
                    ${product.colors && product.colors.length > 0 ? product.colors.map(color => `<span class="color-circle" style="background-color: ${color};" title="${color}"></span>`).join('') : ''}
                </div>
                <button class="btn-add-cart" data-id="${product.id}" data-name="${product.name}" data-price="${product.price}">Agregar al carrito</button>
            </div>
        `;
        productsContainer.appendChild(productItem);
    });

document.querySelectorAll('.btn-add-cart').forEach(button => {
        button.addEventListener('click', () => {
            const productId = parseInt(button.getAttribute('data-id'));
            openProductModal(productId);
        });
    });
}

function showAllProducts() {
    const allProductsContainer = document.getElementById('all-products-container');
    allProductsContainer.innerHTML = '';

const filteredProducts = products.filter(p => {
        return document.getElementById('all-products-search').value === '' || p.name.toLowerCase().includes(document.getElementById('all-products-search').value.toLowerCase());
    });

 filteredProducts.forEach(product => {
        const productItem = document.createElement('div');
        productItem.className = `product-item ${product.category}`;
        productItem.innerHTML = `
 <div class="badge-offer">Oferta</div>
            <img src="${product.image}" alt="${product.name}">
            <div class="product-info">
                <h3>${product.name}</h3>
                <p class="description">${product.description}</p>
                <div class="rating">${product.rating}</div>
                <p class="price">S/ ${product.price.toFixed(2)}</p>
                <div class="color-palette">
                    ${product.colors && product.colors.length > 0 ? product.colors.map(color => `<span class="color-circle" style="background-color: ${color};" title="${color}"></span>`).join('') : ''}
                </div>
                <button class="btn-add-cart" data-id="${product.id}" data-name="${product.name}" data-price="${product.price}">Agregar al carrito</button>
            </div>
        `;
        allProductsContainer.appendChild(productItem);
    });

document.querySelectorAll('#all-products-container .btn-add-cart').forEach(button => {
        button.addEventListener('click', () => {
            const productId = parseInt(button.getAttribute('data-id'));
            openProductModal(productId);
        });
    });

 const modal = document.getElementById('all-products-modal');
    modal.style.display = 'block';
    history.pushState({ modal: 'all-products' }, '', '#all-products');
}

function closeAllProductsModal() {
    document.getElementById('all-products-modal').style.display = 'none';
}

function showBoleta() {
    const boletaItems = document.getElementById('boleta-items');
    boletaItems.innerHTML = '';
    let total = 0;

 cart.forEach(item => {
        total += item.price * item.quantity;
        const boletaItem = document.createElement('div');
        boletaItem.className = 'cart-item';
        boletaItem.innerHTML = `
 <div class="product-info">
                <img src="${item.image}" alt="${item.name}">
                <div class="product-details">
                    <h3>${item.name}</h3>
                    <p>Color: ${item.color || 'N/A'}</p>
                    <p>Precio: S/ ${item.price.toFixed(2)}</p>
                    <p>Cantidad: ${item.quantity}</p>
                </div>
            </div>
        `;
        boletaItems.appendChild(boletaItem);
    });

document.getElementById('boleta-total').textContent = `Total: S/ ${total.toFixed(2)}`;
    document.getElementById('boleta-modal').style.display = 'flex';
    history.pushState({ modal: 'boleta' }, '', '#boleta');
}

function closeBoletaModal() {
    document.getElementById('boleta-modal').style.display = 'none';
}

function downloadBoleta() {
    const boletaModal = document.getElementById('boleta-modal');
    html2canvas(boletaModal, { scale: 2 }).then(canvas => {
        const link = document.createElement('a');
        link.href = canvas.toDataURL('image/png');
        link.download = 'boleta.png';
        link.click();
    });
}

document.addEventListener('DOMContentLoaded', () => {
    filterProducts(currentCategory);

 document.getElementById('cart-button').addEventListener('click', () => {
        document.getElementById('cart').style.display = 'block';
    });

 document.getElementById('viewAllBtn').addEventListener('click', showAllProducts);

document.getElementById('close-product-modal').addEventListener('click', closeProductModal);

document.getElementById('close-all-products-modal').addEventListener('click', closeAllProductsModal);

 document.getElementById('modal-quantity-decrease').addEventListener('click', () => {
        const quantityInput = document.getElementById('modal-quantity');
        let quantity = parseInt(quantityInput.value);
        if (quantity > 1) {
            quantityInput.value = quantity - 1;
        }
    });

document.getElementById('modal-quantity-increase').addEventListener('click', () => {
        const quantityInput = document.getElementById('modal-quantity');
        let quantity = parseInt(quantityInput.value);
        quantityInput.value = quantity + 1;
    });

document.getElementById('modal-add-to-cart').addEventListener('click', () => {
        const quantity = parseInt(document.getElementById('modal-quantity').value);
        addToCart(currentProduct.id, quantity, currentColor);
        closeProductModal();
    });

document.getElementById('all-products-search').addEventListener('input', showAllProducts);

document.getElementById('order-button').addEventListener('click', () => {
        if (cart.length > 0) {
            showBoleta();
        } else {
            alert('El carrito está vacío.');
        }
    });

 document.getElementById('close-boleta-modal').addEventListener('click', closeBoletaModal);

document.getElementById('download-boleta').addEventListener('click', downloadBoleta);

 // Handle back button for modals
    window.addEventListener('popstate', (event) => {
        if (event.state && event.state.modal) {
            switch (event.state.modal) {
                case 'product':
                    closeProductModal();
                    break;
                case 'all-products':
                    closeAllProductsModal();
                    break;
                case 'boleta':
                    closeBoletaModal();
                    break;
            }
        } else {
            closeProductModal();
            closeAllProductsModal();
            closeBoletaModal();
        }
    });
});
</script>
  <b:section class='main' id='main' maxwidgets='1' name='main' showaddelement='yes'/>
</body>
</html>
