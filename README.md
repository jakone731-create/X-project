# X-project
Casino
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Xui X — Мгновенный доступ к цифровым продуктам</title>
    <!-- Google Fonts + Font Awesome -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: #0a0c10;
            color: #eef2ff;
            scroll-behavior: smooth;
            line-height: 1.5;
        }

        /* Кастомный скролл */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #11161f;
        }
        ::-webkit-scrollbar-thumb {
            background: #2d3e5f;
            border-radius: 8px;
        }

        /* Общие контейнеры */
        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 32px;
        }

        /* Гласс-эффекты и фон */
        .gradient-bg {
            background: radial-gradient(circle at 20% 30%, rgba(0, 180, 255, 0.08), transparent 60%),
                        radial-gradient(circle at 85% 70%, rgba(120, 80, 255, 0.06), transparent 55%);
        }

        /* Кнопки */
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 12px 28px;
            font-weight: 600;
            border-radius: 40px;
            font-size: 1rem;
            transition: all 0.25s ease;
            cursor: pointer;
            border: none;
            background: none;
            font-family: inherit;
        }
        .btn-primary {
            background: linear-gradient(105deg, #2b6ef0, #9b4dff);
            color: white;
            box-shadow: 0 4px 12px rgba(43, 110, 240, 0.3);
        }
        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 24px rgba(43, 110, 240, 0.4);
            background: linear-gradient(105deg, #3c7ef5, #a860ff);
        }
        .btn-outline {
            border: 1px solid rgba(255,255,255,0.2);
            background: rgba(10, 15, 25, 0.6);
            backdrop-filter: blur(4px);
            color: #f0f4ff;
        }
        .btn-outline:hover {
            border-color: #3b82f6;
            background: rgba(59, 130, 246, 0.15);
        }

        /* Навигация */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            flex-wrap: wrap;
            gap: 16px;
        }
        .logo {
            font-size: 1.9rem;
            font-weight: 800;
            letter-spacing: -0.02em;
            background: linear-gradient(135deg, #ffffff, #94a3f8);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .logo span {
            background: linear-gradient(135deg, #3b82f6, #c084fc);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .nav-links {
            display: flex;
            gap: 32px;
            align-items: center;
        }
        .nav-links a {
            text-decoration: none;
            color: #cbd5e6;
            font-weight: 500;
            transition: 0.2s;
        }
        .nav-links a:hover {
            color: white;
        }

        /* Hero секция */
        .hero {
            padding: 60px 0 80px 0;
        }
        .hero-grid {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            gap: 48px;
        }
        .hero-content {
            flex: 1;
            min-width: 280px;
        }
        .hero-badge {
            background: rgba(59,130,246,0.2);
            display: inline-block;
            padding: 6px 14px;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            border: 1px solid rgba(59,130,246,0.4);
            margin-bottom: 24px;
            backdrop-filter: blur(2px);
        }
        .hero-content h1 {
            font-size: 3.5rem;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 24px;
            background: linear-gradient(to right, #fff, #b9c8ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .hero-content p {
            font-size: 1.2rem;
            color: #9ca8bf;
            max-width: 540px;
            margin-bottom: 32px;
        }
        .hero-buttons {
            display: flex;
            gap: 18px;
            flex-wrap: wrap;
        }
        .hero-visual {
            flex: 1;
            background: rgba(18, 25, 45, 0.6);
            border-radius: 42px;
            padding: 20px;
            backdrop-filter: blur(8px);
            border: 1px solid rgba(255,255,255,0.05);
            box-shadow: 0 25px 40px -20px rgba(0,0,0,0.5);
        }
        .mock-card {
            background: #0f172ae0;
            border-radius: 28px;
            padding: 24px;
            backdrop-filter: blur(4px);
            border: 1px solid rgba(59,130,246,0.3);
        }
        .mock-item {
            display: flex;
            align-items: center;
            gap: 16px;
            background: #11161f;
            padding: 14px 18px;
            border-radius: 20px;
            margin-bottom: 12px;
        }
        .mock-icon {
            width: 48px;
            height: 48px;
            background: linear-gradient(145deg, #1e2a3e, #0f172a);
            border-radius: 24px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.6rem;
        }
        .mock-text h4 {
            font-weight: 600;
        }
        .mock-text p {
            font-size: 0.8rem;
            color: #8b9bb5;
        }

        /* Секция фич */
        .section {
            padding: 80px 0;
        }
        .section-title {
            text-align: center;
            font-size: 2.4rem;
            font-weight: 700;
            margin-bottom: 16px;
        }
        .section-sub {
            text-align: center;
            color: #8f9bb5;
            max-width: 680px;
            margin: 0 auto 56px auto;
        }
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 32px;
        }
        .feature-card {
            background: rgba(15, 23, 42, 0.6);
            backdrop-filter: blur(4px);
            border-radius: 32px;
            padding: 32px 24px;
            border: 1px solid rgba(255,255,255,0.05);
            transition: all 0.25s;
        }
        .feature-card:hover {
            border-color: rgba(59,130,246,0.4);
            transform: translateY(-4px);
            background: rgba(20, 30, 55, 0.7);
        }
        .feature-icon {
            font-size: 2.6rem;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #3b82f6, #a855f7);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 12px;
        }
        .feature-card p {
            color: #b9c2d4;
        }

        /* Карточки товаров */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 28px;
            margin-top: 20px;
        }
        .product-card {
            background: #0f172a;
            border-radius: 28px;
            overflow: hidden;
            border: 1px solid #1e2a3e;
            transition: 0.2s;
        }
        .product-card:hover {
            border-color: #3b82f6;
            transform: scale(1.02);
        }
        .product-img {
            height: 170px;
            background: linear-gradient(135deg, #121a2c, #091021);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
        }
        .product-info {
            padding: 22px;
        }
        .product-info h3 {
            font-size: 1.4rem;
            margin-bottom: 8px;
        }
        .price {
            font-size: 1.7rem;
            font-weight: 800;
            margin: 12px 0;
            color: #60a5fa;
        }
        .price small {
            font-size: 0.9rem;
            font-weight: 400;
            color: #8f9bb5;
        }
        .btn-small {
            width: 100%;
            justify-content: center;
            padding: 12px;
            margin-top: 8px;
            background: #1e293b;
            color: white;
            border-radius: 60px;
            font-weight: 600;
            transition: 0.2s;
            border: none;
            cursor: pointer;
        }
        .btn-small:hover {
            background: #2b6ef0;
        }

        /* Тарифы / подписки */
        .pricing-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 32px;
            margin-top: 30px;
        }
        .pricing-card {
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(8px);
            border-radius: 36px;
            padding: 32px;
            width: 300px;
            border: 1px solid rgba(59,130,246,0.2);
            transition: 0.2s;
        }
        .pricing-card.popular {
            border: 1px solid #3b82f6;
            background: rgba(30, 58, 100, 0.4);
            box-shadow: 0 10px 25px -5px rgba(59,130,246,0.2);
        }
        .pricing-card h3 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        .pricing-price {
            font-size: 2.5rem;
            font-weight: 800;
            margin: 20px 0;
        }
        .pricing-price span {
            font-size: 1rem;
            font-weight: 400;
        }
        .pricing-features {
            list-style: none;
            margin: 20px 0;
        }
        .pricing-features li {
            margin: 12px 0;
            display: flex;
            gap: 10px;
            align-items: center;
        }
        .pricing-features i {
            color: #3b82f6;
            width: 22px;
        }

        /* CTA */
        .cta-section {
            background: linear-gradient(120deg, #0b1120, #0f172ad9);
            border-radius: 56px;
            margin: 40px 0 60px;
            padding: 64px 48px;
            text-align: center;
            border: 1px solid rgba(59,130,246,0.3);
        }
        .cta-section h2 {
            font-size: 2.2rem;
            margin-bottom: 20px;
        }

        /* Футер */
        footer {
            border-top: 1px solid #1e293b;
            padding: 48px 0 32px;
            margin-top: 40px;
        }
        .footer-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 32px;
        }
        .footer-links {
            display: flex;
            gap: 48px;
            flex-wrap: wrap;
        }
        .footer-col a {
            display: block;
            color: #9aa4bf;
            text-decoration: none;
            margin: 12px 0;
            transition: 0.2s;
        }
        .footer-col a:hover {
            color: white;
        }
        .copyright {
            text-align: center;
            margin-top: 48px;
            color: #6a748b;
            font-size: 0.85rem;
        }

        @media (max-width: 780px) {
            .container {
                padding: 0 24px;
            }
            .hero-content h1 {
                font-size: 2.5rem;
            }
            .navbar {
                flex-direction: column;
            }
            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
            }
            .cta-section {
                padding: 40px 24px;
            }
        }
    </style>
</head>
<body class="gradient-bg">
    <div class="container">
        <!-- Навигация -->
        <nav class="navbar">
            <div class="logo">XUI <span>X</span></div>
            <div class="nav-links">
                <a href="#">Главная</a>
                <a href="#features">Возможности</a>
                <a href="#products">Продукты</a>
                <a href="#pricing">Тарифы</a>
                <a href="#" class="btn btn-outline" style="padding: 8px 22px;">Войти</a>
                <a href="#" class="btn btn-primary" style="padding: 8px 22px;">Начать</a>
            </div>
        </nav>

        <!-- Hero -->
        <section class="hero">
            <div class="hero-grid">
                <div class="hero-content">
                    <div class="hero-badge">
                        <i class="fas fa-bolt" style="margin-right: 6px;"></i> Мгновенный доступ
                    </div>
                    <h1>Получай всё<br>моментально с Xui X</h1>
                    <p>Цифровые продукты, подписки и инструменты в одном месте. Никакой бюрократии — только быстрый старт.</p>
                    <div class="hero-buttons">
                        <button class="btn btn-primary" id="ctaHeroBtn"><i class="fab fa-telegram"></i> Получить доступ</button>
                        <button class="btn btn-outline"><i class="fas fa-play"></i> Смотреть демо</button>
                    </div>
                </div>
                <div class="hero-visual">
                    <div class="mock-card">
                        <div class="mock-item">
                            <div class="mock-icon"><i class="fab fa-spotify"></i></div>
                            <div class="mock-text"><h4>Spotify Premium</h4><p>Готов к активации</p></div>
                            <i class="fas fa-chevron-right" style="margin-left: auto; color:#3b82f6;"></i>
                        </div>
                        <div class="mock-item">
                            <div class="mock-icon"><i class="fab fa-figma"></i></div>
                            <div class="mock-text"><h4>Figma Pro</h4><p>Мгновенный код</p></div>
                            <i class="fas fa-chevron-right" style="margin-left: auto; color:#3b82f6;"></i>
                        </div>
                        <div class="mock-item">
                            <div class="mock-icon"><i class="fas fa-database"></i></div>
                            <div class="mock-text"><h4>VPN + Cloud</h4><p>Безлимитный трафик</p></div>
                            <i class="fas fa-chevron-right" style="margin-left: auto; color:#3b82f6;"></i>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Возможности -->
        <section id="features">
            <div class="section-title">Почему выбирают Xui X</div>
            <div class="section-sub">Скорость, безопасность и полная автоматизация для цифровых потребностей</div>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-bolt"></i></div>
                    <h3>Мгновенная выдача</h3>
                    <p>После оплаты товар или подписка приходят в личный кабинет за секунды. Без ожидания.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-shield-alt"></i></div>
                    <h3>Гарантия качества</h3>
                    <p>Все ключи и аккаунты проходят проверку. Замена в случае проблем — 24/7 поддержка.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-globe"></i></div>
                    <h3>Доступность 24/7</h3>
                    <p>Автоматизированная платформа работает круглосуточно, получай товары в любое время.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-chart-line"></i></div>
                    <h3>Бонусная система</h3>
                    <p>Кешбэк до 15% на каждую покупку, эксклюзивные предложения для постоянных клиентов.</p>
                </div>
            </div>
        </section>

        <!-- Популярные продукты (как Xui X стиль) -->
        <section id="products">
            <div class="section-title">🔥 Популярные товары</div>
            <div class="section-sub">Цифровые продукты на любой вкус — от стриминга до софта</div>
            <div class="products-grid">
                <div class="product-card">
                    <div class="product-img"><i class="fab fa-spotify" style="font-size: 4rem; color:#1DB954;"></i></div>
                    <div class="product-info">
                        <h3>Spotify Premium 1 год</h3>
                        <p>Личный аккаунт, без рекламы</p>
                        <div class="price">1 290₽ <small>/ год</small></div>
                        <button class="btn-small get-product" data-product="Spotify Premium">Купить сейчас</button>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-img"><i class="fab fa-windows" style="font-size: 4rem; color:#00a4ef;"></i></div>
                    <div class="product-info">
                        <h3>Windows 11 Pro</h3>
                        <p>Лицензионный ключ</p>
                        <div class="price">2 490₽ <small>/ навсегда</small></div>
                        <button class="btn-small get-product" data-product="Windows 11 Pro">Купить сейчас</button>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-img"><i class="fas fa-dice-d6" style="font-size: 4rem; color:#facc15;"></i></div>
                    <div class="product-info">
                        <h3>Canva Pro 6 мес</h3>
                        <p>Дизайн без ограничений</p>
                        <div class="price">890₽ <small>/ 6 мес</small></div>
                        <button class="btn-small get-product" data-product="Canva Pro">Купить сейчас</button>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-img"><i class="fas fa-vr-cardboard" style="font-size: 4rem; color:#a855f7;"></i></div>
                    <div class="product-info">
                        <h3>ChatGPT Plus</h3>
                        <p>GPT-4 без очередей</p>
                        <div class="price">1 590₽ <small>/ мес</small></div>
                        <button class="btn-small get-product" data-product="ChatGPT Plus">Купить сейчас</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Тарифы (подписки на сервис) -->
        <section id="pricing">
            <div class="section-title">Выберите свой план</div>
            <div class="section-sub">Для частых покупок и максимальной выгоды</div>
            <div class="pricing-grid">
                <div class="pricing-card">
                    <h3>Старт</h3>
                    <div class="pricing-price">0₽ <span>/мес</span></div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check-circle"></i> Доступ к базовым товарам</li>
                        <li><i class="fas fa-check-circle"></i> Стандартная поддержка</li>
                        <li><i class="fas fa-check-circle"></i> Кешбэк 2%</li>
                    </ul>
                    <button class="btn btn-outline" style="width:100%;">Выбрать</button>
                </div>
                <div class="pricing-card popular">
                    <h3>PRO</h3>
                    <div class="pricing-price">590₽ <span>/мес</span></div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check-circle"></i> Все товары со скидкой -15%</li>
                        <li><i class="fas fa-check-circle"></i> Приоритетная поддержка 24/7</li>
                        <li><i class="fas fa-check-circle"></i> Ранний доступ к новинкам</li>
                        <li><i class="fas fa-check-circle"></i> Кешбэк 10% + бонус 500₽</li>
                    </ul>
                    <button class="btn btn-primary" style="width:100%;" id="proPlanBtn">Оформить PRO</button>
                </div>
                <div class="pricing-card">
                    <h3>Бизнес</h3>
                    <div class="pricing-price">1 490₽ <span>/мес</span></div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check-circle"></i> API доступ + массовые заказы</li>
                        <li><i class="fas fa-check-circle"></i> Персональный менеджер</li>
                        <li><i class="fas fa-check-circle"></i> Индивидуальные условия</li>
                    </ul>
                    <button class="btn btn-outline" style="width:100%;">Связаться</button>
                </div>
            </div>
        </section>

        <!-- CTA + призыв -->
        <div class="cta-section">
            <h2>Готов получить X?</h2>
            <p style="max-width: 550px; margin: 0 auto 28px auto; color:#cbd5e1;">Более 50 000 пользователей уже используют Xui X для мгновенного доступа к цифровым продуктам.</p>
            <button class="btn btn-primary" id="finalCtaBtn"><i class="fas fa-rocket"></i> Начать сейчас — это бесплатно</button>
        </div>

        <!-- Футер -->
        <footer>
            <div class="footer-grid">
                <div class="logo" style="font-size: 1.6rem;">XUI <span>X</span></div>
                <div class="footer-links">
                    <div class="footer-col">
                        <strong>Сервисы</strong>
                        <a href="#">Каталог товаров</a>
                        <a href="#">Подписки</a>
                        <a href="#">Акции</a>
                    </div>
                    <div class="footer-col">
                        <strong>Помощь</strong>
                        <a href="#">FAQ</a>
                        <a href="#">Поддержка</a>
                        <a href="#">Обмен/возврат</a>
                    </div>
                    <div class="footer-col">
                        <strong>Правовая</strong>
                        <a href="#">Политика конфиденциальности</a>
                        <a href="#">Пользовательское соглашение</a>
                    </div>
                </div>
                <div class="footer-social">
                    <i class="fab fa-telegram" style="font-size: 1.8rem; margin-right: 16px; opacity:0.8; cursor:pointer;"></i>
                    <i class="fab fa-discord" style="font-size: 1.8rem; opacity:0.8; cursor:pointer;"></i>
                    <i class="fab fa-x-twitter" style="font-size: 1.8rem; margin-left: 16px; opacity:0.8; cursor:pointer;"></i>
                </div>
            </div>
            <div class="copyright">
                © 2025 Xui X — Мгновенный доступ к цифровому миру. Все права защищены.
            </div>
        </footer>
    </div>

    <!-- Интерактив: уведомления при нажатии на кнопки -->
    <script>
        (function() {
            // Создаём контейнер для тост-уведомлений
            const toastContainer = document.createElement('div');
            toastContainer.style.position = 'fixed';
            toastContainer.style.bottom = '24px';
            toastContainer.style.right = '24px';
            toastContainer.style.zIndex = '9999';
            toastContainer.style.display = 'flex';
            toastContainer.style.flexDirection = 'column';
            toastContainer.style.gap = '12px';
            document.body.appendChild(toastContainer);

            function showToast(message, type = 'success') {
                const toast = document.createElement('div');
                toast.style.background = type === 'success' ? '#0f172ad9' : '#2d1f2cd9';
                toast.style.backdropFilter = 'blur(12px)';
                toast.style.borderLeft = type === 'success' ? '4px solid #2b6ef0' : '4px solid #f97316';
                toast.style.borderRadius = '20px';
                toast.style.padding = '14px 20px';
                toast.style.color = '#fff';
                toast.style.fontWeight = '500';
                toast.style.fontSize = '0.9rem';
                toast.style.boxShadow = '0 12px 28px rgba(0,0,0,0.3)';
                toast.style.minWidth = '240px';
                toast.style.maxWidth = '320px';
                toast.innerHTML = `<i class="fas ${type === 'success' ? 'fa-check-circle' : 'fa-info-circle'}" style="margin-right: 10px; color: #60a5fa;"></i> ${message}`;
                toastContainer.appendChild(toast);
                setTimeout(() => {
                    toast.style.opacity = '0';
                    toast.style.transition = 'opacity 0.3s';
                    setTimeout(() => toast.remove(), 350);
                }, 2800);
            }

            // Обработка всех кнопок "Купить сейчас" у товаров
            const productBtns = document.querySelectorAll('.get-product');
            productBtns.forEach(btn => {
                btn.addEventListener('click', (e) => {
                    e.preventDefault();
                    const productName = btn.getAttribute('data-product') || 'товар';
                    showToast(`✅ ${productName} добавлен в корзину. Переход к оформлению...`, 'success');
                });
            });

            // Кнопка "Получить доступ" в Hero
            const heroBtn = document.getElementById('ctaHeroBtn');
            if (heroBtn) {
                heroBtn.addEventListener('click', () => {
                    showToast('🚀 Переход к регистрации. Добро пожаловать в Xui X!', 'success');
                });
            }

            // Кнопка PRO план
            const proBtn = document.getElementById('proPlanBtn');
            if (proBtn) {
                proBtn.addEventListener('click', () => {
                    showToast('✨ Вы выбрали PRO план. Перенаправление на страницу оплаты...', 'success');
                });
            }

            // Финальная CTA кнопка
            const finalCta = document.getElementById('finalCtaBtn');
            if (finalCta) {
                finalCta.addEventListener('click', () => {
                    showToast('🎉 Спасибо! Регистрация займет 1 минуту. Начните сейчас', 'success');
                });
            }

            // Добавим обработку на кнопки выбора тарифов "Выбрать" / "Связаться"
            const allPricingBtns = document.querySelectorAll('.pricing-card .btn-outline, .pricing-card .btn-primary');
            allPricingBtns.forEach(btn => {
                if (btn.id !== 'proPlanBtn') {
                    btn.addEventListener('click', (e) => {
                        e.preventDefault();
                        const cardTitle = btn.closest('.pricing-card')?.querySelector('h3')?.innerText || 'тариф';
                        if (cardTitle.includes('Бизнес')) {
                            showToast(`📞 Связь с отделом продаж: запрос на тариф "${cardTitle}" отправлен.`, 'info');
                        } else {
                            showToast(`💳 Выбран тариф "${cardTitle}". Детали в личном кабинете.`, 'success');
                        }
                    });
                }
            });

            // Кнопка "Смотреть демо"
            const demoBtn = document.querySelector('.hero-buttons .btn-outline');
            if (demoBtn) {
                demoBtn.addEventListener('click', () => {
                    showToast('🎬 Демо-ролик: как работает Xui X — скоро появится в вашем профиле', 'info');
                });
            }

            // Социальные иконки в футере
            const socialIcons = document.querySelectorAll('.footer-social i');
            socialIcons.forEach(icon => {
                icon.addEventListener('click', () => {
                    showToast('🌐 Мы в соцсетях: следите за новостями и эксклюзивами!', 'info');
                });
            });
        })();
    </script>
</body>
</html>
