<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CJ Coloma - Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header with Animation */
        .hero-section {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            z-index: 2;
            flex: 1;
            padding: 2rem;
        }

        .hero-animation {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        /* Coding Animation */
        .coding-container {
            width: 400px;
            height: 300px;
            background: rgba(0, 0, 0, 0.8);
            border-radius: 20px;
            padding: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .code-header {
            display: flex;
            gap: 8px;
            margin-bottom: 15px;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .dot.red { background: #ff5f56; }
        .dot.yellow { background: #ffbd2e; }
        .dot.green { background: #27ca3f; }

        .code-content {
            font-family: 'Courier New', monospace;
            font-size: 12px;
            line-height: 1.5;
        }

        .code-line {
            opacity: 0;
            animation: typeWriter 0.5s ease-in-out forwards;
        }

        .code-line:nth-child(1) { animation-delay: 0.5s; color: #ff79c6; }
        .code-line:nth-child(2) { animation-delay: 1s; color: #50fa7b; }
        .code-line:nth-child(3) { animation-delay: 1.5s; color: #8be9fd; }
        .code-line:nth-child(4) { animation-delay: 2s; color: #f1fa8c; }
        .code-line:nth-child(5) { animation-delay: 2.5s; color: #bd93f9; }
        .code-line:nth-child(6) { animation-delay: 3s; color: #50fa7b; }
        .code-line:nth-child(7) { animation-delay: 3.5s; color: #ff79c6; }
        .code-line:nth-child(8) { animation-delay: 4s; color: #8be9fd; }

        .cursor {
            display: inline-block;
            width: 2px;
            height: 15px;
            background: #fff;
            animation: blink 1s infinite;
        }

        @keyframes typeWriter {
            to { opacity: 1; }
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        /* Floating Elements */
        .floating-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .floating-icon {
            position: absolute;
            animation: float 6s ease-in-out infinite;
            opacity: 0.1;
            font-size: 2rem;
        }

        .floating-icon:nth-child(1) { top: 10%; left: 10%; animation-delay: 0s; }
        .floating-icon:nth-child(2) { top: 20%; right: 15%; animation-delay: 1s; }
        .floating-icon:nth-child(3) { bottom: 20%; left: 20%; animation-delay: 2s; }
        .floating-icon:nth-child(4) { bottom: 15%; right: 10%; animation-delay: 3s; }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Typography */
        .hero-title {
            font-size: 4rem;
            font-weight: 800;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease infinite;
            margin-bottom: 1rem;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0;
            animation: slideInLeft 1s ease 0.5s forwards;
        }

        .hero-description {
            font-size: 1.1rem;
            line-height: 1.6;
            opacity: 0;
            animation: slideInLeft 1s ease 1s forwards;
            margin-bottom: 2rem;
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Buttons */
        .cta-buttons {
            display: flex;
            gap: 1rem;
            opacity: 0;
            animation: slideInLeft 1s ease 1.5s forwards;
        }

        .btn {
            padding: 12px 30px;
            border: none;
            border-radius: 25px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
        }

        .btn-secondary {
            background: transparent;
            border: 2px solid rgba(255, 255, 255, 0.3);
            color: white;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        /* Cards Section */
        .section {
            padding: 5rem 0;
            position: relative;
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.15);
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            gap: 1rem;
            margin: 2rem 0;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 1rem;
            border-radius: 10px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .skill-item:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: scale(1.05);
        }

        /* Stats Section */
        .stats-section {
            background: rgba(0, 0, 0, 0.2);
            padding: 3rem 0;
            margin: 3rem 0;
            border-radius: 20px;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            text-align: center;
        }

        .stat-item h3 {
            font-size: 3rem;
            color: #4ecdc4;
            margin-bottom: 0.5rem;
        }

        /* Quote Section */
        .quote-section {
            text-align: center;
            padding: 5rem 0;
            background: linear-gradient(135deg, rgba(0, 0, 0, 0.1), rgba(255, 255, 255, 0.1));
            border-radius: 30px;
            margin: 3rem 0;
        }

        .quote {
            font-size: 2rem;
            font-style: italic;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .quote-author {
            font-size: 1.2rem;
            opacity: 0.8;
        }

        /* Contact Section */
        .contact-section {
            text-align: center;
            padding: 3rem 0;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 1rem 2rem;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 25px;
            text-decoration: none;
            color: white;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .social-link:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero-section {
                flex-direction: column;
                text-align: center;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            .coding-container {
                width: 300px;
                height: 250px;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .social-links {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero-section">
        <div class="container">
            <div class="hero-content">
                <h1 class="hero-title">CJ Coloma</h1>
                <p class="hero-subtitle">Full Stack Developer & BSIT Graduate</p>
                <p class="hero-description">
                    Passionate about creating innovative solutions and transforming ideas into reality. 
                    Currently building amazing web applications at Telex Business Support Services.
                </p>
                <div class="cta-buttons">
                    <a href="#projects" class="btn btn-primary">View My Work</a>
                    <a href="#contact" class="btn btn-secondary">Get In Touch</a>
                </div>
            </div>
            <div class="hero-animation">
                <div class="coding-container">
                    <div class="code-header">
                        <div class="dot red"></div>
                        <div class="dot yellow"></div>
                        <div class="dot green"></div>
                    </div>
                    <div class="code-content">
                        <div class="code-line">const developer = {</div>
                        <div class="code-line">  name: 'CJ Coloma',</div>
                        <div class="code-line">  role: 'Full Stack Developer',</div>
                        <div class="code-line">  passion: 'Building Dreams',</div>
                        <div class="code-line">  skills: ['React', 'Laravel', 'Node.js'],</div>
                        <div class="code-line">  mission: 'Create Impact'</div>
                        <div class="code-line">};</div>
                        <div class="code-line">console.log('Ready to code!');<span class="cursor"></span></div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Floating Elements -->
        <div class="floating-elements">
            <div class="floating-icon">⚡</div>
            <div class="floating-icon">🚀</div>
            <div class="floating-icon">💡</div>
            <div class="floating-icon">⭐</div>
        </div>
    </section>

    <!-- About Section -->
    <section class="section">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="cards-grid">
                <div class="card">
                    <h3>🎓 Education Excellence</h3>
                    <p>BSIT Graduate and Class Valedictorian 2025 with Cum Laude honors. Strong foundation in computer science and dedication to continuous learning.</p>
                </div>
                <div class="card">
                    <h3>💼 Professional Experience</h3>
                    <p>Currently working as a Full Stack Developer at Telex Business Support Services, gaining hands-on experience in modern web technologies.</p>
                </div>
                <div class="card">
                    <h3>🚀 Innovation Mindset</h3>
                    <p>Passionate about applying cutting-edge technologies to solve real-world problems and create impactful IT solutions.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="section">
        <div class="container">
            <h2 class="section-title">Tech Arsenal</h2>
            <div class="cards-grid">
                <div class="card">
                    <h3>Frontend Technologies</h3>
                    <div class="skills-grid">
                        <div class="skill-item">React</div>
                        <div class="skill-item">Next.js</div>
                        <div class="skill-item">Vue.js</div>
                        <div class="skill-item">TypeScript</div>
                        <div class="skill-item">Tailwind</div>
                        <div class="skill-item">Bootstrap</div>
                    </div>
                </div>
                <div class="card">
                    <h3>Backend & Database</h3>
                    <div class="skills-grid">
                        <div class="skill-item">Laravel</div>
                        <div class="skill-item">Node.js</div>
                        <div class="skill-item">PHP</div>
                        <div class="skill-item">MySQL</div>
                        <div class="skill-item">MongoDB</div>
                        <div class="skill-item">Express</div>
                    </div>
                </div>
                <div class="card">
                    <h3>Mobile & Tools</h3>
                    <div class="skills-grid">
                        <div class="skill-item">Flutter</div>
                        <div class="skill-item">React Native</div>
                        <div class="skill-item">Git</div>
                        <div class="skill-item">Docker</div>
                        <div class="skill-item">AWS</div>
                        <div class="skill-item">Figma</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats-section">
        <div class="container">
            <h2 class="section-title">Achievements</h2>
            <div class="stats-grid">
                <div class="stat-item">
                    <h3>1000+</h3>
                    <p>GitHub Contributions</p>
                </div>
                <div class="stat-item">
                    <h3>15+</h3>
                    <p>Projects Completed</p>
                </div>
                <div class="stat-item">
                    <h3>2025</h3>
                    <p>Valedictorian</p>
                </div>
                <div class="stat-item">
                    <h3>∞</h3>
                    <p>Lines of Code</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Current Projects -->
    <section class="section" id="projects">
        <div class="container">
            <h2 class="section-title">Featured Projects</h2>
            <div class="cards-grid">
                <div class="card">
                    <h3>🔍 TrackIO</h3>
                    <p>Advanced employee monitoring system with real-time analytics and comprehensive reporting features.</p>
                </div>
                <div class="card">
                    <h3>🗳️ VoSys</h3>
                    <p>OLSHCO Online Voting System for College Department with secure authentication and live results.</p>
                </div>
                <div class="card">
                    <h3>🛒 E-commerce Platform</h3>
                    <p>Modern responsive web and mobile e-commerce solutions with payment integration.</p>
                </div>
                <div class="card">
                    <h3>🏢 BrgyBiclatan</h3>
                    <p>Comprehensive barangay management system for efficient local government operations.</p>
                </div>
                <div class="card">
                    <h3>🌍 Tourist Web Mobile</h3>
                    <p>Interactive travel and tourism application with booking and recommendation features.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Quote Section -->
    <section class="quote-section">
        <div class="container">
            <div class="quote">"Innovation distinguishes between a leader and a follower"</div>
            <div class="quote-author">- Steve Jobs</div>
            <br><br>
            <div class="quote">"Code is like humor. When you have to explain it, it's bad"</div>
            <div class="quote-author">- Cory House</div>
            <br><br>
            <div class="quote">"The only way to do great work is to love what you do"</div>
            <div class="quote-author">- Steve Jobs</div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact-section" id="contact">
        <div class="container">
            <h2 class="section-title">Let's Connect</h2>
            <p>Ready to collaborate on your next project? Let's build something amazing together!</p>
            <div class="social-links">
                <a href="https://github.com/LEVi19xx" class="social-link">
                    <span>💻</span>
                    GitHub
                </a>
                <a href="https://ph.linkedin.com/in/charmaine-joyce-coloma-60588437b" class="social-link">
                    <span>💼</span>
                    LinkedIn
                </a>
            </div>
        </div>
    </section>
</body>
</html>
