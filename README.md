<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adrian Martínez - GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #0a0a0a 0%, #1a0a0a 50%, #0a0a0a 100%);
            color: #e0e0e0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            overflow-x: auto;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            text-align: center;
            margin-bottom: 40px;
            padding: 40px 20px;
            background: linear-gradient(45deg, #1a0000, #330000, #1a0000);
            border-radius: 20px;
            border: 2px solid #660000;
            box-shadow: 0 0 30px rgba(255, 0, 0, 0.1);
        }
        
        .header h1 {
            font-size: 3em;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ff4444, #cc0000, #ff6666);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .header h3 {
            font-size: 1.4em;
            color: #cccccc;
            margin-bottom: 15px;
            font-weight: 300;
        }
        
        .lang-toggle {
            display: inline-flex;
            gap: 10px;
            margin-top: 10px;
        }
        
        .lang-badge {
            padding: 5px 15px;
            background: rgba(255, 0, 0, 0.1);
            border: 1px solid #660000;
            border-radius: 20px;
            color: #ff6666;
            font-size: 0.9em;
        }
        
        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .section {
            background: linear-gradient(135deg, #1a0000, #2a0000);
            border: 2px solid #660000;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 0 20px rgba(255, 0, 0, 0.1);
        }
        
        .section h2 {
            color: #ff4444;
            margin-bottom: 20px;
            font-size: 1.5em;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .info-list {
            list-style: none;
            margin-bottom: 20px;
        }
        
        .info-list li {
            margin-bottom: 12px;
            padding-left: 25px;
            position: relative;
            color: #cccccc;
            line-height: 1.6;
        }
        
        .info-list li::before {
            content: attr(data-icon);
            position: absolute;
            left: 0;
            color: #ff6666;
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-top: 20px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 10px;
            background: rgba(255, 0, 0, 0.05);
            border-radius: 8px;
            border-left: 3px solid #ff4444;
        }
        
        .contact-item a {
            color: #ff6666;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .contact-item a:hover {
            color: #ff4444;
        }
        
        .skills-section {
            grid-column: 1 / -1;
            text-align: center;
        }
        
        .skills-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        
        .skill-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(45deg, #660000, #330000);
            border: 2px solid #ff4444;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #ff6666;
            font-weight: bold;
            font-size: 0.8em;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(255, 0, 0, 0.2);
        }
        
        .skill-icon:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(255, 0, 0, 0.3);
            background: linear-gradient(45deg, #ff4444, #660000);
        }
        
        .stats-section {
            grid-column: 1 / -1;
            background: linear-gradient(135deg, #0a0a0a, #1a0000, #0a0a0a);
            border: 3px solid #990000;
            position: relative;
            overflow: hidden;
        }
        
        .stats-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent, rgba(255, 0, 0, 0.1), transparent);
            animation: shimmer 3s infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
            position: relative;
            z-index: 1;
        }
        
        .stat-card {
            background: linear-gradient(135deg, #1a0000, #330000);
            border: 2px solid #ff4444;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #ff0000, #ff6666, #ff0000);
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }
        
        .stat-number {
            font-size: 2.5em;
            font-weight: bold;
            background: linear-gradient(45deg, #ff4444, #ff6666);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
        }
        
        .stat-label {
            color: #cccccc;
            font-size: 0.9em;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .activity-visual {
            display: grid;
            grid-template-columns: repeat(20, 1fr);
            gap: 3px;
            margin: 20px 0;
            position: relative;
            z-index: 1;
        }
        
        .activity-bar {
            height: 40px;
            background: linear-gradient(180deg, #330000, #660000);
            border-radius: 4px;
            position: relative;
            overflow: hidden;
        }
        
        .activity-bar::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(180deg, #ff4444, #ff0000);
            border-radius: 4px;
            animation: fillUp 2s ease-out forwards;
        }
        
        .activity-bar.low::before { height: 20%; }
        .activity-bar.medium::before { height: 50%; }
        .activity-bar.high::before { height: 80%; }
        .activity-bar.peak::before { height: 100%; }
        
        @keyframes fillUp {
            from { height: 0; }
        }
        
        .timeline {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
            padding: 0 10px;
            color: #999999;
            font-size: 0.8em;
            position: relative;
            z-index: 1;
        }
        
        .project-highlights {
            grid-column: 1 / -1;
            text-align: center;
        }
        
        .highlights-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .highlight-card {
            background: linear-gradient(135deg, #1a0000, #2a0000);
            border: 2px solid #660000;
            border-radius: 15px;
            padding: 20px;
            position: relative;
            overflow: hidden;
        }
        
        .highlight-card::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #ff0000, #660000, #ff0000);
            border-radius: 15px;
            z-index: -1;
            animation: borderGlow 3s infinite;
        }
        
        @keyframes borderGlow {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }
        
        .highlight-title {
            color: #ff4444;
            font-size: 1.2em;
            margin-bottom: 10px;
            font-weight: bold;
        }
        
        .highlight-stats {
            color: #cccccc;
            line-height: 1.6;
        }
        
        @media (max-width: 768px) {
            .main-grid {
                grid-template-columns: 1fr;
            }
            
            .header h1 {
                font-size: 2em;
            }
            
            .activity-visual {
                grid-template-columns: repeat(10, 1fr);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Hi 👋 / ¡Hola!</h1>
            <h3>I'm Adrian Martínez • Fullstack Web Developer from Paraguay</h3>
            <div class="lang-toggle">
                <span class="lang-badge">🇬🇧 English</span>
                <span class="lang-badge">🇪🇸 Español</span>
            </div>
        </div>
        
        <div class="main-grid">
            <div class="section">
                <h2>🇬🇧 English</h2>
                <ul class="info-list">
                    <li data-icon="🔠">Working on two projects: a legal management system and an ERP (more info & links coming soon)</li>
                    <li data-icon="🌱">Currently diving deeper into system automation</li>
                    <li data-icon="🗣️">Ask me about TypeScript, fullstack systems, CRUD workflows, React or anything you like</li>
                    <li data-icon="✨">Fun fact: I'm obsessed with automating systems and workflows</li>
                </ul>
                
                <div class="contact-info">
                    <div class="contact-item">
                        <span>📧</span>
                        <a href="mailto:om1779468@gmail.com">om1779468@gmail.com</a>
                    </div>
                    <div class="contact-item">
                        <span>📱</span>
                        <span>+595 984 141 644</span>
                    </div>
                    <div class="contact-item">
                        <span>🔗</span>
                        <a href="https://www.linkedin.com/in/adrian-martinez">LinkedIn</a>
                    </div>
                </div>
            </div>
            
            <div class="section">
                <h2>🇪🇸 Español</h2>
                <ul class="info-list">
                    <li data-icon="🔠">Actualmente desarrollando dos proyectos: un sistema jurídico y un ERP (habrá novedades y enlaces pronto)</li>
                    <li data-icon="🌱">Enfocado en profundizar en automatización de sistemas</li>
                    <li data-icon="🗣️">Consultame sobre TypeScript, sistemas fullstack, CRUDs, React o lo que quieras</li>
                    <li data-icon="✨">Dato curioso: Estoy obsesionado con la automatización de sistemas y flujos de trabajo</li>
                </ul>
                
                <div class="contact-info">
                    <div class="contact-item">
                        <span>📧</span>
                        <a href="mailto:om1779468@gmail.com">om1779468@gmail.com</a>
                    </div>
                    <div class="contact-item">
                        <span>📱</span>
                        <span>+595 984 141 644</span>
                    </div>
                    <div class="contact-item">
                        <span>🔗</span>
                        <a href="https://www.linkedin.com/in/adrian-martinez">LinkedIn</a>
                    </div>
                </div>
            </div>
            
            <div class="section skills-section">
                <h2>🛠️ Languages and Tools</h2>
                <div class="skills-grid">
                    <div class="skill-icon">JS</div>
                    <div class="skill-icon">TS</div>
                    <div class="skill-icon">React</div>
                    <div class="skill-icon">Node</div>
                    <div class="skill-icon">Express</div>
                    <div class="skill-icon">PG</div>
                    <div class="skill-icon">SQLite</div>
                    <div class="skill-icon">RN</div>
                    <div class="skill-icon">HTML</div>
                    <div class="skill-icon">CSS</div>
                    <div class="skill-icon">Tailwind</div>
                    <div class="skill-icon">GitHub</div>
                    <div class="skill-icon">VSCode</div>
                </div>
            </div>
            
            <div class="section stats-section">
                <h2>📊 GitHub Stats</h2>
                
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-number">216</div>
                        <div class="stat-label">Total Commits</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">19</div>
                        <div class="stat-label">Repositories</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">12</div>
                        <div class="stat-label">New Projects</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">2.8</div>
                        <div class="stat-label">Commits/Day</div>
                    </div>
                </div>
                
                <div class="activity-visual" id="activityBars"></div>
                
                <div class="timeline">
                    <span>Jan</span>
                    <span>Feb</span>
                    <span>Mar</span>
                    <span>Apr</span>
                    <span>May</span>
                    <span>Jun</span>
                </div>
            </div>
            
            <div class="section project-highlights">
                <h2>🚀 Recent Activity</h2>
                <div class="highlights-grid">
                    <div class="highlight-card">
                        <div class="highlight-title">Junio 2025</div>
                        <div class="highlight-stats">
                            • 164 commits en 12 repositorios<br>
                            • Creación de 12 nuevos proyectos<br>
                            • Sistema jurídico en desarrollo<br>
                            • ERP en fase de arquitectura
                        </div>
                    </div>
                    <div class="highlight-card">
                        <div class="highlight-title">Mayo 2025</div>
                        <div class="highlight-stats">
                            • 52 commits en 7 repositorios<br>
                            • Enfoque en automatización<br>
                            • Optimización de workflows<br>
                            • Mejoras en TypeScript
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <script>
        // Generate activity bars
        function generateActivityBars() {
            const container = document.getElementById('activityBars');
            const activities = ['low', 'medium', 'low', 'high', 'medium', 'peak', 'high', 'low', 'medium', 'high', 'peak', 'high', 'medium', 'low', 'high', 'peak', 'medium', 'high', 'low', 'peak'];
            
            activities.forEach((level, index) => {
                const bar = document.createElement('div');
                bar.className = `activity-bar ${level}`;
                bar.style.animationDelay = `${index * 0.1}s`;
                container.appendChild(bar);
            });
        }
        
        // Initialize
        generateActivityBars();
        
        // Add some interactive effects
        document.querySelectorAll('.stat-card').forEach(card => {
            card.addEventListener('mouseenter', () => {
                card.style.transform = 'translateY(-10px) scale(1.05)';
                card.style.boxShadow = '0 20px 40px rgba(255, 0, 0, 0.3)';
            });
            
            card.addEventListener('mouseleave', () => {
                card.style.transform = 'translateY(0) scale(1)';
                card.style.boxShadow = '0 0 20px rgba(255, 0, 0, 0.1)';
            });
        });
    </script>
</body>
</html>
