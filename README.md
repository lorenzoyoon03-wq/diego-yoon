<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Diego Yoon</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Lucide Icons CDN -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <!-- Google Fonts: Inter & Syncopate -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Syncopate:wght@400;700&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Syncopate', 'sans-serif'],
                    },
                    colors: {
                        mercury: {
                            50: '#f6f6f7',
                            100: '#e3e3e7',
                            200: '#c7c7cf',
                            300: '#a1a1ae',
                            400: '#757586',
                            500: '#595968',
                            600: '#464653',
                            700: '#383843',
                            800: '#2f2f37',
                            900: '#19191e',
                            950: '#0b0b0e',
                        }
                    },
                    animation: {
                        'liquid-flow': 'liquidFlow 15s ease infinite',
                        'pulse-slow': 'pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                        'float': 'float 6s ease-in-out infinite',
                    },
                    keyframes: {
                        liquidFlow: {
                            '0%, 100%': { transform: 'translate(0%, 0%) scale(1)' },
                            '50%': { transform: 'translate(5%, 8%) scale(1.1)' },
                        },
                        float: {
                            '0%, 100%': { transform: 'translateY(0px)' },
                            '50%': { transform: 'translateY(-10px)' },
                        }
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #08080a;
            color: #e3e3e7;
            overflow-x: hidden;
            width: 100%;
        }

        /* Glassmorphism Liquid Styling */
        .glass-panel {
            background: rgba(18, 18, 24, 0.65);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
        }

        .glass-panel-hover {
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .glass-panel-hover:hover {
            background: rgba(28, 28, 38, 0.75);
            border-color: rgba(255, 255, 255, 0.2);
            box-shadow: 0 12px 40px 0 rgba(255, 255, 255, 0.05);
            transform: translateY(-2px);
        }

        .chrome-text {
            background: linear-gradient(135deg, #ffffff 0%, #a1a1ae 50%, #464653 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .chrome-text-silver {
            background: linear-gradient(180deg, #ffffff 0%, #d1d1d6 30%, #757586 70%, #ffffff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .liquid-border {
            position: relative;
        }

        .liquid-border::before {
            content: '';
            position: absolute;
            inset: -1px;
            background: linear-gradient(90deg, rgba(255,255,255,0.2), rgba(255,255,255,0.02), rgba(255,255,255,0.2));
            border-radius: inherit;
            z-index: -1;
            pointer-events: none;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #08080a;
        }
        ::-webkit-scrollbar-thumb {
            background: #2f2f37;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #595968;
        }

        /* Hero Image Black and White Styling */
        .bw-hero-portrait {
            filter: grayscale(100%) contrast(120%) brightness(95%);
            transition: filter 0.5s ease;
        }
        .bw-hero-portrait:hover {
            filter: grayscale(100%) contrast(125%) brightness(100%);
        }
    </style>
</head>
<body class="font-sans antialiased selection:bg-white selection:text-black min-h-screen flex flex-col justify-between relative">

    <!-- Ambient Liquid Background Artifacts -->
    <div class="fixed inset-0 overflow-hidden pointer-events-none z-0">
        <div class="absolute top-[-10%] left-[-10%] w-[50vw] h-[50vw] rounded-full bg-gradient-to-br from-mercury-900/20 to-transparent blur-[120px] animate-liquid-flow"></div>
        <div class="absolute top-[40%] right-[-10%] w-[45vw] h-[45vw] rounded-full bg-gradient-to-tl from-mercury-800/15 via-mercury-950/20 to-transparent blur-[140px] animate-liquid-flow" style="animation-delay: -5s;"></div>
        <div class="absolute bottom-[-10%] left-[20%] w-[60vw] h-[50vw] rounded-full bg-gradient-to-tr from-mercury-900/10 to-transparent blur-[150px] animate-liquid-flow" style="animation-delay: -10s;"></div>
        
        <!-- Subtle Grid Overlay -->
        <div class="absolute inset-0 bg-[linear-gradient(to_right,#ffffff03_1px,transparent_1px),linear-gradient(to_bottom,#ffffff03_1px,transparent_1px)] bg-[size:4rem_4rem] [mask-image:radial-gradient(ellipse_60%_50%_at_50%_50%,#000_70%,transparent_100%)]"></div>
    </div>

    <!-- Navigation Header -->
    <header class="sticky top-0 z-50 backdrop-blur-md bg-mercury-950/70 border-b border-white/5">
        <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
            <a href="#home" class="font-display font-bold text-2xl tracking-widest text-white chrome-text flex items-center gap-2 group">
                <span class="w-3 h-3 rounded-full bg-white group-hover:scale-125 transition-transform duration-300"></span>
                DIEGO
            </a>

            <!-- Desktop Nav -->
            <nav class="hidden md:flex items-center gap-8 text-xs tracking-widest uppercase text-mercury-300">
                <a href="#home" class="hover:text-white transition-colors duration-200">Home</a>
                <a href="#about" class="hover:text-white transition-colors duration-200">About</a>
                <a href="#music" class="hover:text-white transition-colors duration-200">Music</a>
                <a href="#portfolio" class="hover:text-white transition-colors duration-200">Portfolio</a>
                <a href="#achievements" class="hover:text-white transition-colors duration-200">Achievements</a>
                <a href="#contact" class="hover:text-white transition-colors duration-200">Contact</a>
            </nav>

            <!-- Social / Quick Action -->
            <div class="hidden md:flex items-center gap-4">
                <a href="#contact" class="px-5 py-2.5 rounded-full text-xs uppercase tracking-wider font-semibold glass-panel glass-panel-hover text-white border border-white/10 hover:border-white/30 transition-all">
                    Inquire
                </a>
            </div>

            <!-- Mobile Menu Toggle Button -->
            <button id="mobileMenuBtn" class="md:hidden text-white p-2 focus:outline-none" aria-label="Toggle Menu">
                <i data-lucide="menu" class="w-6 h-6"></i>
            </button>
        </div>

        <!-- Mobile Navigation Drawer -->
        <div id="mobileMenu" class="hidden md:hidden glass-panel border-b border-white/10 px-6 py-6 space-y-4 text-sm tracking-wider uppercase">
            <a href="#home" class="block text-mercury-300 hover:text-white mobile-link">Home</a>
            <a href="#about" class="block text-mercury-300 hover:text-white mobile-link">About</a>
            <a href="#music" class="block text-mercury-300 hover:text-white mobile-link">Music</a>
            <a href="#portfolio" class="block text-mercury-300 hover:text-white mobile-link">Portfolio</a>
            <a href="#achievements" class="block text-mercury-300 hover:text-white mobile-link">Achievements</a>
            <a href="#contact" class="block text-mercury-300 hover:text-white mobile-link">Contact</a>
        </div>
    </header>

    <main class="relative z-10 flex-grow">

        <!-- ================= HERO SECTION ================= -->
        <section id="home" class="relative min-h-[calc(100vh-5rem)] flex items-center justify-center py-16 px-6">
            <div class="max-w-7xl mx-auto w-full grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-8 items-center">
                
                <!-- Left Text Content -->
                <div class="lg:col-span-7 space-y-8 text-left">
                    <div class="space-y-4">
                        <h1 class="font-display text-5xl sm:text-7xl lg:text-8xl font-bold tracking-tight text-white leading-none chrome-text-silver uppercase">
                            DIEGO YOON
                        </h1>
                        <p class="text-lg sm:text-2xl font-light text-mercury-300 tracking-wide max-w-2xl leading-relaxed">
                            AI Lifestyle Influencer | Virtual Model | AI Indie Artist
                        </p>
                    </div>

                    <p class="text-sm sm:text-base text-mercury-400 font-light max-w-xl leading-relaxed">
                        A digital figure part of the new era of creative execution where human creativity meets artificial intelligence.
                    </p>

                    <!-- Hero Call-to-Actions -->
                    <div class="flex flex-wrap items-center gap-4 pt-4">
                        <a href="#music" class="px-8 py-4 rounded-full bg-white text-black font-semibold text-xs uppercase tracking-widest hover:bg-mercury-200 transition-all duration-300 shadow-[0_0_25px_rgba(255,255,255,0.15)] flex items-center gap-2">
                            <i data-lucide="play" class="w-4 h-4 fill-current"></i>
                            Listen Now
                        </a>
                        <a href="#portfolio" class="px-8 py-4 rounded-full glass-panel glass-panel-hover text-white font-semibold text-xs uppercase tracking-widest border border-white/10 hover:border-white/30 transition-all">
                            View Portfolio
                        </a>
                    </div>
                </div>

                <!-- Right Visual: Custom B&W Diego Portrait -->
                <div class="lg:col-span-5 relative flex justify-center">
                    <div class="relative w-full max-w-md aspect-[3/4] rounded-2xl overflow-hidden glass-panel p-2 border border-white/15 shadow-2xl group">
                        <!-- Liquid metallic overlay tag -->
                        <div class="absolute top-4 left-4 z-20 px-3 py-1 rounded-full glass-panel text-[10px] tracking-widest text-mercury-200 uppercase border border-white/10">
                            DIEGO YOON / Portrait
                        </div>
                        
                        <div class="w-full h-full rounded-xl overflow-hidden relative bg-mercury-900">
                            <img 
                                src="https://lh3.googleusercontent.com/d/1Y31Ua-nSKFBx_Ctx9_bR35DEyn4D4_G2" 
                                onerror="this.onerror=null; this.src='https://drive.google.com/thumbnail?id=1Y31Ua-nSKFBx_Ctx9_bR35DEyn4D4_G2&sz=w1000';" 
                                alt="Diego Yoon" 
                                class="w-full h-full object-cover object-top bw-hero-portrait transition-transform duration-700 group-hover:scale-105"
                            >
                            <!-- Gradient Shadow Overlay -->
                            <div class="absolute inset-0 bg-gradient-to-t from-mercury-950 via-transparent to-transparent opacity-80"></div>
                        </div>
                    </div>
                </div>

            </div>
        </section>


        <!-- ================= ABOUT ME SECTION ================= -->
        <section id="about" class="py-24 px-6 border-t border-white/5 bg-mercury-950/40 relative">
            <div class="max-w-7xl mx-auto space-y-16">
                
                <div class="flex flex-col md:flex-row md:items-end justify-between gap-6">
                    <div>
                        <span class="text-xs font-mono uppercase tracking-widest text-mercury-400">// 01 Architecture</span>
                        <h2 class="font-display text-3xl sm:text-5xl font-bold text-white chrome-text mt-2 uppercase">ABOUT THE PERSONA</h2>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div class="glass-panel p-8 rounded-2xl glass-panel-hover space-y-4">
                        <div class="w-10 h-10 rounded-lg bg-white/5 flex items-center justify-center text-white border border-white/10">
                            <i data-lucide="sparkles" class="w-5 h-5"></i>
                        </div>
                        <h3 class="font-display text-lg font-semibold text-white">Digital Identity</h3>
                        <p class="text-sm text-mercury-300 leading-relaxed font-light">
                            Crafted to virtually embody his human creator's personality, interests, and real-life experiences.
                        </p>
                    </div>

                    <div class="glass-panel p-8 rounded-2xl glass-panel-hover space-y-4">
                        <div class="w-10 h-10 rounded-lg bg-white/5 flex items-center justify-center text-white border border-white/10">
                            <i data-lucide="disc" class="w-5 h-5"></i>
                        </div>
                        <h3 class="font-display text-lg font-semibold text-white">Sonic Expression</h3>
                        <p class="text-sm text-mercury-300 leading-relaxed font-light">
                            Blending dark pop, ambient R&B grooves, and electronic soundscapes into original music compositions that explore connection, synthetic emotion, and identity.
                        </p>
                    </div>

                    <div class="glass-panel p-8 rounded-2xl glass-panel-hover space-y-4">
                        <div class="w-10 h-10 rounded-lg bg-white/5 flex items-center justify-center text-white border border-white/10">
                            <i data-lucide="layers" class="w-5 h-5"></i>
                        </div>
                        <h3 class="font-display text-lg font-semibold text-white">Visual Artistry</h3>
                        <p class="text-sm text-mercury-300 leading-relaxed font-light">
                            From editorial photoshoots to immersive brand collaborations, creating high-impact visual narratives designed for high fashion and modern creative projects.
                        </p>
                    </div>
                </div>

            </div>
        </section>


        <!-- ================= MUSIC SECTION ================= -->
        <section id="music" class="py-24 px-6 relative">
            <div class="max-w-7xl mx-auto space-y-16">
                
                <div class="flex flex-col md:flex-row md:items-end justify-between gap-6">
                    <div>
                        <span class="text-xs font-mono uppercase tracking-widest text-mercury-400">// 02 Discography & Streaming</span>
                        <h2 class="font-display text-3xl sm:text-5xl font-bold text-white chrome-text mt-2">Sonic Discography</h2>
                    </div>
                    <!-- Streaming Platform Links -->
                    <div class="flex flex-wrap items-center gap-3">
                        <a href="https://spotify.com" target="_blank" class="px-4 py-2 rounded-full glass-panel glass-panel-hover text-xs font-medium text-white border border-white/10 flex items-center gap-2">
                            <i data-lucide="music" class="w-4 h-4 text-emerald-400"></i> Spotify
                        </a>
                        <a href="https://music.apple.com" target="_blank" class="px-4 py-2 rounded-full glass-panel glass-panel-hover text-xs font-medium text-white border border-white/10 flex items-center gap-2">
                            <i data-lucide="disc-3" class="w-4 h-4 text-rose-400"></i> Apple Music
                        </a>
                        <a href="https://music.youtube.com" target="_blank" class="px-4 py-2 rounded-full glass-panel glass-panel-hover text-xs font-medium text-white border border-white/10 flex items-center gap-2">
                            <i data-lucide="youtube" class="w-4 h-4 text-red-500"></i> YouTube Music
                        </a>
                    </div>
                </div>

                <!-- Featured Single Showcase & Interactive Audio Player -->
                <div class="glass-panel rounded-3xl p-8 lg:p-12 border border-white/10 relative overflow-hidden">
                    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                        
                        <!-- Album Cover Artwork -->
                        <div class="lg:col-span-5 relative aspect-square rounded-2xl overflow-hidden glass-panel border border-white/15 group">
                            <div class="w-full h-full bg-gradient-to-br from-mercury-800 via-mercury-900 to-black flex items-center justify-center p-8 relative">
                                <div class="absolute inset-0 bg-[radial-gradient(circle_at_center,rgba(255,255,255,0.1),transparent_70%)]"></div>
                                <div class="text-center space-y-3 relative z-10">
                                    <div class="w-20 h-20 mx-auto rounded-full border border-white/20 flex items-center justify-center animate-spin-slow">
                                        <i data-lucide="disc" class="w-10 h-10 text-white/80"></i>
                                    </div>
                                    <span class="text-xs uppercase tracking-widest text-mercury-400 block font-mono">Debut Single</span>
                                    <h4 class="font-display text-2xl font-bold text-white chrome-text">TOUCH ME</h4>
                                </div>
                            </div>
                        </div>

                        <!-- Track Details & Interactive Player Controls -->
                        <div class="lg:col-span-7 space-y-8">
                            <div>
                                <span class="px-3 py-1 rounded-full text-[10px] uppercase tracking-widest bg-white/10 text-white font-mono border border-white/10">
                                    Now Playing Preview
                                </span>
                                <h3 class="font-display text-4xl sm:text-5xl font-bold text-white mt-4 chrome-text">TOUCH ME</h3>
                                <p class="text-mercury-400 text-sm mt-2">Written & Performed by Diego Yoon • Released 2026</p>
                            </div>

                            <p class="text-mercury-300 text-sm sm:text-base font-light leading-relaxed">
                                An atmospheric contemporary R&B single built on subtle hip-hop grooves, pulsing basslines, and reflective lyrical themes.
                            </p>

                            <!-- Audio Scrub Bar & Controls -->
                            <div class="space-y-4 pt-2">
                                <div class="flex items-center justify-between text-xs text-mercury-400 font-mono">
                                    <span id="currentTime">0:00</span>
                                    <span id="duration">2:45</span>
                                </div>
                                <div class="w-full h-1.5 bg-white/10 rounded-full overflow-hidden cursor-pointer relative" id="progressBarContainer">
                                    <div id="progressBar" class="h-full bg-white w-0 transition-all duration-200"></div>
                                </div>

                                <div class="flex items-center justify-between pt-2">
                                    <div class="flex items-center gap-4">
                                        <button id="playBtn" class="w-14 h-14 rounded-full bg-white text-black flex items-center justify-center hover:scale-105 transition-transform shadow-[0_0_20px_rgba(255,255,255,0.2)]">
                                            <i id="playIcon" data-lucide="play" class="w-6 h-6 fill-current translate-x-0.5"></i>
                                        </button>
                                        <div>
                                            <div class="text-sm font-semibold text-white">Preview Track</div>
                                            <div class="text-xs text-mercury-400">Stream complete version on platforms</div>
                                        </div>
                                    </div>

                                    <div class="flex items-center gap-3">
                                        <button class="p-3 rounded-full glass-panel hover:text-white text-mercury-400 transition-colors">
                                            <i data-lucide="share-2" class="w-4 h-4"></i>
                                        </button>
                                        <button class="p-3 rounded-full glass-panel hover:text-white text-mercury-400 transition-colors">
                                            <i data-lucide="heart" class="w-4 h-4"></i>
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>

                    </div>
                </div>

            </div>
        </section>


        <!-- ================= INFLUENCER PORTFOLIO SECTION ================= -->
        <section id="portfolio" class="py-24 px-6 border-t border-white/5 bg-mercury-950/30">
            <div class="max-w-7xl mx-auto space-y-16">
                
                <div class="flex flex-col md:flex-row md:items-end justify-between gap-6">
                    <div>
                        <span class="text-xs font-mono uppercase tracking-widest text-mercury-400">// 03 Creative Archive</span>
                        <h2 class="font-display text-3xl sm:text-5xl font-bold text-white chrome-text mt-2">Influencer Portfolio</h2>
                    </div>

                    <!-- Category Filter Buttons -->
                    <div class="flex flex-wrap items-center gap-2" id="portfolioFilters">
                        <button class="filter-btn active px-4 py-2 rounded-full text-xs uppercase tracking-wider font-semibold glass-panel bg-white text-black border border-white" data-filter="all">All Works</button>
                        <button class="filter-btn px-4 py-2 rounded-full text-xs uppercase tracking-wider font-semibold glass-panel text-mercury-300 border border-white/10 hover:border-white/30" data-filter="fashion">Editorial</button>
                        <button class="filter-btn px-4 py-2 rounded-full text-xs uppercase tracking-wider font-semibold glass-panel text-mercury-300 border border-white/10 hover:border-white/30" data-filter="brands">Campaigns</button>
                        <button class="filter-btn px-4 py-2 rounded-full text-xs uppercase tracking-wider font-semibold glass-panel text-mercury-300 border border-white/10 hover:border-white/30" data-filter="press">Press</button>
                    </div>
                </div>

                <!-- Portfolio Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6" id="portfolioGrid">
                    
                    <!-- Item 1: High Fashion -->
                    <div class="portfolio-item fashion glass-panel rounded-2xl overflow-hidden glass-panel-hover group border border-white/10" data-category="fashion">
                        <div class="aspect-[4/5] relative overflow-hidden bg-mercury-900">
                            <div class="w-full h-full bg-gradient-to-tr from-mercury-950 via-mercury-800 to-mercury-900 flex items-center justify-center p-6">
                                <div class="text-center space-y-2">
                                    <i data-lucide="camera" class="w-8 h-8 text-mercury-400 mx-auto opacity-60"></i>
                                    <span class="text-xs text-mercury-400 uppercase font-mono tracking-widest">Editorial Series</span>
                                    <h4 class="font-display text-xl text-white font-bold">LQUID CHROMIUM</h4>
                                </div>
                            </div>
                            <div class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex flex-col justify-end p-6">
                                <span class="text-xs text-mercury-300 font-mono">Paris Fashion Digital Week</span>
                                <h4 class="text-lg font-bold text-white">LQUID CHROMIUM '26</h4>
                            </div>
                        </div>
                    </div>

                    <!-- Item 2: Brand Campaign -->
                    <div class="portfolio-item brands glass-panel rounded-2xl overflow-hidden glass-panel-hover group border border-white/10" data-category="brands">
                        <div class="aspect-[4/5] relative overflow-hidden bg-mercury-900">
                            <div class="w-full h-full bg-gradient-to-bl from-mercury-950 via-mercury-900 to-mercury-800 flex items-center justify-center p-6">
                                <div class="text-center space-y-2">
                                    <i data-lucide="briefcase" class="w-8 h-8 text-mercury-400 mx-auto opacity-60"></i>
                                    <span class="text-xs text-mercury-400 uppercase font-mono tracking-widest">Brand Partnership</span>
                                    <h4 class="font-display text-xl text-white font-bold">NEO-AVANT GARDE</h4>
                                </div>
                            </div>
                            <div class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex flex-col justify-end p-6">
                                <span class="text-xs text-mercury-300 font-mono">Global Campaign</span>
                                <h4 class="text-lg font-bold text-white">Monochrome Eyewear</h4>
                            </div>
                        </div>
                    </div>

                    <!-- Item 3: Press Release -->
                    <div class="portfolio-item press glass-panel rounded-2xl overflow-hidden glass-panel-hover group border border-white/10" data-category="press">
                        <div class="aspect-[4/5] relative overflow-hidden bg-mercury-900">
                            <div class="w-full h-full bg-gradient-to-br from-mercury-900 via-mercury-950 to-black flex items-center justify-center p-6">
                                <div class="text-center space-y-2">
                                    <i data-lucide="newspaper" class="w-8 h-8 text-mercury-400 mx-auto opacity-60"></i>
                                    <span class="text-xs text-mercury-400 uppercase font-mono tracking-widest">Feature Article</span>
                                    <h4 class="font-display text-xl text-white font-bold">VIRTUAL VOICES</h4>
                                </div>
                            </div>
                            <div class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex flex-col justify-end p-6">
                                <span class="text-xs text-mercury-300 font-mono">Press Feature</span>
                                <h4 class="text-lg font-bold text-white">Redefining Digital Artistry</h4>
                            </div>
                        </div>
                    </div>

                </div>

            </div>
        </section>


        <!-- ================= ACHIEVEMENTS SECTION ================= -->
        <section id="achievements" class="py-24 px-6 relative">
            <div class="max-w-7xl mx-auto space-y-16">
                
                <div>
                    <span class="text-xs font-mono uppercase tracking-widest text-mercury-400">// 04 Milestones</span>
                    <h2 class="font-display text-3xl sm:text-5xl font-bold text-white chrome-text mt-2">Recognitions & Impact</h2>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                    <div class="glass-panel p-8 rounded-2xl border border-white/10 space-y-3">
                        <div class="font-display text-4xl font-bold text-white chrome-text">#1</div>
                        <div class="text-sm font-semibold text-white">Debut Single Charts</div>
                        <p class="text-xs text-mercury-400 font-light">Featured across top editorial indie R&B & dark pop playlists.</p>
                    </div>

                    <div class="glass-panel p-8 rounded-2xl border border-white/10 space-y-3">
                        <div class="font-display text-4xl font-bold text-white chrome-text">100%</div>
                        <div class="text-sm font-semibold text-white">Virtual Persona Concept</div>
                        <p class="text-xs text-mercury-400 font-light">Pioneering next-gen virtual model aesthetics and original music.</p>
                    </div>

                    <div class="glass-panel p-8 rounded-2xl border border-white/10 space-y-3">
                        <div class="font-display text-4xl font-bold text-white chrome-text">Global</div>
                        <div class="text-sm font-semibold text-white">Press Coverage</div>
                        <p class="text-xs text-mercury-400 font-light">Highlighted in modern fashion, AI innovation, and indie music press.</p>
                    </div>

                    <div class="glass-panel p-8 rounded-2xl border border-white/10 space-y-3">
                        <div class="font-display text-4xl font-bold text-white chrome-text">15+</div>
                        <div class="text-sm font-semibold text-white">Editorial Concepts</div>
                        <p class="text-xs text-mercury-400 font-light">High-fashion visual lookbooks and liquid chrome art direction.</p>
                    </div>
                </div>

            </div>
        </section>


        <!-- ================= CONTACT SECTION ================= -->
        <section id="contact" class="py-24 px-6 border-t border-white/5 bg-mercury-950/50 relative">
            <div class="max-w-4xl mx-auto space-y-12">
                
                <div class="text-center space-y-4">
                    <span class="text-xs font-mono uppercase tracking-widest text-mercury-400">// 05 Inquiry</span>
                    <h2 class="font-display text-3xl sm:text-5xl font-bold text-white chrome-text">Initiate Connection</h2>
                    <p class="text-mercury-400 text-sm max-w-lg mx-auto">
                        For brand collaborations, press inquiries, or music production partnerships.
                    </p>
                </div>

                <!-- Contact Form -->
                <form id="contactForm" class="glass-panel p-8 sm:p-12 rounded-3xl border border-white/10 space-y-6">
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                        <div class="space-y-2">
                            <label class="text-xs uppercase tracking-wider text-mercury-300 font-mono">Your Name</label>
                            <input type="text" required placeholder="Name or Organization" class="w-full px-4 py-3 rounded-xl bg-black/40 border border-white/10 text-white placeholder-mercury-600 focus:outline-none focus:border-white/40 text-sm transition-colors">
                        </div>
                        <div class="space-y-2">
                            <label class="text-xs uppercase tracking-wider text-mercury-300 font-mono">Email Address</label>
                            <input type="email" required placeholder="email@domain.com" class="w-full px-4 py-3 rounded-xl bg-black/40 border border-white/10 text-white placeholder-mercury-600 focus:outline-none focus:border-white/40 text-sm transition-colors">
                        </div>
                    </div>

                    <div class="space-y-2">
                        <label class="text-xs uppercase tracking-wider text-mercury-300 font-mono">Inquiry Type</label>
                        <select class="w-full px-4 py-3 rounded-xl bg-black/40 border border-white/10 text-white focus:outline-none focus:border-white/40 text-sm transition-colors">
                            <option value="brand">Brand Collaboration</option>
                            <option value="press">Press / Media Feature</option>
                            <option value="music">Music / Booking</option>
                            <option value="other">General Inquiry</option>
                        </select>
                    </div>

                    <div class="space-y-2">
                        <label class="text-xs uppercase tracking-wider text-mercury-300 font-mono">Message</label>
                        <textarea rows="4" required placeholder="Detail your proposal..." class="w-full px-4 py-3 rounded-xl bg-black/40 border border-white/10 text-white placeholder-mercury-600 focus:outline-none focus:border-white/40 text-sm transition-colors resize-none"></textarea>
                    </div>

                    <button type="submit" class="w-full py-4 rounded-xl bg-white text-black font-semibold text-xs uppercase tracking-widest hover:bg-mercury-200 transition-all shadow-[0_0_20px_rgba(255,255,255,0.15)] flex items-center justify-center gap-2">
                        <i data-lucide="send" class="w-4 h-4"></i>
                        Transmit Message
                    </button>

                    <div id="formSuccess" class="hidden text-center p-4 rounded-xl bg-emerald-500/10 border border-emerald-500/20 text-emerald-300 text-xs">
                        Message transmitted successfully. We will respond shortly.
                    </div>
                </form>

            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="border-t border-white/5 py-8 px-6 text-center text-xs text-mercury-500 relative z-10 bg-mercury-950">
        <div class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-4">
            <div class="font-display font-bold text-white text-sm">DIEGO YOON</div>
            <div>© 2026 Diego Yoon. All rights reserved.</div>
            <div class="flex items-center gap-4 text-mercury-400">
                <a href="#home" class="hover:text-white">Top ↑</a>
            </div>
        </div>
    </footer>

    <!-- Interactive Scripts -->
    <script>
        // Initialize Lucide Icons
        lucide.createIcons();

        // Mobile Navigation Toggle
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        const mobileLinks = document.querySelectorAll('.mobile-link');

        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
            });
        });

        // Audio Preview Simulator
        const playBtn = document.getElementById('playBtn');
        const playIcon = document.getElementById('playIcon');
        const progressBar = document.getElementById('progressBar');
        const currentTimeEl = document.getElementById('currentTime');
        
        let isPlaying = false;
        let progress = 0;
        let audioInterval;

        playBtn.addEventListener('click', () => {
            isPlaying = !isPlaying;
            if (isPlaying) {
                playIcon.setAttribute('data-lucide', 'pause');
                lucide.createIcons();
                audioInterval = setInterval(() => {
                    if (progress >= 100) {
                        progress = 0;
                        isPlaying = false;
                        playIcon.setAttribute('data-lucide', 'play');
                        lucide.createIcons();
                        clearInterval(audioInterval);
                    } else {
                        progress += 0.5;
                        progressBar.style.width = progress + '%';
                        
                        // Time calculation (2:45 total = 165s)
                        const currentSecs = Math.floor((progress / 100) * 165);
                        const mins = Math.floor(currentSecs / 60);
                        const secs = currentSecs % 60;
                        currentTimeEl.textContent = `${mins}:${secs < 10 ? '0' : ''}${secs}`;
                    }
                }, 200);
            } else {
                playIcon.setAttribute('data-lucide', 'play');
                lucide.createIcons();
                clearInterval(audioInterval);
            }
        });

        // Portfolio Filter Tabs
        const filterBtns = document.querySelectorAll('.filter-btn');
        const portfolioItems = document.querySelectorAll('.portfolio-item');

        filterBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                filterBtns.forEach(b => {
                    b.classList.remove('bg-white', 'text-black');
                    b.classList.add('text-mercury-300');
                });
                btn.classList.add('bg-white', 'text-black');
                btn.classList.remove('text-mercury-300');

                const filter = btn.getAttribute('data-filter');
                portfolioItems.forEach(item => {
                    if (filter === 'all' || item.getAttribute('data-category') === filter) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });

        // Contact Form Submission Handler
        const contactForm = document.getElementById('contactForm');
        const formSuccess = document.getElementById('formSuccess');

        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            formSuccess.classList.remove('hidden');
            contactForm.reset();
            setTimeout(() => {
                formSuccess.classList.add('hidden');
            }, 5000);
        });
    </script>
</body>
</html>
