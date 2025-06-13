<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tienda de Accesorios</title>
    <link href='https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css' rel='stylesheet'/>
    <style>
        :root {
            --primary: #ff5722;
            --primary-dark: #e64a19;
            --secondary: #d81b60;
            --secondary-dark: #ad1457;
        }
        
 * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
    body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f9f9f9;
            color: #333;
            padding-bottom: 60px;
        }
        
        /* Header styles */
    .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 20px;
            border-bottom: 1px solid #ddd;
            width: 100%;
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
            color: var(--secondary);
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
            background: var(--secondary);
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
            border: 2px solid var(--primary);
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
            font-size: 0.9rem;
        }
        
    .product-info p.price {
            margin: 0;
            font-size: 18px;
            color: var(--primary);
            font-weight: 700;
        }
        
   .btn-add-cart {
            margin-top: 12px;
            background-color: var(--primary);
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
            background-color: var(--primary-dark);
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
            border-color: var(--primary);
        }
        
    #modal-color-palette .color-circle.selected {
            outline: 3px solid var(--primary);
            transform: scale(1.3);
            border-color: var(--primary);
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
            background-color: var(--primary);
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
            background-color: var(--primary-dark);
        }
        
    #cart-button {
            position: fixed;
            top: 20px;
            right: 20px;
            background-color: var(--primary);
            color: white;
            padding: 15px;
            border-radius: 50%;
            cursor: pointer;
            z-index: 2000;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            font-size: 24px;
        }
        
   #cart-button:hover {
            background-color: var(--primary-dark);
        }
        
        /* Product modal styles */
    #product-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 3000;
            align-items: center;
            justify-content: center;
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
        
   .modal-content .price {
            font-weight: bold;
            margin: 10px 0;
            font-size: 1.2em;
            color: var(--secondary);
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
            border: 2px solid var(--secondary);
        }
        
   .modal-content .quantity {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            margin: 15px 0;
        }
        
   .modal-content .quantity-btn {
            background: var(--secondary);
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
            background: var(--secondary-dark);
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
            background: var(--secondary);
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
            background: var(--secondary-dark);
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
            
    .section-title {
                font-size: 1.5rem;
            }
        }
        
        /* Color indicator in cart */
    .color-indicator {
            display: inline-block;
            width: 15px;
            height: 15px;
            border-radius: 50%;
            margin-left: 5px;
            border: 1px solid #ccc;
            vertical-align: middle;
        }
</style>
</head>
<body>
    <header class='header'>
        <div class='logo'>
            <img alt='Logo de la tienda' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUOK1y_heZD6_UmmHTc9KTq4o6s2AzES1vSi6W5i0WvonBd3-Ts-DXS0eKOqtgT_1e5e4H_NGSezIvujiKdxxOEcYgeTap-tfwuQItGSZrinwaFKubdFlg-4PmJQ2UGe-Pj7rcdWiYhqMPw=w1500-h1000-p-k-no' style='width: 150px; height: auto;'/>
        </div>
        <nav>
            <ul>
                <li><a href='#'>Inicio</a></li>
                <li><a href='#'>Productos</a></li>
                <li><a href='#'>Ofertas</a></li>
                <li><a href='#'>Contacto</a></li>
            </ul>
        </nav>
        <div class='header-icons'>
            <div class='cart-icon' onclick='toggleCart()'>
                🛒
                <span class='cart-count'>0</span>
            </div>
        </div>
    </header>

<section class='carousel slide' data-ride='carousel' id='carouselExampleIndicators'>
        <div class='carousel-inner'>
            <div class='carousel-item active'>
                <img alt='Promoción 1' class='d-block w-100' src='https://pe.todomoda.com/media/wysiwyg/TM_DISNEY_STITCH_-_BANNERS_Desk_new_1.jpg'/>
            </div>
            <div class='carousel-item'>
                <img alt='Promoción 2' class='d-block w-100' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUd2bofobsLtUl3qONXRSiTNou1a9W74yTaVYEr6h64PAuOOqQ-g_w6Ifs8arhOVjWboOrUFEcEDZlmtSBZkgS1YjEnSIw1f3w4IZRdMBwxibVChvNz2c93C78bOxNsx68MuBmN-4iYNCg=w2000-h2000-p-k-no'/>
            </div>
        </div>
        <div aria-label='Ver todos los productos' class='banner-text' id='viewAllBtn' role='button'>VER TODO</div>
        <div class='dots'></div>
        <a class='carousel-control-prev' data-slide='prev' href='#carouselExampleIndicators' role='button'>
            <span aria-hidden='true' class='carousel-control-prev-icon'></span>
            <span class='sr-only'>Previous</span>
        </a>
        <a class='carousel-control-next' data-slide='next' href='#carouselExampleIndicators' role='button'>
            <span aria-hidden='true' class='carousel-control-next-icon'></span>
            <span class='sr-only'>Next</span>
        </a>
    </section>

