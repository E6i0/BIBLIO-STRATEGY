<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BIBLIO STRATEGY | Consola de Sabiduría</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Playfair+Display:ital,wght@0,400;1,400&family=JetBrains+Mono&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: #e5e5e5; }
        .serif { font-family: 'Playfair Display', serif; }
        .gold-text { color: #d4af37; }
        .terminal-input { background: #111; border: 1px solid rgba(212, 175, 55, 0.2); transition: all 0.3s; }
        .terminal-input:focus { border-color: #d4af37; outline: none; box-shadow: 0 0 15px rgba(212, 175, 55, 0.1); }
        .fade-in { animation: fadeIn 0.8s ease-in; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body class="antialiased min-h-screen flex flex-col">

    <main class="max-w-2xl mx-auto px-6 py-20 flex-grow w-full">
        
        <header class="text-center mb-16">
            <h1 class="text-4xl serif italic gold-text mb-2">Biblio Strategy</h1>
            <p class="text-[9px] uppercase tracking-[0.4em] text-gray-600 font-bold">Diagnóstico Operativo de Lunes</p>
        </header>

        <section class="mb-12">
            <label class="block text-[10px] uppercase tracking-widest text-gray-500 mb-4 font-bold text-center italic">
                ¿Cómo está tu clima interno hoy? (Ej: "calma", "caliente", "cansado")
            </label>
            <div class="flex gap-2">
                <input type="text" id="userInput" placeholder="Escribe tu situación aquí..." 
                       class="w-full p-4 rounded-xl terminal-input text-sm font-light italic">
                <button onclick="consultar()" class="bg-[#d4af37] text-black px-6 rounded-xl font-bold text-xs uppercase tracking-tighter hover:bg-[#f4d03f] transition-all">
                    Analizar
                </button>
            </div>
        </section>

        <div id="resultado" class="hidden fade-in space-y-8 bg-[#0a0a0a] p-8 rounded-3xl border border-white/5 shadow-2xl">
            <div class="h-px w-full bg-gradient-to-r from-transparent via-[#d4af37] to-transparent mb-8 opacity-30"></div>
            
            <h3 id="res-fase" class="text-[9px] uppercase tracking-[0.5em] gold-text font-black"></h3>
            
            <p id="res-versiculo" class="serif text-3xl italic text-white leading-snug"></p>
            
            <div class="space-y-4 border-t border-white/5 pt-6">
                <span class="text-[9px] font-mono text-gray-600 uppercase tracking-widest">[ Análisis Epistemológico ]</span>
                <p id="res-analisis" class="text-sm text-gray-400 leading-relaxed font-light"></p>
            </div>
        </div>

    </main>

    <footer class="py-10 text-center opacity-20 text-[8px] uppercase tracking-[1em]">
        Egio Progress • 2026
    </footer>

    <script>
        const motor = [
            {
                keywords: ["calma", "soltar", "fluir", "paz"],
                fase: "Protocolo: Relevo de Carga",
                texto: '"Encomienda tu camino, confía y él hará."',
                analisis: "ANÁLISIS: Hoy la estrategia no es empujar, es permitir el flujo. Rodar la carga fuera de tu sistema para que las variables externas se acomoden solas."
            },
            {
                keywords: ["caliente", "enojo", "prisa", "presión"],
                fase: "Protocolo: Dominio de Caldera",
                texto: '"Mejor es el que se enseñorea de su espíritu que el que toma una ciudad."',
                analisis: "ANÁLISIS: Tienes combustible de sobra. El reto es la ingeniería: no permitas que el calor se vuelva explosión; canalízalo en una sola tarea técnica."
            },
            {
                keywords: ["cansado", "fatiga", "pesado", "lunes"],
                fase: "Protocolo: Resistencia de Materiales",
                texto: '"No nos cansemos de hacer el bien, porque a su tiempo segaremos."',
                analisis: "ANÁLISIS: La fatiga es un indicador de esfuerzo, no de fracaso. Mantén la estructura mínima viable. La cosecha está programada, no la canceles hoy."
            }
        ];

        function consultar() {
            const input = document.getElementById('userInput').value.toLowerCase();
            const resArea = document.getElementById('resultado');
            
            // Buscar coincidencia
            const match = motor.find(m => m.keywords.some(k => input.includes(k)));

            if (match) {
                resArea.classList.remove('hidden');
                document.getElementById('res-fase').innerText = match.fase;
                document.getElementById('res-versiculo').innerText = match.texto;
                document.getElementById('res-analisis').innerText = match.analisis;
            } else {
                alert("Describe tu estado con palabras como: calma, caliente o cansado para procesar.");
            }
        }
    </script>
</body>
</html>
