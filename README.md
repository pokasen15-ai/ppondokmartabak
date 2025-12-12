<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pondok Martabak | Martabak Mesir & Masakan Terbaik</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #FF6B35;
            --secondary: #8B4513;
            --accent: #FFD700;
            --light: #FFF8F0;
            --dark: #2D3142;
            --success: #4ECDC4;
            --danger: #FF6B6B;
            --whatsapp: #25D366;
            --instagram: #E4405F;
            --facebook: #1877F2;
            --closed: #FF6B6B;
            --open: #4ECDC4;
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }
        
        .section-title h2 {
            color: var(--secondary);
            font-size: 2.5rem;
            display: inline-block;
            padding-bottom: 15px;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: var(--primary);
        }
        
        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
            backdrop-filter: blur(10px);
        }
        
        header.scrolled {
            padding: 5px 0;
            box-shadow: 0 5px 20px rgba(0,0,0,0.15);
            background: rgba(255, 255, 255, 0.98);
        }
        
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
            text-decoration: none;
        }
        
        .logo-icon {
            color: var(--primary);
            font-size: 2.5rem;
        }
        
        .logo-text h1 {
            color: var(--secondary);
            font-size: 1.8rem;
            line-height: 1.2;
        }
        
        .logo-text span {
            color: var(--primary);
            font-size: 0.9rem;
            font-weight: normal;
        }
        
        .status-header {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
            font-weight: 600;
            margin-left: 20px;
        }
        
        .status-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            display: inline-block;
        }
        
        .status-open {
            color: var(--open);
        }
        
        .status-closed {
            color: var(--closed);
        }
        
        .status-dot.open {
            background: var(--open);
            animation: pulse 2s infinite;
        }
        
        .status-dot.closed {
            background: var(--closed);
        }
        
        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.5; }
            100% { opacity: 1; }
        }
        
        /* Social Media Badge di Header */
        .social-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-left: 20px;
        }
        
        .social-header a {
            color: var(--dark);
            font-size: 1.2rem;
            transition: var(--transition);
            text-decoration: none;
            position: relative;
        }
        
        .social-header a:hover {
            transform: translateY(-3px);
        }
        
        .social-header .instagram:hover {
            color: var(--instagram);
        }
        
        .social-header .facebook:hover {
            color: var(--facebook);
        }
        
        .social-header .whatsapp:hover {
            color: var(--whatsapp);
        }
        
        .social-tooltip {
            position: absolute;
            bottom: -35px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--dark);
            color: white;
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 0.8rem;
            white-space: nowrap;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            z-index: 100;
        }
        
        .social-header a:hover .social-tooltip {
            opacity: 1;
            visibility: visible;
        }
        
        .nav-menu {
            display: flex;
            list-style: none;
            gap: 30px;
        }
        
        .nav-link {
            text-decoration: none;
            color: var(--dark);
            font-weight: 600;
            padding: 5px 0;
            position: relative;
            transition: var(--transition);
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 3px;
            background: var(--primary);
            transition: var(--transition);
        }
        
        .nav-link:hover::after,
        .nav-link.active::after {
            width: 100%;
        }
        
        .nav-link:hover,
        .nav-link.active {
            color: var(--primary);
        }
        
        .hamburger {
            display: none;
            cursor: pointer;
            font-size: 1.8rem;
            color: var(--secondary);
            transition: var(--transition);
        }
        
        /* Hero dengan Background Rumah Gadang */
        .hero {
            position: relative;
            background: linear-gradient(rgba(139, 69, 19, 0.85), rgba(139, 69, 19, 0.9)), 
                        url('https://images.unsplash.com/photo-1589391886085-9a6de4c7e43c?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: white;
            min-height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            padding-top: 100px;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><path fill="%23FFD700" fill-opacity="0.1" d="M0,0 L1200,0 L1200,800 L0,800 Z M600,400 Q800,200 1000,400 T600,400 Z"/></svg>');
            background-size: cover;
            opacity: 0.3;
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .hero h2 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            color: var(--accent);
            font-weight: bold;
        }
        
        .hero p {
            font-size: 1.3rem;
            margin-bottom: 30px;
            opacity: 0.95;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .motto {
            background: rgba(255, 215, 0, 0.9);
            color: var(--secondary);
            padding: 18px 35px;
            border-radius: 50px;
            display: inline-block;
            font-weight: bold;
            font-size: 1.2rem;
            margin-top: 25px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.3);
            animation: pulse 2s infinite;
            border: 2px solid var(--accent);
            position: relative;
            overflow: hidden;
        }
        
        .motto::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #FFD700, #FF6B35, #8B4513, #FFD700);
            background-size: 400% 400%;
            border-radius: 50px;
            z-index: -1;
            animation: gradientMove 3s ease infinite;
        }
        
        @keyframes gradientMove {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        .status-hero {
            margin-top: 30px;
            padding: 15px 25px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            display: inline-block;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }
        
        .status-hero .status-text {
            font-weight: 600;
            font-size: 1.1rem;
        }
        
        /* Social Media di Hero */
        .hero-social {
            margin-top: 40px;
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }
        
        .social-hero-btn {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1rem;
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255, 255, 255, 0.3);
        }
        
        .social-hero-btn.instagram {
            background: linear-gradient(45deg, var(--instagram), #833AB4);
            color: white;
        }
        
        .social-hero-btn.facebook {
            background: linear-gradient(45deg, var(--facebook), #0D8AF0);
            color: white;
        }
        
        .social-hero-btn.whatsapp {
            background: linear-gradient(45deg, var(--whatsapp), #128C7E);
            color: white;
        }
        
        .social-hero-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
            border-color: rgba(255, 255, 255, 0.5);
        }
        
        /* Elemen Dekoratif Rumah Gadang */
        .rumah-gadang-decoration {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 100%;
            height: 100%;
            pointer-events: none;
            opacity: 0.15;
            z-index: 1;
        }
        
        .rumah-gadang-decoration svg {
            width: 100%;
            height: 100%;
            fill: var(--accent);
        }
        
        /* Quick Order Button */
        .quick-order {
            position: fixed;
            bottom: 30px;
            left: 30px;
            background: var(--whatsapp);
            color: white;
            border: none;
            padding: 18px 30px;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.1rem;
            cursor: pointer;
            z-index: 99;
            box-shadow: 0 10px 30px rgba(37, 211, 102, 0.4);
            display: flex;
            align-items: center;
            gap: 12px;
            transition: var(--transition);
        }
        
        .quick-order:hover {
            background: #128C7E;
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(37, 211, 102, 0.6);
        }
        
        /* Taps */
        .taps-container {
            counter-reset: tap-counter;
        }
        
        .tap-card {
            background: white;
            border-radius: 20px;
            padding: 50px;
            margin-bottom: 50px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.08);
            position: relative;
            overflow: hidden;
            transition: var(--transition);
            border: 1px solid rgba(139, 69, 19, 0.1);
        }
        
        .tap-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 50px rgba(0,0,0,0.15);
        }
        
        .tap-card::before {
            counter-increment: tap-counter;
            content: "Tap " counter(tap-counter);
            position: absolute;
            top: 25px;
            right: 25px;
            background: var(--primary);
            color: white;
            padding: 8px 20px;
            border-radius: 25px;
            font-size: 1rem;
            font-weight: bold;
            box-shadow: 0 5px 15px rgba(255, 107, 53, 0.3);
        }
        
        .tap-header {
            display: flex;
            align-items: center;
            gap: 25px;
            margin-bottom: 35px;
            padding-bottom: 25px;
            border-bottom: 3px solid var(--light);
        }
        
        .tap-icon {
            width: 70px;
            height: 70px;
            background: var(--light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            color: var(--primary);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .tap-title {
            color: var(--secondary);
            font-size: 2.2rem;
        }
        
        /* Products */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 35px;
            margin-top: 50px;
        }
        
        .product-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            transition: var(--transition);
            border: 1px solid rgba(139, 69, 19, 0.1);
            position: relative;
        }
        
        .product-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }
        
        .product-img-container {
            height: 220px;
            position: relative;
            overflow: hidden;
            background-color: #f5f5f5;
        }
        
        .product-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .product-card:hover .product-img {
            transform: scale(1.05);
        }
        
        .product-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--accent);
            color: var(--secondary);
            padding: 8px 15px;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: bold;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            z-index: 2;
        }
        
        .product-info {
            padding: 30px;
        }
        
        .product-name {
            color: var(--secondary);
            font-size: 1.4rem;
            margin-bottom: 15px;
        }
        
        .product-price {
            color: var(--primary);
            font-size: 1.6rem;
            font-weight: bold;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        /* Upload Photo Button */
        .upload-photo-btn {
            position: absolute;
            bottom: 10px;
            left: 10px;
            background: rgba(255, 107, 53, 0.9);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            font-size: 0.8rem;
            cursor: pointer;
            z-index: 3;
            display: flex;
            align-items: center;
            gap: 5px;
            transition: var(--transition);
        }
        
        .upload-photo-btn:hover {
            background: var(--primary);
            transform: translateY(-2px);
        }
        
        .upload-photo-btn.admin-only {
            display: none;
        }
        
        .admin-mode .upload-photo-btn {
            display: flex !important;
        }
        
        /* QRIS Upload Button */
        .upload-qris-btn {
            background: rgba(255, 107, 53, 0.9);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            font-size: 0.8rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 5px;
            transition: var(--transition);
            margin-top: 10px;
            width: 100%;
            justify-content: center;
        }
        
        .upload-qris-btn:hover {
            background: var(--primary);
            transform: translateY(-2px);
        }
        
        .upload-qris-btn.admin-only {
            display: none;
        }
        
        .admin-mode .upload-qris-btn {
            display: flex !important;
        }
        
        /* QRIS Display */
        .qris-display {
            margin-top: 20px;
            text-align: center;
            padding: 20px;
            background: var(--light);
            border-radius: 15px;
            border: 2px dashed var(--primary);
            position: relative;
        }
        
        .qris-image {
            max-width: 250px;
            max-height: 250px;
            margin: 0 auto 15px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            border: 2px solid white;
        }
        
        .qris-placeholder {
            width: 250px;
            height: 250px;
            background: linear-gradient(45deg, #f5f5f5, #e0e0e0);
            margin: 0 auto 15px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #999;
            font-size: 0.9rem;
        }
        
        /* TOMBOL MODE ADMIN */
        .admin-mode-toggle {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: var(--secondary);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 50px;
            font-weight: bold;
            font-size: 0.9rem;
            cursor: pointer;
            z-index: 99;
            box-shadow: 0 5px 15px rgba(139, 69, 19, 0.4);
            display: flex;
            align-items: center;
            gap: 8px;
            transition: var(--transition);
        }
        
        .admin-mode-toggle:hover {
            background: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(139, 69, 19, 0.5);
        }
        
        .admin-mode-toggle.active {
            background: var(--primary);
            box-shadow: 0 0 0 3px var(--accent);
        }
        
        /* Upload Modal */
        .upload-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }
        
        .upload-modal.active {
            display: flex;
        }
        
        .upload-modal-content {
            background: white;
            padding: 30px;
            border-radius: 20px;
            width: 90%;
            max-width: 500px;
            max-height: 80vh;
            overflow-y: auto;
            position: relative;
        }
        
        .upload-preview {
            width: 100%;
            height: 200px;
            background: #f5f5f5;
            border-radius: 10px;
            margin: 20px 0;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }
        
        .upload-preview img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }
        
        /* Menu Categories */
        .menu-categories {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 40px;
        }
        
        .category-btn {
            background: var(--light);
            border: 2px solid var(--primary);
            color: var(--primary);
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .category-btn.active,
        .category-btn:hover {
            background: var(--primary);
            color: white;
        }
        
        /* Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.7);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            padding: 20px;
        }
        
        .modal-overlay.active {
            display: flex;
        }
        
        .modal {
            background: white;
            border-radius: 20px;
            width: 100%;
            max-width: 500px;
            max-height: 90vh;
            overflow-y: auto;
            animation: modalSlideIn 0.3s ease;
        }
        
        @keyframes modalSlideIn {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .modal-header {
            background: var(--whatsapp);
            color: white;
            padding: 25px;
            border-radius: 20px 20px 0 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .modal-header h3 {
            font-size: 1.5rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .close-modal {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }
        
        .close-modal:hover {
            background: rgba(255, 255, 255, 0.2);
        }
        
        /* WhatsApp Float Button */
        .whatsapp-float {
            position: fixed;
            bottom: 100px;
            right: 30px;
            width: 60px;
            height: 60px;
            background: var(--whatsapp);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            text-decoration: none;
            z-index: 99;
            box-shadow: 0 5px 20px rgba(37, 211, 102, 0.4);
            transition: var(--transition);
            animation: float 3s ease-in-out infinite;
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        
        .whatsapp-float:hover {
            background: #128C7E;
            transform: scale(1.1);
            box-shadow: 0 10px 25px rgba(37, 211, 102, 0.6);
        }
        
        /* Social Media Float Buttons */
        .social-float {
            position: fixed;
            bottom: 170px;
            right: 30px;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            text-decoration: none;
            z-index: 99;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            transition: var(--transition);
            animation: floatSocial 4s ease-in-out infinite;
        }
        
        .social-float.instagram {
            background: linear-gradient(45deg, var(--instagram), #833AB4);
            color: white;
            bottom: 170px;
        }
        
        .social-float.facebook {
            background: linear-gradient(45deg, var(--facebook), #0D8AF0);
            color: white;
            bottom: 240px;
        }
        
        @keyframes floatSocial {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-8px); }
            100% { transform: translateY(0px); }
        }
        
        .social-float:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 20px rgba(0,0,0,0.3);
        }
        
        /* Social Media Section */
        .social-media-section {
            background: linear-gradient(135deg, rgba(139, 69, 19, 0.05), rgba(255, 107, 53, 0.05));
            padding: 80px 0;
            margin-top: 70px;
        }
        
        .social-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }
        
        .social-card {
            background: white;
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            transition: var(--transition);
            border-top: 5px solid transparent;
            position: relative;
            overflow: hidden;
        }
        
        .social-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }
        
        .social-card.instagram {
            border-top-color: var(--instagram);
        }
        
        .social-card.facebook {
            border-top-color: var(--facebook);
        }
        
        .social-card.whatsapp {
            border-top-color: var(--whatsapp);
        }
        
        .social-icon {
            font-size: 3.5rem;
            margin-bottom: 25px;
            display: inline-block;
            width: 100px;
            height: 100px;
            line-height: 100px;
            border-radius: 50%;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .social-icon.instagram {
            background: linear-gradient(45deg, var(--instagram), #833AB4);
            color: white;
        }
        
        .social-icon.facebook {
            background: linear-gradient(45deg, var(--facebook), #0D8AF0);
            color: white;
        }
        
        .social-icon.whatsapp {
            background: linear-gradient(45deg, var(--whatsapp), #128C7E);
            color: white;
        }
        
        .social-card h3 {
            color: var(--secondary);
            font-size: 1.8rem;
            margin-bottom: 15px;
        }
        
        .social-card p {
            color: #666;
            margin-bottom: 25px;
            font-size: 1rem;
            line-height: 1.6;
        }
        
        .social-btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 12px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1rem;
            transition: var(--transition);
            margin-top: 10px;
        }
        
        .social-btn.instagram {
            background: linear-gradient(45deg, var(--instagram), #833AB4);
            color: white;
        }
        
        .social-btn.facebook {
            background: linear-gradient(45deg, var(--facebook), #0D8AF0);
            color: white;
        }
        
        .social-btn.whatsapp {
            background: linear-gradient(45deg, var(--whatsapp), #128C7E);
            color: white;
        }
        
        .social-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        }
        
        /* Footer */
        footer {
            background: var(--secondary);
            color: white;
            padding: 80px 0 25px;
            margin-top: 70px;
            position: relative;
        }
        
        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 45px;
            margin-bottom: 50px;
        }
        
        .footer-logo h3 {
            color: var(--accent);
            font-size: 2rem;
            margin-bottom: 20px;
        }
        
        .footer-links h4,
        .footer-contact h4 {
            color: var(--accent);
            margin-bottom: 30px;
            font-size: 1.3rem;
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 15px;
        }
        
        .footer-links a {
            color: #ddd;
            text-decoration: none;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .footer-links a:hover {
            color: var(--primary);
            padding-left: 10px;
        }
        
        /* Footer Social */
        .footer-social {
            margin-top: 25px;
        }
        
        .footer-social h4 {
            color: var(--accent);
            margin-bottom: 20px;
            font-size: 1.3rem;
        }
        
        .social-icons-footer {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }
        
        .social-icon-footer {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            text-decoration: none;
            transition: var(--transition);
            box-shadow: 0 3px 10px rgba(0,0,0,0.2);
        }
        
        .social-icon-footer.instagram {
            background: var(--instagram);
            color: white;
        }
        
        .social-icon-footer.facebook {
            background: var(--facebook);
            color: white;
        }
        
        .social-icon-footer.whatsapp {
            background: var(--whatsapp);
            color: white;
        }
        
        .social-icon-footer:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        
        .copyright {
            text-align: center;
            padding-top: 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.15);
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.95rem;
        }
        
        /* Back to Top Button */
        .back-to-top {
            position: fixed;
            bottom: 180px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: var(--primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            cursor: pointer;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            z-index: 100;
            box-shadow: 0 5px 20px rgba(255, 107, 53, 0.3);
        }
        
        .back-to-top.visible {
            opacity: 1;
            visibility: visible;
        }
        
        .back-to-top:hover {
            background: var(--secondary);
            transform: translateY(-5px);
        }
        
        /* Notification */
        .notification {
            animation: slideIn 0.3s ease;
        }
        
        @keyframes slideIn {
            from {
                transform: translateX(100%);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }
        
        /* Kerjasama Section */
        .partnership-section {
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.1), rgba(139, 69, 19, 0.1));
            padding: 80px 0;
            margin-top: 70px;
        }
        
        .partnership-card {
            background: white;
            border-radius: 20px;
            padding: 50px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.08);
            text-align: center;
            border: 2px solid var(--accent);
            position: relative;
            overflow: hidden;
        }
        
        .partnership-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
        }
        
        .partnership-icon {
            font-size: 3.5rem;
            color: var(--primary);
            margin-bottom: 25px;
            display: inline-block;
            background: var(--light);
            width: 100px;
            height: 100px;
            line-height: 100px;
            border-radius: 50%;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .partners-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }
        
        .partner-card {
            background: var(--light);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(139, 69, 19, 0.1);
        }
        
        .partner-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
            border-color: var(--primary);
        }
        
        .partner-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 20px;
            display: inline-block;
            background: white;
            width: 70px;
            height: 70px;
            line-height: 70px;
            border-radius: 50%;
        }
        
        .partner-name {
            color: var(--secondary);
            font-size: 1.4rem;
            margin-bottom: 10px;
        }
        
        .partner-location {
            color: var(--primary);
            font-weight: 600;
            margin-bottom: 15px;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .hero h2 {
                font-size: 3rem;
            }
            
            .section-title h2 {
                font-size: 2.2rem;
            }
            
            .tap-card {
                padding: 40px 30px;
            }
            
            .status-header {
                display: none;
            }
            
            .social-header {
                display: none;
            }
            
            .partnership-card {
                padding: 40px 30px;
            }
            
            .social-float {
                right: 20px;
            }
            
            .social-float.instagram {
                bottom: 170px;
            }
            
            .social-float.facebook {
                bottom: 240px;
            }
        }
        
        @media (max-width: 768px) {
            .hamburger {
                display: block;
            }
            
            .nav-menu {
                position: fixed;
                top: 85px;
                left: -100%;
                flex-direction: column;
                background: white;
                width: 100%;
                text-align: center;
                transition: var(--transition);
                box-shadow: 0 15px 30px rgba(0,0,0,0.1);
                padding: 30px 0;
                z-index: 999;
                border-top: 3px solid var(--primary);
            }
            
            .nav-menu.active {
                left: 0;
            }
            
            .hero {
                padding-top: 130px;
            }
            
            .hero h2 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .tap-card {
                padding: 35px 25px;
            }
            
            .tap-title {
                font-size: 1.8rem;
            }
            
            section {
                padding: 60px 0;
            }
            
            .quick-order {
                left: 20px;
                bottom: 20px;
                padding: 15px 25px;
                font-size: 1rem;
            }
            
            .admin-mode-toggle {
                bottom: 20px;
                right: 20px;
                padding: 10px 15px;
                font-size: 0.8rem;
            }
            
            .whatsapp-float {
                bottom: 90px;
                right: 20px;
                width: 55px;
                height: 55px;
                font-size: 1.6rem;
            }
            
            .social-float {
                width: 55px;
                height: 55px;
                font-size: 1.4rem;
                right: 20px;
            }
            
            .social-float.instagram {
                bottom: 160px;
            }
            
            .social-float.facebook {
                bottom: 225px;
            }
            
            .back-to-top {
                bottom: 160px;
                right: 20px;
            }
            
            .menu-categories {
                gap: 10px;
            }
            
            .category-btn {
                padding: 10px 20px;
                font-size: 0.9rem;
            }
            
            .partners-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            .partnership-section {
                padding: 60px 0;
            }
            
            .social-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            .social-media-section {
                padding: 60px 0;
            }
        }
        
        @media (max-width: 576px) {
            .hero h2 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .motto {
                font-size: 1.1rem;
                padding: 15px 25px;
            }
            
            .tap-title {
                font-size: 1.6rem;
            }
            
            .products-grid,
            .features-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                gap: 35px;
            }
            
            .modal {
                max-height: 95vh;
            }
            
            .upload-modal-content {
                padding: 20px;
            }
            
            .partnership-card {
                padding: 30px 20px;
            }
            
            .hero-social {
                flex-direction: column;
                align-items: center;
            }
            
            .social-hero-btn {
                width: 100%;
                max-width: 250px;
                justify-content: center;
            }
        }
        
        /* Photo Gallery Styles */
        .photo-gallery {
            display: flex;
            gap: 8px;
            margin-top: 15px;
            flex-wrap: wrap;
        }
        
        .gallery-thumbnail {
            width: 50px;
            height: 50px;
            object-fit: cover;
            border-radius: 5px;
            cursor: pointer;
            border: 2px solid transparent;
            transition: var(--transition);
        }
        
        .gallery-thumbnail:hover,
        .gallery-thumbnail.active {
            border-color: var(--primary);
            transform: scale(1.05);
        }
        
        .photo-count {
            position: absolute;
            top: 10px;
            left: 10px;
            background: rgba(0,0,0,0.7);
            color: white;
            padding: 3px 8px;
            border-radius: 10px;
            font-size: 0.7rem;
            z-index: 2;
        }
    </style>