<section class='categories'>
        <div class='category active' onclick='filterProducts("Ganchos")'>
            <div class='category-image'>
                <img alt='Ganchos' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUGuPXaSC1mPGUKkOYa5z7JyvELvbIy0B4-WtB3tMHIKm2D6Sbg1cTWwU0MsxRJR_5lKb5t1MnVOStZk-tNPdUudQ6-h7M7ueR4l8N5IgmuOrhlNRMi0B_uohBDRomdzQUIHP7y244Zc150=w1024-h1024-p-k-no'/>
            </div>
            <div class='category-title'>Ganchos</div>
        </div>
        <div class='category' onclick='filterProducts("GanchosNiñas")'>
            <div class='category-image'>
                <img alt='Ganchos Niñas' src='https://lh3.googleusercontent.com/gps-cs/AIky0YUDER3L7ISerfG6uiIU8ISdgKkibO-SXwGGNL1azb_TJ0qYIN3T7LsJyU-qc9-kQtucnOkLr5rPYtWt0fW0UL8-7RDD46bg_0JnGLkD8RSfQvGydDvq6L_ZLBoj4hnIhwHB3CEx1fPtJ58O=w1024-h1024-p-k-no'/>
            </div>
            <div class='category-title'>Ganchos Niñas</div>
        </div>
        <div class='category' onclick='filterProducts("lager")'>
            <div class='category-image'>
                <img alt='Cerveza Cusqueña' src='https://lh5.googleusercontent.com/p/AF1QipPTv840Ia5cUZM77OFrOKfiEpKJgbf_5bX-50WC=w1000-h1000-p-k-no'/>
            </div>
            <div class='category-title'>lager</div>
        </div>
        <div class='category' onclick='filterProducts("category4")'>
            <div class='category-image'>
                <img alt='Cerveza Corona' src='https://lh5.googleusercontent.com/p/AF1QipMKukYDijPnCrcbfRTUVW5c8DPfagwxBg5C4P_A=w1000-h1000-p-k-no'/>
            </div>
            <div class='category-title'>Corona</div>
        </div>
    </section>

<main>
        <section class='products-container' id='products'></section>
    </main>

    <!-- Product Modal -->
 <div id='product-modal' style='display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.7); z-index:3000; align-items:center; justify-content:center;'>
        <div style='background:#fff; border-radius:10px; max-width:400px; width:90%; padding:20px; position:relative; box-sizing:border-box;'>
            <button id='close-product-modal' style='position:absolute; top:10px; right:15px; font-size:20px; background:none; border:none; cursor:pointer;'>&#10006;</button>
            <img alt='Producto' id='modal-product-image' src='' style='width:100%; height:auto; border-radius:10px; margin-bottom:15px;'/>
            <h3 id='modal-product-name' style='margin-bottom:10px;'></h3>
            <p id='modal-product-description' style='margin-bottom:10px; font-size:14px; color:#555;'></p>
            <p id='modal-product-price' style='font-weight:bold; font-size:18px; margin-bottom:15px;'></p>
            <div aria-label='Paleta de colores del producto' class='color-palette' id='modal-product-colors' style='margin-bottom:15px; display:flex; justify-content:center; gap:5px; cursor:pointer;'></div>
            <div style='display:flex; align-items:center; gap:10px; margin-bottom:15px; justify-content:center;'>
                <button id='modal-quantity-decrease' style='width:30px; height:30px; cursor:pointer;'>-</button>
                <input id='modal-quantity' readonly='readonly' style='width:40px; text-align:center; pointer-events:none;' type='text' value='1'/>
                <button id='modal-quantity-increase' style='width:30px; height:30px; cursor:pointer;'>+</button>
            </div>
            <button id='modal-add-to-cart' style='width:100%; padding:10px; background:#ff5722; color:#fff; border:none; border-radius:10px; cursor:pointer;'>Agregar al carrito</button>
        </div>
    </div>

    <!-- Modal todos los productos -->
 <div id='all-products-modal' style='display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:#f9f9f9; z-index:3000; overflow-y:auto;'>
        <div style='background:#f9f9f9; width:100%; max-width:1200px; min-height:100vh; padding:20px; box-sizing:border-box; margin:0 auto;'>
            <button id='close-all-products-modal' style='position:fixed; top:10px; right:15px; font-size:20px; background:none; border:none; cursor:pointer; z-index:3100;'>&#10006;</button>
            <h2 style='font-size:24px; margin-bottom:20px; color:#333; text-align:center;'>Todos los Productos</h2>
            <input id='all-products-search' placeholder='Buscar producto por nombre...' type='text' style='width:100%; padding:8px; margin-bottom:20px; border-radius:8px; border:1px solid #ddd; box-sizing:border-box;'/>
            <section class='products-container' id='all-products-container'></section>
        </div>
    </div>

    <!-- Carrito -->
