<!DOCTYPE html>
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
            background-color: var(--primary-color);
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
            background-color: var(--primary-color);
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
        
        /* Responsive */
    @media (max-width: 992px) {
            .header {
                flex-direction: column;
                gap: 15px;
            }
            
   nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
        }
        
    @media (max-width: 768px) {
            .products {
                grid-template-columns: repeat(auto-fill, minmax(170px, 1fr));
            }
            
    .product-img {
                height: 180px;
            }
            
    .model-section {
                grid-template-columns: 1fr;
            }
            
    .banner-text {
                font-size: 1.2rem;
                padding: 8px 20px;
            }
            
    .section-title {
                font-size: 1.5rem;
            }
        }
        
   @media (max-width: 480px) {
            nav ul {
                gap: 15px;
            }
            
    .header-icons {
                gap: 15px;
            }
            
    .products {
                grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
                gap: 15px;
            }
            
    .product-img {
                height: 150px;
            }
            
    .product-name {
                font-size: 1rem;
                height: auto;
            }
            
   .cart-content {
                max-width: 100%;
            }
        }
 </style>
</head>
<body>
    <div class="container">
        <!-- Header mejorado -->
        <header class="header">
            <div class="logo">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YXTTJyLqUwcNn1yduyV6i82lmL4ukvEZp-ePVd_P_Wa_y1VGwXNJOPpVxro2IxUZ55xE4oEndno5MItmJf7wjkFn0RYFCLtB4bOG2AHYHrupD1pkX8cf3jOUBHNUJOFEYOrwzTGEMSJj6j8=w1000-h1000-p-k-no" alt="TodoModa Logo">
            </div>
            <nav>
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
        <div class="products">
            <!-- Producto 1 -->
            <div class="product">
                <span class="product-badge">Nuevo</span>
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YXdnjCFtJm5EhEvClhpsqjsYwwH2Xdqql3H45tWmgLdhiRX--KLwloCAl85SxTImNaOYYbS1MOrlGYrDwH31YoIyFBBn7KapQIKbAHVfoyNmbRBjjgmF0_SefXWn6udgSSaO19kdNtmnQBd=w2000-h2000-p-k-no" alt="Maxilazos" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Maxilazos - 5 Colores</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                        <span>(4.2)</span>
                    </div>
                    <p class="product-price">S/ 7.00</p>
                    <button class="add-to-cart">
                        <i class="fas fa-shopping-cart"></i> Agregar al carrito
                    </button>
                </div>
            </div>
            
            <!-- Producto 2 -->
 <div class="product">
                <span class="product-badge">Popular</span>
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YUd2bofobsLtUl3qONXRSiTNou1a9W74yTaVYEr6h64PAuOOqQ-g_w6Ifs8arhOVjWboOrUFEcEDZlmtSBZkgS1YjEnSIw1f3w4IZRdMBwxibVChvNz2c93C78bOxNsx68MuBmN-4iYNCg=w2000-h2000-p-k-no" alt="Mini Gancho Corazón" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Mini Gancho Corazón</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                        <i class="far fa-star"></i>
                        <span>(3.2)</span>
                    </div>
                    <p class="product-price">S/ 2.50</p>
                    <button class="add-to-cart">
                        <i class="fas fa-shopping-cart"></i> Agregar al carrito
                    </button>
                </div>
            </div>
            
            <!-- Producto 3 -->
 <div class="product">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YV8A_P0YjCC6AIfC2B6HFvCKobK0UJZjVWMnzr6lfYPVXUk0gsszvJXojCK_ycIVH0cOD1-Qw3ICj1Bi9eLIf2TH0ZFaL14TuisJOWESznCPwqs2AAn_lgVOo2yGLhrKuG1yjgsGrWPIZ0k=w2000-h2000-p-k-no" alt="Ganchos Navideños" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Ganchos Navideños</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <span>(5.0)</span>
                    </div>
                    <p class="product-price">S/ 4.00</p>
                    <button class="add-to-cart">
                        <i class="fas fa-shopping-cart"></i> Agregar al carrito
                    </button>
                </div>
            </div>
            
            <!-- Producto 4 -->
 <div class="product">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YVaD4OrbInMGPZXKiKtKplaYEn2Ck-9KCl8p9FJbJIXPMWFCDw9Dd5lrbO-8FfXeJZKvIEr-K5UpFwrCnofwtR30imdZTojz2gxrHqZLSM3qody1gDhWdXAm_C4le7hQ4zKL3imga1TIh_j=w2000-h2000-p-k-no" alt="Gancho Hawaiano" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Gancho Hawaiano</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                        <span>(4.0)</span>
                    </div>
                    <p class="product-price">S/ 5.00</p>
                    <button class="add-to-cart">
                        <i class="fas fa-shopping-cart"></i> Agregar al carrito
                    </button>
                </div>
            </div>
        </div>

        <!-- Model Section mejorada -->
 <div class="model-section">
            <div class="model-item">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YUGuPXaSC1mPGUKkOYa5z7JyvELvbIy0B4-WtB3tMHIKm2D6Sbg1cTWwU0MsxRJR_5lKb5t1MnVOStZk-tNPdUudQ6-h7M7ueR4l8N5IgmuOrhlNRMi0B_uohBDRomdzQUIHP7y244Zc150=w1024-h1024-p-k-no" alt="Clips Damas">
                <button class="model-btn">CLIPS DAMAS</button>
            </div>
            <div class="model-item">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YUDER3L7ISerfG6uiIU8ISdgKkibO-SXwGGNL1azb_TJ0qYIN3T7LsJyU-qc9-kQtucnOkLr5rPYtWt0fW0UL8-7RDD46bg_0JnGLkD8RSfQvGydDvq6L_ZLBoj4hnIhwHB3CEx1fPtJ58O=w1024-h1024-p-k-no" alt="Clips Niñas">
                <button class="model-btn">CLIPS NIÑAS</button>
            </div>
        </div>

        <!-- Nuevos productos -->
 <h2 class="section-title">Nuevos Productos</h2>
        <div class="products">
            <!-- Producto 5 -->
            <div class="product">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YXULCa-2ZSbLgwDDlphVpkyxIs_jH2pp8AIHp25rY65c3VTGPdLnesGcrtuCiDtLbovSHvwiSUpzfWiwyle1UmqeO6d0OEvhBLqp_6k4YBo2QzMGd9aduXbKMXqGVHIB0FKSWvBYE1FNgj_=w2000-h2000-p-k-no" alt="Ganchos Acrílicos Color Celeste" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Ganchos Acrílicos Color Celeste</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                        <span>(4.0)</span>
                    </div>
                    <p class="product-price">S/ 5.00</p>
                    <button class="add-to-cart">
                        <i class="fas fa-shopping-cart"></i> Agregar al carrito
                    </button>
                </div>
            </div>
            
            <!-- Producto 6 -->
 <div class="product">
                <span class="product-badge">Oferta</span>
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YUepENF6loS0sqfXxEEZlTcAEQ7R-6iS6rmphnT9YjPc9whL2WIk8tCzVNnHDeaj6AaV3e6-k4yeUx9j6nSHq-l2Tc_t0dGMQLhBQrbdREDnxR65_tbipCAL3NCKmRQYWk5geU5V_jn3EiW=w2000-h2000-p-k-no" alt="Ganchos" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Ganchos</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                        <i class="far fa-star"></i>
                        <span>(3.1)</span>
                    </div>
                    <p class="product-price">S/ 4.50</p>
                    <button class="add-to-cart">
                        <i class="fas fa-shopping-cart"></i> Agregar al carrito
                    </button>
                </div>
            </div>
            
            <!-- Producto 7 -->
 <div class="product">
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YX2NRiy9kc9B9F5EY9kAoTjy699I8L7qzIaAFyN6ktzntZDbknG5_v1B6_JgD_hJDZQ7pAonmz2ynxpJqX4tYXVpt2EJISwaxV7Vd5er2HXevBcfzH_2KoEuxffPMG6wVLrMxkXZaJcUGxc=w2000-h2000-p-k-no" alt="Ganchos Torna Sol en forma de Flor" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Ganchos Torna Sol en forma de Flor</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                        <span>(4.1)</span>
                    </div>
                    <p class="product-price">S/ 6.00</p>
                    <button class="add-to-cart">
                        <i class="fas fa-shopping-cart"></i> Agregar al carrito
                    </button>
                </div>
            </div>
            
            <!-- Producto 8 -->
 <div class="product">
                <span class="product-badge">Nuevo</span>
                <img src="https://lh3.googleusercontent.com/gps-cs/AIky0YXzdeSiF8Ekcd_sbWEkePfXIFlDCt8BeIvwjgW0_jHy1u9d3KWkRPGKY0IPp8ADAmGFn46hFm8U5vXqhoZ738QBNnwuwb-UXng4k1wKXRwyarfw7ST9PYntIH_SA_XEF0lDF6STVaLz16z2=w2000-h2000-p-k-no" alt="Ganchos Kawai en forma de Flor" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Ganchos Kawai en forma de Flor</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                        <i class="far fa-star"></i>
                        <span>(3.5)</span>
                    </div>
                    <p class="product-price">S/ 4.50</p>
                    <button class="add-to-cart">
                        <i class="fas fa-shopping-cart"></i> Agregar al carrito
                    </button>
                </div>
            </div>
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
                <!-- Los elementos del carrito se añadirán aquí dinámicamente -->
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
    
