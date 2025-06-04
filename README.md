
<html lang="es">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TodoModa - Tienda Online</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"> 
    <style>
        :root {
            --primary-color: #d81b60;
            --secondary-color: #f8bbd0;
            --dark-color: #333;
            --light-color: #f9f9f9;
            --gray-color: #e0e0e0;
            --success-color: #4caf50;
            --shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
 * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
    body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--light-color);
            color: var(--dark-color);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
    .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header mejorado */
    .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
            background-color: white;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
            flex-wrap: wrap;
        }
        
    .logo img {
            height: 60px;
            transition: transform 0.3s ease;
        }
        
    .logo:hover img {
            transform: scale(1.05);
        }
        
    nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
            margin: 0;
            padding: 0;
        }
        
    nav ul li a {
            text-decoration: none;
            color: var(--dark-color);
            font-weight: 600;
            position: relative;
            padding: 5px 0;
            transition: color 0.3s ease;
        }
        
    nav ul li a:hover {
            color: var(--primary-color);
        }
        
   nav ul li a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            transition: width 0.3s ease;
        }
        
    nav ul li a:hover::after {
            width: 100%;
        }
        
   .header-icons {
            display: flex;
            align-items: center;
            gap: 20px;
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
            background: var(--primary-color);
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
        
        /* Carousel mejorado */
    .carousel {
            position: relative;
            width: 100%;
            overflow: hidden;
            margin: 20px 0;
            border-radius: 10px;
            box-shadow: var(--shadow);
        }
        
   .slides {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }
        
    .slide-container {
            min-width: 100%;
            aspect-ratio: 16 / 9;
            position: relative;
        }
        
    .slides img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
    .banner-text {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 1.5em;
            font-weight: bold;
            color: white;
            background: rgba(0, 0, 0, 0.6);
            padding: 10px 25px;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
            backdrop-filter: blur(2px);
            text-align: center;
            z-index: 10;
        }
        
    .banner-text:hover {
            background: rgba(0, 0, 0, 0.8);
            transform: translateX(-50%) scale(1.05);
        }
        
    .carousel-controls {
            position: absolute;
            top: 50%;
            width: 100%;
            display: flex;
            justify-content: space-between;
            transform: translateY(-50%);
            padding: 0 15px;
            z-index: 10;
        }
        
    .carousel-btn {
            background: rgba(255, 255, 255, 0.7);
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 1.2rem;
            transition: all 0.3s ease;
            color: var(--dark-color);
        }
        
    .carousel-btn:hover {
            background: rgba(255, 255, 255, 0.9);
            transform: scale(1.1);
        }
        
   .dots {
            position: absolute;
            bottom: 15px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
            z-index: 10;
        }
        
    .dots span {
            width: 12px;
            height: 12px;
            background-color: rgba(255, 255, 255, 0.6);
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
    .dots span.active {
            background-color: white;
            transform: scale(1.2);
        }
        
        /* Productos mejorados */
    .section-title {
            text-align: center;
            margin: 30px 0 20px;
            font-size: 1.8rem;
            position: relative;
            padding-bottom: 10px;
        }
        
    .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: var(--primary-color);
        }
        
   .products {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 25px;
            margin: 20px 0;
        }
        
   .product {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            cursor: pointer;
        }
        
   .product:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.15);
        }
        
   .product-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background: var(--primary-color);
            color: white;
            padding: 3px 8px;
            border-radius: 3px;
            font-size: 0.8rem;
            font-weight: bold;
            z-index: 1;
        }
        
   .product-img {
            width: 100%;
            height: 220px;
            object-fit: cover;
            border-bottom: 1px solid var(--gray-color);
        }
        
    .product-info {
            padding: 15px;
        }
        
   .product-name {
            font-weight: 600;
            margin-bottom: 5px;
            font-size: 1.1rem;
            height: 45px;
            overflow: hidden;
        }
        
   .product-price {
            font-weight: bold;
            color: var(--primary-color);
            font-size: 1.2rem;
            margin: 8px 0;
        }
        
    .product-rating {
            color: #f1c40f;
            margin: 5px 0;
            font-size: 0.9rem;
        }
        
   .add-to-cart {
            width: 100%;
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }
        
   .add-to-cart:hover {
            background: #ad1457;
        }
        
        /* Model Section mejorada */
    .model-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }
        
    .model-item {
            position: relative;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            height: 300px;
        }
        
   .model-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
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
            transition: all 0.3s ease;
            width: 80%;
            max-width: 250px;
            text-align: center;
            backdrop-filter: blur(2px);
            z-index: 10;
        }
        
    .model-btn:hover {
            background: rgba(0, 0, 0, 0.9);
            transform: translateX(-50%) scale(1.05);
        }
        
        /* Footer */
   .footer {
            background: var(--dark-color);
            color: white;
            padding: 40px 0 20px;
            margin-top: 50px;
        }
        
   .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }
        
   .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
   .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background: var(--primary-color);
        }
        
   .footer-links {
            list-style: none;
        }
        
    .footer-links li {
            margin-bottom: 12px;
        }
        
   .footer-links a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
   .footer-links a:hover {
            color: white;
        }
        
   .footer-contact p {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 12px;
        }
        
    .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }
        
    .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            color: white;
            transition: all 0.3s ease;
        }
        
   .social-icons a:hover {
            background: var(--primary-color);
            transform: translateY(-3px);
        }
        
   .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            font-size: 0.9rem;
            color: #aaa;
        }
        
        /* Carrito de compras */
   .cart-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 2000;
            justify-content: flex-end;
        }
        
    .cart-content {
            background: white;
            width: 100%;
            max-width: 450px;
            height: 100%;
            padding: 20px;
            overflow-y: auto;
            transform: translateX(100%);
            transition: transform 0.4s ease;
            position: relative;
        }
        
    .cart-content.active {
            transform: translateX(0);
        }
        
   .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--gray-color);
            margin-bottom: 20px;
        }
        
    .close-cart {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-color);
        }
        
   .cart-items {
            margin-bottom: 20px;
        }
        
    .cart-item {
            display: flex;
            gap: 15px;
            padding: 15px 0;
            border-bottom: 1px solid var(--gray-color);
        }
        
    .cart-item-img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 5px;
        }
        
   .cart-item-details {
            flex: 1;
        }
        
   .cart-item-name {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
    .cart-item-price {
            color: var(--primary-color);
            font-weight: bold;
        }
        
   .cart-item-actions {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 8px;
        }
        
   .quantity-btn {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background: var(--gray-color);
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
   .remove-item {
            color: #e74c3c;
            background: none;
            border: none;
            cursor: pointer;
            margin-left: auto;
        }
        
   .cart-total {
            font-size: 1.2rem;
            font-weight: bold;
            text-align: right;
            margin: 20px 0;
        }
        
   .checkout-btn {
            width: 100%;
            background: var(--success-color);
            color: white;
            border: none;
            padding: 15px;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
    .checkout-btn:hover {
            background: #388e3c;
        }
        
   .empty-cart {
            text-align: center;
            padding: 30px 0;
            color: #777;
        }
        
        /* Sistema de modales */
   .modal-overlay {
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
            padding: 25px;
            border-radius: 10px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            position: relative;
            box-shadow: 0 5px 30px rgba(0,0,0,0.3);
            max-height: 90vh;
            overflow-y: auto;
        }
        
   .modal-content img {
            width: 100%;
            max-height: 300px;
            object-fit: contain;
            border-radius: 5px;
            margin-bottom: 15px;
        }
        
   .modal-content h3 {
            margin: 0 0 10px;
            font-size: 1.5em;
        }
        
    .modal-content .description {
            margin: 15px 0;
            font-size: 1em;
            color: #555;
        }
        
    .modal-content .rating {
            margin: 15px 0;
            color: #f1c40f;
            font-size: 1.2em;
        }
        
   .modal-content .price {
            font-weight: bold;
            margin: 15px 0;
            font-size: 1.3em;
            color: var(--primary-color);
        }
        
   .modal-content .color-palette {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin: 20px 0;
        }
        
   .modal-content .color-circle {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            border: 1px solid #ddd;
            cursor: pointer;
            transition: transform 0.2s;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
    .modal-content .color-circle.selected {
            transform: scale(1.2);
            border: 2px solid var(--primary-color);
        }
        
   .modal-content .quantity {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin: 20px 0;
        }
        
   .modal-content .quantity-btn {
            background: var(--primary-color);
            color: #fff;
            border: none;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 1.2em;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
   .modal-content .quantity-btn:hover {
            background: #ad1457;
        }
        
   .modal-content .quantity-input {
            width: 60px;
            height: 40px;
            text-align: center;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1.1em;
        }
        
   .modal-content .btn-add-cart {
            background: var(--primary-color);
            color: #fff;
            border: none;
            padding: 12px;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
            margin-top: 15px;
            font-size: 1.1em;
            font-weight: 600;
            transition: background 0.3s ease;
        }
        
   .modal-content .btn-add-cart:hover {
            background: #ad1457;
        }
        
   .modal-content .close-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5em;
            cursor: pointer;
            color: #333;
            background: none;
            border: none;
        }
        
        /* View All and Category Modals */
    .category-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 2500;
            justify-content: center;
            align-items: center;
            overflow-y: auto;
        }
        
   .category-modal-content {
            background: #fff;
            padding: 25px;
            border-radius: 10px;
            max-width: 90%;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            box-sizing: border-box;
            box-shadow: 0 5px 30px rgba(0,0,0,0.3);
        }
        
    .category-modal-content h2 {
            margin: 0 0 20px;
            font-size: 1.8em;
            text-align: center;
            color: var(--primary-color);
            padding-bottom: 10px;
            border-bottom: 2px solid var(--gray-color);
        }
        
   .search-container {
            margin: 20px 0;
            text-align: center;
        }
        
    .search-input {
            width: 80%;
            max-width: 500px;
            padding: 12px;
            border: 1px solid var(--gray-color);
            border-radius: 30px;
            font-size: 1em;
            box-shadow: var(--shadow);
        }
        
    .search-input:focus {
            outline: none;
            border-color: var(--primary-color);
        }
        
    .view-all-products, .clips-damas-products, .clips-ninas-products {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 25px;
            padding: 15px;
        }
        
    .view-all-products .product, .clips-damas-products .product, .clips-ninas-products .product {
            width: 100%;
            min-width: unset;
        }
        
    .category-modal-content .close-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5em;
            cursor: pointer;
            color: #333;
            background: none;
            border: none;
        }
        
        /* MENÚ HAMBURGUESA PARA MÓVIL */
    .menu-toggle {
            display: none;
            flex-direction: column;
            justify-content: space-around;
            width: 30px;
            height: 25px;
            cursor: pointer;
            z-index: 1000;
        }
        
   .menu-toggle span {
            height: 3px;
            width: 100%;
            background-color: var(--dark-color);
            border-radius: 10px;
            transition: all 0.3s ease;
        }
        
        /* Responsive */
        /* Media queries para móviles (compacto) */
    @media (max-width: 767px) {
            /* Menú móvil */
            .menu-toggle {
                display: flex;
            }
            
    nav {
                position: fixed;
                top: 0;
                right: -100%;
                width: 70%;
                max-width: 300px;
                height: 100vh;
                background: white;
                z-index: 999;
                padding-top: 80px;
                transition: right 0.3s ease;
                box-shadow: -5px 0 15px rgba(0,0,0,0.1);
            }
            
    nav.active {
                right: 0;
            }
            
    nav ul {
                flex-direction: column;
                padding: 20px;
                gap: 15px;
            }
            
    nav ul li a {
                padding: 10px 0;
                font-size: 1.1rem;
            }
            
    .close-menu {
                position: absolute;
                top: 20px;
                right: 20px;
                font-size: 1.5rem;
                cursor: pointer;
            }
            
            /* Header compacto */
    .header {
                padding: 10px 15px;
            }
            
    .logo img {
                height: 45px;
            }
            
            /* Carrusel más compacto */
    .carousel {
                margin: 10px 0;
            }
            
    .banner-text {
                font-size: 1.2em;
                padding: 8px 15px;
                bottom: 15px;
            }
            
            /* Productos en 1 columna */
    .products {
                grid-template-columns: 1fr;
                gap: 15px;
                margin: 10px 0;
            }
            
   .product-img {
                height: 180px;
            }
            
   .product-name {
                font-size: 1rem;
                height: auto;
            }
            
   .product-price {
                font-size: 1.1rem;
            }
            
            /* Model section en 1 columna */
   .model-section {
                grid-template-columns: 1fr;
                gap: 15px;
                margin: 20px 0;
            }
            
   .model-item {
                height: 220px;
            }
            
    .model-btn {
                font-size: 1rem;
                padding: 8px 15px;
            }
            
            /* Footer compacto */
   .footer-content {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            /* Títulos más pequeños */
   .section-title {
                font-size: 1.5rem;
                margin: 20px 0 15px;
            }
            
   .section-title::after {
                width: 60px;
            }
            
            /* Modales para móvil */
   .modal-content {
                width: 95%;
                padding: 20px;
            }
            
   .modal-content img {
                max-height: 200px;
            }
            
    .category-modal-content {
                width: 95%;
                padding: 15px;
            }
            
   .view-all-products, .clips-damas-products, .clips-ninas-products {
                grid-template-columns: 1fr;
                gap: 15px;
            }
        }
        

        /* Responsive */

    </style>
</head>
<body>
    <div class="container">
        <!-- Header mejorado -->
        <header class="header">
            <div class="logo">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YXTTJyLqUwcNn1yduyV6i82lmL4ukvEZp-ePVd_P_Wa_y1VGwXNJOPpVxro2IxUZ55xE4oEndno5MItmJf7wjkFn0RYFCLtB4bOG2AHYHrupD1pkX8cf3jOUBHNUJOFEYOrwzTGEMSJj6j8=w1000-h1000-p-k-no" alt="TodoModa Logo">
            </div>
            
   <div class="menu-toggle" id="menuToggle">
                <span></span>
                <span></span>
                <span></span>
            </div>
            
<nav id="mainNav">
                <div class="close-menu" id="closeMenu">
                    <i class="fas fa-times"></i>
                </div>
                <ul>
                    <li><a href="#"><i class="fas fa-home"></i> Inicio</a></li>
                    <li><a href="#"><i class="fas fa-tshirt"></i> Mujer</a></li>
                    <li><a href="#"><i class="fas fa-child"></i> Niñas</a></li>
                    <li><a href="#"><i class="fas fa-percent"></i> Ofertas</a></li>
                    <li><a href="#"><i class="fas fa-phone"></i> Contacto</a></li>
                </ul>
            </nav>
            
<div class="header-icons">
                <div class="search-icon">
                    <i class="fas fa-search"></i>
                </div>
                <div class="user-icon">
                    <i class="fas fa-user"></i>
                </div>
                <div class="cart-icon" id="cartIcon">
                    <i class="fas fa-shopping-cart"></i>
                    <span class="cart-count">0</span>
                </div>
            </div>
        </header>

        <!-- Carousel mejorado -->
 <div class="carousel">
            <div class="slides">
                <div class="slide-container">
                    <img src="https://pe.todomoda.com/media/wysiwyg/TM_DISNEY_STITCH_-_BANNERS_Desk_new_1.jpg" alt="Banner 1">
                </div>
                <div class="slide-container">
                    <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YUd2bofobsLtUl3qONXRSiTNou1a9W74yTaVYEr6h64PAuOOqQ-g_w6Ifs8arhOVjWboOrUFEcEDZlmtSBZkgS1YjEnSIw1f3w4IZRdMBwxibVChvNz2c93C78bOxNsx68MuBmN-4iYNCg=w2000-h2000-p-k-no" alt="Banner 2">
                </div>
            </div>
            <div class="carousel-controls">
                <button class="carousel-btn prev-btn"><i class="fas fa-chevron-left"></i></button>
                <button class="carousel-btn next-btn"><i class="fas fa-chevron-right"></i></button>
            </div>
            <div class="banner-text" id="viewAllBtn">VER TODO</div>
            <div class="dots">
                <span class="active"></span>
                <span></span>
            </div>
        </div>

        <!-- Productos destacados -->
 <h2 class="section-title">Productos Destacados</h2>
        <div class="products" id="featuredProducts">
            <!-- Los productos se insertarán dinámicamente aquí -->
        </div>

        <!-- Model Section mejorada -->
 <div class="model-section">
            <div class="model-item">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YUGuPXaSC1mPGUKkOYa5z7JyvELvbIy0B4-WtB3tMHIKm2D6Sbg1cTWwU0MsxRJR_5lKb5t1MnVOStZk-tNPdUudQ6-h7M7ueR4l8N5IgmuOrhlNRMi0B_uohBDRomdzQUIHP7y244Zc150=w1024-h1024-p-k-no" alt="Clips Damas">
                <button class="model-btn" id="clipsDamasBtn">CLIPS DAMAS</button>
            </div>
            <div class="model-item">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YUDER3L7ISerfG6uiIU8ISdgKkibO-SXwGGNL1azb_TJ0qYIN3T7LsJyU-qc9-kQtucnOkLr5rPYtWt0fW0UL8-7RDD46bg_0JnGLkD8RSfQvGydDvq6L_ZLBoj4hnIhwHB3CEx1fPtJ58O=w1024-h1024-p-k-no" alt="Clips Niñas">
                <button class="model-btn" id="clipsNinasBtn">CLIPS NIÑAS</button>
            </div>
        </div>

        <!-- Nuevos productos -->
<h2 class="section-title">Nuevos Productos</h2>
        <div class="products" id="newProducts">
            <!-- Los productos se insertarán dinámicamente aquí -->
        </div>
    </div>
    
    <!-- Footer -->
 <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>TodoModa</h3>
                    <p>Tu tienda de accesorios de moda con los mejores precios y tendencias.</p>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-tiktok"></i></a>
                        <a href="#"><i class="fab fa-pinterest"></i></a>
                    </div>
                </div>
                
 <div class="footer-column">
                     <h3>Categorías</h3>
                    <ul class="footer-links">
                        <li><a href="#">Accesorios para Damas</a></li>
                        <li><a href="#">Accesorios para Niñas</a></li>
                        <li><a href="#">Colecciones Especiales</a></li>
                        <li><a href="#">Novedades</a></li>
                        <li><a href="#">Ofertas</a></li>
                    </ul>
                </div>
                
 <div class="footer-column">
                    <h3>Enlaces Rápidos</h3>
                    <ul class="footer-links">
                        <li><a href="#">Sobre Nosotros</a></li>
                        <li><a href="#">Preguntas Frecuentes</a></li>
                        <li><a href="#">Política de Envíos</a></li>
                        <li><a href="#">Términos y Condiciones</a></li>
                        <li><a href="#">Política de Privacidad</a></li>
                    </ul>
                </div>
                
<div class="footer-column footer-contact">
                    <h3>Contacto</h3>
                    <p><i class="fas fa-map-marker-alt"></i> Av. Principal 123, Lima, Perú</p>
                    <p><i class="fas fa-phone"></i> +51 987 654 321</p>
                    <p><i class="fas fa-envelope"></i> info@todomoda.com</p>
                    <p><i class="fas fa-clock"></i> Lunes a Sábado: 9:00 AM - 8:00 PM</p>
                </div>
            </div>
            
<div class="copyright">
                <p>&copy; 2023 TodoModa. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>
    
    <!-- Carrito de compras -->
 <div class="cart-modal" id="cartModal">
        <div class="cart-content" id="cartContent">
            <div class="cart-header">
                <h2>Tu Carrito</h2>
                <button class="close-cart" id="closeCart">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
 <div class="cart-items" id="cartItems">
                <div class="empty-cart">
                    <i class="fas fa-shopping-cart fa-3x"></i>
                    <p>Tu carrito está vacío</p>
                </div>
            </div>
            
 <div class="cart-total" id="cartTotal">
                Total: S/ 0.00
            </div>
            
<button class="checkout-btn" id="checkoutBtn">
                <i class="fas fa-check"></i> Realizar Pedido
            </button>
        </div>
    </div>
    
    <!-- Modal de producto -->
<div class="modal-overlay" id="productModal">
        <div class="modal-content">
            <button class="close-btn">&times;</button>
            <img id="modalImage" alt="" src="">
            <h3 id="modalTitle"></h3>
            <p class="description" id="modalDescription"></p>
            <div class="rating" id="modalRating"></div>
            <p class="price" id="modalPrice"></p>
            <div class="color-palette" id="modalColors"></div>
            <div class="quantity">
                <button class="quantity-btn" id="decreaseQty">−</button>
                <input type="number" class="quantity-input" id="quantityInput" value="1" min="1">
                <button class="quantity-btn" id="increaseQty">+</button>
            </div>
            <button class="btn-add-cart" id="modalAddCart">Agregar al carrito</button>
        </div>
    </div>
    
    <!-- View All Products Modal -->
<div class="category-modal" id="viewAllModal">
        <div class="category-modal-content">
            <button class="close-btn">&times;</button>
            <h2>Todos los Productos</h2>
            <div class="search-container">
                <input type="text" class="search-input" id="productSearch" placeholder="Buscar productos...">
            </div>
            <div class="view-all-products" id="viewAllProducts"></div>
        </div>
    </div>
    
    <!-- Clips Damas Modal -->
 <div class="category-modal" id="clipsDamasModal">
        <div class="category-modal-content">
            <button class="close-btn">&times;</button>
            <h2>CLIPS DAMAS</h2>
            <div class="search-container">
                <input type="text" class="search-input" id="clipsDamasSearch" placeholder="Buscar en Clips Damas...">
            </div>
            <div class="clips-damas-products" id="clipsDamasProducts"></div>
        </div>
    </div>
    
    <!-- Clips Niñas Modal -->
 <div class="category-modal" id="clipsNinasModal">
        <div class="category-modal-content">
            <button class="close-btn">&times;</button>
            <h2>CLIPS NIÑAS</h2>
            <div class="search-container">
                <input type="text" class="search-input" id="clipsNinasSearch" placeholder="Buscar en Clips Niñas...">
            </div>
            <div class="clips-ninas-products" id="clipsNinasProducts"></div>
        </div>
   </div>
    
 <script>
        // Datos de productos
        const productsData = [
            // Productos destacados
            {
                id: 1,
                name: "Maxilazos - 5 Colores",
                price: 7.00,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YXdnjCFtJm5EhEvClhpsqjsYwwH2Xdqql3H45tWmgLdhiRX--KLwloCAl85SxTImNaOYYbS1MOrlGYrDwH31YoIyFBBn7KapQIKbAHVfoyNmbRBjjgmF0_SefXWn6udgSSaO19kdNtmnQBd=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐⭐☆ (4.2)",
                description: "Maxilazos coloridos, perfectos para cualquier peinado.",
                colors: [
                    {color: "#ffeb3b", title: "Amarillo"},
                    {color: "#d32f2f", title: "Rojo"},
                    {color: "#e1bee7", title: "Lila"},
                    {color: "#145a32", title: "Verde"},
                    {color: "#d6eaf8", title: "Celeste"}
                ],
                featured: true
            },
            {
                id: 2,
                name: "Mini Gancho Corazón",
                price: 2.50,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YUd2bofobsLtUl3qONXRSiTNou1a9W74yTaVYEr6h64PAuOOqQ-g_w6Ifs8arhOVjWboOrUFEcEDZlmtSBZkgS1YjEnSIw1f3w4IZRdMBwxibVChvNz2c93C78bOxNsx68MuBmN-4iYNCg=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐☆☆ (3.2)",
                description: "Ganchos en forma de corazón, ideales para looks delicados.",
                colors: [
                    {color: "#17202a", title: "Negro"},
                    {color: "#fff9c4", title: "Crema"},
                    {color: "#fdebd0", title: "Piel"},
                    {color: "#fdfefe", title: "Crema"}
                ],
                featured: true
            },
            {
                id: 3,
                name: "Ganchos Navideños",
                price: 4.00,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YV8A_P0YjCC6AIfC2B6HFvCKobK0UJZjVWMnzr6lfYPVXUk0gsszvJXojCK_ycIVH0cOD1-Qw3ICj1Bi9eLIf2TH0ZFaL14TuisJOWESznCPwqs2AAn_lgVOo2yGLhrKuG1yjgsGrWPIZ0k=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐⭐⭐ (5.0)",
                description: "Ganchos temáticos navideños para un estilo festivo.",
                colors: [
                    {color: "#FFFFFF", title: "Blanco"},
                    {color: "#FF0000", title: "Rojo"},
                    {color: "#008000", title: "Verde"}
                ],
                featured: true
            },
            {
                id: 4,
                name: "Gancho Hawaiano",
                price: 5.00,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YVaD4OrbInMGPZXKiKtKplaYEn2Ck-9KCl8p9FJbJIXPMWFCDw9Dd5lrbO-8FfXeJZKvIEr-K5UpFwrCnofwtR30imdZTojz2gxrHqZLSM3qody1gDhWdXAm_C4le7hQ4zKL3imga1TIh_j=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐⭐☆ (4.0)",
                description: "Ganchos hawaianos vibrantes para un look tropical.",
                colors: [
                    {color: "#FFD700", title: "Amarillo"}
                ],
                featured: true
            },
            // Nuevos productos
            {
                id: 5,
                name: "Ganchos Acrílicos Color Celeste",
                price: 5.00,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YXULCa-2ZSbLgwDDlphVpkyxIs_jH2pp8AIHp25rY65c3VTGPdLnesGcrtuCiDtLbovSHvwiSUpzfWiwyle1UmqeO6d0OEvhBLqp_6k4YBo2QzMGd9aduXbKMXqGVHIB0FKSWvBYE1FNgj_=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐⭐☆ (4.0)",
                description: "Ganchos acrílicos elegantes en tonos celestes.",
                colors: [
                    {color: "#5dade2", title: "Celeste"},
                    {color: "#ebf5fb", title: "Agua"},
                    {color: "#FFFFFF", title: "Blanco"}
                ],
                new: true
            },
            {
                id: 6,
                name: "Ganchos",
                price: 4.50,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YUepENF6loS0sqfXxEEZlTcAEQ7R-6iS6rmphnT9YjPc9whL2WIk8tCzVNnHDeaj6AaV3e6-k4yeUx9j6nSHq-l2Tc_t0dGMQLhBQrbdREDnxR65_tbipCAL3NCKmRQYWk5geU5V_jn3EiW=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐☆☆ (3.1)",
                description: "Ganchos clásicos para un estilo minimalista.",
                colors: [
                    {color: "#8d6e63", title: "Marrón"},
                    {color: "#fef9e7", title: "Crema"}
                ],
                new: true
            },
            {
                id: 7,
                name: "Ganchos Torna Sol en forma de Flor",
                price: 6.00,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YX2NRiy9kc9B9F5EY9kAoTjy699I8L7qzIaAFyN6ktzntZDbknG5_v1B6_JgD_hJDZQ7pAonmz2ynxpJqX4tYXVpt2EJISwaxV7Vd5er2HXevBcfzH_2KoEuxffPMG6wVLrMxkXZaJcUGxc=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐⭐☆ (4.1)",
                description: "Ganchos en forma de flor con diseño inspirado en el sol.",
                colors: [],
                new: true
            },
            {
                id: 8,
                name: "Ganchos Kawai en forma de Flor",
                price: 4.50,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YXzdeSiF8Ekcd_sbWEkePfXIFlDCt8BeIvwjgW0_jHy1u9d3KWkRPGKY0IPp8ADAmGFn46hFm8U5vXqhoZ738QBNnwuwb-UXng4k1wKXRwyarfw7ST9PYntIH_SA_XEF0lDF6STVaLz16z2=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐☆☆ (3.5)",
                description: "Ganchos kawai con diseño floral, ideales para niños.",
                colors: [
                    {color: "#FFFF66", title: "Amarillo"},
                    {color: "#CCFF00", title: "Verde"},
                    {color: "#FF8C00", title: "Anaranjado"}
                ],
                new: true
            },
            // Clips Damas
            {
                id: 9,
                name: "Ganchos de Flores",
                price: 5.00,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YUem5vYUL5I1PM57jknLifOO7yf5kSVMtMghU4lP6w0ZMUkV2L9UYoqFLTR_8PcGATvSRKyf0IVg5IYHBQzc5_aND9V8BvtQS47MAT--YXhLlrk645yFo2vaWRADuVRrnbiL5rs4ubhXvU=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐⭐☆ (4.0)",
                description: "Ganchos florales en tonos cálidos para un look vibrante.",
                colors: [
                    {color: "#FFB347", title: "Melón"},
                    {color: "#FFD700", title: "Amarillo"}
                ],
                category: "damas"
            },
            // Clips Niñas
            {
                id: 14,
                name: "Par de mini ganchitos en forma de flor",
                price: 3.00,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YVcDqGO_EKNry0Eb-BkdsNH0V0lOhwW7AM5WEqz8IiNlbpTs2U3Io9_kt4yCGgt5haYI5RgwRDHv-LMBqc5bvmX245QMyriwIoyJyniPQH9cJJ9iCC2fC8hY06M9BU9nFd6NhCLGVGCC34N=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐⭐☆ (4.0)",
                description: "Mini ganchitos florales para destacar tu peinado.",
                colors: [],
                category: "ninas"
            },
            {
                id: 15,
                name: "Mini ganchitos en forma de mariposa",
                price: 2.00,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YW1eFtqiwT_PM-xOZnd2iVogh-XQVJclLEtgsh0i5wUGm9NvOCot9LJLfDmZE58abznArTin0EgjEMw3HuKeK9_9hoODK0kla3nM-GYGSvA8_xXCBmu_qiSuoHzgpSaO_2EtqXLAjnCs34l=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐☆☆ (3.5)",
                description: "Ganchitos en forma de mariposa, perfectos para peinados infantiles.",
                colors: [],
                category: "ninas"
            },
            {
                id: 16,
                name: "Mini ganchitos",
                price: 1.50,
                image: "https://lh3.googleusercontent.com/gps-cs/AIky0YUgnWieVRURnUHds0U4E5FROmRmvztpc0ynONqB5wFO-tvCmbrBn0-E971IAl2YG7r7cobC9Hx-g0AbDpTP71ukEEb6n20lHQz-aPBoI5xDWtVwABfSJFIbqdRT6_YJzOT7x8uhaX-KBSLE=w2000-h2000-p-k-no",
                rating: "⭐⭐⭐☆☆ (3.3)",
                description: "Mini ganchitos versátiles para cualquier ocasión.",
                colors: [],
                category: "ninas"
            }
        ];

        // Generar productos en la página
        function generateProducts(products, containerId) {
            const container = document.getElementById(containerId);
            container.innerHTML = '';
            
            products.forEach(product => {
                const productElement = document.createElement('div');
                productElement.className = 'product';
                productElement.setAttribute('data-id', product.id);
                productElement.setAttribute('data-colors', JSON.stringify(product.colors));
                productElement.setAttribute('data-rating', product.rating);
                productElement.setAttribute('data-description', product.description);
                
                let badge = '';
                if (product.featured) {
                    badge = '<span class="product-badge">Destacado</span>';
                } else if (product.new) {
                    badge = '<span class="product-badge">Nuevo</span>';
                }
                
                productElement.innerHTML = `
                    ${badge}
                    <img src="${product.image}" alt="${product.name}" class="product-img">
                    <div class="product-info">
                        <h3 class="product-name">${product.name}</h3>
                        <div class="product-rating">${product.rating}</div>
                        <p class="product-price">S/ ${product.price.toFixed(2)}</p>
                        <button class="add-to-cart">
                            <i class="fas fa-shopping-cart"></i> Agregar al carrito
                        </button>
                    </div>
                `;
                
                container.appendChild(productElement);
            });
            
            // Asignar eventos a los productos
            document.querySelectorAll(`#${containerId} .product`).forEach(product => {
                product.addEventListener('click', (e) => {
                    if (e.target.classList.contains('add-to-cart')) {
                        e.stopPropagation();
                        addToCart(product);
                    } else {
                        openProductModal(product);
                    }
                });
            });
        }
        
        // Inicializar productos
        const featuredProducts = productsData.filter(p => p.featured);
        const newProducts = productsData.filter(p => p.new);
        
        generateProducts(featuredProducts, 'featuredProducts');
        generateProducts(newProducts, 'newProducts');
        
        // Carrito de compras
        let cart = [];
        const cartIcon = document.getElementById('cartIcon');
        const cartModal = document.getElementById('cartModal');
        const cartContent = document.getElementById('cartContent');
        const closeCart = document.getElementById('closeCart');
        const cartItems = document.getElementById('cartItems');
        const cartTotal = document.getElementById('cartTotal');
        const checkoutBtn = document.getElementById('checkoutBtn');
        
        // Abrir carrito
        cartIcon.addEventListener('click', () => {
            cartModal.style.display = 'flex';
            setTimeout(() => {
                cartContent.classList.add('active');
            }, 10);
        });
        
        // Cerrar carrito
        closeCart.addEventListener('click', () => {
            cartContent.classList.remove('active');
            setTimeout(() => {
                cartModal.style.display = 'none';
            }, 300);
        });
        
        // Cerrar al hacer clic fuera del carrito
        cartModal.addEventListener('click', (e) => {
            if (e.target === cartModal) {
                cartContent.classList.remove('active');
                setTimeout(() => {
                    cartModal.style.display = 'none';
                }, 300);
            }
        });
        
        // Añadir producto al carrito
        function addToCart(productElement) {
            const id = parseInt(productElement.getAttribute('data-id'));
            const product = productsData.find(p => p.id === id);
            
            if (!product) return;
            
            // Verificar si el producto ya está en el carrito
            const existingItem = cart.find(item => item.id === id);
            
            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({
                    id: product.id,
                    name: product.name,
                    price: product.price,
                    image: product.image,
                    quantity: 1
                });
            }
            
            updateCart();
            showAddedNotification(product.name);
        }
        
        // Mostrar notificación de producto añadido
        function showAddedNotification(productName) {
            const notification = document.createElement('div');
            notification.innerHTML = `
                <div style="position: fixed; bottom: 20px; right: 20px; background: var(--success-color); color: white; padding: 15px 20px; border-radius: 5px; display: flex; align-items: center; gap: 10px; z-index: 3000; box-shadow: var(--shadow);">
                    <i class="fas fa-check-circle"></i>
                    <span>¡${productName} añadido al carrito!</span>
                </div>
            `;
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.remove();
            }, 3000);
        }
        
        // Actualizar carrito
        function updateCart() {
            // Actualizar contador del ícono
            const cartCount = document.querySelector('.cart-count');
            const totalItems = cart.reduce((total, item) => total + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            // Actualizar lista de productos en el carrito
            if (cart.length === 0) {
                cartItems.innerHTML = `
                    <div class="empty-cart">
                        <i class="fas fa-shopping-cart fa-3x"></i>
                        <p>Tu carrito está vacío</p>
                    </div>
                `;
                cartTotal.textContent = 'Total: S/ 0.00';
                checkoutBtn.style.display = 'none';
                return;
            }
            
            checkoutBtn.style.display = 'block';
            
            cartItems.innerHTML = '';
            let total = 0;
            
            cart.forEach((item, index) => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                
                const cartItemElement = document.createElement('div');
                cartItemElement.classList.add('cart-item');
                cartItemElement.innerHTML = `
                    <img src="${item.image}" alt="${item.name}" class="cart-item-img">
                    <div class="cart-item-details">
                        <h3 class="cart-item-name">${item.name}</h3>
                        <p class="cart-item-price">S/ ${item.price.toFixed(2)}</p>
                        <div class="cart-item-actions">
                            <button class="quantity-btn decrease" data-index="${index}">-</button>
                            <span>${item.quantity}</span>
                            <button class="quantity-btn increase" data-index="${index}">+</button>
                            <button class="remove-item" data-index="${index}">
                                <i class="fas fa-trash"></i>
                            </button>
                        </div>
                    </div>
                `;
                
                cartItems.appendChild(cartItemElement);
            });
            
            cartTotal.textContent = `Total: S/ ${total.toFixed(2)}`;
            
            // Añadir event listeners para los botones de cantidad
            document.querySelectorAll('.decrease').forEach(button => {
                button.addEventListener('click', () => {
                    const index = button.getAttribute('data-index');
                    if (cart[index].quantity > 1) {
                        cart[index].quantity--;
                    } else {
                        cart.splice(index, 1);
                    }
                    updateCart();
                });
            });
            
            document.querySelectorAll('.increase').forEach(button => {
                button.addEventListener('click', () => {
                    const index = button.getAttribute('data-index');
                    cart[index].quantity++;
                    updateCart();
                });
            });
            
            document.querySelectorAll('.remove-item').forEach(button => {
                button.addEventListener('click', () => {
                    const index = button.getAttribute('data-index');
                    cart.splice(index, 1);
                    updateCart();
                });
            });
        }
        
        // Finalizar compra
        checkoutBtn.addEventListener('click', () => {
            if (cart.length === 0) return;
            
            alert(`¡Gracias por tu compra! Total: S/ ${cart.reduce((total, item) => total + (item.price * item.quantity), 0).toFixed(2)}`);
            cart = [];
            updateCart();
            cartContent.classList.remove('active');
            setTimeout(() => {
                cartModal.style.display = 'none';
            }, 300);
        });
        
        // Modal de producto
        const productModal = document.getElementById('productModal');
        const modalImage = document.getElementById('modalImage');
        const modalTitle = document.getElementById('modalTitle');
        const modalDescription = document.getElementById('modalDescription');
        const modalRating = document.getElementById('modalRating');
        const modalPrice = document.getElementById('modalPrice');
        const modalColors = document.getElementById('modalColors');
        const decreaseQty = document.getElementById('decreaseQty');
        const increaseQty = document.getElementById('increaseQty');
        const quantityInput = document.getElementById('quantityInput');
        const modalAddCart = document.getElementById('modalAddCart');
        const modalCloseBtn = document.querySelector('#productModal .close-btn');
        
        let selectedProduct = null;
        let selectedColor = null;
        
        function openProductModal(productElement) {
            const id = parseInt(productElement.getAttribute('data-id'));
            const product = productsData.find(p => p.id === id);
            
            if (!product) return;
            
            selectedProduct = product;
            
            modalImage.src = product.image;
            modalTitle.textContent = product.name;
            modalDescription.textContent = product.description;
            modalRating.textContent = product.rating;
            modalPrice.textContent = `S/ ${product.price.toFixed(2)}`;
            
            // Generar paleta de colores
            modalColors.innerHTML = '';
            if (product.colors.length > 0) {
                product.colors.forEach(color => {
                    const colorCircle = document.createElement('span');
                    colorCircle.className = 'color-circle';
                    colorCircle.style.backgroundColor = color.color;
                    colorCircle.title = color.title;
                    colorCircle.dataset.color = color.color;
                    
                    colorCircle.addEventListener('click', () => {
                        modalColors.querySelectorAll('.color-circle').forEach(c => c.classList.remove('selected'));
                        colorCircle.classList.add('selected');
                        selectedColor = color;
                    });
                    
                    modalColors.appendChild(colorCircle);
                });
                
                // Seleccionar el primer color por defecto
                if (product.colors.length > 0) {
                    modalColors.firstChild.click();
                }
            } else {
                modalColors.innerHTML = '<p>No hay colores disponibles</p>';
            }
            
            // Resetear cantidad
            quantityInput.value = 1;
            
            // Mostrar modal
            productModal.style.display = 'flex';
        }
        
        // Cerrar modal de producto
        modalCloseBtn.addEventListener('click', () => {
            productModal.style.display = 'none';
        });
        
        productModal.addEventListener('click', (e) => {
            if (e.target === productModal) {
                productModal.style.display = 'none';
            }
        });
        
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape' && productModal.style.display === 'flex') {
                productModal.style.display = 'none';
            }
        });
        
        // Controles de cantidad
        decreaseQty.addEventListener('click', () => {
            let qty = parseInt(quantityInput.value);
            if (qty > 1) quantityInput.value = qty - 1;
        });
        
        increaseQty.addEventListener('click', () => {
            let qty = parseInt(quantityInput.value);
            quantityInput.value = qty + 1;
        });
        
        quantityInput.addEventListener('input', () => {
            if (quantityInput.value < 1) quantityInput.value = 1;
        });
        
        // Añadir al carrito desde modal
        modalAddCart.addEventListener('click', () => {
            if (!selectedProduct) return;
            
            const quantity = parseInt(quantityInput.value);
            
            // Verificar si el producto ya está en el carrito
            const existingItem = cart.find(item => item.id === selectedProduct.id);
            
            if (existingItem) {
                existingItem.quantity += quantity;
            } else {
                cart.push({
                    id: selectedProduct.id,
                    name: selectedProduct.name,
                    price: selectedProduct.price,
                    image: selectedProduct.image,
                    quantity: quantity
                });
            }
            
            updateCart();
            showAddedNotification(selectedProduct.name);
            productModal.style.display = 'none';
        });
        
        // Modal "Ver Todo"
        const viewAllModal = document.getElementById('viewAllModal');
        const viewAllBtn = document.getElementById('viewAllBtn');
        const viewAllProductsContainer = document.getElementById('viewAllProducts');
        const viewAllCloseBtn = document.querySelector('#viewAllModal .close-btn');
        const productSearch = document.getElementById('productSearch');
        
        viewAllBtn.addEventListener('click', () => {
            generateProducts(productsData, 'viewAllProducts');
            viewAllModal.style.display = 'flex';
        });
        
        viewAllCloseBtn.addEventListener('click', () => {
            viewAllModal.style.display = 'none';
        });
        
        viewAllModal.addEventListener('click', (e) => {
            if (e.target === viewAllModal) {
                viewAllModal.style.display = 'none';
            }
        });
        
        // Búsqueda de productos
        productSearch.addEventListener('input', () => {
            const searchTerm = productSearch.value.toLowerCase();
            const filteredProducts = productsData.filter(product => 
                product.name.toLowerCase().includes(searchTerm)
            );
            generateProducts(filteredProducts, 'viewAllProducts');
        });
        
        // Modal "Clips Damas"
        const clipsDamasModal = document.getElementById('clipsDamasModal');
        const clipsDamasBtn = document.getElementById('clipsDamasBtn');
        const clipsDamasProductsContainer = document.getElementById('clipsDamasProducts');
        const clipsDamasCloseBtn = document.querySelector('#clipsDamasModal .close-btn');
        const clipsDamasSearch = document.getElementById('clipsDamasSearch');
        
        clipsDamasBtn.addEventListener('click', () => {
            const damasProducts = productsData.filter(p => p.category === "damas");
            generateProducts(damasProducts, 'clipsDamasProducts');
            clipsDamasModal.style.display = 'flex';
        });
        
        clipsDamasCloseBtn.addEventListener('click', () => {
            clipsDamasModal.style.display = 'none';
        });
        
        clipsDamasModal.addEventListener('click', (e) => {
            if (e.target === clipsDamasModal) {
                clipsDamasModal.style.display = 'none';
            }
        });
        
        clipsDamasSearch.addEventListener('input', () => {
            const searchTerm = clipsDamasSearch.value.toLowerCase();
            const filteredProducts = productsData.filter(product => 
                product.category === "damas" && 
                product.name.toLowerCase().includes(searchTerm)
            );
            generateProducts(filteredProducts, 'clipsDamasProducts');
        });
        
        // Modal "Clips Niñas"
        const clipsNinasModal = document.getElementById('clipsNinasModal');
        const clipsNinasBtn = document.getElementById('clipsNinasBtn');
        const clipsNinasProductsContainer = document.getElementById('clipsNinasProducts');
        const clipsNinasCloseBtn = document.querySelector('#clipsNinasModal .close-btn');
        const clipsNinasSearch = document.getElementById('clipsNinasSearch');
        
        clipsNinasBtn.addEventListener('click', () => {
            const ninasProducts = productsData.filter(p => p.category === "ninas");
            generateProducts(ninasProducts, 'clipsNinasProducts');
            clipsNinasModal.style.display = 'flex';
        });
        
        clipsNinasCloseBtn.addEventListener('click', () => {
            clipsNinasModal.style.display = 'none';
        });
        
        clipsNinasModal.addEventListener('click', (e) => {
            if (e.target === clipsNinasModal) {
                clipsNinasModal.style.display = 'none';
            }
        });
        
        clipsNinasSearch.addEventListener('input', () => {
            const searchTerm = clipsNinasSearch.value.toLowerCase();
            const filteredProducts = productsData.filter(product => 
                product.category === "ninas" && 
                product.name.toLowerCase().includes(searchTerm)
            );
            generateProducts(filteredProducts, 'clipsNinasProducts');
        });
        
        // Carrusel
        const slides = document.querySelector('.slides');
        const dots = document.querySelectorAll('.dots span');
        const prevBtn = document.querySelector('.prev-btn');
        const nextBtn = document.querySelector('.next-btn');
        let currentIndex = 0;
        
        function showSlide(index) {
            slides.style.transform = `translateX(-${index * 100}%)`;
            dots.forEach((dot, i) => {
                dot.classList.toggle('active', i === index);
            });
        }
        
        dots.forEach((dot, i) => {
            dot.addEventListener('click', () => {
                currentIndex = i;
                showSlide(currentIndex);
            });
        });
        
        prevBtn.addEventListener('click', () => {
            currentIndex = (currentIndex - 1 + dots.length) % dots.length;
            showSlide(currentIndex);
        });
        
        nextBtn.addEventListener('click', () => {
            currentIndex = (currentIndex + 1) % dots.length;
            showSlide(currentIndex);
        });
        
        setInterval(() => {
            currentIndex = (currentIndex + 1) % dots.length;
            showSlide(currentIndex);
        }, 5000);
        
        // Menú móvil
        const menuToggle = document.getElementById('menuToggle');
        const mainNav = document.getElementById('mainNav');
        const closeMenu = document.getElementById('closeMenu');
        
        menuToggle.addEventListener('click', () => {
            mainNav.classList.add('active');
        });
        
        closeMenu.addEventListener('click', () => {
            mainNav.classList.remove('active');
        });
        
        // Cerrar menú al hacer clic en un enlace
        document.querySelectorAll('nav a').forEach(link => {
            link.addEventListener('click', () => {
                mainNav.classList.remove('active');
            });
        });
        
        // Inicializar el carrito
        updateCart();
    </script>
</body>
</html>