</head>
<body>
    <!-- Quick Order Button -->
    <button class="quick-order" id="quickOrderBtn">
        <i class="fab fa-whatsapp"></i>
        Pesan Sekarang
    </button>

    <!-- WhatsApp Float Button -->
    <a href="https://wa.me/6285272955232" class="whatsapp-float" target="_blank" title="Chat langsung via WhatsApp">
        <i class="fab fa-whatsapp"></i>
    </a>

    <!-- Social Media Float Buttons -->
    <a href="https://www.facebook.com/share/1AEdAD7PjW/?mibextid=wwXIfr" class="social-float facebook" target="_blank" title="Follow kami di Facebook">
        <i class="fab fa-facebook-f"></i>
    </a>
    
    <a href="https://www.instagram.com/pondok_martabak_?igsh=ZW9la2ltMmFzd3Y5&utm_source=qr" class="social-float instagram" target="_blank" title="Follow kami di Instagram">
        <i class="fab fa-instagram"></i>
    </a>

    <!-- Back to Top Button -->
    <div class="back-to-top" id="backToTop">
        <i class="fas fa-chevron-up"></i>
    </div>

    <!-- Tombol Mode Admin -->
    <button class="admin-mode-toggle" id="adminModeToggle" title="Klik untuk masuk ke mode admin">
        <i class="fas fa-user-shield"></i>
        <span>Mode Admin</span>
    </button>

    <!-- Upload Photo Modal -->
    <div class="upload-modal" id="uploadModal">
        <div class="upload-modal-content">
            <h3 style="color: var(--secondary); margin-bottom: 20px;">
                <i class="fas fa-camera"></i> Upload Foto Produk
            </h3>
            
            <div style="margin-bottom: 20px;">
                <p>Unggah foto untuk: <strong id="uploadProductName">Produk</strong></p>
                <small style="color: #666;">Foto yang diupload akan terlihat oleh semua pengunjung</small>
            </div>
            
            <div class="upload-preview" id="uploadPreview">
                <p style="color: #999;">Pratinjau gambar akan muncul di sini</p>
            </div>
            
            <div style="margin-bottom: 20px;">
                <input type="file" id="photoUpload" accept="image/*" style="width: 100%; padding: 10px; border: 2px dashed var(--primary); border-radius: 10px;">
                <small style="color: #666; display: block; margin-top: 5px;">Pilih file gambar (JPG, PNG, max 5MB)</small>
            </div>
            
            <div style="display: flex; gap: 10px; margin-top: 20px;">
                <button id="savePhotoBtn" style="flex: 1; background: var(--primary); color: white; border: none; padding: 12px; border-radius: 8px; font-weight: 600; cursor: pointer;">
                    <i class="fas fa-save"></i> Simpan Foto
                </button>
                <button id="cancelUploadBtn" style="flex: 1; background: var(--danger); color: white; border: none; padding: 12px; border-radius: 8px; font-weight: 600; cursor: pointer;">
                    <i class="fas fa-times"></i> Batal
                </button>
            </div>
            
            <div id="photoHistory" style="margin-top: 20px; padding-top: 20px; border-top: 1px solid #eee; display: none;">
                <h4 style="color: var(--secondary); margin-bottom: 10px;">Foto yang sudah diupload:</h4>
                <div id="uploadedPhotosList"></div>
            </div>
        </div>
    </div>

    <!-- Upload QRIS Modal -->
    <div class="upload-modal" id="uploadQRISModal">
        <div class="upload-modal-content">
            <h3 style="color: var(--secondary); margin-bottom: 20px;">
                <i class="fas fa-qrcode"></i> Upload QRIS Pembayaran
            </h3>
            
            <div style="margin-bottom: 20px;">
                <p>Unggah foto QRIS untuk pembayaran</p>
                <small style="color: #666;">QRIS ini akan ditampilkan di halaman pembayaran</small>
            </div>
            
            <div class="upload-preview" id="uploadQRISPreview">
                <p style="color: #999;">Pratinjau QRIS akan muncul di sini</p>
            </div>
            
            <div style="margin-bottom: 20px;">
                <input type="file" id="qrisUpload" accept="image/*" style="width: 100%; padding: 10px; border: 2px dashed var(--primary); border-radius: 10px;">
                <small style="color: #666; display: block; margin-top: 5px;">Pilih file gambar QRIS (JPG, PNG, max 5MB)</small>
            </div>
            
            <div style="display: flex; gap: 10px; margin-top: 20px;">
                <button id="saveQRISBtn" style="flex: 1; background: var(--primary); color: white; border: none; padding: 12px; border-radius: 8px; font-weight: 600; cursor: pointer;">
                    <i class="fas fa-save"></i> Simpan QRIS
                </button>
                <button id="cancelQRISUploadBtn" style="flex: 1; background: var(--danger); color: white; border: none; padding: 12px; border-radius: 8px; font-weight: 600; cursor: pointer;">
                    <i class="fas fa-times"></i> Batal
                </button>
            </div>
            
            <div id="qrisInfo" style="margin-top: 20px; padding-top: 20px; border-top: 1px solid #eee;">
                <h4 style="color: var(--secondary); margin-bottom: 10px;">Informasi QRIS:</h4>
                <p style="font-size: 0.9rem; color: #666;">QRIS akan ditampilkan di bagian metode pembayaran. Pastikan kode QR jelas dan mudah dipindai.</p>
            </div>
        </div>
    </div>

    <!-- Quick Order Modal -->
    <div class="modal-overlay" id="orderModal">
        <div class="modal">
            <div class="modal-header">
                <h3><i class="fab fa-whatsapp"></i> Pesan via WhatsApp</h3>
                <button class="close-modal" id="closeModal">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="modal-body">
                <div id="orderCartModal">
                    <h4 style="color: var(--secondary); margin-bottom: 20px;">Keranjang Pesanan Anda:</h4>
                    <div id="cartItemsModal">
                        <p style="text-align: center; color: #999; padding: 20px;">Belum ada item dalam keranjang</p>
                    </div>
                    <div id="cartTotalModal" style="margin-top: 20px; padding-top: 20px; border-top: 2px solid var(--light); display: none;">
                        <h4 style="color: var(--secondary);">Total: <span id="totalAmountModal">Rp 0</span></h4>
                    </div>
                </div>
                
                <div style="margin-top: 30px;">
                    <h4 style="color: var(--secondary); margin-bottom: 15px;">Data Diri:</h4>
                    <div style="margin-bottom: 20px;">
                        <label style="display: block; margin-bottom: 8px; font-weight: 600;">Nama Lengkap *</label>
                        <input type="text" id="modalCustomerName" required style="width: 100%; padding: 15px; border: 2px solid var(--light); border-radius: 10px; font-size: 1rem;" placeholder="Masukkan nama lengkap Anda">
                    </div>
                    
                    <div style="margin-bottom: 20px;">
                        <label style="display: block; margin-bottom: 8px; font-weight: 600;">Nomor WhatsApp *</label>
                        <input type="tel" id="modalCustomerPhone" required style="width: 100%; padding: 15px; border: 2px solid var(--light); border-radius: 10px; font-size: 1rem;" placeholder="Contoh: 081234567890">
                        <small style="color: #666; display: block; margin-top: 5px;">Untuk konfirmasi pesanan</small>
                    </div>
                    
                    <div style="margin-bottom: 20px;">
                        <label style="display: block; margin-bottom: 8px; font-weight: 600;">Alamat Pengiriman</label>
                        <textarea id="modalCustomerAddress" rows="2" style="width: 100%; padding: 15px; border: 2px solid var(--light); border-radius: 10px; font-size: 1rem;" placeholder="Kosongkan jika ambil di tempat (Desa Tanjung Botung)"></textarea>
                    </div>
                    
                    <div style="margin-bottom: 25px;">
                        <label style="display: block; margin-bottom: 8px; font-weight: 600;">Catatan Tambahan</label>
                        <textarea id="modalOrderNotes" rows="2" style="width: 100%; padding: 15px; border: 2px solid var(--light); border-radius: 10px; font-size: 1rem;" placeholder="Contoh: Level pedas 5, tanpa bawang, dll."></textarea>
                    </div>
                    
                    <button id="sendWhatsAppBtn" style="background: var(--whatsapp); color: white; border: none; padding: 18px; border-radius: 10px; font-size: 1.1rem; font-weight: 600; cursor: pointer; width: 100%; transition: var(--transition); display: flex; align-items: center; justify-content: center; gap: 10px;">
                        <i class="fab fa-whatsapp"></i> Kirim Pesan ke WhatsApp
                    </button>
                    
                    <div style="text-align: center; margin-top: 15px; color: #666; font-size: 0.9rem;">
                        <p>Pesan akan dikirim ke: <strong>+62 852-7295-5232</strong> (Imam Musthofa)</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Header -->
    <header id="header">
        <div class="container">
            <nav class="navbar">
                <a href="#" class="logo">
                    <i class="fas fa-utensils logo-icon"></i>
                    <div class="logo-text">
                        <h1>Pondok Martabak</h1>
                        <span>Martabak Mesir & Masakan Terbaik</span>
                    </div>
                </a>
                
                <!-- Status Buka/Tutup di Header -->
                <div class="status-header" id="statusHeader">
                    <span class="status-dot" id="statusDot"></span>
                    <span class="status-text" id="statusText">Memuat status...</span>
                </div>
                
                <!-- Social Media Icons di Header -->
                <div class="social-header">
                    <a href="https://www.instagram.com/pondok_martabak_?igsh=ZW9la2ltMmFzd3Y5&utm_source=qr" class="instagram" target="_blank" title="Instagram Pondok Martabak">
                        <i class="fab fa-instagram"></i>
                        <span class="social-tooltip">Follow Instagram Kami</span>
                    </a>
                    <a href="https://www.facebook.com/share/1AEdAD7PjW/?mibextid=wwXIfr" class="facebook" target="_blank" title="Facebook Pondok Martabak">
                        <i class="fab fa-facebook-f"></i>
                        <span class="social-tooltip">Like Facebook Kami</span>
                    </a>
                    <a href="https://wa.me/6285272955232" class="whatsapp" target="_blank" title="WhatsApp Pondok Martabak">
                        <i class="fab fa-whatsapp"></i>
                        <span class="social-tooltip">Chat via WhatsApp</span>
                    </a>
                </div>
                
                <div class="hamburger" id="hamburger">
                    <i class="fas fa-bars"></i>
                </div>
                
                <ul class="nav-menu" id="navMenu">
                    <li><a href="#home" class="nav-link active">Beranda</a></li>
                    <li><a href="#about" class="nav-link">Tentang</a></li>
                    <li><a href="#products" class="nav-link">Menu</a></li>
                    <li><a href="#menu" class="nav-link">Daftar Harga</a></li>
                    <li><a href="#contact" class="nav-link">Kontak</a></li>
                    <li><a href="#social" class="nav-link">Media Sosial</a></li>
                    <li><a href="#payment" class="nav-link">Pembayaran</a></li>
                    <li><a href="#partnership" class="nav-link">Kerjasama</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section dengan Background Rumah Gadang -->
    <section class="hero" id="home">
        <!-- Elemen Dekoratif Rumah Gadang -->
        <div class="rumah-gadang-decoration">
            <svg viewBox="0 0 1200 800" preserveAspectRatio="xMidYMid slice">
                <!-- Atap Rumah Gadang -->
                <path d="M400,200 L800,200 Q900,100 1000,200 L1000,400 Q950,350 900,300 L600,300 Q500,250 400,300 L400,200 Z" 
                      fill="url(#goldGradient)" opacity="0.2"/>
                <!-- Badan Rumah -->
                <rect x="450" y="300" width="300" height="150" rx="10" fill="url(#brownGradient)" opacity="0.15"/>
                <!-- Pilar-pilar -->
                <rect x="480" y="450" width="20" height="100" fill="#8B4513" opacity="0.2"/>
                <rect x="580" y="450" width="20" height="100" fill="#8B4513" opacity="0.2"/>
                <rect x="680" y="450" width="20" height="100" fill="#8B4513" opacity="0.2"/>
                <!-- Ornamen -->
                <circle cx="600" cy="180" r="15" fill="#FFD700" opacity="0.3"/>
                <path d="M590,180 Q600,160 610,180" fill="none" stroke="#FFD700" stroke-width="3" opacity="0.3"/>
            </svg>
            <defs>
                <linearGradient id="goldGradient" x1="0%" y1="0%" x2="100%" y2="100%">
                    <stop offset="0%" style="stop-color:#FFD700;stop-opacity:0.3" />
                    <stop offset="100%" style="stop-color:#FF6B35;stop-opacity:0.2" />
                </linearGradient>
                <linearGradient id="brownGradient" x1="0%" y1="0%" x2="100%" y2="100%">
                    <stop offset="0%" style="stop-color:#8B4513;stop-opacity:0.2" />
                    <stop offset="100%" style="stop-color:#A0522D;stop-opacity:0.15" />
                </linearGradient>
            </defs>
        </div>
        
        <div class="container">
            <div class="hero-content">
                <h2><i class="fas fa-home"></i> Pondok Martabak</h2>
                <p>Martabak Mesir spesial dengan resep rahasia keluarga. Rasa autentik yang membuat Anda ketagihan!</p>
                <div class="motto">"Gurihnya Martabak Mesir, Nikmatnya Masakan Rumahan"</div>
                
                <!-- Status Buka/Tutup di Hero -->
                <div class="status-hero">
                    <div class="status-text" id="heroStatusText">Memuat status...</div>
                    <div id="heroStatusDetails" style="font-size: 0.9rem; margin-top: 5px;"></div>
                </div>
                
                <!-- Social Media di Hero -->
                <div class="hero-social">
                    <a href="https://www.instagram.com/pondok_martabak_?igsh=ZW9la2ltMmFzd3Y5&utm_source=qr" class="social-hero-btn instagram" target="_blank">
                        <i class="fab fa-instagram"></i> Follow Instagram
                    </a>
                    <a href="https://www.facebook.com/share/1AEdAD7PjW/?mibextid=wwXIfr" class="social-hero-btn facebook" target="_blank">
                        <i class="fab fa-facebook-f"></i> Like Facebook
                    </a>
                    <a href="https://wa.me/6285272955232" class="social-hero-btn whatsapp" target="_blank">
                        <i class="fab fa-whatsapp"></i> Chat WhatsApp
                    </a>
                </div>
                
                <div style="margin-top: 40px;">
                    <button class="quick-order" style="position: static; background: rgba(255, 255, 255, 0.9); color: var(--whatsapp); box-shadow: 0 10px 30px rgba(0,0,0,0.2); border: 2px solid var(--whatsapp);" id="heroOrderBtn">
                        <i class="fab fa-whatsapp"></i>
                        Pesan Sekarang via WhatsApp
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Main Content -->
    <main class="container">
        <!-- Tentang Usaha -->
        <section id="about" class="taps-container">
            <div class="section-title">
                <h2><i class="fas fa-store"></i> Tentang Pondok Martabak</h2>
            </div>
            
            <div class="tap-card">
                <div class="tap-header">
                    <div class="tap-icon">
                        <i class="fas fa-home"></i>
                    </div>
                    <h2 class="tap-title">Rumah Makan Khas</h2>
                </div>
                
                <div class="tap-content">
                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 35px; margin-bottom: 35px;">
                        <div>
                            <h3 style="color: var(--secondary); margin-bottom: 20px;">Identitas Usaha</h3>
                            <p><strong>🏠 Nama:</strong> Pondok Martabak</p>
                            <p><strong>👤 Pemilik:</strong> Imam Musthofa</p>
                            <p><strong>🍽️ Spesialisasi:</strong> Martabak Mesir & Masakan Rumahan</p>
                            <p><strong>📜 Sertifikat Halal:</strong> MUI-54321/2024</p>
                        </div>
                        
                        <div>
                            <h3 style="color: var(--secondary); margin-bottom: 20px;">Informasi Kontak</h3>
                            <p><strong>📱 WhatsApp:</strong> +62 852-7295-5232</p>
                            <p><strong>👤 Pemilik:</strong> Imam Musthofa</p>
                            <p><strong>⏰ Jam Operasional:</strong> 16:00 - 23:00 WIB</p>
                            <p><strong>📍 Alamat:</strong> Desa Tanjung Botung, Provinsi Sumatera Utara</p>
                        </div>
                    </div>
                    
                    <div style="background: var(--light); padding: 30px; border-radius: 15px; margin-top: 30px; border-left: 4px solid var(--primary);">
                        <h3 style="color: var(--secondary); margin-bottom: 20px;">🍛 Filosofi Kami</h3>
                        <p style="margin-bottom: 15px;">Pondok Martabak berkomitmen memberikan cita rasa autentik yang terjaga keasliannya.</p>
                        <p>"<em>Menyajikan masakan dengan cinta dan keikhlasan</em>" - prinsip kami dalam setiap hidangan.</p>
                    </div>
                    
                    <div style="background: var(--light); padding: 30px; border-radius: 15px; margin-top: 30px;">
                        <h3 style="color: var(--secondary); margin-bottom: 20px;">Jam Operasional & Lokasi</h3>
                        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px;">
                            <div>
                                <p><strong>📍 Alamat Lengkap:</strong></p>
                                <p>Desa Tanjung Botung, Provinsi Sumatera Utara</p>
                                <p><small>Dekat dengan pemandangan alam yang indah</small></p>
                            </div>
                            <div>
                                <p><strong>⏰ Jam Buka:</strong></p>
                                <p>16:00 - 23:00 WIB</p>
                                <p><em style="color: var(--open);">Buka: Senin, Selasa, Kamis, Jumat, Sabtu</em></p>
                                <p><em style="color: var(--closed);">Tutup: Rabu & Minggu</em></p>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Informasi Tutup Rabu & Minggu -->
                    <div style="background: linear-gradient(135deg, rgba(255, 107, 53, 0.1), rgba(255, 107, 107, 0.1)); padding: 25px; border-radius: 15px; margin-top: 30px; border-left: 4px solid var(--closed);">
                        <h4 style="color: var(--closed); margin-bottom: 15px; display: flex; align-items: center; gap: 10px;">
                            <i class="fas fa-exclamation-circle"></i> Informasi Hari Tutup
                        </h4>
                        <p>Pondok Martabak <strong style="color: var(--closed);">TUTUP setiap hari Rabu dan Minggu</strong>.</p>
                        <p>Pada hari-hari tersebut, kami tidak melayani pemesanan baik secara langsung maupun delivery.</p>
                        <p style="margin-top: 10px; font-size: 0.9rem; color: #666;">Kami buka kembali pada hari Senin, Selasa, Kamis, Jumat, dan Sabtu pukul 16:00 - 23:00 WIB.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Menu Unggulan dengan Upload Foto -->
        <section id="products" class="taps-container">
            <div class="section-title">
                <h2><i class="fas fa-utensils"></i> Menu Spesial</h2>
                <p style="color: #666; margin-top: 10px; max-width: 600px; margin-left: auto; margin-right: auto;">
                    Klik tombol "Ganti Foto" pada setiap produk untuk mengunggah foto makanan Anda sendiri
                </p>
                <p style="color: var(--primary); font-weight: 600; margin-top: 5px;">
                    <i class="fas fa-info-circle"></i> Foto yang diupload akan terlihat oleh semua pengunjung
                </p>
            </div>
            
            <div class="tap-card">
                <div class="tap-header">
                    <div class="tap-icon">
                        <i class="fas fa-utensils"></i>
                    </div>
                    <h2 class="tap-title">Menu Andalan Kami</h2>
                </div>
                
                <!-- Category Filter -->
                <div class="menu-categories" id="menuCategories">
                    <button class="category-btn active" data-category="all">Semua Menu</button>
                    <button class="category-btn" data-category="martabak">Martabak Mesir</button>
                    <button class="category-btn" data-category="nasi">Nasi Goreng</button>
                    <button class="category-btn" data-category="mie">Mie & Indomie</button>
                    <button class="category-btn" data-category="roti">Roti Cane</button>
                </div>
                
                <div class="products-grid" id="productsGrid">
                    <!-- Products will be populated by JavaScript -->
                </div>
                
                <div style="text-align: center; margin-top: 40px;">
                    <button class="quick-order" style="position: static; display: inline-flex; background: var(--whatsapp); color: white; border: none;" id="productsOrderBtn">
                        <i class="fab fa-whatsapp"></i> Pesan via WhatsApp
                    </button>
                </div>
            </div>
        </section>

        <!-- Daftar Harga Lengkap -->
        <section id="menu" class="taps-container">
            <div class="section-title">
                <h2><i class="fas fa-list-alt"></i> Daftar Harga Lengkap</h2>
            </div>
            
            <div class="tap-card">
                <div class="tap-header">
                    <div class="tap-icon">
                        <i class="fas fa-list-alt"></i>
                    </div>
                    <h2 class="tap-title">Daftar Harga Pondok Martabak</h2>
                </div>
                
                <div style="overflow-x: auto; margin-top: 30px;">
                    <table style="width: 100%; border-collapse: collapse;">
                        <thead>
                            <tr style="background: var(--primary); color: white;">
                                <th style="padding: 20px; text-align: left;">Menu</th>
                                <th style="padding: 20px; text-align: left;">Harga</th>
                                <th style="padding: 20px; text-align: center;">Pesan</th>
                            </tr>
                        </thead>
                        <tbody id="menuTable">
                            <!-- Menu items will be populated by JavaScript -->
                        </tbody>
                    </table>
                </div>
                
                <div style="text-align: center; margin-top: 40px;">
                    <div style="background: var(--light); padding: 25px; border-radius: 15px; margin-bottom: 25px; border: 2px solid var(--accent);">
                        <h4 style="color: var(--secondary); margin-bottom: 15px;">📱 Pesan via WhatsApp</h4>
                        <p>Nomor WhatsApp: <strong>+62 852-7295-5232</strong></p>
                        <p>Pemilik: <strong>Imam Musthofa</strong></p>
                        <p>Jam Operasional: <strong>16:00 - 23:00 WIB</strong></p>
                        <p>Hari Buka: <strong>Senin, Selasa, Kamis, Jumat, Sabtu</strong></p>
                        <p style="color: var(--closed);">Tutup: <strong>Rabu & Minggu</strong></p>
                    </div>
                    
                    <button class="quick-order" style="position: static; display: inline-flex; background: var(--whatsapp); color: white; border: none;" id="menuOrderBtn">
                        <i class="fab fa-whatsapp"></i> Pesan Sekarang via WhatsApp
                    </button>
                </div>
            </div>
        </section>

        <!-- Kontak & Lokasi -->
        <section id="contact" class="taps-container">
            <div class="section-title">
                <h2><i class="fas fa-address-book"></i> Kontak & Lokasi</h2>
            </div>
            
            <div class="tap-card">
                <div class="tap-header">
                    <div class="tap-icon">
                        <i class="fas fa-address-book"></i>
                    </div>
                    <h2 class="tap-title">Hubungi Kami</h2>
                </div>
                
                <div class="contact-grid">
                    <div class="contact-card">
                        <i class="fab fa-whatsapp" style="font-size: 2.5rem; color: var(--whatsapp); margin-bottom: 20px;"></i>
                        <h3>WhatsApp Order</h3>
                        <p><strong>+62 852-7295-5232</strong></p>
                        <p>Imam Musthofa</p>
                        <p><small>Respon cepat 16:00 - 23:00 WIB</small></p>
                        <p><small style="color: var(--closed);">Tutup Rabu & Minggu</small></p>
                        <a href="https://wa.me/6285272955232" class="whatsapp-direct-btn" target="_blank" style="background: var(--whatsapp); color: white; border: none; padding: 12px 25px; border-radius: 8px; font-weight: 600; cursor: pointer; transition: var(--transition); display: inline-block; margin-top: 10px; text-decoration: none;">
                            <i class="fab fa-whatsapp"></i> Chat Sekarang
                        </a>
                    </div>
                    
                    <div class="contact-card">
                        <i class="fas fa-user-tie" style="font-size: 2.5rem; color: var(--primary); margin-bottom: 20px;"></i>
                        <h3>Pemilik</h3>
                        <p><strong>Imam Musthofa</strong></p>
                        <p>Owner Pondok Martabak</p>
                        <p><small>Pengelola usaha</small></p>
                    </div>
                    
                    <div class="contact-card">
                        <i class="fas fa-map-marked-alt" style="font-size: 2.5rem; color: var(--primary); margin-bottom: 20px;"></i>
                        <h3>Lokasi Toko</h3>
                        <p><strong>Desa Tanjung Botung</strong></p>
                        <p><small>Provinsi Sumatera Utara</small></p>
                        <p><small style="color: var(--closed);">Tutup Rabu & Minggu</small></p>
                        <a href="https://maps.app.goo.gl/jU9D7RvUcHhyy12a8" class="maps-btn" target="_blank" style="background: var(--secondary); color: white; border: none; padding: 12px 25px; border-radius: 8px; font-weight: 600; cursor: pointer; transition: var(--transition); display: inline-block; margin-top: 10px; text-decoration: none;">
                            <i class="fas fa-map-marker-alt"></i> Lihat di Google Maps
                        </a>
                    </div>
                </div>
                
                <div style="text-align: center; margin-top: 40px; padding: 25px; background: linear-gradient(135deg, var(--whatsapp), #128C7E); border-radius: 20px; color: white;">
                    <h3 style="margin-bottom: 15px; font-size: 1.5rem;">📞 WhatsApp Langsung</h3>
                    <p style="margin-bottom: 20px; font-size: 1.2rem;">Klik tombol di bawah untuk chat langsung dengan Imam Musthofa:</p>
                    
                    <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px; margin-top: 25px;">
                        <a href="https://wa.me/6285272955232?text=Halo%20Pondok%20Martabak,%20saya%20mau%20pesan%20martabak%20mesir" class="whatsapp-direct-btn" target="_blank" style="background: white; color: var(--whatsapp); text-decoration: none; padding: 15px 30px; border-radius: 10px; font-weight: bold; font-size: 1.1rem; transition: var(--transition); display: flex; align-items: center; gap: 10px;">
                            <i class="fab fa-whatsapp"></i> Pesan Martabak Mesir
                        </a>
                        
                        <a href="https://wa.me/6285272955232?text=Halo%20Imam%20Musthofa,%20saya%20mau%20tanya%20tentang%20menu%20dan%20harga" class="whatsapp-direct-btn" target="_blank" style="background: white; color: var(--whatsapp); text-decoration: none; padding: 15px 30px; border-radius: 10px; font-weight: bold; font-size: 1.1rem; transition: var(--transition); display: flex; align-items: center; gap: 10px;">
                            <i class="fas fa-question-circle"></i> Tanya Menu
                        </a>
                    </div>
                </div>
                
                <div style="background: var(--light); padding: 25px; border-radius: 15px; margin-top: 40px; border: 2px dashed var(--primary);">
                    <h4 style="color: var(--secondary); text-align: center; margin-bottom: 20px;">📍 Informasi Lokasi</h4>
                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; text-align: center;">
                        <div>
                            <p><strong>Alamat:</strong></p>
                            <p>Desa Tanjung Botung</p>
                            <p><small>Provinsi Sumatera Utara</small></p>
                        </div>
                        <div>
                            <p><strong>Jam Operasional:</strong></p>
                            <p>16:00 - 23:00 WIB</p>
                            <p><em>Senin, Selasa, Kamis, Jumat, Sabtu</em></p>
                            <p><em style="color: var(--closed);">Tutup: Rabu & Minggu</em></p>
                        </div>
                        <div>
                            <p><strong>Delivery:</strong></p>
                            <p>Tersedia untuk sekitar lokasi</p>
                            <p><small>Area Tanjung Botung dan sekitarnya</small></p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Media Sosial Section -->
        <section id="social" class="social-media-section">
            <div class="container">
                <div class="section-title">
                    <h2><i class="fas fa-share-alt"></i> Media Sosial Kami</h2>
                    <p style="color: #666; margin-top: 10px; max-width: 800px; margin-left: auto; margin-right: auto;">
                        Ikuti perkembangan terbaru, promo spesial, dan foto-foto makanan kami di media sosial
                    </p>
                </div>
                
                <div class="social-grid">
                    <div class="social-card instagram">
                        <div class="social-icon instagram">
                            <i class="fab fa-instagram"></i>
                        </div>
                        <h3>Instagram</h3>
                        <p>Ikuti Instagram kami untuk melihat foto-foto makanan terbaru, promo spesial, dan cerita di balik dapur Pondok Martabak.</p>
                        
                        <!-- Statistik dihapus -->
                        
                        <a href="https://www.instagram.com/pondok_martabak_?igsh=ZW9la2ltMmFzd3Y5&utm_source=qr" class="social-btn instagram" target="_blank">
                            <i class="fab fa-instagram"></i> Follow @pondok_martabak_
                        </a>
                    </div>
                    
                    <div class="social-card facebook">
                        <div class="social-icon facebook">
                            <i class="fab fa-facebook-f"></i>
                        </div>
                        <h3>Facebook</h3>
                        <p>Like halaman Facebook kami untuk mendapatkan update jadwal buka, menu spesial hari ini, dan info menarik lainnya.</p>
                        
                        <!-- Statistik dihapus -->
                        
                        <a href="https://www.facebook.com/share/1AEdAD7PjW/?mibextid=wwXIfr" class="social-btn facebook" target="_blank">
                            <i class="fab fa-facebook-f"></i> Like Pondok Martabak
                        </a>
                    </div>
                    
                    <div class="social-card whatsapp">
                        <div class="social-icon whatsapp">
                            <i class="fab fa-whatsapp"></i>
                        </div>
                        <h3>WhatsApp</h3>
                        <p>Hubungi kami via WhatsApp untuk pemesanan cepat, konfirmasi pesanan, atau bertanya tentang menu dan harga.</p>
                        
                        <!-- Statistik dihapus -->
                        
                        <a href="https://wa.me/6285272955232" class="social-btn whatsapp" target="_blank">
                            <i class="fab fa-whatsapp"></i> Chat via WhatsApp
                        </a>
                    </div>
                </div>
                
                <div style="text-align: center; margin-top: 50px; padding: 35px; background: white; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.08); border: 2px solid var(--accent);">
                    <h3 style="color: var(--secondary); margin-bottom: 20px;">📱 Tetap Terhubung dengan Kami</h3>
                    <p style="margin-bottom: 20px; font-size: 1.1rem;">Dengan mengikuti media sosial kami, Anda akan menjadi yang pertama tahu tentang:</p>
                    
                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; margin-top: 25px;">
                        <div style="text-align: center;">
                            <div style="width: 60px; height: 60px; background: var(--primary); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 15px; font-size: 1.5rem;">
                                <i class="fas fa-percent"></i>
                            </div>
                            <p style="font-weight: 600; color: var(--secondary);">Promo Spesial</p>
                            <p style="font-size: 0.9rem; color: #666;">Diskon dan penawaran khusus</p>
                        </div>
                        
                        <div style="text-align: center;">
                            <div style="width: 60px; height: 60px; background: var(--instagram); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 15px; font-size: 1.5rem;">
                                <i class="fas fa-camera"></i>
                            </div>
                            <p style="font-weight: 600; color: var(--secondary);">Foto Makanan</p>
                            <p style="font-size: 0.9rem; color: #666;">Update menu dan foto terbaru</p>
                        </div>
                        
                        <div style="text-align: center;">
                            <div style="width: 60px; height: 60px; background: var(--facebook); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 15px; font-size: 1.5rem;">
                                <i class="fas fa-calendar"></i>
                            </div>
                            <p style="font-weight: 600; color: var(--secondary);">Info Jadwal</p>
                            <p style="font-size: 0.9rem; color: #666;">Perubahan jam operasional</p>
                        </div>
                        
                        <div style="text-align: center;">
                            <div style="width: 60px; height: 60px; background: var(--whatsapp); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 15px; font-size: 1.5rem;">
                                <i class="fas fa-bell"></i>
                            </div>
                            <p style="font-weight: 600; color: var(--secondary);">Notifikasi</p>
                            <p style="font-size: 0.9rem; color: #666;">Update langsung ke HP Anda</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Pembayaran dengan QRIS -->
        <section id="payment" class="taps-container">
            <div class="section-title">
                <h2><i class="fas fa-credit-card"></i> Pembayaran</h2>
                <p style="color: #666; margin-top: 10px; max-width: 600px; margin-left: auto; margin-right: auto;">
                    Tersedia berbagai metode pembayaran termasuk QRIS untuk kemudahan bertransaksi
                </p>
            </div>
            
            <div class="tap-card">
                <div class="tap-header">
                    <div class="tap-icon">
                        <i class="fas fa-credit-card"></i>
                    </div>
                    <h2 class="tap-title">Metode Pembayaran</h2>
                </div>
                
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; margin-bottom: 40px;">
                    <div style="background: var(--light); padding: 25px; border-radius: 15px; border: 2px solid var(--accent);">
                        <h3 style="color: var(--secondary); margin-bottom: 15px;">💵 Pembayaran Offline</h3>
                        <p><strong>🏠 Bayar di Toko:</strong> Desa Tanjung Botung, Provinsi Sumatera Utara</p>
                        <p><strong>💳 Metode:</strong> Cash, Debit Card, QRIS</p>
                        <p><strong>⏰ Jam:</strong> 16:00 - 23:00 WIB</p>
                        <p><em>Senin, Selasa, Kamis, Jumat, Sabtu</em></p>
                    </div>
                    
                    <div style="background: var(--light); padding: 25px; border-radius: 15px; border: 2px solid var(--accent);">
                        <h3 style="color: var(--secondary); margin-bottom: 15px;">📱 Pembayaran Online</h3>
                        <p>Transfer bank atau e-wallet untuk pesanan delivery</p>
                        <p><strong>✅ Konfirmasi:</strong> Kirim bukti transfer ke WhatsApp</p>
                        <p><small style="color: var(--closed);">Tutup Rabu & Minggu</small></p>
                    </div>
                </div>
                
                <h3 style="color: var(--secondary); margin: 30px 0 20px;">Metode Pembayaran Online:</h3>
                <div class="payment-methods">
                    <div class="payment-method">
                        <i class="fas fa-university" style="color: var(--primary); font-size: 1.8rem;"></i>
                        <div>
                            <strong>Bank BCA</strong>
                            <p>1234567890 a.n. Pondok Martabak</p>
                        </div>
                    </div>
                    <div class="payment-method">
                        <i class="fab fa-gopay" style="color: var(--primary); font-size: 1.8rem;"></i>
                        <div>
                            <strong>GoPay</strong>
                            <p>085272955232</p>
                        </div>
                    </div>
                    <div class="payment-method">
                        <i class="fas fa-wallet" style="color: var(--primary); font-size: 1.8rem;"></i>
                        <div>
                            <strong>OVO</strong>
                            <p>085272955232</p>
                        </div>
                    </div>
                    <div class="payment-method">
                        <i class="fas fa-qrcode" style="color: var(--primary); font-size: 1.8rem;"></i>
                        <div>
                            <strong>QRIS</strong>
                            <p>Scan untuk semua e-wallet</p>
                        </div>
                    </div>
                </div>
                
                <!-- QRIS Display Section -->
                <div class="qris-display" id="qrisDisplay">
                    <h4 style="color: var(--secondary); margin-bottom: 15px;">
                        <i class="fas fa-qrcode"></i> QRIS Pondok Martabak
                    </h4>
                    <p style="margin-bottom: 15px; color: #666;">Scan kode QR di bawah untuk pembayaran via e-wallet (GoPay, OVO, Dana, dll.)</p>
                    
                    <div id="qrisImageContainer">
                        <div class="qris-placeholder" id="qrisPlaceholder">
                            <div style="text-align: center;">
                                <i class="fas fa-qrcode" style="font-size: 3rem; color: #ccc; margin-bottom: 10px;"></i>
                                <p>QRIS belum diupload</p>
                                <p style="font-size: 0.8rem;">Admin dapat mengupload QRIS</p>
                            </div>
                        </div>
                    </div>
                    
                    <p style="margin-top: 10px; font-size: 0.9rem; color: #666;">
                        Gunakan aplikasi e-wallet Anda untuk scan QRIS di atas
                    </p>
                    
                    <!-- QRIS Upload Button - Hanya untuk Admin -->
                    <button class="upload-qris-btn admin-only" id="uploadQRISBtn">
                        <i class="fas fa-camera"></i> Ganti QRIS
                    </button>
                </div>
                
                <div style="text-align: center; margin-top: 50px; padding: 35px; background: var(--light); border-radius: 20px; border: 2px solid var(--primary);">
                    <h3 style="color: var(--secondary); margin-bottom: 20px;">💬 Konfirmasi Pembayaran</h3>
                    <p>Setelah transfer atau scan QRIS, konfirmasi ke WhatsApp Imam Musthofa:</p>
                    <p><small style="color: var(--closed);">*Perhatikan hari dan jam operasional kami</small></p>
                    <a href="https://wa.me/6285272955232?text=Halo%20Imam%20Musthofa,%20saya%20sudah%20transfer%20untuk%20pesanan%20martabak%20mesir" class="whatsapp-direct-btn" target="_blank" style="background: var(--whatsapp); color: white; text-decoration: none; padding: 15px 30px; border-radius: 10px; font-weight: bold; font-size: 1.1rem; margin-top: 15px; display: inline-block; transition: var(--transition);">
                        <i class="fab fa-whatsapp"></i> Konfirmasi ke WhatsApp
                    </a>
                </div>
            </div>
        </section>

        <!-- Kerjasama dengan Toko Lain -->
        <section id="partnership" class="partnership-section">
            <div class="container">
                <div class="section-title">
                    <h2><i class="fas fa-handshake"></i> Kerjasama Kami</h2>
                    <p style="color: #666; margin-top: 10px; max-width: 800px; margin-left: auto; margin-right: auto;">
                        Pondok Martabak bekerjasama dengan toko-toko terbaik di Desa Tanjung Botung untuk menyajikan bahan-bahan berkualitas tinggi
                    </p>
                </div>
                
                <div class="partnership-card">
                    <div class="partnership-icon">
                        <i class="fas fa-handshake"></i>
                    </div>
                    
                    <h3 style="color: var(--secondary); margin-bottom: 20px; font-size: 1.8rem;">Mitra Bahan Baku Berkualitas</h3>
                    <p style="margin-bottom: 30px; font-size: 1.1rem; max-width: 800px; margin-left: auto; margin-right: auto;">
                        Untuk menjaga kualitas dan cita rasa autentik martabak mesir kami, kami bekerja sama dengan toko-toko terpercaya di Desa Tanjung Botung yang menyediakan bahan-bahan segar dan berkualitas tinggi.
                    </p>
                    
                    <div class="partners-grid">
                        <div class="partner-card">
                            <div class="partner-icon" style="background: linear-gradient(135deg, #FFD700, #FF6B35); color: white;">
                                <i class="fas fa-drumstick-bite"></i>
                            </div>
                            <h4 class="partner-name">Toko Daging Ayam Segar</h4>
                            <p class="partner-location">Desa Tanjung Botung</p>
                            <p>Menyediakan daging ayam segar pilihan untuk isian martabak mesir kami. Daging ayam dipilih dengan kualitas terbaik untuk memastikan cita rasa yang autentik.</p>
                            <div style="margin-top: 15px;">
                                <span style="background: var(--accent); color: var(--secondary); padding: 5px 15px; border-radius: 20px; font-size: 0.9rem; font-weight: 600;">Mitra Resmi</span>
                            </div>
                        </div>
                        
                        <div class="partner-card">
                            <div class="partner-icon" style="background: linear-gradient(135deg, #8B4513, #A0522D); color: white;">
                                <i class="fas fa-hamburger"></i>
                            </div>
                            <h4 class="partner-name">Toko Daging Sapi Premium</h4>
                            <p class="partner-location">Desa Tanjung Botung</p>
                            <p>Menyediakan daging sapi premium untuk variasi martabak mesir spesial kami. Daging sapi dipilih dengan standar tinggi untuk menghasilkan rasa yang gurih dan nikmat.</p>
                            <div style="margin-top: 15px;">
                                <span style="background: var(--accent); color: var(--secondary); padding: 5px 15px; border-radius: 20px; font-size: 0.9rem; font-weight: 600;">Mitra Resmi</span>
                            </div>
                        </div>
                    </div>
                    
                    <div style="margin-top: 40px; padding: 25px; background: var(--light); border-radius: 15px; border-left: 4px solid var(--primary);">
                        <h4 style="color: var(--secondary); margin-bottom: 15px; display: flex; align-items: center; gap: 10px;">
                            <i class="fas fa-info-circle"></i> Komitmen Kualitas
                        </h4>
                        <p>Dengan kerjasama ini, kami menjamin bahwa setiap bahan yang digunakan dalam martabak mesir dan masakan kami adalah bahan-bahan segar dengan kualitas terbaik dari toko-toko terpercaya di Desa Tanjung Botung.</p>
                        <p style="margin-top: 10px; font-weight: 600; color: var(--primary);">
                            "Bahan segar, rasa autentik, kepuasan pelanggan terjamin"
                        </p>
                    </div>
                    
                    <div style="text-align: center; margin-top: 40px;">
                        <button class="quick-order" style="position: static; display: inline-flex; background: var(--whatsapp); color: white; border: none;" id="partnershipOrderBtn">
                            <i class="fab fa-whatsapp"></i> Pesan Martabak Mesir Sekarang
                        </button>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">
                    <h3><i class="fas fa-home"></i> Pondok Martabak</h3>
                    <p>Martabak Mesir spesial dengan resep rahasia keluarga. Setiap gigitan adalah kenikmatan yang tak terlupakan.</p>
                    
                    <div style="margin-top: 20px;">
                        <a href="https://wa.me/6285272955232" class="whatsapp-direct-btn" target="_blank" style="background: var(--whatsapp); color: white; text-decoration: none; padding: 12px 25px; border-radius: 8px; font-weight: 600; display: inline-flex; align-items: center; gap: 10px;">
                            <i class="fab fa-whatsapp"></i> Chat via WhatsApp
                        </a>
                    </div>
                    
                    <!-- Footer Social -->
                    <div class="footer-social">
                        <h4>Ikuti Kami</h4>
                        <div class="social-icons-footer">
                            <a href="https://www.instagram.com/pondok_martabak_?igsh=ZW9la2ltMmFzd3Y5&utm_source=qr" class="social-icon-footer instagram" target="_blank" title="Instagram">
                                <i class="fab fa-instagram"></i>
                            </a>
                            <a href="https://www.facebook.com/share/1AEdAD7PjW/?mibextid=wwXIfr" class="social-icon-footer facebook" target="_blank" title="Facebook">
                                <i class="fab fa-facebook-f"></i>
                            </a>
                            <a href="https://wa.me/6285272955232" class="social-icon-footer whatsapp" target="_blank" title="WhatsApp">
                                <i class="fab fa-whatsapp"></i>
                            </a>
                        </div>
                        <p style="margin-top: 15px; font-size: 0.9rem; color: #ddd;">Ikuti media sosial kami untuk update terbaru dan promo spesial!</p>
                    </div>
                </div>
                
                <div class="footer-links">
                    <h4>Menu Cepat</h4>
                    <ul>
                        <li><a href="#home"><i class="fas fa-home"></i> Beranda</a></li>
                        <li><a href="#products"><i class="fas fa-utensils"></i> Menu Spesial</a></li>
                        <li><a href="#menu"><i class="fas fa-list-alt"></i> Daftar Harga</a></li>
                        <li><a href="#contact"><i class="fas fa-phone"></i> Kontak</a></li>
                        <li><a href="#social"><i class="fas fa-share-alt"></i> Media Sosial</a></li>
                        <li><a href="#payment"><i class="fas fa-credit-card"></i> Pembayaran</a></li>
                        <li><a href="#partnership"><i class="fas fa-handshake"></i> Kerjasama</a></li>
                    </ul>
                </div>
                
                <div class="footer-contact">
                    <h4>Hubungi Kami</h4>
                    <p><i class="fas fa-map-marker-alt" style="margin-right: 12px;"></i> Desa Tanjung Botung, Provinsi Sumatera Utara</p>
                    <p><i class="fab fa-whatsapp" style="margin-right: 12px;"></i> <strong>+62 852-7295-5232</strong></p>
                    <p><i class="fas fa-user" style="margin-right: 12px;"></i> Pemilik: <strong>Imam Musthofa</strong></p>
                    <p><i class="fas fa-clock" style="margin-right: 12px;"></i> 16:00 - 23:00 WIB</p>
                    <p><i class="fas fa-calendar" style="margin-right: 12px;"></i> Buka: <strong>Senin, Selasa, Kamis, Jumat, Sabtu</strong></p>
                    <p><i class="fas fa-calendar-times" style="margin-right: 12px; color: var(--closed);"></i> Tutup: <strong style="color: var(--closed);">Rabu & Minggu</strong></p>
                    <p><i class="fas fa-map" style="margin-right: 12px;"></i> <a href="https://maps.app.goo.gl/jU9D7RvUcHhyy12a8" target="_blank" style="color: #ddd; text-decoration: none;">Lihat di Google Maps</a></p>
                    
                    <div style="margin-top: 20px;">
                        <h4 style="color: var(--accent); margin-bottom: 15px;">Media Sosial</h4>
                        <p><i class="fab fa-instagram" style="margin-right: 12px; color: var(--instagram);"></i> 
                            <a href="https://www.instagram.com/pondok_martabak_?igsh=ZW9la2ltMmFzd3Y5&utm_source=qr" target="_blank" style="color: #ddd; text-decoration: none;">
                                @pondok_martabak_
                            </a>
                        </p>
                        <p><i class="fab fa-facebook" style="margin-right: 12px; color: var(--facebook);"></i> 
                            <a href="https://www.facebook.com/share/1AEdAD7PjW/?mibextid=wwXIfr" target="_blank" style="color: #ddd; text-decoration: none;">
                                Pondok Martabak
                            </a>
                        </p>
                        <p><i class="fab fa-whatsapp" style="margin-right: 12px; color: var(--whatsapp);"></i> 
                            <a href="https://wa.me/6285272955232" target="_blank" style="color: #ddd; text-decoration: none;">
                                WhatsApp Order
                            </a>
                        </p>
                    </div>
                </div>
            </div>
            
            <div class="copyright">
                <p>© 2024 Pondok Martabak. Martabak Mesir & Masakan Terbaik.</p>
                <p>Website ini merupakan bagian dari template ujian akhir e-business - Manajemen Bisnis Digital</p>
                <p style="margin-top: 10px;"><strong>WhatsApp:</strong> +62 852-7295-5232 | <strong>Pemilik:</strong> Imam Musthofa</p>
                <p><strong>Alamat:</strong> Desa Tanjung Botung, Provinsi Sumatera Utara | <strong>Jam:</strong> 16:00 - 23:00 WIB</p>
                <p><strong>Hari Buka:</strong> Senin, Selasa, Kamis, Jumat, Sabtu | <strong style="color: var(--closed);">Tutup: Rabu & Minggu</strong></p>
                <p style="margin-top: 15px;">
                    <a href="https://www.instagram.com/pondok_martabak_?igsh=ZW9la2ltMmFzd3Y5&utm_source=qr" target="_blank" style="color: rgba(255, 255, 255, 0.7); text-decoration: none; margin-right: 15px;">
                        <i class="fab fa-instagram"></i> Instagram
                    </a>
                    <a href="https://www.facebook.com/share/1AEdAD7PjW/?mibextid=wwXIfr" target="_blank" style="color: rgba(255, 255, 255, 0.7); text-decoration: none; margin-right: 15px;">
                        <i class="fab fa-facebook"></i> Facebook
                    </a>
                    <a href="https://wa.me/6285272955232" target="_blank" style="color: rgba(255, 255, 255, 0.7); text-decoration: none;">
                        <i class="fab fa-whatsapp"></i> WhatsApp
                    </a>
                </p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Data Menu Baru dengan tempat untuk foto yang diunggah
        let menuData = [
            // Martabak Mesir
            { 
                category: "martabak", 
                name: "Martabak Mesir Daging Ayam", 
                price: 18000, 
                description: "Martabak mesir dengan isian daging ayam cincang, telur, dan bumbu rahasia",
                defaultImage: "https://images.unsplash.com/photo-1565299624946-b28f40a0ca4b?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                badge: "Best Seller",
                uploadedImages: []
            },
            { 
                category: "martabak", 
                name: "Martabak Mesir Daging Sapi", 
                price: 23000, 
                description: "Martabak mesir dengan isian daging sapi cincang premium",
                defaultImage: "https://images.unsplash.com/photo-1565958011703-44f9829ba187?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                badge: "Premium",
                uploadedImages: []
            },
            { 
                category: "martabak", 
                name: "Martabak Mesir Ayam Jumbo", 
                price: 35000, 
                description: "Martabak mesir ukuran jumbo dengan isian daging ayam ekstra banyak",
                defaultImage: "https://images.unsplash.com/photo-1565299624946-b28f40a0ca4b?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                badge: "Jumbo",
                uploadedImages: []
            },
            { 
                category: "martabak", 
                name: "Martabak Mesir Sapi Jumbo", 
                price: 45000, 
                description: "Martabak mesir ukuran jumbo dengan isian daging sapi premium ekstra banyak",
                defaultImage: "https://images.unsplash.com/photo-1565958011703-44f9829ba187?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                badge: "Premium Jumbo",
                uploadedImages: []
            },
            // Nasi Goreng
            { 
                category: "nasi", 
                name: "Nasi Goreng Spesial", 
                price: 20000, 
                description: "Nasi goreng spesial dengan daging dan bumbu rempah",
                defaultImage: "https://images.unsplash.com/photo-1631452180519-c014fe946bc7?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                badge: "Spesial",
                uploadedImages: []
            },
            // Mie & Indomie
            { 
                category: "mie", 
                name: "Indomie Kuah Spesial", 
                price: 18000, 
                description: "Indomie kuah dengan kaldu spesial dan bumbu rempah",
                defaultImage: "https://images.unsplash.com/photo-1612927601601-6638404737ce?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                badge: "Favorit",
                uploadedImages: []
            },
            { 
                category: "mie", 
                name: "Indomie Goreng Spesial", 
                price: 18000, 
                description: "Indomie goreng spesial dengan bumbu autentik",
                defaultImage: "https://images.unsplash.com/photo-1621996346565-e3dbc353d2e5?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                badge: "Favorit",
                uploadedImages: []
            },
            { 
                category: "mie", 
                name: "Mie Tiaw Spesial", 
                price: 20000, 
                description: "Mie tiaw goreng dengan daging, udang, dan sayuran segar",
                defaultImage: "https://images.unsplash.com/photo-1559054663-e8d23213f55c?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                badge: "Oriental",
                uploadedImages: []
            },
            // Roti Cane
            { 
                category: "roti", 
                name: "Roti Cane Spesial", 
                price: 15000, 
                description: "Roti cane renyah dengan kuah kari spesial yang gurih",
                defaultImage: "https://images.unsplash.com/photo-1555507036-ab794f27d2e9?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                badge: "Tradisional",
                uploadedImages: []
            }
        ];

        // WhatsApp Configuration
        const whatsappNumber = "6285272955232";
        const whatsappOwner = "Imam Musthofa";
        const businessAddress = "Desa Tanjung Botung, Provinsi Sumatera Utara";
        const operatingHours = "16:00 - 23:00 WIB";
        
        // Updated operating days - Tutup Rabu & Minggu
        const operatingDays = {
            "Senin": true,
            "Selasa": true,
            "Rabu": false,
            "Kamis": true,
            "Jumat": true,
            "Sabtu": true,
            "Minggu": false
        };

        // Shopping Cart
        let shoppingCart = [];

        // Upload Foto State
        let currentUploadIndex = null;
        let currentUploadPreview = null;
        let currentUploadFile = null;
        
        // QRIS State
        let currentQRISPreview = null;
        let currentQRISFile = null;
        
        // Admin Mode State
        let isAdminMode = false;

        // DOM Elements
        const hamburger = document.getElementById('hamburger');
        const navMenu = document.getElementById('navMenu');
        const navLinks = document.querySelectorAll('.nav-link');
        const backToTop = document.getElementById('backToTop');
        const header = document.getElementById('header');
        const menuTable = document.getElementById('menuTable');
        const productsGrid = document.getElementById('productsGrid');
        const menuCategories = document.getElementById('menuCategories');
        
        // Status Elements
        const statusHeader = document.getElementById('statusHeader');
        const statusDot = document.getElementById('statusDot');
        const statusText = document.getElementById('statusText');
        const heroStatusText = document.getElementById('heroStatusText');
        const heroStatusDetails = document.getElementById('heroStatusDetails');
        
        // Modal Elements
        const quickOrderBtn = document.getElementById('quickOrderBtn');
        const heroOrderBtn = document.getElementById('heroOrderBtn');
        const productsOrderBtn = document.getElementById('productsOrderBtn');
        const menuOrderBtn = document.getElementById('menuOrderBtn');
        const partnershipOrderBtn = document.getElementById('partnershipOrderBtn');
        const orderModal = document.getElementById('orderModal');
        const closeModal = document.getElementById('closeModal');
        const sendWhatsAppBtn = document.getElementById('sendWhatsAppBtn');
        const cartItemsModal = document.getElementById('cartItemsModal');
        const cartTotalModal = document.getElementById('cartTotalModal');
        const totalAmountModal = document.getElementById('totalAmountModal');
        
        // Upload Modal Elements
        const uploadModal = document.getElementById('uploadModal');
        const uploadProductName = document.getElementById('uploadProductName');
        const uploadPreview = document.getElementById('uploadPreview');
        const photoUpload = document.getElementById('photoUpload');
        const savePhotoBtn = document.getElementById('savePhotoBtn');
        const cancelUploadBtn = document.getElementById('cancelUploadBtn');
        const photoHistory = document.getElementById('photoHistory');
        const uploadedPhotosList = document.getElementById('uploadedPhotosList');
        
        // QRIS Elements
        const uploadQRISModal = document.getElementById('uploadQRISModal');
        const uploadQRISPreview = document.getElementById('uploadQRISPreview');
        const qrisUpload = document.getElementById('qrisUpload');
        const saveQRISBtn = document.getElementById('saveQRISBtn');
        const cancelQRISUploadBtn = document.getElementById('cancelQRISUploadBtn');
        const uploadQRISBtn = document.getElementById('uploadQRISBtn');
        const qrisImageContainer = document.getElementById('qrisImageContainer');
        const qrisPlaceholder = document.getElementById('qrisPlaceholder');
        
        // Admin Mode Elements
        const adminModeToggle = document.getElementById('adminModeToggle');

        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            loadSavedImages();
            loadSavedQRIS();
            initializeProductsGrid();
            initializeMenuTable();
            initializeEventListeners();
            updateCartDisplay();
            updateWhatsAppLinks();
            updateStatus();
            initializeCategoryFilter();
            initializeUploadModal();
            initializeQRISUploadModal();
            initializeAdminMode();
            
            if (partnershipOrderBtn) {
                partnershipOrderBtn.addEventListener('click', handleOrderButtonClick);
            }
            
            setInterval(updateStatus, 60000);
        });

        // Load saved images from localStorage
        function loadSavedImages() {
            for (let i = 0; i < menuData.length; i++) {
                const savedImages = localStorage.getItem(`product_images_${i}`);
                if (savedImages) {
                    try {
                        menuData[i].uploadedImages = JSON.parse(savedImages);
                    } catch (e) {
                        menuData[i].uploadedImages = [];
                    }
                }
            }
        }

        // Load saved QRIS from localStorage
        function loadSavedQRIS() {
            const savedQRIS = localStorage.getItem('pondok_martabak_qris');
            if (savedQRIS) {
                displayQRIS(savedQRIS);
            }
        }

        // Display QRIS image
        function displayQRIS(imageData) {
            if (qrisImageContainer && imageData) {
                qrisImageContainer.innerHTML = `
                    <img src="${imageData}" alt="QRIS Pondok Martabak" class="qris-image" id="qrisImage">
                `;
                qrisPlaceholder.style.display = 'none';
            }
        }

        // Initialize Products Grid with Filtering
        function initializeProductsGrid() {
            productsGrid.innerHTML = '';
            menuData.forEach((item, index) => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.setAttribute('data-category', item.category);
                
                const imageSource = item.uploadedImages && item.uploadedImages.length > 0 
                    ? item.uploadedImages[0] 
                    : item.defaultImage;
                
                const photoCount = item.uploadedImages ? item.uploadedImages.length : 0;
                
                productCard.innerHTML = `
                    <div class="product-img-container">
                        <img src="${imageSource}" alt="${item.name}" class="product-img" id="productImage-${index}">
                        ${item.badge ? `<span class="product-badge">${item.badge}</span>` : ''}
                        ${photoCount > 0 ? `<div class="photo-count">${photoCount} foto</div>` : ''}
                        <button class="upload-photo-btn admin-only" data-index="${index}">
                            <i class="fas fa-camera"></i> Ganti Foto
                        </button>
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">${item.name}</h3>
                        <div class="product-price">Rp ${item.price.toLocaleString()}</div>
                        <p>${item.description}</p>
                        
                        ${photoCount > 1 ? `
                            <div class="photo-gallery" id="gallery-${index}">
                                ${item.uploadedImages.map((img, imgIndex) => `
                                    <img src="${img}" alt="Foto ${imgIndex + 1}" class="gallery-thumbnail ${imgIndex === 0 ? 'active' : ''}" 
                                         data-index="${imgIndex}" data-product="${index}">
                                `).join('')}
                            </div>
                        ` : ''}
                        
                        <button class="order-btn-modal" data-index="${index}" 
                                style="background: var(--primary); color: white; border: none; padding: 12px 25px; border-radius: 8px; font-weight: 600; cursor: pointer; transition: var(--transition); width: 100%; margin-top: 15px;">
                            <i class="fas fa-cart-plus"></i> Tambah ke Keranjang
                        </button>
                    </div>
                `;
                
                productsGrid.appendChild(productCard);
            });
            
            addGalleryEventListeners();
        }

        // Add event listeners for gallery thumbnails
        function addGalleryEventListeners() {
            document.querySelectorAll('.gallery-thumbnail').forEach(thumbnail => {
                thumbnail.addEventListener('click', function() {
                    const productIndex = this.dataset.product;
                    const imgIndex = this.dataset.index;
                    
                    const mainImage = document.getElementById(`productImage-${productIndex}`);
                    if (mainImage) {
                        mainImage.src = this.src;
                    }
                    
                    document.querySelectorAll(`#gallery-${productIndex} .gallery-thumbnail`).forEach(thumb => {
                        thumb.classList.remove('active');
                    });
                    this.classList.add('active');
                });
            });
        }

        // Initialize Menu Table
        function initializeMenuTable() {
            menuTable.innerHTML = '';
            
            const categories = {};
            menuData.forEach(item => {
                if (!categories[item.category]) {
                    categories[item.category] = [];
                }
                categories[item.category].push(item);
            });
            
            Object.keys(categories).forEach(categoryName => {
                const categoryItems = categories[categoryName];
                
                const categoryHeader = document.createElement('tr');
                categoryHeader.style.background = 'var(--light)';
                categoryHeader.innerHTML = `
                    <td colspan="3" style="padding: 15px 20px; font-weight: bold; color: var(--secondary); font-size: 1.2rem;">
                        ${getCategoryLabel(categoryName)}
                    </td>
                `;
                menuTable.appendChild(categoryHeader);
                
                categoryItems.forEach((item, index) => {
                    const originalIndex = menuData.findIndex(m => m.name === item.name);
                    const row = document.createElement('tr');
                    row.style.borderBottom = '1px solid var(--light)';
                    row.innerHTML = `
                        <td style="padding: 18px;">
                            <strong>${item.name}</strong>
                            <p style="color: #666; font-size: 0.9rem; margin-top: 5px;">${item.description}</p>
                        </td>
                        <td style="padding: 18px; font-weight: bold; color: var(--primary);">Rp ${item.price.toLocaleString()}</td>
                        <td style="padding: 18px; text-align: center;">
                            <button class="order-btn-modal" data-index="${originalIndex}" 
                                    style="background: var(--primary); color: white; border: none; padding: 10px 20px; 
                                           border-radius: 8px; cursor: pointer; transition: var(--transition); font-weight: 600;">
                                <i class="fas fa-cart-plus"></i> Tambah
                            </button>
                        </td>
                    `;
                    menuTable.appendChild(row);
                });
            });
        }

        // Get category label
        function getCategoryLabel(category) {
            const labels = {
                'martabak': '🍽️ Martabak Mesir',
                'nasi': '🍚 Nasi Goreng',
                'mie': '🍜 Mie & Indomie',
                'roti': '🥖 Roti Cane'
            };
            return labels[category] || category;
        }

        // Initialize Upload Modal
        function initializeUploadModal() {
            photoUpload.addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    if (file.size > 5 * 1024 * 1024) {
                        showNotification('File terlalu besar! Maksimum 5MB.', 'error');
                        photoUpload.value = '';
                        return;
                    }
                    
                    if (!file.type.match('image.*')) {
                        showNotification('Hanya file gambar yang diperbolehkan!', 'error');
                        photoUpload.value = '';
                        return;
                    }
                    
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        uploadPreview.innerHTML = `<img src="${e.target.result}" alt="Preview">`;
                        currentUploadPreview = e.target.result;
                        currentUploadFile = file;
                    };
                    reader.readAsDataURL(file);
                }
            });
            
            savePhotoBtn.addEventListener('click', async function() {
                if (currentUploadIndex === null || !currentUploadPreview || !currentUploadFile) {
                    showNotification('Pilih foto terlebih dahulu!', 'error');
                    return;
                }
                
                try {
                    const imageData = currentUploadPreview;
                    
                    if (!menuData[currentUploadIndex].uploadedImages) {
                        menuData[currentUploadIndex].uploadedImages = [];
                    }
                    menuData[currentUploadIndex].uploadedImages.unshift(imageData);
                    
                    localStorage.setItem(`product_images_${currentUploadIndex}`, 
                        JSON.stringify(menuData[currentUploadIndex].uploadedImages));
                    
                    updateProductImage(currentUploadIndex);
                    updateProductGallery(currentUploadIndex);
                    showUploadedPhotos(currentUploadIndex);
                    
                    showNotification('Foto produk berhasil disimpan! Akan terlihat oleh semua pengunjung.', 'success');
                    
                } catch (error) {
                    showNotification('Gagal menyimpan foto. Coba lagi.', 'error');
                }
            });
            
            cancelUploadBtn.addEventListener('click', closeUploadModal);
            
            uploadModal.addEventListener('click', function(e) {
                if (e.target === uploadModal) {
                    closeUploadModal();
                }
            });
        }

        // Initialize QRIS Upload Modal
        function initializeQRISUploadModal() {
            qrisUpload.addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    if (file.size > 5 * 1024 * 1024) {
                        showNotification('File terlalu besar! Maksimum 5MB.', 'error');
                        qrisUpload.value = '';
                        return;
                    }
                    
                    if (!file.type.match('image.*')) {
                        showNotification('Hanya file gambar yang diperbolehkan!', 'error');
                        qrisUpload.value = '';
                        return;
                    }
                    
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        uploadQRISPreview.innerHTML = `<img src="${e.target.result}" alt="Preview QRIS">`;
                        currentQRISPreview = e.target.result;
                        currentQRISFile = file;
                    };
                    reader.readAsDataURL(file);
                }
            });
            
            saveQRISBtn.addEventListener('click', function() {
                if (!currentQRISPreview || !currentQRISFile) {
                    showNotification('Pilih foto QRIS terlebih dahulu!', 'error');
                    return;
                }
                
                try {
                    localStorage.setItem('pondok_martabak_qris', currentQRISPreview);
                    displayQRIS(currentQRISPreview);
                    showNotification('QRIS berhasil disimpan! Akan terlihat oleh semua pengunjung.', 'success');
                    closeQRISUploadModal();
                    
                } catch (error) {
                    showNotification('Gagal menyimpan QRIS. Coba lagi.', 'error');
                }
            });
            
            cancelQRISUploadBtn.addEventListener('click', closeQRISUploadModal);
            
            uploadQRISModal.addEventListener('click', function(e) {
                if (e.target === uploadQRISModal) {
                    closeQRISUploadModal();
                }
            });
            
            uploadQRISBtn.addEventListener('click', openQRISUploadModal);
        }

        // Open QRIS Upload Modal
        function openQRISUploadModal() {
            currentQRISPreview = null;
            currentQRISFile = null;
            
            uploadQRISPreview.innerHTML = '<p style="color: #999;">Pratinjau QRIS akan muncul di sini</p>';
            qrisUpload.value = '';
            
            uploadQRISModal.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        // Close QRIS Upload Modal
        function closeQRISUploadModal() {
            uploadQRISModal.classList.remove('active');
            document.body.style.overflow = '';
            currentQRISPreview = null;
            currentQRISFile = null;
            qrisUpload.value = '';
        }

        // Update product image after upload
        function updateProductImage(index) {
            const product = menuData[index];
            const imageSource = product.uploadedImages && product.uploadedImages.length > 0 
                ? product.uploadedImages[0] 
                : product.defaultImage;
            
            const productImage = document.getElementById(`productImage-${index}`);
            if (productImage) {
                productImage.src = imageSource;
            }
            
            const imgContainer = productImage ? productImage.parentElement : null;
            if (imgContainer) {
                let photoCountElement = imgContainer.querySelector('.photo-count');
                const photoCount = product.uploadedImages ? product.uploadedImages.length : 0;
                
                if (photoCount > 0) {
                    if (!photoCountElement) {
                        photoCountElement = document.createElement('div');
                        photoCountElement.className = 'photo-count';
                        imgContainer.appendChild(photoCountElement);
                    }
                    photoCountElement.textContent = `${photoCount} foto`;
                } else if (photoCountElement) {
                    photoCountElement.remove();
                }
            }
        }

        // Update product gallery after upload
        function updateProductGallery(index) {
            const product = menuData[index];
            const photoCount = product.uploadedImages ? product.uploadedImages.length : 0;
            
            if (photoCount > 1) {
                const productCard = document.querySelector(`.product-card[data-index="${index}"]`) || 
                                   document.querySelector(`#productImage-${index}`)?.closest('.product-card');
                
                if (productCard) {
                    let gallery = productCard.querySelector(`#gallery-${index}`);
                    const productInfo = productCard.querySelector('.product-info');
                    
                    if (!gallery) {
                        gallery = document.createElement('div');
                        gallery.className = 'photo-gallery';
                        gallery.id = `gallery-${index}`;
                        
                        const orderBtn = productInfo.querySelector('.order-btn-modal');
                        if (orderBtn) {
                            orderBtn.parentNode.insertBefore(gallery, orderBtn);
                        }
                    }
                    
                    gallery.innerHTML = product.uploadedImages.map((img, imgIndex) => `
                        <img src="${img}" alt="Foto ${imgIndex + 1}" class="gallery-thumbnail ${imgIndex === 0 ? 'active' : ''}" 
                             data-index="${imgIndex}" data-product="${index}">
                    `).join('');
                    
                    addGalleryEventListeners();
                }
            } else {
                const gallery = document.getElementById(`gallery-${index}`);
                if (gallery) {
                    gallery.remove();
                }
            }
        }

        // Show uploaded photos in modal
        function showUploadedPhotos(index) {
            const product = menuData[index];
            const photos = product.uploadedImages || [];
            
            if (photos.length > 0) {
                uploadedPhotosList.innerHTML = photos.map((img, imgIndex) => `
                    <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 10px; padding: 10px; background: #f9f9f9; border-radius: 8px;">
                        <img src="${img}" style="width: 60px; height: 60px; object-fit: cover; border-radius: 5px;">
                        <div style="flex: 1;">
                            <p style="font-size: 0.9rem; margin-bottom: 5px;">Foto ${imgIndex + 1}</p>
                            <div style="display: flex; gap: 5px;">
                                <button class="set-as-main-btn" data-index="${index}" data-img-index="${imgIndex}" 
                                        style="background: var(--primary); color: white; border: none; padding: 5px 10px; border-radius: 3px; font-size: 0.8rem; cursor: pointer;">
                                    <i class="fas fa-star"></i> Jadikan Utama
                                </button>
                                <button class="delete-photo-btn" data-index="${index}" data-img-index="${imgIndex}" 
                                        style="background: var(--danger); color: white; border: none; padding: 5px 10px; border-radius: 3px; font-size: 0.8rem; cursor: pointer;">
                                    <i class="fas fa-trash"></i> Hapus
                                </button>
                            </div>
                        </div>
                    </div>
                `).join('');
                
                photoHistory.style.display = 'block';
                
                document.querySelectorAll('.set-as-main-btn').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const productIndex = this.dataset.index;
                        const imgIndex = this.dataset.imgIndex;
                        setAsMainImage(productIndex, imgIndex);
                    });
                });
                
                document.querySelectorAll('.delete-photo-btn').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const productIndex = this.dataset.index;
                        const imgIndex = this.dataset.imgIndex;
                        deletePhoto(productIndex, imgIndex);
                    });
                });
            } else {
                photoHistory.style.display = 'none';
            }
        }

        // Set image as main
        function setAsMainImage(productIndex, imgIndex) {
            const product = menuData[productIndex];
            if (product.uploadedImages && product.uploadedImages[imgIndex]) {
                const image = product.uploadedImages.splice(imgIndex, 1)[0];
                product.uploadedImages.unshift(image);
                
                localStorage.setItem(`product_images_${productIndex}`, 
                    JSON.stringify(product.uploadedImages));
                
                updateProductImage(productIndex);
                updateProductGallery(productIndex);
                showUploadedPhotos(productIndex);
                
                showNotification('Foto utama berhasil diubah!', 'success');
            }
        }

        // Delete photo
        function deletePhoto(productIndex, imgIndex) {
            if (confirm('Apakah Anda yakin ingin menghapus foto ini?')) {
                const product = menuData[productIndex];
                if (product.uploadedImages && product.uploadedImages[imgIndex]) {
                    product.uploadedImages.splice(imgIndex, 1);
                    
                    localStorage.setItem(`product_images_${productIndex}`, 
                        JSON.stringify(product.uploadedImages));
                    
                    updateProductImage(productIndex);
                    updateProductGallery(productIndex);
                    showUploadedPhotos(productIndex);
                    
                    showNotification('Foto berhasil dihapus!', 'success');
                }
            }
        }

        // Open Upload Modal
        function openUploadModal(index) {
            currentUploadIndex = index;
            currentUploadPreview = null;
            currentUploadFile = null;
            
            uploadProductName.textContent = menuData[index].name;
            uploadPreview.innerHTML = '<p style="color: #999;">Pratinjau gambar akan muncul di sini</p>';
            photoUpload.value = '';
            
            showUploadedPhotos(index);
            
            uploadModal.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        // Close Upload Modal
        function closeUploadModal() {
            uploadModal.classList.remove('active');
            document.body.style.overflow = '';
            currentUploadIndex = null;
            currentUploadPreview = null;
            currentUploadFile = null;
            photoUpload.value = '';
            photoHistory.style.display = 'none';
        }

        // Initialize Admin Mode
        function initializeAdminMode() {
            if (localStorage.getItem('pondokMartabakAdminMode') === 'true') {
                toggleAdminMode(true);
            }
            
            adminModeToggle.addEventListener('click', function() {
                toggleAdminMode(!isAdminMode);
            });
            
            document.addEventListener('keydown', function(e) {
                if (e.ctrlKey && e.shiftKey && e.key === 'A') {
                    e.preventDefault();
                    toggleAdminMode(!isAdminMode);
                }
            });
        }

        // Toggle Admin Mode
        function toggleAdminMode(enable) {
            isAdminMode = enable;
            
            if (isAdminMode) {
                document.body.classList.add('admin-mode');
                adminModeToggle.classList.add('active');
                adminModeToggle.innerHTML = '<i class="fas fa-user-shield"></i><span>Mode Admin Aktif</span>';
                showNotification('Mode admin diaktifkan. Anda sekarang dapat mengupload foto produk dan QRIS.', 'success');
                localStorage.setItem('pondokMartabakAdminMode', 'true');
            } else {
                document.body.classList.remove('admin-mode');
                adminModeToggle.classList.remove('active');
                adminModeToggle.innerHTML = '<i class="fas fa-user-shield"></i><span>Mode Admin</span>';
                localStorage.setItem('pondokMartabakAdminMode', 'false');
            }
        }

        // Update Status Buka/Tutup
        function updateStatus() {
            const now = new Date();
            const currentHour = now.getHours();
            const currentMinute = now.getMinutes();
            const currentDay = getDayName(now.getDay());
            const currentTime = currentHour + currentMinute/60;
            
            const openingTime = 16.0;
            const closingTime = 23.0;
            
            const isOpenToday = operatingDays[currentDay];
            const isWithinHours = currentTime >= openingTime && currentTime <= closingTime;
            const isOpen = isOpenToday && isWithinHours;
            
            if (isOpen) {
                statusDot.className = 'status-dot open';
                statusText.className = 'status-text status-open';
                statusText.textContent = 'BUKA SEKARANG';
                
                heroStatusText.innerHTML = '<span class="status-open">🟢 BUKA SEKARANG</span>';
                heroStatusDetails.innerHTML = `Buka sampai 23:00 WIB | Hari ini: ${currentDay}`;
                
                enableOrderButtons(true);
            } else {
                statusDot.className = 'status-dot closed';
                statusText.className = 'status-text status-closed';
                statusText.textContent = 'TUTUP';
                
                heroStatusText.innerHTML = '<span class="status-closed">🔴 TUTUP</span>';
                
                let reason = '';
                if (!isOpenToday) {
                    reason = `Tutup hari ${currentDay}`;
                } else if (currentTime < openingTime) {
                    const hoursUntilOpen = Math.ceil(openingTime - currentTime);
                    reason = `Buka pukul 16:00 WIB (${hoursUntilOpen} jam lagi)`;
                } else {
                    reason = 'Buka besok pukul 16:00 WIB';
                }
                
                heroStatusDetails.innerHTML = `${reason} | Hari ini: ${currentDay}`;
                
                enableOrderButtons(false);
            }
            
            updateTitleWithStatus(isOpen);
        }

        // Get Day Name in Indonesian
        function getDayName(dayIndex) {
            const days = ["Minggu", "Senin", "Selasa", "Rabu", "Kamis", "Jumat", "Sabtu"];
            return days[dayIndex];
        }

        // Enable/Disable Order Buttons based on status
        function enableOrderButtons(enabled) {
            const orderButtons = [
                quickOrderBtn,
                heroOrderBtn,
                productsOrderBtn,
                menuOrderBtn,
                partnershipOrderBtn,
                sendWhatsAppBtn
            ];
            
            orderButtons.forEach(button => {
                if (button) {
                    button.disabled = !enabled;
                    button.style.opacity = enabled ? '1' : '0.7';
                    button.style.cursor = enabled ? 'pointer' : 'not-allowed';
                    
                    if (!enabled) {
                        button.title = "Pondok Martabak sedang tutup. Pesanan hanya dapat dilakukan pada jam operasional.";
                    } else {
                        button.title = "";
                    }
                }
            });
        }

        // Update browser title with status
        function updateTitleWithStatus(isOpen) {
            const statusEmoji = isOpen ? "🟢" : "🔴";
            const statusText = isOpen ? "BUKA" : "TUTUP";
            document.title = `${statusEmoji} Pondok Martabak | ${statusText} - Martabak Mesir & Masakan Terbaik`;
        }

        // Initialize Category Filter
        function initializeCategoryFilter() {
            const categoryBtns = menuCategories.querySelectorAll('.category-btn');
            
            categoryBtns.forEach(btn => {
                btn.addEventListener('click', function() {
                    categoryBtns.forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    
                    const category = this.getAttribute('data-category');
                    filterProducts(category);
                });
            });
        }

        // Filter Products by Category
        function filterProducts(category) {
            const productCards = productsGrid.querySelectorAll('.product-card');
            
            productCards.forEach(card => {
                if (category === 'all' || card.getAttribute('data-category') === category) {
                    card.style.display = 'block';
                    setTimeout(() => {
                        card.style.opacity = '1';
                        card.style.transform = 'translateY(0)';
                    }, 100);
                } else {
                    card.style.opacity = '0';
                    card.style.transform = 'translateY(20px)';
                    setTimeout(() => {
                        card.style.display = 'none';
                    }, 300);
                }
            });
        }

        // Initialize Event Listeners
        function initializeEventListeners() {
            hamburger.addEventListener('click', toggleMobileMenu);
            
            navLinks.forEach(link => {
                link.addEventListener('click', handleNavClick);
            });
            
            backToTop.addEventListener('click', scrollToTop);
            
            window.addEventListener('scroll', handleScroll);
            
            quickOrderBtn.addEventListener('click', handleOrderButtonClick);
            heroOrderBtn.addEventListener('click', handleOrderButtonClick);
            productsOrderBtn.addEventListener('click', handleOrderButtonClick);
            menuOrderBtn.addEventListener('click', handleOrderButtonClick);
            
            closeModal.addEventListener('click', closeOrderModal);
            orderModal.addEventListener('click', function(e) {
                if (e.target === orderModal) {
                    closeOrderModal();
                }
            });
            
            document.addEventListener('click', function(e) {
                if (e.target.closest('.upload-photo-btn') && isAdminMode) {
                    const index = e.target.closest('.upload-photo-btn').dataset.index;
                    openUploadModal(parseInt(index));
                }
            });
            
            document.addEventListener('click', function(e) {
                if (e.target.closest('.order-btn-modal')) {
                    const index = e.target.closest('.order-btn-modal').dataset.index;
                    addToCart(index);
                }
            });
            
            document.addEventListener('click', function(e) {
                if (e.target.closest('.remove-item-modal')) {
                    const index = e.target.closest('.remove-item-modal').dataset.index;
                    removeFromCart(index);
                }
            });
            
            sendWhatsAppBtn.addEventListener('click', sendWhatsAppOrder);
            
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape') {
                    if (orderModal.classList.contains('active')) {
                        closeOrderModal();
                    }
                    if (uploadModal.classList.contains('active')) {
                        closeUploadModal();
                    }
                    if (uploadQRISModal.classList.contains('active')) {
                        closeQRISUploadModal();
                    }
                }
            });
            
            updateWhatsAppLinks();
        }

        // Handle Order Button Click with Status Check
        function handleOrderButtonClick() {
            const now = new Date();
            const currentHour = now.getHours();
            const currentMinute = now.getMinutes();
            const currentDay = getDayName(now.getDay());
            const currentTime = currentHour + currentMinute/60;
            
            const openingTime = 16.0;
            const closingTime = 23.0;
            const isOpenToday = operatingDays[currentDay];
            const isWithinHours = currentTime >= openingTime && currentTime <= closingTime;
            const isOpen = isOpenToday && isWithinHours;
            
            if (!isOpen) {
                let message = '';
                if (!isOpenToday) {
                    message = `Maaf, Pondok Martabak tutup hari ${currentDay}. Kami buka Senin, Selasa, Kamis, Jumat, dan Sabtu pukul 16:00 - 23:00 WIB.`;
                } else if (currentTime < openingTime) {
                    message = `Maaf, Pondok Martabak baru buka pukul 16:00 WIB. Silakan pesan nanti.`;
                } else {
                    message = `Maaf, Pondok Martabak sudah tutup. Kami buka kembali besok pukul 16:00 WIB.`;
                }
                
                showNotification(message, 'error');
                return;
            }
            
            openOrderModal();
        }

        // Update all WhatsApp links with correct number
        function updateWhatsAppLinks() {
            document.querySelectorAll('.whatsapp-direct-btn').forEach(btn => {
                if (!btn.getAttribute('href').includes(whatsappNumber)) {
                    btn.setAttribute('href', `https://wa.me/${whatsappNumber}`);
                }
            });
        }

        // Mobile Menu Toggle
        function toggleMobileMenu() {
            navMenu.classList.toggle('active');
            const icon = hamburger.querySelector('i');
            icon.classList.toggle('fa-bars');
            icon.classList.toggle('fa-times');
            
            if (navMenu.classList.contains('active')) {
                document.body.style.overflow = 'hidden';
            } else {
                document.body.style.overflow = '';
            }
        }

        // Handle Navigation Click
        function handleNavClick(e) {
            e.preventDefault();
            const targetId = this.getAttribute('href').substring(1);
            const targetElement = document.getElementById(targetId);
            
            if (targetElement) {
                if (navMenu.classList.contains('active')) {
                    toggleMobileMenu();
                }
                
                navLinks.forEach(link => link.classList.remove('active'));
                this.classList.add('active');
                
                window.scrollTo({
                    top: targetElement.offsetTop - 100,
                    behavior: 'smooth'
                });
            }
        }

        // Handle Scroll
        function handleScroll() {
            if (window.scrollY > 100) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
            
            if (window.scrollY > 500) {
                backToTop.classList.add('visible');
            } else {
                backToTop.classList.remove('visible');
            }
            
            updateActiveNavLink();
        }

        // Update Active Nav Link
        function updateActiveNavLink() {
            let current = '';
            const sections = document.querySelectorAll('section[id]');
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (window.scrollY >= (sectionTop - 150)) {
                    current = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === current) {
                    link.classList.add('active');
                }
            });
        }

        // Scroll to Top
        function scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }

        // Open Order Modal
        function openOrderModal() {
            orderModal.classList.add('active');
            document.body.style.overflow = 'hidden';
            updateCartDisplay();
            
            setTimeout(() => {
                document.getElementById('modalCustomerName').focus();
            }, 300);
        }

        // Close Order Modal
        function closeOrderModal() {
            orderModal.classList.remove('active');
            document.body.style.overflow = '';
        }

        // Add to Cart by Index
        function addToCart(index) {
            const now = new Date();
            const currentHour = now.getHours();
            const currentMinute = now.getMinutes();
            const currentDay = getDayName(now.getDay());
            const currentTime = currentHour + currentMinute/60;
            
            const openingTime = 16.0;
            const closingTime = 23.0;
            const isOpenToday = operatingDays[currentDay];
            const isWithinHours = currentTime >= openingTime && currentTime <= closingTime;
            const isOpen = isOpenToday && isWithinHours;
            
            if (!isOpen) {
                showNotification('Maaf, Pondok Martabak sedang tutup. Pesanan hanya dapat dilakukan pada jam operasional.', 'error');
                return;
            }
            
            const item = menuData[index];
            shoppingCart.push({
                name: item.name,
                price: item.price,
                quantity: 1,
                description: item.description
            });
            
            showNotification(`${item.name} ditambahkan ke keranjang!`);
            updateCartDisplay();
            
            if (!orderModal.classList.contains('active')) {
                openOrderModal();
            }
        }

        // Remove from Cart
        function removeFromCart(index) {
            const removedItem = shoppingCart[index];
            shoppingCart.splice(index, 1);
            updateCartDisplay();
            showNotification(`${removedItem.name} dihapus dari keranjang!`, 'info');
        }

        // Update Cart Display in Modal
        function updateCartDisplay() {
            cartItemsModal.innerHTML = '';
            
            if (shoppingCart.length === 0) {
                cartItemsModal.innerHTML = '<p style="text-align: center; color: #999; padding: 20px;">Belum ada item dalam keranjang</p>';
                cartTotalModal.style.display = 'none';
                return;
            }
            
            let total = 0;
            
            shoppingCart.forEach((item, index) => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                
                const cartItem = document.createElement('div');
                cartItem.style.padding = '15px';
                cartItem.style.marginBottom = '10px';
                cartItem.style.background = 'var(--light)';
                cartItem.style.borderRadius = '10px';
                cartItem.style.boxShadow = '0 3px 10px rgba(0,0,0,0.05)';
                
                cartItem.innerHTML = `
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px;">
                        <div>
                            <strong style="color: var(--secondary);">${item.name}</strong>
                            <p style="color: #666; font-size: 0.9rem; margin-top: 5px;">${item.description}</p>
                        </div>
                        <button class="remove-item-modal" data-index="${index}" 
                                style="background: var(--danger); color: white; border: none; padding: 5px 10px; 
                                       border-radius: 5px; cursor: pointer; font-size: 0.9rem;">
                            <i class="fas fa-trash"></i>
                        </button>
                    </div>
                    <div style="display: flex; justify-content: space-between; align-items: center;">
                        <div>
                            <span style="color: var(--primary); font-weight: bold;">Rp ${item.price.toLocaleString()} x ${item.quantity}</span>
                        </div>
                        <div>
                            <strong style="color: var(--secondary);">Rp ${itemTotal.toLocaleString()}</strong>
                        </div>
                    </div>
                `;
                
                cartItemsModal.appendChild(cartItem);
            });
            
            totalAmountModal.textContent = `Rp ${total.toLocaleString()}`;
            cartTotalModal.style.display = 'block';
        }

        // Send WhatsApp Order
        function sendWhatsAppOrder() {
            const now = new Date();
            const currentHour = now.getHours();
            const currentMinute = now.getMinutes();
            const currentDay = getDayName(now.getDay());
            const currentTime = currentHour + currentMinute/60;
            
            const openingTime = 16.0;
            const closingTime = 23.0;
            const isOpenToday = operatingDays[currentDay];
            const isWithinHours = currentTime >= openingTime && currentTime <= closingTime;
            const isOpen = isOpenToday && isWithinHours;
            
            if (!isOpen) {
                let message = '';
                if (!isOpenToday) {
                    message = `Maaf, Pondok Martabak tutup hari ${currentDay}. Pesanan hanya dapat dilakukan pada hari Senin, Selasa, Kamis, Jumat, dan Sabtu pukul 16:00 - 23:00 WIB.`;
                } else if (currentTime < openingTime) {
                    message = `Maaf, Pondok Martabak baru buka pukul 16:00 WIB. Silakan pesan nanti.`;
                } else {
                    message = `Maaf, Pondok Martabak sudah tutup. Kami buka kembali besok pukul 16:00 WIB.`;
                }
                
                showNotification(message, 'error');
                return;
            }
            
            if (shoppingCart.length === 0) {
                showNotification('Keranjang Anda kosong! Tambahkan produk terlebih dahulu.', 'error');
                return;
            }
            
            const name = document.getElementById('modalCustomerName').value.trim();
            const phone = document.getElementById('modalCustomerPhone').value.trim();
            const address = document.getElementById('modalCustomerAddress').value.trim();
            const notes = document.getElementById('modalOrderNotes').value.trim();
            
            if (!name) {
                showNotification('Silakan isi nama lengkap Anda!', 'error');
                document.getElementById('modalCustomerName').focus();
                return;
            }
            
            if (!phone) {
                showNotification('Silakan isi nomor WhatsApp Anda!', 'error');
                document.getElementById('modalCustomerPhone').focus();
                return;
            }
            
            const cleanPhone = phone.replace(/[^0-9]/g, '');
            let formattedPhone = cleanPhone;
            if (formattedPhone.startsWith('0')) {
                formattedPhone = '62' + formattedPhone.substring(1);
            } else if (!formattedPhone.startsWith('62')) {
                formattedPhone = '62' + formattedPhone;
            }
            
            let message = `*PESANAN PONDOK MARTABAK*%0A%0A`;
            message += `*Nama Pemesan:* ${name}%0A`;
            message += `*No. WhatsApp:* ${phone}%0A`;
            message += `*Alamat Pengiriman:* ${address || 'Ambil di tempat (' + businessAddress + ')'}%0A`;
            message += `*Catatan:* ${notes || 'Tidak ada catatan'}%0A%0A`;
            message += `*DETAIL PESANAN:*%0A`;
            message += `════════════════════════%0A`;
            
            let total = 0;
            shoppingCart.forEach((item, index) => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                message += `*${index + 1}. ${item.name}*%0A`;
                message += `   ${item.description}%0A`;
                message += `   Harga: Rp ${item.price.toLocaleString()} x ${item.quantity}%0A`;
                message += `   Subtotal: Rp ${itemTotal.toLocaleString()}%0A%0A`;
            });
            
            message += `════════════════════════%0A`;
            message += `*TOTAL PEMBAYARAN:* Rp ${total.toLocaleString()}%0A%0A`;
            message += `*METODE PEMBAYARAN:*%0A`;
            message += `• Tunai (COD)%0A`;
            message += `• Transfer Bank (BCA, Mandiri, BRI)%0A`;
            message += `• E-Wallet (GoPay, OVO, Dana)%0A`;
            message += `• QRIS (Tersedia di website)%0A%0A`;
            message += `*FOLLOW MEDIA SOSIAL KAMI:*%0A`;
            message += `📸 Instagram: @pondok_martabak_%0A`;
            message += `👍 Facebook: Pondok Martabak%0A`;
            message += `*INFORMASI TOKO:*%0A`;
            message += `🏠 Pondok Martabak%0A`;
            message += `📍 ${businessAddress}%0A`;
            message += `📱 +62 852-7295-5232 (${whatsappOwner})%0A`;
            message += `⏰ ${operatingHours}%0A`;
            message += `📅 BUKA: Senin, Selasa, Kamis, Jumat, Sabtu%0A`;
            message += `📅 TUTUP: Rabu & Minggu%0A%0A`;
            message += `_Pesanan ini dikirim otomatis via website Pondok Martabak_`;
            
            const whatsappUrl = `https://wa.me/${whatsappNumber}?text=${message}`;
            
            window.open(whatsappUrl, '_blank');
            
            showNotification('Pesanan berhasil dikirim ke WhatsApp!', 'success');
            
            setTimeout(() => {
                shoppingCart = [];
                updateCartDisplay();
                closeOrderModal();
                document.getElementById('modalCustomerName').value = '';
                document.getElementById('modalCustomerPhone').value = '';
                document.getElementById('modalCustomerAddress').value = '';
                document.getElementById('modalOrderNotes').value = '';
            }, 2000);
        }

        // Show Notification
        function showNotification(message, type = 'success') {
            const existingNotification = document.querySelector('.notification');
            if (existingNotification) {
                existingNotification.remove();
            }
            
            const notification = document.createElement('div');
            notification.className = `notification ${type}`;
            notification.style.position = 'fixed';
            notification.style.top = '20px';
            notification.style.right = '20px';
            notification.style.padding = '15px 25px';
            notification.style.borderRadius = '10px';
            notification.style.color = 'white';
            notification.style.fontWeight = '600';
            notification.style.zIndex = '10000';
            notification.style.boxShadow = '0 5px 15px rgba(0,0,0,0.2)';
            notification.style.animation = 'slideIn 0.3s ease';
            notification.style.display = 'flex';
            notification.style.alignItems = 'center';
            notification.style.gap = '10px';
            
            if (type === 'success') {
                notification.style.background = 'var(--success)';
            } else if (type === 'error') {
                notification.style.background = 'var(--danger)';
            } else if (type === 'info') {
                notification.style.background = 'var(--secondary)';
            } else {
                notification.style.background = 'var(--primary)';
            }
            
            notification.innerHTML = `
                <i class="fas fa-${type === 'success' ? 'check-circle' : type === 'error' ? 'exclamation-circle' : 'info-circle'}"></i>
                ${message}
            `;
            
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.style.animation = 'slideOut 0.3s ease';
                setTimeout(() => {
                    if (notification.parentNode) {
                        notification.parentNode.removeChild(notification);
                    }
                }, 300);
            }, 3000);
        }

        // Add CSS for notifications and gallery
        const style = document.createElement('style');
        style.textContent = `
            .order-btn-modal, .cta-button {
                background: var(--primary);
                color: white;
                border: none;
                padding: 12px 25px;
                border-radius: 8px;
                font-weight: 600;
                cursor: pointer;
                transition: var(--transition);
                display: inline-block;
                margin-top: 10px;
                text-decoration: none;
                width: 100%;
            }
            
            .order-btn-modal:hover, .cta-button:hover {
                background: var(--secondary);
                transform: translateY(-3px);
                box-shadow: 0 5px 15px rgba(255, 107, 53, 0.3);
            }
            
            .order-btn-modal:disabled, .cta-button:disabled {
                background: #ccc !important;
                cursor: not-allowed !important;
                transform: none !important;
                box-shadow: none !important;
            }
            
            .whatsapp-direct-btn:hover, .maps-btn:hover {
                transform: translateY(-3px);
                box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            }
            
            button:active:not(:disabled) {
                transform: scale(0.98);
            }
            
            input:focus, textarea:focus {
                outline: none;
                border-color: var(--primary) !important;
                box-shadow: 0 0 0 3px rgba(255, 107, 53, 0.1);
            }
            
            #sendWhatsAppBtn:hover:not(:disabled) {
                background: #128C7E !important;
                transform: translateY(-3px);
                box-shadow: 0 5px 15px rgba(37, 211, 102, 0.4);
            }
            
            .product-card {
                opacity: 1;
                transform: translateY(0);
                transition: opacity 0.3s ease, transform 0.3s ease;
            }
            
            @keyframes slideOut {
                from {
                    transform: translateX(0);
                    opacity: 1;
                }
                to {
                    transform: translateX(100%);
                    opacity: 0;
                }
            }
            
            /* Contact Grid Styles */
            .contact-grid {
                display: grid;
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
                gap: 30px;
                margin-top: 30px;
            }
            
            .contact-card {
                background: var(--light);
                padding: 25px;
                border-radius: 15px;
                text-align: center;
                transition: var(--transition);
            }
            
            .contact-card:hover {
                transform: translateY(-5px);
                box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            }
            
            /* Payment Methods Styles */
            .payment-methods {
                display: grid;
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
                gap: 15px;
                margin-top: 20px;
            }
            
            .payment-method {
                display: flex;
                align-items: center;
                gap: 15px;
                padding: 15px;
                background: var(--light);
                border-radius: 10px;
            }
            
            .payment-method i {
                font-size: 1.8rem;
                color: var(--primary);
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