<section id='cart' style='display:none; position:fixed; top:0; right:0; width:100%; height:100%; background: white; background-size:cover; background-repeat:no-repeat; background-position:center; box-shadow:-5px 0px 15px rgba(0, 0, 0, 0.1); z-index:1000; padding:0; overflow-y:auto;'>
        <h2 style='font-size:24px; margin-bottom:20px; color:#333; text-align:center;'>Carrito de Compras</h2>
        <div style='margin:10px 0; text-align:center;'>
            <input id='client-name' placeholder='Nombre del cliente' style='width:90%; padding:8px; margin:5px auto; display:block; border:1px solid #ddd; border-radius:5px;' type='text'/>
            <input id='client-dni' placeholder='DNI del cliente (8 dígitos)' style='width:90%; padding:8px; margin:5px auto; display:block; border:1px solid #ddd; border-radius:5px;' type='text'/>
        </div>
        <div id='cart-items' style='max-height:60vh; overflow-y:auto; padding: 0 20px;'></div>
        <p id='cart-total' style='font-size:22px; font-weight:bold; color:#333; margin:20px; text-align:center;'></p>
        <button id='order-button' style='width:90%; margin: 0 auto 30px; display:block; padding:15px; background-color:#ff5722; color:white; border:none; font-size:18px; border-radius:20px; cursor:pointer; transition:background-color 0.3s;'>Realizar Pedido</button>
    </section>

<div id='loading-spinner' style='display:none; position:fixed; top:50%; left:50%; transform:translate(-50%, -50%); z-index:4000; background:rgba(0,0,0,0.5); color:white; padding:20px; border-radius:10px;'>Cargando...</div>

 <script src='https://code.jquery.com/jquery-3.6.0.min.js'></script>
 <script src='https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js'></script>
 <script src='https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js'></script>

