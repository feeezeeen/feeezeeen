<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zeen2 - Full Stack Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            color: #2d3748;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 40px 20px;
        }
        
        /* Header Section */
        .header {
            background: white;
            border-radius: 16px;
            padding: 60px 40px;
            text-align: center;
            margin-bottom: 40px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
            animation: slideDown 0.6s ease-out;
        }
        
        .avatar {
            width: 120px;
            height: 120px;
            margin: 0 auto 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 48px;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }
        
        .header h1 {
            font-size: 36px;
            font-weight: 700;
            margin-bottom: 10px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .header .title {
            font-size: 18px;
            color: #667eea;
            margin-bottom: 15px;
            font-weight: 600;
        }
        
        .header p {
            color: #718096;
            font-size: 16px;
            line-height: 1.6;
            max-width: 500px;
            margin: 0 auto 30px;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
        }
        
        .social-links a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: #f0f4ff;
            color: #667eea;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }
        
        .social-links a:hover {
            background: #667eea;
            color: white;
            transform: translateY(-3px);
            box-shadow: 0 5px 20px rgba(102, 126, 234, 0.4);
        }
        
        /* Section Styles */
        .section {
            background: white;
            border-radius: 16px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
            animation: fadeIn 0.6s ease-out;
            animation-fill-mode: both;
        }
        
        .section:nth-child(2) { animation-delay: 0.1s; }
        .section:nth-child(3) { animation-delay: 0.2s; }
        .section:nth-child(4) { animation-delay: 0.3s; }
        
        .section h2 {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 25px;
            color: #2d3748;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .section h2::before {
            content: '';
            width: 4px;
            height: 24px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 2px;
        }
        
        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 15px;
        }
        
        .skill-badge {
            background: linear-gradient(135deg, #f0f4ff 0%, #e8ecff 100%);
            border: 2px solid #e0e7ff;
            border-radius: 10px;
            padding: 12px 16px;
            text-align: center;
            font-weight: 600;
            color: #667eea;
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .skill-badge:hover {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-color: #667eea;
            transform: translateY(-4px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.3);
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }
        
        .project-card {
            background: #f9fafb;
            border: 2px solid #e5e7eb;
            border-radius: 12px;
            padding: 24px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.3s ease;
        }
        
        .project-card:hover {
            border-color: #667eea;
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.15);
            transform: translateY(-5px);
        }
        
        .project-card:hover::before {
            transform: scaleX(1);
        }
        
        .project-card h3 {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 8px;
            color: #2d3748;
        }
        
        .project-card p {
            font-size: 14px;
            color: #718096;
            margin-bottom: 15px;
            line-height: 1.5;
        }
        
        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 15px;
        }
        
        .tech-tag {
            background: white;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            padding: 4px 10px;
            font-size: 12px;
            color: #667eea;
            font-weight: 600;
        }
        
        .project-links {
            display: flex;
            gap: 10px;
        }
        
        .project-links a {
            flex: 1;
            padding: 8px 12px;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            text-align: center;
            text-decoration: none;
            color: #667eea;
            font-size: 12px;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .project-links a:hover {
            background: #667eea;
            color: white;
            border-color: #667eea;
        }
        
        /* About Section */
        .about-content {
            line-height: 1.8;
            color: #718096;
            font-size: 15px;
        }
        
        .about-content p {
            margin-bottom: 15px;
        }
        
        .highlight {
            color: #667eea;
            font-weight: 600;
        }
        
        /* Footer */
        .footer {
            text-align: center;
            color: #718096;
            font-size: 14px;
            padding: 30px 20px;
        }
        
        .divider {
            width: 60px;
            height: 2px;
            background: linear-gradient(90deg, transparent, #667eea, transparent);
            margin: 20px auto;
        }
        
        /* Animations */
        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header {
                padding: 40px 20px;
            }
            
            .header h1 {
                font-size: 28px;
            }
            
            .section {
                padding: 25px 20px;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="avatar">
                <i class="fas fa-code"></i>
            </div>
            <h1>Zeen2</h1>
            <p class="title">Full Stack Developer | React & Node.js</p>
            <p>Building intuitive and efficient web applications with modern technologies. Passionate about clean code, user experience, and continuous learning.</p>
            
            <div class="social-links">
                <a href="#" title="GitHub"><i class="fab fa-github"></i></a>
                <a href="#" title="LinkedIn"><i class="fab fa-linkedin"></i></a>
                <a href="#" title="Twitter"><i class="fab fa-twitter"></i></a>
                <a href="#" title="Email"><i class="fas fa-envelope"></i></a>
            </div>
        </div>
        
        <!-- About Section -->
        <div class="section">
            <h2>About Me</h2>
            <div class="about-content">
                <p>I'm a junior full-stack developer with a passion for creating elegant solutions to complex problems. With expertise in both frontend and backend technologies, I enjoy working across the entire application stack to deliver complete, user-focused products.</p>
                <p>Currently focused on building with <span class="highlight">React</span>, <span class="highlight">Node.js</span>, and <span class="highlight">PostgreSQL</span>, while continuously expanding my knowledge of modern web development practices, architectural patterns, and best practices.</p>
                <p>When I'm not coding, I'm exploring new technologies, contributing to open-source projects, and sharing knowledge with the developer community.</p>
            </div>
        </div>
        
        <!-- Skills Section -->
        <div class="section">
            <h2>Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-badge">JavaScript</div>
                <div class="skill-badge">React</div>
                <div class="skill-badge">Node.js</div>
                <div class="skill-badge">Express</div>
                <div class="skill-badge">PostgreSQL</div>
                <div class="skill-badge">MongoDB</div>
                <div class="skill-badge">HTML/CSS</div>
                <div class="skill-badge">Git</div>
                <div class="skill-badge">REST APIs</div>
                <div class="skill-badge">Tailwind</div>
                <div class="skill-badge">Docker</div>
                <div class="skill-badge">AWS</div>
            </div>
        </div>
        
        <!-- Projects Section -->
        <div class="section">
            <h2>Featured Projects</h2>
            <div class="projects-grid">
                <!-- Project 1 -->
                <div class="project-card">
                    <h3>E-Commerce Platform</h3>
                    <p>Full-stack e-commerce application with user authentication, product management, and secure payment integration using Stripe.</p>
                    <div class="project-tech">
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">Node.js</span>
                        <span class="tech-tag">PostgreSQL</span>
                    </div>
                    <div class="project-links">
                        <a href="#">View Code</a>
                        <a href="#">Live Demo</a>
                    </div>
                </div>
                
                <!-- Project 2 -->
                <div class="project-card">
                    <h3>Task Management App</h3>
                    <p>Collaborative task management tool with real-time updates, user teams, and project organization features.</p>
                    <div class="project-tech">
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">Firebase</span>
                        <span class="tech-tag">Tailwind</span>
                    </div>
                    <div class="project-links">
                        <a href="#">View Code</a>
                        <a href="#">Live Demo</a>
                    </div>
                </div>
                
                <!-- Project 3 -->
                <div class="project-card">
                    <h3>Weather Dashboard</h3>
                    <p>Real-time weather application with location-based search, detailed forecasts, and interactive data visualizations.</p>
                    <div class="project-tech">
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">API</span>
                        <span class="tech-tag">Chart.js</span>
                    </div>
                    <div class="project-links">
                        <a href="#">View Code</a>
                        <a href="#">Live Demo</a>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Contact Section -->
        <div class="section">
            <h2>Let's Connect</h2>
            <div class="about-content">
                <p>I'm always interested in hearing about new projects and opportunities. Feel free to reach out if you'd like to collaborate or just chat about web development!</p>
                <div class="divider"></div>
                <p style="text-align: center;">
                    <strong>Email:</strong> zeen2@email.com | 
                    <strong>GitHub:</strong> github.com/zeen2
                </p>
            </div>
        </div>
        
        <!-- Footer -->
        <div class="footer">
            <p>© 2024 Zeen2. Designed & Built with care.</p>
        </div>
    </div>
</body>
</html>
