
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Landing page| Premium Ecosystem v2.0</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&family=JetBrains+Mono&display=swap');

        :root {
            --accent: #58a6ff;
            --bg: #0d1117;
            --card: #161b22;
            --border: #30363d;
            --glass: rgba(13, 17, 23, 0.85);
        }

        body {
            background-color: var(--bg);
            color: #c9d1d9;
            font-family: 'Plus Jakarta Sans', sans-serif;
            scroll-behavior: smooth;
            overflow-x: hidden;
        }

        /* --- 1. PREMIUM DOCKING NAVIGATION --- */
        .nav-dock {
            position: fixed; right: 20px; top: 50%; transform: translateY(-50%);
            display: flex; flex-direction: column; align-items: center; gap: 15px; z-index: 10000;
        }
        #nav-launcher {
            width: 42px; height: 42px; background: var(--glass); border: 1px solid var(--border);
            color: var(--accent); border-radius: 12px; cursor: pointer; display: flex;
            align-items: center; justify-content: center; font-size: 1.5rem; backdrop-filter: blur(10px);
            transition: 0.4s; box-shadow: 0 8px 32px rgba(0,0,0,0.5);
        }
        #nav-launcher.open { background: var(--accent); color: white; transform: rotate(180deg); }
        .nav-group { display: flex; flex-direction: column; gap: 12px; pointer-events: none; opacity: 0; transform: translateX(20px); transition: 0.4s; }
        .nav-group.active { pointer-events: auto; opacity: 1; transform: translateX(0); }
        .nav-btn {
            width: 38px; height: 38px; background: var(--glass); border: 1px solid var(--border);
            color: #8b949e; border-radius: 50%; display: flex; align-items: center; justify-content: center;
            transition: 0.3s; cursor: pointer;
        }
        .nav-btn:hover { background: var(--accent); color: white; transform: scale(1.1); }

        /* --- 2. LAZY LOAD REVEAL --- */
        .reveal { opacity: 0; transform: translateY(30px); transition: 1s cubic-bezier(0.17, 0.67, 0.83, 0.67); }
        .reveal.active { opacity: 1; transform: translateY(0); }

        /* --- 3. AUTO-SLIDE TICKER --- */
        .ticker-wrap { background: #1f6feb; color: white; padding: 12px 0; overflow: hidden; white-space: nowrap; }
        .ticker-move { display: inline-block; animation: ticker 30s linear infinite; font-size: 12px; font-weight: 800; letter-spacing: 1px; }
        @keyframes ticker { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }

        /* --- 4. CAROUSEL STYLING --- */
        .carousel-box { width: 100%; overflow: hidden; position: relative; border-radius: 24px; background: var(--card); border: 1px solid var(--border); }
        .carousel-inner { display: flex; transition: transform 0.6s ease-in-out; }
        .carousel-slide { min-width: 100%; padding: 60px 40px; text-align: center; }

        /* --- 5. PREMIUM IFRAME MODAL --- */
        #iframe-modal {
            position: fixed; inset: 0; background: #000; z-index: 10001; display: none; flex-direction: column;
            animation: zoomIn 0.3s ease-out;
        }
        .iframe-nav { background: #161b22; padding: 15px 25px; display: flex; justify-content: space-between; align-items: center; border-bottom: 2px solid var(--accent); }
        @keyframes zoomIn { from { opacity: 0; transform: scale(0.95); } to { opacity: 1; transform: scale(1); } }
    </style>
</head>
<body>

    <div class="nav-dock">
        <button id="nav-launcher" onclick="toggleNav()">›</button>
        <div class="nav-group" id="navGroup">
            <button class="nav-btn" onclick="window.scrollTo({top: 0, behavior: 'smooth'})" title="Top"><i class="fas fa-chevron-up"></i></button>
            <button class="nav-btn" onclick="openPortal('https://debeatzgh1.blogspot.com/')" title="Main Blog"><i class="fab fa-blogger-b"></i></button>
            <button class="nav-btn" onclick="window.open('https://github.com/debeatzgh1', '_blank')" title="GitHub"><i class="fab fa-github"></i></button>
        </div>
    </div>

    <header class="pt-24 pb-16 px-6 text-center reveal">
        <h1 class="text-5xl md:text-7xl font-black tracking-tighter text-white mb-4">DEBEATZGH <span class="text-blue-500">CORE</span></h1>
        <p class="text-gray-500 max-w-xl mx-auto text-sm md:text-base">The central nervous system for all software development, content strategy, and AI-driven business tools.</p>
    </header>

    <section class="max-w-5xl mx-auto px-6 mb-20 reveal">
        <div class="carousel-box">
            <div class="carousel-inner" id="carouselInner">
                <div class="carousel-slide">
                    <span class="text-blue-400 font-bold text-xs uppercase tracking-widest">Featured Tool</span>
                    <h2 class="text-3xl font-extrabold text-white mt-2">Decode AI Starter Kit</h2>
                    <p class="text-gray-400 mt-4 max-w-md mx-auto">High-performance prompt engineering assets for content creators and developers.</p>
                </div>
                <div class="carousel-slide">
                    <span class="text-green-400 font-bold text-xs uppercase tracking-widest">Business Asset</span>
                    <h2 class="text-3xl font-extrabold text-white mt-2">Online Business Kit</h2>
                    <p class="text-gray-400 mt-4 max-w-md mx-auto">The ultimate 2026 blueprint for launching scalable digital income streams.</p>
                </div>
                <div class="carousel-slide">
                    <span class="text-purple-400 font-bold text-xs uppercase tracking-widest">UI Framework</span>
                    <h2 class="text-3xl font-extrabold text-white mt-2">Floating Dock System</h2>
                    <p class="text-gray-400 mt-4 max-w-md mx-auto">Smart iframe modal controllers and kinetic UI components for modern webs.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="max-w-6xl mx-auto px-6 mb-20 reveal">
        <h3 class="flex items-center gap-3 text-white font-bold mb-8 uppercase tracking-widest text-xs">
            <i class="fas fa-layer-group text-blue-500"></i> Blogger Network (Iframe Mode)
        </h3>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
            <div class="bg-[#161b22] p-8 rounded-3xl border border-[#30363d] hover:border-blue-500 transition cursor-pointer" onclick="openPortal('https://debeatzgh1.blogspot.com/')">
                <i class="fab fa-blogger text-2xl text-blue-500 mb-4"></i>
                <h4 class="text-white font-bold">Primary Portal</h4>
                <p class="text-xs text-gray-500 mt-2">Official DeBeatzGH blog and ecosystem announcements.</p>
            </div>
            <div class="bg-[#161b22] p-8 rounded-3xl border border-[#30363d] hover:border-blue-500 transition cursor-pointer" onclick="openPortal('https://digimartgh.blogspot.com/')">
                <i class="fas fa-shopping-cart text-2xl text-green-500 mb-4"></i>
                <h4 class="text-white font-bold">DigiMart GH</h4>
                <p class="text-xs text-gray-500 mt-2">Digital marketplace and professional service listings.</p>
            </div>
            <div class="bg-[#161b22] p-8 rounded-3xl border border-[#30363d] hover:border-blue-500 transition cursor-pointer" onclick="openPortal('https://mybrandsonline.blogspot.com/')">
                <i class="fas fa-globe text-2xl text-purple-500 mb-4"></i>
                <h4 class="text-white font-bold">Brands Online</h4>
                <p class="text-xs text-gray-500 mt-2">Branding strategies and corporate identity management.</p>
            </div>
        </div>
    </section>

    <section class="max-w-6xl mx-auto px-6 mb-20 reveal">
        <h3 class="flex items-center gap-3 text-white font-bold mb-8 uppercase tracking-widest text-xs">
            <i class="fab fa-github text-white"></i> GitHub Projects (New Tab Mode)
        </h3>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
            <div class="bg-black/40 p-6 rounded-2xl border border-white/5 hover:bg-blue-500/10 transition cursor-pointer" onclick="window.open('https://debeatzgh1.github.io/Decode-AI-starter-kit-/', '_blank')">
                <h5 class="text-white text-sm font-bold">Decode AI</h5>
                <p class="text-[10px] text-gray-500">Prompt Engineering</p>
            </div>
            <div class="bg-black/40 p-6 rounded-2xl border border-white/5 hover:bg-blue-500/10 transition cursor-pointer" onclick="window.open('https://debeatzgh1.github.io/Side-hustle-starter-kit-/', '_blank')">
                <h5 class="text-white text-sm font-bold">Side Hustle</h5>
                <p class="text-[10px] text-gray-500">Business Blueprints</p>
            </div>
            <div class="bg-black/40 p-6 rounded-2xl border border-white/5 hover:bg-blue-500/10 transition cursor-pointer" onclick="window.open('https://debeatzgh1.github.io/Personal-Portfolio-site-/', '_blank')">
                <h5 class="text-white text-sm font-bold">Developer CV</h5>
                <p class="text-[10px] text-gray-500">Pro Portfolio</p>
            </div>
            <div class="bg-black/40 p-6 rounded-2xl border border-white/5 hover:bg-blue-500/10 transition cursor-pointer" onclick="window.open('https://debeatzgh1.github.io/popup-html-page-generator-blogger/', '_blank')">
                <h5 class="text-white text-sm font-bold">Popup Gen</h5>
                <p class="text-[10px] text-gray-500">HTML Utility</p>
            </div>
        </div>
    </section>

    <div class="ticker-wrap reveal">
        <div class="ticker-move">
            🚀 DECODE AI STARTER KIT IS NOW LIVE // 💎 PREMIUM ONLINE BUSINESS KIT V2.0 // ⚡ NEW: KINETIC UI FRAMEWORK DEPLOYED // 🚀 DECODE AI STARTER KIT IS NOW LIVE // 💎 PREMIUM ONLINE BUSINESS KIT V2.0
        </div>
    </div>

    <footer class="py-20 text-center reveal">
        <div class="flex justify-center gap-8 mb-6">
            <a href="https://wa.me/233549757544" class="text-gray-500 hover:text-green-500 text-xl"><i class="fab fa-whatsapp"></i></a>
            <a href="https://youtube.com/debeatzgh" class="text-gray-500 hover:text-red-500 text-xl"><i class="fab fa-youtube"></i></a>
            <a href="https://github.com/debeatzgh1" class="text-gray-500 hover:text-white text-xl"><i class="fab fa-github"></i></a>
        </div>
        <p class="text-[10px] font-bold text-gray-600 uppercase tracking-widest">© 2026 DEBEATZGH // DKONSULT DIGITAL SOLUTIONS</p>
    </footer>

    <div id="iframe-modal">
        <div class="iframe-nav">
            <span class="text-xs font-black text-white uppercase tracking-tighter">DeBeatzGH <span class="text-blue-500">Portal</span></span>
            <div class="flex gap-4">
                <i class="fas fa-external-link-alt text-gray-500 cursor-pointer hover:text-white" onclick="popOut()"></i>
                <i class="fas fa-times-circle text-red-500 cursor-pointer text-xl" onclick="closePortal()"></i>
            </div>
        </div>
        <iframe id="portalFrame" src="" class="w-full flex-grow border-none bg-white"></iframe>
    </div>

    <script>
        // --- 1. Navigation Dock ---
        function toggleNav() {
            const group = document.getElementById('navGroup');
            const launcher = document.getElementById('nav-launcher');
            const isOpen = group.classList.toggle('active');
            launcher.classList.toggle('open');
            launcher.innerText = isOpen ? '‹' : '›';
        }

        // --- 2. Auto-Slide Carousel ---
        let currentSlide = 0;
        const slides = document.getElementById('carouselInner');
        setInterval(() => {
            currentSlide = (currentSlide + 1) % 3;
            slides.style.transform = `translateX(-${currentSlide * 100}%)`;
        }, 5000);

        // --- 3. Iframe Controller ---
        function openPortal(url) {
            const modal = document.getElementById('iframe-modal');
            const frame = document.getElementById('portalFrame');
            frame.src = url;
            modal.style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }
        function closePortal() {
            document.getElementById('iframe-modal').style.display = 'none';
            document.getElementById('portalFrame').src = '';
            document.body.style.overflow = 'auto';
        }
        function popOut() {
            const url = document.getElementById('portalFrame').src;
            if(url) window.open(url, '_blank');
        }

        // --- 4. Lazy Load Reveal ---
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) entry.target.classList.add('active');
            });
        }, { threshold: 0.1 });
        document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
    </script>
</body>
</html>
