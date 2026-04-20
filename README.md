<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>RISER COTTON • Rising Star Actress</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&amp;family=Playfair+Display:wght@700&amp;display=swap');
        
        body { font-family: 'Inter', system_ui, sans-serif; }
        .heading-serif { font-family: 'Playfair Display', Georgia, serif; font-weight: 700; letter-spacing: -0.025em; }
        
        .cinematic-bg { background: radial-gradient(circle at center, #1a1a2e 0%, #000000 80%); position: relative; overflow: hidden; }
        .film-grain { position: absolute; inset: 0; background-image: linear-gradient(rgba(255,255,255,0.02) 50%, transparent 50%), linear-gradient(90deg, rgba(255,255,255,0.02) 50%, transparent 50%); background-size: 4px 4px; pointer-events: none; z-index: 1; animation: grain 80ms steps(1) infinite; }
        
        .neon-text { text-shadow: 0 0 5px #FFD700, 0 0 10px #FFD700, 0 0 20px #C084FC, 0 0 40px #B91C1C; }
        .gold-glow { box-shadow: 0 0 15px rgba(255,215,0,0.6), 0 0 30px rgba(255,215,0,0.3); }
        
        .photo-card { transition: all 0.3s cubic-bezier(0.23,1,0.32,1); }
        .photo-card:hover { transform: scale(1.02); }
        
        .portfolio-grid { column-count: 1; column-gap: 1rem; }
        @media (min-width: 640px) { .portfolio-grid { column-count: 2; } }
        @media (min-width: 1024px) { .portfolio-grid { column-count: 3; } }
        .portfolio-item { break-inside: avoid; margin-bottom: 1rem; }
        
        .spotlight { display: none; }
        @media (min-width: 768px) { .spotlight { display: block; } }
        
        .mobile-hero-text { font-size: 3.25rem; line-height: 1; }
        @media (min-width: 640px) { .mobile-hero-text { font-size: 5.5rem; } }
        @media (min-width: 1024px) { .mobile-hero-text { font-size: 7.5rem; } }
        
        button, .photo-card { touch-action: manipulation; }
    </style>
</head>
<body class="bg-black text-white overflow-x-hidden">
    <!-- NAV -->
    <nav class="fixed top-0 left-0 right-0 z-50 bg-black/95 backdrop-blur-lg border-b border-white/10">
        <div class="max-w-7xl mx-auto px-5 h-20 flex items-center justify-between">
            <div class="flex items-center gap-x-3">
                <div class="flex items-center gap-x-2">
                    <div class="w-9 h-9 rounded-full bg-gradient-to-br from-yellow-400 via-purple-500 to-red-600 flex items-center justify-center">
                        <span class="text-black font-bold text-xl tracking-tighter">R</span>
                    </div>
                    <div>
                        <div class="font-bold text-2xl tracking-tighter">RISER</div>
                        <div class="text-[9px] text-white/60 -mt-1 tracking-[2px]">COTTON</div>
                    </div>
                </div>
            </div>
            
            <div class="hidden md:flex items-center gap-x-8 text-sm font-medium">
                <a href="#about" class="hover:text-yellow-400 transition-colors">About</a>
                <a href="#gallery" class="hover:text-yellow-400 transition-colors">Gallery</a>
                <a href="#reel" class="hover:text-yellow-400 transition-colors">Reel</a>
                <a href="#dreams" class="hover:text-yellow-400 transition-colors">Dream Roles</a>
            </div>
            
            <div class="flex items-center gap-x-3">
                <a href="#contact" class="px-5 py-2 rounded-full border border-yellow-400 text-yellow-400 hover:bg-yellow-400 hover:text-black text-sm font-semibold transition-all active:scale-95">BOOK</a>
                <button id="mobile-menu-btn" class="md:hidden w-11 h-11 flex items-center justify-center text-xl"><i class="fa-solid fa-bars"></i></button>
            </div>
        </div>
    </nav>

    <!-- HERO -->
    <header class="relative min-h-[100dvh] flex items-center justify-center cinematic-bg pt-20">
        <div class="absolute inset-0 bg-[radial-gradient(#ffffff10_0.8px,transparent_1px)] bg-[length:4px_4px]"></div>
        <div class="film-grain"></div>
        
        <div class="relative z-20 max-w-5xl mx-auto px-5 text-center">
            <div class="inline-flex items-center gap-x-2 px-4 py-1.5 rounded-full bg-white/5 border border-white/20 mb-6">
                <div class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></div>
                <span class="uppercase text-xs tracking-[2px] font-medium text-white/80">OPEN FOR AUDITIONS 2026</span>
            </div>
            
            <h1 class="mobile-hero-text font-black tracking-tighter mb-4 glitch neon-text" data-text="RISER COTTON">RISER<br>COTTON</h1>
            
            <p class="max-w-xs mx-auto text-2xl text-white/90 font-light tracking-tight mb-8">11 • Actress • Future Star</p>
            
            <div class="flex flex-col gap-4 px-2">
                <button onclick="document.getElementById('gallery').scrollIntoView({behavior:'smooth'})" 
                        class="w-full py-4 rounded-2xl bg-white text-black font-semibold text-lg active:scale-[0.985] transition-all">
                    VIEW THE PHOTOS
                </button>
                <button onclick="watchReel()" 
                        class="w-full py-4 rounded-2xl border border-white/40 text-lg flex items-center justify-center gap-x-2 active:bg-white/10 transition-all">
                    <i class="fa-solid fa-play"></i> <span>WATCH THE REEL</span>
                </button>
            </div>
        </div>
        
        <canvas id="hero-particles" class="absolute inset-0 z-10 pointer-events-none"></canvas>
    </header>

    <!-- ABOUT -->
    <section id="about" class="max-w-5xl mx-auto px-5 py-16">
        <div class="grid md:grid-cols-12 gap-x-8 items-center">
            <div class="md:col-span-7">
                <div class="uppercase tracking-[3px] text-xs text-yellow-400 mb-3">CHAPTER 01</div>
                <h2 class="text-6xl md:text-7xl leading-none tracking-tighter heading-serif mb-8">Meet Riser.</h2>
                <div class="text-xl text-white/90 max-w-[42ch]">
                    <p class="mb-6">At just 11 years old, Riser has that rare star quality — natural charisma, emotional depth, and a smile that lights up any room.</p>
                    <p>Whether she’s delivering a dramatic monologue or jumping for joy in a trench coat, she brings pure magic to every shoot.</p>
                </div>
            </div>
            <div class="md:col-span-5 mt-12 md:mt-0">
                <div class="relative group">
                    <img src="IMG_2811.JPEG" alt="Riser Cotton headshot" class="w-full rounded-3xl shadow-2xl gold-glow object-cover aspect-[4/5]">
                    <div class="absolute -bottom-4 -right-4 bg-black border border-yellow-400 px-4 py-1.5 rounded-2xl text-sm flex items-center gap-x-2">
                        <i class="fa-solid fa-star text-yellow-400"></i>
                        <span class="font-semibold">Jinah Manly Photography</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- STATS -->
    <div class="bg-zinc-950 py-8 border-y border-white/10">
        <div class="max-w-5xl mx-auto px-5 grid grid-cols-2 md:grid-cols-4 gap-6 text-center">
            <div><div class="text-5xl font-black text-yellow-400">98</div><div class="text-xs text-white/60 mt-1 tracking-widest">CHARISMA</div></div>
            <div><div class="text-5xl font-black text-yellow-400">95</div><div class="text-xs text-white/60 mt-1 tracking-widest">EMOTIONAL RANGE</div></div>
            <div><div class="text-5xl font-black text-yellow-400">100</div><div class="text-xs text-white/60 mt-1 tracking-widest">SMILE POWER</div></div>
            <div><div class="text-5xl font-black text-yellow-400">92</div><div class="text-xs text-white/60 mt-1 tracking-widest">JOY FACTOR</div></div>
        </div>
    </div>

    <!-- GALLERY -->
    <section id="gallery" class="max-w-7xl mx-auto px-5 py-16">
        <div class="mb-10">
            <div class="uppercase tracking-[3px] text-xs text-yellow-400">CHAPTER 02</div>
            <h2 class="text-6xl tracking-tighter heading-serif">The Spotlight Gallery</h2>
            <p class="text-white/70 mt-2">9 exclusive moments • Jinah Manly Photography</p>
        </div>
        
        <div class="portfolio-grid" id="gallery-grid"></div>
    </section>

    <!-- REEL -->
    <section id="reel" class="bg-zinc-950 py-16 border-y border-white/10">
        <div class="max-w-5xl mx-auto px-5 text-center">
            <div class="uppercase tracking-[3px] text-xs text-yellow-400 mb-3">CHAPTER 03</div>
            <h2 class="text-6xl tracking-tighter heading-serif mb-6">The Reel</h2>
            
            <div onclick="watchReel()" class="relative mx-auto max-w-[820px] aspect-video rounded-3xl overflow-hidden shadow-2xl border border-white/10 group cursor-pointer">
                <img src="IMG_1179.JPG" class="w-full h-full object-cover" alt="Riser jumping with joy">
                <div class="absolute inset-0 bg-black/60 flex items-center justify-center group-active:bg-black/40 transition-all">
                    <div class="w-20 h-20 rounded-full border-4 border-white flex items-center justify-center">
                        <i class="fa-solid fa-play text-4xl ml-1 text-white"></i>
                    </div>
                </div>
                <div class="absolute bottom-6 left-6 text-sm font-medium hidden md:block">“Riser brings an authenticity that’s rare for her age.”</div>
            </div>
        </div>
    </section>

    <!-- DREAM ROLES -->
    <section id="dreams" class="max-w-5xl mx-auto px-5 py-16">
        <div class="text-center mb-12">
            <div class="uppercase tracking-[3px] text-xs text-yellow-400 mb-3">CHAPTER 04</div>
            <h2 class="text-6xl tracking-tighter heading-serif">Roles She Was Born To Play</h2>
        </div>
        
        <div class="grid md:grid-cols-3 gap-6">
            <div class="bg-zinc-900 border border-white/10 rounded-3xl p-8">
                <div class="text-xs uppercase tracking-widest text-purple-400">DISNEY+</div>
                <div class="text-3xl font-semibold mt-3 leading-none">Young Heroine<br>in Epic Fantasy</div>
                <div class="mt-6 text-sm text-white/70">A brave young wizard discovering her powers.</div>
            </div>
            <div class="bg-zinc-900 border border-white/10 rounded-3xl p-8">
                <div class="text-xs uppercase tracking-widest text-red-400">NETFLIX</div>
                <div class="text-3xl font-semibold mt-3 leading-none">Lead in Coming-of-Age<br>Drama Series</div>
                <div class="mt-6 text-sm text-white/70">A resilient girl navigating friendship &amp; big changes.</div>
            </div>
            <div class="bg-zinc-900 border border-white/10 rounded-3xl p-8">
                <div class="text-xs uppercase tracking-widest text-blue-400">MARVEL STUDIOS</div>
                <div class="text-3xl font-semibold mt-3 leading-none">Young Superhero<br>Origin Story</div>
                <div class="mt-6 text-sm text-white/70">A clever kid who gains powers and learns what it means to be a hero.</div>
            </div>
        </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="max-w-xl mx-auto px-5 py-16 text-center">
        <div class="mb-8"><div class="inline-flex px-4 py-1 bg-yellow-400 text-black text-xs font-bold tracking-[2px] rounded-full">NEXT CHAPTER</div></div>
        <h2 class="text-6xl tracking-tighter heading-serif mb-4">Ready to cast the next big star?</h2>
        <p class="text-xl text-white/70 mb-10">Riser is available for film, TV, commercials &amp; theater.</p>
        
        <form id="contact-form" onsubmit="submitBookingForm(event)" class="text-left">
            <div class="space-y-4">
                <input type="text" placeholder="Your Name" required class="w-full bg-white/5 border border-white/20 focus:border-yellow-400 placeholder:text-white/50 px-6 py-4 rounded-2xl text-lg">
                <input type="text" placeholder="Production / Company" required class="w-full bg-white/5 border border-white/20 focus:border-yellow-400 placeholder:text-white/50 px-6 py-4 rounded-2xl text-lg">
                <input type="email" placeholder="Email Address" required class="w-full bg-white/5 border border-white/20 focus:border-yellow-400 placeholder:text-white/50 px-6 py-4 rounded-2xl text-lg">
                <textarea placeholder="Tell us about the role..." rows="4" required class="w-full bg-white/5 border border-white/20 focus:border-yellow-400 placeholder:text-white/50 px-6 py-4 rounded-3xl text-lg resize-y"></textarea>
            </div>
            <button type="submit" class="mt-6 w-full py-4 rounded-2xl bg-gradient-to-r from-yellow-400 to-amber-500 text-black font-extrabold text-lg active:scale-[0.985]">SEND AUDITION REQUEST</button>
        </form>
    </section>

    <footer class="bg-black border-t border-white/10 py-12 text-center text-xs text-white/50">
        © 2026 Riser Cotton • Photos by Jinah Manly Photography
    </footer>

    <!-- MODAL -->
    <div id="photo-modal" onclick="if (event.target.id === 'photo-modal') closeModal()" class="hidden fixed inset-0 bg-black/95 z-[100] flex items-center justify-center p-4">
        <div onclick="event.stopImmediatePropagation()" class="modal relative w-full max-w-[1000px]">
            <button onclick="closeModal()" class="absolute -top-3 -right-3 z-10 w-12 h-12 flex items-center justify-center bg-zinc-900 hover:bg-red-600 transition rounded-full text-white border border-white/30 text-2xl">×</button>
            
            <div class="bg-zinc-900 rounded-3xl overflow-hidden border border-white/10">
                <div class="relative bg-black flex items-center justify-center min-h-[420px]">
                    <img id="modal-image" class="max-h-[70vh] w-auto max-w-full object-contain" alt="">
                </div>
                <div class="p-6 md:p-8">
                    <div id="modal-category" class="uppercase text-xs tracking-[2.5px] text-yellow-400"></div>
                    <div id="modal-title" class="text-4xl font-semibold tracking-tight mt-1"></div>
                    <div id="modal-caption" class="mt-4 text-white/80 text-[15px] leading-snug"></div>
                </div>
            </div>
            
            <div class="flex justify-between mt-4 px-2 text-xs text-white/60">
                <button onclick="prevPhoto()" class="flex items-center gap-x-2 hover:text-white transition"><i class="fa-solid fa-chevron-left"></i> PREV</button>
                <div class="font-mono" id="modal-counter">01 / 09</div>
                <button onclick="nextPhoto()" class="flex items-center gap-x-2 hover:text-white transition">NEXT <i class="fa-solid fa-chevron-right"></i></button>
            </div>
        </div>
    </div>

    <script>
        // All the same beautiful JS from before (particles, modal, confetti, etc.)
        function initializeTailwind() {
            tailwind.config = { theme: { extend: {} } };
        }

        function createHeroParticles() {
            const canvas = document.getElementById('hero-particles');
            if (!canvas) return;
            const ctx = canvas.getContext('2d');
            let particles = [];
            function resize() { canvas.width = window.innerWidth; canvas.height = window.innerHeight; }
            window.addEventListener('resize', resize);
            resize();
            class Particle {
                constructor() { this.reset(); }
                reset() { this.x = Math.random() * canvas.width; this.y = Math.random() * canvas.height * 0.6; this.size = Math.random() * 2.5 + 1.2; this.speed = Math.random() * 0.5 + 0.25; this.opacity = Math.random() * 0.6 + 0.3; this.twinkle = Math.random() * Math.PI * 2; }
                update() { this.y -= this.speed; this.twinkle += 0.02; if (this.y < -10) { this.reset(); this.y = canvas.height * 0.7 + Math.random() * 150; } }
                draw() { ctx.save(); ctx.fillStyle = '#FFD700'; ctx.globalAlpha = this.opacity * (0.5 + Math.sin(this.twinkle) * 0.5); ctx.shadowBlur = 8; ctx.shadowColor = '#FFD700'; ctx.beginPath(); ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2); ctx.fill(); ctx.restore(); }
            }
            for (let i = 0; i < 55; i++) particles.push(new Particle());
            function animate() { ctx.clearRect(0, 0, canvas.width, canvas.height); particles.forEach(p => { p.update(); p.draw(); }); requestAnimationFrame(animate); }
            animate();
        }

        const galleryPhotos = [
            { id: 1, src: "IMG_1181.JPG", category: "FASHION", title: "Trench Coat Elegance", caption: "Side profile power pose — pure sophistication." },
            { id: 2, src: "IMG_1178.JPG", category: "PORTRAIT", title: "Barefoot Confidence", caption: "Full-body trench coat moment. Effortless cool." },
            { id: 3, src: "IMG_1179.JPG", category: "ACTION", title: "Pure Joy", caption: "Mid-air happiness! This one captures her spirit perfectly." },
            { id: 4, src: "IMG_2814.JPEG", category: "DRAMATIC", title: "Thoughtful Muse", caption: "Finger on chin — already thinking like a leading lady." },
            { id: 5, src: "IMG_2822.JPEG", category: "CASUAL", title: "Casual Cool", caption: "Brown top + jeans. That smile wins every time." },
            { id: 6, src: "IMG_2817.JPEG", category: "FASHION", title: "Puffer Vest Glow", caption: "White vest energy — cozy and confident." },
            { id: 7, src: "IMG_2821.JPEG", category: "FUN", title: "Denim Cowgirl", caption: "White cowboy hat + denim jacket. Total star power." },
            { id: 8, src: "IMG_2816.JPEG", category: "FASHION", title: "Pink Puffer Chic", caption: "Pink puffer + beanie. Cozy couture vibes." },
            { id: 9, src: "IMG_2811.JPEG", category: "HEADSHOT", title: "Signature Headshot", caption: "The one that stops casting directors in their tracks." }
        ];

        let currentPhotoIndex = 0;

        function renderGallery() {
            const grid = document.getElementById('gallery-grid');
            grid.innerHTML = '';
            galleryPhotos.forEach((photo, index) => {
                const item = document.createElement('div');
                item.className = `portfolio-item photo-card rounded-3xl overflow-hidden cursor-pointer border border-white/10 shadow-xl`;
                item.innerHTML = `
                    <div class="relative">
                        <img src="${photo.src}" alt="${photo.title}" class="w-full h-auto object-cover aspect-[4/5]" loading="lazy">
                        <div class="absolute bottom-0 left-0 right-0 p-4 bg-gradient-to-t from-black/90 to-transparent">
                            <div class="text-[10px] font-mono tracking-widest text-yellow-400">${photo.category}</div>
                            <div class="text-white text-xl font-semibold tracking-tight">${photo.title}</div>
                        </div>
                    </div>
                `;
                item.onclick = () => openPhotoModal(index);
                grid.appendChild(item);
            });
        }

        function openPhotoModal(index) {
            currentPhotoIndex = index;
            const photo = galleryPhotos[index];
            const modal = document.getElementById('photo-modal');
            document.getElementById('modal-image').src = photo.src;
            document.getElementById('modal-title').textContent = photo.title;
            document.getElementById('modal-category').textContent = photo.category;
            document.getElementById('modal-caption').textContent = photo.caption;
            document.getElementById('modal-counter').textContent = `${String(index + 1).padStart(2, '0')} / 09`;
            modal.classList.remove('hidden');
            modal.classList.add('flex');
            document.onkeydown = (e) => {
                if (e.key === "Escape") closeModal();
                if (e.key === "ArrowRight") nextPhoto();
                if (e.key === "ArrowLeft") prevPhoto();
            };
        }

        function closeModal() {
            const modal = document.getElementById('photo-modal');
            modal.classList.remove('flex');
            modal.classList.add('hidden');
            document.onkeydown = null;
        }

        function nextPhoto() { currentPhotoIndex = (currentPhotoIndex + 1) % galleryPhotos.length; openPhotoModal(currentPhotoIndex); }
        function prevPhoto() { currentPhotoIndex = (currentPhotoIndex - 1 + galleryPhotos.length) % galleryPhotos.length; openPhotoModal(currentPhotoIndex); }

        function watchReel() {
            const modal = document.createElement('div');
            modal.className = `fixed inset-0 bg-black/95 z-[200] flex items-center justify-center p-4`;
            modal.innerHTML = `
                <div class="relative w-full max-w-[900px] aspect-video bg-zinc-950 rounded-3xl overflow-hidden border border-white/20">
                    <div class="absolute inset-0 flex items-center justify-center">
                        <div class="text-center px-6">
                            <div class="mx-auto mb-6 w-16 h-16 border-4 border-yellow-400 border-t-transparent animate-spin rounded-full"></div>
                            <div class="text-3xl font-bold tracking-tighter mb-2">NOW PLAYING</div>
                            <div class="text-xl text-white/90">Riser Cotton • 2026 Highlight Reel</div>
                        </div>
                    </div>
                    <button onclick="this.closest('.fixed').remove()" class="absolute top-4 right-4 text-white text-4xl">×</button>
                </div>
            `;
            document.body.appendChild(modal);
            setTimeout(() => { if (modal.parentNode) modal.parentNode.removeChild(modal); }, 4200);
        }

        function submitBookingForm(e) {
            e.preventDefault();
            const btn = e.target.querySelector('button');
            const original = btn.innerHTML;
            btn.innerHTML = `SENDING...`;
            btn.disabled = true;
            setTimeout(() => {
                btn.innerHTML = `✓ SENT!`;
                btn.style.background = '#22c55e';
                launchConfetti();
                setTimeout(() => {
                    alert("Thank you! Riser's team will reply within 48 hours ✨");
                    e.target.reset();
                    btn.innerHTML = original;
                    btn.style.background = '';
                    btn.disabled = false;
                }, 1200);
            }, 1100);
        }

        function launchConfetti() {
            const colors = ['#FFD700', '#C084FC', '#B91C1C'];
            for (let i = 0; i < 70; i++) {
                setTimeout(() => {
                    const c = document.createElement('div');
                    c.style.cssText = `position:fixed;left:${Math.random()*100}vw;top:-20px;width:8px;height:8px;background:${colors[Math.floor(Math.random()*3)]};z-index:99999;pointer-events:none;border-radius:50%`;
                    document.body.appendChild(c);
                    c.animate([{transform:'translateY(0)'}, {transform:`translateY(${window.innerHeight+100}px)`}], {duration: Math.random()*3000+2200, easing:'ease-out'}).onfinish = () => c.remove();
                }, i * 0.5);
            }
        }

        function initMobileMenu() {
            const btn = document.getElementById('mobile-menu-btn');
            if (!btn) return;
            btn.onclick = () => {
                const menu = document.createElement('div');
                menu.className = `fixed inset-0 bg-black/95 z-[90] flex flex-col pt-20 px-6`;
                menu.innerHTML = `
                    <div class="flex flex-col text-3xl font-light gap-y-4">
                        <a href="#about" class="py-4 border-b border-white/10">About Riser</a>
                        <a href="#gallery" class="py-4 border-b border-white/10">Gallery</a>
                        <a href="#reel" class="py-4 border-b border-white/10">The Reel</a>
                        <a href="#dreams" class="py-4 border-b border-white/10">Dream Roles</a>
                        <a href="#contact" class="py-4">Book Riser</a>
                    </div>
                `;
                document.body.appendChild(menu);
                menu.onclick = (e) => { if (e.target === menu) menu.remove(); };
            };
        }

        function initializeWebsite() {
            initializeTailwind();
            createHeroParticles();
            renderGallery();
            initMobileMenu();
            
            // Mobile-friendly stat animation
            const stats = document.querySelector('.bg-zinc-950');
            if (stats) {
                const obs = new IntersectionObserver((entries) => {
                    if (entries[0].isIntersecting) {
                        document.querySelectorAll('.bg-zinc-950 .text-5xl').forEach(el => el.style.transition = 'all 1.2s cubic-bezier(0.34,1.56,0.64,1)');
                        obs.disconnect();
                    }
                });
                obs.observe(stats);
            }
            
            console.log('%c[RISER COTTON] ✨ Mobile-optimized site loaded with all 9 photos!', 'color:#FFD700');
        }

        window.onload = initializeWebsite;
    </script>
</body>
</html>
