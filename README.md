<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sathya | Full-Stack Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Space Grotesk', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0a0a0a, #1a1a2e, #16213e);
            color: #f8fafc;
            overflow-x: hidden;
        }
        
        .section {
            min-height: 100vh;
            padding: 5rem 2rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
        }
        
        .hero-title {
            font-size: 4.5rem;
            font-weight: 700;
            background: linear-gradient(90deg, #00dbde, #fc00ff, #00dbde);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: gradient-shift 4s ease infinite, text-glow 3s ease-in-out infinite alternate;
            background-size: 200% 200%;
            text-shadow: 0 0 30px rgba(0, 219, 222, 0.3);
        }
        
        @keyframes gradient-shift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        @keyframes text-glow {
            from { text-shadow: 0 0 20px rgba(0, 219, 222, 0.5); }
            to { text-shadow: 0 0 30px rgba(252, 0, 255, 0.7); }
        }
        
        .floating {
            animation: floating 4s ease-in-out infinite;
        }
        
        @keyframes floating {
            0% { transform: translate(0, 0) rotate(0deg); }
            33% { transform: translate(10px, -15px) rotate(5deg); }
            66% { transform: translate(-5px, 10px) rotate(-3deg); }
            100% { transform: translate(0, 0) rotate(0deg); }
        }
        
        .tech-icon {
            transition: all 0.4s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }
        
        .tech-icon::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }
        
        .tech-icon:hover::before {
            left: 100%;
        }
        
        .tech-icon:hover {
            transform: scale(1.2) rotate(5deg);
            filter: drop-shadow(0 0 12px rgba(0, 219, 222, 0.8));
        }
        
        .project-card {
            transition: all 0.4s ease;
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #00dbde, #fc00ff);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.4s ease;
        }
        
        .project-card:hover::before {
            transform: scaleX(1);
        }
        
        .project-card:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
            border-color: rgba(0, 219, 222, 0.3);
        }
        
        .skill-bar {
            height: 10px;
            border-radius: 5px;
            background: rgba(255, 255, 255, 0.1);
            overflow: hidden;
            position: relative;
        }
        
        .skill-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            animation: shimmer 2s infinite;
        }
        
        .skill-progress {
            height: 100%;
            border-radius: 5px;
            background: linear-gradient(90deg, #00dbde, #fc00ff);
            width: 0;
            transition: width 1.8s cubic-bezier(0.22, 0.61, 0.36, 1);
            position: relative;
            z-index: 1;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .animate-on-scroll {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s cubic-bezier(0.22, 0.61, 0.36, 1);
        }
        
        .animate-on-scroll.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .pulse {
            animation: pulse 2.5s infinite;
        }
        
        @keyframes pulse {
            0% { 
                box-shadow: 0 0 0 0 rgba(0, 219, 222, 0.6);
                transform: scale(1);
            }
            70% { 
                box-shadow: 0 0 0 15px rgba(0, 219, 222, 0);
                transform: scale(1.05);
            }
            100% { 
                box-shadow: 0 0 0 0 rgba(0, 219, 222, 0);
                transform: scale(1);
            }
        }
        
        .matrix-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
            opacity: 0.1;
        }
        
        .matrix-column {
            position: absolute;
            top: -100px;
            animation: matrix-fall 15s linear infinite;
            color: #00dbde;
            font-family: monospace;
            font-size: 14px;
        }
        
        @keyframes matrix-fall {
            0% { transform: translateY(-100px); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(100vh); opacity: 0; }
        }
        
        .binary-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
            opacity: 0.05;
        }
        
        .binary-digit {
            position: absolute;
            color: #00dbde;
            font-family: monospace;
            font-size: 16px;
            animation: binary-float 20s linear infinite;
        }
        
        @keyframes binary-float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100px) rotate(360deg); opacity: 0; }
        }
        
        .typewriter {
            overflow: hidden;
            border-right: 2px solid #00dbde;
            white-space: nowrap;
            margin: 0 auto;
            animation: typing 3.5s steps(40, end), blink-caret 0.75s step-end infinite;
        }
        
        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: #00dbde }
        }
        
        .experience-card {
            background: rgba(15, 23, 42, 0.7);
            border-left: 4px solid #00dbde;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }
        
        .experience-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 219, 222, 0.05), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s ease;
        }
        
        .experience-card:hover::before {
            transform: translateX(100%);
        }
        
        .experience-card:hover {
            transform: translateX(10px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }
        
        .code-bracket {
            position: absolute;
            font-size: 120px;
            color: rgba(0, 219, 222, 0.1);
            z-index: -1;
        }
        
        .git-branch {
            position: relative;
        }
        
        .git-branch::before {
            content: '';
            position: absolute;
            top: 50%;
            left: -20px;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: #00dbde;
            transform: translateY(-50%);
        }
    </style>
</head>
<body>
    <!-- Matrix Background -->
    <div class="matrix-bg" id="matrixBg"></div>
    
    <!-- Binary Background -->
    <div class="binary-bg" id="binaryBg"></div>

    <!-- Navigation -->
    <nav class="fixed w-full z-50 bg-slate-900/90 backdrop-blur-md py-4 border-b border-slate-800">
        <div class="container mx-auto px-6 flex justify-between items-center">
            <div class="text-2xl font-bold bg-gradient-to-r from-cyan-400 to-purple-500 bg-clip-text text-transparent">
                Sathya<span class="text-cyan-400">.</span>
            </div>
            <div class="hidden md:flex space-x-8">
                <a href="#home" class="hover:text-cyan-400 transition-colors relative group">
                    Home
                    <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-cyan-400 transition-all group-hover:w-full"></span>
                </a>
                <a href="#about" class="hover:text-cyan-400 transition-colors relative group">
                    About
                    <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-cyan-400 transition-all group-hover:w-full"></span>
                </a>
                <a href="#skills" class="hover:text-cyan-400 transition-colors relative group">
                    Skills
                    <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-cyan-400 transition-all group-hover:w-full"></span>
                </a>
                <a href="#experience" class="hover:text-cyan-400 transition-colors relative group">
                    Experience
                    <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-cyan-400 transition-all group-hover:w-full"></span>
                </a>
                <a href="#projects" class="hover:text-cyan-400 transition-colors relative group">
                    Projects
                    <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-cyan-400 transition-all group-hover:w-full"></span>
                </a>
                <a href="#contact" class="hover:text-cyan-400 transition-colors relative group">
                    Contact
                    <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-cyan-400 transition-all group-hover:w-full"></span>
                </a>
            </div>
            <div class="md:hidden">
                <button id="menu-toggle" class="text-white">
                    <i class="fas fa-bars text-xl"></i>
                </button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="section relative">
        <div class="code-bracket top-10 left-10">{</div>
        <div class="code-bracket bottom-10 right-10">}</div>
        
        <div class="absolute inset-0 overflow-hidden">
            <div class="floating absolute top-10 left-10 w-20 h-20 bg-cyan-500/20 rounded-full blur-xl"></div>
            <div class="floating absolute top-1/3 right-20 w-32 h-32 bg-purple-500/20 rounded-full blur-xl"></div>
            <div class="floating absolute bottom-20 left-1/3 w-24 h-24 bg-pink-500/20 rounded-full blur-xl"></div>
        </div>
        
        <div class="container mx-auto text-center z-10">
            <div class="mb-6">
                <div class="inline-block px-4 py-1 rounded-full bg-cyan-900/30 text-cyan-400 border border-cyan-800 mb-4">
                    <i class="fas fa-code mr-2"></i>Full-Stack Developer
                </div>
            </div>
            <h1 class="hero-title mb-6">Sathya</h1>
            <p class="text-xl mb-8 max-w-2xl mx-auto typewriter">
                Computer Science Graduate | Building Digital Experiences
            </p>
            <div class="flex justify-center space-x-6 mb-12 flex-wrap">
                <div class="tech-icon text-5xl text-cyan-400">
                    <i class="fab fa-python"></i>
                </div>
                <div class="tech-icon text-5xl text-blue-400">
                    <i class="fab fa-react"></i>
                </div>
                <div class="tech-icon text-5xl text-green-500">
                    <i class="fab fa-node-js"></i>
                </div>
                <div class="tech-icon text-5xl text-red-500">
                    <i class="fab fa-html5"></i>
                </div>
                <div class="tech-icon text-5xl text-blue-600">
                    <i class="fab fa-css3-alt"></i>
                </div>
                <div class="tech-icon text-5xl text-cyan-500">
                    <i class="fab fa-git-alt"></i>
                </div>
                <div class="tech-icon text-5xl text-purple-500">
                    <i class="fab fa-github"></i>
                </div>
            </div>
            <button class="bg-gradient-to-r from-cyan-500 to-purple-600 text-white px-8 py-4 rounded-full font-medium hover:from-cyan-600 hover:to-purple-700 transition-all transform hover:scale-105 pulse text-lg">
                Explore My Work
            </button>
        </div>
        
        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2">
            <div class="animate-bounce">
                <i class="fas fa-chevron-down text-2xl text-cyan-400"></i>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section bg-slate-900/40">
        <div class="container mx-auto">
            <h2 class="text-4xl font-bold text-center mb-16 animate-on-scroll">About Me</h2>
            
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="animate-on-scroll">
                    <div class="relative">
                        <div class="w-80 h-80 mx-auto bg-gradient-to-br from-cyan-500 to-purple-600 rounded-full flex items-center justify-center overflow-hidden">
                            <div class="w-72 h-72 bg-slate-900 rounded-full flex items-center justify-center">
                                <i class="fas fa-user-tie text-8xl text-cyan-400"></i>
                            </div>
                        </div>
                        <div class="absolute -bottom-4 -right-4 bg-cyan-500 text-slate-900 px-4 py-2 rounded-lg font-bold">
                            CS Graduate
                        </div>
                    </div>
                </div>
                
                <div class="animate-on-scroll">
                    <h3 class="text-2xl font-semibold mb-6 text-cyan-400">Crafting Digital Solutions</h3>
                    <p class="text-slate-300 mb-6 text-lg">
                        I'm a passionate Full-Stack Developer with a Computer Science background, currently working at <span class="text-cyan-400 font-semibold">Suntrion Technosol Pvt Limited</span> since 2023. I specialize in creating robust, scalable web applications using modern technologies.
                    </p>
                    <p class="text-slate-300 mb-6 text-lg">
                        My expertise spans across both frontend and backend development, with a keen eye for creating intuitive user experiences and efficient server-side architectures.
                    </p>
                    <div class="flex space-x-4">
                        <div class="bg-slate-800/70 p-4 rounded-lg text-center">
                            <div class="text-3xl font-bold text-cyan-400">2+</div>
                            <div class="text-slate-400">Years Experience</div>
                        </div>
                        <div class="bg-slate-800/70 p-4 rounded-lg text-center">
                            <div class="text-3xl font-bold text-purple-400">20+</div>
                            <div class="text-slate-400">Projects Completed</div>
                        </div>
                        <div class="bg-slate-800/70 p-4 rounded-lg text-center">
                            <div class="text-3xl font-bold text-green-400">10+</div>
                            <div class="text-slate-400">Technologies</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="section bg-slate-900/60">
        <div class="container mx-auto">
            <h2 class="text-4xl font-bold text-center mb-16 animate-on-scroll">Technical Skills</h2>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-12">
                <!-- Frontend Skills -->
                <div class="bg-slate-900/70 p-6 rounded-xl animate-on-scroll">
                    <h3 class="text-2xl font-semibold mb-6 text-cyan-400 flex items-center">
                        <i class="fas fa-desktop mr-3"></i> Frontend Technologies
                    </h3>
                    <div class="space-y-4">
                        <div>
                            <div class="flex justify-between mb-1">
                                <span>React</span>
                                <span>90%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" data-width="90"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-1">
                                <span>JavaScript</span>
                                <span>95%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" data-width="95"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-1">
                                <span>HTML/CSS</span>
                                <span>98%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" data-width="98"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-1">
                                <span>Tailwind CSS</span>
                                <span>92%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" data-width="92"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Backend Skills -->
                <div class="bg-slate-900/70 p-6 rounded-xl animate-on-scroll">
                    <h3 class="text-2xl font-semibold mb-6 text-green-400 flex items-center">
                        <i class="fas fa-server mr-3"></i> Backend Technologies
                    </h3>
                    <div class="space-y-4">
                        <div>
                            <div class="flex justify-between mb-1">
                                <span>Python</span>
                                <span>95%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" data-width="95"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-1">
                                <span>Django</span>
                                <span>90%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" data-width="90"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-1">
                                <span>PostgreSQL</span>
                                <span>85%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" data-width="85"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-1">
                                <span>Redis/Celery</span>
                                <span>80%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" data-width="80"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Other Technologies -->
            <div class="animate-on-scroll">
                <h3 class="text-2xl font-semibold mb-6 text-center text-purple-400">Development Tools & Others</h3>
                <div class="flex flex-wrap justify-center gap-6">
                    <div class="tech-icon bg-slate-800 p-4 rounded-lg flex flex-col items-center w-24">
                        <i class="fab fa-git-alt text-4xl text-cyan-500 mb-2"></i>
                        <span>Git</span>
                    </div>
                    <div class="tech-icon bg-slate-800 p-4 rounded-lg flex flex-col items-center w-24">
                        <i class="fab fa-github text-4xl text-purple-500 mb-2"></i>
                        <span>GitHub</span>
                    </div>
                    <div class="tech-icon bg-slate-800 p-4 rounded-lg flex flex-col items-center w-24">
                        <i class="fas fa-database text-3xl text-blue-500 mb-2"></i>
                        <span>JWT</span>
                    </div>
                    <div class="tech-icon bg-slate-800 p-4 rounded-lg flex flex-col items-center w-24">
                        <i class="fas fa-plug text-3xl text-green-500 mb-2"></i>
                        <span>WebSocket</span>
                    </div>
                    <div class="tech-icon bg-slate-800 p-4 rounded-lg flex flex-col items-center w-24">
                        <i class="fas fa-migration text-3xl text-yellow-500 mb-2"></i>
                        <span>Flyway</span>
                    </div>
                    <div class="tech-icon bg-slate-800 p-4 rounded-lg flex flex-col items-center w-24">
                        <i class="fas fa-tasks text-3xl text-red-500 mb-2"></i>
                        <span>Celery</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience" class="section bg-slate-900/40">
        <div class="container mx-auto">
            <h2 class="text-4xl font-bold text-center mb-16 animate-on-scroll">Professional Experience</h2>
            
            <div class="max-w-4xl mx-auto">
                <div class="experience-card p-6 rounded-lg mb-8 animate-on-scroll">
                    <div class="flex flex-col md:flex-row md:justify-between md:items-start mb-4">
                        <div>
                            <h3 class="text-2xl font-semibold text-cyan-400">Full-Stack Developer</h3>
                            <p class="text-lg text-slate-300">Suntrion Technosol Pvt Limited</p>
                        </div>
                        <div class="mt-2 md:mt-0 px-3 py-1 bg-cyan-900/30 text-cyan-400 rounded-full text-sm font-medium">
                            2023 - Present
                        </div>
                    </div>
                    <ul class="text-slate-300 space-y-2 list-disc pl-5">
                        <li>Developed and maintained full-stack web applications using Python, Django, React, and PostgreSQL</li>
                        <li>Implemented RESTful APIs and integrated third-party services</li>
                        <li>Collaborated with cross-functional teams to design, develop, and ship new features</li>
                        <li>Optimized application performance and implemented caching strategies with Redis</li>
                        <li>Managed database migrations using Flyway and implemented background tasks with Celery</li>
                        <li>Utilized Git and GitHub for version control and team collaboration</li>
                    </ul>
                </div>
                
                <div class="experience-card p-6 rounded-lg animate-on-scroll">
                    <div class="flex flex-col md:flex-row md:justify-between md:items-start mb-4">
                        <div>
                            <h3 class="text-2xl font-semibold text-purple-400">Computer Science Graduate</h3>
                            <p class="text-lg text-slate-300">Bachelor of Technology</p>
                        </div>
                        <div class="mt-2 md:mt-0 px-3 py-1 bg-purple-900/30 text-purple-400 rounded-full text-sm font-medium">
                            2019 - 2023
                        </div>
                    </div>
                    <ul class="text-slate-300 space-y-2 list-disc pl-5">
                        <li>Graduated with strong foundation in algorithms, data structures, and software engineering principles</li>
                        <li>Completed projects in web development, database management, and software design</li>
                        <li>Participated in coding competitions and hackathons</li>
                        <li>Developed academic projects using full-stack technologies</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section">
        <div class="container mx-auto">
            <h2 class="text-4xl font-bold text-center mb-16 animate-on-scroll">Featured Projects</h2>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Project 1 -->
                <div class="project-card rounded-xl overflow-hidden animate-on-scroll">
                    <div class="h-48 bg-gradient-to-r from-cyan-500 to-purple-600 relative overflow-hidden">
                        <div class="absolute inset-0 bg-black/30 flex items-center justify-center">
                            <i class="fas fa-shopping-cart text-6xl text-white"></i>
                        </div>
                        <div class="absolute top-4 right-4 bg-cyan-900/80 text-cyan-300 px-2 py-1 rounded text-xs font-medium">
                            <i class="fab fa-github mr-1"></i> GitHub
                        </div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-semibold mb-2">E-Commerce Platform</h3>
                        <p class="text-slate-300 mb-4">Full-stack e-commerce solution with Django backend and React frontend.</p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">Django</span>
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">React</span>
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">PostgreSQL</span>
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">JWT</span>
                        </div>
                        <div class="flex space-x-4">
                            <a href="#" class="text-cyan-400 hover:text-cyan-300 transition-colors">
                                <i class="fab fa-github mr-1"></i> Code
                            </a>
                            <a href="#" class="text-green-400 hover:text-green-300 transition-colors">
                                <i class="fas fa-external-link-alt mr-1"></i> Live Demo
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- Project 2 -->
                <div class="project-card rounded-xl overflow-hidden animate-on-scroll">
                    <div class="h-48 bg-gradient-to-r from-green-500 to-cyan-600 relative overflow-hidden">
                        <div class="absolute inset-0 bg-black/30 flex items-center justify-center">
                            <i class="fas fa-comments text-6xl text-white"></i>
                        </div>
                        <div class="absolute top-4 right-4 bg-cyan-900/80 text-cyan-300 px-2 py-1 rounded text-xs font-medium">
                            <i class="fab fa-github mr-1"></i> GitHub
                        </div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-semibold mb-2">Real-Time Chat App</h3>
                        <p class="text-slate-300 mb-4">WebSocket-based chat application with Django Channels and Redis.</p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">Django</span>
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">WebSocket</span>
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">Redis</span>
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">Celery</span>
                        </div>
                        <div class="flex space-x-4">
                            <a href="#" class="text-cyan-400 hover:text-cyan-300 transition-colors">
                                <i class="fab fa-github mr-1"></i> Code
                            </a>
                            <a href="#" class="text-green-400 hover:text-green-300 transition-colors">
                                <i class="fas fa-external-link-alt mr-1"></i> Live Demo
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- Project 3 -->
                <div class="project-card rounded-xl overflow-hidden animate-on-scroll">
                    <div class="h-48 bg-gradient-to-r from-purple-500 to-pink-600 relative overflow-hidden">
                        <div class="absolute inset-0 bg-black/30 flex items-center justify-center">
                            <i class="fas fa-chart-line text-6xl text-white"></i>
                        </div>
                        <div class="absolute top-4 right-4 bg-cyan-900/80 text-cyan-300 px-2 py-1 rounded text-xs font-medium">
                            <i class="fab fa-github mr-1"></i> GitHub
                        </div>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-semibold mb-2">Data Analytics Dashboard</h3>
                        <p class="text-slate-300 mb-4">Interactive dashboard with real-time data visualization and reporting.</p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">Python</span>
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">React</span>
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">PostgreSQL</span>
                            <span class="bg-cyan-900/50 text-cyan-300 px-2 py-1 rounded text-sm">Flyway</span>
                        </div>
                        <div class="flex space-x-4">
                            <a href="#" class="text-cyan-400 hover:text-cyan-300 transition-colors">
                                <i class="fab fa-github mr-1"></i> Code
                            </a>
                            <a href="#" class="text-green-400 hover:text-green-300 transition-colors">
                                <i class="fas fa-external-link-alt mr-1"></i> Live Demo
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section bg-slate-900/60">
        <div class="container mx-auto max-w-4xl">
            <h2 class="text-4xl font-bold text-center mb-16 animate-on-scroll">Get In Touch</h2>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
                <div class="animate-on-scroll">
                    <h3 class="text-2xl font-semibold mb-6 text-cyan-400">Let's Work Together</h3>
                    <p class="text-slate-300 mb-6 text-lg">
                        I'm always interested in new opportunities and challenges. Whether you have a project in mind or just want to connect, feel free to reach out!
                    </p>
                    
                    <div class="space-y-4">
                        <div class="flex items-center">
                            <i class="fas fa-envelope text-cyan-400 mr-4 text-xl"></i>
                            <span>sathya.dev@example.com</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-phone text-green-400 mr-4 text-xl"></i>
                            <span>+91 98765 43210</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-map-marker-alt text-red-400 mr-4 text-xl"></i>
                            <span>India</span>
                        </div>
                    </div>
                    
                    <div class="flex space-x-4 mt-8">
                        <a href="#" class="tech-icon bg-slate-800 p-3 rounded-full">
                            <i class="fab fa-github text-xl"></i>
                        </a>
                        <a href="#" class="tech-icon bg-slate-800 p-3 rounded-full">
                            <i class="fab fa-linkedin text-xl text-blue-500"></i>
                        </a>
                        <a href="#" class="tech-icon bg-slate-800 p-3 rounded-full">
                            <i class="fab fa-twitter text-xl text-cyan-400"></i>
                        </a>
                        <a href="#" class="tech-icon bg-slate-800 p-3 rounded-full">
                            <i class="fab fa-dev text-xl text-white"></i>
                        </a>
                    </div>
                </div>
                
                <div class="animate-on-scroll">
                    <form class="space-y-6">
                        <div>
                            <label for="name" class="block mb-2">Your Name</label>
                            <input type="text" id="name" class="w-full bg-slate-800 border border-slate-700 rounded-lg px-4 py-3 focus:outline-none focus:ring-2 focus:ring-cyan-500 focus:border-transparent transition-all">
                        </div>
                        <div>
                            <label for="email" class="block mb-2">Your Email</label>
                            <input type="email" id="email" class="w-full bg-slate-800 border border-slate-700 rounded-lg px-4 py-3 focus:outline-none focus:ring-2 focus:ring-cyan-500 focus:border-transparent transition-all">
                        </div>
                        <div>
                            <label for="message" class="block mb-2">Your Message</label>
                            <textarea id="message" rows="4" class="w-full bg-slate-800 border border-slate-700 rounded-lg px-4 py-3 focus:outline-none focus:ring-2 focus:ring-cyan-500 focus:border-transparent transition-all"></textarea>
                        </div>
                        <button type="submit" class="w-full bg-gradient-to-r from-cyan-500 to-purple-600 text-white py-3 rounded-lg font-medium hover:from-cyan-600 hover:to-purple-700 transition-all transform hover:scale-[1.02]">
                            Send Message
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-slate-900 py-8 text-center border-t border-slate-800">
        <div class="container mx-auto">
            <p class="text-slate-400">© 2023 Sathya. Crafted with <i class="fas fa-heart text-red-500 mx-1"></i> and code.</p>
        </div>
    </footer>

    <script>
        // Create Matrix background effect
        function createMatrixBackground() {
            const matrixBg = document.getElementById('matrixBg');
            const chars = "01";
            const columns = Math.floor(window.innerWidth / 20);
            
            for (let i = 0; i < columns; i++) {
                const column = document.createElement('div');
                column.className = 'matrix-column';
                column.style.left = `${i * 20}px`;
                column.style.animationDelay = `${Math.random() * 15}s`;
                
                // Create characters for this column
                for (let j = 0; j < 30; j++) {
                    const char = document.createElement('div');
                    char.textContent = chars.charAt(Math.floor(Math.random() * chars.length));
                    char.style.opacity = Math.random();
                    column.appendChild(char);
                }
                
                matrixBg.appendChild(column);
            }
        }
        
        // Create Binary background effect
        function createBinaryBackground() {
            const binaryBg = document.getElementById('binaryBg');
            const binaryCount = 50;
            
            for (let i = 0; i < binaryCount; i++) {
                const binary = document.createElement('div');
                binary.className = 'binary-digit';
                binary.textContent = Math.random() > 0.5 ? '1' : '0';
                binary.style.left = `${Math.random() * 100}%`;
                binary.style.animationDelay = `${Math.random() * 20}s`;
                binary.style.fontSize = `${Math.random() * 10 + 10}px`;
                binaryBg.appendChild(binary);
            }
        }
        
        // Scroll animation
        document.addEventListener('DOMContentLoaded', function() {
            // Create background effects
            createMatrixBackground();
            createBinaryBackground();
            
            // Animate skill bars on scroll
            const skillBars = document.querySelectorAll('.skill-progress');
            const animateOnScrollElements = document.querySelectorAll('.animate-on-scroll');
            
            // Intersection Observer for scroll animations
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        
                        // If it's a skill bar, animate the width
                        if (entry.target.classList.contains('skill-progress')) {
                            const width = entry.target.getAttribute('data-width');
                            setTimeout(() => {
                                entry.target.style.width = width + '%';
                            }, 300);
                        }
                    }
                });
            }, { threshold: 0.1 });
            
            // Observe all elements that should animate on scroll
            animateOnScrollElements.forEach(el => {
                observer.observe(el);
            });
            
            // Mobile menu toggle
            const menuToggle = document.getElementById('menu-toggle');
            const navLinks = document.querySelector('nav .hidden');
            
            if (menuToggle) {
                menuToggle.addEventListener('click', () => {
                    navLinks.classList.toggle('hidden');
                    navLinks.classList.toggle('flex');
                    navLinks.classList.toggle('flex-col');
                    navLinks.classList.toggle('absolute');
                    navLinks.classList.toggle('top-16');
                    navLinks.classList.toggle('left-0');
                    navLinks.classList.toggle('w-full');
                    navLinks.classList.toggle('bg-slate-900');
                    navLinks.classList.toggle('p-4');
                    navLinks.classList.toggle('space-y-4');
                });
            }
            
            // Smooth scrolling for navigation links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                        
                        // Close mobile menu if open
                        if (!navLinks.classList.contains('hidden')) {
                            menuToggle.click();
                        }
                    }
                });
            });
        });
    </script>
</body>
</html>
