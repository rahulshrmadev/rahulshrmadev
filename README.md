<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rahul Sharma - GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Fira Code', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, monospace;
            background: linear-gradient(135deg, #0a0e1a 0%, #1a1a2e 25%, #16213e 50%, #0f3460 75%, #533483 100%);
            color: #e6edf3;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated starfield background */
        .starfield {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s ease-in-out infinite alternate;
        }

        @keyframes twinkle {
            0% { opacity: 0.3; transform: scale(1); }
            100% { opacity: 1; transform: scale(1.2); }
        }

        /* Floating particles */
        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            border-radius: 50%;
            animation: float 8s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) translateX(0px) rotate(0deg); }
            25% { transform: translateY(-20px) translateX(10px) rotate(90deg); }
            50% { transform: translateY(-10px) translateX(-10px) rotate(180deg); }
            75% { transform: translateY(-30px) translateX(20px) rotate(270deg); }
        }

        /* Header with glassmorphism */
        .header {
            background: rgba(10, 14, 26, 0.8);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255, 107, 107, 0.3);
            padding: 1rem 2rem;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            animation: slideDown 1s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        @keyframes slideDown {
            from { transform: translateY(-100%) rotateX(-90deg); opacity: 0; }
            to { transform: translateY(0) rotateX(0deg); opacity: 1; }
        }

        .nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 1.8rem;
            font-weight: bold;
            color: #f0f6fc;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            animation: logoSpin 4s ease-in-out infinite;
            position: relative;
            overflow: hidden;
        }

        .logo-icon::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.3), transparent);
            animation: logoShine 3s ease-in-out infinite;
        }

        @keyframes logoSpin {
            0%, 100% { transform: rotate(0deg) scale(1); }
            50% { transform: rotate(180deg) scale(1.1); }
        }

        @keyframes logoShine {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-links a {
            color: #7d8590;
            text-decoration: none;
            transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            position: relative;
            padding: 10px 15px;
            border-radius: 25px;
        }

        .nav-links a:hover {
            color: #ff6b6b;
            transform: translateY(-3px) scale(1.05);
            background: rgba(255, 107, 107, 0.1);
            box-shadow: 0 10px 25px rgba(255, 107, 107, 0.2);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            width: 0;
            height: 3px;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1);
            transition: all 0.4s ease;
            transform: translateX(-50%);
            border-radius: 5px;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Main Container */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 140px 2rem 4rem;
            position: relative;
            z-index: 1;
        }

        /* Hero Section */
        .hero-section {
            text-align: center;
            margin-bottom: 4rem;
            animation: fadeInUp 1s ease-out;
        }

        .hero-title {
            font-size: 4rem;
            font-weight: bold;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 3s ease-in-out infinite;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: #7d8590;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .typing-animation {
            font-size: 1.3rem;
            color: #4ecdc4;
            margin-bottom: 3rem;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        @keyframes fadeInUp {
            from { transform: translateY(50px) rotateX(-45deg); opacity: 0; }
            to { transform: translateY(0) rotateX(0deg); opacity: 1; }
        }

        /* Profile Section */
        .profile-section {
            display: grid;
            grid-template-columns: 350px 1fr;
            gap: 4rem;
            margin-bottom: 4rem;
        }

        .profile-card {
            background: rgba(26, 26, 46, 0.6);
            backdrop-filter: blur(25px);
            border: 2px solid transparent;
            background-clip: padding-box;
            border-radius: 25px;
            padding: 2.5rem;
            text-align: center;
            animation: slideInLeft 1.2s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            position: relative;
            overflow: hidden;
        }

        .profile-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            border-radius: 25px;
            padding: 2px;
            mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            mask-composite: subtract;
            z-index: -1;
            animation: borderGlow 3s ease-in-out infinite;
        }

        @keyframes borderGlow {
            0%, 100% { opacity: 0.7; transform: rotate(0deg); }
            50% { opacity: 1; transform: rotate(180deg); }
        }

        .profile-card::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 107, 107, 0.1), transparent);
            animation: cardShimmer 4s ease-in-out infinite;
        }

        @keyframes cardShimmer {
            0% { transform: translateX(-100%) translateY(-100%) rotate(0deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        @keyframes slideInLeft {
            from { transform: translateX(-100%) rotateY(-90deg); opacity: 0; }
            to { transform: translateX(0) rotateY(0deg); opacity: 1; }
        }

        .profile-avatar {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            margin: 0 auto 1.5rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            padding: 6px;
            animation: profilePulse 2s ease-in-out infinite;
            position: relative;
        }

        @keyframes profilePulse {
            0%, 100% { transform: rotate(0deg) scale(1); box-shadow: 0 0 30px rgba(255, 107, 107, 0.5); }
            50% { transform: rotate(180deg) scale(1.05); box-shadow: 0 0 50px rgba(78, 205, 196, 0.8); }
        }

        .avatar-img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: linear-gradient(45deg, #1a1a2e, #16213e);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            animation: avatarSpin 3s ease-in-out infinite reverse;
        }

        @keyframes avatarSpin {
            0%, 100% { transform: rotate(0deg); }
            50% { transform: rotate(-180deg); }
        }

        .profile-name {
            font-size: 2.2rem;
            font-weight: bold;
            margin-bottom: 0.8rem;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: nameGlow 2s ease-in-out infinite alternate;
        }

        @keyframes nameGlow {
            0% { filter: drop-shadow(0 0 5px rgba(255, 107, 107, 0.5)); }
            100% { filter: drop-shadow(0 0 15px rgba(78, 205, 196, 0.8)); }
        }

        .profile-username {
            color: #7d8590;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            animation: fadeInUp 1s ease-out 0.8s both;
        }

        .profile-bio {
            color: #e6edf3;
            line-height: 1.8;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease-out 1s both;
        }

        .connect-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-bottom: 2rem;
        }

        .connect-btn {
            padding: 12px 24px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            position: relative;
            overflow: hidden;
        }

        .btn-linkedin {
            background: linear-gradient(45deg, #0077b5, #00a0dc);
            color: white;
        }

        .btn-gmail {
            background: linear-gradient(45deg, #d44638, #ea4335);
            color: white;
        }

        .connect-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
        }

        .connect-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }

        .connect-btn:hover::before {
            left: 100%;
        }

        /* Stats Section */
        .stats-section {
            animation: slideInRight 1.2s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        @keyframes slideInRight {
            from { transform: translateX(100%) rotateY(90deg); opacity: 0; }
            to { transform: translateX(0) rotateY(0deg); opacity: 1; }
        }

        .about-section {
            background: rgba(26, 26, 46, 0.6);
            backdrop-filter: blur(25px);
            border: 1px solid rgba(255, 107, 107, 0.2);
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease-out 0.5s both;
        }

        .section-title {
            font-size: 1.8rem;
            font-weight: bold;
            margin-bottom: 1.5rem;
            color: #ff6b6b;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .about-list {
            list-style: none;
            space-y: 1rem;
        }

        .about-item {
            color: #e6edf3;
            margin-bottom: 1rem;
            padding: 0.8rem 1.2rem;
            background: rgba(69, 183, 209, 0.1);
            border-radius: 12px;
            border-left: 4px solid #4ecdc4;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .about-item:hover {
            transform: translateX(10px);
            background: rgba(69, 183, 209, 0.2);
            box-shadow: 0 5px 20px rgba(78, 205, 196, 0.2);
        }

        .about-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(78, 205, 196, 0.1), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s ease;
        }

        .about-item:hover::before {
            transform: translateX(100%);
        }

        /* Tech Stack */
        .tech-section {
            background: rgba(26, 26, 46, 0.6);
            backdrop-filter: blur(25px);
            border: 1px solid rgba(78, 205, 196, 0.2);
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease-out 0.7s both;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(60px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .tech-icon {
            width: 60px;
            height: 60px;
            background: rgba(69, 183, 209, 0.1);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            border: 2px solid transparent;
            position: relative;
            cursor: pointer;
        }

        .tech-icon:hover {
            transform: translateY(-10px) rotateY(180deg) scale(1.1);
            background: rgba(255, 107, 107, 0.2);
            border-color: #ff6b6b;
            box-shadow: 0 15px 30px rgba(255, 107, 107, 0.3);
        }

        .tech-icon::after {
            content: attr(data-tech);
            position: absolute;
            bottom: -30px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 0.8rem;
            color: #7d8590;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .tech-icon:hover::after {
            opacity: 1;
        }

        /* GitHub Stats */
        .github-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .stat-card {
            background: rgba(26, 26, 46, 0.6);
            backdrop-filter: blur(25px);
            border: 1px solid rgba(150, 206, 180, 0.2);
            border-radius: 20px;
            padding: 1.5rem;
            text-align: center;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            animation: fadeInUp 1s ease-out 1.2s both;
        }

        .stat-card:hover {
            transform: translateY(-8px) rotateX(5deg);
            border-color: #96ceb4;
            box-shadow: 0 20px 40px rgba(150, 206, 180, 0.2);
        }

        .stat-card img {
            width: 100%;
            border-radius: 12px;
            transition: all 0.3s ease;
        }

        .stat-card:hover img {
            transform: scale(1.02);
        }

        /* Contribution Graph */
        .contribution-section {
            background: rgba(26, 26, 46, 0.6);
            backdrop-filter: blur(25px);
            border: 1px solid rgba(255, 107, 107, 0.2);
            border-radius: 20px;
            padding: 2rem;
            margin: 3rem 0;
            text-align: center;
            animation: fadeInUp 1s ease-out 1.5s both;
        }

        .snake-animation {
            width: 100%;
            max-width: 800px;
            margin: 2rem auto;
            filter: drop-shadow(0 0 20px rgba(78, 205, 196, 0.3));
        }

        /* Activity Graph */
        .activity-section {
            background: rgba(26, 26, 46, 0.6);
            backdrop-filter: blur(25px);
            border: 1px solid rgba(69, 183, 209, 0.2);
            border-radius: 20px;
            padding: 2rem;
            margin: 3rem 0;
            text-align: center;
            animation: fadeInUp 1s ease-out 1.8s both;
        }

        .activity-graph {
            width: 100%;
            border-radius: 12px;
            margin-top: 1.5rem;
            filter: drop-shadow(0 0 20px rgba(69, 183, 209, 0.3));
        }

        /* Support Section */
        .support-section {
            background: rgba(26, 26, 46, 0.6);
            backdrop-filter: blur(25px);
            border: 1px solid rgba(150, 206, 180, 0.2);
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            animation: fadeInUp 1s ease-out 2s both;
        }

        .code-block {
            background: rgba(0, 0, 0, 0.4);
            border: 1px solid rgba(78, 205, 196, 0.3);
            border-radius: 12px;
            padding: 1.5rem;
            margin: 1.5rem 0;
            font-family: 'Fira Code', monospace;
            color: #4ecdc4;
            font-size: 1.1rem;
            position: relative;
            overflow: hidden;
        }

        .code-block::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(78, 205, 196, 0.1), transparent);
            animation: codeShine 3s ease-in-out infinite;
        }

        @keyframes codeShine {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero-title { font-size: 2.5rem; }
            .hero-subtitle { font-size: 1.2rem; }
            .profile-section { grid-template-columns: 1fr; gap: 2rem; }
            .nav-links { display: none; }
            .container { padding: 120px 1rem 2rem; }
            .tech-grid { grid-template-columns: repeat(auto-fit, minmax(50px, 1fr)); }
            .github-stats { grid-template-columns: 1fr; }
        }

        /* Scrollbar Styling */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: rgba(26, 26, 46, 0.3);
        }

        ::-webkit-scrollbar-thumb {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(45deg, #4ecdc4, #45b7d1);
        }
    </style>
</head>
<body>
    <div class="starfield" id="starfield"></div>
    
    <header class="header">
        <nav class="nav">
            <div class="logo">
                <div class="logo-icon">🚀</div>
                rahulshrmadev
            </div>
            <ul class="nav-links">
                <li><a href="#about">About</a></li>
                <li><a href="#tech">Tech Stack</a></li>
                <li><a href="#stats">Stats</a></li>
                <li><a href="#connect">Connect</a></li>
            </ul>
        </nav>
    </header>

    <div class="container">
        <!-- Hero Section -->
        <section class="hero-section">
            <h1 class="hero-title">Hi 👋, I'm Rahul Sharma</h1>
            <h3 class="hero-subtitle">System Developer | RL Enthusiast | Full-Stack Dev</h3>
            <div class="typing-animation" id="typingText">Full-Stack Dev 💻</div>
        </section>

        <!-- Profile Section -->
        <section class="profile-section">
            <div class="profile-card">
                <div class="profile-avatar">
                    <div class="avatar-img">👨‍💻</div>
                </div>
                <h2 class="profile-name">Rahul Sharma</h2>
                <p class="profile-username">@rahulshrmadev</p>
                <p class="profile-bio">
                    System Engineer by Soul 🧡<br>
                    RL Researcher at Heart 🔬<br>
                    Full-Stack Developer 💻
                </p>
                <div class="connect-buttons">
                    <a href="https://linkedin.com/in/rahulshrmadev" class="connect-btn btn-linkedin">
                        💼 LinkedIn
                    </a>
                    <a href="mailto:rahulshrmadev@gmail.com" class="connect-btn btn-gmail">
                        📧 Gmail
                    </a>
                </div>
            </div>

            <div class="stats-section">
                <div class="about-section" id="about">
                    <h3 class="section-title">🧠 About Me</h3>
                    <ul class="about-list">
                        <li class="about-item">🔭 Currently working on <strong>Full-stack ERP/CRM apps</strong></li>
                        <li class="about-item">🌱 Learning more about <strong>Reinforcement Learning & System Design</strong></li>
                        <li class="about-item">💬 Ask me about: <strong>JavaScript, Node.js, MongoDB, Linux, Git, React, NestJS</strong></li>
                        <li class="about-item">⚡ Fun fact: I love debugging more than coding sometimes 🐞</li>
                    </ul>
                </div>

                <div class="tech-section" id="tech">
                    <h3 class="section-title">🛠️ Tech Stack</h3>
                    <div class="tech-grid">
                        <div class="tech-icon" data-tech="JavaScript">⚡</div>
                        <div class="tech-icon" data-tech="TypeScript">🔷</div>
                        <div class="tech-icon" data-tech="React">⚛️</div>
                        <div class="tech-icon" data-tech="Next.js">▲</div>
                        <div class="tech-icon" data-tech="Node.js">🟢</div>
                        <div class="tech-icon" data-tech="NestJS">🔴</div>
                        <div class="tech-icon" data-tech="MongoDB">🍃</div>
                        <div class="tech-icon" data-tech="PostgreSQL">🐘</div>
                        <div class="tech-icon" data-tech="Express">🚀</div>
                        <div class="tech-icon" data-tech="Linux">🐧</div>
                        <div class="tech-icon" data-tech="Git">🌿</div>
                        <div class="tech-icon" data-tech="C++">⚙️</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- GitHub Stats -->
        <section class="github-stats" id="stats">
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api?username=rahulshrmadev&show_icons=true&hide_border=true&theme=radical" alt="GitHub Stats" />
            </div>
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=rahulshrmadev&layout=compact&hide_border=true&theme=radical" alt="Top Languages" />
            </div>
        </section>

        <!-- Contribution Snake -->
        <section class="contribution-section">
            <h3 class="section-title">⏳ GitHub Contribution Snake</h3>
            <img src="https://raw.githubusercontent.com/rahulshrmadev/rahulshrmadev/output/github-contribution-grid-snake.svg" alt="Contribution Snake" class="snake-animation" />
        </section>

        <!-- Activity Graph -->
        <section class="activity-section">
            <h3 class="section-title">📊 GitHub Activity Graph</h3>
            <img src="https://github-readme-activity-graph.vercel.app/graph?username=rahulshrmadev&theme=github-compact&hide_border=true" alt="Activity Graph" class="activity-graph" />
        </section>

        <!-- Tools Section -->
        <section class="tech-section">
            <h3 class="section-title">⚙️ Tools & IDEs I Use</h3>
            <div class="tech-grid">
                <div class="tech-icon" data-tech="VS Code">💙</div>
                <div class="tech-icon" data-tech="Figma">🎨</div>
                <div class="tech-icon" data-tech="Postman">📮</div>
                <div class="tech-icon" data-tech="Vercel">▲</div>
                <div class="tech-icon" data-tech="Netlify">🌐</div>
            </div>
        </section>

        <!-- Support Section -->
        <section class="support-section" id="connect">
            <h3 class="section-title">🙏 Support My Work</h3>
            <div class="code-block">
                git clone https://github.com/rahulshrmadev ❤️
                <br>
                npm install appreciation<br>
                yarn add encouragement<br>
                <br>
                # Your support means the world!<br>
                # Let's build something amazing together 🚀
            </div>
            <p>If you like what I do, feel free to:</p>
            <div class="connect-buttons">
                <a href="https://github.com/rahulshrmadev" class="connect-btn btn-linkedin">
                    ⭐ Star My Repos
                </a>
                <a href="https://github.com/sponsors/rahulshrmadev" class="connect-btn btn-gmail">
                    💖 Sponsor Me
                </a>
            </div>
        </section>
    </div>

    <script>
        // Create starfield
        const starfield = document.getElementById('starfield');
        for (let i = 0; i < 200; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            star.style.width = `${Math.random() * 3}px`;
            star.style.height = star.style.width;
            star.style.left = `${Math.random() * 100}%`;
            star.style.top = `${Math.random() * 100}%`;
            star.style.animationDelay = `${Math.random() * 3}s`;
            star.style.opacity = Math.random();
            starfield.appendChild(star);
        }

        // Create floating particles
        for (let i = 0; i < 15; i++) {
            const particle = document.createElement('div');
            particle.classList.add('particle');
            particle.style.left = `${Math.random() * 100}%`;
            particle.style.top = `${Math.random() * 100}%`;
            particle.style.animationDelay = `${Math.random() * 8}s`;
            particle.style.width = `${4 + Math.random() * 4}px`;
            particle.style.height = particle.style.width;
            document.body.appendChild(particle);
        }

        // Typing animation
        const typingText = document.getElementById('typingText');
        const texts = [
            "Full-Stack Developer 💻", 
            "System Engineer 🖥️",
            "RL Enthusiast 🤖",
            "Open Source Contributor 🌍",
            "Problem Solver 🧩"
        ];
        let currentText = 0;
        let charIndex = 0;
        let isDeleting = false;
        let isEnd = false;

        function type() {
            const fullText = texts[currentText];
            
            if (isDeleting) {
                typingText.textContent = fullText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingText.textContent = fullText.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === fullText.length) {
                isEnd = true;
                setTimeout(() => {
                    isDeleting = true;
                }, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                currentText = (currentText + 1) % texts.length;
            }
            

            const speed = isDeleting ? 50 : isEnd ? 100 : 150;
            setTimeout(type, speed);
            
            if (isEnd) isEnd = false;
        }

        setTimeout(type, 1000);

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
