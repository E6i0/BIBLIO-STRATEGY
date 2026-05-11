<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BIBLIO STRATEGY | Egio Progress</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=JetBrains+Mono&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: #e5e5e5; }
        .serif { font-family: 'Playfair Display', serif; }
        .gold-text { color: #d4af37; }
        .gold-bg { background-color: #d4af37; }
        .border-gold { border-color: rgba(212, 175, 55, 0.2); }
        .terminal-bg { background-color: rgba(15, 15, 15, 0.95); }
    </style>
</head>
<body class="antialiased">

    <nav class="max-w-6xl mx-auto px-8 py-12 flex justify-between items-center border-b border-white/5">
        <div class="text-2xl font-bold tracking-tighter serif italic gold-text">Biblio Strategy</div>
        <div class="text-[9px] uppercase tracking-[0.5em] text-gray-600 font-bold">Protocolo v2.0</div>
    </nav>

    <main class="max-w-4xl mx-auto pt-16 px-8 pb-32">
        
        <section class="text-center mb-20">
            <h1 class="text-6xl serif font-light mb-6 uppercase tracking-tight">Sabiduría <br><span class="italic gold-text">Operativa</span></h1>
            <p class="text-gray-500 max-w-lg mx-auto text-sm leading-relaxed italic">
                "No es religión, es tecnología espiritual para el dominio del caos diario."
            </p>
        </section>

        <section id="display-area" class="mb-16 hidden">
            <div class="terminal-bg border border-gold p-10 rounded-3xl shadow-[0_0_50px_rgba(212,175,55,0.05)]">
                <h3 id="res-fase" class="text-[10px] uppercase tracking-[0.4em] gold-text font-bold mb-6">Procesando...</h3>
                <div id="res-texto" class="serif text-3xl italic text-white mb-8 leading-snug"></div>
                <div id="res-analisis" class="text-sm text-gray-400 leading-relaxed border-t border-white/5 pt-8 font-light"></div>
                <button onclick="cerrarDisplay()" class="mt-8 text-[9px] uppercase tracking-widest text-gray-600 hover:text-white transition-colors underline">Limpiar Terminal</button>
            </div>
        </section>

        <div class="grid md:grid-cols-3 gap-6">
            <button onclick="procesar('manana')" class="group p-10 terminal-bg border border-white/5 rounded-3xl hover:border-gold transition-all text-left">
                <span class="gold-text text-[9px] font-bold tracking-[0.3em] uppercase">01. Enfoque</span>
                <h4 class="text-xl serif mt-2">Mañana</h4>
            </button>

            <button onclick="procesar('tarde')" class="group p-10 terminal-bg border border-white/5 rounded-3xl hover:border-gold transition-all text-left">
                <span class="gold-text text-[9px] font-bold tracking-[0.3em] uppercase">02. Ajuste</span>
                <h4 class="text-xl serif mt-2">Mediodía</h4>
            </button>

            <button onclick="procesar('noche')" class="group p-10 terminal-bg border border-white/5 rounded-3xl hover:border-gold transition-all text-left">
                <span class="gold-text text-[9px] font-bold tracking-[0.3em] uppercase">03. Cierre</span>
                <h4 class="text-xl serif mt-2">Cosecha</h4>
            </button>
        </div>
    </main>

    <script>
        const database = {
            manana: {
                fase: "Protocolo de Apertura",
                texto: '"En la quietud y en la confianza estará vuestra fortaleza."',
                analisis: "ANÁLISIS: La fuerza no nace de la velocidad, sino de la estabilidad interna. Si tu clima es 'caliente', usa este principio como refrigerante para tomar decisiones técnicas, no emocionales."
            },
            tarde: {
                fase: "Termómetro de Intención",
                texto: '"No nos cansemos, pues, de hacer bien; porque a su tiempo segaremos."',
                analisis: "ANÁLISIS: La fatiga del mediodía es el filtro que separa al profesional del aficionado. La constancia en BAMX hoy es la semilla de tu independencia mañana."
            },
            noche: {
                fase: "Auditoría de Cierre",
                texto: '"En paz me acostaré, y asimismo dormiré."',
                analisis: "ANÁLISIS: El ciclo ha terminado. Si lograste tus metas, el descanso es tu derecho legal. Suelta el ruido de lo pendiente; mañana el sistema se reinicia."
            }
        };

        function procesar(momento) {
            const area = document.getElementById('display-area');
            document.getElementById('res-fase').innerText = database[momento].fase;
            document.getElementById('res-texto').innerText = database[momento].texto;
            document.getElementById('res-analisis').innerText = database[momento].analisis;
            area.classList.remove('hidden');
            window.scrollTo({ top: area.offsetTop - 50, behavior: 'smooth' });
        }

        function cerrarDisplay() {
            document.getElementById('display-area').classList.add('hidden');
        }
    </script>
</body>
</html>