<script>
        // Carrito de compras
        let cart = [];
        const cartIcon = document.getElementById('cartIcon');
        const cartModal = document.getElementById('cartModal');
        const cartContent = document.getElementById('cartContent');
        const closeCart = document.getElementById('closeCart');
        const cartItems = document.getElementById('cartItems');
        const cartTotal = document.getElementById('cartTotal');
        const checkoutBtn = document.getElementById('checkoutBtn');
        const addToCartButtons = document.querySelectorAll('.add-to-cart');
        
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
        addToCartButtons.forEach(button => {
            button.addEventListener('click', () => {
                const product = button.closest('.product');
                const name = product.querySelector('.product-name').textContent;
                const price = parseFloat(product.querySelector('.product-price').textContent.replace('S/ ', ''));
                const image = product.querySelector('.product-img').src;
                
                // Verificar si el producto ya está en el carrito
                const existingItem = cart.find(item => item.name === name);
                
                if (existingItem) {
                    existingItem.quantity++;
                } else {
                    cart.push({
                        name,
                        price,
                        image,
                        quantity: 1
                    });
                }
                
                updateCart();
                showAddedNotification(name);
            });
        });
        
        // Mostrar notificación de producto añadido
        function showAddedNotification(productName) {
            const notification = document.createElement('div');
            notification.innerHTML = `
                <div style="position: fixed; bottom: 20px; right: 20px; background: var(--success-color); color: white; padding: 15px 20px; border-radius: 5px; display: flex; align-items: center; gap: 10px; z-index: 1000; box-shadow: var(--shadow);">
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
        
        // Carousel functionality
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
        
        // Inicializar el carrito
        updateCart();
    </script>
</body>
</html>
