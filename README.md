<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mounib's Epic Profile</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@900&family=Poppins:wght@400;600&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #0a0e27 0%, #1a1a2e 50%, #16213e 100%);
            color: #fff;
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        /* 3D Animated Name */
        .name-container {
            text-align: center;
            perspective: 1000px;
            margin: 80px 0 60px 0;
            position: relative;
            height: 200px;
        }

        .name-3d {
            font-family: 'Orbitron', sans-serif;
            font-size: 100px;
            font-weight: 900;
            background: linear-gradient(45deg, #ff6b6b, #ee5a6f, #c44569, #ff6b6b);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientMove 3s ease infinite, float 3s ease-in-out infinite;
            text-shadow: 0 10px 30px rgba(255, 107, 107, 0.5);
            transform-style: preserve-3d;
            position: relative;
            z-index: 1;
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
        .dragon {
            position: absolute;
            font-size: 60px;
            z-index: 100;
            animation: dragonFly 10s linear infinite;
            filter: drop-shadow(0 0 20px rgba(255, 107, 107, 0.8));
        }

        @keyframes dragonFly {
            0% { 
                left: -10%; 
                top: 20%;
                transform: scale(0.5) rotate(-10deg);
                opacity: 0;
            }
            10% { opacity: 1; }
            50% { 
                left: 50%; 
                top: 10%;
                transform: scale(1.2) rotate(5deg);
            }
            90% { opacity: 1; }
            100% { 
                left: 110%; 
                top: 30%;
                transform: scale(0.5) rotate(10deg);
                opacity: 0;
            }
        }

        /* Fire particles */
        .fire-particle {
            position: absolute;
            width: 8px;
            height: 8px;
            background: radial-gradient(circle, #ff6b00 0%, #ff0000 50%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
            animation: fireParticle 1.5s ease-out forwards;
        }

        @keyframes fireParticle {
            0% { 
                transform: translate(0, 0) scale(1);
                opacity: 1;
            }
            100% { 
                transform: translate(var(--tx), var(--ty)) scale(0);
                opacity: 0;
            }
        }

        /* Sections */
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
            font-size: 18px;
            line-height: 1.8;
            color: #e0e0e0;
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 25px 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            position: relative;
            cursor: pointer;
        }

        .skill-card:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: #ff6b6b;
            box-shadow: 0 20px 40px rgba(255, 107, 107, 0.4);
            background: rgba(255, 107, 107, 0.1);
        }

        .skill-icon {
            font-size: 50px;
            margin-bottom: 15px;
            display: inline-block;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }

        .skill-name {
            font-size: 16px;
            font-weight: 600;
            color: #fff;
        }

        /* Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(255, 107, 107, 0.15), rgba(196, 69, 105, 0.15));
            border-radius: 15px;
            padding: 25px;
            border: 2px solid rgba(255, 107, 107, 0.3);
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 50px rgba(255, 107, 107, 0.4);
            border-color: #ff6b6b;
        }

        .project-title {
            font-size: 22px;
            font-weight: 600;
            color: #ff6b6b;
            margin-bottom: 12px;
        }

        .project-tech {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
            margin-top: 15px;
        }

        .tech-tag {
            background: rgba(255, 107, 107, 0.2);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 13px;
            border: 1px solid rgba(255, 107, 107, 0.5);
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin: 40px 0;
            flex-wrap: wrap;
        }

        .social-btn {
            background: linear-gradient(135deg, #ff6b6b, #c44569);
            color: white;
            padding: 15px 35px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 16px;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(255, 107, 107, 0.3);
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .social-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 50px rgba(255, 107, 107, 0.6);
        }

        /* Stats */
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
            font-size: 14px;
            color: #aaa;
            margin-top: 8px;
        }

        .footer {
            text-align: center;
            margin: 50px 0 30px 0;
            color: #888;
            font-size: 14px;
        }

        @media (max-width: 768px) {
            .name-3d {
                font-size: 50px;
            }
            h2 {
                font-size: 28px;
            }
            .section {
                padding: 25px;
            }
        }
    </style>
</head>
<body>
    <div class="dragon">🐉</div>
    
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
                <div class="skill-card" data-skill="python">
                    <div class="skill-icon">🐍</div>
                    <div class="skill-name">Python</div>
                </div>
                <div class="skill-card" data-skill="cpp">
                    <div class="skill-icon">⚙️</div>
                    <div class="skill-name">C++</div>
                </div>
                <div class="skill-card" data-skill="sql">
                    <div class="skill-icon">🗄️</div>
                    <div class="skill-name">SQL</div>
                </div>
                <div class="skill-card" data-skill="css">
                    <div class="skill-icon">🎨</div>
                    <div class="skill-name">CSS</div>
                </div>
                <div class="skill-card" data-skill="html">
                    <div class="skill-icon">🌐</div>
                    <div class="skill-name">HTML</div>
                </div>
                <div class="skill-card" data-skill="colab">
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
            <p class="intro" style="font-size: 20px;">
                <strong>🤖 Artificial Intelligence Degree</strong><br>
                Diving deep into the world of AI, machine learning, and intelligent systems. Building the future, one algorithm at a time!
            </p>
        </div>

        <!-- Social Links -->
        <div class="social-links">
            <a href="https://instagram.com/yourusername" class="social-btn" target="_blank">
                📸 Follow on Instagram
            </a>
            <a href="https://github.com/yourusername" class="social-btn" target="_blank">
                💻 GitHub Profile
            </a>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p style="font-size: 16px; margin-bottom: 10px;">✨ Always learning, always coding, always creating ✨</p>
            <p>💬 Let's connect and build something amazing together!</p>
        </div>
    </div>

    <script>
        // Fire particles on skill hover
        document.querySelectorAll('.skill-card').forEach(card => {
            card.addEventListener('mouseenter', function(e) {
                const rect = this.getBoundingClientRect();
                const centerX = rect.left + rect.width / 2;
                const centerY = rect.top + rect.height / 2;
                
                for (let i = 0; i < 15; i++) {
                    setTimeout(() => {
                        const particle = document.createElement('div');
                        particle.className = 'fire-particle';
                        
                        const angle = Math.random() * Math.PI * 2;
                        const distance = 50 + Math.random() * 100;
                        const tx = Math.cos(angle) * distance;
                        const ty = Math.sin(angle) * distance;
                        
                        particle.style.left = centerX + 'px';
                        particle.style.top = centerY + 'px';
                        particle.style.setProperty('--tx', tx + 'px');
                        particle.style.setProperty('--ty', ty + 'px');
                        
                        document.body.appendChild(particle);
                        
                        setTimeout(() => particle.remove(), 1500);
                    }, i * 30);
                }
            });
        });

        // 3D effect on mouse move
        let mouseX = 0;
        let mouseY = 0;
        
        document.addEventListener('mousemove', (e) => {
            mouseX = (e.clientX - window.innerWidth / 2) / window.innerWidth;
            mouseY = (e.clientY - window.innerHeight / 2) / window.innerHeight;
        });
        
        function animate3DName() {
            const nameEl = document.querySelector('.name-3d');
            if (nameEl) {
                const rotateY = mouseX * 15;
                const rotateX = -mouseY * 15;
                nameEl.style.transform = `perspective(1000px) rotateY(${rotateY}deg) rotateX(${rotateX}deg)`;
            }
            requestAnimationFrame(animate3DName);
        }
        
        animate3DName();
    </script>
</body>
</html>
