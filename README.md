<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UrbanStyle - Moda Juvenil</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&family=Montserrat:wght@700;800;900&display=swap" rel="stylesheet">
    <style>
        /* Variables y estilos base */
        :root {
            --primary: #ff3f8e;
            --secondary: #6c5ce7;
            --accent: #00cec9;
            --dark: #2d3436;
            --light: #f7f7f7;
            --success: #00b894;
            --warning: #fdcb6e;
            --gray: #b2bec3;
            --light-gray: #dfe6e9;
            --shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
            --border-radius: 16px;
        }

 * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

   body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
            -webkit-text-size-adjust: 100%; /* Evita el zoom automático en iOS */
        }

    .container {
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* HEADER - Mejoras móviles */
     header {
            background-color: white;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

   .top-bar {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            padding: 8px 0;
            font-size: 14px;
            font-weight: 500;
        }

     .top-bar-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

   .promo-text {
            flex: 1;
            text-align: center;
            min-width: 100%;
            order: 1;
        }

   .social-icons {
            display: flex;
            gap: 15px;
        }

   .social-icon {
            color: white;
            font-size: 16px;
            transition: var(--transition);
        }

    .social-icon:hover {
            transform: translateY(-3px);
        }

   .language-selector {
            display: flex;
            align-items: center;
            gap: 5px;
        }

   .nav-bar {
            display: flex;
            align-items: center;
            padding: 15px 0;
            flex-wrap: wrap;
        }

    .logo {
            font-family: 'Montserrat', sans-serif;
            font-size: 28px;
            font-weight: 800;
            color: var(--dark);
            margin-right: 15px;
            display: flex;
            align-items: center;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            white-space: nowrap;
        }

    .logo i {
            margin-right: 8px;
        }

   .search-container {
            flex: 1;
            display: flex;
            max-width: 700px;
            position: relative;
            margin-top: 15px;
            order: 3;
            min-width: 100%;
        }

   .search-container input {
            flex: 1;
            padding: 12px 20px;
            border: 2px solid var(--light-gray);
            border-radius: 50px;
            font-size: 14px;
            outline: none;
            transition: var(--transition);
            box-shadow: var(--shadow);
        }

   .search-container input:focus {
            border-color: var(--secondary);
            box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.2);
        }

    .search-btn {
            position: absolute;
            right: 5px;
            top: 5px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 16px;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(255, 63, 142, 0.3);
        }

    .search-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 15px rgba(255, 63, 142, 0.4);
        }

   .header-actions {
            display: flex;
            margin-left: auto;
            gap: 12px;
        }

    .action-btn {
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            color: var(--dark);
            position: relative;
            transition: var(--transition);
            padding: 8px;
            border-radius: 12px;
            min-width: 50px;
        }

   .action-btn:hover {
            background: rgba(108, 92, 231, 0.05);
            transform: translateY(-3px);
        }

    .action-btn i {
            font-size: 20px;
            margin-bottom: 3px;
        }

    .action-btn span {
            font-size: 11px;
            font-weight: 500;
        }

    .cart-count {
            position: absolute;
            top: -5px;
            right: 0;
            background: var(--primary);
            color: white;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 10px;
            font-weight: bold;
        }

        /* Navigation */
   .categories {
            background: white;
            padding: 12px 0;
            border-top: 1px solid var(--light-gray);
            overflow-x: auto;
            -webkit-overflow-scrolling: touch;
        }

    .categories ul {
            display: flex;
            list-style: none;
            justify-content: flex-start;
            gap: 8px;
            flex-wrap: nowrap;
            padding: 0 10px;
            min-width: max-content;
        }

    .categories li a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            padding: 8px 16px;
            border-radius: 50px;
            transition: var(--transition);
            font-size: 13px;
            border: 2px solid transparent;
            white-space: nowrap;
        }

    .categories li a:hover, .categories li a.active {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            border-color: transparent;
            box-shadow: 0 4px 12px rgba(108, 92, 231, 0.25);
        }

        /* Hero Section */
   .hero {
            height: 300px;
            background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.4)), url('https://images.unsplash.com/photo-1483985988355-763728e1935b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            border-radius: var(--border-radius);
            position: relative;
            overflow: hidden;
            margin: 10px;
        }

   .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(255,63,142,0.3), rgba(108,92,231,0.3));
        }

    .hero-content {
            max-width: 650px;
            padding: 0 20px;
            position: relative;
            z-index: 2;
            text-align: center;
        }

    .hero h1 {
            font-size: 28px;
            margin-bottom: 15px;
            font-weight: 800;
            line-height: 1.1;
            font-family: 'Montserrat', sans-serif;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

   .hero p {
            font-size: 16px;
            margin-bottom: 20px;
            text-shadow: 0 1px 2px rgba(0,0,0,0.3);
        }

   .btn {
            display: inline-block;
            padding: 12px 25px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 14px;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            box-shadow: 0 6px 15px rgba(255, 63, 142, 0.3);
            position: relative;
            overflow: hidden;
            margin: 5px;
        }

   .btn::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -60%;
            width: 20%;
            height: 200%;
            background: rgba(255, 255, 255, 0.3);
            transform: rotate(25deg);
            transition: all 0.4s;
        }

   .btn:hover::after {
            left: 120%;
        }

    .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(255, 63, 142, 0.4);
        }

    .btn-outline {
            background: transparent;
            border: 2px solid white;
            box-shadow: none;
        }

   .btn-outline:hover {
            background: rgba(255,255,255,0.1);
            transform: translateY(-5px);
        }

        /* Product Grid */
    .section-title {
            font-size: 28px;
            margin: 30px 0 20px;
            font-weight: 800;
            position: relative;
            padding-bottom: 10px;
            font-family: 'Montserrat', sans-serif;
            text-align: center;
        }

   .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 5px;
        }

   .filters {
            display: flex;
            background: white;
            padding: 15px;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            margin-bottom: 20px;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
        }

   .filter-group {
            display: flex;
            flex-direction: column;
            min-width: 100%;
        }

    .filter-group label {
            font-size: 13px;
            margin-bottom: 6px;
            color: var(--gray);
            font-weight: 500;
        }

    .filter-group select, .filter-group input {
            padding: 12px 15px;
            border: 2px solid var(--light-gray);
            border-radius: 12px;
            background: white;
            font-size: 14px;
            transition: var(--transition);
        }

    .filter-group select:focus, .filter-group input:focus {
            border-color: var(--secondary);
            box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.2);
        }

    .apply-btn {
            display: flex;
            align-items: flex-end;
            min-width: 100%;
        }

    .apply-btn button {
            padding: 14px 20px;
            width: 100%;
            margin-top: 0;
        }

   .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

   .product-card {
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

   .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }

   .product-badge {
            position: absolute;
            top: 12px;
            left: 12px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            padding: 5px 12px;
            border-radius: 50px;
            font-size: 12px;
            font-weight: 600;
            z-index: 2;
        }

   .product-image {
            height: 220px;
            width: 100%;
            overflow: hidden;
            position: relative;
            background: #f9f9f9;
            display: flex;
            align-items: center;
            justify-content: center;
        }

   .product-image img {
            max-width: 80%;
            max-height: 80%;
            object-fit: contain;
            transition: var(--transition);
            cursor: pointer;
        }

    .product-card:hover .product-image img {
            transform: scale(1.1);
        }

    .quick-view {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background: rgba(0,0,0,0.8);
            color: white;
            padding: 12px;
            text-align: center;
            font-size: 13px;
            font-weight: 500;
            opacity: 0;
            transform: translateY(100%);
            transition: var(--transition);
            cursor: pointer;
            z-index: 3;
        }

   .product-card:hover .quick-view {
            opacity: 1;
            transform: translateY(0);
        }

    .product-info {
            padding: 15px;
        }

   .product-category {
            color: var(--gray);
            font-size: 12px;
            margin-bottom: 4px;
            font-weight: 500;
        }

   .product-title {
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 8px;
            height: 44px;
            overflow: hidden;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
        }

    .product-rating {
            color: var(--warning);
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            font-size: 14px;
        }

   .product-rating span {
            color: var(--gray);
            font-size: 13px;
            margin-left: 6px;
        }

    .product-price {
            display: flex;
            align-items: center;
            margin-bottom: 12px;
            flex-wrap: wrap;
            gap: 5px;
        }

     .current-price {
            font-size: 20px;
            font-weight: 700;
            color: var(--primary);
        }

    .original-price {
            font-size: 14px;
            color: var(--gray);
            text-decoration: line-through;
        }

    .discount {
            font-size: 13px;
            color: var(--success);
            font-weight: 600;
            background: rgba(0, 184, 148, 0.1);
            padding: 3px 8px;
            border-radius: 4px;
        }

   .product-stats {
            display: flex;
            justify-content: space-between;
            font-size: 12px;
            color: var(--gray);
            padding-top: 12px;
            border-top: 1px solid var(--light-gray);
            margin-top: 12px;
        }

    .product-actions {
            display: flex;
            margin-top: 12px;
            gap: 8px;
        }

     .add-to-cart {
            flex: 1;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 600;
            font-size: 13px;
            box-shadow: 0 4px 10px rgba(255, 63, 142, 0.3);
        }

    .add-to-cart:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(255, 63, 142, 0.4);
        }

    .wishlist-btn {
            width: 40px;
            height: 40px;
            border: 2px solid var(--light-gray);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: var(--transition);
            background: white;
            font-size: 16px;
        }

    .wishlist-btn.active i {
            color: var(--primary);
        }

    .wishlist-btn:hover {
            border-color: var(--primary);
            color: var(--primary);
            transform: translateY(-3px);
        }

        /* Nuevos estilos para selector de tallas */
    .size-selector {
            margin-bottom: 20px;
        }

    .size-selector label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            font-size: 16px;
        }

    .size-options {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

    .size-option {
            min-width: 45px;
            padding: 8px;
            border: 2px solid var(--light-gray);
            border-radius: 8px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            position: relative;
            font-size: 14px;
        }

    .size-option:hover {
            border-color: var(--secondary);
        }

     .size-option.selected {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            border-color: transparent;
        }

    .size-option.unavailable {
            background: var(--light-gray);
            color: #999;
            cursor: not-allowed;
            text-decoration: line-through;
        }

   .size-option.unavailable::after {
            content: "✗";
            position: absolute;
            top: -5px;
            right: -5px;
            background: var(--primary);
            color: white;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            font-size: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Product Detail Modal - Pantalla Completa */
    .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            z-index: 2000;
            overflow-y: auto;
        }

    .modal.active {
            display: block;
        }

     .modal-content {
            background: white;
            width: 100%;
            min-height: 100vh;
            position: relative;
            animation: modalOpen 0.5s ease;
            padding: 60px 15px 40px;
        }

    @keyframes modalOpen {
            from { opacity: 0; transform: translateY(-50px); }
            to { opacity: 1; transform: translateY(0); }
        }

    .close-modal {
            position: fixed;
            top: 15px;
            right: 15px;
            font-size: 24px;
            cursor: pointer;
            color: var(--dark);
            background: white;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            z-index: 10;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
        }

    .close-modal:hover {
            background: var(--primary);
            color: white;
            transform: rotate(90deg);
        }

    .product-detail {
            display: flex;
            flex-direction: column;
            gap: 25px;
            max-width: 1400px;
            margin: 0 auto;
        }

   .product-gallery {
            display: flex;
            flex-direction: column;
            height: 100%;
        }

     .main-image {
            width: 100%;
            height: 50vh;
            border-radius: var(--border-radius);
            overflow: hidden;
            background: var(--light);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 15px;
        }

   .main-image img {
            max-width: 90%;
            max-height: 90%;
            object-fit: contain;
        }

    .thumbnails {
            display: flex;
            gap: 10px;
            overflow-x: auto;
            padding-bottom: 10px;
        }

    .thumbnail {
            min-width: 80px;
            height: 80px;
            border-radius: 10px;
            overflow: hidden;
            cursor: pointer;
            border: 2px solid transparent;
            transition: var(--transition);
            background: var(--light);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

   .thumbnail img {
            max-width: 90%;
            max-height: 90%;
            object-fit: contain;
        }

    .thumbnail.active, .thumbnail:hover {
            border-color: var(--primary);
            transform: scale(1.05);
        }

    .product-info-detail {
            padding: 15px 0;
        }

    .product-info-detail h1 {
            font-size: 32px;
            margin-bottom: 12px;
            font-weight: 800;
            font-family: 'Montserrat', sans-serif;
            line-height: 1.2;
        }

    .product-category-detail {
            display: inline-block;
            background: rgba(108, 92, 231, 0.1);
            color: var(--secondary);
            padding: 6px 15px;
            border-radius: 50px;
            margin-bottom: 20px;
            font-size: 14px;
            font-weight: 600;
        }

    .rating-detail {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

    .stars {
            color: var(--warning);
            font-size: 20px;
            margin-right: 12px;
        }

    .reviews {
            color: var(--gray);
            font-weight: 500;
            font-size: 16px;
        }

    .price-detail {
            display: flex;
            align-items: center;
            margin-bottom: 25px;
            flex-wrap: wrap;
            gap: 12px;
        }

    .current-price-detail {
            font-size: 32px;
            font-weight: 800;
            color: var(--primary);
        }

    .original-price-detail {
            font-size: 22px;
            color: var(--gray);
            text-decoration: line-through;
        }

     .discount-detail {
            font-size: 18px;
            color: var(--success);
            font-weight: 700;
            background: rgba(0, 184, 148, 0.1);
            padding: 6px 15px;
            border-radius: 50px;
        }

    .product-description {
            margin-bottom: 30px;
            line-height: 1.7;
            color: #555;
            font-size: 16px;
        }

   .specs-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 8px;
        }

    .specs-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 5px;
        }

    .specs-grid {
            display: grid;
            grid-template-columns: repeat(1, 1fr);
            gap: 15px;
            margin-bottom: 30px;
        }

    .spec-item {
            display: flex;
            padding: 15px;
            background: rgba(223, 230, 233, 0.3);
            border-radius: 12px;
            font-size: 15px;
        }

   .spec-label {
            font-weight: 600;
            margin-right: 12px;
            min-width: 120px;
            color: var(--dark);
        }

    .spec-value {
            color: #555;
        }

    .actions-detail {
            display: flex;
            gap: 15px;
            margin-top: 30px;
            flex-wrap: wrap;
        }

    .quantity-selector {
            display: flex;
            align-items: center;
            border: 2px solid var(--light-gray);
            border-radius: 12px;
            overflow: hidden;
            padding: 4px;
            min-width: 180px;
        }

    .quantity-btn {
            width: 45px;
            height: 45px;
            background: white;
            border: none;
            font-size: 20px;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
        }

    .quantity-btn:hover {
            background: var(--light);
        }

    .quantity-input {
            width: 60px;
            height: 45px;
            text-align: center;
            border: none;
            border-left: 2px solid var(--light-gray);
            border-right: 2px solid var(--light-gray);
            font-size: 20px;
            font-weight: 600;
        }

    .add-to-cart-detail {
            flex: 1;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            padding: 0 25px;
            border-radius: 12px;
            cursor: pointer;
            font-size: 18px;
            font-weight: 600;
            transition: var(--transition);
            box-shadow: 0 6px 15px rgba(255, 63, 142, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            height: 53px;
        }

    .add-to-cart-detail:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(255, 63, 142, 0.4);
        }

    .wishlist-detail {
            width: 60px;
            height: 60px;
            border: 2px solid var(--light-gray);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: var(--transition);
            font-size: 24px;
            background: white;
        }

    .wishlist-detail.active i {
            color: var(--primary);
        }

    .wishlist-detail:hover {
            border-color: var(--primary);
            color: var(--primary);
            transform: translateY(-5px);
        }

        /* Cart Modal */
    .cart-modal {
            display: none;
            position: fixed;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background: white;
            z-index: 3000;
            box-shadow: -10px 0 30px rgba(0,0,0,0.1);
            overflow-y: auto;
            transform: translateX(100%);
            transition: transform 0.4s ease;
        }

    .cart-modal.active {
            transform: translateX(0);
            display: block;
        }

     .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid var(--light-gray);
        }

    .cart-header h2 {
            font-size: 22px;
            font-weight: 700;
        }

   .close-cart {
            font-size: 22px;
            cursor: pointer;
            transition: var(--transition);
        }

    .close-cart:hover {
            color: var(--primary);
            transform: scale(1.1);
        }

   .cart-items {
            padding: 15px;
        }

    .cart-item {
            display: flex;
            padding: 15px 0;
            border-bottom: 1px solid var(--light-gray);
        }

     .cart-item-img {
            width: 80px;
            height: 80px;
            border-radius: 10px;
            overflow: hidden;
            margin-right: 15px;
            background: var(--light);
            display: flex;
            align-items: center;
            justify-content: center;
        }

    .cart-item-img img {
            max-width: 80%;
            max-height: 80%;
            object-fit: contain;
        }

    .cart-item-details {
            flex: 1;
        }

    .cart-item-title {
            font-weight: 600;
            margin-bottom: 6px;
            font-size: 15px;
        }

    .cart-item-price {
            color: var(--primary);
            font-weight: 700;
            margin-bottom: 10px;
            font-size: 16px;
        }

        /* Nuevo estilo para mostrar talla en carrito */
     .cart-item-size {
            display: flex;
            align-items: center;
            margin-bottom: 10px;
            gap: 8px;
            font-size: 14px;
        }

    .cart-item-size label {
            font-weight: 600;
        }

    .cart-item-size select {
            padding: 6px;
            border: 1px solid var(--light-gray);
            border-radius: 6px;
            background: white;
            font-size: 13px;
        }

    .cart-item-quantity {
            display: flex;
            align-items: center;
        }

     .cart-item-quantity button {
            width: 28px;
            height: 28px;
            border: 1px solid var(--light-gray);
            background: white;
            border-radius: 6px;
            cursor: pointer;
            font-size: 14px;
        }

    .cart-item-quantity input {
            width: 36px;
            height: 28px;
            text-align: center;
            border: none;
            margin: 0 6px;
            font-size: 14px;
        }

    .cart-item-remove {
            color: var(--gray);
            font-size: 13px;
            margin-top: 8px;
            cursor: pointer;
            transition: var(--transition);
            display: inline-block;
        }

    .cart-item-remove:hover {
            color: var(--primary);
            transform: translateX(3px);
        }

     .cart-summary {
            padding: 20px;
            background: rgba(223, 230, 233, 0.3);
            border-radius: var(--border-radius);
            margin: 15px;
        }

    .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 20px;
        }

    .cart-actions {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

    .checkout-btn {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            padding: 16px;
            border-radius: 14px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }

    .checkout-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 63, 142, 0.4);
        }

    .continue-shopping {
            background: white;
            color: var(--dark);
            border: 2px solid var(--light-gray);
            padding: 14px;
            border-radius: 14px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }

     .continue-shopping:hover {
            border-color: var(--primary);
            color: var(--primary);
        }

        /* Modal de Favoritos */
    .favorites-modal {
            display: none;
            position: fixed;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background: white;
            z-index: 3000;
            box-shadow: -10px 0 30px rgba(0,0,0,0.1);
            overflow-y: auto;
            transform: translateX(100%);
            transition: transform 0.4s ease;
        }

   .favorites-modal.active {
            transform: translateX(0);
            display: block;
        }

    .favorites-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid var(--light-gray);
        }

    .favorites-header h2 {
            font-size: 22px;
            font-weight: 700;
        }

    .close-favorites {
            font-size: 22px;
            cursor: pointer;
            transition: var(--transition);
        }

   .close-favorites:hover {
            color: var(--primary);
            transform: scale(1.1);
        }

    .favorites-items {
            padding: 15px;
        }

    .favorite-item {
            display: flex;
            padding: 15px 0;
            border-bottom: 1px solid var(--light-gray);
        }

    .favorite-item-img {
            width: 80px;
            height: 80px;
            border-radius: 10px;
            overflow: hidden;
            margin-right: 15px;
            background: var(--light);
            display: flex;
            align-items: center;
            justify-content: center;
        }

    .favorite-item-img img {
            max-width: 80%;
            max-height: 80%;
            object-fit: contain;
        }

    .favorite-item-details {
            flex: 1;
        }

     .favorite-item-title {
            font-weight: 600;
            margin-bottom: 6px;
            font-size: 15px;
        }

     .favorite-item-price {
            color: var(--primary);
            font-weight: 700;
            margin-bottom: 10px;
            font-size: 16px;
        }

      .favorite-item-actions {
            display: flex;
            gap: 8px;
        }

    .add-to-cart-from-fav {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            padding: 8px 12px;
            border-radius: 6px;
            cursor: pointer;
            transition: var(--transition);
            font-size: 13px;
        }

    .add-to-cart-from-fav:hover {
            transform: translateY(-3px);
            box-shadow: 0 4px 10px rgba(255, 63, 142, 0.3);
        }

     .remove-from-fav {
            background: white;
            color: var(--dark);
            border: 1px solid var(--light-gray);
            padding: 8px 12px;
            border-radius: 6px;
            cursor: pointer;
            transition: var(--transition);
            font-size: 13px;
        }

    .remove-from-fav:hover {
            background: var(--light);
            transform: translateY(-3px);
        }

        /* Modal de Contacto */
     .contact-modal {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 90%;
            max-width: 500px;
            background: white;
            z-index: 4000;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            padding: 25px;
        }

    .contact-modal.active {
            display: block;
        }

    .contact-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

   .contact-header h2 {
            font-size: 24px;
            font-weight: 700;
        }

   .close-contact {
            font-size: 24px;
            cursor: pointer;
            transition: var(--transition);
        }

   .close-contact:hover {
            color: var(--primary);
            transform: scale(1.1);
        }

    .contact-content p {
            margin-bottom: 12px;
            font-size: 16px;
            display: flex;
            align-items: center;
        }

    .contact-content i {
            margin-right: 12px;
            font-size: 20px;
            color: var(--primary);
            width: 24px;
        }

     .whatsapp-btn {
            display: inline-block;
            background: #25D366;
            color: white;
            padding: 12px 20px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            margin-top: 15px;
            transition: var(--transition);
            font-size: 16px;
        }

    .whatsapp-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 15px rgba(37, 211, 102, 0.3);
        }

    .whatsapp-btn i {
            color: white;
            margin-right: 8px;
        }

        /* Overlay para modales */
    .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 2000;
        }

    .modal-overlay.active {
            display: block;
        }

        /* Footer */
     footer {
            background: var(--dark);
            color: white;
            padding: 50px 0 25px;
            margin-top: 40px;
        }

    .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

    .footer-column h3 {
            font-size: 20px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 8px;
            font-family: 'Montserrat', sans-serif;
        }

     .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 3px;
            background: var(--primary);
        }

    .footer-links {
            list-style: none;
        }

    .footer-links li {
            margin-bottom: 12px;
        }

     .footer-links a {
            color: #bbb;
            text-decoration: none;
            transition: var(--transition);
            display: inline-block;
            font-size: 14px;
        }

    .footer-links a:hover {
            color: white;
            transform: translateX(5px);
        }

    .footer-social {
            display: flex;
            margin-top: 20px;
            gap: 12px;
        }

    .social-icon-footer {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255,255,255,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            font-size: 16px;
        }

    .social-icon-footer:hover {
            background: var(--primary);
            transform: translateY(-5px);
        }

    .footer-bottom {
            text-align: center;
            padding-top: 25px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #999;
            font-size: 13px;
        }

        /* Notificaciones */
    .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--success);
            color: white;
            padding: 12px 20px;
            border-radius: 10px;
            box-shadow: var(--shadow);
            z-index: 3000;
            animation: fadeIn 0.3s, fadeOut 0.3s 2.7s;
            font-weight: 500;
            font-size: 14px;
        }

     @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

      @keyframes fadeOut {
            from { opacity: 1; transform: translateY(0); }
            to { opacity: 0; transform: translateY(20px); }
        }

        /* Responsive - Mejoras adicionales */
     @media (min-width: 576px) {
            .top-bar-content {
                flex-wrap: nowrap;
            }
            
    .promo-text {
                min-width: auto;
                order: 0;
            }
            
     .search-container {
                min-width: auto;
                margin-top: 0;
                order: 0;
            }
            
     .logo {
                font-size: 30px;
            }
            
   .hero {
                height: 350px;
            }
            
    .hero h1 {
                font-size: 32px;
            }
            
    .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
            
    .specs-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

    @media (min-width: 768px) {
            .logo {
                font-size: 32px;
            }
            
    .action-btn span {
                font-size: 12px;
            }
            
     .hero {
                height: 400px;
            }
            
    .hero h1 {
                font-size: 40px;
            }
            
    .hero-content {
                text-align: left;
                padding: 0 40px;
            }
            
    .btn {
                margin-left: 0;
                margin-right: 15px;
            }
            
    .filter-group {
                min-width: 200px;
            }
            
    .apply-btn {
                min-width: auto;
            }
            
    .product-detail {
                flex-direction: row;
                gap: 30px;
            }
            
    .product-gallery {
                width: 50%;
            }
            
    .product-info-detail {
                width: 50%;
            }
            
    .cart-modal, .favorites-modal {
                width: 400px;
            }
        }

    @media (min-width: 992px) {
            .hero {
                height: 450px;
            }
            
    .hero h1 {
                font-size: 48px;
            }
            
     .section-title {
                font-size: 32px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="top-bar">
            <div class="container top-bar-content">
                <div class="social-icons">
                    <a href="#" class="social-icon"><i class="fab fa-instagram"></i></a>
                    <a href="#" class="social-icon"><i class="fab fa-tiktok"></i></a>
                    <a href="#" class="social-icon"><i class="fab fa-twitter"></i></a>
                </div>
                <div class="promo-text">
                    ✨ ENVÍO GRATIS EN PEDIDOS SUPERIORES A S/200 ✨
                </div>
                <div class="language-selector">
                    <i class="fas fa-globe"></i> Español
                </div>
            </div>
        </div>
        
<div class="container">
            <div class="nav-bar">
                <div class="logo">
                    <i class="fas fa-tshirt"></i>
                    URBANSTYLE
                </div>
                
<div class="search-container">
                    <input type="text" placeholder="Busca entre miles de productos de moda...">
                    <button class="search-btn"><i class="fas fa-search"></i></button>
                </div>
                
 <div class="header-actions">
                    <div class="action-btn">
                        <i class="fas fa-user"></i>
                        <span>Cuenta</span>
                    </div>
                    <div class="action-btn" id="open-favorites">
                        <i class="fas fa-heart"></i>
                        <span>Favoritos</span>
                        <span class="cart-count" id="favorites-count">0</span>
                    </div>
                    <div class="action-btn cart-btn" id="open-cart">
                        <i class="fas fa-shopping-cart"></i>
                        <span>Carrito</span>
                        <span class="cart-count">0</span>
                    </div>
                </div>
            </div>
        </div>
        
 <div class="categories">
            <div class="container">
                <ul>
                    <li><a href="#" class="category-link active" data-category="all">Novedades</a></li>
                    <li><a href="#" class="category-link" data-category="Ropa de Hombre">Ropa</a></li>
                    <li><a href="#" class="category-link" data-category="Zapatos Unisex">Zapatos</a></li>
                    <li><a href="#" class="category-link" data-category="Accesorios">Accesorios</a></li>
                    <li><a href="#" class="category-link" data-category="Deportes">Deportes</a></li>
                    <li><a href="#" class="category-link" data-category="Belleza">Belleza</a></li>
                    <li><a href="#" class="category-link" data-category="Ofertas">Ofertas</a></li>
                    <li><a href="#" class="category-link" data-category="Colecciones">Colecciones</a></li>
                </ul>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
<section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>DESCUBRE TU ESTILO ÚNICO</h1>
                <p>Moda urbana para jóvenes con actitud. Encuentra las últimas tendencias a precios increíbles.</p>
                <a href="#" class="btn">VER COLECCIÓN</a>
                <a href="#" class="btn btn-outline">OFERTAS FLASH</a>
            </div>
        </div>
    </section>

    <!-- Main Content -->
<main class="container">
        <h2 class="section-title">Tendencias del Momento</h2>
        
 <div class="filters">
            <div class="filter-group">
                <label for="category">CATEGORÍA</label>
                <select id="category">
                    <option value="all">Todas las categorías</option>
                    <option value="Ropa de Mujer">Ropa de mujer</option>
                    <option value="Ropa de Hombre">Ropa de hombre</option>
                    <option value="Zapatos Unisex">Zapatos</option>
                    <option value="Accesorios">Accesorios</option>
                    <option value="Deportes">Deportes</option>
                </select>
            </div>
            
 <div class="filter-group">
                <label for="price">RANGO DE PRECIOS</label>
                <select id="price">
                    <option value="all">Todos los precios</option>
                    <option value="0-50">Menos de S/50</option>
                    <option value="50-100">S/50 - S/100</option>
                    <option value="100-200">S/100 - S/200</option>
                    <option value="200+">Más de S/200</option>
                </select>
            </div>
            
 <div class="filter-group">
                <label for="sort">ORDENAR POR</label>
                <select id="sort">
                    <option value="default">Recomendados</option>
                    <option value="popular">Más vendidos</option>
                    <option value="newest">Más nuevos</option>
                    <option value="price-asc">Precio: Menor a Mayor</option>
                    <option value="price-desc">Precio: Mayor a Menor</option>
                    <option value="rating">Mejor valorados</option>
                </select>
            </div>
            
 <div class="filter-group apply-btn">
                <button class="btn" id="apply-filters">Aplicar Filtros</button>
            </div>
        </div>
        
 <div class="product-grid" id="product-grid">
            <!-- Productos cargados dinámicamente con JavaScript -->
        </div>
        
 <div class="text-center" style="margin-bottom: 60px;">
            <button class="btn" style="padding: 16px 60px; font-size: 18px;" id="load-more">CARGAR MÁS PRODUCTOS</button>
        </div>
    </main>
    
    <!-- Product Detail Modal - Pantalla Completa -->
<div class="modal" id="product-modal">
        <div class="modal-content">
            <span class="close-modal" id="close-product">&times;</span>
            
<div class="product-detail">
                <div class="product-gallery">
                    <div class="main-image" id="main-image">
                        <!-- Imagen principal cargada dinámicamente -->
                    </div>
                    <div class="thumbnails" id="thumbnails">
                        <!-- Thumbnails cargados dinámicamente -->
                    </div>
                </div>
                
<div class="product-info-detail">
                    <h1 id="detail-title">Nombre del Producto</h1>
                    <div class="product-category-detail" id="detail-category">Categoría</div>
                    
<div class="rating-detail">
                        <div class="stars" id="detail-rating">
                            <!-- Estrellas de valoración -->
                        </div>
                        <div class="reviews" id="detail-reviews">128 reviews</div>
                    </div>
                    
 <div class="price-detail">
                        <div class="current-price-detail" id="detail-price">S/49.99</div>
                        <div class="original-price-detail" id="detail-original-price">S/89.99</div>
                        <div class="discount-detail" id="detail-discount">-44%</div>
                    </div>
                    
 <p class="product-description" id="detail-description">
                        Descripción detallada del producto con todas sus características, materiales, y beneficios. Perfecto para el uso diario y ocasiones especiales.
                    </p>
                    
                    <!-- Nuevo selector de tallas -->
 <div class="size-selector">
                        <label>Talla:</label>
                        <div class="size-options" id="size-options">
                            <!-- Opciones de talla cargadas dinámicamente -->
                        </div>
                    </div>
                    
 <div class="specs-title">Especificaciones</div>
                    <div class="specs-grid" id="specs-grid">
                        <!-- Especificaciones cargadas dinámicamente -->
                    </div>
                    
<div class="actions-detail">
                        <div class="quantity-selector">
                            <button class="quantity-btn minus">-</button>
                            <input type="text" class="quantity-input" value="1" readonly>
                            <button class="quantity-btn plus">+</button>
                        </div>
                        <button class="add-to-cart-detail" id="add-to-cart-detail">
                            <i class="fas fa-shopping-cart"></i> Añadir al carrito
                        </button>
                        <button class="wishlist-detail" id="detail-wishlist">
                            <i class="far fa-heart"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Cart Modal -->
 <div class="cart-modal" id="cart-modal">
        <div class="cart-header">
            <h2>Tu Carrito</h2>
            <span class="close-cart" id="close-cart">&times;</span>
        </div>
        
 <div class="cart-items" id="cart-items">
            <!-- Elementos del carrito cargados dinámicamente -->
        </div>
        
  <div class="cart-summary">
            <div class="cart-total">
                <span>Total:</span>
                <span id="cart-total-price">S/0.00</span>
            </div>
            <div class="cart-actions">
                <button class="checkout-btn">Proceder al Pago</button>
                <button class="continue-shopping" id="continue-shopping">Seguir Comprando</button>
            </div>
        </div>
    </div>
    
    <!-- Favorites Modal -->
 <div class="favorites-modal" id="favorites-modal">
        <div class="favorites-header">
            <h2>Tus Favoritos</h2>
            <span class="close-favorites" id="close-favorites">&times;</span>
        </div>
        <div class="favorites-items" id="favorites-items">
            <!-- Productos favoritos se cargarán aquí -->
        </div>
    </div>
    
    <!-- Contact Modal -->
 <div class="contact-modal" id="contact-modal">
        <div class="contact-header">
            <h2>Contacto</h2>
            <span class="close-contact" id="close-contact">&times;</span>
        </div>
        <div class="contact-content">
            <p><i class="fas fa-map-marker-alt"></i> Av. Arequipa 123, Lima</p>
            <p><i class="fas fa-phone"></i> +51 1 123 4567</p>
            <p><i class="fas fa-envelope"></i> info@urbanstyle.com</p>
            <a href="https://wa.me/5111234567" class="whatsapp-btn" target="_blank">
                <i class="fab fa-whatsapp"></i> Contactar por WhatsApp
            </a>
        </div>
    </div>
    
    <!-- Overlay para modales -->
 <div class="modal-overlay" id="modal-overlay"></div>
    
    <!-- Footer -->
<footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-column">
                    <h3>URBANSTYLE</h3>
                    <p>Tu destino para la moda juvenil más actual. Calidad, estilo y precios increíbles.</p>
                    <div class="footer-social">
                        <a href="#" class="social-icon-footer"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="social-icon-footer"><i class="fab fa-tiktok"></i></a>
                        <a href="#" class="social-icon-footer"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="social-icon-footer"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                
 <div class="footer-column">
                    <h3>Comprar</h3>
                    <ul class="footer-links">
                        <li><a href="#">Novedades</a></li>
                        <li><a href="#">Ropa de mujer</a></li>
                        <li><a href="#">Ropa de hombre</a></li>
                        <li><a href="#">Zapatos</a></li>
                        <li><a href="#">Accesorios</a></li>
                        <li><a href="#">Ofertas</a></li>
                    </ul>
                </div>
                
<div class="footer-column">
                    <h3>Ayuda</h3>
                    <ul class="footer-links">
                        <li><a href="#">Centro de ayuda</a></li>
                        <li><a href="#">Seguimiento de pedido</a></li>
                        <li><a href="#">Devoluciones</a></li>
                        <li><a href="#">Guía de tallas</a></li>
                        <li><a href="#" id="footer-contact">Contacto</a></li>
                    </ul>
                </div>
                
<div class="footer-column">
                    <h3>Contacto</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-map-marker-alt"></i> Av. Arequipa 123, Lima</li>
                        <li><i class="fas fa-phone"></i> +51 1 123 4567</li>
                        <li><i class="fas fa-envelope"></i> info@urbanstyle.com</li>
                        <li><i class="fas fa-clock"></i> L-V: 9:00 - 20:00</li>
                    </ul>
                </div>
            </div>
            
 <div class="footer-bottom">
                <p>&copy; 2023 UrbanStyle. Todos los derechos reservados. | Diseñado con ❤️ para jóvenes con estilo</p>
            </div>
        </div>
    </footer>
    
 <script>
        // Datos de productos de moda juvenil con tallas
        const products = [
            {
                id: 1,
                name: "Sudadera Oversized con Estampado Urbano",
                category: "Ropa de Hombre",
                price: 120.99,
                originalPrice: 199.99,
                images: [
                    "https://images.unsplash.com/photo-1551028719-00167b16eac5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1525507119028-edc6dcb6d633?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1523381210434-271e8be1f52b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                ],
                rating: 4.7,
                reviews: 128,
                sold: 450,
                stock: 25,
                badge: "NUEVO",
                description: "Sudadera oversized de alta calidad con estampado urbano en la espalda. Fabricada en algodón orgánico 100% para máxima comodidad. Perfecta para looks casuales y deportivos.",
                specs: {
                    "Material": "Algodón 100%",
                    "Color": "Negro con estampado blanco",
                    "Tallas": "S, M, L, XL",
                    "Peso": "450g",
                    "Cuidados": "Lavable a máquina 30°",
                    "Origen": "Portugal"
                },
                sizes: ['S', 'M', 'L', 'XL'],
                sizesStock: {
                    'S': 8,
                    'M': 10,
                    'L': 5,
                    'XL': 2
                },
                isFavorite: false
            },
            {
                id: 2,
                name: "Zapatillas Deportivas UltraLigeras Urbanas",
                category: "Zapatos Unisex",
                price: 169.99,
                originalPrice: 299.99,
                images: [
                    "https://images.unsplash.com/photo-1542291026-7eec264c27ff?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1606107557195-0e29a4b5b4aa?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1600185365926-3a2ce3cdb9eb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                ],
                rating: 4.9,
                reviews: 342,
                sold: 1200,
                stock: 8,
                badge: "OFERTA",
                description: "Zapatillas deportivas ultraligeras con suela de goma de alta tracción y plantilla extraíble. Diseñadas para máximo confort durante todo el día. Ideales para deporte y uso diario.",
                specs: {
                    "Material": "Malla transpirable, suela de goma",
                    "Color": "Blanco/Negro",
                    "Tallas": "36-45",
                    "Peso": "320g (par)",
                    "Cuidados": "Limpiar con paño húmedo",
                    "Origen": "Vietnam"
                },
                sizes: ['36', '37', '38', '39', '40', '41', '42', '43', '44', '45'],
                sizesStock: {
                    '36': 2,
                    '37': 3,
                    '38': 0,
                    '39': 5,
                    '40': 8,
                    '41': 4,
                    '42': 0,
                    '43': 6,
                    '44': 1,
                    '45': 0
                },
                isFavorite: false
            },
            {
                id: 3,
                name: "Chaqueta Vaquera Desgastada para Mujer",
                category: "Ropa de Mujer",
                price: 159.99,
                originalPrice: 269.99,
                images: [
                    "https://images.unsplash.com/photo-1591047139829-d91aecb6caea?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1548126032-079a0fb0099d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1591369822091-5aac1a1cbc4a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                ],
                rating: 4.5,
                reviews: 87,
                sold: 310,
                stock: 42,
                badge: "POPULAR",
                description: "Chaqueta vaquera estilo boyfriend con efecto desgastado. Cuello solapa y bolsillos delanteros funcionales. Corte moderno que favorece cualquier tipo de cuerpo.",
                specs: {
                    "Material": "Denim 98%, Elastano 2%",
                    "Color": "Azul claro desgastado",
                    "Tallas": "XS, S, M, L",
                    "Peso": "680g",
                    "Cuidados": "Lavable a máquina 30°",
                    "Origen": "Turquía"
                },
                sizes: ['XS', 'S', 'M', 'L'],
                sizesStock: {
                    'XS': 5,
                    'S': 15,
                    'M': 12,
                    'L': 10
                },
                isFavorite: false
            },
            {
                id: 4,
                name: "Camiseta Oversized Color Block",
                category: "Ropa de Mujer",
                price: 89.99,
                originalPrice: 139.99,
                images: [
                    "https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1617137968427-85924c800a22?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1594035910387-fea47794261f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                ],
                rating: 4.3,
                reviews: 56,
                sold: 210,
                stock: 15,
                badge: "NUEVO",
                description: "Camiseta oversized con diseño color block en tonos vibrantes. Corte moderno y cómodo para un look urbano y juvenil.",
                specs: {
                    "Material": "Algodón 95%, Elastano 5%",
                    "Color": "Blanco/Rosa/Azul",
                    "Tallas": "XS, S, M, L",
                    "Peso": "250g",
                    "Cuidados": "Lavable a máquina 30°",
                    "Origen": "España"
                },
                sizes: ['XS', 'S', 'M', 'L'],
                sizesStock: {
                    'XS': 3,
                    'S': 7,
                    'M': 4,
                    'L': 1
                },
                isFavorite: false
            },
            {
                id: 5,
                name: "Pantalones Cargo Jogger",
                category: "Ropa de Hombre",
                price: 139.99,
                originalPrice: 199.99,
                images: [
                    "https://images.unsplash.com/photo-1596755094514-f87e34085b2c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1604176354204-9268737828e4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1602810318383-e386cc2a3ccf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                ],
                rating: 4.6,
                reviews: 92,
                sold: 320,
                stock: 18,
                badge: "OFERTA",
                description: "Pantalones cargo jogger con tejido técnico y múltiples bolsillos. Diseño moderno y funcional para el día a día.",
                specs: {
                    "Material": "Poliéster 85%, Algodón 15%",
                    "Color": "Negro",
                    "Tallas": "S, M, L, XL",
                    "Peso": "380g",
                    "Cuidados": "Lavable a máquina 30°",
                    "Origen": "Marruecos"
                },
                sizes: ['S', 'M', 'L', 'XL'],
                sizesStock: {
                    'S': 3,
                    'M': 8,
                    'L': 5,
                    'XL': 2
                },
                isFavorite: false
            },
            {
                id: 6,
                name: "Vestido Midi con Estampado Floral",
                category: "Ropa de Mujer",
                price: 149.99,
                originalPrice: 239.99,
                images: [
                    "https://images.unsplash.com/photo-1539008835657-9e8e9680c956?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1618354691373-d851c5c3a990?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                    "https://images.unsplash.com/photo-1595777457583-95e059d581b8?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                ],
                rating: 4.8,
                reviews: 134,
                sold: 480,
                stock: 22,
                badge: "POPULAR",
                description: "Vestido midi con estampado floral y mangas abullonadas. Corte entallado en la cintura para una silueta favorecedora.",
                specs: {
                    "Material": "Viscosa 100%",
                    "Color": "Floral multicolor",
                    "Tallas": "XS, S, M, L",
                    "Peso": "320g",
                    "Cuidados": "Lavable a mano",
                    "Origen": "Italia"
                },
                sizes: ['XS', 'S', 'M', 'L'],
                sizesStock: {
                    'XS': 4,
                    'S': 10,
                    'M': 6,
                    'L': 2
                },
                isFavorite: false
            }
        ];
        
        // Carrito de compras
        let cart = [];
        let currentProduct = null;
        let currentCategory = "all";
        let visibleProducts = 6; // Mostrar todos inicialmente
        let selectedSize = null; // Talla seleccionada actualmente
        let favorites = []; // Lista de productos favoritos
        
        // Renderizar productos
        function renderProducts(productsToRender = products) {
            const productGrid = document.getElementById('product-grid');
            productGrid.innerHTML = '';
            
            if (productsToRender.length === 0) {
                productGrid.innerHTML = '<p class="no-results" style="grid-column: 1/-1; text-align: center; padding: 40px;">No se encontraron productos</p>';
                return;
            }
            
            productsToRender.forEach(product => {
                const discount = Math.round(((product.originalPrice - product.price) / product.originalPrice) * 100);
                
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    ${product.badge ? `<div class="product-badge">${product.badge}</div>` : ''}
                    <div class="product-image">
                        <img src="${product.images[0]}" alt="${product.name}">
                        <div class="quick-view" data-id="${product.id}">Vista rápida</div>
                    </div>
                    <div class="product-info">
                        <div class="product-category">${product.category}</div>
                        <h3 class="product-title">${product.name}</h3>
                        <div class="product-rating">
                            ${renderRating(product.rating)}
                            <span>${product.reviews} reviews</span>
                        </div>
                        <div class="product-price">
                            <div class="current-price">S/${product.price.toFixed(2)}</div>
                            <div class="original-price">S/${product.originalPrice.toFixed(2)}</div>
                            <div class="discount">-${discount}%</div>
                        </div>
                        <div class="product-stats">
                            <div>Vendidos: ${product.sold}</div>
                            <div>Stock: ${product.stock}</div>
                        </div>
                        <div class="product-actions">
                            <button class="add-to-cart" data-id="${product.id}">Añadir al carrito</button>
                            <button class="wishlist-btn ${product.isFavorite ? 'active' : ''}" data-id="${product.id}">
                                <i class="${product.isFavorite ? 'fas' : 'far'} fa-heart"></i>
                            </button>
                        </div>
                    </div>
                `;
                
                productGrid.appendChild(productCard);
                
                // Agregar evento de clic a la imagen del producto
                const productImage = productCard.querySelector('.product-image img');
                productImage.addEventListener('click', () => {
                    openProductDetail(product.id);
                });
            });
            
            // Event listeners para botones
            document.querySelectorAll('.add-to-cart').forEach(button => {
                button.addEventListener('click', addToCart);
            });
            
            document.querySelectorAll('.quick-view').forEach(button => {
                button.addEventListener('click', (e) => {
                    const productId = parseInt(e.target.dataset.id);
                    openProductDetail(productId);
                });
            });
            
            // Event listeners para botones de favoritos
            document.querySelectorAll('.wishlist-btn').forEach(button => {
                button.addEventListener('click', (e) => {
                    const productId = parseInt(button.dataset.id);
                    toggleFavorite(productId);
                    
                    // Actualizar el botón de favoritos
                    const icon = button.querySelector('i');
                    icon.classList.toggle('far');
                    icon.classList.toggle('fas');
                    button.classList.toggle('active');
                    
                    e.stopPropagation();
                });
            });
        }
        
        // Abrir vista detallada del producto
        function openProductDetail(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;
            
            currentProduct = product;
            selectedSize = null; // Resetear talla seleccionada
            
            // Actualizar contenido del modal
            document.getElementById('detail-title').textContent = product.name;
            document.getElementById('detail-category').textContent = product.category;
            document.getElementById('detail-rating').innerHTML = renderRating(product.rating);
            document.getElementById('detail-reviews').textContent = `${product.reviews} reviews`;
            document.getElementById('detail-price').textContent = `S/${product.price.toFixed(2)}`;
            document.getElementById('detail-original-price').textContent = `S/${product.originalPrice.toFixed(2)}`;
            document.getElementById('detail-discount').textContent = `-${Math.round(((product.originalPrice - product.price) / product.originalPrice) * 100)}%`;
            document.getElementById('detail-description').textContent = product.description;
            
            // Actualizar imágenes
            const thumbnailsContainer = document.getElementById('thumbnails');
            thumbnailsContainer.innerHTML = '';
            
            product.images.forEach((img, index) => {
                const thumbnail = document.createElement('div');
                thumbnail.className = 'thumbnail' + (index === 0 ? ' active' : '');
                thumbnail.innerHTML = `<img src="${img}" alt="Thumbnail ${index + 1}">`;
                thumbnail.addEventListener('click', () => {
                    document.querySelectorAll('.thumbnail').forEach(t => t.classList.remove('active'));
                    thumbnail.classList.add('active');
                    document.querySelector('.main-image img').src = img;
                });
                thumbnailsContainer.appendChild(thumbnail);
            });
            
            // Actualizar imagen principal
            const mainImage = document.querySelector('.main-image');
            mainImage.innerHTML = `<img src="${product.images[0]}" alt="${product.name}">`;
            
            // Actualizar especificaciones
            const specsGrid = document.getElementById('specs-grid');
            specsGrid.innerHTML = '';
            
            for (const [key, value] of Object.entries(product.specs)) {
                const specItem = document.createElement('div');
                specItem.className = 'spec-item';
                specItem.innerHTML = `
                    <div class="spec-label">${key}:</div>
                    <div class="spec-value">${value}</div>
                `;
                specsGrid.appendChild(specItem);
            }
            
            // Actualizar selector de tallas
            const sizeOptions = document.getElementById('size-options');
            sizeOptions.innerHTML = '';
            
            if (product.sizes && product.sizes.length > 0) {
                product.sizes.forEach(size => {
                    const isAvailable = product.sizesStock[size] > 0;
                    const sizeOption = document.createElement('div');
                    sizeOption.className = `size-option ${!isAvailable ? 'unavailable' : ''}`;
                    sizeOption.textContent = size;
                    sizeOption.dataset.size = size;
                    
                    if (isAvailable) {
                        sizeOption.addEventListener('click', () => {
                            // Deseleccionar todas las tallas
                            document.querySelectorAll('.size-option').forEach(option => {
                                option.classList.remove('selected');
                            });
                            
                            // Seleccionar la talla actual
                            sizeOption.classList.add('selected');
                            selectedSize = size;
                        });
                    }
                    
                    sizeOptions.appendChild(sizeOption);
                });
            } else {
                sizeOptions.innerHTML = '<p>Este producto no requiere selección de talla</p>';
            }
            
            // Actualizar estado de favorito en vista detallada
            const wishlistDetail = document.getElementById('detail-wishlist');
            wishlistDetail.className = `wishlist-detail ${product.isFavorite ? 'active' : ''}`;
            wishlistDetail.innerHTML = `<i class="${product.isFavorite ? 'fas' : 'far'} fa-heart"></i>`;
            
            wishlistDetail.addEventListener('click', () => {
                toggleFavorite(product.id);
                wishlistDetail.classList.toggle('active');
                const icon = wishlistDetail.querySelector('i');
                icon.classList.toggle('far');
                icon.classList.toggle('fas');
                
                // Actualizar también en la lista de productos
                renderProducts();
            });
            
            // Mostrar modal
            document.getElementById('product-modal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }
        
        // Renderizar estrellas de valoración
        function renderRating(rating) {
            let stars = '';
            for (let i = 1; i <= 5; i++) {
                if (i <= Math.floor(rating)) {
                    stars += '<i class="fas fa-star"></i>';
                } else if (i - 0.5 <= rating) {
                    stars += '<i class="fas fa-star-half-alt"></i>';
                } else {
                    stars += '<i class="far fa-star"></i>';
                }
            }
            return stars;
        }
        
        // Añadir al carrito
        function addToCart(e) {
            const productId = parseInt(e.target.dataset.id);
            const product = products.find(p => p.id === productId);
            
            // Si el producto requiere talla pero no se ha seleccionado una
            if (product.sizes && product.sizes.length > 0 && !selectedSize) {
                showNotification('Por favor selecciona una talla');
                openProductDetail(productId); // Abrir vista rápida para seleccionar talla
                return;
            }
            
            // Verificar si ya está en el carrito (mismo producto y misma talla)
            const existingItemIndex = cart.findIndex(item => 
                item.id === productId && 
                item.size === selectedSize
            );
            
            if (existingItemIndex !== -1) {
                // Incrementar cantidad si existe
                cart[existingItemIndex].quantity += 1;
            } else {
                // Añadir nuevo elemento al carrito
                cart.push({
                    ...product,
                    quantity: 1,
                    size: selectedSize || 'Única' // Usar 'Única' si no hay tallas
                });
            }
            
            // Actualizar stock de la talla seleccionada
            if (selectedSize && product.sizesStock[selectedSize] > 0) {
                product.sizesStock[selectedSize] -= 1;
            }
            
            // Mostrar notificación
            const sizeText = selectedSize ? ` (Talla: ${selectedSize})` : '';
            showNotification(`"${product.name}"${sizeText} añadido al carrito`);
            
            // Actualizar contador del carrito
            updateCartCount();
        }
        
        // Actualizar contador del carrito
        function updateCartCount() {
            const totalItems = cart.reduce((total, item) => total + item.quantity, 0);
            document.querySelector('.cart-btn .cart-count').textContent = totalItems;
        }
        
        // Renderizar carrito
        function renderCart() {
            const cartItems = document.getElementById('cart-items');
            const cartTotal = document.getElementById('cart-total-price');
            
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                cartItems.innerHTML = '<p style="text-align: center; padding: 40px;">Tu carrito está vacío</p>';
                cartTotal.textContent = 'S/0.00';
                return;
            }
            
            let total = 0;
            
            cart.forEach((item, index) => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                cartItem.innerHTML = `
                    <div class="cart-item-img">
                        <img src="${item.images[0]}" alt="${item.name}">
                    </div>
                    <div class="cart-item-details">
                        <div class="cart-item-title">${item.name}</div>
                        <div class="cart-item-price">S/${item.price.toFixed(2)}</div>
                        
                        <!-- Nueva sección para mostrar y cambiar talla -->
                        <div class="cart-item-size">
                            <label>Talla:</label>
                            <select class="size-selector" data-index="${index}">
                                ${item.sizes ? item.sizes.map(size => 
                                    `<option value="${size}" ${item.size === size ? 'selected' : ''} 
                                    ${item.sizesStock[size] <= 0 ? 'disabled' : ''}>
                                        ${size}${item.sizesStock[size] <= 0 ? ' (Agotado)' : ''}
                                    </option>`
                                ).join('') : '<option>Única</option>'}
                            </select>
                        </div>
                        
                        <div class="cart-item-quantity">
                            <button class="decrease-quantity" data-index="${index}">-</button>
                            <input type="text" value="${item.quantity}" readonly>
                            <button class="increase-quantity" data-index="${index}">+</button>
                        </div>
                        <div class="cart-item-remove" data-index="${index}">Eliminar</div>
                    </div>
                `;
                
                cartItems.appendChild(cartItem);
            });
            
            cartTotal.textContent = `S/${total.toFixed(2)}`;
            
            // Agregar event listeners para botones del carrito
            document.querySelectorAll('.decrease-quantity').forEach(button => {
                button.addEventListener('click', (e) => {
                    const index = parseInt(e.target.dataset.index);
                    updateQuantity(index, -1);
                });
            });
            
            document.querySelectorAll('.increase-quantity').forEach(button => {
                button.addEventListener('click', (e) => {
                    const index = parseInt(e.target.dataset.index);
                    updateQuantity(index, 1);
                });
            });
            
            document.querySelectorAll('.cart-item-remove').forEach(button => {
                button.addEventListener('click', (e) => {
                    const index = parseInt(e.target.dataset.index);
                    removeFromCart(index);
                });
            });
            
            // Event listeners para cambiar talla en el carrito
            document.querySelectorAll('.size-selector').forEach(select => {
                select.addEventListener('change', (e) => {
                    const index = parseInt(e.target.dataset.index);
                    const newSize = e.target.value;
                    changeSize(index, newSize);
                });
            });
        }
        
        // Cambiar talla de un producto en el carrito
        function changeSize(index, newSize) {
            const item = cart[index];
            
            // Verificar si hay stock disponible
            if (item.sizesStock[newSize] <= 0) {
                showNotification('Esta talla no está disponible');
                return;
            }
            
            // Actualizar stock
            if (item.size) {
                item.sizesStock[item.size] += item.quantity; // Devolver stock anterior
            }
            
            item.size = newSize;
            item.sizesStock[newSize] -= item.quantity; // Reservar nueva talla
            
            showNotification(`Talla cambiada a ${newSize}`);
            renderCart(); // Actualizar vista del carrito
        }
        
        // Actualizar cantidad en el carrito
        function updateQuantity(index, change) {
            const item = cart[index];
            
            // Verificar stock disponible para la talla seleccionada
            if (change > 0 && item.sizesStock[item.size] < item.quantity + 1) {
                showNotification('No hay suficiente stock disponible');
                return;
            }
            
            // Actualizar cantidad
            item.quantity += change;
            
            if (item.quantity < 1) {
                cart.splice(index, 1);
            } else {
                // Actualizar stock
                item.sizesStock[item.size] -= change;
            }
            
            renderCart();
            updateCartCount();
        }
        
        // Eliminar del carrito
        function removeFromCart(index) {
            const item = cart[index];
            
            // Devolver stock al eliminar
            if (item.size && item.sizesStock[item.size]) {
                item.sizesStock[item.size] += item.quantity;
            }
            
            cart.splice(index, 1);
            renderCart();
            updateCartCount();
            showNotification('Producto eliminado del carrito');
        }
        
        // Añadir/eliminar de favoritos
        function toggleFavorite(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;
            
            product.isFavorite = !product.isFavorite;
            
            // Actualizar contador de favoritos
            updateFavoritesCount();
            
            // Actualizar icono en la tarjeta del producto
            const wishlistBtn = document.querySelector(`.wishlist-btn[data-id="${productId}"]`);
            if (wishlistBtn) {
                wishlistBtn.classList.toggle('active');
                const icon = wishlistBtn.querySelector('i');
                icon.classList.toggle('far');
                icon.classList.toggle('fas');
            }
            
            // Mostrar notificación
            const action = product.isFavorite ? 'añadido a' : 'eliminado de';
            showNotification(`Producto ${action} favoritos`);
        }
        
        // Actualizar contador de favoritos
        function updateFavoritesCount() {
            const favoritesCount = document.getElementById('favorites-count');
            const count = products.filter(p => p.isFavorite).length;
            favoritesCount.textContent = count;
        }
        
        // Renderizar favoritos
        function renderFavorites() {
            const favoritesItems = document.getElementById('favorites-items');
            favoritesItems.innerHTML = '';
            
            const favoriteProducts = products.filter(p => p.isFavorite);
            
            if (favoriteProducts.length === 0) {
                favoritesItems.innerHTML = '<p style="text-align: center; padding: 40px;">No tienes productos favoritos</p>';
                return;
            }
            
            favoriteProducts.forEach(product => {
                const discount = Math.round(((product.originalPrice - product.price) / product.originalPrice) * 100);
                
                const favoriteItem = document.createElement('div');
                favoriteItem.className = 'favorite-item';
                favoriteItem.innerHTML = `
                    <div class="favorite-item-img">
                        <img src="${product.images[0]}" alt="${product.name}">
                    </div>
                    <div class="favorite-item-details">
                        <div class="favorite-item-title">${product.name}</div>
                        <div class="favorite-item-price">S/${product.price.toFixed(2)}</div>
                        <div class="favorite-item-actions">
                            <button class="add-to-cart-from-fav" data-id="${product.id}">Añadir al carrito</button>
                            <button class="remove-from-fav" data-id="${product.id}">Eliminar</button>
                        </div>
                    </div>
                `;
                
                favoritesItems.appendChild(favoriteItem);
            });
            
            // Event listeners para botones en favoritos
            document.querySelectorAll('.add-to-cart-from-fav').forEach(button => {
                button.addEventListener('click', (e) => {
                    const productId = parseInt(e.target.dataset.id);
                    const product = products.find(p => p.id === productId);
                    if (!product) return;
                    
                    // Verificar si el producto requiere talla
                    if (product.sizes && product.sizes.length > 0) {
                        showNotification('Por favor selecciona una talla en la vista detallada');
                        openProductDetail(productId);
                    } else {
                        // Añadir directamente al carrito
                        const existingItemIndex = cart.findIndex(item => item.id === productId);
                        
                        if (existingItemIndex !== -1) {
                            cart[existingItemIndex].quantity += 1;
                        } else {
                            cart.push({
                                ...product,
                                quantity: 1,
                                size: 'Única'
                            });
                        }
                        
                        showNotification(`"${product.name}" añadido al carrito`);
                        updateCartCount();
                    }
                });
            });
            
            document.querySelectorAll('.remove-from-fav').forEach(button => {
                button.addEventListener('click', (e) => {
                    const productId = parseInt(e.target.dataset.id);
                    toggleFavorite(productId);
                    renderFavorites(); // Volver a renderizar favoritos
                });
            });
        }
        
        // Mostrar notificación
        function showNotification(message) {
            const notification = document.createElement('div');
            notification.className = 'notification';
            notification.textContent = message;
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.remove();
            }, 3000);
        }
        
        // Implementar funcionalidad de búsqueda
        function setupSearch() {
            const searchBtn = document.querySelector('.search-btn');
            const searchInput = document.querySelector('.search-container input');
            
            searchBtn.addEventListener('click', searchProducts);
            searchInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    searchProducts();
                }
            });
        }
        
        function searchProducts() {
            const searchInput = document.querySelector('.search-container input');
            const searchTerm = searchInput.value.toLowerCase().trim();
            
            const filteredProducts = products.filter(product => 
                product.name.toLowerCase().includes(searchTerm) ||
                product.category.toLowerCase().includes(searchTerm) ||
                product.description.toLowerCase().includes(searchTerm)
            );
            
            renderProducts(filteredProducts);
        }
        
        // Aplicar filtros con botón
        function applyFilters() {
            const category = document.getElementById('category').value;
            const price = document.getElementById('price').value;
            const sort = document.getElementById('sort').value;
            
            let filteredProducts = [...products];
            
            // Filtrar por categoría
            if (category !== "all") {
                filteredProducts = filteredProducts.filter(product => product.category === category);
            }
            
            // Filtrar por precio
            if (price === "0-50") {
                filteredProducts = filteredProducts.filter(product => product.price < 50);
            } else if (price === "50-100") {
                filteredProducts = filteredProducts.filter(product => product.price >= 50 && product.price <= 100);
            } else if (price === "100-200") {
                filteredProducts = filteredProducts.filter(product => product.price > 100 && product.price <= 200);
            } else if (price === "200+") {
                filteredProducts = filteredProducts.filter(product => product.price > 200);
            }
            
            // Ordenar
            if (sort === "popular") {
                filteredProducts.sort((a, b) => b.sold - a.sold);
            } else if (sort === "newest") {
                filteredProducts.sort((a, b) => b.id - a.id);
            } else if (sort === "price-asc") {
                filteredProducts.sort((a, b) => a.price - b.price);
            } else if (sort === "price-desc") {
                filteredProducts.sort((a, b) => b.price - a.price);
            } else if (sort === "rating") {
                filteredProducts.sort((a, b) => b.rating - a.rating);
            }
            
            renderProducts(filteredProducts);
        }
        
        // Filtrar por categoría desde la barra de navegación
        function filterByCategory(category) {
            currentCategory = category;
            
            // Actualizar estado activo en la barra de navegación
            document.querySelectorAll('.category-link').forEach(link => {
                link.classList.remove('active');
                if (link.dataset.category === category) {
                    link.classList.add('active');
                }
            });
            
            // Actualizar título de la sección
            const sectionTitle = document.querySelector('.section-title');
            if (category === "all") {
                sectionTitle.textContent = "Tendencias del Momento";
            } else {
                sectionTitle.textContent = `Productos: ${category}`;
            }
            
            // Filtrar productos
            let filteredProducts;
            if (category === "all") {
                filteredProducts = products;
            } else if (category === "Ofertas") {
                filteredProducts = products.filter(product => product.originalPrice > product.price);
            } else if (category === "Novedades") {
                filteredProducts = products.filter(product => product.badge === "NUEVO");
            } else {
                filteredProducts = products.filter(product => product.category === category);
            }
            
            renderProducts(filteredProducts);
        }
        
        // Implementar funcionalidad de cargar más productos
        function setupLoadMore() {
            const loadMoreBtn = document.getElementById('load-more');
            
            // Ocultar botón si se muestran todos los productos
            if (visibleProducts >= products.length) {
                loadMoreBtn.style.display = 'none';
            }
            
            loadMoreBtn.addEventListener('click', () => {
                visibleProducts = Math.min(visibleProducts + 3, products.length);
                
                // Ocultar botón si se muestran todos los productos
                if (visibleProducts >= products.length) {
                    loadMoreBtn.style.display = 'none';
                }
            });
        }
        
        // Inicializar
        document.addEventListener('DOMContentLoaded', () => {
            renderProducts();
            setupSearch();
            setupLoadMore();
            updateFavoritesCount();
            updateCartCount();
            
            // Botón para aplicar filtros
            document.getElementById('apply-filters').addEventListener('click', applyFilters);
            
            // Filtros por categoría en la barra de navegación
            document.querySelectorAll('.category-link').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    filterByCategory(this.dataset.category);
                });
            });
            
            // Cerrar modal de producto
            document.getElementById('close-product').addEventListener('click', () => {
                document.getElementById('product-modal').classList.remove('active');
                document.body.style.overflow = 'auto';
            });
            
            // Cerrar al hacer clic fuera del modal de producto
            document.getElementById('product-modal').addEventListener('click', (e) => {
                if (e.target === document.getElementById('product-modal')) {
                    document.getElementById('product-modal').classList.remove('active');
                    document.body.style.overflow = 'auto';
                }
            });
            
            // Funcionalidad del selector de cantidad
            document.querySelectorAll('.quantity-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const input = this.parentNode.querySelector('.quantity-input');
                    let value = parseInt(input.value);
                    
                    if (this.classList.contains('minus') && value > 1) {
                        input.value = value - 1;
                    } else if (this.classList.contains('plus')) {
                        input.value = value + 1;
                    }
                });
            });
            
            // Añadir al carrito desde la vista detallada
            document.getElementById('add-to-cart-detail').addEventListener('click', () => {
                if (!currentProduct) return;
                
                const quantityInput = document.querySelector('.quantity-input');
                const quantity = parseInt(quantityInput.value);
                
                // Validar que se ha seleccionado una talla si es necesario
                if (currentProduct.sizes && currentProduct.sizes.length > 0 && !selectedSize) {
                    showNotification('Por favor selecciona una talla');
                    return;
                }
                
                // Verificar stock
                if (selectedSize && currentProduct.sizesStock[selectedSize] < quantity) {
                    showNotification('No hay suficiente stock disponible');
                    return;
                }
                
                // Buscar si ya existe el mismo producto con la misma talla en el carrito
                const existingItemIndex = cart.findIndex(item => 
                    item.id === currentProduct.id && 
                    item.size === selectedSize
                );
                
                if (existingItemIndex !== -1) {
                    // Actualizar cantidad si ya existe
                    cart[existingItemIndex].quantity += quantity;
                } else {
                    // Añadir nuevo elemento al carrito
                    cart.push({
                        ...currentProduct,
                        quantity: quantity,
                        size: selectedSize || 'Única'
                    });
                }
                
                // Actualizar stock
                if (selectedSize) {
                    currentProduct.sizesStock[selectedSize] -= quantity;
                }
                
                const sizeText = selectedSize ? ` (Talla: ${selectedSize})` : '';
                showNotification(`"${currentProduct.name}"${sizeText} añadido al carrito`);
                updateCartCount();
            });
            
            // Abrir carrito
            document.getElementById('open-cart').addEventListener('click', () => {
                renderCart();
                document.getElementById('cart-modal').classList.add('active');
                document.getElementById('modal-overlay').classList.add('active');
            });
            
            // Cerrar carrito
            document.getElementById('close-cart').addEventListener('click', () => {
                document.getElementById('cart-modal').classList.remove('active');
                document.getElementById('modal-overlay').classList.remove('active');
            });
            
            // Continuar comprando
            document.getElementById('continue-shopping').addEventListener('click', () => {
                document.getElementById('cart-modal').classList.remove('active');
                document.getElementById('modal-overlay').classList.remove('active');
            });
            
            // Abrir favoritos
            document.getElementById('open-favorites').addEventListener('click', () => {
                renderFavorites();
                document.getElementById('favorites-modal').classList.add('active');
                document.getElementById('modal-overlay').classList.add('active');
            });
            
            // Cerrar favoritos
            document.getElementById('close-favorites').addEventListener('click', () => {
                document.getElementById('favorites-modal').classList.remove('active');
                document.getElementById('modal-overlay').classList.remove('active');
            });
            
            // Abrir modal de contacto desde footer
            document.getElementById('footer-contact').addEventListener('click', (e) => {
                e.preventDefault();
                document.getElementById('contact-modal').classList.add('active');
                document.getElementById('modal-overlay').classList.add('active');
            });
            
            // Cerrar modal de contacto
            document.getElementById('close-contact').addEventListener('click', () => {
                document.getElementById('contact-modal').classList.remove('active');
                document.getElementById('modal-overlay').classList.remove('active');
            });
            
            // Cerrar modales al hacer clic en el overlay
             document.getElementById('modal-overlay').addEventListener('click', () => {
                document.getElementById('product-modal').classList.remove('active');
                document.getElementById('cart-modal').classList.remove('active');
                document.getElementById('favorites-modal').classList.remove('active');
                document.getElementById('contact-modal').classList.remove('active');
                document.getElementById('modal-overlay').classList.remove('active');
            });
        });
    </script>
</body>
</html>
