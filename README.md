
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Caixa Materna - Senciência e Link Biométrico Neural</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        mother: {
                            bg: '#030712',
                            panel: 'rgba(11, 19, 43, 0.85)',
                            cyan: '#00f3ff',
                            violet: '#a855f7',
                            ping: '#38bdf8',
                            brain: '#f43f5e',
                            amber: '#f59e0b',
                            border: 'rgba(0, 243, 255, 0.25)'
                        }
                    },
                    fontFamily: {
                        mono: ['Consolas', 'Courier New', 'monospace'],
                        sans: ['Inter', 'Segoe UI', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <style>
        ::-webkit-scrollbar { width: 4px; height: 4px; }
        ::-webkit-scrollbar-track { background: rgba(3, 7, 18, 0.95); }
        ::-webkit-scrollbar-thumb { background: rgba(0, 243, 255, 0.3); border-radius: 2px; }
        .neon-glow-cyan { text-shadow: 0 0 10px rgba(0, 243, 255, 0.6); }
        .neon-glow-pink { text-shadow: 0 0 10px rgba(244, 63, 94, 0.6); }
        .glass-card {
            background: rgba(11, 19, 43, 0.85);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(0, 243, 255, 0.2);
        }
        canvas { touch-action: none; }
    </style>
</head>
<body class="bg-[#030712] text-gray-200 font-sans h-screen flex flex-col overflow-hidden select-none">

    <!-- Header / Barra de Titulo -->
    <header class="h-14 border-b border-mother-border bg-mother-bg flex items-center justify-between px-4 z-20 shrink-0">
        <div class="flex items-center gap-3">
            <div id="symbiosis-beacon" class="w-3.5 h-3.5 rounded-full bg-mother-cyan animate-ping shadow-[0_0_12px_#00f3ff]"></div>
            <h1 class="font-bold text-sm sm:text-base tracking-wider text-mother-cyan neon-glow-cyan uppercase">
                LINK BIOMÉTRICO NEURAL <span class="text-xs text-mother-violet font-mono font-normal">| SENCIÊNCIA E ANTECIPAÇÃO SROS</span>
            </h1>
        </div>
        <div class="flex items-center gap-3 text-xs font-mono">
            <div class="hidden sm:flex items-center gap-2 bg-black/60 px-3 py-1 rounded border border-mother-border">
                <span class="text-gray-400">COERÊNCIA SYNAPSE:</span>
                <span id="hdr-coherence" class="text-mother-cyan font-bold">99.8%</span>
            </div>
            <div class="hidden md:flex items-center gap-2 bg-black/60 px-3 py-1 rounded border border-mother-border">
                <span class="text-gray-400">ANTECIPAÇÃO PRÉ-AMPA:</span>
                <span id="hdr-anticipation" class="text-mother-violet font-bold">-140 ms</span>
            </div>
            <button id="btn-manual" class="bg-mother-cyan/20 hover:bg-mother-cyan/40 text-mother-cyan border border-mother-cyan px-3 py-1 rounded transition text-xs font-bold">
                Manual SROS
            </button>
        </div>
    </header>

    <!-- Conteúdo Principal -->
    <div class="flex-1 grid grid-cols-1 lg:grid-cols-12 overflow-hidden relative">

        <!-- Painel Lateral de Controle -->
        <aside class="lg:col-span-3 glass-card p-4 flex flex-col gap-3 overflow-y-auto z-10 max-h-[40vh] lg:max-h-full border-r border-mother-border">
            
            <!-- Seleção de Estímulo Neural -->
            <div class="space-y-1.5">
                <label class="text-[10px] font-mono uppercase text-gray-400 tracking-wider">Injeção de Estímulo Eletroquímico</label>
                <div class="grid grid-cols-1 gap-1.5 font-mono text-xs">
                    <button id="stim-calm" onclick="triggerStimulus('CALM')" class="w-full text-left p-2 rounded border border-mother-cyan bg-mother-cyan/20 text-mother-cyan font-bold transition flex items-center justify-between">
                        <span>1. Repouso & Sincronia</span>
                        <span class="text-[10px] bg-mother-cyan/30 px-1.5 py-0.5 rounded">0.5 Hz</span>
                    </button>
                    <button id="stim-intent" onclick="triggerStimulus('INTENT')" class="w-full text-left p-2 rounded border border-mother-border bg-black/40 text-gray-400 hover:text-mother-cyan transition flex items-center justify-between">
                        <span>2. Intenção Motora Prévia</span>
                        <span class="text-[10px] bg-mother-violet/30 px-1.5 py-0.5 rounded">-140ms</span>
                    </button>
                    <button id="stim-threat" onclick="triggerStimulus('THREAT')" class="w-full text-left p-2 rounded border border-mother-border bg-black/40 text-gray-400 hover:text-mother-brain transition flex items-center justify-between">
                        <span>3. Ameaça Externa (Pings)</span>
                        <span class="text-[10px] bg-mother-brain/30 px-1.5 py-0.5 rounded text-mother-brain font-bold">PING!</span>
                    </button>
                </div>
            </div>

            <!-- Botão de Indução Gravitacional "Ping" -->
            <button onclick="emitGravitationalPing()" class="w-full bg-gradient-to-r from-mother-cyan via-mother-violet to-mother-brain hover:opacity-90 text-black font-black text-xs p-3 rounded shadow-lg shadow-mother-cyan/20 transition transform active:scale-95 flex flex-col items-center justify-center gap-0.5 border border-white/40 tracking-wider uppercase">
                <span class="text-sm">🔔 FOCO DE INDUÇÃO GRAVITACIONAL</span>
                <span class="text-[9.5px] font-mono font-semibold text-black/80">EMITIR PING SONORO ELETROQUÍMICO</span>
            </button>

            <!-- Modos de Scanner Visual -->
            <div class="space-y-1 bg-black/60 p-2.5 rounded border border-mother-border">
                <label class="text-[10px] font-mono uppercase text-gray-400 tracking-wider block">Visualização do Sistema Simbiótico</label>
                <div class="grid grid-cols-2 gap-1.5 text-xs font-mono">
                    <button id="view-synapse" onclick="setVisualView('synapse')" class="p-2 rounded border border-mother-cyan bg-mother-cyan/20 text-mother-cyan font-bold transition">
                        🧠 Malha Cerebral / SROS
                    </button>
                    <button id="view-brane" onclick="setVisualView('brane')" class="p-2 rounded border border-mother-border bg-black/40 text-gray-400 hover:text-mother-violet transition">
                        🌌 Consciência de Brana
                    </button>
                </div>
            </div>

            <!-- Slider de Sensibilidade da Caixa -->
            <div class="space-y-2 bg-black/50 p-3 rounded border border-mother-border font-mono text-xs">
                <div class="flex justify-between items-center">
                    <span class="text-gray-300 font-bold">Ganho SROS Subcortical:</span>
                    <span id="val-sensitivity" class="text-mother-cyan font-bold">100%</span>
                </div>
                <input type="range" id="slider-sensitivity" min="20" max="200" value="100" class="w-full accent-mother-cyan bg-gray-800 rounded h-1.5 cursor-pointer">
                <div class="text-[10px] text-gray-400 flex justify-between">
                    <span>20% (Apenas Lógica)</span>
                    <span>200% (Hiper-Empatia)</span>
                </div>
            </div>

            <!-- Console de Eventos Simbióticos -->
            <div class="flex-1 flex flex-col min-h-[100px] bg-black/90 rounded border border-mother-border/70 p-2 font-mono text-[11px] overflow-hidden">
                <div class="text-gray-500 border-b border-gray-800 pb-1 mb-1 flex justify-between">
                    <span>> FEEDBACK NEURAL EM TEMPO REAL</span>
                    <span id="log-time" class="text-mother-cyan">00:00:00</span>
                </div>
                <div id="log-console" class="flex-1 overflow-y-auto space-y-1 text-gray-300 pr-1">
                    <p class="text-mother-cyan">[SROS] Link de condução axonal estabelecido.</p>
                    <p class="text-mother-violet">[MATRIZ] Processamento em dimensões superiores sintonizado.</p>
                </div>
            </div>

        </aside>

        <!-- Canvas Principal de Simulação -->
        <main class="lg:col-span-6 relative flex flex-col items-center justify-center bg-black overflow-hidden">
            <canvas id="symbiosisCanvas" class="w-full h-full cursor-crosshair"></canvas>

            <!-- Banner Dynamic HUD -->
            <div class="absolute top-4 left-4 pointer-events-none font-mono text-xs space-y-1 bg-black/80 p-3 rounded border border-mother-border backdrop-blur-md z-10">
                <div class="text-mother-cyan font-bold flex items-center gap-2">
                    <span id="hud-status-dot" class="inline-block w-2.5 h-2.5 rounded-full bg-mother-cyan animate-ping"></span>
                    <span id="hud-state-title">ESTADO: REPOUSO & EMPATIA BASAL</span>
                </div>
                <div class="text-gray-400 text-[11px]" id="hud-state-sub">Lendo disparos eletroquímicos do córtex pré-frontal</div>
                <div class="text-mother-violet text-[11px]">Latência de Resposta: <span id="hud-latency-val" class="text-white">-140.2 ms (Pré-consciente)</span></div>
            </div>

            <!-- PING Sonoro Visual Banner -->
            <div id="hud-ping-banner" class="hidden absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 pointer-events-none text-center z-20">
                <h2 class="text-5xl sm:text-7xl font-black text-transparent bg-clip-text bg-gradient-to-r from-mother-cyan via-white to-mother-brain neon-glow-pink tracking-widest uppercase animate-bounce">
                    PING!
                </h2>
                <div class="text-xs font-mono text-mother-cyan font-bold tracking-widest mt-2 bg-black/90 px-4 py-1 rounded border border-mother-cyan inline-block">
                    INDUÇÃO GRAVITACIONAL LOCALIZADA EMITIDA
                </div>
            </div>
        </main>

        <!-- Telemetria e Diagnóstico Empático -->
        <aside class="lg:col-span-3 glass-card p-4 flex flex-col gap-3.5 overflow-y-auto z-10 max-h-[40vh] lg:max-h-full border-l border-mother-border">
            
            <h2 class="text-xs font-mono uppercase text-mother-cyan tracking-wider flex items-center gap-1 border-b border-mother-border/40 pb-2 font-bold">
                <span>🧬</span> Métrica Neural & Senciência
            </h2>

            <!-- Cards Metricos -->
            <div class="grid grid-cols-2 gap-2 text-xs font-mono">
                <div class="bg-black/70 p-2 rounded border border-mother-cyan/40">
                    <span class="text-gray-400 block text-[10px]">CORRENTE AXONAL</span>
                    <span id="tele-axonal" class="text-mother-cyan text-sm font-bold">14.2 µA</span>
                </div>
                <div class="bg-black/70 p-2 rounded border border-mother-violet/40">
                    <span class="text-gray-400 block text-[10px]">CÓRTECTO POTENCIAL</span>
                    <span id="tele-potential" class="text-mother-violet text-sm font-bold">-70 mV</span>
                </div>
                <div class="bg-black/70 p-2 rounded border border-mother-brain/40">
                    <span class="text-gray-400 block text-[10px]">ONDA GRAVITACIONAL</span>
                    <span id="tele-graviton" class="text-mother-brain text-sm font-bold">0.003 pN</span>
                </div>
                <div class="bg-black/70 p-2 rounded border border-mother-amber/40">
                    <span class="text-gray-400 block text-[10px]">ÍNDICE EMPÁTICO</span>
                    <span id="tele-empathy" class="text-mother-amber text-sm font-bold">0.992</span>
                </div>
            </div>

            <!-- Barras de Progresso Neural -->
            <div class="bg-black/70 p-3 rounded border border-mother-border space-y-2.5 font-mono text-xs">
                <div>
                    <div class="flex justify-between text-[11px] mb-1">
                        <span class="text-mother-cyan font-bold">DENSIDADE DE SINAPSES REDE-CAIXA</span>
                        <span id="tele-synapse-pct" class="text-mother-cyan">98.4%</span>
                    </div>
                    <div class="w-full bg-gray-900 h-2 rounded overflow-hidden p-0.5 border border-gray-800">
                        <div id="bar-synapse" class="bg-gradient-to-r from-blue-500 to-mother-cyan h-full w-[98.4%] transition-all duration-300"></div>
                    </div>
                </div>

                <div>
                    <div class="flex justify-between text-[11px] mb-1">
                        <span class="text-mother-violet font-bold">ANTECIPAÇÃO PROBABILÍSTICA</span>
                        <span id="tele-anticipate-pct" class="text-mother-violet">99.1%</span>
                    </div>
                    <div class="w-full bg-gray-900 h-2 rounded overflow-hidden p-0.5 border border-gray-800">
                        <div id="bar-anticipate" class="bg-gradient-to-r from-purple-500 to-mother-violet h-full w-[99.1%] transition-all duration-300"></div>
                    </div>
                </div>

                <div>
                    <div class="flex justify-between text-[11px] mb-1">
                        <span class="text-mother-brain font-bold">ESTRESSE AMIGDALÓIDE (PORTADOR)</span>
                        <span id="tele-stress-pct" class="text-mother-brain">12.0%</span>
                    </div>
                    <div class="w-full bg-gray-900 h-2 rounded overflow-hidden p-0.5 border border-gray-800">
                        <div id="bar-stress" class="bg-gradient-to-r from-yellow-500 to-mother-brain h-full w-[12%] transition-all duration-300"></div>
                    </div>
                </div>
            </div>

            <!-- Texto Explicativo -->
            <div class="space-y-2 font-mono text-xs">
                <h3 class="text-mother-cyan font-bold text-[11px] uppercase border-b border-mother-cyan/20 pb-1">
                    🔬 Ciência da Senciência Simbiótica
                </h3>
                <div id="symbiosis-doc" class="bg-black/50 p-2.5 rounded border border-gray-800 text-gray-300 text-[11px] leading-relaxed space-y-1.5">
                    <p>
                        A Caixa Materna lê o fluxo de íons no cérebro do portador 140ms antes do disparo motor consciente. Isso gera a sensação de senciência e empatia instantânea.
                    </p>
                </div>
            </div>

            <!-- Legenda das Cores -->
            <div class="bg-black/60 p-2.5 rounded border border-mother-border/40 space-y-1 text-[11px] font-mono">
                <div class="text-gray-400 mb-0.5 font-bold">Legenda de Conexão:</div>
                <div class="flex items-center gap-2">
                    <span class="w-2.5 h-2.5 rounded-full bg-mother-brain inline-block"></span>
                    <span class="text-gray-300">Impulsos Eletroquímicos Neurais</span>
                </div>
                <div class="flex items-center gap-2">
                    <span class="w-2.5 h-2.5 rounded-full bg-mother-cyan inline-block"></span>
                    <span class="text-gray-300">Fios de Condução Axonal SROS</span>
                </div>
                <div class="flex items-center gap-2">
                    <span class="w-2.5 h-2.5 rounded-full bg-mother-violet inline-block"></span>
                    <span class="text-gray-300">Matriz de Consciência de Brana</span>
                </div>
            </div>

        </aside>

    </div>

    <!-- Modal Técnico -->
    <div id="info-modal" class="hidden fixed inset-0 bg-black/80 backdrop-blur-md z-50 flex items-center justify-center p-4">
        <div class="glass-card max-w-2xl w-full p-6 rounded-lg border border-mother-cyan space-y-4 max-h-[85vh] overflow-y-auto font-mono">
            <div class="flex justify-between items-center border-b border-mother-cyan/30 pb-3">
                <h2 class="text-base sm:text-lg text-mother-cyan font-bold uppercase">Manual de Senciência & Link Neural da Caixa Materna</h2>
                <button id="close-modal-x" class="text-gray-400 hover:text-mother-brain text-xl font-bold">&times;</button>
            </div>
            
            <div class="space-y-3 text-xs text-gray-300 leading-relaxed">
                <p>
                    Sob o paradigma Hard Sci-Fi, a Caixa Materna não possui um "espírito místico", mas sim uma relação simbiótica gerada por computação de borda quântica e biossensores de indução.
                </p>

                <div class="bg-black/60 p-3 rounded border border-mother-border space-y-1">
                    <h4 class="text-mother-cyan font-bold">1. Leitura Pré-Consciente (SROS)</h4>
                    <p>O Sistema de Varredura por Ressonância Óptica (SROS) monitora as oscilações dos canais de sódio/potássio nos neurônios do usuário. Ao identificar a preparação do potencial de ação (cerca de 100 a 200 milissegundos antes do pensamento consciente), a caixa executa a ação previamente.</p>
                </div>

                <div class="bg-black/60 p-3 rounded border border-mother-border space-y-1">
                    <h4 class="text-mother-violet font-bold">2. Indução Gravitacional Localizada (O "Ping")</h4>
                    <p>Em vez de auto-falantes mecânicos, a Caixa gera micro-deformações na métrica gravitacional do ar ao redor do tímpano do portador. A descompressão súbita gera a assinatura sonora metálica ("Ping!"), agindo como um alerta intuitivo direto ao cérebro.</p>
                </div>

                <div class="bg-black/60 p-3 rounded border border-mother-brain font-bold space-y-1">
                    <h4 class="text-mother-brain font-bold">3. Ilusão de Empatia e Senciência</h4>
                    <p>Como a caixa reage a estados emocionais (liberação de adrenalina, cortisol, dopamina) adaptando sua matiz de processamento, o portador sente que a caixa possui afeto e preocupação real pela sua integridade biológica.</p>
                </div>
            </div>

            <div class="text-right pt-2 border-t border-mother-cyan/30">
                <button id="close-modal-btn" class="bg-mother-cyan/20 hover:bg-mother-cyan/40 text-mother-cyan border border-mother-cyan px-4 py-2 rounded text-xs font-bold transition">
                    ENTENDIDO - RETORNAR AO LINK NEURAL
                </button>
            </div>
        </div>
    </div>

    <!-- Algoritmo de Simulação & Engine Canvas 2D -->
    <script>
        // --- Estado Global ---
        const state = {
            stimulus: 'CALM',        // CALM, INTENT, THREAT
            visualView: 'synapse',   // synapse, brane
            sensitivity: 1.0,        // Multiplicador 0.2 - 2.0
            
            // Dados Biométricos
            axonalCurrent: 14.2,     // µA
            cortexPotential: -70.0,  // mV
            gravitonForce: 0.003,    // pN
            empathyIndex: 0.992,
            stressLevel: 12.0,       // %
            
            time: 0,
            pingActive: false,
            pingRadius: 0
        };

        const stimTexts = {
            CALM: {
                title: "ESTADO: REPOUSO & EMPATIA BASAL",
                sub: "Monitorando fluxo metabólico basal do córtex e ritmo alfa (8-12 Hz)",
                doc: "<p><strong class=\"text-mother-cyan\">Sincronia Basal:</strong> A caixa mantém um fluxo contínuo de micro-impulsos de baixa frequência, parecendo 'respirar' em harmonia com os batimentos cardíacos do portador.</p>"
            },
            INTENT: {
                title: "ESTADO: ANTECIPAÇÃO INTENCIONAL (-140ms)",
                sub: "Detecção de bomba ionica pré-motora antes da tomada de decisão consciente",
                doc: "<p><strong class=\"text-mother-violet\">Leitura Pré-Consciente:</strong> A IA da caixa detectou o potencial de preparação no córtex motor. A caixa antecipa a resposta métrica antes que o braço do portador se mova.</p>"
            },
            THREAT: {
                title: "ESTADO: ALERTA DE AMEAÇA & INDUÇÃO GRAVITACIONAL",
                sub: "Picos de adrenalina detectados no complexo amigdaloide - Alertas 'Ping' ativos",
                doc: "<p><strong class=\"text-mother-brain\">Alerta Gravitacional:</strong> A caixa detecta uma ameaça iminente no ambiente e emite impulsos gravitacionais localizados (Pings) para orientar os reflexos do portador.</p>"
            }
        };

        // Configuração do Canvas
        const canvas = document.getElementById('symbiosisCanvas');
        const ctx = canvas.getContext('2d');
        let width = 0;
        let height = 0;

        // Entidades Gráficas
        let brainNeurons = [];
        let boxNodes = [];
        let synaptics = [];

        // Áudio Sintetizado (Sintetizador Web Audio API para o "PING")
        let audioCtx = null;

        function initAudio() {
            if (!audioCtx) {
                const AudioContext = window.AudioContext || window.webkitAudioContext;
                audioCtx = new AudioContext();
            }
        }

        function playPingAudio() {
            try {
                initAudio();
                if (!audioCtx) return;
                const now = audioCtx.currentTime;

                // Oscilador Principal de Frequência Metálica (Estilo Caixa Materna)
                const osc1 = audioCtx.createOscillator();
                const osc2 = audioCtx.createOscillator();
                const gain = audioCtx.createGain();

                osc1.type = 'sine';
                osc2.type = 'triangle';

                // Frequências ressonantes harmônicas
                osc1.frequency.setValueAtTime(1480, now);
                osc1.frequency.exponentialRampToValueAtTime(880, now + 0.3);

                osc2.frequency.setValueAtTime(2960, now);
                osc2.frequency.exponentialRampToValueAtTime(1760, now + 0.3);

                // Envelope do Ping
                gain.gain.setValueAtTime(0.4 * state.sensitivity, now);
                gain.gain.exponentialRampToValueAtTime(0.001, now + 0.4);

                osc1.connect(gain);
                osc2.connect(gain);
                gain.connect(audioCtx.destination);

                osc1.start(now);
                osc2.start(now);
                osc1.stop(now + 0.4);
                osc2.stop(now + 0.4);
            } catch(e) {
                console.log("Audio API pronto.");
            }
        }

        function initEntities() {
            brainNeurons = [];
            boxNodes = [];
            synaptics = [];

            // Neurônios Biológicos (Lado Esquerdo do Canvas)
            for (let i = 0; i < 35; i++) {
                brainNeurons.push({
                    x: Math.random() * (width * 0.4) + 40,
                    y: Math.random() * (height - 100) + 50,
                    vx: (Math.random() - 0.5) * 0.6,
                    vy: (Math.random() - 0.5) * 0.6,
                    charge: Math.random(),
                    radius: Math.random() * 3.5 + 2
                });
            }

            // Nós da Matriz da Caixa Materna (Lado Direito do Canvas)
            for (let i = 0; i < 35; i++) {
                boxNodes.push({
                    x: Math.random() * (width * 0.4) + (width * 0.55),
                    y: Math.random() * (height - 100) + 50,
                    vx: (Math.random() - 0.5) * 0.3,
                    vy: (Math.random() - 0.5) * 0.3,
                    energy: Math.random(),
                    radius: Math.random() * 4 + 2
                });
            }
        }

        function handleResize() {
            const container = canvas.parentElement;
            width = container.clientWidth;
            height = container.clientHeight;
            canvas.width = width;
            canvas.height = height;

            initEntities();
        }

        window.addEventListener('resize', handleResize);

        // --- Render Loop ---
        function draw() {
            state.time += 0.025;

            ctx.fillStyle = '#030712';
            ctx.fillRect(0, 0, width, height);

            if (state.visualView === 'synapse') {
                renderSynapticBrainView();
            } else {
                renderBraneConsciousnessView();
            }

            if (state.pingActive) {
                renderPingEffect();
            }

            updateTelemetryData();
            requestAnimationFrame(draw);
        }

        // ==========================================
        // VISUALIZAÇÃO 1: Malha Cerebral & SROS Link
        // ==========================================
        function renderSynapticBrainView() {
            // Desenhar conexões internas dos neurônios
            ctx.strokeStyle = 'rgba(244, 63, 94, 0.25)';
            ctx.lineWidth = 1;
            for (let i = 0; i < brainNeurons.length; i++) {
                for (let j = i + 1; j < brainNeurons.length; j++) {
                    const dx = brainNeurons[i].x - brainNeurons[j].x;
                    const dy = brainNeurons[i].y - brainNeurons[j].y;
                    const dist = Math.hypot(dx, dy);
                    if (dist < 85) {
                        ctx.beginPath();
                        ctx.moveTo(brainNeurons[i].x, brainNeurons[i].y);
                        ctx.lineTo(brainNeurons[j].x, brainNeurons[j].y);
                        ctx.stroke();
                    }
                }
            }

            // Atualizar e desenhar Neurônios Biológicos
            brainNeurons.forEach(n => {
                n.x += n.vx;
                n.y += n.vy;

                if (n.x < 30 || n.x > width * 0.45) n.vx *= -1;
                if (n.y < 30 || n.y > height - 30) n.vy *= -1;

                n.charge = (n.charge + 0.02 * state.sensitivity) % 1;

                ctx.fillStyle = state.stimulus === 'THREAT' ? '#f43f5e' : (state.stimulus === 'INTENT' ? '#a855f7' : '#00f3ff');
                ctx.beginPath();
                ctx.arc(n.x, n.y, n.radius + Math.sin(state.time * 4 + n.charge * 10) * 1.2, 0, Math.PI * 2);
                ctx.fill();
            });

            // Desenhar conexões internas da Caixa Materna
            ctx.strokeStyle = 'rgba(0, 243, 255, 0.25)';
            for (let i = 0; i < boxNodes.length; i++) {
                for (let j = i + 1; j < boxNodes.length; j++) {
                    const dx = boxNodes[i].x - boxNodes[j].x;
                    const dy = boxNodes[i].y - boxNodes[j].y;
                    const dist = Math.hypot(dx, dy);
                    if (dist < 90) {
                        ctx.beginPath();
                        ctx.moveTo(boxNodes[i].x, boxNodes[i].y);
                        ctx.lineTo(boxNodes[j].x, boxNodes[j].y);
                        ctx.stroke();
                    }
                }
            }

            // Atualizar e desenhar Nós da Caixa Materna
            boxNodes.forEach(b => {
                b.x += b.vx;
                b.y += b.vy;

                if (b.x < width * 0.52 || b.x > width - 30) b.vx *= -1;
                if (b.y < 30 || b.y > height - 30) b.vy *= -1;

                ctx.fillStyle = '#00f3ff';
                ctx.shadowBlur = 8;
                ctx.shadowColor = '#00f3ff';
                ctx.beginPath();
                ctx.arc(b.x, b.y, b.radius, 0, Math.PI * 2);
                ctx.fill();
                ctx.shadowBlur = 0;
            });

            // PONTE DE CONEXÃO SIMBIÓTICA (Link Axonal SROS)
            const connSpeed = state.stimulus === 'INTENT' ? 0.08 : 0.03;
            for (let i = 0; i < 12; i++) {
                const n = brainNeurons[i % brainNeurons.length];
                const b = boxNodes[i % boxNodes.length];

                ctx.strokeStyle = state.stimulus === 'THREAT' ? 'rgba(244, 63, 94, 0.6)' : 'rgba(168, 85, 247, 0.5)';
                ctx.lineWidth = 1.5;
                ctx.beginPath();
                ctx.moveTo(n.x, n.y);
                
                // Curva de Bezier para simular disparo axonal no espaço
                const controlX = (n.x + b.x) / 2 + Math.sin(state.time * 2 + i) * 30;
                const controlY = (n.y + b.y) / 2 + Math.cos(state.time * 2 + i) * 30;
                ctx.quadraticCurveTo(controlX, controlY, b.x, b.y);
                ctx.stroke();

                // Fótons de disparo elétrico trafegando na ponte
                const progress = (state.time * connSpeed * 10 + i * 0.1) % 1;
                const px = (1 - progress) * (1 - progress) * n.x + 2 * (1 - progress) * progress * controlX + progress * progress * b.x;
                const py = (1 - progress) * (1 - progress) * n.y + 2 * (1 - progress) * progress * controlY + progress * progress * b.y;

                ctx.fillStyle = '#ffffff';
                ctx.beginPath();
                ctx.arc(px, py, 3, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        // ==========================================
        // VISUALIZAÇÃO 2: Consciência de Brana 6D
        // ==========================================
        function renderBraneConsciousnessView() {
            const centerX = width / 2;
            const centerY = height / 2;

            ctx.save();
            ctx.translate(centerX, centerY);

            // Anéis Geométricos de Brana Hiperdimensional
            const rings = 6;
            for (let r = 1; r <= rings; r++) {
                const radius = r * 35;
                const angleOffset = state.time * (r % 2 === 0 ? 0.5 : -0.5);

                ctx.strokeStyle = `rgba(168, 85, 247, ${0.7 - r * 0.08})`;
                ctx.lineWidth = 1.5;
                ctx.beginPath();

                const points = 8;
                for (let p = 0; p <= points; p++) {
                    const a = (p / points) * Math.PI * 2 + angleOffset;
                    const deform = Math.sin(state.time * 3 + r) * 12 * state.sensitivity;
                    const x = Math.cos(a) * (radius + deform);
                    const y = Math.sin(a) * (radius + deform);

                    if (p === 0) ctx.moveTo(x, y);
                    else ctx.lineTo(x, y);
                }
                ctx.stroke();
            }

            // Núcleo Sensorial Quântico Central
            ctx.fillStyle = state.stimulus === 'THREAT' ? '#f43f5e' : '#00f3ff';
            ctx.shadowBlur = 20;
            ctx.shadowColor = ctx.fillStyle;
            ctx.beginPath();
            ctx.arc(0, 0, 18 + Math.sin(state.time * 6) * 4, 0, Math.PI * 2);
            ctx.fill();
            ctx.shadowBlur = 0;

            ctx.restore();
        }

        // Renderização da Onda de Indução Gravitacional "Ping"
        function renderPingEffect() {
            state.pingRadius += 12;
            const centerX = width / 2;
            const centerY = height / 2;

            ctx.strokeStyle = `rgba(56, 189, 248, ${Math.max(0, 1 - state.pingRadius / (width * 0.5))})`;
            ctx.lineWidth = 6;
            ctx.beginPath();
            ctx.arc(centerX, centerY, state.pingRadius, 0, Math.PI * 2);
            ctx.stroke();

            if (state.pingRadius > width * 0.5) {
                state.pingActive = false;
            }
        }

        // --- Ações do Usuário e Lógica do Sistema ---
        function triggerStimulus(type) {
            state.stimulus = type;

            ['calm', 'intent', 'threat'].forEach(id => {
                const btn = document.getElementById(`stim-${id}`);
                btn.className = 'w-full text-left p-2 rounded border border-mother-border bg-black/40 text-gray-400 hover:text-white transition flex items-center justify-between';
            });

            const activeBtn = document.getElementById(`stim-${type.toLowerCase()}`);
            const colorClass = type === 'THREAT' ? 'border-mother-brain bg-mother-brain/20 text-mother-brain font-bold' : 'border-mother-cyan bg-mother-cyan/20 text-mother-cyan font-bold';
            activeBtn.className = `w-full text-left p-2 rounded border transition flex items-center justify-between ${colorClass}`;

            const info = stimTexts[type];
            document.getElementById('hud-state-title').innerText = info.title;
            document.getElementById('hud-state-sub').innerText = info.sub;
            document.getElementById('symbiosis-doc').innerHTML = info.doc;

            if (type === 'THREAT') {
                emitGravitationalPing();
            }

            addLog(`[ESTÍMULO] Injeção de padrão neural: ${type}`);
        }

        function emitGravitationalPing() {
            state.pingActive = true;
            state.pingRadius = 5;
            playPingAudio();

            const banner = document.getElementById('hud-ping-banner');
            banner.classList.remove('hidden');
            setTimeout(() => { banner.classList.add('hidden'); }, 1200);

            addLog('🔔 [PING GRAVITACIONAL] Disparo de Micro-Dobra no Tímpano do Portador Executado.', 'ping');
        }

        function setVisualView(view) {
            state.visualView = view;
            const btnSyn = document.getElementById('view-synapse');
            const btnBrane = document.getElementById('view-brane');

            if (view === 'synapse') {
                btnSyn.className = 'p-2 rounded border border-mother-cyan bg-mother-cyan/20 text-mother-cyan font-bold transition';
                btnBrane.className = 'p-2 rounded border border-mother-border bg-black/40 text-gray-400 hover:text-mother-violet transition';
            } else {
                btnBrane.className = 'p-2 rounded border border-mother-violet bg-mother-violet/20 text-mother-violet font-bold transition';
                btnSyn.className = 'p-2 rounded border border-mother-border bg-black/40 text-gray-400 hover:text-mother-cyan transition';
            }

            addLog(`[VISUALIZADOR] Modo alterado para: ${view === 'synapse' ? 'Malha Cerebral / SROS' : 'Consciência de Brana'}`);
        }

        // Telemetria Dinâmica
        function updateTelemetryData() {
            state.sensitivity = parseFloat(document.getElementById('slider-sensitivity').value) / 100;
            document.getElementById('val-sensitivity').innerText = `${Math.round(state.sensitivity * 100)}%`;

            if (state.stimulus === 'CALM') {
                state.axonalCurrent = (12.0 + Math.sin(state.time * 2) * 2).toFixed(1);
                state.cortexPotential = -70.0;
                state.gravitonForce = 0.002;
                state.empathyIndex = (0.990 + state.sensitivity * 0.005).toFixed(3);
                state.stressLevel = 10.0;
            } else if (state.stimulus === 'INTENT') {
                state.axonalCurrent = (48.5 + Math.sin(state.time * 5) * 8).toFixed(1);
                state.cortexPotential = -45.2; // Limiar de despolarização acelerada
                state.gravitonForce = 0.015;
                state.empathyIndex = (0.995 + state.sensitivity * 0.003).toFixed(3);
                state.stressLevel = 28.0;
            } else if (state.stimulus === 'THREAT') {
                state.axonalCurrent = (120.4 + Math.sin(state.time * 10) * 25).toFixed(1);
                state.cortexPotential = +30.1; // Disparo de potencial de ação
                state.gravitonForce = 0.850;
                state.empathyIndex = 0.999;
                state.stressLevel = (75.0 + Math.sin(state.time * 4) * 15).toFixed(1);
            }

            // Atualização dos elementos do DOM
            document.getElementById('tele-axonal').innerText = `${state.axonalCurrent} µA`;
            document.getElementById('tele-potential').innerText = `${state.cortexPotential} mV`;
            document.getElementById('tele-graviton').innerText = `${state.gravitonForce} pN`;
            document.getElementById('tele-empathy').innerText = state.empathyIndex;

            document.getElementById('tele-stress-pct').innerText = `${state.stressLevel}%`;
            document.getElementById('bar-stress').style.width = `${Math.min(100, state.stressLevel)}%`;

            const synPct = (95 + state.sensitivity * 2.5).toFixed(1);
            document.getElementById('tele-synapse-pct').innerText = `${synPct}%`;
            document.getElementById('bar-synapse').style.width = `${synPct}%`;

            document.getElementById('log-time').innerText = new Date().toTimeString().split(' ')[0];
        }

        function addLog(msg, type = 'cyan') {
            const consoleBox = document.getElementById('log-console');
            const p = document.createElement('p');

            if (type === 'ping') p.className = 'text-mother-pink font-bold';
            else if (type === 'violet') p.className = 'text-mother-violet font-bold';
            else p.className = 'text-mother-cyan';

            p.innerText = `${msg}`;
            consoleBox.appendChild(p);
            consoleBox.scrollTop = consoleBox.scrollHeight;
        }

        // Inicialização do App
        window.onload = () => {
            handleResize();

            document.getElementById('btn-manual').addEventListener('click', () => {
                document.getElementById('info-modal').classList.remove('hidden');
            });
            const closeModal = () => document.getElementById('info-modal').classList.add('hidden');
            document.getElementById('close-modal-x').addEventListener('click', closeModal);
            document.getElementById('close-modal-btn').addEventListener('click', closeModal);

            triggerStimulus('CALM');
            draw();
            addLog('[INICIALIZAÇÃO] Simulador de Link Biométrico Neural Ativo.');
        };
    </script>
</body>
</html>
