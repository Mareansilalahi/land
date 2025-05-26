<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Point Blank - Game FPS Terbaik</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@400;500;600;700&family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <style>
        /* Reset CSS */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Variabel Warna */
        :root {
            --primary-color: #0a1929;
            --secondary-color: #152238;
            --accent-color: #ffd700;
            --text-primary: #ffffff;
            --text-secondary: #cccccc;
        }

        /* Gaya Dasar */
        body {
            font-family: 'Roboto', sans-serif;
            background-color: var(--primary-color);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: linear-gradient(to bottom, rgba(10, 25, 41, 0.95), rgba(10, 25, 41, 0.98)), url('https://i.ibb.co/JnHwXSJ/pb-background.jpg');
            background-size: cover;
            background-attachment: fixed;
            background-position: center;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Rajdhani', sans-serif;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        a {
            text-decoration: none;
            color: var(--text-primary);
            transition: all 0.3s ease;
        }

        a:hover {
            color: var(--accent-color);
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            padding: 20px 0;
            position: relative;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo-container {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            position: relative;
        }

        .website-icon {
            position: absolute;
            left: 0;
            width: 40px;
            height: 40px;
            cursor: pointer;
        }

        .website-logo {
            height: 60px;
            cursor: pointer;
        }

        /* Navigasi */
        .nav-menu {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }

        .nav-menu ul {
            display: flex;
            list-style: none;
            gap: 10px;
        }

        .nav-menu li {
            margin: 0 5px;
        }

        .nav-menu a {
            display: block;
            padding: 10px 20px;
            background-color: rgba(21, 34, 56, 0.8);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 6px;
            font-family: 'Rajdhani', sans-serif;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease;
        }

        .nav-menu a:hover {
            background-color: rgba(255, 215, 0, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.2);
        }

        .hamburger-menu {
            display: none;
            cursor: pointer;
            z-index: 100;
        }

        .hamburger-menu div {
            width: 25px;
            height: 3px;
            background-color: var(--text-primary);
            margin: 5px 0;
            transition: all 0.3s ease;
        }

        /* Hero Section dengan Slider */
        .hero-section {
            padding: 40px 0;
            position: relative;
        }

        .slider-container {
            position: relative;
            width: 100%;
            height: 400px;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }

        .slider {
            display: flex;
            width: 500%;
            height: 100%;
            transition: transform 0.5s ease-in-out;
        }

        .slide {
            width: 20%;
            height: 100%;
            position: relative;
            background-size: cover;
            background-position: center;
        }

        .slide-content {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            padding: 20px;
            background: linear-gradient(to top, rgba(10, 25, 41, 0.9), transparent);
        }

        .slide-content h2 {
            color: var(--accent-color);
            font-size: 2rem;
            margin-bottom: 10px;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
        }

        .slide-content p {
            color: var(--text-primary);
            font-size: 1rem;
            max-width: 80%;
            text-shadow: 0 1px 2px rgba(0, 0, 0, 0.5);
        }

        .slider-nav {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
        }

        .slider-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .slider-dot.active {
            background-color: var(--accent-color);
            transform: scale(1.2);
        }

        .slider-arrow {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 40px;
            height: 40px;
            background-color: rgba(10, 25, 41, 0.7);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 10;
            transition: all 0.3s ease;
        }

        .slider-arrow:hover {
            background-color: var(--accent-color);
        }

        .slider-arrow.prev {
            left: 10px;
        }

        .slider-arrow.next {
            right: 10px;
        }

        .slider-arrow::before {
            content: '';
            width: 10px;
            height: 10px;
            border-top: 2px solid white;
            border-right: 2px solid white;
            display: block;
        }

        .slider-arrow.prev::before {
            transform: rotate(-135deg);
        }

        .slider-arrow.next::before {
            transform: rotate(45deg);
        }

        /* Auth Section */
        .auth-section {
            padding: 30px 0;
            text-align: center;
        }

        .auth-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }

        .auth-button {
            padding: 12px 30px;
            background: linear-gradient(135deg, #ffd700, #ffaa00);
            color: #0a1929;
            border: none;
            border-radius: 6px;
            font-family: 'Rajdhani', sans-serif;
            font-weight: 700;
            font-size: 1.2rem;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
        }

        .auth-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 215, 0, 0.5);
        }

        .auth-button:active {
            transform: translateY(-1px);
        }

        /* Articles Section */
        .articles-section {
            padding: 40px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 40px;
            color: var(--accent-color);
            text-transform: uppercase;
            letter-spacing: 2px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background-color: var(--accent-color);
        }

        .articles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .article-card {
            background-color: var(--secondary-color);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            transition: all 0.3s ease;
        }

        .article-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
        }

        .article-image {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .article-content {
            padding: 20px;
        }

        .article-title {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--accent-color);
        }

        .article-excerpt {
            color: var(--text-secondary);
            margin-bottom: 15px;
            font-size: 0.9rem;
            line-height: 1.5;
        }

        .read-more {
            display: inline-block;
            padding: 8px 15px;
            background-color: rgba(255, 215, 0, 0.2);
            color: var(--accent-color);
            border-radius: 4px;
            font-size: 0.9rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .read-more:hover {
            background-color: var(--accent-color);
            color: var(--primary-color);
        }

        /* Footer */
        footer {
            background-color: rgba(10, 20, 30, 0.8);
            padding: 30px 0;
            margin-top: 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .footer-logo {
            height: 40px;
        }

        .footer-links {
            display: flex;
            gap: 20px;
        }

        .footer-links a {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        .footer-links a:hover {
            color: var(--accent-color);
        }

        .copyright {
            width: 100%;
            text-align: center;
            margin-top: 20px;
            color: var(--text-secondary);
            font-size: 0.8rem;
        }

        /* 3D Animation Elements */
        .animation-3d {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 5px;
            height: 5px;
            background-color: rgba(255, 215, 0, 0.5);
            border-radius: 50%;
            animation: float 15s infinite linear;
        }

        @keyframes float {
            0% {
                transform: translateY(0) translateX(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) translateX(100px) rotate(360deg);
                opacity: 0;
            }
        }

        /* Responsif */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
            }

            .website-icon {
                position: relative;
                margin-bottom: 10px;
            }

            .nav-menu {
                display: none;
            }

            .nav-menu.active {
                display: flex;
                flex-direction: column;
                position: fixed;
                top: 0;
                right: 0;
                width: 70%;
                height: 100vh;
                background-color: var(--primary-color);
                z-index: 99;
                padding-top: 80px;
            }

            .nav-menu.active ul {
                flex-direction: column;
                width: 100%;
            }

            .nav-menu.active li {
                margin: 10px 0;
                width: 100%;
            }

            .nav-menu.active a {
                width: 100%;
                text-align: center;
            }

            .hamburger-menu {
                display: block;
                position: absolute;
                top: 20px;
                right: 20px;
            }

            .slider-container {
                height: 300px;
            }

            .slide-content h2 {
                font-size: 1.5rem;
            }

            .slide-content p {
                font-size: 0.9rem;
                max-width: 100%;
            }

            .auth-buttons {
                flex-direction: column;
                gap: 10px;
            }

            .articles-grid {
                grid-template-columns: 1fr;
            }

            .footer-content {
                flex-direction: column;
                gap: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo-container">
                    <!-- Icon Website (bisa diganti) -->
                    <img src="https://i.ibb.co/cXVdqTM/pb-icon.png" alt="Point Blank Icon" class="website-icon" id="website-icon">
                    
                    <!-- Logo Website (bisa diganti) -->
                    <img src="https://i.ibb.co/5jGF9Lv/pb-logo.png" alt="Point Blank Logo" class="website-logo" id="website-logo">
                </div>
                
                <!-- Hamburger Menu untuk Mobile -->
                <div class="hamburger-menu" id="hamburger-menu">
                    <div></div>
                    <div></div>
                    <div></div>
                </div>
            </div>
            
            <!-- Menu Navigasi -->
            <nav class="nav-menu" id="nav-menu">
                <ul>
                    <li><a href="#">Beranda</a></li>
                    <li><a href="#">Berita</a></li>
                    <li><a href="#">Turnamen</a></li>
                    <li><a href="#">Top-Up</a></li>
                    <li><a href="#">Unduh</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section dengan Slider -->
    <section class="hero-section">
        <div class="container">
            <div class="slider-container">
                <div class="slider" id="slider">
                    <!-- Slide 1 -->
                    <div class="slide" style="background-image: url('https://i.ibb.co/Qp9Nv7k/pb-slide1.jpg');">
                        <div class="slide-content">
                            <h2>Point Blank - FPS Terbaik</h2>
                            <p>Rasakan pengalaman bermain FPS terbaik dengan grafis memukau dan gameplay seru!</p>
                        </div>
                    </div>
                    
                    <!-- Slide 2 -->
                    <div class="slide" style="background-image: url('https://i.ibb.co/Jy8MVHW/pb-slide2.jpg');">
                        <div class="slide-content">
                            <h2>Turnamen Nasional</h2>
                            <p>Ikuti turnamen nasional dan menangkan hadiah jutaan rupiah!</p>
                        </div>
                    </div>
                    
                    <!-- Slide 3 -->
                    <div class="slide" style="background-image: url('https://i.ibb.co/HxbJZhL/pb-slide3.jpg');">
                        <div class="slide-content">
                            <h2>Senjata Baru</h2>
                            <p>Koleksi senjata terbaru dengan kemampuan unik telah tiba!</p>
                        </div>
                    </div>
                    
                    <!-- Slide 4 -->
                    <div class="slide" style="background-image: url('https://i.ibb.co/Jqf4Lbw/pb-slide4.jpg');">
                        <div class="slide-content">
                            <h2>Mode Permainan Baru</h2>
                            <p>Jelajahi mode permainan baru yang menantang dan seru!</p>
                        </div>
                    </div>
                    
                    <!-- Slide 5 -->
                    <div class="slide" style="background-image: url('https://i.ibb.co/0jHvZZB/pb-slide5.jpg');">
                        <div class="slide-content">
                            <h2>Karakter Eksklusif</h2>
                            <p>Dapatkan karakter eksklusif dengan kemampuan spesial!</p>
                        </div>
                    </div>
                </div>
                
                <!-- Navigasi Slider -->
                <div class="slider-arrow prev" id="prev-slide"></div>
                <div class="slider-arrow next" id="next-slide"></div>
                
                <!-- Indikator Slider -->
                <div class="slider-nav" id="slider-nav">
                    <div class="slider-dot active"></div>
                    <div class="slider-dot"></div>
                    <div class="slider-dot"></div>
                    <div class="slider-dot"></div>
                    <div class="slider-dot"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- Auth Section -->
    <section class="auth-section">
        <div class="container">
            <div class="auth-buttons">
                <button class="auth-button">Daftar</button>
                <button class="auth-button">Login</button>
            </div>
        </div>
    </section>

    <!-- Articles Section -->
    <section class="articles-section">
        <div class="container">
            <h2 class="section-title">Berita Terbaru</h2>
            
            <div class="articles-grid">
                <!-- Article 1 -->
                <div class="article-card">
                    <img src="https://i.ibb.co/JnHwXSJ/pb-background.jpg" alt="Update Terbaru" class="article-image">
                    <div class="article-content">
                        <h3 class="article-title">Update Terbaru Point Blank</h3>
                        <p class="article-excerpt">Nikmati pengalaman bermain yang lebih seru dengan update terbaru Point Blank. Fitur baru, peta baru, dan banyak lagi!</p>
                        <a href="#" class="read-more">Baca Selengkapnya</a>
                    </div>
                </div>
                
                <!-- Article 2 -->
                <div class="article-card">
                    <img src="https://i.ibb.co/Qp9Nv7k/pb-slide1.jpg" alt="Turnamen" class="article-image">
                    <div class="article-content">
                        <h3 class="article-title">Turnamen Point Blank Championship</h3>
                        <p class="article-excerpt">Daftarkan tim kamu sekarang dan ikuti turnamen Point Blank Championship dengan total hadiah ratusan juta rupiah!</p>
                        <a href="#" class="read-more">Baca Selengkapnya</a>
                    </div>
                </div>
                
                <!-- Article 3 -->
                <div class="article-card">
                    <img src="https://i.ibb.co/HxbJZhL/pb-slide3.jpg" alt="Senjata Baru" class="article-image">
                    <div class="article-content">
                        <h3 class="article-title">Senjata Baru: Kriss Super V</h3>
                        <p class="article-excerpt">Senjata baru Kriss Super V telah hadir dengan kemampuan damage tinggi dan recoil rendah. Dapatkan sekarang!</p>
                        <a href="#" class="read-more">Baca Selengkapnya</a>
                    </div>
                </div>
                
                <!-- Article 4 -->
                <div class="article-card">
                    <img src="https://i.ibb.co/Jy8MVHW/pb-slide2.jpg" alt="Event" class="article-image">
                    <div class="article-content">
                        <h3 class="article-title">Event Spesial Akhir Tahun</h3>
                        <p class="article-excerpt">Rayakan akhir tahun dengan event spesial Point Blank. Dapatkan hadiah menarik dan item eksklusif!</p>
                        <a href="#" class="read-more">Baca Selengkapnya</a>
                    </div>
                </div>
                
                <!-- Article 5 -->
                <div class="article-card">
                    <img src="https://i.ibb.co/0jHvZZB/pb-slide5.jpg" alt="Karakter Baru" class="article-image">
                    <div class="article-content">
                        <h3 class="article-title">Karakter Baru: Shadow Assassin</h3>
                        <p class="article-excerpt">Karakter baru Shadow Assassin telah hadir dengan kemampuan stealth dan kecepatan tinggi. Mainkan sekarang!</p>
                        <a href="#" class="read-more">Baca Selengkapnya</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <img src="https://i.ibb.co/5jGF9Lv/pb-logo.png" alt="Point Blank Logo" class="footer-logo">
                
                <div class="footer-links">
                    <a href="#">Tentang Kami</a>
                    <a href="#">Syarat & Ketentuan</a>
                    <a href="#">Kebijakan Privasi</a>
                    <a href="#">Bantuan</a>
                </div>
            </div>
            
            <div class="copyright">
                &copy; 2025 Point Blank. All Rights Reserved.
            </div>
        </div>
    </footer>

    <!-- 3D Animation Elements -->
    <div class="animation-3d" id="animation-3d"></div>

    <!-- JavaScript -->
    <script>
        // Slider Functionality
        document.addEventListener('DOMContentLoaded', function() {
            const slider = document.getElementById('slider');
            const slides = document.querySelectorAll('.slide');
            const dots = document.querySelectorAll('.slider-dot');
            const prevBtn = document.getElementById('prev-slide');
            const nextBtn = document.getElementById('next-slide');
            let currentSlide = 0;
            let slideInterval;

            // Function to update slider position
            function updateSlider() {
                slider.style.transform = `translateX(-${currentSlide * 20}%)`;
                
                // Update active dot
                dots.forEach((dot, index) => {
                    dot.classList.toggle('active', index === currentSlide);
                });
            }

            // Function to go to next slide
            function nextSlide() {
                currentSlide = (currentSlide + 1) % slides.length;
                updateSlider();
            }

            // Function to go to previous slide
            function prevSlide() {
                currentSlide = (currentSlide - 1 + slides.length) % slides.length;
                updateSlider();
            }

            // Set up click events for navigation
            prevBtn.addEventListener('click', () => {
                clearInterval(slideInterval);
                prevSlide();
                startSlideInterval();
            });

            nextBtn.addEventListener('click', () => {
                clearInterval(slideInterval);
                nextSlide();
                startSlideInterval();
            });

            // Set up click events for dots
            dots.forEach((dot, index) => {
                dot.addEventListener('click', () => {
                    clearInterval(slideInterval);
                    currentSlide = index;
                    updateSlider();
                    startSlideInterval();
                });
            });

            // Function to start automatic sliding
            function startSlideInterval() {
                slideInterval = setInterval(nextSlide, 5000);
            }

            // Start automatic sliding
            startSlideInterval();

            // Mobile Menu Toggle
            const hamburgerMenu = document.getElementById('hamburger-menu');
            const navMenu = document.getElementById('nav-menu');

            hamburgerMenu.addEventListener('click', () => {
                navMenu.classList.toggle('active');
                hamburgerMenu.classList.toggle('active');
            });

            // 3D Animation
            const animationContainer = document.getElementById('animation-3d');
            
            // Create particles
            for (let i = 0; i < 30; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Random position
                const posX = Math.random() * 100;
                const posY = Math.random() * 100;
                const size = Math.random() * 5 + 2;
                const delay = Math.random() * 15;
                const duration = Math.random() * 10 + 10;
                
                particle.style.left = `${posX}%`;
                particle.style.top = `${posY}%`;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.animationDelay = `${delay}s`;
                particle.style.animationDuration = `${duration}s`;
                
                animationContainer.appendChild(particle);
            }

            // Logo and Icon Replacement Functionality
            const websiteIcon = document.getElementById('website-icon');
            const websiteLogo = document.getElementById('website-logo');

            // Example of how to change the logo and icon (for demonstration)
            // In a real implementation, this would be connected to an admin panel
            websiteIcon.addEventListener('click', function() {
                alert('Klik untuk mengganti ikon website. Dalam implementasi sebenarnya, ini akan membuka dialog pemilihan file.');
                // Implementasi sebenarnya akan menggunakan input file dan mengubah src gambar
            });

            websiteLogo.addEventListener('click', function() {
                alert('Klik untuk mengganti logo website. Dalam implementasi sebenarnya, ini akan membuka dialog pemilihan file.');
                // Implementasi sebenarnya akan menggunakan input file dan mengubah src gambar
            });
        });
    </script>
</body>
</html>
