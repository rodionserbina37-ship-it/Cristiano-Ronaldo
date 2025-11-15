<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CR7 - Легенда футбола</title>
    <link rel="icon" type="image/x-icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>⚽</text></svg>">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: #000;
            color: #fff;
            overflow-x: hidden;
        }

        .hero {
            height: 100vh;
            background: linear-gradient(135deg, #000 0%, #1a1a1a 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at center, transparent 0%, #000 70%);
        }

        .hero-content {
            text-align: center;
            z-index: 2;
            opacity: 0;
            transform: translateY(50px);
            animation: heroAppear 1.5s ease-out 0.5s forwards;
        }

        @keyframes heroAppear {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 4.5rem;
            font-weight: 700;
            background: linear-gradient(45deg, #ff0000, #ff6b00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.5rem;
            opacity: 0.8;
            margin-bottom: 2rem;
        }

        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0) translateX(-50%);
            }
            40% {
                transform: translateY(-10px) translateX(-50%);
            }
            60% {
                transform: translateY(-5px) translateX(-50%);
            }
        }

        .slider-section {
            padding: 100px 0;
            background: #111;
        }

        .slider-container {
            max-width: 1200px;
            margin: 0 auto;
            position: relative;
        }

        .slider {
            display: flex;
            overflow: hidden;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(255, 107, 0, 0.3);
        }

        .slide {
            min-width: 100%;
            transition: transform 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
        }

        .slide-content {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            padding: 40px;
            background: linear-gradient(transparent, rgba(0,0,0,0.9));
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.6s ease;
        }

        .slide.active .slide-content {
            transform: translateY(0);
            opacity: 1;
        }

        .slide h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #ff6b00;
        }

        .slide p {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        .slider-nav {
            display: flex;
            justify-content: center;
            margin-top: 30px;
            gap: 15px;
        }

        .slider-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #333;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .slider-dot.active {
            background: #ff6b00;
            transform: scale(1.2);
        }

        .stats-section {
            padding: 100px 0;
            background: linear-gradient(45deg, #1a1a1a, #000);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 40px 30px;
            border-radius: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 107, 0, 0.1);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            border-color: rgba(255, 107, 0, 0.3);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 700;
            color: #ff6b00;
            margin-bottom: 10px;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.8;
        }

        .video-section {
            padding: 100px 0;
            background: #000;
        }

        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .video-card {
            position: relative;
            border-radius: 15px;
            overflow: hidden;
            background: #1a1a1a;
            transition: all 0.3s ease;
        }

        .video-card:hover {
            transform: scale(1.05);
            box-shadow: 0 20px 40px rgba(255, 107, 0, 0.4);
        }

        .video-card video {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .video-info {
            padding: 20px;
        }

        .video-info h3 {
            color: #ff6b00;
            margin-bottom: 10px;
        }

        .parallax-section {
            height: 60vh;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)),
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><rect fill="%231a1a1a" width="1200" height="800"/><circle fill="%23ff6b00" cx="200" cy="200" r="50" opacity="0.1"/><circle fill="%23ff0000" cx="800" cy="400" r="80" opacity="0.1"/><circle fill="%23ffffff" cx="1000" cy="200" r="30" opacity="0.1"/></svg>');
            background-attachment: fixed;
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        .parallax-content h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #fff, #ff6b00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        footer {
            background: #111;
            padding: 50px 20px;
            text-align: center;
            border-top: 1px solid #333;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .cr7-logo {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(45deg, #ff0000, #ff6b00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 20px;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .slide h2 {
                font-size: 1.8rem;
            }
            
            .parallax-content h2 {
                font-size: 2rem;
            }
        }

        .loading-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 0%;
            height: 3px;
            background: linear-gradient(90deg, #ff0000, #ff6b00);
            z-index: 1000;
            transition: width 0.3s ease;
        }

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <div class="loading-bar" id="loadingBar"></div>

    <section class="hero">
        <div class="hero-content">
            <h1>CRISTIANO RONALDO</h1>
            <p>Величайший футболист всех времен</p>
        </div>
        <div class="scroll-indicator">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 5v14M5 12l7 7 7-7"/>
            </svg>
        </div>
    </section>

    <section class="slider-section">
        <div class="slider-container">
            <div class="slider" id="slider">
                <div class="slide active">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='1200' height='600' viewBox='0 0 1200 600'><rect fill='%231a1a1a' width='1200' height='600'/><text x='50%' y='50%' font-family='Arial' font-size='48' fill='%23ff6b00' text-anchor='middle'>Реал Мадрид • 2009-2018</text></svg>" alt="Real Madrid Era" style="width: 100%; height: 600px; object-fit: cover;">
                    <div class="slide-content">
                        <h2>Золотая эра в Реале</h2>
                        <p>450 голов в 438 матчах • 4 Лиги Чемпионов • 4 Золотых мяча</p>
                    </div>
                </div>
                <div class="slide">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='1200' height='600' viewBox='0 0 1200 600'><rect fill='%23000' width='1200' height='600'/><text x='50%' y='50%' font-family='Arial' font-size='48' fill='%23ff0000' text-anchor='middle'>Манчестер Юнайтед • Возвращение</text></svg>" alt="Manchester United Return" style="width: 100%; height: 600px; object-fit: cover;">
                    <div class="slide-content">
                        <h2>Легенда возвращается</h2>
                        <p>Возвращение в клуб, где родилась легенда • Лидерство и опыт</p>
                    </div>
                </div>
                <div class="slide">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='1200' height='600' viewBox='0 0 1200 600'><rect fill='%23111' width='1200' height='600'/><text x='50%' y='50%' font-family='Arial' font-size='48' fill='%23ffffff' text-anchor='middle'>Сборная Португалии • Капитан</text></svg>" alt="Portugal National Team" style="width: 100%; height: 600px; object-fit: cover;">
                    <div class="slide-content">
                        <h2>Гордость Португалии</h2>
                        <p>Чемпион Европы 2016 • Лидер сборной • Рекордсмен по голам</p>
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

    <section class="stats-section">
        <div class="stats-grid">
            <div class="stat-card fade-in">
                <div class="stat-number">850+</div>
                <div class="stat-label">Голов за карьеру</div>
            </div>
            <div class="stat-card fade-in">
                <div class="stat-number">5</div>
                <div class="stat-label">Золотых мячей</div>
            </div>
            <div class="stat-card fade-in">
                <div class="stat-number">34</div>
                <div class="stat-label">Трофея</div>
            </div>
            <div class="stat-card fade-in">
                <div class="stat-number">120+</div>
                <div class="stat-label">Голов за сборную</div>
            </div>
        </div>
    </section>

    <section class="video-section">
        <div class="video-grid">
            <div class="video-card fade-in">
                <video controls poster="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='400' height='200' viewBox='0 0 400 200'><rect fill='%23ff6b00' width='400' height='200'/><text x='50%' y='50%' font-family='Arial' font-size='24' fill='white' text-anchor='middle'>Лучшие голы</text></svg>">
                    <source src="#" type="video/mp4">
                </video>
                <div class="video-info">
                    <h3>Лучшие голы</h3>
                    <p>Самые запоминающиеся моменты карьеры</p>
                </div>
            </div>
            <div class="video-card fade-in">
                <video controls poster="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='400' height='200' viewBox='0 0 400 200'><rect fill='%23ff0000' width='400' height='200'/><text x='50%' y='50%' font-family='Arial' font-size='24' fill='white' text-anchor='middle'>Тренировки</text></svg>">
                    <source src="#" type="video/mp4">
                </video>
                <div class="video-info">
                    <h3>Рабочая этика</h3>
                    <p>Секрет успеха Криштиану</p>
                </div>
            </div>
            <div class="video-card fade-in">
                <video controls poster="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='400' height='200' viewBox='0 0 400 200'><rect fill='%23000' width='400' height='200'/><text x='50%' y='50%' font-family='Arial' font-size='24' fill='white' text-anchor='middle'>Интервью</text></svg>">
                    <source src="#" type="video/mp4">
                </video>
                <div class="video-info">
                    <h3>Мотивация</h3>
                    <p>Мысли чемпиона об успехе</p>
                </div>
            </div>
        </div>
    </section>

    <section class="parallax-section">
        <div class="parallax-content">
            <h2>"Ваш любят не за то, что вы говорите. Ваш любят за то, что вы делаете."</h2>
            <p>— Криштиану Роналду</p>
        </div>
    </section>

    <footer>
        <div class="footer-content">
            <div class="cr7-logo">CR7</div>
            <p>Легенда футбола • Икона стиля • Вдохновение для миллионов</p>
            <p style="margin-top: 20px; opacity: 0.6;">© 2024 Cristiano Ronaldo Legacy. Все права защищены.</p>
        </div>
    </footer>

    <script>
        // Slider functionality
        class Slider {
            constructor() {
                this.slides = document.querySelectorAll('.slide');
                this.dots = document.querySelectorAll('.slider-dot');
                this.currentSlide = 0;
                this.interval = null;
                this.init();
            }

            init() {
                this.startAutoSlide();
                this.dots.forEach((dot, index) => {
                    dot.addEventListener('click', () => {
                        this.goToSlide(index);
                        this.resetAutoSlide();
                    });
                });

                // Pause on hover
                const slider = document.getElementById('slider');
                slider.addEventListener('mouseenter', () => this.stopAutoSlide());
                slider.addEventListener('mouseleave', () => this.startAutoSlide());
            }

            goToSlide(index) {
                this.slides[this.currentSlide].classList.remove('active');
                this.dots[this.currentSlide].classList.remove('active');
                
                this.currentSlide = index;
                
                this.slides[this.currentSlide].classList.add('active');
                this.dots[this.currentSlide].classList.add('active');
            }

            nextSlide() {
                const next = (this.currentSlide + 1) % this.slides.length;
                this.goToSlide(next);
            }

            startAutoSlide() {
                this.interval = setInterval(() => this.nextSlide(), 5000);
            }

            stopAutoSlide() {
                if (this.interval) {
                    clearInterval(this.interval);
                    this.interval = null;
                }
            }

            resetAutoSlide() {
                this.stopAutoSlide();
                this.startAutoSlide();
            }
        }

        // Loading progress
        window.addEventListener('load', () => {
            document.getElementById('loadingBar').style.width = '100%';
            setTimeout(() => {
                document.getElementById('loadingBar').style.opacity = '0';
            }, 500);
        });

        // Scroll animations
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

        // Initialize everything when DOM is loaded
        document.addEventListener('DOMContentLoaded', () => {
            // Initialize slider
            new Slider();

            // Observe fade-in elements
            document.querySelectorAll('.fade-in').forEach(el => {
                observer.observe(el);
            });

            // Smooth scroll for anchor links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });

            // Parallax effect
            window.addEventListener('scroll', () => {
                const scrolled = window.pageYOffset;
                const parallax = document.querySelector('.parallax-section');
                if (parallax) {
                    parallax.style.transform = `translateY(${scrolled * 0.5}px)`;
                }
            });
        });

        // Loading progress simulation
        let progress = 0;
        const loadingBar = document.getElementById('loadingBar');
        const loadingInterval = setInterval(() => {
            progress += Math.random() * 10;
            if (progress > 90) {
                clearInterval(loadingInterval);
            }
            loadingBar.style.width = progress + '%';
        }, 100);
    </script>
</body>
</html>
