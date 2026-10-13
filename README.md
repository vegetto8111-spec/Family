<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reunión Día de Disfraces - Cinemática de Terror</title>
    <style>
        :root {
            --orange: #ff5500;
            --orange-glow: rgba(255, 85, 0, 0.8);
            --purple: #8b00ff;
            --card-bg: rgba(10, 5, 20, 0.35); 
            --yellow: #ffcc00;
            --text-light: #ffffff;
            --text-muted: #e0e0e0;
        }

        * {
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: var(--text-light);
            margin: 0;
            padding: 0;
            background: #cb2a2a url('Gemini_Generated_Image_dcvyfodcvyfodcvy.jfif') no-repeat center center fixed;
            background-size: cover;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .overlay-bg {
            min-height: 100vh;
            background: rgba(0, 0, 0, 0.4); 
            padding: 20px 15px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .main-wrapper {
            max-width: 800px;
            width: 100%;
            margin: 0 auto;
        }

        /* HUD NAV */
        .hud-nav {
            display: flex;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
            margin-bottom: 25px;
            background: rgba(0, 0, 0, 0.6);
            padding: 12px;
            border-radius: 30px;
            border: 1px solid var(--orange);
            box-shadow: 0 0 15px var(--orange-glow);
            backdrop-filter: blur(5px);
        }

        .hud-btn {
            background: rgba(139, 0, 255, 0.3);
            border: 1px solid var(--orange);
            color: var(--text-light);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .hud-btn:hover {
            background: var(--orange);
            color: #000;
            transform: scale(1.05);
            box-shadow: 0 0 10px var(--orange);
        }

        /* HERO HEADER */
        .hero-section {
            text-align: center;
            padding: 25px 15px;
            background: var(--card-bg);
            border: 1px solid var(--orange);
            border-radius: 20px;
            box-shadow: 0 0 25px var(--orange-glow);
            backdrop-filter: blur(4px);
            margin-bottom: 25px;
        }

        .badge-event {
            display: inline-block;
            background: rgba(0, 0, 0, 0.6);
            border: 1px solid var(--yellow);
            color: var(--yellow);
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: bold;
            letter-spacing: 1.5px;
            margin-bottom: 10px;
        }

        h1 {
            font-size: 2.3rem;
            color: var(--orange);
            margin: 5px 0;
            text-shadow: 0 0 15px #000, 0 0 10px var(--orange);
            font-weight: 900;
        }

        .slogan {
            font-size: 1rem;
            color: var(--yellow);
            font-style: italic;
            text-shadow: 1px 1px 3px #000;
            margin-bottom: 15px;
        }

        .spec-grid-hero {
            display: flex;
            justify-content: center;
            gap: 10px;
            flex-wrap: wrap;
        }

        .spec-field {
            background: rgba(0, 0, 0, 0.6);
            border: 1px solid var(--purple);
            padding: 6px 14px;
            border-radius: 8px;
            font-size: 0.85rem;
        }

        /* PANELES */
        .tech-section {
            background: var(--card-bg);
            border: 1px solid rgba(255, 85, 0, 0.5);
            border-radius: 14px;
            padding: 20px;
            margin-bottom: 20px;
            backdrop-filter: blur(3px);
            box-shadow: 0 4px 15px rgba(0,0,0,0.6);
            display: none;
        }

        .tech-section.active-panel {
            display: block;
            animation: fadeIn 0.4s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section-title {
            font-size: 1.3rem;
            color: var(--orange);
            font-weight: bold;
            margin-bottom: 15px;
            text-shadow: 1px 1px 3px #000;
            border-left: 4px solid var(--orange);
            padding-left: 10px;
        }

        .instructions-box {
            color: var(--text-light);
            font-size: 0.95rem;
            line-height: 1.5;
            background: rgba(0,0,0,0.6);
            padding: 15px;
            border-radius: 8px;
            border-left: 4px solid var(--purple);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 10px;
        }

        .feature-card {
            background: rgba(0, 0, 0, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.2);
            padding: 10px 14px;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
        }

        .feature-card:hover {
            border-color: var(--orange);
            background: rgba(255, 85, 0, 0.3);
        }

        .feature-tag {
            font-size: 0.75rem;
            padding: 3px 8px;
            border-radius: 4px;
            font-weight: bold;
        }

        .tag-available {
            background: rgba(139, 0, 255, 0.5);
            color: var(--yellow);
            border: 1px dashed var(--orange);
        }

        .tag-assigned {
            background: var(--orange);
            color: #000;
        }

        .families-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 8px;
        }

        .family-pill {
            background: rgba(0, 0, 0, 0.65);
            border: 1px solid var(--purple);
            padding: 10px 12px;
            border-radius: 6px;
            font-size: 0.9rem;
        }

        /* MODAL DE FAMILIAS */
        #family-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0, 0, 0, 0.85);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease;
        }

        #family-modal.show {
            opacity: 1;
            pointer-events: auto;
        }

        .modal-box {
            background: #110303;
            border: 2px solid var(--orange);
            padding: 25px;
            border-radius: 14px;
            width: 90%;
            max-width: 400px;
            text-align: center;
            box-shadow: 0 0 25px var(--orange-glow);
        }

        .modal-title {
            color: var(--orange);
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .modal-family-btn {
            background: rgba(139, 0, 255, 0.4);
            border: 1px solid var(--orange);
            color: white;
            padding: 10px;
            margin: 6px 0;
            width: 100%;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.2s;
        }

        .modal-family-btn:hover {
            background: var(--orange);
            color: black;
        }

        .modal-cancel-btn {
            margin-top: 15px;
            background: #333;
            color: #aaa;
            border: none;
            padding: 8px 15px;
            border-radius: 6px;
            cursor: pointer;
        }

        /* CINEMÁTICA DEL ATAÚD */
        #coffin-cinematic {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: #000;
            z-index: 99999;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.8s ease;
        }

        #coffin-cinematic.active {
            opacity: 1;
            pointer-events: auto;
        }

        .coffin-container {
            position: relative;
            width: 320px;
            height: 520px;
            display: flex;
            justify-content: center;
            align-items: center;
            perspective: 1000px;
        }

        .coffin-lid {
            position: absolute;
            width: 100%;
            height: 100%;
            background: #3b2219;
            border: 4px solid #1a0e0a;
            border-radius: 120px 120px 20px 20px;
            box-shadow: inset 0 0 30px #000;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            transform-origin: left center;
            transition: transform 2s cubic-bezier(0.77, 0, 0.175, 1);
            z-index: 3;
        }

        #coffin-cinematic.open-lid .coffin-lid {
            transform: rotateY(-110deg);
        }

        .coffin-cross { font-size: 4rem; color: #734d26; text-shadow: 2px 2px 5px #000; }

        .coffin-inside {
            position: absolute;
            width: 100%;
            height: 100%;
            background: #0a0101;
            border: 4px solid #551a1a;
            border-radius: 120px 120px 20px 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            padding: 25px 15px;
            text-align: center;
            z-index: 1;
            box-shadow: inset 0 0 50px #ff0000;
        }

        .coffin-text { color: #ff3300; font-size: 1rem; font-weight: bold; text-shadow: 0 0 10px #ff0000; }
        .btn-close-coffin { background: var(--orange); color: #000; border: none; padding: 8px 16px; font-weight: bold; border-radius: 6px; cursor: pointer; z-index: 1000000; }

        /* SCREAMER OVERLAY (PANTALLA COMPLETA PERFECTA) */
        .screamer-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(180, 0, 0, 0.85);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 999999;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.05s ease-in;
            overflow: hidden;
        }

        .screamer-overlay.trigger {
            opacity: 1;
            animation: shakeScreamer 0.1s infinite;
        }

        .screamer-monster {
            width: 100vw !important;
            height: 100vh !important;
            max-width: none !important;
            max-height: none !important;
            object-fit: cover !important; /* Llena toda la pantalla manteniendo proporción sin espacios */
            transform: scale(0.9);
            transition: transform 0.1s cubic-bezier(0, 1.3, 0.5, 1.6);
        }

        .screamer-overlay.trigger .screamer-monster {
            transform: scale(1.05); /* Efecto de salto hacia la pantalla */
        }

        @keyframes shakeScreamer {
            0% { transform: translate(4px, 4px) rotate(0deg); }
            20% { transform: translate(-4px, -3px) rotate(-2deg); }
            40% { transform: translate(-3px, 4px) rotate(2deg); }
            60% { transform: translate(4px, 2px) rotate(0deg); }
            80% { transform: translate(-2px, -4px) rotate(1deg); }
            100% { transform: translate(3px, 3px) rotate(-1deg); }
        }

        footer {
            text-align: center;
            margin-top: 30px;
            color: var(--text-muted);
            font-size: 0.8rem;
            text-shadow: 1px 1px 2px #000;
        }
    </style>
</head>
<body>

<!-- ARCHIVO DE AUDIO LOCAL PARA EL GRITO -->
<audio id="screamer-audio" src="grito.mp3" preload="auto"></audio>

<div class="overlay-bg">
    <div class="main-wrapper">

        <!-- MENÚ DE BOTONES INTERACTIVOS (HUD) -->
        <nav class="hud-nav">
            <button class="hud-btn" onclick="showPanel('panel-home')">🏠 Inicio</button>
            <button class="hud-btn" onclick="showPanel('panel-menu')">📋 Menú</button>
            <button class="hud-btn" onclick="showPanel('panel-familias')">🦇 Familias</button>
            <button class="hud-btn" onclick="iniciarCinematicaAtaud()">⚰️ Visitar Ataúd</button>
        </nav>

        <!-- PANEL 1: INICIO -->
        <div id="panel-home" class="tech-section active-panel">
            <header class="hero-section" style="margin-bottom:0;">
                <div class="badge-event">🎃 Compensar • Evento Especial 🎃</div>
                <h1>Reunión Día de Disfraces</h1>
                <div class="slogan">"Un compartir familiar - Como la perinola: todos ponen"</div>
                
                <div class="spec-grid-hero">
                    <div class="spec-field">📅 <strong>Día:</strong> 24</div>
                    <div class="spec-field">🌙 <strong>Mes:</strong> 10</div>
                    <div class="spec-field">⚡ <strong>Año:</strong> 2026</div>
                </div>
            </header>
            <div style="margin-top: 20px;" class="instructions-box">
                Cada familia escoge una opción del menú para compartir seleccionando directamente de la lista de familias convocadas 👻.
            </div>
        </div>

        <!-- PANEL 2: MENÚ PARA APARTAR -->
        <div id="panel-menu" class="tech-section">
            <div class="section-title">📋 Menú de la Velada (Toca para apartar tu familia)</div>
            <div class="features-grid">
                <div class="feature-card" onclick="abrirSelectorFamilia(0)"><span class="feature-name">Papa chorreada 🧠</span><span id="tag-0" class="feature-tag tag-available">Disponible</span></div>
                <div class="feature-card" onclick="abrirSelectorFamilia(1)"><span class="feature-name">Gelatina c/ crema y wafer ☠️</span><span id="tag-1" class="feature-tag tag-available">Disponible</span></div>
                <div class="feature-card" onclick="abrirSelectorFamilia(2)"><span class="feature-name">Chorizo coctelero 🧪</span><span id="tag-2" class="feature-tag tag-available">Disponible</span></div>
                <div class="feature-card" onclick="abrirSelectorFamilia(3)"><span class="feature-name">Galletas 👻</span><span id="tag-3" class="feature-tag tag-assigned">Alejo & Juan</span></div>
                <div class="feature-card" onclick="abrirSelectorFamilia(4)"><span class="feature-name">Conos de helado 🩸</span><span id="tag-4" class="feature-tag tag-available">Disponible</span></div>
                <div class="feature-card" onclick="abrirSelectorFamilia(5)"><span class="feature-name">Empanaditas 🦇</span><span id="tag-5" class="feature-tag tag-available">Disponible</span></div>
                <div class="feature-card" onclick="abrirSelectorFamilia(6)"><span class="feature-name">Fruta picada 👁️</span><span id="tag-6" class="feature-tag tag-available">Disponible</span></div>
                <div class="feature-card" onclick="abrirSelectorFamilia(7)"><span class="feature-name">Toppings🧛‍♂️</span><span id="tag-7" class="feature-tag tag-available">Disponible</span></div>
            </div>
        </div>

        <!-- PANEL 3: FAMILIAS -->
        <div id="panel-familias" class="tech-section">
            <div class="section-title">🦇 Familias Convocadas</div>
            <div class="families-container">
                <div class="family-pill">👹 Freddy y Leidy</div>
                <div class="family-pill">🕷️ Giovanny y Yolima</div>
                <div class="family-pill">💀 Nelson y Elizabeth</div>
                <div class="family-pill">🧙‍♂️ Wilinton y Marlene</div>
                <div class="family-pill">🧟‍♂️ David y Julieth</div>
                <div class="family-pill">🎃 Alejandro - Santi - Juan</div>
            </div>
        </div>

        <footer>
            ¡Prepárate con tu mejor disfraz! 🎃🦇
        </footer>

    </div>
</div>

<!-- VENTANA EMERGENTE DE FAMILIAS -->
<div id="family-modal">
    <div class="modal-box">
        <div class="modal-title">🦇 Selecciona tu Familia</div>
        <div id="modal-families-list"></div>
        <button class="modal-cancel-btn" onclick="cerrarSelectorFamilia()">Cancelar</button>
    </div>
</div>

<!-- CINEMÁTICA DEL ATAÚD -->
<div id="coffin-cinematic">
    <div class="coffin-container">
        <div class="coffin-inside">
            <div class="coffin-text">¡SISTEMA INFECTADO!</div>
            <div class="coffin-text" style="font-size: 0.85rem; color:#fff;">¡Nos vemos el 24 de Octubre!</div>
            <button class="btn-close-coffin" onclick="cerrarCinematicaAtaud()">Cerrar Ataúd y Huir</button>
        </div>
        <div class="coffin-lid">
            <div class="coffin-cross">✝️</div>
            <div style="color: #734d26; font-size: 0.8rem; margin-top:20px; font-weight:bold;">RIP</div>
        </div>
    </div>
</div>

<!-- PANTALLA DEL SCREAMER A PANTALLA COMPLETA -->
<div id="screamer-screen" class="screamer-overlay">
    <img src="monstruo.jfif" alt="Screamer Monster" class="screamer-monster" onerror="this.src='monstruo.png';">
</div>

<script>
    const familiasConvocadas = [
        "Freddy y Leidy",
        "Giovanny y Yolima",
        "Nelson y Elizabeth",
        "Wilinton y Marlene",
        "David y Julieth",
        "Alejandro - Santi - Juan",
        "Alejo & Juan"
    ];

    let indicePlatoActual = null;
    let contadorScreamer = 0;      
    const limiteScreamer = 1;      

    // CARGAR ESTADOS GUARDADOS EN LOCALSTORAGE AL ABRIR LA PÁGINA
    window.onload = function() {
        for (let i = 0; i < 8; i++) {
            let guardado = localStorage.getItem('plato_index_' + i);
            if (guardado) {
                let tag = document.getElementById('tag-' + i);
                if (tag) {
                    tag.className = "feature-tag tag-assigned";
                    tag.innerText = guardado;
                }
            }
        }
    };

    function showPanel(panelId) {
        let panels = document.querySelectorAll('.tech-section');
        panels.forEach(p => p.classList.remove('active-panel'));
        document.getElementById(panelId).classList.add('active-panel');
        reproducirSonidoClick();
    }

    function abrirSelectorFamilia(index) {
        indicePlatoActual = index;
        let listaContainer = document.getElementById('modal-families-list');
        listaContainer.innerHTML = "";

        familiasConvocadas.forEach(fam => {
            let btn = document.createElement('button');
            btn.className = "modal-family-btn";
            btn.innerText = fam;
            btn.onclick = function() {
                let tag = document.getElementById('tag-' + index);
                tag.className = "feature-tag tag-assigned";
                tag.innerText = fam;

                // GUARDAR EN LA MEMORIA DEL NAVEGADOR (LOCALSTORAGE)
                localStorage.setItem('plato_index_' + index, fam);

                cerrarSelectorFamilia();
            };
            listaContainer.appendChild(btn);
        });

        document.getElementById('family-modal').classList.add('show');
        reproducirSonidoClick();
    }

    function cerrarSelectorFamilia() {
        document.getElementById('family-modal').classList.remove('show');
    }

    // Cinemática del ataúd con screamer por 4 segundos
    function iniciarCinematicaAtaud() {
        let cin = document.getElementById('coffin-cinematic');
        let screamer = document.getElementById('screamer-screen');
        let audioGrito = document.getElementById('screamer-audio');
        
        cin.classList.add('active');
        reproducirSonidoTerror();
        
        setTimeout(() => {
            cin.classList.add('open-lid');
        }, 800);

        if (contadorScreamer < limiteScreamer) {
            setTimeout(() => {
                screamer.classList.add('trigger');
                
                if (audioGrito) {
                    audioGrito.currentTime = 0;
                    audioGrito.play().catch(e => reproducirSonidoScreamer());
                } else {
                    reproducirSonidoScreamer();
                }

                // Ocultar el screamer exactamente a los 4 segundos
                setTimeout(() => {
                    screamer.classList.remove('trigger');
                    if (audioGrito) {
                        audioGrito.pause();
                    }
                }, 4000);

                contadorScreamer++;
            }, 1800);
        }
    }

    function cerrarCinematicaAtaud() {
        let cin = document.getElementById('coffin-cinematic');
        let screamer = document.getElementById('screamer-screen');
        let audioGrito = document.getElementById('screamer-audio');

        if (audioGrito) {
            audioGrito.pause();
        }
        screamer.classList.remove('trigger');
        cin.classList.remove('open-lid');
        setTimeout(() => {
            cin.classList.remove('active');
        }, 500);
    }

    function reproducirSonidoClick() {
        try {
            const ctx = new (window.AudioContext || window.webkitAudioContext)();
            const osc = ctx.createOscillator();
            const gain = ctx.createGain();
            osc.frequency.setValueAtTime(300, ctx.currentTime);
            osc.exponentialRampToValueAtTime(100, ctx.currentTime + 0.1);
            gain.gain.setValueAtTime(0.1, ctx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.1);
            osc.connect(gain);
            gain.connect(ctx.destination);
            osc.start();
            osc.stop(ctx.currentTime + 0.1);
        } catch(e) {}
    }

    function reproducirSonidoTerror() {
        try {
            const ctx = new (window.AudioContext || window.webkitAudioContext)();
            const osc = ctx.createOscillator();
            const gain = ctx.createGain();
            osc.type = 'sawtooth';
            osc.frequency.setValueAtTime(80, ctx.currentTime);
            osc.frequency.linearRampToValueAtTime(40, ctx.currentTime + 1.5);
            gain.gain.setValueAtTime(0.2, ctx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 1.5);
            osc.connect(gain);
            gain.connect(ctx.destination);
            osc.start();
            osc.stop(ctx.currentTime + 1.5);
        } catch(e) {}
    }

    function reproducirSonidoScreamer() {
        try {
            const ctx = new (window.AudioContext || window.webkitAudioContext)();
            const osc = ctx.createOscillator();
            const gain = ctx.createGain();
            osc.type = 'square';
            osc.frequency.setValueAtTime(950, ctx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(150, ctx.currentTime + 0.7);
            gain.gain.setValueAtTime(0.5, ctx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.7);
            osc.connect(gain);
            gain.connect(ctx.destination);
            osc.start();
            osc.stop(ctx.currentTime + 0.7);
        } catch(e) {}
    }
</script>

</body>
</html>
