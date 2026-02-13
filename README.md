
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --nav-glass: rgba(13, 17, 23, 0.85);
            --nav-border: rgba(255, 255, 255, 0.1);
            --color-guide: #00f2fe; /* Cyan */
            --color-home: #70ff03;  /* Green */
            --color-social: #ff007a; /* Pink */
            --color-top: #ffffff;   /* White */
        }

        .side-nav {
            position: fixed;
            top: 50%;
            transform: translateY(-50%);
            z-index: 9999;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .nav-left { left: 0; }
        .nav-right { right: 0; }

        .nav-item {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 48px;
            height: 48px;
            background: var(--nav-glass);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid var(--nav-border);
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-decoration: none;
            position: relative;
            overflow: hidden;
        }

        .nav-left .nav-item { border-radius: 0 10px 10px 0; border-left: none; }
        .nav-right .nav-item { border-radius: 10px 0 0 10px; border-right: none; }

        .item-guide { color: var(--color-guide); }
        .item-social { color: var(--color-social); }
        .item-home { color: var(--color-home); }
        .item-top { color: var(--color-top); opacity: 0; visibility: hidden; transition: 0.5s; }
        .item-top.visible { opacity: 1; visibility: visible; }

        .shake-anim { animation: timely-shake 0.5s ease-in-out; }
        @keyframes timely-shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(4px); }
            50% { transform: translateX(-4px); }
        }

        .nav-item:hover { width: 60px; }
        .item-guide:hover { background: var(--color-guide); color: #000; }
        .item-social:hover { background: var(--color-social); color: #fff; }
        .item-home:hover { background: var(--color-home); color: #000; }
        .item-top:hover { background: #fff; color: #000; }

        .nav-item::after {
            content: attr(data-label);
            position: absolute;
            font-size: 9px;
            font-weight: 900;
            white-space: nowrap;
            opacity: 0;
            transition: 0.3s;
        }
        .nav-left .nav-item::after { left: 65px; color: inherit; }
        .nav-right .nav-item::after { right: 65px; color: inherit; }
        .nav-item:hover::after { opacity: 1; }

        svg { width: 22px; height: 22px; pointer-events: none; }
    </style>
</head>
<body>

    <div class="side-nav nav-left">
        <a href="https://debeatzgh1.github.io/me-/" target="_blank" class="nav-item item-guide shake-trigger" data-label="Essential Guides">
            <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path></svg>
        </a>
        <a href="https://debeatzgh1.github.io/The-Ultimate-Guide-to-Side-Hustle/" target="_blank" class="nav-item item-social shake-trigger" data-label="Side Hustle">
            <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 1 1-7.6-10.4 8.38 8.38 0 0 1 3.9 1.1L21 3z"></path></svg>
        </a>
    </div>

    <div class="side-nav nav-right">
        <a href="https://debeatzgh1.github.io/Decode-AI-starter-kit-/" target="_blank" class="nav-item item-home shake-trigger" data-label="AI Starter Kit">
            <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path><polyline points="9 22 9 12 15 12 15 22"></polyline></svg>
        </a>
        <div onclick="scrollToTop()" class="nav-item item-top" id="backToTop" data-label="Back To Top">
            <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="18 15 12 9 6 15"></polyline></svg>
        </div>
    </div>

    <script>
        function startShaking() {
            const icons = document.querySelectorAll('.shake-trigger');
            setInterval(() => {
                icons.forEach((icon, index) => {
                    setTimeout(() => {
                        icon.classList.add('shake-anim');
                        setTimeout(() => icon.classList.remove('shake-anim'), 500);
                    }, index * 200);
                });
            }, 6000);
        }

        const topBtn = document.getElementById('backToTop');
        window.onscroll = function() {
            if (document.body.scrollTop > 300 || document.documentElement.scrollTop > 300) {
                topBtn.classList.add('visible');
            } else {
                topBtn.classList.remove('visible');
            }
        };

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        window.onload = startShaking;
    </script>

</body>
</html>



<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DeBeatzGH | Digital Ecosystem Launcher</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #2563eb;
            --accent: #ef4444;
            --bg: #0f172a;
            --card: #1e293b;
            --text: #f8fafc;
            --glass: rgba(30, 41, 59, 0.8);
        }

        [data-theme="light"] {
            --bg: #f1f5f9;
            --card: #ffffff;
            --text: #0f172a;
            --glass: rgba(255, 255, 255, 0.8);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Plus Jakarta Sans', sans-serif; }
        body { background-color: var(--bg); color: var(--text); transition: 0.3s; overflow-x: hidden; }

        /* --- Heartbeat Animation --- */
        @keyframes heartbeat {
            0% { transform: scale(1); }
            15% { transform: scale(1.15); }
            30% { transform: scale(1); }
            45% { transform: scale(1.15); }
            100% { transform: scale(1); }
        }
        .badge-live {
            background: var(--accent); color: white; padding: 2px 8px;
            border-radius: 20px; font-size: 0.65rem; font-weight: 800;
            display: inline-block; animation: heartbeat 2s infinite;
            vertical-align: middle; margin-left: 5px;
        }

        /* --- Layout --- */
        .top-nav {
            position: fixed; top: 0; width: 100%; padding: 15px 30px;
            background: var(--glass); backdrop-filter: blur(12px);
            display: flex; justify-content: space-between; align-items: center; z-index: 1000;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .container { max-width: 1200px; margin: 100px auto 50px; padding: 0 20px; }

        h2.section-title {
            margin: 40px 0 20px; font-size: 1.5rem; display: flex; align-items: center; gap: 10px;
        }
        h2.section-title i { color: var(--primary); }

        /* --- Tab Grid --- */
        .launcher-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 20px;
        }

        .launch-card {
            background: var(--card); padding: 20px; border-radius: 16px;
            border: 1px solid rgba(128,128,128,0.1); transition: 0.3s;
            cursor: pointer; position: relative; overflow: hidden;
        }
        .launch-card:hover { transform: translateY(-5px); border-color: var(--primary); box-shadow: 0 10px 25px rgba(0,0,0,0.2); }
        .launch-card h3 { font-size: 1rem; margin-bottom: 8px; }
        .launch-card p { font-size: 0.8rem; opacity: 0.6; margin-bottom: 15px; }

        .type-tag {
            font-size: 0.7rem; text-transform: uppercase; letter-spacing: 1px;
            color: var(--primary); font-weight: 700;
        }

        /* --- Smart Iframe Modal --- */
        #iframe-modal {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: #000; z-index: 9999; display: none; flex-direction: column;
        }
        .iframe-controls {
            background: #1e293b; padding: 10px 20px; display: flex;
            justify-content: space-between; align-items: center; color: white;
        }
        .iframe-actions i { margin-left: 20px; cursor: pointer; font-size: 1.2rem; }
        .iframe-actions i:hover { color: var(--primary); }
        iframe { width: 100%; flex-grow: 1; border: none; }

        /* --- Auto Slider --- */
        .slider-box { background: var(--primary); color: white; padding: 15px 0; margin-top: 40px; overflow: hidden; white-space: nowrap; }
        .slider-track { display: inline-block; animation: scroll 40s linear infinite; }
        .slider-item { display: inline-block; margin: 0 30px; font-weight: 600; font-size: 0.9rem; }

        @keyframes scroll { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }

        /* --- Footer Socials --- */
        footer { text-align: center; padding: 50px 20px; opacity: 0.7; font-size: 0.9rem; }
        .socials { margin-top: 15px; display: flex; justify-content: center; gap: 20px; }
        .socials a { color: var(--text); font-size: 1.2rem; }
    </style>
</head>
<body>

    <div id="iframe-modal">
        <div class="iframe-controls">
            <span id="modal-title">Blogger Preview</span>
            <div class="iframe-actions">
                <i class="fas fa-expand" title="Full Screen" onclick="toggleFullScreen()"></i>
                <i class="fas fa-times-circle" title="Close" onclick="closeIframe()" style="color: var(--accent);"></i>
            </div>
        </div>
        <iframe id="portal-frame" src=""></iframe>
    </div>

    <nav class="top-nav">
        <div style="font-weight: 800; font-size: 1.2rem;">DEBEATZGH <span style="color:var(--primary)">HUB</span></div>
        <div style="display: flex; gap: 20px; align-items: center;">
            <div id="liveClock" style="font-family: monospace; font-size: 0.9rem;">00:00:00</div>
            <i class="fas fa-adjust" onclick="toggleTheme()" style="cursor:pointer"></i>
        </div>
    </nav>

    <div class="container">
        <div style="text-align: center; margin-bottom: 60px;">
            <h1 style="font-size: 2.5rem; margin-bottom: 10px;">Modern Workspace</h1>
            <p style="opacity: 0.7;">Centralized access to all DeBeatzGH platforms and GitHub repositories.</p>
        </div>

        <h2 class="section-title"><i class="fab fa-blogger"></i> Blogger Ecosystem <span class="badge-live">IFRAME MODE</span></h2>
        <div class="launcher-grid">
            <div class="launch-card" onclick="openPortal('https://debeatzgh1.blogspot.com/', 'Official Blog')">
                <span class="type-tag">Main Portal</span>
                <h3>Debeatzgh1 Blog</h3>
                <p>Primary insights and digital updates.</p>
            </div>
            <div class="launch-card" onclick="openPortal('https://beatzde4.blogspot.com/', 'Beatzde4')">
                <span class="type-tag">Network</span>
                <h3>Beatzde4</h3>
                <p>Content syndication and media.</p>
            </div>
            <div class="launch-card" onclick="openPortal('https://digimartgh.blogspot.com/', 'DigiMart GH')">
                <span class="type-tag">Ecommerce</span>
                <h3>DigiMart GH</h3>
                <p>Digital marketplace and services.</p>
            </div>
            <div class="launch-card" onclick="openPortal('https://mybrandsonline.blogspot.com/', 'Brands Online')">
                <span class="type-tag">Branding</span>
                <h3>My Brands Online</h3>
                <p>Brand management and visibility.</p>
            </div>
        </div>

        <h2 class="section-title"><i class="fab fa-github"></i> GitHub Projects <span class="badge-live" style="background:var(--primary)">NEW TAB</span></h2>
        <div class="launcher-grid">
            <div class="launch-card" onclick="window.open('https://debeatzgh1.github.io/1/', '_blank')">
                <span class="type-tag">Project</span>
                <h3>Official Website</h3>
                <p>DeBeatzGH main GitHub landing page.</p>
            </div>
            <div class="launch-card" onclick="window.open('https://debeatzgh1.github.io/Decode-AI-starter-kit-/', '_blank')">
                <span class="type-tag">AI Tool</span>
                <h3>Decode AI Kit</h3>
                <p>AI-powered starter components.</p>
            </div>
            <div class="launch-card" onclick="window.open('https://debeatzgh1.github.io/Personal-Portfolio-site-/', '_blank')">
                <span class="type-tag">Portfolio</span>
                <h3>Pro Portfolio</h3>
                <p>Showcasing development expertise.</p>
            </div>
            <div class="launch-card" onclick="window.open('https://debeatzgh1.github.io/Side-hustle-starter-kit-/', '_blank')">
                <span class="type-tag">Business</span>
                <h3>Side Hustle Kit</h3>
                <p>The ultimate guide to extra income.</p>
            </div>
            <div class="launch-card" onclick="window.open('https://debeatzgh1.github.io/popup-html-page-generator-blogger/', '_blank')">
                <span class="type-tag">Utility</span>
                <h3>Popup Generator</h3>
                <p>Custom HTML tools for Blogger.</p>
            </div>
            <div class="launch-card" onclick="window.open('https://debeatzgh1.github.io/-Floating-Dock-Smart-Iframe-Modal/#', '_blank')">
                <span class="type-tag">UI Component</span>
                <h3>Floating Dock</h3>
                <p>Smart Iframe modal controller.</p>
            </div>
        </div>
    </div>

    <div class="slider-box">
        <div class="slider-track">
            <span class="slider-item">🚀 NEW: Decode AI Starter Kit Live</span>
            <span class="slider-item">💎 PREMIUM: Online Business Kit Available</span>
            <span class="slider-item">🔥 TRENDING: Modern Tailwind Styling</span>
            <span class="slider-item">⚡ UPDATE: Collaborative Hub v2.0</span>
            <span class="slider-item">🚀 NEW: Decode AI Starter Kit Live</span>
            <span class="slider-item">💎 PREMIUM: Online Business Kit Available</span>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 DeBeatzGH Digital. Built for Excellence.</p>
        <div class="socials">
            <a href="https://wa.me/233549757544"><i class="fab fa-whatsapp"></i></a>
            <a href="https://facebook.com/Debeatzgh"><i class="fab fa-facebook"></i></a>
            <a href="https://youtube.com/debeatzgh"><i class="fab fa-youtube"></i></a>
        </div>
    </footer>

    <script>
        // --- Portal Controller ---
        function openPortal(url, title) {
            const modal = document.getElementById('iframe-modal');
            const frame = document.getElementById('portal-frame');
            document.getElementById('modal-title').innerText = "DeBeatzGH Portal: " + title;
            frame.src = url;
            modal.style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }

        function closeIframe() {
            const modal = document.getElementById('iframe-modal');
            const frame = document.getElementById('portal-frame');
            modal.style.display = 'none';
            frame.src = '';
            document.body.style.overflow = 'auto';
        }

        function toggleFullScreen() {
            if (!document.fullscreenElement) {
                document.getElementById('iframe-modal').requestFullscreen();
            } else {
                document.exitFullscreen();
            }
        }

        // --- Theme Toggle ---
        function toggleTheme() {
            const current = document.body.getAttribute('data-theme');
            document.body.setAttribute('data-theme', current === 'light' ? 'dark' : 'light');
        }

        // --- Clock ---
        setInterval(() => {
            document.getElementById('liveClock').innerText = new Date().toLocaleTimeString();
        }, 1000);
    </script>
</body>
</html>
