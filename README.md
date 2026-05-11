<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EGIO PROGRESS | Biblio Strategy</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=JetBrains+Mono&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #0a0a0a; color: #e5e5e5; }
        .serif { font-family: 'Playfair Display', serif; }
        .mono { font-family: 'JetBrains Mono', monospace; }
        .gold-gradient { background: linear-gradient(135deg, #d4af37 0%, #f4d03f 100%); }
        .gold-text { color: #d4af37; }
        .border-gold { border-color: rgba(212, 175, 55, 0.3); }
    </style>
</head>
<body class="antialiased">

    <nav class="max-w-6xl mx-auto px-8 py-10 flex justify-between items-center border-b border-white/5">
        <div class="text-2xl font-bold tracking-tighter serif">EGIO <span class="gold-text italic underline">PROGRESS</span></div>
        <div class="hidden md:flex space-x-10 text-[10px] uppercase tracking-[0.4em] text-gray-500 font-bold">
            <a href="#" class="hover:text-white transition-all">Mente</a>
            <a href="#" class="hover:text-white transition-all">Cuerpo</a>
            <a href="#" class="hover:text-white transition-all">Alma</a>
        </div>
    </nav>

    <main class="max-w-4xl mx-auto pt-20 pb-12 px-8">
        
        <div class="text-center mb-24">
            <h2 class="text-[10px] uppercase tracking-[0.5em] gold-text mb-4 font-bold opacity-80">Epistemología Aplicada</h2>
            <h1 class="text-5xl md:text-7xl font-light serif leading-tight mb-8">BIBLIO <br> <span class="italic">STRATEGY</span></h1>
            <div class="h-px w-24 bg-gradient-to-r from-transparent via-[#d4af37] to-transparent mx-auto"></div>
        </div>

        <section class="bg-[#111] rounded-3xl p-10 md:p-16 border border-white/5 shadow-2xl relative overflow-hidden">
            <div class="absolute top-0 right-0 w-64 h-64 bg-[#d4af37] opacity-[0.03] blur-[100px] rounded-full"></div>
            
            <div class="grid md:grid-cols-2 gap-16 mb-20 relative">
                <div>
                    <p class="serif italic text-2xl text-gray-300 leading-relaxed mb-8">
                        "La esencia no es la religión, es la verdad operativa que calma y enfoca el espíritu."
                    </p>
                    <p class="text-sm text-gray-500 leading-relaxed font-light">
                        Este protocolo utiliza el análisis de textos antiguos para decodificar palabras que necesitas leer según tu estado emocional actual. 
                    </p>
                </div>
                <div class="bg-black/40 rounded-2xl p-8 border border-gold">
                    <code class="text-[11px] mono text-amber-200/70">
                        <span class="text-gray-600">// Procesando estado emocional...</span><br>
                        IF (clima_interno == "Caliente") {<br>
                        &nbsp;&nbsp;return "Dominio Propio";<br>
                        } ELSE {<br>
                        &nbsp;&nbsp;return "Serenidad Operativa";<br>
                        }
                    </code>
                </div>
            </div>

            <div class="grid md:grid-cols-3 gap-6">
                <button onclick="faseManana()" class="group text-left p-8 bg-white/5 border border-white/5 rounded-2xl hover:border-[#d4af37]/50 transition-all">
                    <span class="text-[9px] uppercase tracking-widest gold-text font-black">01. Inicio</span>
                    <h4 class="text-xl serif mt-2 mb-4">Mañana</h4>
                    <p class="text-[10px] text-gray-500 italic mb-6">¿Cuál es el matiz de tu energía hoy?</p>
                    <div class="text-[9px] font-bold gold-text uppercase tracking-widest group-hover:underline">Consultar →</div>
                </button>

                <button onclick="faseTarde()" class="group text-left p-8 bg-white/5 border border-white/5 rounded-2xl hover:border-[#d4af37]/50 transition-all">
                    <span class="text-[9px] uppercase tracking-widest gold-text font-black">02. Refuerzo</span>
                    <h4 class="text-xl serif mt-2 mb-4">Tarde</h4>
                    <p class="text-[10px] text-gray-500 italic mb-6">¿Qué domina tus horas ahora?</p>
                    <div class="text-[9px] font-bold gold-text uppercase tracking-widest group-hover:underline">Seguimiento →</div>
                </button>

                <button onclick="faseNoche()" class="group text-left p-8 bg-white/5 border border-white/5 rounded-2xl hover:border-[#d4af37]/50 transition-all">
                    <span class="text-[9px] uppercase tracking-widest gold-text font-black">03. Cosecha</span>
                    <h4 class="text-xl serif mt-2 mb-4">Noche</h4>
                    <p class="text-[10px] text-gray-500 italic mb-6">¿Qué pesa más en tu balance?</p>
                    <div class="text-[9px] font-bold gold-text uppercase tracking-widest group-hover:underline">Cerrar día →</div>
                </button>
            </div>
        </section>
    </main>

    <footer class="py-20 text-center opacity-30">
        <p class="text-[9px] uppercase tracking-[1em] font-bold">Hecho para el Bien • 2026</p>
    </footer>

    <script>
        function faseManana() {
            let r = prompt("¿Cuál es el matiz principal de tu energía hoy? ¿Impulso de ejecución o incertidumbre?");
            if(r) alert("Entendido. Ahora dime esto en nuestro chat para darte tu versículo de enfoque.");
        }
        function faseTarde() {
            let r = prompt("¿Qué ha dominado tus primeras horas: el progreso o las distracciones ajenas?");
            if(r) alert("Recalibrando... Comparte esto en el chat para tu refuerzo de mediodía.");
        }
        function faseNoche() {
            let r = prompt("Al hacer balance hoy, ¿qué pesa más: la satisfacción o el ruido por lo pendiente?");
            if(r) alert("Es momento de soltar. Copia tu respuesta en el chat para tu reflexión final.");
        }
    </script>

</body>
</html>
