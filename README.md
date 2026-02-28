<!DOCTYPE html>
<html lang="tr">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mehmet Yasin Çaldıran | Cyber Portfolio</title>
    <link
        href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;700;900&family=Rajdhani:wght@400;500;600;700&display=swap"
        rel="stylesheet">
    <style>
        :root {
            --primary: #00E0FF;
            --secondary: #BC13FE;
            --dark: #050510;
            --darker: #020205;
            --glass: rgba(5, 5, 16, 0.6);
            --border: rgba(0, 224, 255, 0.3);
            --text-glow: 0 0 10px rgba(0, 224, 255, 0.8), 0 0 20px rgba(0, 224, 255, 0.5);
            --box-glow: 0 0 15px rgba(188, 19, 254, 0.3), inset 0 0 15px rgba(188, 19, 254, 0.3);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--darker);
            color: #ffffff;
            font-family: 'Rajdhani', sans-serif;
            overflow-x: hidden;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* Animated Grid Background */
        .bg-grid {
            position: fixed;
            width: 200vw;
            height: 200vh;
            left: -50vw;
            bottom: -50vh;
            background-image:
                linear-gradient(var(--border) 1px, transparent 1px),
                linear-gradient(90deg, var(--border) 1px, transparent 1px);
            background-size: 60px 60px;
            transform: perspective(600px) rotateX(60deg);
            animation: gridMove 10s linear infinite;
            z-index: -2;
            pointer-events: none;
        }

        .bg-gradient {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: radial-gradient(circle at center, transparent 0%, var(--darker) 70%);
            z-index: -1;
            pointer-events: none;
        }

        @keyframes gridMove {
            0% {
                background-position: 0 0;
            }

            100% {
                background-position: 0 60px;
            }
        }

        /* Container */
        .container {
            width: 100%;
            max-width: 1200px;
            padding: 4rem 2rem;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4rem;
            z-index: 10;
        }

        /* Header / Hero Section */
        .hero {
            text-align: center;
            animation: fadeInDown 1s ease-out;
        }

        h1.glitch {
            position: relative;
            font-family: 'Orbitron', sans-serif;
            font-size: 4rem;
            font-weight: 900;
            color: #fff;
            text-shadow: var(--text-glow);
            letter-spacing: 4px;
            margin-bottom: 1rem;
            text-transform: uppercase;
        }

        h1.glitch::before,
        h1.glitch::after {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.8;
        }

        h1.glitch::before {
            left: 2px;
            text-shadow: -2px 0 red;
            animation: glitch-anim 2s infinite linear alternate-reverse;
        }

        h1.glitch::after {
            left: -2px;
            text-shadow: -2px 0 blue;
            animation: glitch-anim2 3s infinite linear alternate-reverse;
        }

        @keyframes glitch-anim {
            0% {
                clip: rect(24px, 9999px, 86px, 0);
            }

            20% {
                clip: rect(61px, 9999px, 32px, 0);
            }

            40% {
                clip: rect(100px, 9999px, 98px, 0);
            }

            60% {
                clip: rect(10px, 9999px, 4px, 0);
            }

            80% {
                clip: rect(44px, 9999px, 78px, 0);
            }

            100% {
                clip: rect(81px, 9999px, 5px, 0);
            }
        }

        @keyframes glitch-anim2 {
            0% {
                clip: rect(65px, 9999px, 100px, 0);
            }

            20% {
                clip: rect(3px, 9999px, 49px, 0);
            }

            40% {
                clip: rect(46px, 9999px, 2px, 0);
            }

            60% {
                clip: rect(98px, 9999px, 43px, 0);
            }

            80% {
                clip: rect(15px, 9999px, 80px, 0);
            }

            100% {
                clip: rect(52px, 9999px, 24px, 0);
            }
        }

        .typewriter {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.5rem;
            color: var(--primary);
            min-height: 2rem;
            margin-bottom: 2rem;
            text-shadow: 0 0 5px var(--primary);
        }

        .cursor {
            display: inline-block;
            width: 10px;
            height: 1.2em;
            background-color: var(--primary);
            animation: blink 1s step-end infinite;
            vertical-align: bottom;
            margin-left: 5px;
        }

        @keyframes blink {

            0%,
            100% {
                opacity: 1;
            }

            50% {
                opacity: 0;
            }
        }

        /* Badges */
        .badges {
            display: flex;
            gap: 1.5rem;
            flex-wrap: wrap;
            justify-content: center;
        }

        .badge {
            display: flex;
            align-items: center;
            font-family: 'Orbitron', sans-serif;
            font-size: 0.8rem;
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid;
            border-radius: 4px;
            padding: 0;
            overflow: hidden;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: default;
        }

        .badge:hover {
            transform: translateY(-3px) scale(1.05);
        }

        .badge-label {
            padding: 0.5rem 1rem;
            background: #111;
            font-weight: 700;
            color: #ccc;
        }

        .badge-value {
            padding: 0.5rem 1rem;
            font-weight: 900;
        }

        .badge.cyan {
            border-color: var(--primary);
        }

        .badge.cyan .badge-value {
            background: var(--primary);
            color: #000;
            box-shadow: 0 0 10px var(--primary);
        }

        .badge.cyan:hover {
            box-shadow: 0 0 15px var(--primary);
        }

        .badge.purple {
            border-color: var(--secondary);
        }

        .badge.purple .badge-value {
            background: var(--secondary);
            color: #fff;
            box-shadow: 0 0 10px var(--secondary);
        }

        .badge.purple:hover {
            box-shadow: 0 0 15px var(--secondary);
        }

        .badge.blue {
            border-color: #0066ff;
        }

        .badge.blue .badge-value {
            background: #0066ff;
            color: #fff;
            box-shadow: 0 0 10px #0066ff;
        }

        .badge.blue:hover {
            box-shadow: 0 0 15px #0066ff;
        }

        /* Panels / Glassmorphism */
        .panel-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            width: 100%;
        }

        .panel {
            background: var(--glass);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2rem;
            box-shadow: var(--box-glow);
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
        }

        .panel::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 50%;
            height: 100%;
            background: linear-gradient(to right, transparent, rgba(255, 255, 255, 0.05), transparent);
            transform: skewX(-25deg);
            transition: left 0.7s ease;
        }

        .panel:hover::before {
            left: 200%;
        }

        .panel:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 25px rgba(0, 224, 255, 0.4), inset 0 0 20px rgba(0, 224, 255, 0.2);
            border-color: var(--primary);
        }

        .panel h2 {
            font-family: 'Orbitron', sans-serif;
            color: var(--secondary);
            margin-bottom: 1.5rem;
            font-size: 1.6rem;
            display: flex;
            align-items: center;
            gap: 10px;
            text-shadow: 0 0 8px var(--secondary);
        }

        .panel h2::before {
            content: '>>';
            color: var(--primary);
            font-size: 1.2rem;
            text-shadow: 0 0 5px var(--primary);
        }

        .panel p {
            font-size: 1.2rem;
            line-height: 1.6;
            color: #ddd;
            margin-bottom: 1rem;
        }

        /* Skills */
        .skills-list {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-tag {
            background: rgba(0, 224, 255, 0.1);
            border: 1px solid var(--primary);
            color: var(--primary);
            padding: 0.4rem 1rem;
            border-radius: 20px;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            background: var(--primary);
            color: #000;
            box-shadow: 0 0 15px var(--primary);
            transform: scale(1.1);
        }

        /* Terminal Window */
        .terminal {
            background: #000;
            border-radius: 8px;
            border: 1px solid #333;
            overflow: hidden;
            font-family: 'Courier New', Courier, monospace;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.8);
            margin-top: 1rem;
        }

        .terminal-header {
            background: #1a1a1a;
            padding: 0.5rem 1rem;
            display: flex;
            gap: 8px;
            border-bottom: 1px solid #333;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .dot.red {
            background: #ff5f56;
        }

        .dot.yellow {
            background: #ffbd2e;
        }

        .dot.green {
            background: #27c93f;
        }

        .terminal-body {
            padding: 1.5rem;
            color: #0f0;
            min-height: 200px;
            font-size: 1.1rem;
            line-height: 1.5;
        }

        .term-line {
            margin-bottom: 0.5rem;
            display: none;
        }

        .term-line.active {
            display: block;
        }

        .term-prompt {
            color: var(--primary);
            font-weight: bold;
        }

        .term-cmd {
            color: #fff;
        }

        /* Footer */
        footer {
            margin-top: auto;
            padding: 2rem;
            text-align: center;
            font-family: 'Orbitron', sans-serif;
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.9rem;
            letter-spacing: 2px;
            position: relative;
            z-index: 10;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80%;
            height: 1px;
            background: linear-gradient(90deg, transparent, var(--secondary), transparent);
        }

        /* Animations */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Scanline Overlay */
        .scanlines {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
            background-size: 100% 4px, 6px 100%;
            z-index: 9999;
            pointer-events: none;
            opacity: 0.6;
        }

        /* Mobile fixes */
        @media(max-width: 768px) {
            h1.glitch {
                font-size: 2.5rem;
            }

            .typewriter {
                font-size: 1.2rem;
            }

            .panel-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>

<body>

    <div class="bg-grid"></div>
    <div class="bg-gradient"></div>
    <div class="scanlines"></div>

    <div class="container">
        <!-- Hero Section -->
        <header class="hero">
            <img src="https://i.imgur.com/1ZvVkDc.gif" width="60px"
                style="margin-bottom: 20px; filter: hue-rotate(180deg);" alt="Hologram">

            <h1 class="glitch" data-text="MEHMET YASİN ÇALDIRAN">MEHMET YASİN ÇALDIRAN</h1>

            <div class="typewriter-container">
                <span class="typewriter" id="typewriter-text"></span><span class="cursor"></span>
            </div>

            <div class="badges">
                <div class="badge cyan">
                    <span class="badge-label">SYSTEM STATUS</span>
                    <span class="badge-value">ONLINE</span>
                </div>
                <div class="badge purple">
                    <span class="badge-label">NEON ENGINE</span>
                    <span class="badge-value">ENABLED</span>
                </div>
                <div class="badge blue">
                    <span class="badge-label">VERSION</span>
                    <span class="badge-value">8.0</span>
                </div>
            </div>
        </header>

        <!-- Main Content Grid -->
        <div class="panel-grid">
            <!-- About Panel -->
            <div class="panel">
                <h2>HAKKIMDA</h2>
                <p>Geleceğin teknolojilerini bugünden inşa eden, yenilikçi ve siber güvenlik odaklı bir sistem mimarı ve
                    tam yığın geliştiriciyim.</p>
                <p>Karanlık temalar, neon ışıklar ve kusursuz kod mimarileri içinde kaybolmayı severim. Yazılım
                    geliştirme sürecini bir sanat eseri yaratmak gibi görüyorum.</p>
            </div>

            <!-- Skills Panel -->
            <div class="panel">
                <h2>YETENEKLER & DONANIM</h2>
                <div class="skills-list">
                    <span class="skill-tag">JavaScript / TypeScript</span>
                    <span class="skill-tag">Vue.js / Nuxt.js</span>
                    <span class="skill-tag">React / Next.js</span>
                    <span class="skill-tag">Node.js / Express</span>
                    <span class="skill-tag">Mobil Geliştirme (Flutter/RN)</span>
                    <span class="skill-tag">Siber Güvenlik / Sızma Testi</span>
                    <span class="skill-tag">Veri Tabanı Mimarisi</span>
                    <span class="skill-tag">DevOps / CI-CD</span>
                </div>
            </div>

            <!-- Terminal Panel -->
            <div class="panel terminal-panel"
                style="padding: 0; background: transparent; border: none; box-shadow: none;">
                <div class="terminal">
                    <div class="terminal-header">
                        <div class="dot red"></div>
                        <div class="dot yellow"></div>
                        <div class="dot green"></div>
                    </div>
                    <div class="terminal-body" id="term-body">
                        <div class="term-line active"><span class="term-prompt">yasin@cyber-core:~$</span> <span
                                class="term-cmd">./initialize_system.sh</span></div>
                        <div class="term-line" style="color: #888;">> Yükleniyor çekirdek modülleri... [OK]</div>
                        <div class="term-line" style="color: #888;">> Neon arayüzü başlatılıyor... [OK]</div>
                        <div class="term-line" style="color: #888;">> Siber savunma kalkanları aktif... [OK]</div>
                        <div class="term-line active" style="margin-top: 10px;"><span
                                class="term-prompt">yasin@cyber-core:~$</span> <span class="term-cmd blink">_</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </div>

    <footer>
        &copy; 2026. CYBERPUNK PORTFOLIO V2 • YASİN ÇALDIRAN ALL RIGHTS RESERVED.
    </footer>

    <script>
        // Typewriter Effect
        const roles = [
            "CYBERPUNK DEVELOPER",
            "FULL STACK ENGINEER",
            "MOBİL + WEB DEVELOPER",
            "SİBER GÜVENLİK UZMANI"
        ];

        let roleIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        let typeSpeed = 100;

        function type() {
            const currentRole = roles[roleIndex];
            const typeText = document.getElementById("typewriter-text");

            if (isDeleting) {
                typeText.textContent = currentRole.substring(0, charIndex - 1);
                charIndex--;
                typeSpeed = 50;
            } else {
                typeText.textContent = currentRole.substring(0, charIndex + 1);
                charIndex++;
                typeSpeed = 100;
            }

            if (!isDeleting && charIndex === currentRole.length) {
                isDeleting = true;
                typeSpeed = 2000; // pause at end
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                roleIndex = (roleIndex + 1) % roles.length;
                typeSpeed = 500; // pause before next
            }

            setTimeout(type, typeSpeed);
        }

        setTimeout(type, 1000);

        // Terminal animation logic
        const termLines = document.querySelectorAll('.term-line');
        let currentTermLine = 1;

        function animateTerminal() {
            if (currentTermLine < termLines.length - 1) {
                termLines[currentTermLine].classList.add('active');
                currentTermLine++;
                setTimeout(animateTerminal, Math.random() * 500 + 400);
            } else {
                setTimeout(() => {
                    termLines[currentTermLine].classList.add('active');
                }, 500);
            }
        }

        setTimeout(animateTerminal, 1500);
    </script>
</body>

</html>
