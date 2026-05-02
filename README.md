<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abhishek - Portfolio</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap"
        rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #2563eb;
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
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #2563eb;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: #333;
            margin: 3px 0;
            transition: 0.3s;
        }

        .hamburger.active span:nth-child(1) {
            transform: rotate(-45deg) translate(-5px, 6px);
        }

        .hamburger.active span:nth-child(2) {
            opacity: 0;
        }

        .hamburger.active span:nth-child(3) {
            transform: rotate(45deg) translate(-5px, -6px);
        }

        /* Hero Section */
        #hero {
            height: 100vh;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 800px;
            padding: 0 2rem;
            animation: fadeInUp 1s ease;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            opacity: 0;
            animation: fadeInUp 1s ease 0.2s forwards;
        }

        .hero-content p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0;
            animation: fadeInUp 1s ease 0.4s forwards;
        }

        .cta-buttons {
            opacity: 0;
            animation: fadeInUp 1s ease 0.6s forwards;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            margin: 0 10px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .btn-primary {
            background: white;
            color: #2563eb;
        }

        .btn-primary:hover {
            background: transparent;
            color: white;
            border-color: white;
            transform: translateY(-3px);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            border-color: white;
        }

        .btn-secondary:hover {
            background: white;
            color: #2563eb;
            transform: translateY(-3px);
        }

        /* Sections */
        section {
            padding: 100px 0;
            max-width: 1200px;
            margin: 0 auto;
            padding-left: 2rem;
            padding-right: 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 3rem;
            color: #333;
        }

        /* About Section */
        #about {
            background: #f8fafc;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 4rem;
            align-items: center;
        }

        .about-image {
            position: relative;
        }

        .about-image img {
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .about-text h3 {
            font-size: 1.8rem;
            color: #2563eb;
            margin-bottom: 1rem;
        }

        .about-text p {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            color: #666;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-tag {
            background: #2563eb;
            color: white;
            padding: 8px 16px;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 500;
        }

        /* Experience Section */
        .experience-timeline {
            max-width: 800px;
            margin: 0 auto;
        }

        .experience-item {
            display: flex;
            margin-bottom: 3rem;
            position: relative;
        }

        .experience-item::before {
            content: '';
            position: absolute;
            left: 20px;
            top: 0;
            bottom: -3rem;
            width: 2px;
            background: #e2e8f0;
        }

        .experience-date {
            min-width: 120px;
            font-weight: 600;
            color: #2563eb;
        }

        .experience-content {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            margin-left: 40px;
            position: relative;
        }

        .experience-content::before {
            content: '';
            position: absolute;
            left: -20px;
            top: 2rem;
            width: 20px;
            height: 20px;
            background: #2563eb;
            border-radius: 50%;
        }

        .experience-company {
            font-size: 1.2rem;
            font-weight: 600;
            color: #333;
            margin-bottom: 0.5rem;
        }

        .experience-role {
            color: #2563eb;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.15);
        }

        .project-image {
            height: 200px;
            background: linear-gradient(45deg, #2563eb, #1e40af);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        .project-description {
            color: #666;
            margin-bottom: 1rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
            margin-bottom: 1rem;
        }

        .project-link {
            color: #2563eb;
            text-decoration: none;
            font-weight: 500;
        }

        .project-link:hover {
            text-decoration: underline;
        }

        /* Contact Section */
        #contact {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            text-align: center;
        }

        .contact-info h3 {
            font-size: 1.5rem;
            margin-bottom: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }

        .contact-form {
            background: rgba(255, 255, 255, 0.1);
            padding: 2rem;
            border-radius: 20px;
            backdrop-filter: blur(10px);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 16px;
            border: none;
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.9);
            font-family: inherit;
            font-size: 1rem;
        }

        .form-group textarea {
            height: 120px;
            resize: vertical;
        }

        .btn-submit {
            background: white;
            color: #2563eb;
            padding: 12px 30px;
            border: none;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            width: 100%;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .btn-submit:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        /* Footer */
        footer {
            background: #1e293b;
            color: white;
            text-align: center;
            padding: 2rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 1rem;
        }

        .social-links a {
            width: 50px;
            height: 50px;
            background: #2563eb;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background: #1e40af;
            transform: translateY(-3px);
        }

        /* Animations */
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

        /* Responsive */
        @media (max-width: 768px) {
            .hamburger {
                display: flex;
            }

            .nav-links {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background-color: white;
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: 0 10px 27px rgba(0, 0, 0, 0.05);
                padding: 2rem 0;
            }

            .nav-links.active {
                left: 0;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
                gap: 2rem;
            }

            .contact-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            section {
                padding: 60px 0;
                padding-left: 1rem;
                padding-right: 1rem;
            }

            .experience-item {
                flex-direction: column;
                text-align: center;
            }

            .experience-content {
                margin-left: 0;
                margin-top: 1rem;
            }

            .experience-item::before {
                display: none;
            }
        }
    </style>
</head>
<link rel="icon" href="i-con.jpeg" type="image/png">

<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo">Abhishek</div>
            <ul class="nav-links">
                <li><a href="#hero">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="hero">
        <div class="hero-content">
            <h1>Hi, I'm <span style="color: #ffd700;">Abhishek</span></h1>
            <p>Full Stack Developer & Problem Solver | Passionate about creating innovative web solutions</p>
            <div class="cta-buttons">
                <a href="#projects" class="btn btn-primary">View My Work</a>
                <a href="#contact" class="btn btn-secondary">Get In Touch</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2 class="section-title">About Me</h2>
        <div class="about-content"> 
            <div class="about-image">
                <div
                    style="width: 100%; height: 400px; background: linear-gradient(45deg, #2563eb, #1e40af); border-radius: 20px; display: flex; align-items: center; justify-content: center; color: white; font-size: 4rem;">
                    <i class="fas fa-user"></i>
                </div>
            </div>
            <div class="about-text">
                <h3>Full Stack Developer</h3>
                <p>I'm a passionate developer with 2+ Months of experience building scalable web applications. I love
                    turning complex problems into simple, beautiful solutions. Currently focused on React, Node.js, and
                    modern web technologies.</p>
                <p>When I'm not coding, you'll find me exploring new technologies, contributing to open source, or
                    playing cricket.</p>
                <div class="skills">
                    <span class="skill-tag">React</span>
                    <span class="skill-tag">Node.js</span>
                    <span class="skill-tag">JavaScript</span>
                    <span class="skill-tag">Python</span>
                    <span class="skill-tag">MongoDB</span>
                    <span class="skill-tag">AWS</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience">
        <h2 class="section-title">Experience</h2>
        <div class="experience-timeline">
            <div class="experience-item">
                <div class="experience-date">2026 - Present</div>
                <div class="experience-content">
                    <div class="experience-company">TechCorp Solutions</div>
                    <div class="experience-role">Senior Full Stack Developer</div>
                    <p>Led development of enterprise web applications serving 10K+ users. Implemented microservices
                        architecture and optimized performance by 40%.</p>
                </div>
            </div>
            </div>
            
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" style="background: #f8fafc;">
        <h2 class="section-title">Featured Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-image">
                    <i class="fas fa-shopping-cart"></i>
                </div>
                <div class="project-content">
                    <h3 class="project-title">E-Commerce Platform</h3>
                    <p class="project-description">Full stack e-commerce solution with payment integration, admin
                        dashboard, and real-time inventory management.</p>
                    <div class="project-tech">
                        <span class="skill-tag">React</span>
                        <span class="skill-tag">Node.js</span>
                        <span class="skill-tag">MongoDB</span>
                    </div>
                    <a href="#" class="project-link">View Project →</a>
                </div>
            </div>
            <div class="project-card">
                <div class="project-image">
                    <i class="fas fa-tasks"></i>
                </div>
                <div class="project-content">
                    <h3 class="project-title">Task Management App</h3>
                    <p class="project-description">Collaborative task manager with drag & drop, real-time updates, and
                        team collaboration features.</p>
                    <div class="project-tech">
                        <span class="skill-tag">Next.js</span>
                        <span class="skill-tag">Socket.io</span>
                        <span class="skill-tag">PostgreSQL</span>
                    </div>
                    <a href="#" class="project-link">View Project →</a>
                </div>
            </div>
            <div class="project-card">
                <div class="project-image">
                    <i class="fas fa-chart-line"></i>
                </div>
                <div class="project-content">
                    <h3 class="project-title">Analytics Dashboard</h3>
                    <p class="project-description">Interactive dashboard with real-time data visualization, custom
                        charts, and predictive analytics features.</p>
                    <div class="project-tech">
                        <span class="skill-tag">React</span>
                        <span class="skill-tag">D3.js</span>
                        <span class="skill-tag">Node.js</span>
                    </div>
                    <a href="#" class="project-link">View Project →</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2 class="section-title" style="color: white;">Get In Touch</h2>
        <div class="contact-content">
            <div class="contact-info">
                <h3>Let's work together!</h3>
                <div class="contact-item">
                    <i class="fas fa-envelope" style="font-size: 1.5rem;"></i>
                    <span> abhsiheksingh22535@gmail.com</span>
                </div>
                <div class="contact-item">
                    <i class="fas fa-phone" style="font-size: 1.5rem;"></i>
                    <span>+91 8393003509</span>
                </div>
                <div class="contact-item">
                    <i class="fas fa-map-marker-alt" style="font-size: 1.5rem;"></i>
                    <span>Muzaffarnagr, India</span>
                </div>
            </div>
            <form class="contact-form" id="contactForm">
                <div class="form-group">
                    <input type="text" id="name" placeholder="Your Name" required>
                </div>
                <div class="form-group">
                    <input type="email" id="email" placeholder="Your Email" required>
                </div>
                <div class="form-group">
                    <input type="text" id="subject" placeholder="Subject" required>
                </div>
                <div class="form-group">
                    <textarea id="message" placeholder="Your Message" required></textarea>
                </div>
                <button type="submit" class="btn-submit">Send Message</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="social-links">
            <a
                href="https://www.linkedin.com/in/abhishek-94a92031a?utm_source=share_via&utm_content=profile&utm_medium=member_android" target="_blank"><i class="fab fa-linkedin"> </i></a>
            <a href="https://github.com/abhishek0597" target="_blank"><i class="fab fa-github"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="https://www.instagram.com/abhishek_goryan?igsh=MTR2YnYzeHgwcms4OQ==" target="_blank"><i class="fab fa-instagram"></i></a>
        </div>
        <p>&copy; 2026 Abhishek. Made with ❤️</p>
    </footer>

    <script>
        // Mobile Navigation Toggle
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');

        hamburger.addEventListener('click', () => {
            hamburger.classList.toggle('active');
            navLinks.classList.toggle('active');
        });

        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                hamburger.classList.remove('active');
                navLinks.classList.remove('active');
            });
        });

        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const nav = document.querySelector('nav');
            if (window.scrollY > 50) {
                nav.classList.add('scrolled');
            } else {
                nav.classList.remove('scrolled');
            }
        });

        // Smooth scrolling for anchor links
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

        // Contact form handling
        document.getElementById('contactForm').addEventListener('submit', function (e) {
            e.preventDefault();

            // Get form data
            const formData = {
                name: document.getElementById('name').value,
                email: document.getElementById('email').value,
                subject: document.getElementById('subject').value,
                message: document.getElementById('message').value
            };

            // Simple form submission simulation
            alert('Thank you for your message! I\'ll get back to you soon. 🚀');

            // Reset form
            this.reset();
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

        // Observe project cards and experience items
        document.querySelectorAll('.project-card, .experience-item').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>

</html>

