# baby.wishesh<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Srishti Babyy ❤️</title>
    
    <!-- 1. External Libraries -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    
    <!-- 2. Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600&family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&display=swap" rel="stylesheet">

    <!-- 3. Tailwind Config -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        serif: ['"Playfair Display"', 'serif'],
                        sans: ['"Outfit"', 'sans-serif'],
                    },
                    colors: {
                        dark: '#0c0a09',
                    },
                    animation: {
                        'pulse-slow': 'pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                    }
                }
            }
        }
    </script>

    <!-- 4. Custom CSS -->
    <style>
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            background-color: #0c0a09;
            color: #f3f4f6;
        }

        /* --- Aurora Background --- */
        #aurora-layer {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            background: 
                radial-gradient(circle at 15% 50%, hsla(333,70%,55%,.25), transparent 25%), 
                radial-gradient(circle at 85% 30%, hsla(282, 82%, 54%, .2), transparent 25%), 
                radial-gradient(circle at 50% 50%, hsla(210, 89%, 60%, .15), transparent 50%),
                radial-gradient(circle at 50% 80%, hsla(35, 90%, 60%, .15), transparent 40%);
            filter: blur(60px);
            animation: auroraMove 15s ease-in-out infinite alternate;
        }

        @keyframes auroraMove {
            0% { transform: scale(1); opacity: 0.8; }
            100% { transform: scale(1.2); opacity: 1; }
        }

        /* --- Three.js Layer --- */
        #canvas-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        /* --- Glass Cards --- */
        .glass-card {
            background: rgba(20, 20, 20, 0.6);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
        }

        /* --- Text Gradients --- */
        .text-gradient {
            background: linear-gradient(to right, #fce7f3, #fbcfe8, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* --- Buttons --- */
        .btn-modern {
            background: linear-gradient(135deg, #ec4899 0%, #ef4444 100%);
            transition: all 0.3s ease;
            box-shadow: 0 0 20px rgba(236, 72, 153, 0.4);
        }
        .btn-modern:hover {
            transform: scale(1.05) translateY(-2px);
            box-shadow: 0 0 30px rgba(236, 72, 153, 0.7);
        }
        .btn-modern:active {
            transform: scale(0.98);
        }

        /* --- Polaroid Effect --- */
        .polaroid-container {
            perspective: 1000px;
        }
        .polaroid {
            background: white;
            padding: 12px 12px 50px 12px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.6);
            transform-style: preserve-3d;
            transition: transform 0.1s ease-out;
        }
        
        /* --- Utilities --- */
        .hidden-step {
            display: none;
            opacity: 0;
        }
        
        .bento-item {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: background 0.3s;
        }
        .bento-item:hover {
            background: rgba(255, 255, 255, 0.07);
        }
        
        /* Image styling for Step 5 */
        .finale-image-container {
            box-shadow: 0 0 25px rgba(236, 72, 153, 0.3);
            border: 2px solid rgba(255,255,255,0.2);
        }
    </style>
</head>
<body>

    <!-- Background Layers -->
    <div id="aurora-layer"></div>
    <div id="canvas-container"></div>

    <!-- Progress Bar -->
    <div class="fixed top-0 left-0 w-full h-1.5 bg-white/5 backdrop-blur-sm z-50">
        <div id="progress-bar" class="h-full bg-gradient-to-r from-pink-500 to-red-500 w-0 transition-all duration-700 ease-out"></div>
    </div>

    <!-- Main Content -->
    <main class="relative w-full h-full flex items-center justify-center p-4">

        <!-- STEP 1: WELCOME -->
        <div id="step-1" class="step absolute inset-0 flex flex-col items-center justify-center z-10">
            <div class="glass-card p-10 md:p-14 rounded-3xl max-w-lg w-full text-center flex flex-col items-center gap-6">
                <div class="text-7xl filter drop-shadow-lg animate-pulse-slow">❤️</div>
                <h1 class="font-serif text-4xl md:text-5xl font-bold text-gradient leading-tight">Hey Beautiful,</h1>
                <p class="font-sans text-gray-300 text-lg font-light leading-relaxed">
                    I built a little world for you, myy babydoll, just to bring a smile to your face on your special day.
                </p>
                <button onclick="goToStep(2)" class="btn-modern px-10 py-3 rounded-full text-white font-bold text-lg tracking-wide mt-4">
                    Let's Begin
                </button>
            </div>
        </div>

        <!-- STEP 2: MESSAGE -->
        <div id="step-2" class="step hidden-step absolute inset-0 flex flex-col items-center justify-center z-10">
            <div class="glass-card p-10 md:p-14 rounded-3xl max-w-lg w-full text-center flex flex-col items-center gap-6">
                <div class="text-7xl animate-bounce">🎉</div>
                <h1 class="font-serif text-4xl md:text-5xl font-bold text-gradient leading-tight">
                    Happy Birthday!<br>Srishti darling
                </h1>
                <p class="font-sans text-gray-300 text-lg font-light leading-relaxed">
                    Another year of you making the world brighter. Your existence is a gift, and I'm so lucky to witness it.
                </p>
                <button onclick="goToStep(3)" class="btn-modern px-10 py-3 rounded-full text-white font-bold text-lg tracking-wide mt-4">
                    There's more...
                </button>
            </div>
        </div>

        <!-- STEP 3: BENTO GRID -->
        <div id="step-3" class="step hidden-step absolute inset-0 flex flex-col items-center justify-center z-10">
            <div class="glass-card p-6 md:p-10 rounded-3xl max-w-2xl w-full flex flex-col items-center gap-6">
                <h2 class="font-serif text-3xl font-bold text-gradient text-center">A Few Things I Adore About You</h2>
                
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4 w-full">
                    <div class="bento-item md:col-span-2 p-5 rounded-2xl">
                        <h3 class="font-serif text-xl text-pink-300 mb-2">✨ Your Unmatched Kindness</h3>
                        <p class="font-sans text-sm text-gray-400">The genuine warmth you show to everyone is something truly rare and beautiful.</p>
                    </div>
                    <div class="bento-item p-5 rounded-2xl">
                        <h3 class="font-serif text-xl text-pink-300 mb-2">😊 That Smile</h3>
                        <p class="font-sans text-sm text-gray-400">It's a work of art. Seriously.</p>
                    </div>
                    <div class="bento-item md:col-span-2 p-5 rounded-2xl">
                        <h3 class="font-serif text-xl text-pink-300 mb-2">🌟 Your Radiant Spirit</h3>
                        <p class="font-sans text-sm text-gray-400">Your passion for life is infectious. Being around you makes everything feel more exciting and possible.</p>
                    </div>
                </div>

                <button onclick="goToStep(4)" class="btn-modern px-8 py-3 rounded-full text-white font-bold tracking-wide mt-2">
                    Remember this?
                </button>
            </div>
        </div>

        <!-- STEP 4: POLAROID MEMORY -->
        <div id="step-4" class="step hidden-step absolute inset-0 flex flex-col items-center justify-center z-10">
            <div class="glass-card p-8 rounded-3xl max-w-lg w-full text-center flex flex-col items-center gap-6">
                <h2 class="font-serif text-3xl font-bold text-gradient">That One Time...</h2>
                
                <!-- Floating Polaroid -->
                <div class="polaroid-container w-64 h-auto cursor-pointer" id="polaroid-wrapper">
                    <div class="polaroid transform rotate-[-3deg]">
                        <!-- MAKE SURE srishti.jpg IS IN THE FOLDER -->
                        <img src="srishti.jpg" alt="MYYY BABYYY" class="w-full h-64 object-cover bg-gray-200 mb-3" onerror="this.src='https://placehold.co/400x500/pink/white?text=Add+Photo+srishti.jpg';">
                        <div class="font-serif text-gray-800 text-xl font-bold uppercase tracking-wide">MYYY BABYYY.</div>
                    </div>
                </div>

                <p class="font-sans text-gray-300 text-lg leading-relaxed mt-2">
                    Every moment with you feels like a scene from a movie I'd watch on repeat.
                </p>
                <button onclick="goToStep(5)" class="btn-modern px-8 py-3 rounded-full text-white font-bold tracking-wide mt-2">
                    One last thing...
                </button>
            </div>
        </div>

        <!-- STEP 5: FINALE -->
        <div id="step-5" class="step hidden-step absolute inset-0 flex flex-col items-center justify-center z-10">
            <div class="glass-card p-8 md:p-12 rounded-3xl max-w-lg w-full text-center flex flex-col items-center gap-5">
                <div class="text-6xl mb-1">🎂</div>
                <h2 class="font-serif text-3xl md:text-4xl font-bold text-gradient">My Wish For You</h2>
                
                <p class="font-sans text-gray-300 text-lg leading-relaxed">
                    May the next year bring you all the love, success, and pure happiness and hum milke somthing hilarious kreeee. You so rightfully deserve. May your dreams soar higher than ever.
                </p>

                <!-- Small Image Preview in Finale -->
                <div class="finale-image-container relative w-48 h-48 rounded-full overflow-hidden mt-2 mb-2">
                     <!-- MAKE SURE srishti.jpg IS IN THE FOLDER -->
                    <img src="srishti.jpg" alt="Srishti" class="w-full h-full object-cover" onerror="this.src='https://placehold.co/400x400/pink/white?text=Add+Photo';">
                </div>

                <!-- Hidden Final Message -->
                <div id="final-message" class="hidden opacity-0 translate-y-4 transition-all duration-1000">
                    <h1 class="font-serif text-4xl md:text-5xl font-bold text-pink-400 drop-shadow-md mt-4">
                        Happy Birthday,<br>my crush! ❤️
                    </h1>
                </div>

                <button id="celebrate-btn" onclick="celebrate()" class="btn-modern px-12 py-4 rounded-full text-white font-bold text-xl tracking-wide mt-4 shadow-[0_0_30px_rgba(236,72,153,0.5)]">
                    Celebrate!
                </button>
            </div>
        </div>

    </main>

    <!-- LOGIC SCRIPT -->
    <script>
        // --- 1. Navigation Logic ---
        let currentStep = 1;
        const totalSteps = 5;

        function goToStep(stepNumber) {
            // Update Progress Bar
            const progress = ((stepNumber - 1) / (totalSteps - 1)) * 100;
            document.getElementById('progress-bar').style.width = `${progress}%`;

            const currentEl = document.getElementById(`step-${currentStep}`);
            const nextEl = document.getElementById(`step-${stepNumber}`);

            // Animate OUT
            gsap.to(currentEl, {
                duration: 0.5,
                opacity: 0,
                scale: 0.9,
                y: -30,
                ease: "power2.in",
                onComplete: () => {
                    currentEl.classList.add('hidden-step');
                    currentEl.style.display = 'none'; 
                }
            });

            // Animate IN
            nextEl.style.display = 'flex';
            nextEl.classList.remove('hidden-step');
            
            gsap.fromTo(nextEl, {
                opacity: 0,
                scale: 0.9,
                y: 30
            }, {
                duration: 0.6,
                delay: 0.2,
                opacity: 1,
                scale: 1,
                y: 0,
                ease: "back.out(1.7)"
            });

            currentStep = stepNumber;
        }

        // --- 2. Polaroid Tilt Effect (Step 4) ---
        const polaroidWrapper = document.getElementById('polaroid-wrapper');
        const polaroidCard = polaroidWrapper.querySelector('.polaroid');

        polaroidWrapper.addEventListener('mousemove', (e) => {
            const rect = polaroidWrapper.getBoundingClientRect();
            const x = e.clientX - rect.left;
            const y = e.clientY - rect.top;
            
            // Calculate rotation
            const xRot = ((y - rect.height / 2) / rect.height) * -15; 
            const yRot = ((x - rect.width / 2) / rect.width) * 15;

            gsap.to(polaroidCard, {
                duration: 0.5,
                rotationX: xRot,
                rotationY: yRot,
                scale: 1.05,
                ease: "power2.out"
            });
        });

        polaroidWrapper.addEventListener('mouseleave', () => {
            gsap.to(polaroidCard, {
                duration: 0.5,
                rotationX: 0,
                rotationY: 0,
                rotate: -3, 
                scale: 1,
                ease: "power2.out"
            });
        });

        // --- 3. Grand Finale Logic ---
        let heartsFlying = false;

        function celebrate() {
            const btn = document.getElementById('celebrate-btn');
            const msg = document.getElementById('final-message');

            // 1. Fade out button
            gsap.to(btn, {
                duration: 0.5,
                opacity: 0,
                scale: 0.5,
                onComplete: () => btn.style.display = 'none'
            });

            // 2. Show Message
            msg.classList.remove('hidden');
            gsap.to(msg, {
                duration: 1,
                opacity: 1,
                y: 0,
                delay: 0.3,
                ease: "power3.out"
            });

            // 3. Trigger Background Hearts Fly Away
            heartsFlying = true;

            // 4. Confetti Explosion
            launchConfetti();
        }

        function launchConfetti() {
            // Big burst from bottom
            confetti({
                particleCount: 150,
                spread: 70,
                origin: { y: 0.8 },
                colors: ['#ec4899', '#ef4444', '#f472b6', '#ffffff']
            });

            // Continuous gentle rain
            const end = Date.now() + 5000;

            (function frame() {
                confetti({
                    particleCount: 5,
                    angle: 60,
                    spread: 55,
                    origin: { x: 0 },
                    colors: ['#ec4899', '#ef4444']
                });
                confetti({
                    particleCount: 5,
                    angle: 120,
                    spread: 55,
                    origin: { x: 1 },
                    colors: ['#ec4899', '#ef4444']
                });

                // Emoji Confetti
                if (Date.now() % 10 === 0) {
                     confetti({
                        particleCount: 2,
                        scalar: 2.5,
                        shapes: ['emoji'],
                        shapeOptions: {
                            emoji: { value: ['❤️', '💖', '✨', '🌸'] }
                        },
                        origin: { x: Math.random(), y: 0 }
                    });
                }

                if (Date.now() < end) {
                    requestAnimationFrame(frame);
                }
            }());
        }

        // --- 4. Three.js Background (Hearts) ---
        const initThree = () => {
            const container = document.getElementById('canvas-container');
            const scene = new THREE.Scene();
            
            const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
            camera.position.z = 30;

            const renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true });
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(window.devicePixelRatio);
            container.appendChild(renderer.domElement);

            // Light
            const ambientLight = new THREE.AmbientLight(0xffffff, 0.6);
            scene.add(ambientLight);
            const pointLight = new THREE.PointLight(0xffffff, 0.8);
            pointLight.position.set(10, 10, 10);
            scene.add(pointLight);

            // Heart Shape
            const x = 0, y = 0;
            const heartShape = new THREE.Shape();
            heartShape.moveTo( x + 5, y + 5 );
            heartShape.bezierCurveTo( x + 5, y + 5, x + 4, y, x, y );
            heartShape.bezierCurveTo( x - 6, y, x - 6, y + 7,x - 6, y + 7 );
            heartShape.bezierCurveTo( x - 6, y + 11, x - 3, y + 15.4, x + 5, y + 19 );
            heartShape.bezierCurveTo( x + 12, y + 15.4, x + 16, y + 11, x + 16, y + 7 );
            heartShape.bezierCurveTo( x + 16, y + 7, x + 16, y, x + 10, y );
            heartShape.bezierCurveTo( x + 7, y, x + 5, y + 5, x + 5, y + 5 );

            const geometry = new THREE.ShapeGeometry(heartShape);
            geometry.center();

            // Create hearts
            const hearts = [];
            const heartMaterial = new THREE.MeshPhongMaterial({ 
                color: 0xec4899, 
                shininess: 100, 
                opacity: 0.7, 
                transparent: true,
                side: THREE.DoubleSide
            });

            for(let i=0; i<25; i++) {
                const mesh = new THREE.Mesh(geometry, heartMaterial);
                
                // Randomize
                mesh.position.set(
                    (Math.random() - 0.5) * 60,
                    (Math.random() - 0.5) * 40,
                    (Math.random() - 0.5) * 20
                );
                
                const scale = Math.random() * 0.04 + 0.02;
                mesh.scale.set(scale, scale, scale);
                
                mesh.rotation.z = Math.random() * Math.PI;

                mesh.userData = {
                    speedY: Math.random() * 0.02 + 0.01,
                    wobbleSpeed: Math.random() * 0.02 + 0.01,
                    wobbleOffset: Math.random() * Math.PI * 2,
                    initialX: mesh.position.x
                };

                scene.add(mesh);
                hearts.push(mesh);
            }

            // Animation Loop
            function animate() {
                requestAnimationFrame(animate);

                hearts.forEach(heart => {
                    if(!heartsFlying) {
                        heart.position.y += heart.userData.speedY;
                        heart.position.x = heart.userData.initialX + Math.sin(Date.now() * 0.001 + heart.userData.wobbleOffset) * 2;
                        heart.rotation.y += 0.01;
                        if(heart.position.y > 25) heart.position.y = -25;
                    } else {
                        heart.position.y += 0.5;
                        heart.position.z += 0.2;
                        heart.material.opacity -= 0.01;
                    }
                });

                renderer.render(scene, camera);
            }
            animate();

            // Resize Handler
            window.addEventListener('resize', () => {
                camera.aspect = window.innerWidth / window.innerHeight;
                camera.updateProjectionMatrix();
                renderer.setSize(window.innerWidth, window.innerHeight);
            });
        }

        window.onload = initThree;
    </script>
</body>
</html>
