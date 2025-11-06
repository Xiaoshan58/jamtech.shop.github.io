<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tetho's Home - Authentic Japanese Cuisine</title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400;500;700&family=Noto+Serif+JP:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary: #d32f2f;
            --secondary: #5d4037;
            --dark: #212121;
            --light: #f5f5f5;
            --accent: #ffc107;
            --success: #2e7d32;
            --warning: #ed6c02;
            --admin-color: #3f51b5;
        }
        
        body {
            background-color: #f8f5f2;
            color: #333;
            font-family: 'Noto Sans JP', sans-serif;
            line-height: 1.6;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        header {
            background-color: var(--dark);
            color: white;
            padding: 12px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
            transition: transform 0.3s;
        }
        
        .logo:hover {
            transform: scale(1.05);
        }
        
        .logo-icon {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            position: relative;
            overflow: hidden;
            transition: transform 0.5s;
        }
        
        .logo-icon:hover {
            transform: scale(1.1);
        }
        
        .logo-icon::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: rgba(255,255,255,0.1);
            transform: rotate(45deg);
            transition: all 0.5s;
        }
        
        .logo:hover .logo-icon::before {
            left: 100%;
        }
        
        .logo-icon img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
        }
        
        .logo-text {
            display: flex;
            flex-direction: column;
            line-height: 1.1;
        }
        
        .logo-main {
            font-size: 1.5rem;
        }
        
        .logo-sub {
            font-size: 0.7rem;
            color: #aaa;
            font-weight: 400;
        }
        
        .contact-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .contact-info a {
            color: white;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 6px;
            font-weight: 500;
            transition: color 0.3s;
            font-size: 0.9rem;
        }
        
        .contact-info a:hover {
            color: var(--primary);
        }
        
        .admin-login-btn {
            background-color: var(--admin-color);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 6px;
            z-index: 1000;
            position: relative;
        }
        
        .admin-login-btn:hover {
            background-color: #303f9f;
            transform: translateY(-2px);
        }
        
        .hero {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 80px 0;
            text-align: center;
            position: relative;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at center, transparent 0%, rgba(0,0,0,0.4) 100%);
            z-index: 1;
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.7);
            animation: fadeInDown 1s ease-out;
            font-family: 'Noto Serif JP', serif;
        }
        
        .hero p {
            font-size: 1.1rem;
            max-width: 90%;
            margin: 0 auto 25px;
            text-shadow: 1px 1px 4px rgba(0,0,0,0.7);
            animation: fadeInUp 1s ease-out 0.3s both;
        }
        
        .delivery-badge {
            display: inline-block;
            background-color: var(--primary);
            color: white;
            padding: 10px 20px;
            border-radius: 30px;
            font-weight: 700;
            margin-top: 20px;
            box-shadow: 0 6px 12px rgba(0,0,0,0.3);
            animation: fadeInUp 1s ease-out 0.6s both;
            transition: transform 0.3s, box-shadow 0.3s;
            font-size: 0.95rem;
        }
        
        .delivery-badge:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 16px rgba(0,0,0,0.4);
        }
        
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .features {
            padding: 50px 0;
            background-color: white;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 40px;
            color: var(--dark);
        }
        
        .section-title h2 {
            font-size: 2rem;
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
            font-family: 'Noto Serif JP', serif;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background-color: var(--primary);
            border-radius: 2px;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }
        
        .feature-card {
            background-color: var(--light);
            padding: 25px 20px;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.4s, box-shadow 0.4s;
            position: relative;
            overflow: hidden;
        }
        
        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
        }
        
        .feature-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        
        .feature-icon {
            font-size: 2.8rem;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .feature-card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        .feature-card p {
            color: #666;
            line-height: 1.6;
            font-size: 0.95rem;
        }
        
        .menu {
            padding: 50px 0;
            background-color: #f8f5f2;
        }
        
        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
        }
        
        .menu-item {
            background-color: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            transition: transform 0.4s, box-shadow 0.4s;
            position: relative;
            display: flex;
            flex-direction: column;
            height: 420px;
        }
        
        .menu-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(211,47,47,0.05) 0%, rgba(255,193,7,0.05) 100%);
            opacity: 0;
            transition: opacity 0.3s;
            z-index: 1;
        }
        
        .menu-item:hover::before {
            opacity: 1;
        }
        
        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.12);
        }
        
        .menu-image-container {
            height: 200px;
            overflow: hidden;
            flex-shrink: 0;
        }
        
        .menu-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .menu-item:hover img {
            transform: scale(1.05);
        }
        
        .menu-content {
            padding: 20px;
            position: relative;
            z-index: 2;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }
        
        .menu-title {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--dark);
            font-weight: 700;
            flex-shrink: 0;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
            text-overflow: ellipsis;
            min-height: 2.6rem;
        }
        
        .menu-description {
            color: #666;
            margin-bottom: 15px;
            font-size: 0.9rem;
            line-height: 1.5;
            flex-grow: 1;
            overflow: hidden;
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
        }
        
        .menu-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-shrink: 0;
            margin-top: auto;
        }
        
        .price {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .order-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 12px 18px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            font-size: 0.95rem;
            text-decoration: none;
            display: inline-block;
            text-align: center;
        }
        
        .order-btn:hover {
            background-color: #b71c1c;
            transform: translateY(-2px);
            box-shadow: 0 5px 10px rgba(211,47,47,0.3);
        }
        
        .delivery {
            padding: 50px 0;
            background-color: white;
        }
        
        .delivery-container {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            align-items: center;
        }
        
        .delivery-image {
            flex: 1;
            min-width: 100%;
        }
        
        .delivery-image img {
            width: 100%;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
            transition: transform 0.5s;
        }
        
        .delivery-image:hover img {
            transform: scale(1.02);
        }
        
        .delivery-content {
            flex: 1;
            min-width: 100%;
        }
        
        .delivery-content h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--dark);
            position: relative;
            display: inline-block;
            font-family: 'Noto Serif JP', serif;
        }
        
        .delivery-content h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 50px;
            height: 4px;
            background-color: var(--primary);
            border-radius: 2px;
        }
        
        .delivery-content p {
            margin-bottom: 20px;
            font-size: 1rem;
            line-height: 1.7;
            color: #555;
        }
        
        .app-list {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 25px;
        }
        
        .app-badge {
            display: flex;
            align-items: center;
            gap: 10px;
            background-color: var(--light);
            padding: 12px 18px;
            border-radius: 10px;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 3px 8px rgba(0,0,0,0.05);
            font-size: 0.9rem;
        }
        
        .app-badge:hover {
            background-color: #e9ecef;
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.1);
        }
        
        .app-badge i {
            font-size: 1.5rem;
            color: var(--primary);
        }
        
        .contact {
            padding: 50px 0;
            background: linear-gradient(135deg, var(--dark) 0%, #424242 100%);
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .contact::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(211,47,47,0.1) 0%, transparent 70%);
            z-index: 1;
        }
        
        .contact-container {
            position: relative;
            z-index: 2;
        }
        
        .contact h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            font-family: 'Noto Serif JP', serif;
        }
        
        .contact-info-large {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            margin: 25px 0;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            padding: 12px 25px;
            background-color: rgba(255,255,255,0.1);
            border-radius: 15px;
            backdrop-filter: blur(10px);
            transition: transform 0.3s, background-color 0.3s;
        }
        
        .contact-info-large:hover {
            transform: translateY(-5px);
            background-color: rgba(255,255,255,0.15);
        }
        
        .contact-note {
            max-width: 90%;
            margin: 0 auto;
            font-size: 1rem;
            opacity: 0.9;
            line-height: 1.7;
        }
        
        footer {
            background-color: var(--secondary);
            color: #f5f5f5;
            padding: 30px 0;
            text-align: center;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .footer-logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            margin-bottom: 10px;
        }
        
        .footer-logo-icon {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: white;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.9rem;
            overflow: hidden;
        }
        
        .footer-logo-icon img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
        }
        
        .footer-logo-text {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
        }
        
        .social-links a {
            color: #f5f5f5;
            font-size: 1.5rem;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 45px;
            height: 45px;
            background-color: rgba(255,255,255,0.05);
            border-radius: 50%;
        }
        
        .social-links a:hover {
            color: var(--primary);
            background-color: rgba(211,47,47,0.1);
            transform: translateY(-3px);
        }
        
        .cart-summary {
            position: fixed;
            bottom: 80px;
            right: 20px;
            background-color: var(--primary);
            color: white;
            padding: 15px;
            border-radius: 50px;
            display: flex;
            align-items: center;
            gap: 15px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            cursor: pointer;
            transition: all 0.3s;
            z-index: 999;
        }
        
        .cart-summary:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
        }
        
        .cart-icon {
            font-size: 1.5rem;
        }
        
        .cart-info {
            display: flex;
            flex-direction: column;
        }
        
        .cart-count {
            font-size: 0.9rem;
            font-weight: 600;
        }
        
        .cart-total {
            font-size: 1.1rem;
            font-weight: 700;
        }
        
        .quantity-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 3000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }
        
        .quantity-modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal-content {
            background-color: white;
            border-radius: 15px;
            padding: 30px;
            max-width: 400px;
            width: 90%;
            text-align: center;
            position: relative;
        }
        
        .modal-close {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #666;
            transition: color 0.3s;
        }
        
        .modal-close:hover {
            color: var(--primary);
        }
        
        .modal-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--dark);
        }
        
        .menu-name {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .quantity-selector {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin: 25px 0;
        }
        
        .quantity-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .quantity-btn:hover {
            background-color: #b71c1c;
            transform: scale(1.1);
        }
        
        .quantity-input {
            width: 70px;
            text-align: center;
            font-size: 1.5rem;
            font-weight: 700;
            padding: 8px;
            border: 2px solid var(--light);
            border-radius: 8px;
        }
        
        .modal-actions {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 25px;
        }
        
        .modal-btn {
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1rem;
        }
        
        .confirm-btn {
            background-color: var(--success);
            color: white;
        }
        
        .confirm-btn:hover {
            background-color: #1b5e20;
            transform: translateY(-2px);
            box-shadow: 0 5px 10px rgba(46,125,50,0.3);
        }
        
        .cancel-btn {
            background-color: #e0e0e0;
            color: #666;
        }
        
        .cancel-btn:hover {
            background-color: #d0d0d0;
        }
        
        .cart-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 4000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }
        
        .cart-modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        .cart-modal-content {
            background-color: white;
            border-radius: 15px;
            padding: 30px;
            max-width: 600px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
            position: relative;
        }
        
        .cart-modal-close {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #666;
            transition: color 0.3s;
        }
        
        .cart-modal-close:hover {
            color: var(--primary);
        }
        
        .cart-modal-title {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--dark);
            text-align: center;
            font-family: 'Noto Serif JP', serif;
        }
        
        .cart-items-container {
            margin-bottom: 20px;
        }
        
        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            border-bottom: 1px solid #eee;
        }
        
        .cart-item-info {
            flex: 1;
        }
        
        .cart-item-name {
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--dark);
            margin-bottom: 5px;
        }
        
        .cart-item-price {
            font-size: 0.95rem;
            color: #666;
        }
        
        .cart-item-actions {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .cart-item-quantity {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .cart-item-total {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--primary);
            min-width: 80px;
            text-align: right;
        }
        
        .cart-modal-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-top: 20px;
            border-top: 1px solid #eee;
        }
        
        .cart-modal-total {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .cart-modal-actions {
            display: flex;
            gap: 10px;
        }
        
        .clear-cart-btn {
            background-color: #e0e0e0;
            color: #666;
        }
        
        .clear-cart-btn:hover {
            background-color: #d0d0d0;
        }
        
        .send-order-btn {
            background-color: var(--success);
            color: white;
        }
        
        .send-order-btn:hover {
            background-color: #1b5e20;
        }
        
        .empty-cart-message {
            text-align: center;
            padding: 30px;
            color: #666;
            font-style: italic;
        }
        
        .loading-indicator {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
        }
        
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
        
        .admin-login-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 5000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }
        
        .admin-login-modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        .admin-login-content {
            background-color: white;
            border-radius: 15px;
            padding: 40px;
            max-width: 450px;
            width: 90%;
            text-align: center;
            position: relative;
        }
        
        .admin-login-title {
            font-size: 1.8rem;
            margin-bottom: 30px;
            color: var(--admin-color);
            font-family: 'Noto Serif JP', serif;
        }
        
        .form-group {
            margin-bottom: 20px;
            text-align: left;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }
        
        .form-group input {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }
        
        .form-group input:focus {
            outline: none;
            border-color: var(--admin-color);
        }
        
        .admin-login-actions {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 30px;
        }
        
        .admin-login-btn {
            background-color: var(--admin-color);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1rem;
        }
        
        .admin-login-btn:hover {
            background-color: #303f9f;
            transform: translateY(-2px);
            box-shadow: 0 5px 10px rgba(63,81,181,0.3);
        }
        
        .admin-cancel-btn {
            background-color: #e0e0e0;
            color: #666;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1rem;
        }
        
        .admin-cancel-btn:hover {
            background-color: #d0d0d0;
        }
        
        .error-message {
            color: var(--primary);
            margin-top: 15px;
            font-size: 0.9rem;
            display: none;
        }
        
        .admin-panel {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: #f5f5f5;
            z-index: 6000;
            overflow-y: auto;
            display: none;
        }
        
        .admin-panel.active {
            display: block;
        }
        
        .admin-header {
            background-color: var(--admin-color);
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .admin-header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .admin-logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.5rem;
            font-weight: 700;
        }
        
        .admin-nav {
            display: flex;
            gap: 20px;
        }
        
        .admin-nav-item {
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .admin-nav-item:hover {
            background-color: rgba(255,255,255,0.1);
        }
        
        .admin-nav-item.active {
            background-color: rgba(255,255,255,0.2);
        }
        
        .admin-logout {
            background-color: rgba(255,255,255,0.2);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .admin-logout:hover {
            background-color: rgba(255,255,255,0.3);
        }
        
        .admin-content {
            padding: 30px 0;
        }
        
        .admin-section {
            display: none;
        }
        
        .admin-section.active {
            display: block;
        }
        
        .admin-section-title {
            font-size: 1.8rem;
            margin-bottom: 25px;
            color: var(--dark);
            font-family: 'Noto Serif JP', serif;
        }
        
        .admin-card {
            background-color: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 25px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .admin-card-title {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--dark);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .admin-btn {
            background-color: var(--admin-color);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            font-size: 0.95rem;
        }
        
        .admin-btn:hover {
            background-color: #303f9f;
            transform: translateY(-2px);
            box-shadow: 0 5px 10px rgba(63,81,181,0.3);
        }
        
        .admin-btn-danger {
            background-color: var(--primary);
        }
        
        .admin-btn-danger:hover {
            background-color: #b71c1c;
            box-shadow: 0 5px 10px rgba(211,47,47,0.3);
        }
        
        .admin-form {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        
        .admin-form-group {
            margin-bottom: 20px;
        }
        
        .admin-form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }
        
        .admin-form-group input,
        .admin-form-group textarea,
        .admin-form-group select {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }
        
        .admin-form-group input:focus,
        .admin-form-group textarea:focus,
        .admin-form-group select:focus {
            outline: none;
            border-color: var(--admin-color);
        }
        
        .admin-form-group textarea {
            resize: vertical;
            min-height: 100px;
        }
        
        .admin-form-actions {
            display: flex;
            gap: 15px;
            justify-content: flex-end;
            margin-top: 20px;
        }
        
        .admin-menu-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .admin-menu-item {
            background-color: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }
        
        .admin-menu-item:hover {
            transform: translateY(-5px);
        }
        
        .admin-menu-image {
            height: 150px;
            overflow: hidden;
        }
        
        .admin-menu-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .admin-menu-content {
            padding: 20px;
        }
        
        .admin-menu-title {
            font-size: 1.2rem;
            margin-bottom: 10px;
            color: var(--dark);
        }
        
        .admin-menu-price {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 15px;
        }
        
        .admin-menu-actions {
            display: flex;
            gap: 10px;
        }
        
        .admin-edit-btn {
            background-color: var(--warning);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            font-size: 0.9rem;
        }
        
        .admin-edit-btn:hover {
            background-color: #e65100;
            transform: translateY(-2px);
        }
        
        .admin-delete-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            font-size: 0.9rem;
        }
        
        .admin-delete-btn:hover {
            background-color: #b71c1c;
            transform: translateY(-2px);
        }
        
        .admin-image-upload {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .admin-image-preview {
            width: 150px;
            height: 150px;
            border: 2px dashed #ccc;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }
        
        .admin-image-preview img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }
        
        .admin-image-upload-btn {
            background-color: var(--light);
            color: var(--dark);
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .admin-image-upload-btn:hover {
            background-color: #e0e0e0;
        }
        
        .admin-success-message {
            background-color: var(--success);
            color: white;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            display: none;
        }
        
        .admin-error-message {
            background-color: var(--primary);
            color: white;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            display: none;
        }
        
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .delivery-container {
                flex-direction: column;
            }
            
            .contact-info-large {
                font-size: 1.5rem;
            }
            
            .order-btn {
                padding: 14px 20px;
                font-size: 1rem;
                min-width: 100px;
            }
            
            .menu-grid {
                grid-template-columns: 1fr;
            }
            
            .menu-item {
                max-width: 400px;
                margin: 0 auto;
                height: 380px;
            }
            
            .menu-image-container {
                height: 180px;
            }
            
            .logo {
                font-size: 1.3rem;
            }
            
            .logo-icon {
                width: 35px;
                height: 35px;
            }
            
            .logo-main {
                font-size: 1.3rem;
            }
            
            .footer-logo-icon {
                width: 25px;
                height: 25px;
            }
            
            .cart-summary {
                bottom: 70px;
                padding: 12px;
            }
            
            .cart-modal-content {
                padding: 20px;
            }
            
            .cart-item {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
            
            .cart-item-actions {
                width: 100%;
                justify-content: space-between;
            }
            
            .admin-header-container {
                flex-direction: column;
                gap: 15px;
            }
            
            .admin-nav {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .admin-menu-list {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 480px) {
            .header-container {
                flex-direction: column;
                gap: 10px;
            }
            
            .contact-info {
                gap: 12px;
            }
            
            .contact-info a {
                font-size: 0.85rem;
            }
            
            .hero {
                padding: 60px 0;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .hero p {
                font-size: 0.95rem;
            }
            
            .section-title h2 {
                font-size: 1.6rem;
            }
            
            .feature-card {
                padding: 20px 15px;
            }
            
            .feature-icon {
                font-size: 2.5rem;
            }
            
            .feature-card h3 {
                font-size: 1.2rem;
            }
            
            .menu-content {
                padding: 15px;
            }
            
            .menu-title {
                font-size: 1.2rem;
            }
            
            .menu-description {
                font-size: 0.85rem;
            }
            
            .price {
                font-size: 1.3rem;
            }
            
            .order-btn {
                padding: 12px 16px;
                font-size: 0.9rem;
                min-width: 90px;
            }
            
            .app-badge {
                padding: 10px 15px;
                font-size: 0.85rem;
            }
            
            .app-badge i {
                font-size: 1.3rem;
            }
            
            .contact h2 {
                font-size: 1.8rem;
            }
            
            .contact-info-large {
                font-size: 1.4rem;
                padding: 10px 20px;
            }
            
            .contact-note {
                font-size: 0.95rem;
            }
            
            .menu-item {
                height: 360px;
            }
            
            .menu-image-container {
                height: 160px;
            }
            
            .logo {
                font-size: 1.1rem;
            }
            
            .logo-icon {
                width: 30px;
                height: 30px;
            }
            
            .logo-main {
                font-size: 1.1rem;
            }
            
            .logo-sub {
                font-size: 0.6rem;
            }
            
            .footer-logo-icon {
                width: 20px;
                height: 20px;
            }
            
            .cart-summary {
                bottom: 65px;
                padding: 10px;
                gap: 10px;
            }
            
            .cart-icon {
                font-size: 1.2rem;
            }
            
            .cart-count {
                font-size: 0.8rem;
            }
            
            .cart-total {
                font-size: 1rem;
            }
            
            .cart-modal-content {
                padding: 15px;
            }
            
            .cart-modal-title {
                font-size: 1.5rem;
            }
            
            .cart-item-name {
                font-size: 1rem;
            }
            
            .cart-item-price {
                font-size: 0.9rem;
            }
            
            .cart-item-total {
                font-size: 1rem;
            }
            
            .cart-modal-total {
                font-size: 1.2rem;
            }
            
            .admin-login-content {
                padding: 30px 20px;
            }
            
            .admin-form {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <a href="#" class="logo">
                <div class="logo-icon">
                    <img src="https://images.unsplash.com/photo-1574484284002-952d92456975?ixlib=rb-4.0.3&auto=format&fit=crop&w=100&q=80" alt="Logo">
                </div>
                <div class="logo-text">
                    <span class="logo-main">Tetho's Home</span>
                    <span class="logo-sub">Authentic Japanese Cuisine</span>
                </div>
            </a>
            <div class="contact-info">
                <a href="tel:016980097">
                    <i class="fas fa-phone"></i> 016 980097
                </a>
                <a href="https://t.me/tethoshome" target="_blank">
                    <i class="fab fa-telegram"></i> Telegram
                </a>
                <button class="admin-login-btn" id="adminLoginBtn" onclick="showAdminLogin()">
                    <i class="fas fa-user-shield"></i> Admin
                </button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container hero-content">
            <h1>Authentic Japanese Cuisine Delivered</h1>
            <p>Experience the true taste of Japan with our traditional dishes, prepared with authentic ingredients and techniques. All dishes under $15.</p>
            <div class="delivery-badge">
                <i class="fas fa-motorcycle"></i> Delivery Only
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features">
        <div class="container">
            <div class="section-title">
                <h2>Why Choose Tetho's Home?</h2>
                <p>Authentic Japanese flavors delivered to your doorstep</p>
            </div>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-utensils"></i>
                    </div>
                    <h3>Authentic Recipes</h3>
                    <p>Our dishes are prepared using traditional Japanese recipes passed down through generations.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-dollar-sign"></i>
                    </div>
                    <h3>Affordable Prices</h3>
                    <p>All our dishes are priced under $15, making authentic Japanese cuisine accessible to everyone.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3>Easy Ordering</h3>
                    <p>Order through your favorite delivery apps or directly through our website for a seamless experience.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section class="menu">
        <div class="container">
            <div class="section-title">
                <h2>Our Popular Dishes</h2>
                <p>Authentic Japanese cuisine, all under $15</p>
            </div>
            <div class="menu-grid" id="menuGrid">
                <!-- Menu items are hardcoded here as fallback -->
                <div class="menu-item">
                    <div class="menu-image-container">
                        <img src="https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Sushi Platter">
                    </div>
                    <div class="menu-content">
                        <h3 class="menu-title">Sushi Platter</h3>
                        <p class="menu-description">Assorted fresh sushi with salmon, tuna, and shrimp, served with wasabi and pickled ginger</p>
                        <div class="menu-footer">
                            <span class="price">$3.99</span>
                            <button type="button" class="order-btn" onclick="openQuantityModal('Sushi Platter', 14.99)">Order</button>
                        </div>
                    </div>
                </div>
                <div class="menu-item">
                    <div class="menu-image-container">
                        <img src="https://images.unsplash.com/photo-1569718212165-3a8278d5f624?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Ramen Bowl">
                    </div>
                    <div class="menu-content">
                        <h3 class="menu-title">Tonkotsu Ramen</h3>
                        <p class="menu-description">Rich pork bone broth with tender chashu pork, soft-boiled egg, and fresh noodles</p>
                        <div class="menu-footer">
                            <span class="price">$5.99</span>
                            <button type="button" class="order-btn" onclick="openQuantityModal('Tonkotsu Ramen', 12.99)">Order</button>
                        </div>
                    </div>
                </div>
                <div class="menu-item">
                    <div class="menu-image-container">
                        <img src="https://images.unsplash.com/photo-1553621042-f6e147245754?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Tempura">
                    </div>
                    <div class="menu-content">
                        <h3 class="menu-title">Tempura Assortment</h3>
                        <p class="menu-description">Lightly battered and fried shrimp, vegetables, and served with tentsuyu dipping sauce</p>
                        <div class="menu-footer">
                            <span class="price">$4.99</span>
                            <button type="button" class="order-btn" onclick="openQuantityModal('Tempura Assortment', 11.99)">Order</button>
                        </div>
                    </div>
                </div>
                <div class="menu-item">
                    <div class="menu-image-container">
                        <img src="https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Teriyaki Chicken">
                    </div>
                    <div class="menu-content">
                        <h3 class="menu-title">Teriyaki Chicken</h3>
                        <p class="menu-description">Grilled chicken glazed with our house-made teriyaki sauce, served with steamed rice</p>
                        <div class="menu-footer">
                            <span class="price">$4.99</span>
                            <button type="button" class="order-btn" onclick="openQuantityModal('Teriyaki Chicken', 10.99)">Order</button>
                        </div>
                    </div>
                </div>
                <div class="menu-item">
                    <div class="menu-image-container">
                        <img src="https://th.bing.com/th/id/R.4dd50c55210350d65038492a1084925e?rik=QxqB5QHi7P3lLQ&riu=http%3a%2f%2fmedia.carbfree.cooking%2f2016%2f07%2fmiso-soup-big.jpg&ehk=DGlMBkZvY%2fxuB3W%2bBvVwGyyr7foDScbAZkeRlQVZO%2b4%3d&risl=&pid=ImgRaw&r=0" alt="Miso Soup">
                    </div>
                    <div class="menu-content">
                        <h3 class="menu-title">Miso Soup</h3>
                        <p class="menu-description">Traditional Japanese soup with fermented soybean paste, tofu, and seaweed</p>
                        <div class="menu-footer">
                            <span class="price">$3.99</span>
                            <button type="button" class="order-btn" onclick="openQuantityModal('Miso Soup', 3.99)">Order</button>
                        </div>
                    </div>
                </div>
                <div class="menu-item">
                    <div class="menu-image-container">
                        <img src="https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Bento Box">
                    </div>
                    <div class="menu-content">
                        <h3 class="menu-title">Bento Box</h3>
                        <p class="menu-description">Complete meal with rice, grilled fish, pickled vegetables, and miso soup</p>
                        <div class="menu-footer">
                            <span class="price">$6.99</span>
                            <button type="button" class="order-btn" onclick="openQuantityModal('Bento Box', 13.99)">Order</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Delivery Section -->
    <section class="delivery">
        <div class="container">
            <div class="delivery-container">
                <div class="delivery-image">
                    <img src="https://asian-recipe.com/wp-content/uploads/2024/02/best-Japanese-restaurant-jpg.webp" alt="Delivery Service">
                </div>
                <div class="delivery-content">
                    <h2>How to Order</h2>
                    <p>We offer delivery through popular food delivery services. You can order your favorite Japanese dishes through any of these platforms:</p>
                    
                    <div class="app-list">
                        <div class="app-badge">
                            <i class="fas fa-motorcycle"></i>
                            <span>Grab Order</span>
                        </div>
                        <div class="app-badge">
                            <i class="fas fa-motorcycle"></i>
                            <span>Food Panda</span>
                        </div>
                        <div class="app-badge">
                            <i class="fas fa-motorcycle"></i>
                            <span>Woownow</span>
                        </div>
                        <div class="app-badge">
                            <i class="fas fa-motorcycle"></i>
                            <span>Wingmall</span>
                        </div>
                    </div>
                    
                    <p style="margin-top: 25px;">Or contact us directly via Telegram to place your order.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact">
        <div class="container contact-container">
            <h2>Contact Us</h2>
            <p>For more information or to place an order</p>
            <div class="contact-info-large">
                <i class="fas fa-phone"></i> 016 980097
            </div>
            <p class="contact-note">
                Please note: We are a delivery-only restaurant and do not accept dine-in customers. Please order through delivery apps or by phone.
            </p>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">
                    <div class="footer-logo-icon">
                        <img src="https://images.unsplash.com/photo-1574484284002-952d92456975?ixlib=rb-4.0.3&auto=format&fit=crop&w=100&q=80" alt="Logo">
                    </div>
                    <div class="footer-logo-text">Tetho's Home</div>
                </div>
                <p>&copy; 2023 Tetho's Home Japanese Restaurant. All rights reserved.</p>
                <div class="social-links">
                    <a href="https://www.facebook.com/tethoshome" target="_blank"><i class="fab fa-facebook"></i></a>
                    <a href="https://www.instagram.com/tethoshome" target="_blank"><i class="fab fa-instagram"></i></a>
                    <a href="https://t.me/franklin2588?text" target="_blank"><i class="fab fa-telegram"></i></a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Cart Summary -->
    <div class="cart-summary" id="cartSummary" onclick="displayCartModal()">
        <div class="cart-icon">
            <i class="fas fa-shopping-cart"></i>
        </div>
        <div class="cart-info">
            <div class="cart-count" id="cartCount">0</div>
            <div class="cart-total" id="cartTotal">$0.00</div>
        </div>
    </div>

    <!-- Quantity Selection Modal -->
    <div class="quantity-modal" id="quantityModal">
        <div class="modal-content">
            <button type="button" class="modal-close" onclick="closeQuantityModal()">
                <i class="fas fa-times"></i>
            </button>
            <h3 class="modal-title">Select Quantity</h3>
            <div class="menu-name" id="selectedMenuName"></div>
            <div class="quantity-selector">
                <button type="button" class="quantity-btn" onclick="decreaseQuantity()">
                    <i class="fas fa-minus"></i>
                </button>
                <input type="number" class="quantity-input" id="quantityInput" value="1" min="1" max="99">
                <button type="button" class="quantity-btn" onclick="increaseQuantity()">
                    <i class="fas fa-plus"></i>
                </button>
            </div>
            <div class="modal-actions">
                <button type="button" class="modal-btn cancel-btn" onclick="closeQuantityModal()">Cancel</button>
                <button type="button" class="modal-btn confirm-btn" onclick="confirmAddToCart()">Add to Cart</button>
            </div>
        </div>
    </div>

    <!-- Cart Modal -->
    <div class="cart-modal" id="cartModal">
        <div class="cart-modal-content">
            <button type="button" class="cart-modal-close" onclick="closeCartModal()">
                <i class="fas fa-times"></i>
            </button>
            <h3 class="cart-modal-title">Your Cart</h3>
            <div class="cart-items-container" id="cartItemsContainer">
                <!-- Cart items will be inserted here -->
            </div>
            <div class="cart-modal-footer">
                <div class="cart-modal-total" id="cartModalTotal">$0.00</div>
                <div class="cart-modal-actions">
                    <button type="button" class="modal-btn clear-cart-btn" onclick="clearCart()">Clear</button>
                    <button type="button" class="modal-btn send-order-btn" onclick="sendOrder()">Place Order</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Admin Login Modal -->
    <div class="admin-login-modal" id="adminLoginModal">
        <div class="admin-login-content">
            <h2 class="admin-login-title">Admin Login</h2>
            <form id="adminLoginForm" onsubmit="handleAdminLogin(event)">
                <div class="form-group">
                    <label for="adminUsername">Username</label>
                    <input type="text" id="adminUsername" required>
                </div>
                <div class="form-group">
                    <label for="adminPassword">Password</label>
                    <input type="password" id="adminPassword" required>
                </div>
                <div class="error-message" id="loginError">Invalid username or password</div>
                <div class="admin-login-actions">
                    <button type="button" class="admin-cancel-btn" onclick="hideAdminLogin()">Cancel</button>
                    <button type="submit" class="admin-login-btn">Login</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Admin Panel -->
    <div class="admin-panel" id="adminPanel">
        <div class="admin-header">
            <div class="container admin-header-container">
                <div class="admin-logo">
                    <i class="fas fa-user-shield"></i>
                    <span>Tetho's Home Admin</span>
                </div>
                <nav class="admin-nav">
                    <div class="admin-nav-item active" onclick="showAdminSection('menu')">Menu</div>
                    <div class="admin-nav-item" onclick="showAdminSection('info')">Restaurant Info</div>
                    <div class="admin-nav-item" onclick="showAdminSection('contact')">Contact</div>
                    <div class="admin-nav-item" onclick="showAdminSection('delivery')">Delivery</div>
                </nav>
                <button class="admin-logout" onclick="adminLogout()">Logout</button>
            </div>
        </div>
        <div class="container admin-content">
            <!-- Menu Section -->
            <div class="admin-section active" id="menuSection">
                <h2 class="admin-section-title">Menu Management</h2>
                
                <div class="admin-success-message" id="menuSuccessMessage">Changes saved successfully!</div>
                <div class="admin-error-message" id="menuErrorMessage">Error saving changes!</div>
                
                <div class="admin-card">
                    <div class="admin-card-title">
                        <span>Add New Menu Item</span>
                    </div>
                    <form id="addMenuItemForm" onsubmit="handleAddMenuItem(event)">
                        <div class="admin-form">
                            <div class="admin-form-group">
                                <label for="menuItemName">Item Name</label>
                                <input type="text" id="menuItemName" required>
                            </div>
                            <div class="admin-form-group">
                                <label for="menuItemPrice">Price ($)</label>
                                <input type="number" id="menuItemPrice" step="0.01" min="0" required>
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label for="menuItemDescription">Description</label>
                                <textarea id="menuItemDescription" required></textarea>
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label>Item Image</label>
                                <div class="admin-image-upload">
                                    <div class="admin-image-preview" id="newItemImagePreview">
                                        <i class="fas fa-image" style="font-size: 3rem; color: #ccc;"></i>
                                    </div>
                                    <div>
                                        <input type="file" id="newItemImage" accept="image/*" style="display: none;" onchange="previewNewItemImage(event)">
                                        <button type="button" class="admin-image-upload-btn" onclick="document.getElementById('newItemImage').click()">Choose Image</button>
                                        <p style="margin-top: 10px; font-size: 0.9rem; color: #666;">Or enter image URL:</p>
                                        <input type="url" id="newItemImageUrl" placeholder="https://example.com/image.jpg" oninput="previewNewItemImageUrl(this.value)">
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="admin-form-actions">
                            <button type="submit" class="admin-btn">Add Menu Item</button>
                        </div>
                    </form>
                </div>
                
                <div class="admin-card">
                    <div class="admin-card-title">
                        <span>Current Menu Items</span>
                    </div>
                    <div class="admin-menu-list" id="adminMenuList">
                        <!-- Menu items will be dynamically loaded here -->
                    </div>
                </div>
            </div>
            
            <!-- Restaurant Info Section -->
            <div class="admin-section" id="infoSection">
                <h2 class="admin-section-title">Restaurant Information</h2>
                
                <div class="admin-success-message" id="infoSuccessMessage">Changes saved successfully!</div>
                <div class="admin-error-message" id="infoErrorMessage">Error saving changes!</div>
                
                <div class="admin-card">
                    <div class="admin-card-title">
                        <span>Basic Information</span>
                    </div>
                    <form id="restaurantInfoForm" onsubmit="handleRestaurantInfo(event)">
                        <div class="admin-form">
                            <div class="admin-form-group">
                                <label for="restaurantName">Restaurant Name</label>
                                <input type="text" id="restaurantName" value="Tetho's Home">
                            </div>
                            <div class="admin-form-group">
                                <label for="restaurantTagline">Tagline</label>
                                <input type="text" id="restaurantTagline" value="Authentic Japanese Cuisine">
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label for="heroTitle">Hero Title</label>
                                <input type="text" id="heroTitle" value="Authentic Japanese Cuisine Delivered">
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label for="heroDescription">Hero Description</label>
                                <textarea id="heroDescription">Experience the true taste of Japan with our traditional dishes, prepared with authentic ingredients and techniques. All dishes under $15.</textarea>
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label>Hero Background Image</label>
                                <div class="admin-image-upload">
                                    <div class="admin-image-preview" id="heroImagePreview">
                                        <img src="https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80" alt="Hero Background">
                                    </div>
                                    <div>
                                        <input type="file" id="heroImage" accept="image/*" style="display: none;" onchange="previewHeroImage(event)">
                                        <button type="button" class="admin-image-upload-btn" onclick="document.getElementById('heroImage').click()">Change Image</button>
                                        <p style="margin-top: 10px; font-size: 0.9rem; color: #666;">Or enter image URL:</p>
                                        <input type="url" id="heroImageUrl" value="https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80" oninput="previewHeroImageUrl(this.value)">
                                    </div>
                                </div>
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label>Logo Image</label>
                                <div class="admin-image-upload">
                                    <div class="admin-image-preview" id="logoImagePreview">
                                        <img src="https://images.unsplash.com/photo-1574484284002-952d92456975?ixlib=rb-4.0.3&auto=format&fit=crop&w=100&q=80" alt="Logo">
                                    </div>
                                    <div>
                                        <input type="file" id="logoImage" accept="image/*" style="display: none;" onchange="previewLogoImage(event)">
                                        <button type="button" class="admin-image-upload-btn" onclick="document.getElementById('logoImage').click()">Change Image</button>
                                        <p style="margin-top: 10px; font-size: 0.9rem; color: #666;">Or enter image URL:</p>
                                        <input type="url" id="logoImageUrl" value="https://images.unsplash.com/photo-1574484284002-952d92456975?ixlib=rb-4.0.3&auto=format&fit=crop&w=100&q=80" oninput="previewLogoImageUrl(this.value)">
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="admin-form-actions">
                            <button type="submit" class="admin-btn">Save Changes</button>
                        </div>
                    </form>
                </div>
            </div>
            
            <!-- Contact Section -->
            <div class="admin-section" id="contactSection">
                <h2 class="admin-section-title">Contact Information</h2>
                
                <div class="admin-success-message" id="contactSuccessMessage">Changes saved successfully!</div>
                <div class="admin-error-message" id="contactErrorMessage">Error saving changes!</div>
                
                <div class="admin-card">
                    <div class="admin-card-title">
                        <span>Contact Details</span>
                    </div>
                    <form id="contactInfoForm" onsubmit="handleContactInfo(event)">
                        <div class="admin-form">
                            <div class="admin-form-group">
                                <label for="phoneNumber">Phone Number</label>
                                <input type="tel" id="phoneNumber" value="016 980097">
                            </div>
                            <div class="admin-form-group">
                                <label for="telegramLink">Telegram Link</label>
                                <input type="url" id="telegramLink" value="https://t.me/franklin2588">
                            </div>
                            <div class="admin-form-group">
                                <label for="facebookLink">Facebook Link</label>
                                <input type="url" id="facebookLink" value="https://www.facebook.com/tethoshome">
                            </div>
                            <div class="admin-form-group">
                                <label for="instagramLink">Instagram Link</label>
                                <input type="url" id="instagramLink" value="https://www.instagram.com/tethoshome">
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label for="contactNote">Contact Note</label>
                                <textarea id="contactNote">Please note: We are a delivery-only restaurant and do not accept dine-in customers. Please order through delivery apps or by phone.</textarea>
                            </div>
                        </div>
                        <div class="admin-form-actions">
                            <button type="submit" class="admin-btn">Save Changes</button>
                        </div>
                    </form>
                </div>
            </div>
            
            <!-- Delivery Section -->
            <div class="admin-section" id="deliverySection">
                <h2 class="admin-section-title">Delivery Information</h2>
                
                <div class="admin-success-message" id="deliverySuccessMessage">Changes saved successfully!</div>
                <div class="admin-error-message" id="deliveryErrorMessage">Error saving changes!</div>
                
                <div class="admin-card">
                    <div class="admin-card-title">
                        <span>Delivery Options</span>
                    </div>
                    <form id="deliveryInfoForm" onsubmit="handleDeliveryInfo(event)">
                        <div class="admin-form">
                            <div class="admin-form-group">
                                <label for="deliveryTitle">Delivery Title</label>
                                <input type="text" id="deliveryTitle" value="How to Order">
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label for="deliveryDescription">Delivery Description</label>
                                <textarea id="deliveryDescription">We offer delivery through popular food delivery services. You can order your favorite Japanese dishes through any of these platforms:</textarea>
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label>Delivery Image</label>
                                <div class="admin-image-upload">
                                    <div class="admin-image-preview" id="deliveryImagePreview">
                                        <img src="https://asian-recipe.com/wp-content/uploads/2024/02/best-Japanese-restaurant-jpg.webp" alt="Delivery">
                                    </div>
                                    <div>
                                        <input type="file" id="deliveryImage" accept="image/*" style="display: none;" onchange="previewDeliveryImage(event)">
                                        <button type="button" class="admin-image-upload-btn" onclick="document.getElementById('deliveryImage').click()">Change Image</button>
                                        <p style="margin-top: 10px; font-size: 0.9rem; color: #666;">Or enter image URL:</p>
                                        <input type="url" id="deliveryImageUrl" value="https://asian-recipe.com/wp-content/uploads/2024/02/best-Japanese-restaurant-jpg.webp" oninput="previewDeliveryImageUrl(this.value)">
                                    </div>
                                </div>
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label>Delivery Apps</label>
                                <div id="deliveryAppsList">
                                    <div class="admin-form-group" style="display: flex; gap: 10px; align-items: center;">
                                        <input type="text" class="delivery-app-name" value="Grab Order" style="flex: 1;">
                                        <button type="button" class="admin-btn-danger remove-app-btn" onclick="removeDeliveryApp(this)">Remove</button>
                                    </div>
                                    <div class="admin-form-group" style="display: flex; gap: 10px; align-items: center;">
                                        <input type="text" class="delivery-app-name" value="Food Panda" style="flex: 1;">
                                        <button type="button" class="admin-btn-danger remove-app-btn" onclick="removeDeliveryApp(this)">Remove</button>
                                    </div>
                                    <div class="admin-form-group" style="display: flex; gap: 10px; align-items: center;">
                                        <input type="text" class="delivery-app-name" value="Woownow" style="flex: 1;">
                                        <button type="button" class="admin-btn-danger remove-app-btn" onclick="removeDeliveryApp(this)">Remove</button>
                                    </div>
                                    <div class="admin-form-group" style="display: flex; gap: 10px; align-items: center;">
                                        <input type="text" class="delivery-app-name" value="Wingmall" style="flex: 1;">
                                        <button type="button" class="admin-btn-danger remove-app-btn" onclick="removeDeliveryApp(this)">Remove</button>
                                    </div>
                                </div>
                                <button type="button" class="admin-btn" onclick="addDeliveryApp()">Add App</button>
                            </div>
                            <div class="admin-form-group" style="grid-column: 1 / -1;">
                                <label for="deliveryNote">Delivery Note</label>
                                <textarea id="deliveryNote">Or contact us directly via Telegram to place your order.</textarea>
                            </div>
                        </div>
                        <div class="admin-form-actions">
                            <button type="submit" class="admin-btn">Save Changes</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Initialize data
        let menuItems = [
            {
                id: 1,
                name: "Sushi Platter",
                price: 3.99,
                description: "Assorted fresh sushi with salmon, tuna, and shrimp, served with wasabi and pickled ginger",
                image: "https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80"
            },
            {
                id: 2,
                name: "Tonkotsu Ramen",
                price: 5.99,
                description: "Rich pork bone broth with tender chashu pork, soft-boiled egg, and fresh noodles",
                image: "https://images.unsplash.com/photo-1569718212165-3a8278d5f624?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80"
            },
            {
                id: 3,
                name: "Tempura Assortment",
                price: 4.99,
                description: "Lightly battered and fried shrimp, vegetables, and served with tentsuyu dipping sauce",
                image: "https://images.unsplash.com/photo-1553621042-f6e147245754?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80"
            },
            {
                id: 4,
                name: "Teriyaki Chicken",
                price: 4.99,
                description: "Grilled chicken glazed with our house-made teriyaki sauce, served with steamed rice",
                image: "https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80"
            },
            {
                id: 5,
                name: "Miso Soup",
                price: 3.99,
                description: "Traditional Japanese soup with fermented soybean paste, tofu, and seaweed",
                image: "https://th.bing.com/th/id/R.4dd50c55210350d65038492a1084925e?rik=QxqB5QHi7P3lLQ&riu=http%3a%2f%2fmedia.carbfree.cooking%2f2016%2f07%2fmiso-soup-big.jpg&ehk=DGlMBkZvY%2fxuB3W%2bBvVwGyyr7foDScbAZkeRlQVZO%2b4%3d&risl=&pid=ImgRaw&r=0"
            },
            {
                id: 6,
                name: "Bento Box",
                price: 6.99,
                description: "Complete meal with rice, grilled fish, pickled vegetables, and miso soup",
                image: "https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80"
            }
        ];
        
        let restaurantInfo = {
            name: "Tetho's Home",
            tagline: "Authentic Japanese Cuisine",
            heroTitle: "Authentic Japanese Cuisine Delivered",
            heroDescription: "Experience the true taste of Japan with our traditional dishes, prepared with authentic ingredients and techniques. All dishes under $15.",
            heroImage: "https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80",
            logoImage: "https://images.unsplash.com/photo-1574484284002-952d92456975?ixlib=rb-4.0.3&auto=format&fit=crop&w=100&q=80"
        };
        
        let contactInfo = {
            phoneNumber: "016 980097",
            telegramLink: "https://t.me/franklin2588",
            facebookLink: "https://www.facebook.com/tethoshome",
            instagramLink: "https://www.instagram.com/tethoshome",
            contactNote: "Please note: We are a delivery-only restaurant and do not accept dine-in customers. Please order through delivery apps or by phone."
        };
        
        let deliveryInfo = {
            title: "How to Order",
            description: "We offer delivery through popular food delivery services. You can order your favorite Japanese dishes through any of these platforms:",
            image: "https://asian-recipe.com/wp-content/uploads/2024/02/best-Japanese-restaurant-jpg.webp",
            apps: ["Grab Order", "Food Panda", "Woownow", "Wingmall"],
            note: "Or contact us directly via Telegram to place your order."
        };
        
        // Initialize cart
        let cart = JSON.parse(localStorage.getItem('cart')) || [];
        let currentMenuItem = null;
        let currentPrice = null;
        let isAdminLoggedIn = false;
        
        // Google Apps Script URL
        const webAppUrl = 'https://script.google.com/macros/s/AKfycbxXEdovhn5kOe-X85WHZ1f01hyqkB_BqWK2liFI2RW_PLm_Phxu1vMEB5Zr5hE6raWiNg/exec';

        // Function to save cart to localStorage
        function saveCart() {
            localStorage.setItem('cart', JSON.stringify(cart));
        }

        // Function to generate a unique device ID
        function generateDeviceId() {
            let deviceId = localStorage.getItem('deviceId');
            if (!deviceId) {https://script.google.com/macros/s/AKfycbxXEdovhn5kOe-X85WHZ1f01hyqkB_BqWK2liFI2RW_PLm_Phxu1vMEB5Zr5hE6raWiNg/exec
                deviceId = 'device_' + Math.random().toString(36).substr(2, 9);
                localStorage.setItem('deviceId', deviceId);
            }
            return deviceId;
        }

        // Function to load data from localStorage
        function loadData() {
            const savedMenuItems = localStorage.getItem('menuItems');
            if (savedMenuItems) {
                menuItems = JSON.parse(savedMenuItems);
            }
            
            const savedRestaurantInfo = localStorage.getItem('restaurantInfo');
            if (savedRestaurantInfo) {
                restaurantInfo = JSON.parse(savedRestaurantInfo);
            }
            
            const savedContactInfo = localStorage.getItem('contactInfo');
            if (savedContactInfo) {
                contactInfo = JSON.parse(savedContactInfo);
            }
            
            const savedDeliveryInfo = localStorage.getItem('deliveryInfo');
            if (savedDeliveryInfo) {
                deliveryInfo = JSON.parse(savedDeliveryInfo);
            }
        }

        // Function to save data to localStorage
        function saveData() {
            localStorage.setItem('menuItems', JSON.stringify(menuItems));
            localStorage.setItem('restaurantInfo', JSON.stringify(restaurantInfo));
            localStorage.setItem('contactInfo', JSON.stringify(contactInfo));
            localStorage.setItem('deliveryInfo', JSON.stringify(deliveryInfo));
        }

        // Function to render menu items
        function renderMenuItems() {
            const menuGrid = document.getElementById('menuGrid');
            menuGrid.innerHTML = '';
            
            menuItems.forEach(item => {
                const menuItem = document.createElement('div');
                menuItem.className = 'menu-item';
                menuItem.innerHTML = `
                    <div class="menu-image-container">
                        <img src="${item.image}" alt="${item.name}">
                    </div>
                    <div class="menu-content">
                        <h3 class="menu-title">${item.name}</h3>
                        <p class="menu-description">${item.description}</p>
                        <div class="menu-footer">
                            <span class="price">$${item.price.toFixed(2)}</span>
                            <button type="button" class="order-btn" onclick="openQuantityModal('${item.name}', ${item.price})">Order</button>
                        </div>
                    </div>
                `;
                menuGrid.appendChild(menuItem);
            });
        }

        // Function to render admin menu items
        function renderAdminMenuItems() {
            const adminMenuList = document.getElementById('adminMenuList');
            adminMenuList.innerHTML = '';
            
            menuItems.forEach(item => {
                const adminMenuItem = document.createElement('div');
                adminMenuItem.className = 'admin-menu-item';
                adminMenuItem.innerHTML = `
                    <div class="admin-menu-image">
                        <img src="${item.image}" alt="${item.name}">
                    </div>
                    <div class="admin-menu-content">
                        <h3 class="admin-menu-title">${item.name}</h3>
                        <div class="admin-menu-price">$${item.price.toFixed(2)}</div>
                        <div class="admin-menu-actions">
                            <button type="button" class="admin-edit-btn" onclick="editMenuItem(${item.id})">Edit</button>
                            <button type="button" class="admin-delete-btn" onclick="deleteMenuItem(${item.id})">Delete</button>
                        </div>
                    </div>
                `;
                adminMenuList.appendChild(adminMenuItem);
            });
        }

        // Function to update website content
        function updateWebsiteContent() {
            // Update restaurant info
            document.querySelector('.logo-main').textContent = restaurantInfo.name;
            document.querySelector('.logo-sub').textContent = restaurantInfo.tagline;
            document.querySelector('.hero h1').textContent = restaurantInfo.heroTitle;
            document.querySelector('.hero p').textContent = restaurantInfo.heroDescription;
            document.querySelector('.hero').style.background = `linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('${restaurantInfo.heroImage}')`;
            document.querySelector('.hero').style.backgroundSize = 'cover';
            document.querySelector('.hero').style.backgroundPosition = 'center';
            document.querySelector('.logo-icon img').src = restaurantInfo.logoImage;
            document.querySelector('.footer-logo-icon img').src = restaurantInfo.logoImage;
            document.querySelector('.footer-logo-text').textContent = restaurantInfo.name;
            
            // Update contact info
            document.querySelector('.contact-info a[href^="tel"]').innerHTML = `<i class="fas fa-phone"></i> ${contactInfo.phoneNumber}`;
            document.querySelector('.contact-info a[href^="tel"]').href = `tel:${contactInfo.phoneNumber}`;
            document.querySelector('.contact-info a[href^="https://t.me"]').href = contactInfo.telegramLink;
            document.querySelector('.contact-info-large').innerHTML = `<i class="fas fa-phone"></i> ${contactInfo.phoneNumber}`;
            document.querySelector('.contact-note').textContent = contactInfo.contactNote;
            document.querySelector('.social-links a[href*="facebook"]').href = contactInfo.facebookLink;
            document.querySelector('.social-links a[href*="instagram"]').href = contactInfo.instagramLink;
            document.querySelector('.social-links a[href*="telegram"]').href = contactInfo.telegramLink;
            
            // Update delivery info
            document.querySelector('.delivery-content h2').textContent = deliveryInfo.title;
            document.querySelector('.delivery-content p').textContent = deliveryInfo.description;
            document.querySelector('.delivery-image img').src = deliveryInfo.image;
            document.querySelector('.delivery-content p:last-of-type').textContent = deliveryInfo.note;
            
            // Update delivery apps
            const appList = document.querySelector('.app-list');
            appList.innerHTML = '';
            deliveryInfo.apps.forEach(app => {
                const appBadge = document.createElement('div');
                appBadge.className = 'app-badge';
                appBadge.innerHTML = `
                    <i class="fas fa-motorcycle"></i>
                    <span>${app}</span>
                `;
                appList.appendChild(appBadge);
            });
        }

        // Function to show message
        function showMessage(messageId, message) {
            const messageElement = document.getElementById(messageId);
            messageElement.textContent = message;
            messageElement.style.display = 'block';
            
            setTimeout(() => {
                messageElement.style.display = 'none';
            }, 3000);
        }

        // Function to add item to cart
        function addToCart(menuName, price, quantity) {
            // Check if the item is already in the cart
            const existingItemIndex = cart.findIndex(item => item.menuName === menuName);
            
            if (existingItemIndex !== -1) {
                // Update the quantity if item already exists
                cart[existingItemIndex].quantity += quantity;
            } else {
                // Add new item to cart
                const newItem = {
                    id: Date.now().toString(),
                    menuName: menuName,
                    price: parseFloat(price),
                    quantity: quantity
                };
                
                cart.push(newItem);
            }
            
            // Save cart to localStorage
            saveCart();
            
            // Update cart summary
            updateCartSummary();
            
            // Show notification
            showNotification(`${menuName} added to cart`);
        }

        // Function to update cart summary
        function updateCartSummary() {
            const cartCount = cart.reduce((total, item) => total + item.quantity, 0);
            const cartTotal = cart.reduce((total, item) => total + (item.price * item.quantity), 0);
            
            // Update cart summary display
            document.getElementById('cartCount').textContent = cartCount;
            document.getElementById('cartTotal').textContent = `$${cartTotal.toFixed(2)}`;
        }

        // Function to display cart modal
        function displayCartModal() {
            const cartItemsContainer = document.getElementById('cartItemsContainer');
            const cartModalTotal = document.getElementById('cartModalTotal');
            
            // Clear the container
            cartItemsContainer.innerHTML = '';
            
            if (cart.length === 0) {
                cartItemsContainer.innerHTML = '<div class="empty-cart-message">Your cart is empty</div>';
                cartModalTotal.textContent = '$0.00';
            } else {
                let total = 0;
                
                cart.forEach(item => {
                    const itemTotal = item.price * item.quantity;
                    total += itemTotal;
                    
                    const cartItem = document.createElement('div');
                    cartItem.className = 'cart-item';
                    cartItem.innerHTML = `
                        <div class="cart-item-info">
                            <div class="cart-item-name">${item.menuName}</div>
                            <div class="cart-item-price">$${item.price.toFixed(2)} each</div>
                        </div>
                        <div class="cart-item-actions">
                            <div class="cart-item-quantity">
                                <button class="quantity-btn decrease-quantity" onclick="updateCartItemQuantity('${item.id}', ${item.quantity - 1})">
                                    <i class="fas fa-minus"></i>
                                </button>
                                <input type="number" class="quantity-input cart-quantity-input" value="${item.quantity}" min="1" max="99" onchange="updateCartItemQuantity('${item.id}', this.value)">
                                <button class="quantity-btn increase-quantity" onclick="updateCartItemQuantity('${item.id}', ${item.quantity + 1})">
                                    <i class="fas fa-plus"></i>
                                </button>
                            </div>
                            <div class="cart-item-total">$${itemTotal.toFixed(2)}</div>
                            <button class="remove-item" onclick="removeFromCart('${item.id}')">
                                <i class="fas fa-trash"></i>
                            </button>
                        </div>
                    `;
                    
                    cartItemsContainer.appendChild(cartItem);
                });
                
                cartModalTotal.textContent = `$${total.toFixed(2)}`;
            }
            
            // Show cart modal
            document.getElementById('cartModal').classList.add('active');
        }

        // Function to update cart item quantity
        function updateCartItemQuantity(itemId, newQuantity) {
            const item = cart.find(item => item.id === itemId);
            
            if (item) {
                if (newQuantity <= 0) {
                    removeFromCart(itemId);
                } else {
                    // Update quantity
                    item.quantity = parseInt(newQuantity);
                    saveCart();
                    updateCartSummary();
                    
                    // Refresh cart modal if it's open
                    if (document.getElementById('cartModal').classList.contains('active')) {
                        displayCartModal();
                    }
                }
            }
        }

        // Function to remove item from cart
        function removeFromCart(itemId) {
            cart = cart.filter(item => item.id !== itemId);
            saveCart();
            updateCartSummary();
            
            // Refresh cart modal if it's open
            if (document.getElementById('cartModal').classList.contains('active')) {
                displayCartModal();
            }
        }

        // Function to clear cart
        function clearCart() {
            if (cart.length === 0) {
                return;
            }
            
            if (confirm('Are you sure you want to clear your cart?')) {
                cart = [];
                saveCart();
                updateCartSummary();
                
                // Refresh cart modal if it's open
                if (document.getElementById('cartModal').classList.contains('active')) {
                    displayCartModal();
                }
            }
        }

        // Function to send order to Google Sheets and Telegram
        function sendOrder() {
            if (cart.length === 0) {
                alert('Your cart is empty!');
                return;
            }
            
            // Send order to Google Sheets
            sendOrderToGoogleSheets();
            
            // Send order to Telegram
            sendOrderToTelegram();
            
            // Clear cart after sending
            cart = [];
            saveCart();
            updateCartSummary();
            
            // Close cart modal
            document.getElementById('cartModal').classList.remove('active');
            
            // Show success notification
            showNotification('Order placed successfully!');
        }

        // Function to send order to Google Sheets
        function sendOrderToGoogleSheets() {
            if (!webAppUrl) {
                console.log('Google Apps Script URL not configured');
                return;
            }
            
            // Generate a unique order ID
            const orderId = 'order_' + Date.now();
            
            // Calculate total amount
            const totalAmount = cart.reduce((total, item) => total + (item.price * item.quantity), 0);
            
            // Prepare the order data
            const orderData = {
                orderId: orderId,
                orderDetails: cart,
                totalAmount: totalAmount,
                timestamp: new Date().toISOString(),
                deviceId: generateDeviceId(),
                status: "completed"
            };
            
            // Format date and time
            const date = new Date(orderData.timestamp);
            const data = {
                orderId: orderData.orderId,
                orderDetails: orderData.orderDetails,
                totalAmount: orderData.totalAmount,
                date: date.toLocaleDateString('en-US'),
                time: date.toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit' }),
                deviceId: orderData.deviceId,
                status: orderData.status
            };
            
            fetch(webAppUrl, {
                method: 'POST',
                mode: 'no-cors',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(data)
            })
            .then(response => {
                console.log('Order sent to Google Sheets');
            })
            .catch(error => {
                console.error('Error sending order to Google Sheets:', error);
            });
        }

        // Function to send order to Telegram
        function sendOrderToTelegram() {
            let message = 'My Order:\n\n';
            let total = 0;
            
            cart.forEach(item => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                message += `- ${item.menuName}: ${item.quantity} x $${item.price.toFixed(2)} = $${itemTotal.toFixed(2)}\n`;
            });
            
            message += `\nTotal: $${total.toFixed(2)}`;
            
            const encodedMessage = encodeURIComponent(message);
            const telegramUrl = `https://t.me/franklin2588?text=${encodedMessage}`;
            
            // Open Telegram with order message
            window.open(telegramUrl, '_blank');
        }

        // Function to show notification
        function showNotification(message) {
            // Create notification element
            const notification = document.createElement('div');
            notification.className = 'notification';
            notification.textContent = message;
            
            // Style the notification
            notification.style.position = 'fixed';
            notification.style.bottom = '20px';
            notification.style.left = '50%';
            notification.style.transform = 'translateX(-50%)';
            notification.style.backgroundColor = 'var(--success)';
            notification.style.color = 'white';
            notification.style.padding = '12px 20px';
            notification.style.borderRadius = '8px';
            notification.style.boxShadow = '0 4px 12px rgba(0,0,0,0.15)';
            notification.style.zIndex = '5000';
            notification.style.opacity = '0';
            notification.style.transition = 'opacity 0.3s';
            
            // Add to DOM
            document.body.appendChild(notification);
            
            // Fade in
            setTimeout(() => {
                notification.style.opacity = '1';
            }, 10);
            
            // Remove after 3 seconds
            setTimeout(() => {
                notification.style.opacity = '0';
                setTimeout(() => {
                    document.body.removeChild(notification);
                }, 300);
            }, 3000);
        }

        // Admin functions
        function showAdminLogin() {
            document.getElementById('adminLoginModal').classList.add('active');
        }

        function hideAdminLogin() {
            document.getElementById('adminLoginModal').classList.remove('active');
            document.getElementById('loginError').style.display = 'none';
        }

        function handleAdminLogin(event) {
            event.preventDefault();
            
            const username = document.getElementById('adminUsername').value;
            const password = document.getElementById('adminPassword').value;
            
            // Simple authentication
            if (username === 'admin' && password === '016980097') {
                isAdminLoggedIn = true;
                document.getElementById('adminLoginModal').classList.remove('active');
                document.getElementById('adminPanel').classList.add('active');
                
                // Reset form
                document.getElementById('adminUsername').value = '';
                document.getElementById('adminPassword').value = '';
                document.getElementById('loginError').style.display = 'none';
                
                // Render admin menu items
                renderAdminMenuItems();
                
                // Populate admin forms with current data
                document.getElementById('restaurantName').value = restaurantInfo.name;
                document.getElementById('restaurantTagline').value = restaurantInfo.tagline;
                document.getElementById('heroTitle').value = restaurantInfo.heroTitle;
                document.getElementById('heroDescription').value = restaurantInfo.heroDescription;
                document.getElementById('heroImageUrl').value = restaurantInfo.heroImage;
                document.getElementById('logoImageUrl').value = restaurantInfo.logoImage;
                document.getElementById('heroImagePreview').innerHTML = `<img src="${restaurantInfo.heroImage}" alt="Hero Background">`;
                document.getElementById('logoImagePreview').innerHTML = `<img src="${restaurantInfo.logoImage}" alt="Logo">`;
                
                document.getElementById('phoneNumber').value = contactInfo.phoneNumber;
                document.getElementById('telegramLink').value = contactInfo.telegramLink;
                document.getElementById('facebookLink').value = contactInfo.facebookLink;
                document.getElementById('instagramLink').value = contactInfo.instagramLink;
                document.getElementById('contactNote').value = contactInfo.contactNote;
                
                document.getElementById('deliveryTitle').value = deliveryInfo.title;
                document.getElementById('deliveryDescription').value = deliveryInfo.description;
                document.getElementById('deliveryImageUrl').value = deliveryInfo.image;
                document.getElementById('deliveryImagePreview').innerHTML = `<img src="${deliveryInfo.image}" alt="Delivery">`;
                document.getElementById('deliveryNote').value = deliveryInfo.note;
                
                // Populate delivery apps
                const deliveryAppsList = document.getElementById('deliveryAppsList');
                deliveryAppsList.innerHTML = '';
                deliveryInfo.apps.forEach(app => {
                    const appDiv = document.createElement('div');
                    appDiv.className = 'admin-form-group';
                    appDiv.style.display = 'flex';
                    appDiv.style.gap = '10px';
                    appDiv.style.alignItems = 'center';
                    appDiv.innerHTML = `
                        <input type="text" class="delivery-app-name" value="${app}" style="flex: 1;">
                        <button type="button" class="admin-btn-danger remove-app-btn" onclick="removeDeliveryApp(this)">Remove</button>
                    `;
                    deliveryAppsList.appendChild(appDiv);
                });
            } else {
                document.getElementById('loginError').style.display = 'block';
            }
        }

        function adminLogout() {
            isAdminLoggedIn = false;
            document.getElementById('adminPanel').classList.remove('active');
        }

        function showAdminSection(section) {
            // Remove active class from all items and sections
            document.querySelectorAll('.admin-nav-item').forEach(item => item.classList.remove('active'));
            document.querySelectorAll('.admin-section').forEach(section => section.classList.remove('active'));
            
            // Add active class to clicked item
            event.target.classList.add('active');
            
            // Show corresponding section
            document.getElementById(section + 'Section').classList.add('active');
        }

        function handleAddMenuItem(event) {
            event.preventDefault();
            
            const name = document.getElementById('menuItemName').value;
            const price = parseFloat(document.getElementById('menuItemPrice').value);
            const description = document.getElementById('menuItemDescription').value;
            const imageUrl = document.getElementById('newItemImageUrl').value;
            
            // Create new menu item
            const newItem = {
                id: Date.now(),
                name: name,
                price: price,
                description: description,
                image: imageUrl || 'https://via.placeholder.com/800x600?text=No+Image'
            };
            
            // Add to menu items
            menuItems.push(newItem);
            
            // Save data
            saveData();
            
            // Update UI
            renderMenuItems();
            renderAdminMenuItems();
            
            // Reset form
            document.getElementById('addMenuItemForm').reset();
            document.getElementById('newItemImagePreview').innerHTML = '<i class="fas fa-image" style="font-size: 3rem; color: #ccc;"></i>';
            
            // Show success message
            showMessage('menuSuccessMessage', 'Menu item added successfully!');
        }

        function editMenuItem(id) {
            const item = menuItems.find(item => item.id === id);
            
            if (item) {
                // Create edit modal
                const editModal = document.createElement('div');
                editModal.className = 'quantity-modal active';
                editModal.id = 'editMenuItemModal';
                editModal.innerHTML = `
                    <div class="modal-content" style="max-width: 600px;">
                        <button type="button" class="modal-close" onclick="closeEditModal()">
                            <i class="fas fa-times"></i>
                        </button>
                        <h3 class="modal-title">Edit Menu Item</h3>
                        <form onsubmit="saveMenuItem(event, ${id})">
                            <div class="admin-form">
                                <div class="admin-form-group">
                                    <label for="editMenuItemName">Item Name</label>
                                    <input type="text" id="editMenuItemName" value="${item.name}" required>
                                </div>
                                <div class="admin-form-group">
                                    <label for="editMenuItemPrice">Price ($)</label>
                                    <input type="number" id="editMenuItemPrice" value="${item.price}" step="0.01" min="0" required>
                                </div>
                                <div class="admin-form-group" style="grid-column: 1 / -1;">
                                    <label for="editMenuItemDescription">Description</label>
                                    <textarea id="editMenuItemDescription" required>${item.description}</textarea>
                                </div>
                                <div class="admin-form-group" style="grid-column: 1 / -1;">
                                    <label>Item Image</label>
                                    <div class="admin-image-upload">
                                        <div class="admin-image-preview" id="editItemImagePreview">
                                            <img src="${item.image}" alt="${item.name}">
                                        </div>
                                        <div>
                                            <input type="file" id="editItemImage" accept="image/*" style="display: none;" onchange="previewEditItemImage(event)">
                                            <button type="button" class="admin-image-upload-btn" onclick="document.getElementById('editItemImage').click()">Choose Image</button>
                                            <p style="margin-top: 10px; font-size: 0.9rem; color: #666;">Or enter image URL:</p>
                                            <input type="url" id="editItemImageUrl" value="${item.image}" oninput="previewEditItemImageUrl(this.value)">
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="modal-actions">
                                <button type="button" class="modal-btn cancel-btn" onclick="closeEditModal()">Cancel</button>
                                <button type="submit" class="modal-btn confirm-btn">Save Changes</button>
                            </div>
                        </form>
                    </div>
                `;
                
                document.body.appendChild(editModal);
            }
        }

        function closeEditModal() {
            const editModal = document.getElementById('editMenuItemModal');
            if (editModal) {
                document.body.removeChild(editModal);
            }
        }

        function saveMenuItem(event, id) {
            event.preventDefault();
            
            const name = document.getElementById('editMenuItemName').value;
            const price = parseFloat(document.getElementById('editMenuItemPrice').value);
            const description = document.getElementById('editMenuItemDescription').value;
            const imageUrl = document.getElementById('editItemImageUrl').value;
            
            // Find and update menu item
            const itemIndex = menuItems.findIndex(item => item.id === id);
            if (itemIndex !== -1) {
                menuItems[itemIndex] = {
                    id: id,
                    name: name,
                    price: price,
                    description: description,
                    image: imageUrl || menuItems[itemIndex].image
                };
                
                // Save data
                saveData();
                
                // Update UI
                renderMenuItems();
                renderAdminMenuItems();
                
                // Close modal
                closeEditModal();
                
                // Show success message
                showMessage('menuSuccessMessage', 'Menu item updated successfully!');
            }
        }

        function deleteMenuItem(id) {
            if (confirm('Are you sure you want to delete this menu item?')) {
                menuItems = menuItems.filter(item => item.id !== id);
                saveData();
                renderMenuItems();
                renderAdminMenuItems();
                showMessage('menuSuccessMessage', 'Menu item deleted successfully!');
            }
        }

        function handleRestaurantInfo(event) {
            event.preventDefault();
            
            // Update restaurant info
            restaurantInfo = {
                name: document.getElementById('restaurantName').value,
                tagline: document.getElementById('restaurantTagline').value,
                heroTitle: document.getElementById('heroTitle').value,
                heroDescription: document.getElementById('heroDescription').value,
                heroImage: document.getElementById('heroImageUrl').value,
                logoImage: document.getElementById('logoImageUrl').value
            };
            
            // Save data
            saveData();
            
            // Update website content
            updateWebsiteContent();
            
            // Show success message
            showMessage('infoSuccessMessage', 'Restaurant information updated successfully!');
        }

        function handleContactInfo(event) {
            event.preventDefault();
            
            // Update contact info
            contactInfo = {
                phoneNumber: document.getElementById('phoneNumber').value,
                telegramLink: document.getElementById('telegramLink').value,
                facebookLink: document.getElementById('facebookLink').value,
                instagramLink: document.getElementById('instagramLink').value,
                contactNote: document.getElementById('contactNote').value
            };
            
            // Save data
            saveData();
            
            // Update website content
            updateWebsiteContent();
            
            // Show success message
            showMessage('contactSuccessMessage', 'Contact information updated successfully!');
        }

        function handleDeliveryInfo(event) {
            event.preventDefault();
            
            // Get delivery apps
            const appInputs = document.querySelectorAll('.delivery-app-name');
            const apps = [];
            appInputs.forEach(input => {
                if (input.value.trim()) {
                    apps.push(input.value.trim());
                }
            });
            
            // Update delivery info
            deliveryInfo = {
                title: document.getElementById('deliveryTitle').value,
                description: document.getElementById('deliveryDescription').value,
                image: document.getElementById('deliveryImageUrl').value,
                apps: apps,
                note: document.getElementById('deliveryNote').value
            };
            
            // Save data
            saveData();
            
            // Update website content
            updateWebsiteContent();
            
            // Show success message
            showMessage('deliverySuccessMessage', 'Delivery information updated successfully!');
        }

        function addDeliveryApp() {
            const deliveryAppsList = document.getElementById('deliveryAppsList');
            const appDiv = document.createElement('div');
            appDiv.className = 'admin-form-group';
            appDiv.style.display = 'flex';
            appDiv.style.gap = '10px';
            appDiv.style.alignItems = 'center';
            appDiv.innerHTML = `
                <input type="text" class="delivery-app-name" value="" style="flex: 1;" placeholder="App name">
                <button type="button" class="admin-btn-danger remove-app-btn" onclick="removeDeliveryApp(this)">Remove</button>
            `;
            deliveryAppsList.appendChild(appDiv);
        }

        function removeDeliveryApp(button) {
            if (confirm('Are you sure you want to remove this app?')) {
                button.closest('.admin-form-group').remove();
            }
        }

        // Image preview functions
        function previewNewItemImage(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('newItemImagePreview').innerHTML = `<img src="${e.target.result}" alt="Preview">`;
                    document.getElementById('newItemImageUrl').value = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        }

        function previewNewItemImageUrl(url) {
            if (url) {
                document.getElementById('newItemImagePreview').innerHTML = `<img src="${url}" alt="Preview">`;
            } else {
                document.getElementById('newItemImagePreview').innerHTML = '<i class="fas fa-image" style="font-size: 3rem; color: #ccc;"></i>';
            }
        }

        function previewEditItemImage(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('editItemImagePreview').innerHTML = `<img src="${e.target.result}" alt="Preview">`;
                    document.getElementById('editItemImageUrl').value = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        }

        function previewEditItemImageUrl(url) {
            if (url) {
                document.getElementById('editItemImagePreview').innerHTML = `<img src="${url}" alt="Preview">`;
            } else {
                document.getElementById('editItemImagePreview').innerHTML = '<i class="fas fa-image" style="font-size: 3rem; color: #ccc;"></i>';
            }
        }

        function previewHeroImage(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('heroImagePreview').innerHTML = `<img src="${e.target.result}" alt="Preview">`;
                    document.getElementById('heroImageUrl').value = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        }

        function previewHeroImageUrl(url) {
            if (url) {
                document.getElementById('heroImagePreview').innerHTML = `<img src="${url}" alt="Preview">`;
            }
        }

        function previewLogoImage(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('logoImagePreview').innerHTML = `<img src="${e.target.result}" alt="Preview">`;
                    document.getElementById('logoImageUrl').value = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        }

        function previewLogoImageUrl(url) {
            if (url) {
                document.getElementById('logoImagePreview').innerHTML = `<img src="${url}" alt="Preview">`;
            }
        }

        function previewDeliveryImage(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('deliveryImagePreview').innerHTML = `<img src="${e.target.result}" alt="Preview">`;
                    document.getElementById('deliveryImageUrl').value = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        }

        function previewDeliveryImageUrl(url) {
            if (url) {
                document.getElementById('deliveryImagePreview').innerHTML = `<img src="${url}" alt="Preview">`;
            }
        }

        // Quantity modal functions
        function openQuantityModal(menuName, price) {
            currentMenuItem = menuName;
            currentPrice = price;
            
            // Set menu name in modal
            document.getElementById('selectedMenuName').textContent = menuName;
            
            // Reset quantity to 1
            document.getElementById('quantityInput').value = 1;
            
            // Show modal
            document.getElementById('quantityModal').classList.add('active');
        }

        function closeQuantityModal() {
            document.getElementById('quantityModal').classList.remove('active');
        }

        function decreaseQuantity() {
            let currentValue = parseInt(document.getElementById('quantityInput').value);
            if (currentValue > 1) {
                document.getElementById('quantityInput').value = currentValue - 1;
            }
        }

        function increaseQuantity() {
            let currentValue = parseInt(document.getElementById('quantityInput').value);
            if (currentValue < 99) {
                document.getElementById('quantityInput').value = currentValue + 1;
            }
        }

        function confirmAddToCart() {
            const quantity = parseInt(document.getElementById('quantityInput').value);
            
            // Add to cart
            addToCart(currentMenuItem, currentPrice, quantity);
            
            // Close modal
            closeQuantityModal();
        }

        function closeCartModal() {
            document.getElementById('cartModal').classList.remove('active');
        }

        // Initialize everything when DOM is loaded
        document.addEventListener('DOMContentLoaded', function() {
            // Load data from localStorage
            loadData();
            
            // Initialize website content
            updateWebsiteContent();
            
            // Render menu items
            renderMenuItems();
            
            // Initialize cart summary
            updateCartSummary();
            
            // Close modal when clicking outside
            document.getElementById('quantityModal').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeQuantityModal();
                }
            });
            
            document.getElementById('cartModal').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeCartModal();
                }
            });
            
            document.getElementById('adminLoginModal').addEventListener('click', function(e) {
                if (e.target === this) {
                    hideAdminLogin();
                }
            });
        });
    </script>
</body>
</html>
