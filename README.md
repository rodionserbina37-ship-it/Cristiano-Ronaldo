<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CR7 - Cristiano Ronaldo</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;


        body {
            background: #0a0a0a;
            color: #fff;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #1a1a1a 0%, #000 100%);
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 2px solid #ff6b00;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: #ff6b00;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        .nav-links a {
            color: #fff;
            text-decoration: none;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #ff6b00;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), 
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="800" viewBox="0 0 1200 800"><rect fill="%231a1a1a" width="1200" height="800"/></svg>');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            text-align: center;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ff6b00, #ff0000);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: #ff6b00;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            transition: background 0.3s;
        }

        .btn:hover {
            background: #ff8c00;
        }

        /* Slider */
        .slider-section {
            padding: 100px 0;
            background: #111;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 50px;
            color: #ff6b00;
        }

        .slider {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(255,107,0,0.3);
        }

        .slides {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }

        .slide {
            min-width: 100%;
            position: relative;
        }

        .slide img {
            width: 100%;
            height: 500px;
            object-fit: cover;
        }

        .slide-content {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0,0,0,0.9));
            padding: 30px;
            color: white;
        }

        .slide-content h3 {
            font-size: 1.8rem;
            margin-bottom: 10px;
            color: #ff6b00;
        }

        .slider-nav {
            display: flex;
            justify-content: center;
            margin-top: 20px;
            gap: 10px;
        }

        .slider-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #333;
            cursor: pointer;
            transition: background 0.3s;
        }

        .slider-dot.active {
            background: #ff6b00;
        }

        /* Stats */
        .stats {
            padding: 80px 0;
            background: #000;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .stat-card {
            background: #1a1a1a;
            padding: 40px 20px;
            text-align: center;
            border-radius: 10px;
            border: 1px solid #333;
            transition: transform 0.3s;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            border-color: #ff6b00;
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #ff6b00;
            margin-bottom: 10px;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.9;
        }

        /* Videos */
        .videos {
            padding: 80px 0;
            background: #111;
        }

        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .video-card {
            background: #1a1a1a;
            border-radius: 10px;
            overflow: hidden;
            transition: transform 0.3s;
        }

        .video-card:hover {
            transform: scale(1.05);
        }

        .video-placeholder {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, #ff6b00, #ff0000);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
        }

        .video-info {
            padding: 20px;
        }

        .video-info h3 {
            color: #ff6b00;
            margin-bottom: 10px;
        }

        /* Footer */
        footer {
            background: #000;
            padding: 50px 0 20px;
            border-top: 2px solid #ff6b00;
        }

        .footer-content {
            text-align: center;
        }

        .cr7-badge {
            font-size: 3rem;
            font-weight: bold;
            color: #ff6b00;
            margin-bottom: 20px;
        }

        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .nav-links {
                gap: 15px;
            }
            
            .slide img {
                height: 300px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">CR7</div>
                <ul class="nav-links">
                    <li><a href="#home">Главная</a></li>
                    <li><a href="#career">Карьера</a></li>
                    <li><a href="#stats">Статистика</a></li>
                    <li><a href="#videos">Видео</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1>Криштиану Роналду</h1>
                <p>Легенда футбола. Вдохновение для миллионов.</p>
                <a href="#career" class="btn">Узнать больше</a>
            </div>
        </div>
    </section>

    <!-- Slider Section -->
    <section class="slider-section" id="career">
        <div class="container">
            <h2 class="section-title">Карьера</h2>
            <div class="slider">
                <div class="slides">
                    <div class="slide">
                        <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='800' height='500' viewBox='0 0 800 500'><rect fill='%231a1a1a' width='800' height='500'/><text x='50%' y='50%' font-family='Arial' font-size='36' fill='%23ff6b00' text-anchor='middle'>Спортинг • 2002-2003</text></svg>" alt="Sporting">
                        <div class="slide-content">
                            <h3>Начало в Спортинге</h3>
                            <p>Первые шаги в профессиональном футболе</p>
                        </div>
                    </div>
                    <div class="slide">
                        <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='800' height='500' viewBox='0 0 800 500'><rect fill='%23000' width='800' height='500'/><text x='50%' y='50%' font-family='Arial' font-size='36' fill='%23ff0000' text-anchor='middle'>Манчестер Юнайтед • 2003-2009</text></svg>" alt="Manchester United">
                        <div class="slide-content">
                            <h3>Манчестер Юнайтед</h3>
                            <p>Становление звездой мирового футбола</p>
                        </div>
                    </div>
                    <div class="slide">
                        <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='800' height='500' viewBox='0 0 800 500'><rect fill='%23111' width='800' height='500'/><text x='50%' y='50%' font-family='Arial' font-size='36' fill='%23ffffff' text-anchor='middle'>Реал Мадрид • 2009-2018</text></svg>" alt="Real Madrid">
                        <div class="slide-content">
                            <h3>Реал Мадрид</h3>
                            <p>450 голов • 4 Лиги Чемпионов • Легенда клуба</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="slider-nav">
                <div class="slider-dot active" data-slide="0"></div>
                <div class="slider-dot" data-slide="1"></div>
                <div class="slider-dot" data-slide="2"></div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats" id="stats">
        <div class="container">
            <h2 class="section-title">Рекорды</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number">850+</div>
                    <div class="stat-label">Голов за карьеру</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">5</div>
                    <div class="stat-label">Золотых мячей</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">34</div>
                    <div class="stat-label">Трофея</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">120+</div>
                    <div class="stat-label">Голов за сборную</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Videos Section -->
    <section class="videos" id="videos">
        <div class="container">
            <h2 class="section-title">Лучшие моменты</h2>
            <div class="video-grid">
                <div class="video-card">
                    <div class="video-placeholder">🎥 Лучшие голы</div>
                    <div class="video-info">
                        <h3>Топ-10 голов</h3>
                        <p>Самые зрелищные голы в карьере</p>
                    </div>
                </div>
                <div class="video-card">
                    <div class="video-placeholder">⚽ Тренировки</div>
                    <div class="video-info">
                        <h3>Рабочая этика</h3>
                        <p>Как тренируется чемпион</p>
                    </div>
                </div>
                <div class="video-card">
                    <div class="video-placeholder">🏆 Трофеи</div>
                    <div class="video-info">
                        <h3>Коллекция наград</h3>
                        <p>Все достижения легенды</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="cr7-badge">CRISTIANO RONALDO</div>
                <p>Величайший футболист всех времен • Икона спорта • Легенда</p>
                <p style="margin-top: 20px; opacity: 0.7;">© 2024 CR7 Legacy</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple slider
        class SimpleSlider {
            constructor() {
                this.slides = document.querySelector('.slides');
                this.dots = document.querySelectorAll('.slider-dot');
                this.currentSlide = 0;
                this.totalSlides = this.dots.length;
                this.init();
            }

            init() {
                // Dot click events
                this.dots.forEach((dot, index) => {
                    dot.addEventListener('click', () => {
                        this.goToSlide(index);
                    });
                });

                // Auto slide
                setInterval(() => {
                    this.nextSlide();
                }, 5000);
            }

            goToSlide(index) {
                this.currentSlide = index;
                this.updateSlider();
            }

            nextSlide() {
                this.currentSlide = (this.currentSlide + 1) % this.totalSlides;
                this.updateSlider();
            }

            updateSlider() {
                // Move slides
                this.slides.style.transform = `translateX(-${this.currentSlide * 100}%)`;
                
                // Update dots
                this.dots.forEach((dot, index) => {
                    dot.classList.toggle('active', index === this.currentSlide);
                });
            }
        }

        // Smooth scroll for navigation links
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

        // Header background on scroll
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(0, 0, 0, 0.95)';
            } else {
                header.style.background = 'linear-gradient(135deg, #1a1a1a 0%, #000 100%)';
            }
        });

        // Initialize slider when page loads
        document.addEventListener('DOMContentLoaded', () => {
            new SimpleSlider();
        });

        // Simple animation for stat cards
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        });

        // Observe stat cards
        document.querySelectorAll('.stat-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(20px)';
            card.style.transition = 'all 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
