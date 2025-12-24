<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Кафе "Бегемот"</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800&family=Patrick+Hand&display=swap" rel="stylesheet">
    <style>
        /* ---------  ОСНОВНЫЕ СТИЛИ  --------- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Nunito', sans-serif;
            background-color: #FFF9F0;
            color: #5D4037;
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* ---------  ШАПКА  --------- */
        header {
            background-color: #8B6B4D;
            color: #FFF9F0;
            padding: 1.2rem 0;
            box-shadow: 0 4px 15px rgba(139, 107, 77, 0.2);
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-icon {
            font-size: 3rem;
            color: #FF9800;
            filter: drop-shadow(0 0 5px rgba(255, 152, 0, 0.5));
        }
        
        .logo-text h1 {
            font-family: 'Patrick Hand', cursive;
            font-size: 2.2rem;
            margin-bottom: 5px;
            letter-spacing: 1px;
            color: #FFE0B2;
        }
        
        .logo-text p {
            font-size: 0.9rem;
            opacity: 0.9;
            letter-spacing: 1.5px;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 30px;
        }
        
        nav ul li a {
            color: #FFF9F0;
            text-decoration: none;
            font-size: 1.1rem;
            padding: 10px 18px;
            border-radius: 30px;
            transition: all 0.3s ease;
            position: relative;
            font-weight: 600;
        }
        
        nav ul li a:hover {
            background-color: rgba(255, 152, 0, 0.2);
            transform: translateY(-2px);
        }
        
        nav ul li a.active {
            background-color: #FF9800;
            color: #5D4037;
            font-weight: 700;
            box-shadow: 0 4px 10px rgba(255, 152, 0, 0.3);
        }
        
        /* ---------  ОСНОВНОЙ КОНТЕНТ  --------- */
        .main-content {
            padding: 50px 0;
            min-height: calc(100vh - 220px);
        }
        
        .tab-content {
            display: none;
            animation: fadeIn 0.6s ease;
        }
        
        .tab-content.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* ---------  ГЛАВНАЯ СТРАНИЦА  --------- */
        .hero {
            background: linear-gradient(rgba(139, 107, 77, 0.85), rgba(139, 107, 77, 0.9)), 
                        url('https://images.unsplash.com/photo-1554118811-1e0d58224f24?ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80');
            background-size: cover;
            background-position: center;
            color: #FFF9F0;
            padding: 100px 0;
            text-align: center;
            border-radius: 20px;
            margin-bottom: 50px;
            box-shadow: 0 15px 30px rgba(139, 107, 77, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg width="100" height="100" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><path d="M10,10 Q50,5 90,10 Q95,50 90,90 Q50,95 10,90 Q5,50 10,10 Z" fill="none" stroke="%23FF9800" stroke-width="0.5"/></svg>');
            opacity: 0.1;
        }
        
        .hero h2 {
            font-family: 'Patrick Hand', cursive;
            font-size: 3.5rem;
            margin-bottom: 25px;
            color: #FFE0B2;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .hero p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto 40px;
            opacity: 0.95;
            line-height: 1.8;
        }
        
        .btn {
            display: inline-block;
            background-color: #FF9800;
            color: #5D4037;
            padding: 15px 35px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(255, 152, 0, 0.3);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(255, 152, 0, 0.4);
            background-color: #FFB74D;
        }
        
        .btn:active {
            transform: translateY(-2px);
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 60px;
        }
        
        .feature-card {
            background: #FFF;
            padding: 35px 30px;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(139, 107, 77, 0.08);
            text-align: center;
            transition: all 0.4s ease;
            border-top: 5px solid #FF9800;
            position: relative;
            overflow: hidden;
        }
        
        .feature-card:hover {
            transform: translateY(-12px);
            box-shadow: 0 15px 30px rgba(139, 107, 77, 0.15);
        }
        
        .feature-card i {
            font-size: 2.8rem;
            margin-bottom: 25px;
            color: #8B6B4D;
        }
        
        .feature-card h3 {
            font-family: 'Patrick Hand', cursive;
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: #5D4037;
        }
        
        .feature-card p {
            color: #8B6B4D;
            font-size: 1rem;
        }
        
        /* ---------  МЕНЮ  --------- */
        .menu-header {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .menu-header h2 {
            font-family: 'Patrick Hand', cursive;
            font-size: 3rem;
            color: #5D4037;
            margin-bottom: 15px;
        }
        
        .menu-header p {
            color: #8B6B4D;
            max-width: 700px;
            margin: 0 auto;
            font-size: 1.1rem;
        }
        
        .menu-category {
            margin-bottom: 70px;
        }
        
        .category-title {
            font-family: 'Patrick Hand', cursive;
            font-size: 2.2rem;
            color: #8B6B4D;
            border-bottom: 3px dotted #FF9800;
            padding-bottom: 12px;
            margin-bottom: 35px;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .dishes-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }
        
        .dish-card {
            background: #FFF;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 25px rgba(139, 107, 77, 0.08);
            transition: all 0.4s ease;
            display: flex;
            flex-direction: column;
            height: 100%;
            position: relative;
        }
        
        .dish-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(139, 107, 77, 0.15);
        }
        
        .dish-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background-color: #FF9800;
        }
        
        .dish-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            display: block;
            transition: transform 0.5s ease;
        }
        
        .dish-card:hover .dish-img {
            transform: scale(1.05);
        }
        
        .dish-info {
            padding: 25px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }
        
        .dish-name-price {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .dish-name {
            font-family: 'Patrick Hand', cursive;
            font-size: 1.6rem;
            font-weight: 700;
            color: #5D4037;
        }
        
        .dish-price {
            font-size: 1.5rem;
            font-weight: 800;
            color: #FF9800;
            background: #FFF3E0;
            padding: 5px 15px;
            border-radius: 20px;
        }
        
        .dish-description {
            color: #8B6B4D;
            font-size: 1rem;
            margin-bottom: 20px;
            flex-grow: 1;
        }
        
        .dish-ingredients {
            font-size: 0.9rem;
            color: #A1887F;
            font-style: italic;
            border-top: 1px dashed #D7CCC8;
            padding-top: 15px;
        }
        
        /* ---------  О НАС  --------- */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
            margin-bottom: 60px;
        }
        
        .about-text h2 {
            font-family: 'Patrick Hand', cursive;
            font-size: 2.5rem;
            color: #5D4037;
            margin-bottom: 25px;
        }
        
        .about-text p {
            color: #8B6B4D;
            font-size: 1.1rem;
            margin-bottom: 20px;
            line-height: 1.8;
        }
        
        .about-image img {
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(139, 107, 77, 0.15);
        }
        
        /* ---------  ГАЛЕРЕЯ  --------- */

        /* ---------  ФУТЕР  --------- */
        footer {
            background-color: #8B6B4D;
            color: #FFF9F0;
            padding: 50px 0 25px;
            margin-top: 50px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-section h3 {
            font-family: 'Patrick Hand', cursive;
            font-size: 1.6rem;
            margin-bottom: 25px;
            color: #FFE0B2;
        }
        
        .footer-section p, .footer-section a {
            color: #FFE0B2;
            margin-bottom: 12px;
            display: block;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-section a:hover {
            color: #FF9800;
        }
        
        .footer-section i {
            margin-right: 10px;
            width: 20px;
            text-align: center;
            color: #FF9800;
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: #FF9800;
            border-radius: 50%;
            color: #5D4037;
            font-size: 1.2rem;
            transition: all 0.3s ease;
        }
        
        .social-icons a:hover {
            transform: translateY(-5px);
            background-color: #FFB74D;
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 25px;
            border-top: 1px solid #A1887F;
            color: #D7CCC8;
            font-size: 0.9rem;
        }
        
        /* ---------  АДАПТИВНОСТЬ  --------- */
        @media (max-width: 992px) {
            .hero h2 {
                font-size: 2.8rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .dishes-list {
                grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 20px;
                justify-content: center;
                flex-wrap: wrap;
            }
            
            nav ul li {
                margin: 5px 10px;
            }
            
            .hero {
                padding: 70px 0;
            }
            
            .hero h2 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .features {
                grid-template-columns: 1fr;
            }
            
            .dishes-list {
                grid-template-columns: 1fr;
            }
            
            .menu-header h2 {
                font-size: 2.5rem;
            }
        }
        
        @media (max-width: 480px) {
            .logo {
                flex-direction: column;
                text-align: center;
                gap: 10px;
            }
            
            .logo-text h1 {
                font-size: 1.8rem;
            }
            
            .hero h2 {
                font-size: 1.8rem;
            }
            
            .btn {
                padding: 12px 25px;
                font-size: 1rem;
            }
            
            .category-title {
                font-size: 1.8rem;
            }
        }
        
        /* ---------  ДОПОЛНИТЕЛЬНЫЕ ЭЛЕМЕНТЫ  --------- */
        .special-offer {
            background-color: #FFF3E0;
            border-radius: 15px;
            padding: 30px;
            margin-top: 60px;
            text-align: center;
            border: 3px dashed #FF9800;
        }
        
        .special-offer h3 {
            font-family: 'Patrick Hand', cursive;
            font-size: 2rem;
            color: #5D4037;
            margin-bottom: 15px;
        }
        
        .special-offer p {
            color: #8B6B4D;
            font-size: 1.1rem;
            margin-bottom: 20px;
        }
        
        .hours {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .hour-item {
            background-color: #FFF;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(139, 107, 77, 0.08);
        }
        
        .hour-item h4 {
            color: #5D4037;
            margin-bottom: 10px;
        }
        
        .hour-item p {
            color: #8B6B4D;
            font-weight: 600;
        }
    </style>
</head>
<body>
    <!-- =====================  ШАПКА  ===================== -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">🦛</div>
                    <div class="logo-text">
                        <h1>Бегемот</h1>
                        <p>Уютное кафе с домашней кухней</p>
                    </div>
                </div>
                <nav>
                    <ul>
                        <li><a href="#" class="tab-link active" data-tab="home">Главная</a></li>
                        <li><a href="#" class="tab-link" data-tab="menu">Меню</a></li>
                        <li><a href="#" class="tab-link" data-tab="about">О нас</a></li>
                        <li><a href="#" class="tab-link" data-tab="contact">Контакты</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- =================  ОСНОВНОЙ КОНТЕНТ  ================= -->
    <div class="main-content">
        <div class="container">
            <!-- ................  ГЛАВНАЯ  ................ -->
            <div id="home" class="tab-content active">
                <div class="hero">
                    <h2>Добро пожаловать в кафе "Бегемот"!</h2>
                    <p>Место, где царит уютная атмосфера, пахнет домашней выпечкой и готовят с любовью. Приходите к нам за вкусной едой, хорошим кофе и отличным настроением!</p>
                    <a href="#" class="btn tab-link" data-tab="menu">Посмотреть меню</a>
                </div>

                <div class="features">
                    <div class="feature-card">
                        <i class="fas fa-coffee"></i>
                        <h3>Кофе на любой вкус</h3>
                        <p>Свежеобжаренный кофе, капучино, латте и авторские напитки от нашего бариста.</p>
                    </div>
                    <div class="feature-card">
                        <i class="fas fa-home"></i>
                        <h3>Домашняя кухня</h3>
                        <p>Все блюда готовятся на нашей кухне из свежих продуктов по домашним рецептам.</p>
                    </div>
                    <div class="feature-card">
                        <i class="fas fa-cookie-bite"></i>
                        <h3>Своя выпечка</h3>
                        <p>Пироги, торты, печенье и другая выпечка готовятся ежедневно в нашей кондитерской.</p>
                    </div>
                </div>
                
                <div class="special-offer">
                    <h3>Специальное предложение!</h3>
                    <p>Каждый день с 8:00 до 11:00 у нас действует "Утренний сет": кофе + выпечка всего за 250 рублей!</p>
                    <a href="#" class="btn tab-link" data-tab="contact">Узнать подробности</a>
                </div>
            </div>

            <!-- ................  МЕНЮ  ................ -->
            <div id="menu" class="tab-content">
                <div class="menu-header">
                    <h2>Наше меню</h2>
                    <p>Вкусные блюда, приготовленные с любовью и заботой о наших гостях.</p>
                </div>

                <!-- ::::::::::::::  ЗАВТРАКИ  :::::::::::::: -->
                <div class="menu-category">
                    <h3 class="category-title"><i class="fas fa-egg"></i> Завтраки</h3>
                    <div class="dishes-list">
                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Сырники с ягодами</div>
                                    <div class="dish-price">320 ₽</div>
                                </div>
                                <p class="dish-description">Нежные творожные сырники со сметаной и свежими ягодами.</p>
                                <p class="dish-ingredients">Творог, яйца, мука, сметана, ягоды (сезонные)</p>
                            </div>
                        </div>

                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Омлет с овощами</div>
                                    <div class="dish-price">280 ₽</div>
                                </div>
                                <p class="dish-description">Пышный омлет с томатами, болгарским перцем и зеленью.</p>
                                <p class="dish-ingredients">Яйца, молоко, помидоры, перец, зелень, сыр</p>
                            </div>
                        </div>

                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Овсяная каша</div>
                                    <div class="dish-price">240 ₽</div>
                                </div>
                                <p class="dish-description">Овсяная каша на молоке с медом, орехами и сухофруктами.</p>
                                <p class="dish-ingredients">Овсяные хлопья, молоко, мед, грецкие орехи, изюм, курага</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- ::::::::::::::  ОСНОВНЫЕ БЛЮДА  :::::::::::::: -->
                <div class="menu-category">
                    <h3 class="category-title"><i class="fas fa-utensils"></i> Основные блюда</h3>
                    <div class="dishes-list">
                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Домашние котлеты</div>
                                    <div class="dish-price">420 ₽</div>
                                </div>
                                <p class="dish-description">Котлеты из говядины и свинины с картофельным пюре и овощами.</p>
                                <p class="dish-ingredients">Говядина, свинина, лук, картофель, морковь, горошек</p>
                            </div>
                        </div>

                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Курица в сливочном соусе</div>
                                    <div class="dish-price">380 ₽</div>
                                </div>
                                <p class="dish-description">Филе курицы в нежном сливочном соусе с грибами и рисом.</p>
                                <p class="dish-ingredients">Куриное филе, сливки, шампиньоны, рис, лук, специи</p>
                            </div>
                        </div>

                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Салат Цезарь</div>
                                    <div class="dish-price">350 ₽</div>
                                </div>
                                <p class="dish-description">Классический салат с курицей, сыром пармезан и соусом цезарь.</p>
                                <p class="dish-ingredients">Курица, салат айсберг, помидоры черри, пармезан, сухарики, соус</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- ::::::::::::::  ВЫПЕЧКА И ДЕСЕРТЫ  :::::::::::::: -->
                <div class="menu-category">
                    <h3 class="category-title"><i class="fas fa-birthday-cake"></i> Выпечка и десерты</h3>
                    <div class="dishes-list">
                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Яблочная шарлотка</div>
                                    <div class="dish-price">180 ₽</div>
                                </div>
                                <p class="dish-description">Домашняя шарлотка с яблоками и корицей, подается теплой.</p>
                                <p class="dish-ingredients">Яблоки, мука, яйца, сахар, корица, сливочное масло</p>
                            </div>
                        </div>

                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Чизкейк Нью-Йорк</div>
                                    <div class="dish-price">280 ₽</div>
                                </div>
                                <p class="dish-description">Классический чизкейк с нежной творожной основой и ягодным соусом.</p>
                                <p class="dish-ingredients">Творожный сыр, сливки, печенье, яйца, ягодный соус</p>
                            </div>
                        </div>

                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Круассан с шоколадом</div>
                                    <div class="dish-price">150 ₽</div>
                                </div>
                                <p class="dish-description">Слоеный круассан с начинкой из темного шоколада.</p>
                                <p class="dish-ingredients">Слоеное тесто, темный шоколад, яйцо для смазки</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- ::::::::::::::  НАПИТКИ  :::::::::::::: -->
                <div class="menu-category">
                    <h3 class="category-title"><i class="fas fa-coffee"></i> Напитки</h3>
                    <div class="dishes-list">
                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Капучино</div>
                                    <div class="dish-price">220 ₽</div>
                                </div>
                                <p class="dish-description">Классический капучино с молочной пенкой.</p>
                            </div>
                        </div>

                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Латте</div>
                                    <div class="dish-price">240 ₽</div>
                                </div>
                                <p class="dish-description">Нежный латте с возможностью выбора сиропа (ваниль, карамель, кокос).</p>
                            </div>
                        </div>

                        <div class="dish-card">
                            <div class="dish-info">
                                <div class="dish-name-price">
                                    <div class="dish-name">Молочный коктейль</div>
                                    <div class="dish-price">280 ₽</div>
                                </div>
                                <p class="dish-description">Густой молочный коктейль со вкусом клубники, банана или шоколада.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- ................  О НАС  ................ -->
            <div id="about" class="tab-content">
                <div class="menu-header">
                    <h2>О нашем кафе</h2>
                    <p>История создания и философия "Бегемота"</p>
                </div>
                
                <div class="about-content">
                    <div class="about-text">
                        <h2>Добро пожаловать в нашу большую семью!</h2>
                        <p>Кафе "Бегемот" было основано в 2015 году с простой идеей: создать место, где каждый гость будет чувствовать себя как дома. Мы верим, что хорошая еда — это не просто утоление голода, а целый ритуал, который должен приносить удовольствие.</p>
                        <p>Название "Бегемот" было выбрано не случайно. Как и эти удивительные животные, мы — большие, добрые и гостеприимные. Наша миссия — создать атмосферу тепла и уюта, где можно отдохнуть от городской суеты.</p>
                        <p>Все блюда в нашем меню готовятся из свежих, качественных продуктов. Мы сотрудничаем с местными фермерами и поставщиками, чтобы обеспечить наилучшее качество. Наша выпечка готовится ежедневно, а кофе обжаривается специально для нас.</p>
                        <p>Приходите к нам на завтрак, обед или просто на чашечку кофе с десертом. Мы ждем вас!</p>
                    </div>
                    <div class="about-image">
                        <img src="https://images.unsplash.com/photo-1559925393-8be0ec4767c8?auto=format&fit=crop&w=800&q=80" alt="Интерьер кафе" loading="lazy">
                    </div>
                </div>
                
                <div class="features">
                    <div class="feature-card">
                        <i class="fas fa-heart"></i>
                        <h3>Готовим с любовью</h3>
                        <p>Каждое блюдо готовится с заботой и вниманием к деталям.</p>
                    </div>
                    
                    <div class="feature-card">
                        <i class="fas fa-leaf"></i>
                        <h3>Свежие продукты</h3>
                        <p>Используем только свежие, качественные ингредиенты.</p>
                    </div>
                    
                    <div class="feature-card">
                        <i class="fas fa-users"></i>
                        <h3>Для всей семьи</h3>
                        <p>У нас есть детское меню и игровая зона для маленьких гостей.</p>
                    </div>
                </div>
            </div>

            <!-- ................  ГАЛЕРЕЯ  ................ -->


            <!-- ................  КОНТАКТЫ  ................ -->
            <div id="contact" class="tab-content">
                <div class="menu-header">
                    <h2>Контакты</h2>
                    <p>Приходите в гости или свяжитесь с нами</p>
                </div>
                
                <div class="features">
                    <div class="feature-card">
                        <i class="fas fa-map-marker-alt"></i>
                        <h3>Адрес</h3>
                        <p>Москва, ул. Пушкина, д. Колотушкина<br>м. Чистые пруды</p>
                    </div>
                    
                    <div class="feature-card">
                        <i class="fas fa-phone"></i>
                        <h3>Телефон</h3>
                        <p>+7 (XXX) XXX-XX-XX<br>
                        Для бронирования: +7 (XXX) XXX-XX-XX</p>
                    </div>
                    
                    <div class="feature-card">
                        <i class="fas fa-envelope"></i>
                        <h3>Электронная почта</h3>
                        <p>info@begemot-cafe.ru<br>
                        booking@begemot-cafe.ru</p>
                    </div>
                </div>
                
                <div class="hours">
                    <div class="hour-item">
                        <h4>Понедельник - Пятница</h4>
                        <p>8:00 - 23:00</p>
                    </div>
                    <div class="hour-item">
                        <h4>Суббота</h4>
                        <p>9:00 - 00:00</p>
                    </div>
                    <div class="hour-item">
                        <h4>Воскресенье</h4>
                        <p>9:00 - 22:00</p>
                    </div>
                    <div class="hour-item">
                        <h4>Завтраки</h4>
                        <p>8:00 - 12:00 ежедневно</p>
                    </div>
                </div>
                
                <div class="special-offer" style="margin-top: 50px;">
                    <h3>Хотите забронировать столик?</h3>
                    <p>Позвоните нам по телефону +7 (XXX) XXX-XX-XX или оставьте заявку на сайте. Мы перезвоним вам в течение 15 минут!</p>
                    <button class="btn" onclick="alert('Функционал бронирования находится в разработке. Пожалуйста, позвоните нам по телефону +7 (XXX) XXX-XX-XX')">Забронировать столик</button>
                </div>
            </div>
        </div>
    </div>

    <!-- =====================  ФУТЕР  ===================== -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>Кафе "Бегемот"</h3>
                    <p>Уютное кафе с домашней кухней, где каждый найдет что-то по вкусу. Приходите к нам за вкусной едой, хорошим кофе и отличным настроением!</p>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-vk"></i></a>
                        <a href="#"><i class="fab fa-telegram"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-facebook"></i></a>
                    </div>
                </div>
                <div class="footer-section">
                    <h3>Контакты</h3>
                    <p><i class="fas fa-map-marker-alt"></i> Москва, ул. Пушкина, д. Колотушкина</p>
                    <p><i class="fas fa-phone"></i> +7 (XXX) XXX-XX-XX</p>
                    <p><i class="fas fa-envelope"></i> info@begemot-cafe.ru</p>
                </div>
                <div class="footer-section">
                    <h3>Подпишитесь на новости</h3>
                    <p>Узнавайте первыми об акциях, новых блюдах и специальных предложениях.</p>

                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 Кафе "Бегемот". Все права защищены.</p>
            </div>
        </div>
    </footer>

    <!-- =================  ПЕРЕКЛЮЧЕНИЕ ВКЛАДОК  ================= -->
    <script>
        document.querySelectorAll('.tab-link').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelectorAll('.tab-link').forEach(item => item.classList.remove('active'));
                document.querySelectorAll('.tab-content').forEach(item => item.classList.remove('active'));
                this.classList.add('active');
                const tabId = this.getAttribute('data-tab');
                document.getElementById(tabId).classList.add('active');
                
                // Плавная прокрутка к началу контента при переключении вкладок
                window.scrollTo({
                    top: document.querySelector('.main-content').offsetTop - 100,
                    behavior: 'smooth'
                });
            });
        });
        
        // Добавляем интерактивность для карточек меню
        document.querySelectorAll('.dish-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0)';
            });
        });
        
        // Анимация для специального предложения
        const specialOffer = document.querySelector('.special-offer');
        if (specialOffer) {
            setInterval(() => {
                specialOffer.style.boxShadow = specialOffer.style.boxShadow === '0 0 20px rgba(255, 152, 0, 0.5)' 
                    ? '0 0 10px rgba(255, 152, 0, 0.3)' 
                    : '0 0 20px rgba(255, 152, 0, 0.5)';
            }, 1500);
        }
    </script>
</body>
</html>
