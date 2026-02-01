# Techdrop<!DOCTYPE html>
<!-- Write code below -->
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TechDrop - Gaming, Móvil & Tech | Dropshipping</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;500;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --neon-cyan: #00FFFF;
            --neon-pink: #FF00FF;
            --neon-yellow: #FFFF00;
            --electric-blue: #0080FF;
            --deep-purple: #1A0033;
            --dark-bg: #0D0221;
            --card-bg: #1B0F3A;
            --text-white: #FFFFFF;
            --text-gray: #B8B8D1;
        }

        body {
            font-family: 'Rajdhani', sans-serif;
            background: var(--dark-bg);
            color: var(--text-white);
            overflow-x: hidden;
        }

        /* Animated background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(0, 255, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(255, 0, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 20%, rgba(0, 128, 255, 0.1) 0%, transparent 50%);
            animation: bgPulse 10s ease-in-out infinite;
            z-index: 0;
        }

        @keyframes bgPulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        /* Grid overlay */
        .grid-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(0, 255, 255, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 255, 255, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            z-index: 1;
            pointer-events: none;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 2;
        }

        /* Navigation */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 25px 0;
            position: sticky;
            top: 0;
            background: rgba(13, 2, 33, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 2px solid rgba(0, 255, 255, 0.2);
        }

        .logo {
            font-family: 'Orbitron', sans-serif;
            font-size: 2rem;
            font-weight: 900;
            background: linear-gradient(135deg, var(--neon-cyan), var(--neon-pink));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-gray);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--neon-cyan);
            transition: width 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--neon-cyan);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .cart-btn {
            background: linear-gradient(135deg, var(--neon-cyan), var(--electric-blue));
            padding: 12px 30px;
            border-radius: 25px;
            border: none;
            color: var(--dark-bg);
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.4);
            font-size: 1rem;
        }

        .cart-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(0, 255, 255, 0.6);
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 100px 0;
            position: relative;
        }

        .hero h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(3rem, 10vw, 6rem);
            font-weight: 900;
            background: linear-gradient(135deg, var(--neon-cyan), var(--neon-pink), var(--neon-yellow));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: -2px;
            animation: glowPulse 3s ease-in-out infinite;
        }

        @keyframes glowPulse {
            0%, 100% { filter: drop-shadow(0 0 20px rgba(0, 255, 255, 0.8)); }
            50% { filter: drop-shadow(0 0 40px rgba(255, 0, 255, 0.8)); }
        }

        .hero p {
            font-size: 1.5rem;
            color: var(--text-gray);
            margin-bottom: 40px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--neon-pink), var(--electric-blue));
            padding: 18px 45px;
            border-radius: 30px;
            border: none;
            color: white;
            font-weight: 700;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 0 30px rgba(255, 0, 255, 0.5);
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 40px rgba(255, 0, 255, 0.7);
        }

        .btn-secondary {
            background: transparent;
            padding: 18px 45px;
            border-radius: 30px;
            border: 2px solid var(--neon-cyan);
            color: var(--neon-cyan);
            font-weight: 700;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-secondary:hover {
            background: var(--neon-cyan);
            color: var(--dark-bg);
            transform: translateY(-5px);
        }

        /* Categories */
        .categories {
            padding: 80px 0;
        }

        .section-title {
            font-family: 'Orbitron', sans-serif;
            font-size: 3rem;
            text-align: center;
            margin-bottom: 60px;
            background: linear-gradient(135deg, var(--neon-yellow), var(--neon-cyan));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-transform: uppercase;
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }

        .category-card {
            background: linear-gradient(145deg, var(--card-bg), rgba(27, 15, 58, 0.5));
            border: 2px solid rgba(0, 255, 255, 0.2);
            border-radius: 20px;
            padding: 40px;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .category-card::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, var(--neon-cyan), var(--neon-pink), var(--neon-yellow));
            border-radius: 20px;
            z-index: -1;
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .category-card:hover::before {
            opacity: 1;
        }

        .category-card:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: 0 20px 60px rgba(0, 255, 255, 0.3);
        }

        .category-icon {
            font-size: 4rem;
            margin-bottom: 20px;
            filter: drop-shadow(0 0 10px rgba(0, 255, 255, 0.6));
        }

        .category-card h3 {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: var(--neon-cyan);
        }

        .category-card p {
            color: var(--text-gray);
            font-size: 1.1rem;
            line-height: 1.6;
        }

        /* Products */
        .products {
            padding: 80px 0;
            background: rgba(0, 0, 0, 0.3);
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }

        .product-card {
            background: var(--card-bg);
            border: 1px solid rgba(0, 255, 255, 0.2);
            border-radius: 15px;
            overflow: hidden;
            transition: all 0.3s ease;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-10px);
            border-color: var(--neon-pink);
            box-shadow: 0 15px 40px rgba(255, 0, 255, 0.3);
        }

        .product-image {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, rgba(0, 128, 255, 0.2), rgba(255, 0, 255, 0.2));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 5rem;
            position: relative;
            overflow: hidden;
        }

        .product-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--neon-pink);
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-weight: 700;
            font-size: 0.85rem;
        }

        .product-info {
            padding: 25px;
        }

        .product-info h4 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--neon-cyan);
        }

        .product-price {
            display: flex;
            align-items: center;
            gap: 10px;
            margin: 15px 0;
        }

        .price-original {
            text-decoration: line-through;
            color: var(--text-gray);
            font-size: 1rem;
        }

        .price-sale {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--neon-yellow);
        }

        .add-to-cart {
            width: 100%;
            background: linear-gradient(135deg, var(--electric-blue), var(--neon-cyan));
            border: none;
            padding: 12px;
            border-radius: 8px;
            color: white;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 10px;
        }

        .add-to-cart:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 20px rgba(0, 255, 255, 0.5);
        }

        /* Features */
        .features {
            padding: 80px 0;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            text-align: center;
        }

        .feature-item {
            padding: 30px;
        }

        .feature-icon {
            font-size: 3.5rem;
            margin-bottom: 20px;
            filter: drop-shadow(0 0 15px rgba(255, 255, 0, 0.6));
        }

        .feature-item h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--neon-yellow);
        }

        .feature-item p {
            color: var(--text-gray);
            line-height: 1.6;
        }

        /* Newsletter */
        .newsletter {
            background: linear-gradient(135deg, rgba(0, 128, 255, 0.1), rgba(255, 0, 255, 0.1));
            padding: 80px 20px;
            text-align: center;
            border-top: 2px solid rgba(0, 255, 255, 0.3);
            border-bottom: 2px solid rgba(255, 0, 255, 0.3);
        }

        .newsletter h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--neon-cyan);
        }

        .newsletter p {
            font-size: 1.2rem;
            color: var(--text-gray);
            margin-bottom: 30px;
        }

        .newsletter-form {
            display: flex;
            gap: 15px;
            max-width: 600px;
            margin: 0 auto;
            flex-wrap: wrap;
            justify-content: center;
        }

        .newsletter-form input {
            flex: 1;
            min-width: 250px;
            padding: 15px 25px;
            border-radius: 30px;
            border: 2px solid var(--neon-cyan);
            background: rgba(0, 0, 0, 0.5);
            color: white;
            font-size: 1rem;
        }

        .newsletter-form input::placeholder {
            color: var(--text-gray);
        }

        .newsletter-form button {
            padding: 15px 40px;
            border-radius: 30px;
            border: none;
            background: linear-gradient(135deg, var(--neon-pink), var(--electric-blue));
            color: white;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .newsletter-form button:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 20px rgba(255, 0, 255, 0.5);
        }

        /* Footer */
        footer {
            padding: 60px 20px 30px;
            background: rgba(0, 0, 0, 0.5);
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h3 {
            font-family: 'Orbitron', sans-serif;
            color: var(--neon-cyan);
            margin-bottom: 20px;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 10px;
        }

        .footer-section a {
            color: var(--text-gray);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-section a:hover {
            color: var(--neon-cyan);
        }

        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            border: 2px solid var(--neon-cyan);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .social-icon:hover {
            background: var(--neon-cyan);
            color: var(--dark-bg);
            transform: scale(1.1);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(0, 255, 255, 0.2);
            color: var(--text-gray);
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--neon-cyan);
            font-size: 1.8rem;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: rgba(13, 2, 33, 0.98);
                flex-direction: column;
                padding: 20px;
                gap: 15px;
            }

            .nav-links.active {
                display: flex;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .category-grid,
            .product-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Animations */
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .floating {
            animation: float 3s ease-in-out infinite;
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>
    <div class="grid-overlay"></div>

    <div class="container">
        <!-- Navigation -->
        <nav>
            <div class="logo">TECHDROP</div>
            <button class="mobile-menu-btn" onclick="toggleMenu()">☰</button>
            <ul class="nav-links" id="navLinks">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#categorias">Categorías</a></li>
                <li><a href="#productos">Productos</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
            <button class="cart-btn">🛒 Carrito (0)</button>
        </nav>

        <!-- Hero Section -->
        <section class="hero" id="inicio">
            <h1 class="floating">Tech del Futuro</h1>
            <p>Gaming, Accesorios Móvil y Tecnología de Última Generación. Envíos rápidos desde Europa y Asia.</p>
            <div class="cta-buttons">
                <a href="#productos" class="btn-primary">Ver Productos</a>
                <a href="#categorias" class="btn-secondary">Explorar Categorías</a>
            </div>
        </section>

        <!-- Categories -->
        <section class="categories" id="categorias">
            <h2 class="section-title">Nuestras Categorías</h2>
            <div class="category-grid">
                <div class="category-card">
                    <div class="category-icon">🎮</div>
                    <h3>Gaming</h3>
                    <p>Teclados mecánicos, ratones RGB, auriculares pro, mandos, sillas gaming y accesorios para llevar tu setup al siguiente nivel.</p>
                </div>
                <div class="category-card">
                    <div class="category-icon">📱</div>
                    <h3>Accesorios Móvil</h3>
                    <p>Fundas premium, cargadores rápidos, powerbanks, soportes, cables magnéticos y protectores de pantalla de máxima calidad.</p>
                </div>
                <div class="category-card">
                    <div class="category-icon">💻</div>
                    <h3>Tech General</h3>
                    <p>Smart home, wearables, audio TWS, gadgets de productividad, cámaras de seguridad y la última tecnología.</p>
                </div>
            </div>
        </section>

        <!-- Featured Products -->
        <section class="products" id="productos">
            <div class="container">
                <h2 class="section-title">Productos Destacados</h2>
                <div class="product-grid">
                    <!-- Product 1 -->
                    <div class="product-card">
                        <div class="product-image">
                            🎮
                            <span class="product-badge">-40%</span>
                        </div>
                        <div class="product-info">
                            <h4>Teclado Mecánico RGB</h4>
                            <p>Switch azules, iluminación personalizable, cable USB-C desmontable</p>
                            <div class="product-price">
                                <span class="price-original">€79.99</span>
                                <span class="price-sale">€47.99</span>
                            </div>
                            <button class="add-to-cart">Añadir al Carrito</button>
                        </div>
                    </div>

                    <!-- Product 2 -->
                    <div class="product-card">
                        <div class="product-image">
                            🖱️
                            <span class="product-badge">HOT</span>
                        </div>
                        <div class="product-info">
                            <h4>Ratón Gaming Pro</h4>
                            <p>16,000 DPI, 7 botones programables, RGB dinámico</p>
                            <div class="product-price">
                                <span class="price-original">€59.99</span>
                                <span class="price-sale">€34.99</span>
                            </div>
                            <button class="add-to-cart">Añadir al Carrito</button>
                        </div>
                    </div>

                    <!-- Product 3 -->
                    <div class="product-card">
                        <div class="product-image">
                            🎧
                            <span class="product-badge">NUEVO</span>
                        </div>
                        <div class="product-info">
                            <h4>Auriculares TWS Pro</h4>
                            <p>ANC activo, 30h batería, carga inalámbrica, resistentes al agua</p>
                            <div class="product-price">
                                <span class="price-original">€89.99</span>
                                <span class="price-sale">€54.99</span>
                            </div>
                            <button class="add-to-cart">Añadir al Carrito</button>
                        </div>
                    </div>

                    <!-- Product 4 -->
                    <div class="product-card">
                        <div class="product-image">
                            📱
                            <span class="product-badge">-35%</span>
                        </div>
                        <div class="product-info">
                            <h4>Funda Premium MagSafe</h4>
                            <p>Compatible iPhone 15, protección militar, textura premium</p>
                            <div class="product-price">
                                <span class="price-original">€29.99</span>
                                <span class="price-sale">€19.49</span>
                            </div>
                            <button class="add-to-cart">Añadir al Carrito</button>
                        </div>
                    </div>

                    <!-- Product 5 -->
                    <div class="product-card">
                        <div class="product-image">
                            🔋
                            <span class="product-badge">TOP</span>
                        </div>
                        <div class="product-info">
                            <h4>PowerBank 20000mAh</h4>
                            <p>Carga rápida 65W, 3 puertos, pantalla LED, ultra compacto</p>
                            <div class="product-price">
                                <span class="price-original">€49.99</span>
                                <span class="price-sale">€32.99</span>
                            </div>
                            <button class="add-to-cart">Añadir al Carrito</button>
                        </div>
                    </div>

                    <!-- Product 6 -->
                    <div class="product-card">
                        <div class="product-image">
                            ⌚
                            <span class="product-badge">-50%</span>
                        </div>
                        <div class="product-info">
                            <h4>Smartwatch Fitness Pro</h4>
                            <p>Monitor cardíaco, GPS, 14 días batería, resistente agua</p>
                            <div class="product-price">
                                <span class="price-original">€99.99</span>
                                <span class="price-sale">€49.99</span>
                            </div>
                            <button class="add-to-cart">Añadir al Carrito</button>
                        </div>
                    </div>

                    <!-- Product 7 -->
                    <div class="product-card">
                        <div class="product-image">
                            💡
                        </div>
                        <div class="product-info">
                            <h4>Tira LED Smart RGB 5m</h4>
                            <p>Control por app, 16M colores, sincronización música</p>
                            <div class="product-price">
                                <span class="price-original">€39.99</span>
                                <span class="price-sale">€24.99</span>
                            </div>
                            <button class="add-to-cart">Añadir al Carrito</button>
                        </div>
                    </div>

                    <!-- Product 8 -->
                    <div class="product-card">
                        <div class="product-image">
                            📷
                            <span class="product-badge">OFERTA</span>
                        </div>
                        <div class="product-info">
                            <h4>Cámara Seguridad WiFi</h4>
                            <p>1080p, visión nocturna, detección movimiento, app móvil</p>
                            <div class="product-price">
                                <span class="price-original">€69.99</span>
                                <span class="price-sale">€39.99</span>
                            </div>
                            <button class="add-to-cart">Añadir al Carrito</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Features -->
        <section class="features">
            <h2 class="section-title">¿Por Qué TechDrop?</h2>
            <div class="features-grid">
                <div class="feature-item">
                    <div class="feature-icon">🚀</div>
                    <h3>Envío Express</h3>
                    <p>Envíos rápidos desde almacenes en Europa. Recibe en 7-14 días.</p>
                </div>
                <div class="feature-item">
                    <div class="feature-icon">💰</div>
                    <h3>Mejores Precios</h3>
                    <p>Importación directa = precios increíbles. Hasta 60% más barato.</p>
                </div>
                <div class="feature-item">
                    <div class="feature-icon">✅</div>
                    <h3>Garantía Total</h3>
                    <p>30 días de devolución. Si no te gusta, te devolvemos el dinero.</p>
                </div>
                <div class="feature-item">
                    <div class="feature-icon">🔒</div>
                    <h3>Pago Seguro</h3>
                    <p>Encriptación SSL. PayPal, tarjeta, transferencia. 100% seguro.</p>
                </div>
            </div>
        </section>

        <!-- Newsletter -->
        <section class="newsletter" id="contacto">
            <h2>Únete a la Comunidad Tech</h2>
            <p>Suscríbete y recibe ofertas exclusivas, nuevos productos y descuentos de hasta 50%</p>
            <form class="newsletter-form">
                <input type="email" placeholder="tu@email.com" required>
                <button type="submit">Suscribirse</button>
            </form>
        </section>

        <!-- Footer -->
        <footer>
            <div class="footer-content">
                <div class="footer-section">
                    <h3>TechDrop</h3>
                    <p>Tu tienda de tecnología gaming, móvil y gadgets tech. Calidad premium a precios increíbles.</p>
                    <div class="social-icons">
                        <div class="social-icon">📘</div>
                        <div class="social-icon">📸</div>
                        <div class="social-icon">🐦</div>
                        <div class="social-icon">📺</div>
                    </div>
                </div>
                <div class="footer-section">
                    <h3>Categorías</h3>
                    <ul>
                        <li><a href="#">Gaming</a></li>
                        <li><a href="#">Accesorios Móvil</a></li>
                        <li><a href="#">Smart Home</a></li>
                        <li><a href="#">Wearables</a></li>
                        <li><a href="#">Audio</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Ayuda</h3>
                    <ul>
                        <li><a href="#">Seguimiento Pedido</a></li>
                        <li><a href="#">Devoluciones</a></li>
                        <li><a href="#">Envíos</a></li>
                        <li><a href="#">Preguntas Frecuentes</a></li>
                        <li><a href="#">Contacto</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Legal</h3>
                    <ul>
                        <li><a href="#">Términos y Condiciones</a></li>
                        <li><a href="#">Política de Privacidad</a></li>
                        <li><a href="#">Política de Cookies</a></li>
                        <li><a href="#">Aviso Legal</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 TechDrop. Todos los derechos reservados. | Diseñado con 💙 para gamers y tech lovers</p>
            </div>
        </footer>
    </div>

    <script>
        // Mobile menu toggle
        function toggleMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.toggle('active');
        }

        // Add to cart functionality
        const addToCartButtons = document.querySelectorAll('.add-to-cart');
        let cartCount = 0;

        addToCartButtons.forEach(button => {
            button.addEventListener('click', function() {
                cartCount++;
                document.querySelector('.cart-btn').textContent = `🛒 Carrito (${cartCount})`;
                
                // Animation
                this.textContent = '✅ Añadido!';
                this.style.background = 'linear-gradient(135deg, #00FF00, #00CC00)';
                
                setTimeout(() => {
                    this.textContent = 'Añadir al Carrito';
                    this.style.background = 'linear-gradient(135deg, var(--electric-blue), var(--neon-cyan))';
                }, 1500);
            });
        });

        // Newsletter form
        const newsletterForm = document.querySelector('.newsletter-form');
        newsletterForm.addEventListener('submit', function(e) {
            e.preventDefault();
            alert('¡Gracias por suscribirte! Recibirás ofertas exclusivas pronto 🚀');
            this.reset();
        });

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </script>
</body>
</html>
