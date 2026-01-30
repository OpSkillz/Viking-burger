# Viking-burger
Viking burger restaurant website
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>فايكنج بركر | Viking Burger - أقوى بركر بالموصل</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Rakkas&family=Amiri:wght@400;700&family=Cairo:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --viking-red: #C41E3A;
            --viking-gold: #D4AF37;
            --viking-dark: #0D0D0D;
            --viking-charcoal: #1A1A1A;
            --viking-warmgray: #2A2A2A;
            --viking-orange: #FF6B35;
            --viking-cream: #F5E6D3;
            --text-light: #FFFFFF;
            --text-muted: #B0B0B0;
        }

        body {
            font-family: 'Cairo', sans-serif;
            background-color: var(--viking-dark);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animated Background Pattern */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                repeating-linear-gradient(45deg, transparent, transparent 35px, rgba(212, 175, 55, 0.02) 35px, rgba(212, 175, 55, 0.02) 70px);
            pointer-events: none;
            z-index: 0;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(13, 13, 13, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 2px solid var(--viking-gold);
            animation: slideDown 0.6s ease-out;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
        }

        .logo {
            font-family: 'Rakkas', cursive;
            font-size: 2rem;
            background: linear-gradient(135deg, var(--viking-gold), var(--viking-orange));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(212, 175, 55, 0.3);
            animation: glow 3s ease-in-out infinite;
        }

        @keyframes glow {
            0%, 100% { filter: brightness(1); }
            50% { filter: brightness(1.3); }
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            position: relative;
            padding: 0.5rem 0;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 0;
            height: 2px;
            background: var(--viking-gold);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--viking-gold);
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--text-light);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 6rem 2rem 4rem;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(196, 30, 58, 0.15), transparent 50%),
                radial-gradient(circle at 80% 50%, rgba(255, 107, 53, 0.15), transparent 50%);
            animation: heroGlow 8s ease-in-out infinite;
        }

        @keyframes heroGlow {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }

        .hero-content {
            position: relative;
            text-align: center;
            max-width: 1200px;
            z-index: 1;
        }

        .hero h1 {
            font-family: 'Rakkas', cursive;
            font-size: clamp(3rem, 8vw, 6rem);
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--viking-gold), var(--viking-orange), var(--viking-red));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: slideUp 0.8s ease-out 0.2s both;
            text-shadow: 0 4px 20px rgba(212, 175, 55, 0.4);
        }

        @keyframes slideUp {
            from {
                transform: translateY(40px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .hero-subtitle {
            font-size: clamp(1.2rem, 3vw, 1.8rem);
            color: var(--viking-cream);
            margin-bottom: 2rem;
            font-weight: 600;
            animation: slideUp 0.8s ease-out 0.4s both;
        }

        .hero-features {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin-bottom: 3rem;
            animation: slideUp 0.8s ease-out 0.6s both;
        }

        .feature-badge {
            background: rgba(212, 175, 55, 0.1);
            border: 2px solid var(--viking-gold);
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            font-weight: 600;
            color: var(--viking-gold);
            transition: all 0.3s;
        }

        .feature-badge:hover {
            background: var(--viking-gold);
            color: var(--viking-dark);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(212, 175, 55, 0.3);
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: slideUp 0.8s ease-out 0.8s both;
        }

        .btn {
            padding: 1.2rem 3rem;
            font-size: 1.2rem;
            font-weight: 700;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.4s;
            text-decoration: none;
            display: inline-block;
            font-family: 'Cairo', sans-serif;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--viking-red), var(--viking-orange));
            color: var(--text-light);
            box-shadow: 0 10px 40px rgba(196, 30, 58, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 50px rgba(196, 30, 58, 0.6);
        }

        .btn-secondary {
            background: transparent;
            color: var(--viking-gold);
            border: 3px solid var(--viking-gold);
        }

        .btn-secondary:hover {
            background: var(--viking-gold);
            color: var(--viking-dark);
            transform: translateY(-5px);
        }

        /* Sections */
        section {
            padding: 6rem 2rem;
            position: relative;
            z-index: 1;
        }

        .section-title {
            font-family: 'Rakkas', cursive;
            font-size: clamp(2.5rem, 5vw, 4rem);
            text-align: center;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--viking-gold), var(--viking-orange));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .section-subtitle {
            text-align: center;
            color: var(--text-muted);
            margin-bottom: 4rem;
            font-size: 1.2rem;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text {
            animation: fadeIn 1s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .about-text h3 {
            font-size: 2rem;
            color: var(--viking-gold);
            margin-bottom: 1.5rem;
            font-family: 'Cairo', sans-serif;
            font-weight: 900;
        }

        .about-text p {
            font-size: 1.2rem;
            line-height: 2;
            margin-bottom: 1.5rem;
            color: var(--viking-cream);
        }

        .trust-signals {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
            margin-top: 3rem;
        }

        .trust-item {
            text-align: center;
            padding: 2rem;
            background: rgba(212, 175, 55, 0.05);
            border-radius: 20px;
            border: 1px solid rgba(212, 175, 55, 0.2);
            transition: all 0.3s;
        }

        .trust-item:hover {
            background: rgba(212, 175, 55, 0.1);
            transform: translateY(-5px);
        }

        .trust-number {
            font-size: 3rem;
            font-weight: 900;
            color: var(--viking-gold);
            font-family: 'Rakkas', cursive;
        }

        .trust-label {
            color: var(--text-muted);
            margin-top: 0.5rem;
        }

        /* Menu Section */
        #menu {
            background: linear-gradient(180deg, var(--viking-dark) 0%, var(--viking-charcoal) 100%);
        }

        .menu-categories {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }

        .category-btn {
            padding: 0.8rem 2rem;
            background: transparent;
            border: 2px solid var(--viking-gold);
            color: var(--viking-gold);
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            font-family: 'Cairo', sans-serif;
            font-size: 1rem;
            transition: all 0.3s;
        }

        .category-btn.active,
        .category-btn:hover {
            background: var(--viking-gold);
            color: var(--viking-dark);
            transform: translateY(-3px);
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
        }

        .menu-item {
            background: rgba(26, 26, 26, 0.8);
            border-radius: 20px;
            overflow: hidden;
            border: 2px solid transparent;
            transition: all 0.4s;
            position: relative;
        }

        .menu-item:hover {
            border-color: var(--viking-gold);
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(212, 175, 55, 0.2);
        }

        .menu-item.popular::before {
            content: 'الأكثر طلباً';
            position: absolute;
            top: 20px;
            left: 20px;
            background: var(--viking-red);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 700;
            z-index: 2;
            box-shadow: 0 5px 15px rgba(196, 30, 58, 0.4);
        }

        .menu-item-image {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, var(--viking-charcoal), var(--viking-warmgray));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            position: relative;
            overflow: hidden;
        }

        .menu-item-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(196, 30, 58, 0.2), rgba(255, 107, 53, 0.2));
            opacity: 0;
            transition: opacity 0.4s;
        }

        .menu-item:hover .menu-item-image::before {
            opacity: 1;
        }

        .menu-item-content {
            padding: 1.5rem;
        }

        .menu-item-title {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--viking-gold);
            margin-bottom: 0.5rem;
        }

        .menu-item-description {
            color: var(--text-muted);
            margin-bottom: 1rem;
            font-size: 0.95rem;
        }

        .menu-item-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .menu-item-price {
            font-size: 1.8rem;
            font-weight: 900;
            color: var(--viking-orange);
            font-family: 'Cairo', sans-serif;
        }

        .menu-item-order {
            padding: 0.6rem 1.5rem;
            background: linear-gradient(135deg, var(--viking-red), var(--viking-orange));
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 700;
            transition: all 0.3s;
            font-family: 'Cairo', sans-serif;
        }

        .menu-item-order:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 20px rgba(196, 30, 58, 0.4);
        }

        /* Reviews Section */
        .reviews-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .review-card {
            background: rgba(26, 26, 26, 0.6);
            padding: 2rem;
            border-radius: 20px;
            border-right: 4px solid var(--viking-gold);
            transition: all 0.3s;
        }

        .review-card:hover {
            background: rgba(26, 26, 26, 0.9);
            transform: translateX(-10px);
        }

        .review-stars {
            color: var(--viking-gold);
            font-size: 1.3rem;
            margin-bottom: 1rem;
        }

        .review-text {
            color: var(--viking-cream);
            line-height: 1.8;
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .review-author {
            color: var(--text-muted);
            font-style: italic;
        }

        .google-rating {
            text-align: center;
            margin-bottom: 3rem;
            padding: 2rem;
            background: rgba(212, 175, 55, 0.05);
            border-radius: 20px;
        }

        .google-rating-score {
            font-size: 4rem;
            font-weight: 900;
            color: var(--viking-gold);
            font-family: 'Rakkas', cursive;
        }

        .google-rating-text {
            font-size: 1.2rem;
            color: var(--text-muted);
        }

        /* Contact Section */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .contact-item {
            background: rgba(26, 26, 26, 0.6);
            padding: 2rem;
            border-radius: 20px;
            border-right: 4px solid var(--viking-gold);
            transition: all 0.3s;
        }

        .contact-item:hover {
            background: rgba(26, 26, 26, 0.9);
            transform: translateX(-10px);
        }

        .contact-label {
            font-size: 1rem;
            color: var(--text-muted);
            margin-bottom: 0.5rem;
        }

        .contact-value {
            font-size: 1.5rem;
            color: var(--viking-gold);
            font-weight: 700;
        }

        .contact-value a {
            color: var(--viking-gold);
            text-decoration: none;
            transition: all 0.3s;
        }

        .contact-value a:hover {
            color: var(--viking-orange);
        }

        .map-container {
            height: 500px;
            border-radius: 20px;
            overflow: hidden;
            border: 3px solid var(--viking-gold);
            box-shadow: 0 10px 40px rgba(212, 175, 55, 0.2);
        }

        .map-container iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Footer */
        footer {
            background: var(--viking-charcoal);
            padding: 3rem 2rem;
            border-top: 2px solid var(--viking-gold);
            text-align: center;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
        }

        .footer-logo {
            font-family: 'Rakkas', cursive;
            font-size: 2.5rem;
            background: linear-gradient(135deg, var(--viking-gold), var(--viking-orange));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
        }

        .footer-text {
            color: var(--text-muted);
            margin-bottom: 2rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(212, 175, 55, 0.1);
            border: 2px solid var(--viking-gold);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--viking-gold);
            text-decoration: none;
            transition: all 0.3s;
            font-size: 1.5rem;
        }

        .social-link:hover {
            background: var(--viking-gold);
            color: var(--viking-dark);
            transform: translateY(-5px);
        }

        /* Services Badges */
        .services-badges {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin-top: 3rem;
        }

        .service-badge {
            background: linear-gradient(135deg, var(--viking-red), var(--viking-orange));
            padding: 1.5rem 2.5rem;
            border-radius: 60px;
            font-weight: 700;
            font-size: 1.1rem;
            box-shadow: 0 10px 30px rgba(196, 30, 58, 0.3);
            animation: float 3s ease-in-out infinite;
        }

        .service-badge:nth-child(2) {
            animation-delay: 0.5s;
        }

        .service-badge:nth-child(3) {
            animation-delay: 1s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .mobile-menu-btn {
                display: block;
            }

            .about-content,
            .contact-grid {
                grid-template-columns: 1fr;
            }

            .trust-signals {
                grid-template-columns: 1fr;
            }

            .hero-features {
                flex-direction: column;
                align-items: center;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: stretch;
            }

            .menu-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Scroll animations */
        .fade-in-up {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }

        .fade-in-up.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo">فايكنج بركر</div>
            <ul class="nav-links">
                <li><a href="#home">الرئيسية</a></li>
                <li><a href="#about">من نحن</a></li>
                <li><a href="#menu">القائمة</a></li>
                <li><a href="#reviews">التقييمات</a></li>
                <li><a href="#contact">اتصل بنا</a></li>
            </ul>
            <button class="mobile-menu-btn">☰</button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>أقوى بركر بالموصل</h1>
            <p class="hero-subtitle">Viking Burger - طعم لا يُنسى، جودة لا تُضاهى</p>
            
            <div class="hero-features">
                <div class="feature-badge">🍔 حجم كبير</div>
                <div class="feature-badge">⭐ طعم مميز</div>
                <div class="feature-badge">💰 أسعار منافسة</div>
            </div>

            <div class="cta-buttons">
                <a href="tel:07706662044" class="btn btn-primary">اطلب الآن 📞</a>
                <a href="#menu" class="btn btn-secondary">شاهد القائمة</a>
            </div>

            <div class="services-badges">
                <div class="service-badge">✅ توصيل</div>
                <div class="service-badge">✅ استلام</div>
                <div class="service-badge">✅ تناول بالمطعم</div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="container">
            <h2 class="section-title fade-in-up">من نحن</h2>
            <p class="section-subtitle fade-in-up">قصة نجاح في قلب الموصل</p>
            
            <div class="about-content">
                <div class="about-text fade-in-up">
                    <h3>فايكنج بركر - وجهتك الأولى للبرغر الفاخر</h3>
                    <p>
                        في فايكنج بركر، نحن نؤمن بأن البرغر الرائع يبدأ بمكونات عالية الجودة وحب للطعام. 
                        منذ تأسيسنا في قلب الموصل، كنا ملتزمين بتقديم أفضل تجربة طعام لعملائنا الكرام.
                    </p>
                    <p>
                        نفخر بتقديم وجبات بحجم كبير، طعم لا يُقاوم، وأسعار تناسب الجميع. 
                        كل برغر يُحضّر بعناية فائقة ومكونات طازجة لضمان رضاكم التام.
                    </p>
                    <p>
                        نظافة المطعم، سرعة الخدمة، وجودة الطعام - هذه هي وعودنا لكم.
                    </p>
                </div>

                <div class="trust-signals fade-in-up">
                    <div class="trust-item">
                        <div class="trust-number">3.9</div>
                        <div class="trust-label">تقييم جوجل من 5</div>
                    </div>
                    <div class="trust-item">
                        <div class="trust-number">175+</div>
                        <div class="trust-label">تقييم من العملاء</div>
                    </div>
                    <div class="trust-item">
                        <div class="trust-number">100%</div>
                        <div class="trust-label">طازج يومياً</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section id="menu">
        <div class="container">
            <h2 class="section-title fade-in-up">القائمة</h2>
            <p class="section-subtitle fade-in-up">اختر من تشكيلتنا المميزة</p>

            <div class="menu-categories fade-in-up">
                <button class="category-btn active">الكل</button>
                <button class="category-btn">برغر</button>
                <button class="category-btn">وجبات</button>
                <button class="category-btn">مشروبات</button>
            </div>

            <div class="menu-grid">
                <div class="menu-item popular fade-in-up">
                    <div class="menu-item-image">🍔</div>
                    <div class="menu-item-content">
                        <h3 class="menu-item-title">وجبة بركر بالفطر</h3>
                        <p class="menu-item-description">برغر فاخر مع فطر طازج، جبنة ذائبة، وصوص خاص</p>
                        <div class="menu-item-footer">
                            <span class="menu-item-price">6,000 د.ع</span>
                            <button class="menu-item-order">اطلب</button>
                        </div>
                    </div>
                </div>

                <div class="menu-item popular fade-in-up">
                    <div class="menu-item-image">🍗</div>
                    <div class="menu-item-content">
                        <h3 class="menu-item-title">زنجر</h3>
                        <p class="menu-item-description">دجاج مقرمش حار، خس طازج، مع صوص زنجر الشهير</p>
                        <div class="menu-item-footer">
                            <span class="menu-item-price">5,500 د.ع</span>
                            <button class="menu-item-order">اطلب</button>
                        </div>
                    </div>
                </div>

                <div class="menu-item popular fade-in-up">
                    <div class="menu-item-image">🏍️</div>
                    <div class="menu-item-content">
                        <h3 class="menu-item-title">Super Gypsy Biker</h3>
                        <p class="menu-item-description">أكبر برغر لدينا، مزدوج اللحم، جبنة، خضار طازجة</p>
                        <div class="menu-item-footer">
                            <span class="menu-item-price">7,500 د.ع</span>
                            <button class="menu-item-order">اطلب</button>
                        </div>
                    </div>
                </div>

                <div class="menu-item fade-in-up">
                    <div class="menu-item-image">🍚</div>
                    <div class="menu-item-content">
                        <h3 class="menu-item-title">ريزو</h3>
                        <p class="menu-item-description">رز مع دجاج متبل بطريقة فايكنج الخاصة</p>
                        <div class="menu-item-footer">
                            <span class="menu-item-price">6,000 د.ع</span>
                            <button class="menu-item-order">اطلب</button>
                        </div>
                    </div>
                </div>

                <div class="menu-item fade-in-up">
                    <div class="menu-item-image">🍟</div>
                    <div class="menu-item-content">
                        <h3 class="menu-item-title">بطاطا فايكنج</h3>
                        <p class="menu-item-description">بطاطا مقرمشة مع توابل فايكنج السرية</p>
                        <div class="menu-item-footer">
                            <span class="menu-item-price">2,500 د.ع</span>
                            <button class="menu-item-order">اطلب</button>
                        </div>
                    </div>
                </div>

                <div class="menu-item fade-in-up">
                    <div class="menu-item-image">🥤</div>
                    <div class="menu-item-content">
                        <h3 class="menu-item-title">مشروبات</h3>
                        <p class="menu-item-description">كولا، سفن اب، ميراندا - كل الأحجام</p>
                        <div class="menu-item-footer">
                            <span class="menu-item-price">1,000 د.ع</span>
                            <button class="menu-item-order">اطلب</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Reviews Section -->
    <section id="reviews">
        <div class="container">
            <h2 class="section-title fade-in-up">آراء عملائنا</h2>
            <p class="section-subtitle fade-in-up">ماذا يقول من جربوا فايكنج بركر</p>

            <div class="google-rating fade-in-up">
                <div class="google-rating-score">3.9 ⭐</div>
                <div class="google-rating-text">من 175 تقييم على جوجل</div>
            </div>

            <div class="reviews-grid">
                <div class="review-card fade-in-up">
                    <div class="review-stars">⭐⭐⭐⭐⭐</div>
                    <p class="review-text">
                        "أحسن برغر بالموصل، الحجم كبير والطعم خرافي. الأسعار معقولة جداً 
                        والخدمة سريعة. أنصح الجميع بتجربة وجبة الفطر!"
                    </p>
                    <p class="review-author">- أحمد م.</p>
                </div>

                <div class="review-card fade-in-up">
                    <div class="review-stars">⭐⭐⭐⭐</div>
                    <p class="review-text">
                        "مطعم نظيف والطعم ممتاز، خصوصاً الزنجر. يستحقون الدعم. 
                        الوحيد الي يزعج شوية هو وقت الانتظار بأوقات الذروة."
                    </p>
                    <p class="review-author">- سارة ع.</p>
                </div>

                <div class="review-card fade-in-up">
                    <div class="review-stars">⭐⭐⭐⭐⭐</div>
                    <p class="review-text">
                        "Super Gypsy Biker أكبر برغر شفته بحياتي! سعره معقول جداً مقارنة 
                        بالحجم والجودة. المكان نظيف والموظفين محترمين."
                    </p>
                    <p class="review-author">- كريم ح.</p>
                </div>

                <div class="review-card fade-in-up">
                    <div class="review-stars">⭐⭐⭐⭐</div>
                    <p class="review-text">
                        "طعم ممتاز وأسعار مناسبة. البطاطا لذيذة جداً والريزو عجيب. 
                        أكيد رح أرجع مرة ثانية."
                    </p>
                    <p class="review-author">- علي ن.</p>
                </div>

                <div class="review-card fade-in-up">
                    <div class="review-stars">⭐⭐⭐⭐⭐</div>
                    <p class="review-text">
                        "من أفضل مطاعم البرغر بالموصل. الجودة عالية، النظافة ممتازة، 
                        والأهم من هذا كله الطعم الرائع. ننصح فيه بقوة!"
                    </p>
                    <p class="review-author">- فاطمة س.</p>
                </div>

                <div class="review-card fade-in-up">
                    <div class="review-stars">⭐⭐⭐⭐</div>
                    <p class="review-text">
                        "وجبة الفطر تحفة، والتوصيل سريع. الأسعار معقولة جداً. 
                        بس يا ريت يزيدون أصناف بالقائمة."
                    </p>
                    <p class="review-author">- محمد ر.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <h2 class="section-title fade-in-up">اتصل بنا</h2>
            <p class="section-subtitle fade-in-up">نحن في انتظارك</p>

            <div class="contact-grid">
                <div class="contact-info fade-in-up">
                    <div class="contact-item">
                        <div class="contact-label">📞 رقم الهاتف</div>
                        <div class="contact-value">
                            <a href="tel:07706662044">0770 666 2044</a>
                        </div>
                    </div>

                    <div class="contact-item">
                        <div class="contact-label">📍 العنوان</div>
                        <div class="contact-value">95F9+65J، الموصل، محافظة نينوى</div>
                    </div>

                    <div class="contact-item">
                        <div class="contact-label">🕐 ساعات العمل</div>
                        <div class="contact-value">
                            يومياً - نغلق الساعة 3:00 صباحاً
                        </div>
                    </div>

                    <div class="contact-item">
                        <div class="contact-label">📱 خدماتنا</div>
                        <div class="contact-value">
                            توصيل • استلام • تناول بالمطعم
                        </div>
                    </div>

                    <a href="tel:07706662044" class="btn btn-primary" style="width: 100%; text-align: center; margin-top: 1rem;">
                        اتصل الآن للطلب 📞
                    </a>
                </div>

                <div class="map-container fade-in-up">
                    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3267.8425!2d43.1185!3d36.3733!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMzbCsDIyJzIzLjkiTiA0M8KwMDcnMDYuNiJF!5e0!3m2!1sen!2siq!4v1234567890" allowfullscreen="" loading="lazy"></iframe>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-logo">فايكنج بركر</div>
            <p class="footer-text">أقوى بركر بالموصل - طعم لا يُنسى</p>
            
            <div class="social-links">
                <a href="https://www.facebook.com" class="social-link" target="_blank">📘</a>
                <a href="https://www.instagram.com" class="social-link" target="_blank">📷</a>
                <a href="tel:07706662044" class="social-link">📞</a>
            </div>

            <p class="footer-text">
                © 2026 Viking Burger Restaurant. جميع الحقوق محفوظة.
            </p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
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

        // Scroll animation observer
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in-up').forEach(el => {
            observer.observe(el);
        });

        // Menu category filter (simple simulation)
        const categoryBtns = document.querySelectorAll('.category-btn');
        categoryBtns.forEach(btn => {
            btn.addEventListener('click', function() {
                categoryBtns.forEach(b => b.classList.remove('active'));
                this.classList.add('active');
            });
        });

        // Order button click handler
        document.querySelectorAll('.menu-item-order').forEach(btn => {
            btn.addEventListener('click', function() {
                const itemTitle = this.closest('.menu-item').querySelector('.menu-item-title').textContent;
                window.location.href = `tel:07706662044`;
            });
        });

        // Active nav link on scroll
        window.addEventListener('scroll', () => {
            const sections = document.querySelectorAll('section[id]');
            const navLinks = document.querySelectorAll('.nav-links a');
            
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (scrollY >= (sectionTop - 200)) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === `#${current}`) {
                    link.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>
