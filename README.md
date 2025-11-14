<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mounib's Epic Profile</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@900&family=Poppins:wght@400;600&display=swap');
        
        body {
            margin: 0;
            padding: 20px;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1a2e 50%, #16213e 100%);
            color: #fff;
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        /* 3D Animated Name */
        .name-container {
            text-align: center;
            perspective: 1000px;
            margin: 50px 0;
            position: relative;
        }

        .name-3d {
            font-family: 'Orbitron', sans-serif;
            font-size: 120px;
            font-weight: 900;
            background: linear-gradient(45deg, #ff6b6b, #ee5a6f, #c44569, #ff6b6b);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientMove 3s ease infinite, float 3s ease-in-out infinite;
            text-shadow: 0 10px 30px rgba(255, 107, 107, 0.5);
            transform-style: preserve-3d;
        }

        @keyframes gradientMove {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotateX(0deg); }
            50% { transform: translateY(-20px) rotateX(10deg); }
        }

        /* Dragon Animation */
        .dragon-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 80px;
            animation: dragonFly 8s ease-in-out infinite;
            z-index: 10;
            opacity: 0;
        }

        @keyframes dragonFly {
            0% { opacity: 0; left: -10%; transform: translateY(0) scale(0.5); }
            20% { opacity: 1; }
            50% { left: 50%; transform: translateY(-30px) scale(1.2) rotate(10deg); }
            80% { opacity: 1; }
            100% { opacity: 0; left: 110%; transform: translateY(0) scale(0.5); }
        }

        /* Fire Effect */
        .fire {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .flame {
            position: absolute;
            width: 40px;
            height: 40px;
            background: radial-gradient(circle, #ff6b00 0%, #ff0000 50%, transparent 70%);
            border-radius: 50%;
            animation: fireRise 2s ease-in-out infinite;
            opacity: 0;
        }

        @keyframes fireRise {
            0% { transform: translateY(0) scale(1); opacity: 1; }
            100% { transform: translateY(-200px) scale(0); opacity: 0; }
        }

        /* About Section */
        .section {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin: 30px 0;
            border: 2px solid rgba(255, 107, 107, 0.3);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            animation: fadeInUp 1s ease;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 36px;
            color: #ff6b6b;
            margin-bottom: 20px;
            text-shadow: 0 0 20px rgba(255, 107, 107, 0.5);
        }

        .intro {
            font-size: 20px;
            line-height: 1.8;
            color: #e0e0e0;
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 30px 20px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            position: relative;
            overflow: hidden;
        }

        .skill-card:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: #ff6b6b;
            box-shadow: 0 20px 40px rgba(255, 107, 107, 0.3);
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 107, 107, 0.1) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .skill-card:hover::before {
            opacity: 1;
        }

        .skill-icon {
            font-size: 60px;
            margin-bottom: 15px;
            display: inline-block;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .skill-name {
            font-size: 18px;
            font-weight: 600;
            color: #fff;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(255, 107, 107, 0.1), rgba(196, 69, 105, 0.1));
            border-radius: 15px;
            padding: 30px;
            border: 2px solid rgba(255, 107, 107, 0.3);
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(255, 107, 107, 0.4);
            border-color: #ff6b6b;
        }

        .project-title {
            font-size: 24px;
            font-weight: 600;
            color: #ff6b6b;
            margin-bottom: 15px;
        }

        .project-tech {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-top: 15px;
        }

        .tech-tag {
            background: rgba(255, 107, 107, 0.2);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 14px;
            border: 1px solid rgba(255, 107, 107, 0.5);
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 40px 0;
        }

        .social-btn {
            background: linear-gradient(135deg, #ff6b6b, #c44569);
            color: white;
            padding: 15px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 18px;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(255, 107, 107, 0.3);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .social-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 50px rgba(255, 107, 107, 0.5);
        }

        /* Stats Section */
        .stats-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 30px;
            margin: 30px 0;
        }

        .stat-box {
            text-align: center;
            padding: 20px;
        }

        .stat-number {
            font-size: 48px;
            font-weight: 900;
            color: #ff6b6b;
            font-family: 'Orbitron', sans-serif;
        }

        .stat-label {
            font-size: 16px;
            color: #aaa;
            margin-top: 10px;
        }

        @media (max-width: 768px) {
            .name-3d {
                font-size: 60px;
            }
            
            h2 {
                font-size: 28px;
            }
        }
    </style>
</head>
<body>
    <div class="fire" id="fireContainer"></div>
    <div class="dragon-container">🐉</div>
    
    <div class="container">
        <!-- Animated 3D Name -->
        <div class="name-container">
            <h1 class="name-3d">MOUNIB</h1>
        </div>

        <!-- About Section -->
        <div class="section">
            <h2>🚀 Full Stack Developer & AI Enthusiast</h2>
            <p class="intro">
                Hey there! I'm <strong>Mounib</strong>, a passionate programmer and problem solver on a journey to master the art of code. 
                Currently pursuing my <strong>Artificial Intelligence Degree</strong>, I'm transforming ideas into reality through elegant code and innovative solutions. 
                I believe in continuous learning, creative problem-solving, and building things that make a difference! 💡
            </p>
        </div>

        <!-- Skills Section -->
        <div class="section">
            <h2>⚡ Tech Arsenal</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <div class="skill-icon">🐍</div>
                    <div class="skill-name">Python</div>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">⚙️</div>
                    <div class="skill-name">C++</div>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🗄️</div>
                    <div class="skill-name">SQL</div>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🎨</div>
                    <div class="skill-name">CSS</div>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🌐</div>
                    <div class="skill-name">HTML</div>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🤝</div>
                    <div class="skill-name">Google Colab</div>
                </div>
            </div>
        </div>

        <!-- Projects Section -->
        <div class="section">
            <h2>🔥 Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-title">🎨 Web Design Masterpiece</div>
                    <p>Crafted stunning, responsive web interfaces with modern CSS animations and HTML5 structure.</p>
                    <div class="project-tech">
                        <span class="tech-tag">HTML</span>
                        <span class="tech-tag">CSS</span>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-title">🐍 Python Automation Suite</div>
                    <p>Built powerful automation scripts and data processing tools that save hours of manual work.</p>
                    <div class="project-tech">
                        <span class="tech-tag">Python</span>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-title">🤖 AI/ML Experiments</div>
                    <p>Exploring machine learning algorithms and AI models in Google Colab for innovative solutions.</p>
                    <div class="project-tech">
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">Colab</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Stats -->
        <div class="section">
            <div class="stats-container">
                <div class="stat-box">
                    <div class="stat-number">6+</div>
                    <div class="stat-label">Technologies Mastered</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">∞</div>
                    <div class="stat-label">Lines of Code</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">🔥</div>
                    <div class="stat-label">Passion for Coding</div>
                </div>
            </div>
        </div>

        <!-- Education -->
        <div class="section">
            <h2>🎓 Education</h2>
            <p class="intro" style="font-size: 22px;">
                <strong>🤖 Artificial Intelligence Degree</strong><br>
                Diving deep into the world of AI, machine learning, and intelligent systems. Building the future, one algorithm at a time!
            </p>
        </div>

        <!-- Social Links -->
        <div class="social-links">
            <a href="https://instagram.com/yourusername" class="social-btn" target="_blank">
                📸 Instagram
            </a>
            <a href="https://github.com/yourusername" class="social-btn" target="_blank">
                💻 GitHub
            </a>
        </div>

        <!-- Footer -->
        <div style="text-align: center; margin: 50px 0; color: #888;">
            <p>✨ Always learning, always coding, always creating ✨</p>
            <p>💬 Let's connect and build something amazing together!</p>
        </div>
    </div>

    <script>
        // Fire effect that targets skills
        function createFlame() {
            const fireContainer = document.getElementById('fireContainer');
            const skillCards = document.querySelectorAll('.skill-card');
            
            skillCards.forEach(card => {
                if (Math.random() > 0.7) {
                    const rect = card.getBoundingClientRect();
                    const flame = document.createElement('div');
                    flame.className = 'flame';
                    flame.style.left = (rect.left + rect.width / 2) + 'px';
                    flame.style.top = (rect.top + rect.height / 2) + 'px';
                    flame.style.animationDelay = Math.random() + 's';
                    fireContainer.appendChild(flame);
                    
                    setTimeout(() => flame.remove(), 2000);
                }
            });
        }

        setInterval(createFlame, 800);

        // Add parallax effect on mouse move
        document.addEventListener('mousemove', (e) => {
            const moveX = (e.clientX - window.innerWidth / 2) * 0.01;
            const moveY = (e.clientY - window.innerHeight / 2) * 0.01;
            
            document.querySelector('.name-3d').style.transform = 
                `translateY(-20px) rotateX(${moveY}deg) rotateY(${moveX}deg)`;
        });
    </script>
</body>
</html>
