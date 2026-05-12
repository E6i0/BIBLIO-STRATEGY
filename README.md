<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BIBLIO STRATEGY | Consola v3.0</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Playfair+Display:ital,wght@0,400;1,400&family=JetBrains+Mono&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: #e5e5e5; }
        .serif { font-family: 'Playfair Display', serif; }
        .gold-text { color: #d4af37; }
        .terminal-input { background: #111; border: 1px solid rgba(212, 175, 55, 0.1); transition: all 0.3s; }
        .terminal-input:focus { border-color: #d4af37; outline: none; box-shadow: 0 0 20px rgba(212, 175, 55, 0.05); }
        .fade-in { animation: fadeIn 0.6s ease-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body class="antialiased min-h-screen flex flex-col">

    <main class="max-w-2xl mx-auto px-6 py-16 flex-grow w-full">
        
        <header class="text-center mb-12">
            <h1 class="text-4xl serif italic gold-text mb-2">Biblio Strategy</h1>
            <p class="text-[9px] uppercase tracking-[0.4em] text-gray-600 font-bold">Motor de Sabiduría Evolutiva</p>
        </header>

        <section class="mb-10">
            <div class="relative">
                <input type="text" id="userInput" placeholder="Describe tu estado (ej. estrés, duda, ambición, calma...)" 
                       class="w-full p-5 pr-16 rounded-2xl terminal-input text-sm font-light italic">
                <button onclick="consultar()" class="absolute right-2 top-2 bottom-2 bg-[#d4af37] text-black px-4 rounded-xl font-bold text-[10px] uppercase hover:bg-[#f4d03f] transition-all">
                    Analizar
                </button>
            </div>
        </section>

        <div id="resultado" class="hidden fade-in space-y-8 bg-[#0a0a0a] p-10 rounded-[2.5rem] border border-white/5 shadow-2xl relative overflow-hidden">
            <div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-transparent via-[#d4af37] to-transparent opacity-20"></div>
            
            <div>
                <h3 id="res-fase" class="text-[9px] uppercase tracking-[0.5em] gold-text font-black mb-6"></h3>
                <p id="res-versiculo" class="serif text-3xl italic text-white leading-tight mb-8"></p>
            </div>
            
            <div class="space-y-4 border-t border-white/10 pt-8">
                <span class="text-[9px] font-mono text-gray-600 uppercase tracking-widest block mb-2">[ Diagnóstico Estratégico ]</span>
                <p id="res-analisis" class="text-sm text-gray-400 leading-relaxed font-light italic"></p>
            </div>
        </div>
    </main>

    <script>
        const biblioteca = [
            {
                tags: ["soltar", "calma", "fluir", "paz", "control"],
                fase: "Protocolo: Desapego Operativo",
                versiculo: '"Encomienda tu camino, confía y él hará."',
                analisis: "La microgestión es el enemigo de la paz. Suelta las variables que no controlas para que el sistema respire."
            },
            {
                tags: ["caliente", "ira", "enojo", "molesto", "pelea"],
                fase: "Protocolo: Control de Incendio",
                versiculo: '"La blanda respuesta quita la ira; mas la palabra áspera hace subir el furor."',
                analisis: "En negociaciones o conflictos, el silencio es tu armadura. No desperdicies combustible en discusiones estériles."
            },
            {
                tags: ["cansado", "agobiado", "fatiga", "pesado", "rendirse"],
                fase: "Protocolo: Renovación de Células",
                versiculo: '"Él da esfuerzo al cansado, y multiplica las fuerzas al que no tiene ningunas."',
                analisis: "El cansancio es físico, la fatiga es mental. Hoy no necesitas velocidad, necesitas consistencia de fondo."
            },
            {
                tags: ["duda", "miedo", "incertidumbre", "futuro"],
                fase: "Protocolo: Claridad en Niebla",
                versiculo: '"Lámpara es a mis pies tu palabra, y lumbrera a mi camino."',
                analisis: "No intentes ver el final del camino. Solo necesitas luz para el siguiente paso de hoy. Ejecuta lo inmediato."
            },
            {
                tags: ["ambicion", "exito", "dinero", "crecer", "negocio"],
                fase: "Protocolo: Cimentación de Estructura",
                versiculo: '"Si el Señor no edificare la casa, en vano trabajan los que la edifican."',
                analisis: "Asegúrate de que tus proyectos tengan un propósito real. Si el cimiento es sólido, el crecimiento es inevitable."
            },
            {
                tags: ["espera", "paciencia", "tiempo", "tarda"],
                fase: "Protocolo: Maduración de Cosecha",
                versiculo: '"Todo tiene su tiempo, y todo lo que se quiere debajo del cielo tiene su hora."',
                analisis: "No puedes acelerar el crecimiento del arroz. Respeta los tiempos biológicos y operativos de tus proyectos."
            }
        ];

        function consultar() {
            const input = document.getElementById('userInput').value.toLowerCase();
            const resArea = document.getElementById('resultado');
            
            // Filtro avanzado: busca coincidencias parciales en los tags
            let opciones = biblioteca.filter(item => 
                item.tags.some(t => input.includes(t))
            );

            // Si no hay match, dar una respuesta por defecto para "General"
            const match = opciones.length > 0 
                ? opciones[Math.floor(Math.random() * opciones.length)] 
                : {
                    fase: "Protocolo: Estado General",
                    versiculo: '"Sobre toda cosa guardada, guarda tu corazón; porque de él mana la vida."',
                    analisis: "Tu estado no encaja en un diagnóstico crítico. Mantén la guardia de tu paz mental por encima de todo hoy."
                };

            resArea.classList.remove('hidden');
            document.getElementById('res-fase').innerText = match.fase;
            document.getElementById('res-versiculo').innerText = match.versiculo;
            document.getElementById('res-analisis').innerText = match.analisis;
        }
    </script>
</body>
</html>