<script>
        const products = [ 
            // Ganchos
            {
                id: 1,
                name: 'Maxilazos - 5 Colores',
                category: 'Ganchos',
                price: 7.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YXdnjCFtJm5EhEvClhpsqjsYwwH2Xdqql3H45tWmgLdhiRX--KLwloCAl85SxTImNaOYYbS1MOrlGYrDwH31YoIyFBBn7KapQIKbAHVfoyNmbRBjjgmF0_SefXWn6udgSSaO19kdNtmnQBd=w2000-h2000-p-k-no',
                description: 'Vibrant and durable maxilazos with a mix of five bold colors, perfect for versatile hairstyles and adding flair to any look.',
                colors: ['#ffeb3b', '#d32f2f', '#e1bee7', '#145a32', '#d6eaf8']
            },
            {
                id: 2,
                name: 'Mini Gancho Corazón',
                category: 'Ganchos',
                price: 2.50,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YUd2bofobsLtUl3qONXRSiTNou1a9W74yTaVYEr6h64PAuOOqQ-g_w6Ifs8arhOVjWboOrUFEcEDZlmtSBZkgS1YjEnSIw1f3w4IZRdMBwxibVChvNz2c93C78bOxNsx68MuBmN-4iYNCg=w2000-h2000-p-k-no',
                description: 'Delicate heart-shaped clips in elegant neutral tones, ideal for subtle hair accents and minimalist styles.'
            },
            {
                id: 3,
                name: 'Ganchos Navideños',
                category: 'Ganchos',
                price: 4.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YV8A_P0YjCC6AIfC2B6HFvCKobK0UJZjVWMnzr6lfYPVXUk0gsszvJXojCK_ycIVH0cOD1-Qw3ICj1Bi9eLIf2TH0ZFaL14TuisJOWESznCPwqs2AAn_lgVOo2yGLhrKuG1yjgsGrWPIZ0k=w2000-h2000-p-k-no',
                description: 'Festive Christmas-themed clips in classic holiday colors, perfect for adding cheer to your seasonal hairstyles.',
                colors: ['#FFFFFF', '#FF0000', '#008000']
            },
            {
                id: 4,
                name: 'Gancho Hawaiano',
                category: 'Ganchos',
                price: 5.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YVaD4OrbInMGPZXKiKtKplaYEn2Ck-9KCl8p9FJbJIXPMWFCDw9Dd5lrbO-8FfXeJZKvIEr-K5UpFwrCnofwtR30imdZTojz2gxrHqZLSM3qody1gDhWdXAm_C4le7hQ4zKL3imga1TIh_j=w2000-h2000-p-k-no',
                description: 'Bright yellow Hawaiian-inspired clips, evoking sunny beaches and vibrant tropical vibes for a fun hairstyle.',
                colors: ['#FFD700']
            },
            {
                id: 5,
                name: 'Ganchos Acrílicos Color Celeste',
                category: 'Ganchos',
                price: 5.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YXULCa-2ZSbLgwDDlphVpkyxIs_jH2pp8AIHp25rY65c3VTGPdLnesGcrtuCiDtLbovSHvwiSUpzfWiwyle1UmqeO6d0OEvhBLqp_6k4YBo2QzMGd9aduXbKMXqGVHIB0FKSWvBYE1FNgj_=w2000-h2000-p-k-no',
                description: 'Lightweight sky blue and white acrylic clips, offering a fresh, modern look for everyday wear.',
                colors: ['#5dade2', '#ebf5fb', '#FFFFFF']
            },
            {
                id: 6,
                name: 'Ganchos',
                category: 'Ganchos',
                price: 4.50,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YUepENF6loS0sqfXxEEZlTcAEQ7R-6iS6rmphnT9YjPc9whL2WIk8tCzVNnHDeaj6AaV3e6-k4yeUx9j6nSHq-l2Tc_t0dGMQLhBQrbdREDnxR65_tbipCAL3NCKmRQYWk5geU5V_jn3EiW=w2000-h2000-p-k-no',
                description: 'Classic brown and cream clips, perfect for a sophisticated, elegant style suitable for daily use.'
            },
            {
                id: 7,
                name: 'Ganchos Torna Sol en forma de Flor',
                category: 'Ganchos',
                price: 6.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YX2NRiy9kc9B9F5EY9kAoTjy699I8L7qzIaAFyN6ktzntZDbknG5_v1B6_JgD_hJDZQ7pAonmz2ynxpJqX4tYXVpt2EJISwaxV7Vd5er2HXevBcfzH_2KoEuxffPMG6wVLrMxkXZaJcUGxc=w2000-h2000-p-k-no',
                description: 'Iridescent flower-shaped clips with shimmering reflections, adding a unique and eye-catching touch to your style.'
            },
            {
                id: 8,
                name: 'Ganchos Kawai en forma de Flor',
                category: 'Ganchos',
                price: 4.50,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YXzdeSiF8Ekcd_sbWEkePfXIFlDCt8BeIvwjgW0_jHy1u9d3KWkRPGKY0IPp8ADAmGFn46hFm8U5vXqhoZ738QBNnwuwb-UXng4k1wKXRwyarfw7ST9PYntIH_SA_XEF0lDF6STVaLz16z2=w2000-h2000-p-k-no',
                description: 'Adorable flower-shaped clips in vibrant yellow, green, and orange, ideal for a playful, kawaii-inspired look.',
                colors: ['#FFFF66', '#CCFF00', '#FF8C00']
            },
            {
                id: 9,
                name: 'Ganchos de Flores',
                category: 'Ganchos',
                price: 5.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YUem5vYUL5I1PM57jknLifOO7yf5kSVMtMghU4lP6w0ZMUkV2L9UYoqFLTR_8PcGATvSRKyf0IVg5IYHBQzc5_aND9V8BvtQS47MAT--YXhLlrk645yFo2vaWRADuVRrnbiL5rs4ubhXvU=w2000-h2000-p-k-no',
                description: 'Melon and yellow floral clips, perfect for a romantic, summery hairstyle that\'s lightweight and comfortable.',
                colors: ['#FFB347', '#FFD700']
            },
            // GanchosNiñas
            {
                id: 14,
                name: 'Par de mini ganchitos en forma de flor',
                category: 'GanchosNiñas',
                price: 3.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YVcDqGO_EKNry0Eb-BkdsNH0V0lOhwW7AM5WEqz8IiNlbpTs2U3Io9_kt4yCGgt5haYI5RgwRDHv-LMBqc5bvmX245QMyriwIoyJyniPQH9cJJ9iCC2fC8hY06M9BU9nFd6NhCLGVGCC34N=w2000-h2000-p-k-no',
                description: 'Mini flower-shaped clips, ideal for subtle hairstyle details, especially for kids or minimalist styles.'
            },
            {
                id: 15,
                name: 'Mini ganchitos en forma de mariposa',
                category: 'GanchosNiñas',
                price: 2.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YW1eFtqiwT_PM-xOZnd2iVogh-XQVJclLEtgsh0i5wUGm9NvOCot9LJLfDmZE58abznArTin0EgjEMw3HuKeK9_9hoODK0kla3nM-GYGSvA8_xXCBmu_qiSuoHzgpSaO_2EtqXLAjnCs34l=w2000-h2000-p-k-no',
                description: 'Charming butterfly-shaped clips, adding a playful and whimsical touch to any hairstyle.'
            },
            {
                id: 16,
                name: 'Mini ganchitos',
                category: 'GanchosNiñas',
                price: 1.50,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YUgnWieVRURnUHds0U4E5FROmRmvztpc0ynONqB5wFO-tvCmbrBn0-E971IAl2YG7r7cobC9Hx-g0AbDpTP71ukEEb6n20lHQz-aPBoI5xDWtVwABfSJFIbqdRT6_YJzOT7x8uhaX-KBSLE=w2000-h2000-p-k-no',
                description: 'Small, discreet clips, perfect for securing fine strands or adding details to elaborate hairstyles.'
            },
            {
                id: 17,
                name: 'Ligas colores pasteles y fuertes',
                category: 'GanchosNiñas',
                price: 1.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YVwhLWhfaBVh3ChmdRjktxd6WCi7W6fTmz2_7TvWPHTT_-3tX1zci-DGspLNMmn3SpAYgh9RN5G_lHRBehTbWzF16lZ9CNiBbjgj5-EVSXMU3aVjCsYaPQ5Maahznx9Fi79zzSnwLxM_nkC=w2000-h2000-p-k-no',
                description: 'Durable elastic hair ties in pastel and vibrant colors, versatile for any hairstyle and comfortable for all-day wear.'
            },
            {
                id: 18,
                name: 'Colets negros',
                category: 'GanchosNiñas',
                price: 1.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YWE3Z0a1qVkSdmBI9RQzayKeT8bgvXn5RTJNXmMJjHG9uzg5VUrwt4-PKEq6AdcYPITi3LkJvKtdxDXq6PucsAOpzZGm2J8QGEYCR4Ff59f3YXXaKQ_Ww8lgm4vOYlRuyCNXxPuyWPFWf23=w2000-h2000-p-k-no',
                description: 'Versatile black hair ties, offering a firm hold for all hair types and styles, perfect for everyday use.'
            },
            {
                id: 19,
                name: 'Colets colores pasteles',
                category: 'GanchosNiñas',
                price: 1.00,
                image: 'https://lh3.googleusercontent.com/gps-cs/AIky0YVVXgYaHEulEuraO7tX6LShXlnoogs6cvwc7jryv8vOVwEt2wCEPWyj0ihUEHTjGMKv0HpL3uglAD96vZsANfdnMrLB4hRI1quw3OaPX-ewOFjUY9eF2ggyG4sMZLcBfJ8amsKoKsAgOXPG=w2000-h2000-p-k-no',
                description: 'Soft pastel hair ties, ideal for a delicate, feminine look, comfortable and easy to use for any occasion.'
            },
            // Lager
            {
                id: 13,
                name: 'Cusqueña Dorada 12-Pack 620ml',
                category: 'lager',
                price: 38.00,
                image: 'https://lh5.googleusercontent.com/p/AF1QipNoTsJrETd6q5R_4NE-3J7NFqBZ2_lDVDz_qgFP=w1000-h1000-p-k-no',
                description: 'A crisp Peruvian lager with 5% ABV, featuring a light golden hue and refreshing taste. Perfect for barbecues or casual gatherings.'
            },
            {
                id: 14,
                name: 'Cusqueña Dorada 6-Pack 355ml',
                category: 'lager',
                price: 40.00,
                image: 'https://lh5.googleusercontent.com/p/AF1QipPxFbOmsmYehzvFwrsgO7n7sYIVmGNIhbyIkTfB=w1000-h1000-p-k-no',
                description: 'A light and balanced Peruvian lager with 5% ABV, ideal for enjoying a refreshing beer anytime.'
            }
        ];

        function renderProducts(containerId = 'products') {
            const container = document.getElementById(containerId);
            let productsHTML = '';
            products.forEach(product => {
                productsHTML += `
                    <div class='product-item ${product.category}' data-id='${product.id}'>
                        <div class='badge-offer'>Oferta</div>
                        <img alt='${product.name}' src='${product.image}'/>
                        <div class='product-info'>
                            <h3>${product.name}</h3>
                            <p class='price'>S/ ${product.price.toFixed(2)}</p>
                            <button class='btn-add-cart' data-id='${product.id}' data-name='${product.name}' data-price='${product.price}'>Agregar al carrito</button>
                            ${product.colors ? `
                                <div class='color-palette'>
                                    ${product.colors.map(color => `
                                        <span class='color-circle' style='background-color: ${color};' title='${color}'/>
                                    `).join('')}
                                </div>
                            ` : ''}
                        </div>
                    </div>
                `;
            });
            container.innerHTML = productsHTML;
        }

        $(document).ready(function() {
            renderProducts();
            renderProducts('all-products-container');

            let cart = [];
            let modalQuantity = 1;
            let modalCurrentProduct = null;
            let modalSelectedColor = null;

            function formatCurrency(amount) {
                return `S/ ${parseFloat(amount).toFixed(2)}`;
            }

            function updateCart() {
                let cartItemsHtml = '';
                let total = 0;
                let itemCount = 0;
                cart.forEach(item => {
                    cartItemsHtml += `
                        <div class='cart-item'>
                            <div class='product-info'>
                                <img alt='${item.name}' src='${item.image}'/>
                                <div class='product-details'>
                                    <p style='margin: 0; font-weight: bold;'>${item.name}</p>
                                    ${item.color ? `<p style='margin: 0;'>Color: <span class='color-indicator' style='background-color: ${item.color};'></span></p>` : ''}
                                    <p style='margin: 0;'>Precio unitario: ${formatCurrency(item.price)}</p>
                                    <p style='margin: 0;'>Cantidad: ${item.quantity}</p>
                                </div>
                            </div>
                            <div class='actions'>
                                <button class='increase-quantity' data-product='${item.id}'>+</button>
                                <button class='decrease-quantity' data-product='${item.id}'>-</button>
                                <button class='remove-item' data-product='${item.id}'>🗑️ Eliminar</button>
                            </div>
                        </div>
                    `;
                    total += item.price * item.quantity;
                    itemCount += item.quantity;
                });
                $('#cart-items').html(cartItemsHtml);
                $('#cart-total').text(`Total: ${formatCurrency(total)}`);
                $('.cart-count').text(itemCount);
            }

            $(document).on('click', '.btn-add-cart', function(e) {
                e.stopPropagation();
                const productId = $(this).data('id').toString();
                const product = products.find(p => p.id.toString() === productId);
                modalCurrentProduct = product;
                modalSelectedColor = product.colors ? product.colors[0] : null;
                $('#modal-product-image').attr('src', product.image);
                $('#modal-product-name').text(product.name);
                $('#modal-product-description').text(product.description);
                $('#modal-product-price').text(`S/ ${product.price.toFixed(2)}`);
                
                // Generate color palette with data-color attribute
                $('#modal-product-colors').html(product.colors ? `
                    <div class='color-palette'>
                        ${product.colors.map((color, index) => `
                            <span class='color-circle ${index === 0 ? 'selected' : ''}' 
                                style='background-color: ${color};' 
                                data-color='${color}' 
                                title='${color}'/>
                        `).join('')}
                    </div>
                ` : '');
                
                modalQuantity = 1;
                $('#modal-quantity').val(modalQuantity);
                if ($('#all-products-modal').is(':visible')) {
                    $('#all-products-modal').css('z-index', 2000);
                    $('#product-modal').css('z-index', 3000);
                }
                $('#product-modal').fadeIn(200);
            });

            // Handle color selection in modal
            $(document).on('click', '#modal-product-colors .color-circle', function() {
                $('#modal-product-colors .color-circle').removeClass('selected');
                $(this).addClass('selected');
                modalSelectedColor = $(this).data('color');
            });

            $(document).on('click', '.product-item', function(e) {
                if ($(e.target).is('button')) return;
                const productId = $(this).data('id').toString();
                const product = products.find(p => p.id.toString() === productId);
                modalCurrentProduct = product;
                modalSelectedColor = product.colors ? product.colors[0] : null;
                $('#modal-product-image').attr('src', product.image);
                $('#modal-product-name').text(product.name);
                $('#modal-product-description').text(product.description);
                $('#modal-product-price').text(`S/ ${product.price.toFixed(2)}`);
                
                // Generate color palette with data-color attribute
                $('#modal-product-colors').html(product.colors ? `
                    <div class='color-palette'>
                        ${product.colors.map((color, index) => `
                            <span class='color-circle ${index === 0 ? 'selected' : ''}' 
                                style='background-color: ${color};' 
                                data-color='${color}' 
                                title='${color}'/>
                        `).join('')}
                    </div>
                ` : '');
                
                modalQuantity = 1;
                $('#modal-quantity').val(modalQuantity);
                if ($('#all-products-modal').is(':visible')) {
                    $('#all-products-modal').css('z-index', 2000);
                    $('#product-modal').css('z-index', 3000);
                }
                $('#product-modal').fadeIn(200);
            });

            $('#modal-quantity-increase').click(function() {
                modalQuantity++;
                $('#modal-quantity').val(modalQuantity);
            });
            
            $('#modal-quantity-decrease').click(function() {
                if (modalQuantity > 1) {
                    modalQuantity--;
                    $('#modal-quantity').val(modalQuantity);
                }
            });

            $('#viewAllBtn').click(function() {
                renderProducts('all-products-container');
                $('#all-products-modal').css('z-index', 2500).fadeIn(200);
                $('#all-products-search').val('').trigger('input');
            });

            $('#close-all-products-modal').click(function() {
                $('#all-products-modal').fadeOut(200);
                $('#all-products-search').val('');
            });

            $('#all-products-search').on('input', function() {
                const searchTerm = $(this).val().toLowerCase();
                $('#all-products-container .product-item').each(function() {
                    const productName = $(this).find('h3').text().toLowerCase();
                    $(this).toggle(productName.includes(searchTerm));
                });
            });

            $('#modal-add-to-cart').click(function() {
                if (!modalCurrentProduct) return;
                const productId = modalCurrentProduct.id.toString();
                const productName = $('#modal-product-name').text();
                const productPrice = parseFloat($('#modal-product-price').text().replace(/[^0-9\.]/g, ''));
                const productImage = $('#modal-product-image').attr('src');
                
                // Check if this product with the same color already exists in cart
                let existingProduct = cart.find(item => 
                    item.id.toString() === productId && 
                    item.color === modalSelectedColor
                );
                
                if (existingProduct) {
                    existingProduct.quantity += modalQuantity;
                } else {
                    cart.push({
                        id: productId,
                        name: productName,
                        price: productPrice,
                        quantity: modalQuantity,
                        image: productImage,
                        color: modalSelectedColor  // Store selected color
                    });
                }
                
                updateCart();
                $('#product-modal').fadeOut(200);
                if ($('#all-products-modal').css('z-index') == 2000) {
                    $('#all-products-modal').css('z-index', 2500);
                }
            });

            $('#close-product-modal').click(function() {
                $('#product-modal').fadeOut(200);
                if ($('#all-products-modal').css('z-index') == 2000) {
                    $('#all-products-modal').css('z-index', 2500);
                }
            });
            
            $('#product-modal').click(function(e) {
                if (e.target === this) {
                    $(this).fadeOut(200);
                    if ($('#all-products-modal').css('z-index') == 2000) {
                        $('#all-products-modal').css('z-index', 2500);
                    }
                }
            });

            $(document).on('click', '.increase-quantity', function() {
                const productId = $(this).data('product').toString();
                let product = cart.find(item => item.id.toString() === productId);
                if (product) {
                    product.quantity++;
                    updateCart();
                }
            });
            
            $(document).on('click', '.decrease-quantity', function() {
                const productId = $(this).data('product').toString();
                let product = cart.find(item => item.id.toString() === productId);
                if (product) {
                    product.quantity--;
                    if (product.quantity === 0) {
                        cart = cart.filter(item => item.id.toString() !== productId);
                    }
                    updateCart();
                }
            });
            
            $(document).on('click', '.remove-item', function() {
                const productId = $(this).data('product').toString();
                cart = cart.filter(item => item.id.toString() !== productId);
                updateCart();
            });

            window.toggleCart = function() {
                $('#cart').toggle();
            };

            window.filterProducts = function(category) {
                $('#all-products-search').val('');
                $('.product-item').hide();
                $(`.product-item.${category}`).show();
                $('.category').removeClass('active');
                $(`.category[onclick="filterProducts('${category}')"]`).addClass('active');
            };

            $('#order-button').click(function() {
                const clientName = $('#client-name').val().trim();
                const clientDni = $('#client-dni').val().trim();
                if (!clientName || !clientDni) {
                    alert("Por favor, complete nombre y DNI.");
                    return;
                }
                if (!/^\d{8}$/.test(clientDni)) {
                    alert("El DNI debe tener exactamente 8 dígitos.");
                    return;
                }
                if (cart.length === 0) {
                    alert("El carrito está vacío. Agregue productos antes de realizar el pedido.");
                    return;
                }

                let fecha = new Date();
                let fechaStr = fecha.toLocaleDateString();
                let horaStr = fecha.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
                let total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0);

                const enLetras = (n) => {
                    const parts = n.toFixed(2).split('.');
                    return `${Number(parts[0])} CON ${parts[1]}/100 SOLES`;
                };

                let boletaHtml = `
                    <div style='font-family: monospace; font-size: 14px; line-height: 1.4; text-align: left;'>
                        <h3 style='text-align: center; margin-bottom: 5px;'>BOLETA DE VENTA ELECTRÓNICA</h3>
                        <div style='text-align: center; margin: 15px 0;'>
                            <img id='qr-image' src='[yape-qr-image-url]' style='width: 200px; border-radius: 10px;'/>
                            <p style='margin: 5px 0; font-size: 12px;'>Paga aquí con Yape</p>
                            <p style='margin: 0; font-size: 12px;'>Jhonny David Palacios Gutierrez</p>
                        </div>
                        <p style='margin:0;'><strong>CLIENTE:</strong> ${clientName}</p>
                        <p style='margin:0;'><strong>DNI:</strong> ${clientDni}</p>
                        <p style='margin:0;'><strong>FECHA:</strong> ${fechaStr}   <strong>HORA:</strong> ${horaStr}</p>
                        <hr/>
                        <p style='margin: 0;'><strong>Cant U.M PRODUCTO P.U. TOTAL</strong></p>`;
                cart.forEach(item => {
                    boletaHtml += `
                        <p style='margin: 0;'>${item.quantity} UNIDAD ${item.name.substring(0,24)} ${formatCurrency(item.price)} ${formatCurrency(item.price * item.quantity)}</p>`;
                });
                boletaHtml += `
                        <hr/>
                        <table style='width: 100%; font-size: 14px;'>
                            <tr>
                                <td style='text-align: left;'><strong>TOTAL (S/)</strong></td>
                                <td style='text-align: right;'><strong>${formatCurrency(total)}</strong></td>
                            </tr>
                        </table>
                        <hr/>
                        <p style='margin: 0;'><strong>SON:</strong> ${enLetras(total)}</p>
                        <button id='capture-button' style='margin-top:10px; background:#FF9800; color:white; padding:10px 20px; border:none; border-radius:5px;'>📸 Capturar Imagen</button>
                        <button onclick='window.print()' style='margin-top:10px; background:#2196F3; color:white; padding:10px 20px; border:none; border-radius:5px;'>🖨 Imprimir</button>
                        <button id='confirm-purchase' style='margin-top:10px; padding:10px 20px; background-color:#4CAF50; color:white; border:none; border-radius:5px; font-size:16px;'>Confirmar Compra</button>
                    </div>`;

                const modal = document.createElement('div');
                modal.id = "boleta-modal";
                modal.style = "position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.6); display:flex; align-items:center; justify-content:center; z-index:2000;";
                modal.innerHTML = `<div style='background:white; padding:20px; border-radius:10px; max-width:400px; width:90%; max-height:80vh; overflow-y:auto;'>${boletaHtml}</div>`;
                document.body.appendChild(modal);

                $('#capture-button').click(function() {
                    $('#loading-spinner').show();
                    const contentDiv = modal.querySelector('div');
                    const prevMaxHeight = contentDiv.style.maxHeight;
                    const prevOverflow = contentDiv.style.overflowY;
                    contentDiv.style.maxHeight = 'none';
                    contentDiv.style.overflowY = 'visible';
                    html2canvas(contentDiv, {
                        useCORS: true,
                        allowTaint: false,
                        scale: 2
                    }).then(canvas => {
                        contentDiv.style.maxHeight = prevMaxHeight;
                        contentDiv.style.overflowY = prevOverflow;
                        $('#loading-spinner').hide();
                        const link = document.createElement('a');
                        link.download = 'boleta.png';
                        link.href = canvas.toDataURL('image/png');
                        link.click();
                    }).catch(error => {
                        $('#loading-spinner').hide();
                        console.error('Error al capturar:', error);
                        alert('No se pudo capturar la boleta. Por favor, intenta de nuevo.');
                    });
                });

                $('#confirm-purchase').click(function() {
                    let orderDetails = `Hola! 👋 Quiero realizar un pedido:\n\nCliente: ${clientName}\nDNI: ${clientDni}\n\nProductos:\n`;
                    cart.forEach(item => {
                        orderDetails += `${item.quantity} unidad ${item.name} - ${formatCurrency(item.price * item.quantity)}\n`;
                    });
                    orderDetails += `\nTotal: ${formatCurrency(total)}`;
                    orderDetails += `\n\nAdjuntar: (captura de boleta)📸 (pago electrónico)💳`;
                    let whatsappURL = `https://wa.me/51975842622?text=${encodeURIComponent(orderDetails)}`;
                    window.open(whatsappURL, '_blank');
                    document.body.removeChild(modal);
                    cart = [];
                    updateCart();
                    const successMsg = document.createElement('div');
                    successMsg.textContent = "✓ Mensaje de WhatsApp listo";
                    successMsg.style = "position:fixed; top:20px; right:20px; background:#4CAF50; color:white; padding:10px 20px; border-radius:5px; font-size:16px; z-index:3000;";
                    document.body.appendChild(successMsg);
                    setTimeout(() => {
                        window.location.reload();
                    }, 2000);
                });

                modal.addEventListener('click', function(e) {
                    if (e.target === modal) {
                        document.body.removeChild(modal);
                    }
                });
            });

            window.onload = function() {
                filterProducts('lager');
                updateCart();
            };
        });
    </script>
</body>
</html>
