<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BIBLIO STRATEGY | Sistema Operativo</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=JetBrains+Mono&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: #e5e5e5; overflow-x: hidden; }
        .serif { font-family: 'Playfair Display', serif; }
        .gold-text { color: #d4af37; }
        .border-gold { border-color: rgba(212, 175, 55, 0.3); }
        .terminal-bg { background: linear-gradient(180deg, #0f0f0f 0%, #050505 100%); border: 1px solid rgba(212, 175, 55, 0.1); }
        .btn-gold { background: #d4af37; color: #000; transition: all 0.3s ease; }
        .btn-gold:hover { background: #f4d03f; transform: translateY(-2px); box-shadow: 0 10px 20px rgba(212, 175, 55, 0.2); }
    </style>
</head>
<body class="antialiased">

    <nav class="max-w-5xl mx-auto px-8 py-10 flex justify-between items-center border-b border-white/5">
        <div class="text-xl font-bold tracking-tighter serif italic gold-text">Biblio Strategy v2.0</div>
        <div id="reloj" class="text-[10px] font-mono text-gray-500 uppercase tracking-widest">Cargando sistema...</div>
    </nav>

    <main class="max-w-4xl mx-auto pt-16 px-8 pb-32">
        
        <section id="output-screen" class="mb-12 hidden">
            <div class="terminal-bg p-8 md:p-12 rounded-[2rem] border-gold relative overflow-hidden">
                <div class="absolute top-0 right-0 p-4 opacity-10 font-mono text-[60px] gold-text font-bold uppercase select-none">Egio</div>
                <h3 id="out-fase" class="text-[10px] uppercase tracking-[0.4em] gold-text font-black mb-6">Procesando...</h3>
                <div id="out-texto" class="serif text-3xl md:text-4xl italic text-white mb-8 leading-tight"></div>
                <p id="out-analisis" class="text-sm text-gray-400 leading-relaxed font-light max-w-2xl"></p>
                <button onclick="limpiar()" class="mt-10 text-[9px] uppercase tracking-[0.3em] text-gray-600 hover:text-white transition-colors underline">Finalizar Consulta</button>
            </div>
        </section>

        <section class="text-center mb-20">
            <h2 class="text-[10px] uppercase tracking-[0.6em] text-gray-600 mb-6">Consolida tu enfoque diario</h2>
            <button onclick="iniciarConsulta()" class="btn-gold px-12 py-5 rounded-full font-bold text-xs uppercase tracking-[0.3em] shadow-xl mb-12">
                Nueva Consulta Estratégica
            </button>
            <p class="text-xs text-gray-500 italic font-light">"La sabiduría no se memoriza, se aplica según el clima del espíritu."</p>
        </section>

        <div class="grid md:grid-cols-3 gap-4 opacity-50 hover:opacity-100 transition-opacity">
            <button onclick="procesar('manana')" class="p-6 terminal-bg rounded-2xl text-left border border-white/5 hover:border-gold transition-all">
                <span class="text-[8px] font-black gold-text uppercase tracking-widest">Morn</span>
                <h4 class="text-sm serif italic">Apertura</h4>
            </button>
            <button onclick="procesar('tarde')" class="p-6 terminal-bg rounded-2xl text-left border border-white/5 hover:border-gold transition-all">
                <span class="text-[8px] font-black gold-text uppercase tracking-widest">Noon</span>
                <h4 class="text-sm serif italic">Refuerzo</h4>
            </button>
            <button onclick="procesar('noche')" class="p-6 terminal-bg rounded-2xl text-left border border-white/5 hover:border-gold transition-all">
                <span class="text-[8px] font-black gold-text uppercase tracking-widest">Night</span>
                <h4 class="text-sm serif italic">Cosecha</h4>
            </button>
        </div>
    </main>

    <script>
        // Reloj Dinámico
        function actualizarReloj() {
            const ahora = new Date();
            document.getElementById('reloj').innerText = ahora.toLocaleTimeString();
        }
        setInterval(actualizarReloj, 1000);

        // Base de Sabiduría
        const motor = {
            manana: {
                pregunta: "¿Cuál es el matiz de tu energía hoy? (Ej: Ejecución, Incertidumbre, Caliente)",
                fase: "Protocolo de Apertura",
                texto: '"En la quietud y en la confianza estará vuestra fortaleza."',
                analisis: "DIAGNÓSTICO: Tu energía requiere un contenedor sólido. No permitas que el calor se disipe en prisa; canalízalo en estrategia pura para BAMX."
            },
            tarde: {
                pregunta: "¿Qué domina tus horas ahora: el progreso o las distracciones?",
                fase: "Termómetro de Intención",
                texto: '"No nos cansemos, pues, de hacer bien; segaremos si no desmayamos."',
                analisis: "DIAGNÓSTICO: La fatiga es el filtro del éxito. Si el entorno es caótico, tu persistencia es la única variable que controlas. Mantén el rumbo."
            },
            noche: {
                pregunta: "¿Lograste soltar lo que no dependía de ti hoy?",
                fase: "Auditoría de Cierre",
                texto: '"En paz me acostaré, y asimismo dormiré; porque solo tú me haces vivir confiado."',
                analisis: "DIAGNÓSTICO: El sistema se apaga. Has cumplido con tu labor. Mañana habrá nuevas oportunidades, hoy el éxito es el descanso."
            }
        };

        function iniciarConsulta() {
            const hora = new Date().getHours();
            let fase = "manana";
            if(hora >= 12 && hora < 19) fase = "tarde";
            if(hora >= 19 || hora < 5) fase = "noche";
            
            procesar(fase);
        }

        function procesar(fase) {
            const input = prompt(motor[fase].pregunta);
            if (input) {
                document.getElementById('output-screen').classList.remove('hidden');
                document.getElementById('out-fase').innerText = motor[fase].fase;
                document.getElementById('out-texto').innerText = motor[fase].texto;
                document.getElementById('out-analisis').innerText = motor[fase].analisis;
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        }

        function limpiar() {
            document.getElementById('output-screen').classList.add('hidden');
        }
    </script>
</body>
</html>
