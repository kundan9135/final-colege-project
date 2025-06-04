# final-colege-project
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TechLife Hub - AI Technology & Lifestyle Blog</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: #1a1a1a;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            transition: all 0.3s ease;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #667eea;
            transform: translateY(-2px);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            padding: 120px 0 80px;
            text-align: center;
            color: white;
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="75" cy="75" r="1" fill="rgba(255,255,255,0.1)"/><circle cx="50" cy="10" r="0.5" fill="rgba(255,255,255,0.05)"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            opacity: 0.5;
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(1deg); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #fff, #f0f8ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 4px 20px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 15px 30px;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
            box-shadow: 0 10px 30px rgba(255, 107, 107, 0.3);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(10px);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
        }

        /* Main Content */
        main {
            background: white;
            margin-top: -50px;
            border-radius: 30px 30px 0 0;
            position: relative;
            z-index: 10;
            box-shadow: 0 -10px 40px rgba(0,0,0,0.1);
        }

        .content-section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Blog Grid */
        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .blog-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .blog-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
        }

        .blog-image {
            height: 200px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            position: relative;
            overflow: hidden;
        }

        .blog-image::before {
            content: '🤖';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 3rem;
            opacity: 0.3;
        }

        .ai-image::before { content: '🤖'; }
        .lifestyle-image::before { content: '✨'; }
        .affiliate-image::before { content: '💰'; }

        .blog-content {
            padding: 1.5rem;
        }

        .blog-category {
            display: inline-block;
            padding: 0.3rem 0.8rem;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .blog-title {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .blog-excerpt {
            color: #666;
            margin-bottom: 1rem;
            line-height: 1.6;
        }

        .read-more {
            color: #667eea;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .read-more:hover {
            color: #764ba2;
            text-decoration: underline;
        }

        /* Email Newsletter */
        .newsletter {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 60px 0;
            text-align: center;
        }

        .newsletter h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .newsletter p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .email-form {
            max-width: 500px;
            margin: 0 auto;
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            justify-content: center;
        }

        .email-input {
            flex: 1;
            min-width: 250px;
            padding: 15px 20px;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            background: rgba(255,255,255,0.9);
            backdrop-filter: blur(10px);
        }

        .email-input:focus {
            outline: none;
            box-shadow: 0 0 20px rgba(255,255,255,0.3);
        }

        /* Affiliate Section */
        .affiliate-products {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            text-align: center;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .product-card:hover {
            transform: translateY(-5px);
            border-color: #667eea;
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        }

        .product-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .product-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .product-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: #667eea;
            margin-bottom: 1rem;
        }

        /* Footer */
        footer {
            background: #1a1a1a;
            color: white;
            padding: 40px 0;
            text-align: center;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #667eea;
        }

        .footer-section a {
            color: #ccc;
            text-decoration: none;
            display: block;
            margin-bottom: 0.5rem;
            transition: color 0.3s ease;
        }

        .footer-section a:hover {
            color: #667eea;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                flex-direction: column;
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .email-form {
                flex-direction: column;
            }

            .email-input {
                min-width: 100%;
            }
        }

        /* Success Message */
        .success-message {
            background: linear-gradient(45deg, #00b894, #55a3ff);
            color: white;
            padding: 1rem;
            border-radius: 10px;
            margin-top: 1rem;
            display: none;
            animation: slideIn 0.5s ease;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Loading Animation */
        .loading {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: #fff;
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <div class="logo">TechLife Hub</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#ai-tech">AI Tech</a></li>
                <li><a href="#lifestyle">Lifestyle</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#newsletter">Newsletter</a></li>
            </ul>
        </nav>
    </header>

    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1>Welcome to TechLife Hub</h1>
                <p>Discover the future of AI technology, enhance your lifestyle, and find the best products to transform your daily life.</p>
                <div class="cta-buttons">
                    <a href="#blog" class="btn btn-primary">Explore Articles</a>
                    <a href="#newsletter" class="btn btn-secondary">Join Newsletter</a>
                </div>
            </div>
        </div>
    </section>

    <main>
        <section class="content-section" id="blog">
            <div class="container">
                <h2 class="section-title">Latest Articles</h2>
                <div class="blog-grid">
                    <article class="blog-card">
                        <div class="blog-image ai-image"></div>
                        <div class="blog-content">
                            <span class="blog-category">AI Technology</span>
                            <h3 class="blog-title">The Future of AI in Everyday Life</h3>
                            <p class="blog-excerpt">Explore how artificial intelligence is revolutionizing our daily routines, from smart homes to personal assistants, and what to expect in the coming years.</p>
                            <a href="#" class="read-more">Read More →</a>
                        </div>
                    </article>

                    <article class="blog-card">
                        <div class="blog-image lifestyle-image"></div>
                        <div class="blog-content">
                            <span class="blog-category">Lifestyle</span>
                            <h3 class="blog-title">10 Productivity Hacks for Remote Workers</h3>
                            <p class="blog-excerpt">Discover proven strategies to boost your productivity while working from home, including tools, techniques, and mindset shifts.</p>
                            <a href="#" class="read-more">Read More →</a>
                        </div>
                    </article>

                    <article class="blog-card">
                        <div class="blog-image ai-image"></div>
                        <div class="blog-content">
                            <span class="blog-category">AI Technology</span>
                            <h3 class="blog-title">ChatGPT vs Claude: Which AI Assistant is Right for You?</h3>
                            <p class="blog-excerpt">A comprehensive comparison of the leading AI assistants, their strengths, weaknesses, and best use cases for different needs.</p>
                            <a href="#" class="read-more">Read More →</a>
                        </div>
                    </article>

                    <article class="blog-card">
                        <div class="blog-image lifestyle-image"></div>
                        <div class="blog-content">
                            <span class="blog-category">Lifestyle</span>
                            <h3 class="blog-title">Minimalist Tech Setup for Maximum Impact</h3>
                            <p class="blog-excerpt">Learn how to create a clean, efficient workspace that enhances focus and productivity without breaking the bank.</p>
                            <a href="#" class="read-more">Read More →</a>
                        </div>
                    </article>

                    <article class="blog-card">
                        <div class="blog-image ai-image"></div>
                        <div class="blog-content">
                            <span class="blog-category">AI Technology</span>
                            <h3 class="blog-title">Machine Learning for Beginners: Your First Steps</h3>
                            <p class="blog-excerpt">A beginner-friendly guide to understanding machine learning concepts, tools, and how to start your journey in AI.</p>
                            <a href="#" class="read-more">Read More →</a>
                        </div>
                    </article>

                    <article class="blog-card">
                        <div class="blog-image affiliate-image"></div>
                        <div class="blog-content">
                            <span class="blog-category">Product Review</span>
                            <h3 class="blog-title">Best Smart Home Devices for 2025</h3>
                            <p class="blog-excerpt">Our top picks for smart home devices that will transform your living space, complete with pros, cons, and buying guides.</p>
                            <a href="#" class="read-more">Read More →</a>
                        </div>
                    </article>
                </div>
            </div>
        </section>

        <section class="content-section" id="products">
            <div class="container">
                <h2 class="section-title">Recommended Products</h2>
                <div class="affiliate-products">
                    <div class="product-card">
                        <div class="product-icon">💻</div>
                        <h3 class="product-title">Premium Laptop Stand</h3>
                        <div class="product-price">$89.99</div>
                        <p>Ergonomic aluminum laptop stand that improves posture and increases productivity.</p>
                        <a href="#" class="btn btn-primary" style="margin-top: 1rem;">Shop Now</a>
                    </div>

                    <div class="product-card">
                        <div class="product-icon">🎧</div>
                        <h3 class="product-title">Noise-Canceling Headphones</h3>
                        <div class="product-price">$299.99</div>
                        <p>Industry-leading noise cancellation for focused work and immersive audio experience.</p>
                        <a href="#" class="btn btn-primary" style="margin-top: 1rem;">Shop Now</a>
                    </div>

                    <div class="product-card">
                        <div class="product-icon">📱</div>
                        <h3 class="product-title">AI-Powered Fitness Tracker</h3>
                        <div class="product-price">$199.99</div>
                        <p>Smart fitness tracking with AI insights to optimize your health and wellness journey.</p>
                        <a href="#" class="btn btn-primary" style="margin-top: 1rem;">Shop Now</a>
                    </div>

                    <div class="product-card">
                        <div class="product-icon">🏠</div>
                        <h3 class="product-title">Smart Home Hub</h3>
                        <div class="product-price">$149.99</div>
                        <p>Central control for all your smart home devices with voice control and automation.</p>
                        <a href="#" class="btn btn-primary" style="margin-top: 1rem;">Shop Now</a>
                    </div>
                </div>
            </div>
        </section>

        <section class="newsletter" id="newsletter">
            <div class="container">
                <h2>Stay Updated with TechLife Hub</h2>
                <p>Get the latest insights on AI technology, lifestyle tips, and exclusive product recommendations delivered to your inbox.</p>
                <form class="email-form" id="newsletterForm">
                    <input type="email" class="email-input" placeholder="Enter your email address" required id="emailInput">
                    <button type="submit" class="btn btn-primary">Subscribe Now</button>
                </form>
                <div class="success-message" id="successMessage">
                    🎉 Thank you for subscribing! You'll receive our newsletter soon.
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>Categories</h3>
                    <a href="#">AI Technology</a>
                    <a href="#">Lifestyle</a>
                    <a href="#">Product Reviews</a>
                    <a href="#">Tutorials</a>
                </div>
                <div class="footer-section">
                    <h3>Resources</h3>
                    <a href="#">About Us</a>
                    <a href="#">Contact</a>
                    <a href="#">Privacy Policy</a>
                    <a href="#">Terms of Service</a>
                </div>
                <div class="footer-section">
                    <h3>Follow Us</h3>
                    <a href="#">Twitter</a>
                    <a href="#">LinkedIn</a>
                    <a href="#">YouTube</a>
                    <a href="#">Instagram</a>
                </div>
                <div class="footer-section">
                    <h3>Newsletter</h3>
                    <p>Subscribe to get weekly updates on the latest in tech and lifestyle.</p>
                </div>
            </div>
            <div style="border-top: 1px solid #333; padding-top: 2rem; margin-top: 2rem;">
                <p>&copy; 2025 TechLife Hub. All rights reserved.</p>
            </div>
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

        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 5px 20px rgba(0,0,0,0.1)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.boxShadow = 'none';
            }
        });

        // Newsletter subscription
        const newsletterForm = document.getElementById('newsletterForm');
        const emailInput = document.getElementById('emailInput');
        const successMessage = document.getElementById('successMessage');

        let subscribers = [];

        newsletterForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const email = emailInput.value.trim();
            if (!email) return;

            // Show loading state
            const submitBtn = this.querySelector('button[type="submit"]');
            const originalText = submitBtn.textContent;
            submitBtn.innerHTML = '<span class="loading"></span> Subscribing...';
            submitBtn.disabled = true;

            // Simulate API call
            setTimeout(() => {
                // Store email (in real app, this would go to your backend)
                subscribers.push({
                    email: email,
                    timestamp: new Date().toISOString(),
                    interests: ['AI', 'Lifestyle', 'Products']
                });

                // Show success message
                successMessage.style.display = 'block';
                emailInput.value = '';
                
                // Reset button
                submitBtn.textContent = originalText;
                submitBtn.disabled = false;

                // Hide success message after 5 seconds
                setTimeout(() => {
                    successMessage.style.display = 'none';
                }, 5000);

                console.log('New subscriber:', email);
                console.log('Total subscribers:', subscribers.length);
            }, 1500);
        });

        // Animate elements on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe all blog cards and product cards
        document.querySelectorAll('.blog-card, .product-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(card);
        });

        // Simulate affiliate link tracking
        document.querySelectorAll('.product-card .btn').forEach(button => {
            button.addEventListener('click', function(e) {
                e.preventDefault();
                const productTitle = this.closest('.product-card').querySelector('.product-title').textContent;
                
                // Track affiliate click (in real app, send to analytics)
                console.log('Affiliate click tracked:', {
                    product: productTitle,
                    timestamp: new Date().toISOString(),
                    userAgent: navigator.userAgent
                });

                // Show confirmation
                const originalText = this.textContent;
                this.textContent = 'Redirecting...';
                this.style.background = 'linear-gradient(45deg, #00b894, #55a3ff)';
                
                setTimeout(() => {
                    this.textContent = originalText;
                    this.style.background = '';
                    alert(`Thanks for your interest in ${productTitle}! In a real site, you'd be redirected to the product page.`);
                }, 1000);
            });
        });

        // Add some interactive features for blog cards
        document.querySelectorAll('.blog-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Mobile menu toggle (for smaller screens)
        const createMobileMenu = () => {
            if (window.innerWidth <= 768) {
                const nav = document.querySelector('nav');
                const navLinks = document.querySelector('.nav-links');
                
                if (!document.querySelector('.mobile-toggle')) {
                    const toggleBtn = document.createElement('button');
                    toggleBtn.className = 'mobile-toggle';
                    toggleBtn.innerHTML = '☰';
                    toggleBtn.style.cssText = `
                        background: none;
                        border: none;
                        font-size: 1.5rem;
                        cursor: pointer;
                        color: #333;
                    `;
                    
                    toggleBtn.addEventListener('click', () => {
                        navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
                    });
                    
                    nav.appendChild(toggleBtn);
                    navLinks.style.display = 'none';
                }
            }
        };

        window.addEventListener('resize', createMobileMenu);
        createMobileMenu();

        // Email validation
        emailInput.addEventListener('input', function() {
            const email = this.value;
            const isValid = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
            
            if (email && !isValid) {
                this.style.border = '2px solid #ff6b6b';
            } else {
                this.style.border = 'none';
            }
        });

        console.log('TechLife Hub Blog initialized successfully! 🚀');
    </script>
</body>
</html> 

