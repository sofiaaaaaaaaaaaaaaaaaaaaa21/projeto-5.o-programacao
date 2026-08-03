!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Projeto Integrador de Automação e Aquecimento Solar Sustentável para a Piscina Térmica do CEP.">
    <title>EcoPiscina CEP - Automação & Óptica Aplicada</title>
    
    <style>
        /* ==========================================================================
           1. VARIÁVEIS DE DESIGN E ACESSIBILIDADE
           ========================================================================== */
        :root {
            --primary-color: #0b4f6c;
            --secondary-color: #01baef;
            --accent-color: #f7b2b7;
            --bg-color: #fbfbfc;
            --card-bg: #ffffff;
            --text-color: #1a1a1a;
            --border-color: #d1d5db;
            --focus-ring: #2563eb;
            --font-main: 'Segoe UI', system-ui, -apple-system, sans-serif;
            --font-size-base: 1rem;
        }

        /* Tema de Alto Contraste (Acessibilidade) */
        body.high-contrast {
            --primary-color: #ffff00;
            --secondary-color: #00ffff;
            --bg-color: #000000;
            --card-bg: #121212;
            --text-color: #ffffff;
            --border-color: #ffffff;
            --focus-ring: #ffff00;
        }

        /* ==========================================================================
           2. ESTILOS BASE E RESETS
           ========================================================================== */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: var(--font-main);
            font-size: var(--font-size-base);
            line-height: 1.6;
            background-color: var(--bg-color);
            color: var(--text-color);
            transition: background-color 0.3s, color 0.3s;
        }

        /* Foco Visível para Navegação via Teclado */
        a:focus, button:focus, input:focus {
            outline: 3px solid var(--focus-ring);
            outline-offset: 3px;
        }

        /* Skip Link para Acessibilidade */
        .skip-link {
            position: absolute;
            top: -40px;
            left: 0;
            background: var(--primary-color);
            color: white;
            padding: 8px 16px;
            z-index: 1000;
            transition: top 0.3s;
            text-decoration: none;
            font-weight: bold;
        }

        .skip-link:focus {
            top: 0;
        }

        /* ==========================================================================
           3. CABEÇALHO E NAVEGAÇÃO
           ========================================================================== */
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem 2rem;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        body.high-contrast header {
            background-color: #000;
            border-bottom: 2px solid #fff;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 1.5rem;
        }

        nav a {
            color: inherit;
            text-decoration: none;
            font-weight: 600;
            padding: 0.5rem;
            border-radius: 4px;
        }

        nav a:hover {
            text-decoration: underline;
        }

        .accessibility-toolbar {
            display: flex;
            gap: 0.5rem;
        }

        .btn-acc {
            background-color: var(--card-bg);
            color: var(--text-color);
            border: 1px solid var(--border-color);
            padding: 0.4rem 0.8rem;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 0.3rem;
        }

        /* ==========================================================================
           4. CONTEÚDO PRINCIPAL E SEÇÕES
           ========================================================================== */
        main {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }

        section {
            margin-bottom: 3rem;
            background: var(--card-bg);
            padding: 2rem;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
        }

        h1, h2, h3 {
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        body.high-contrast h1, 
        body.high-contrast h2, 
        body.high-contrast h3 {
            color: var(--primary-color);
        }

        .hero {
            text-align: center;
            padding: 3rem 1rem;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            border-radius: 12px;
            margin-bottom: 2rem;
        }

        body.high-contrast .hero {
            background: #000;
            border: 2px solid #fff;
        }

        .hero h1 {
            color: white;
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .grid-2 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 1.5rem;
        }

        /* ==========================================================================
           5. ESTILOS DEÓPTICA E ROBÓTICA
           ========================================================================== */
        .analogia-box {
            background-color: rgba(1, 186, 239, 0.1);
            border-left: 5px solid var(--secondary-color);
            padding: 1rem;
            margin-top: 1rem;
            border-radius: 0 8px 8px 0;
        }

        .fluxograma {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            margin-top: 1rem;
        }

        .passo-fluxo {
            background-color: var(--bg-color);
            border: 2px solid var(--primary-color);
            padding: 1rem;
            border-radius: 8px;
            position: relative;
        }

        .passo-fluxo::after {
            content: "↓";
            display: block;
            text-align: center;
            font-weight: bold;
            font-size: 1.5rem;
            color: var(--primary-color);
            margin-top: 0.5rem;
        }

        .passo-fluxo:last-child::after {
            content: "";
        }

        /* ==========================================================================
           6. SIMULADOR INTERATIVO DE AUTOMÇÃO
           ========================================================================== */
        .simulator {
            border: 2px dashed var(--primary-color);
            padding: 1.5rem;
            border-radius: 8px;
            background-color: var(--bg-color);
        }

        .sim-control {
            margin-bottom: 1.5rem;
        }

        .sim-control label {
            display: block;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }

        .sim-control input[type="range"] {
            width: 100%;
            height: 10px;
        }

        .status-display {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem;
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            font-weight: bold;
        }

        .indicator {
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background-color: #888;
            display: inline-block;
        }

        .indicator.active {
            background-color: #22c55e; /* Verde quando a bomba está ligada */
            box-shadow: 0 0 10px #22c55e;
        }

        /* ==========================================================================
           7. RODAPÉ
           ========================================================================== */
        footer {
            background-color: var(--primary-color);
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
        }

        body.high-contrast footer {
            background-color: #000;
            border-top: 2px solid #fff;
        }

        /* RESPONSIVIDADE PARA DISPOSITIVOS MÓVEIS */
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
                align-items: flex-start;
            }
            nav ul {
                flex-wrap: wrap;
                gap: 0.5rem;
            }
            .hero h1 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>

    <!-- Link de Acessibilidade para navegação via teclado -->
    <a href="#main-content" class="skip-link">Pular para o conteúdo principal</a>

    <!-- CABEÇALHO -->
    <header>
        <div class="nav-container">
            <div class="logo">
                <span aria-hidden="true">☀️🏊‍♂️</span>
                <span>EcoPiscina CEP</span>
            </div>
            <nav aria-label="Navegação Principal">
                <ul>
                    <li><a href="#optica">Óptica Aplicada</a></li>
                    <li><a href="#robotica">Automação</a></li>
                    <li><a href="#simulador">Simulador</a></li>
                    <li><a href="#acessibilidade">Acessibilidade</a></li>
                </ul>
            </nav>
            <div class="accessibility-toolbar" aria-label="Ferramentas de Acessibilidade">
                <button class="btn-acc" id="toggle-contrast" aria-label="Alternar Alto Contraste">
                    <span aria-hidden="true">👁️</span> Contraste
                </button>
                <button class="btn-acc" id="increase-font" aria-label="Aumentar tamanho do texto">A+</button>
                <button class="btn-acc" id="decrease-font" aria-label="Diminuir tamanho do texto">A-</button>
            </div>
        </div>
    </header>

    <!-- CONTEÚDO PRINCIPAL -->
    <main id="main-content">

        <!-- HERO SECTION -->
        <section class="hero">
            <h1>Automação e Aquecimento Sustentável para a Piscina Térmica do CEP</h1>
            <p>Uma solução integrada unindo Física Óptica, Programação, Robótica e Responsabilidade Social.</p>
        </section>

        <!-- SEÇÃO 1: ÓPTICA APLICADA E TECNOCIÊNCIA -->
        <section id="optica">
            <h2>1. Tecnociência e Óptica Aplicada</h2>
            <p>O projeto de aquecimento da piscina térmica utiliza princípios fundamentais da óptica geométrica e física para maximizar a captação de energia solar e sua conversão em energia térmica.</p>

            <div class="grid-2">
                <div>
                    <h3>Fenômenos Ópticos nos Coletores</h3>
                    <ul>
                        <li><strong>Absorção de Radiação:</strong> A superfície dos coletores é projetada com alto coeficiente de absorção para capturar a radiação infravermelha do Sol, minimizando perdas por reflexão.</li>
                        <li><strong>Reflexão Direcionada:</strong> Espelhos concentradores secundários utilizam a reflexão regular para direcionar feixes de luz extras aos tubos de passagem de água.</li>
                        <li><strong>Refração e Efeito Estufa:</strong> O vidro transparente sobre os tubos permite a passagem da luz visível (refração). Ao atingir a placa preta, a luz é reemitida como radiação infravermelha (calor), que não consegue atravessar o vidro de volta, retendo o calor.</li>
                    </ul>
                </div>
                <div>
                    <h3>Analogia: O Disco de Newton, a Câmara Escura e os Materiais</h3>
                    <div class="analogia-box">
                        <p><strong>O Disco de Newton e a Escolha da Cor Preta:</strong> O Disco de Newton demonstra que a luz branca é a sobreposição de todas as cores do espectro visível. Coletores solares utilizam superfícies na cor <em>preta fosca</em> exatamente pelo princípio oposto: o preto absorve todas as frequências da luz visível em vez de refletilas. Toda essa energia luminosa absorvida é convertida diretamente em agitação térmica (calor).</p>
                        <br>
                        <p><strong>A Câmara Escura e o Isolamento Térmico:</strong> O princípio da câmara escura envolve o confinamento e o controle da entrada da luz em um ambiente isolado. De forma análoga, a caixa do coletor solar funciona como uma câmara isolada que aprisiona a radiação térmica gerada, impedindo que o vento lave o calor capturado.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- SEÇÃO 2: ROBÓTICA E AUTOMÇÃO -->
        <section id="robotica">
            <h2>2. Arquitetura de Robótica e Programação</h2>
            <p>Para garantir a máxima eficiência energética sem desperdício de água aquecida ou energia elétrica, o sistema opera de forma autônoma através de um microcontrolador (ex: ESP32 ou Arduino).</p>

            <div class="grid-2">
                <div>
                    <h3>Componentes do Sistema (Hardware)</h3>
                    <ul>
                        <li><strong>Sensor de Temperatura 1 (Placa Solar):</strong> Termopar NTC/DS18B20 posicionado no coletor solar.</li>
                        <li><strong>Sensor de Temperatura 2 (Piscina):</strong> Sensor submerso na água da piscina do CEP.</li>
                        <li><strong>Atuador (Bomba de Circulação/Relé):</strong> Liga/desliga o fluxo de água entre a piscina e os coletores solares.</li>
                        <li><strong>Painel Elétrico Fotovoltaico:</strong> Fornece energia limpa para alimentar a automação e as bombas.</li>
                    </ul>
                </div>
                <div>
                    <h3>Fluxograma da Automação</h3>
                    <div class="fluxograma" role="region" aria-label="Passos do funcionamento da automação">
                        <div class="passo-fluxo">1. Sensores de temperatura realizam leituras em tempo real (Placa vs. Piscina).</div>
                        <div class="passo-fluxo">2. O código processa se: <code>Temp_Placa > Temp_Piscina + 5°C</code>.</div>
                        <div class="passo-fluxo">3. Se VERDADEIRO: Ativa o Relé/Bomba (a água circula e aquece).</div>
                        <div class="passo-fluxo">4. Se FALSO: Desativa a Bomba (evita que a água fria da placa resfrie a piscina).</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- SEÇÃO 3: SIMULADOR INTERATIVO -->
        <section id="simulador">
            <h2>3. Simulador Interativo do Sistema (Protótipo Funcional)</h2>
            <p>Abaixo, você pode interagir com a lógica do algoritmo que controlará a automação da piscina térmica do CEP.</p>

            <div class="simulator">
                <div class="sim-control">
                    <label id="lbl-temp-placa" for="temp-placa">Temperatura no Coletor Solar: <span id="val-placa">35</span>°C</label>
                    <input type="range" id="temp-placa" min="15" max="60" value="35" aria-labelledby="lbl-temp-placa">
                </div>

                <div class="sim-control">
                    <label id="lbl-temp-piscina" for="temp-piscina">Temperatura da Água da Piscina: <span id="val-piscina">25</span>°C</label>
                    <input type="range" id="temp-piscina" min="15" max="35" value="25" aria-labelledby="lbl-temp-piscina">
                </div>

                <div class="status-display" role="status" aria-live="polite">
                    <div>
                        Estado do Atuador: <span id="status-bomba-texto">Bomba Desligada</span>
                    </div>
                    <div id="indicador-bomba" class="indicator" aria-hidden="true"></div>
                </div>
            </div>
        </section>

        <!-- SEÇÃO 4: ACESSIBILIDADE DIGITAL E IMPACTO SOCIAL -->
        <section id="acessibilidade">
            <h2>4. Acessibilidade Digital, Inovação e Impacto Social</h2>
            
            <div class="grid-2">
                <div>
                    <h3>Inclusão e Acessibilidade Digital neste Site</h3>
                    <p>Este site foi desenvolvido aplicando as diretrizes globais do <strong>WCAG 2.1 (Web Content Accessibility Guidelines)</strong>:</p>
                    <ul style="margin-top: 0.5rem;">
                        <li><strong>Contraste Ajustável:</strong> Botão superior permite modo de alto contraste para pessoas com baixa visão ou daltonismo.</li>
                        <li><strong>Redimensionamento de Fonte:</strong> Usuários podem aumentar a fonte sem quebrar o layout.</li>
                        <li><strong>Navegação Inteiramente por Teclado:</strong> Foco bem visível e estrutura semântica HTML5.</li>
                        <li><strong>Leitores de Tela:</strong> Rótulos <code>aria-label</code> e marcações dinâmicas para fácil compreensão por pessoas cegas.</li>
                    </ul>
                </div>
                <div>
                    <h3>Inovação e Impacto Sustentável no CEP</h3>
                    <p>A implementação deste projeto integrador no Colégio Estadual do Paraná (CEP) traz benefícios diretos à comunidade escolar:</p>
                    <ul style="margin-top: 0.5rem;">
                        <li><strong>Uso Otimizado o Ano Todo:</strong> Permite o uso continuado da piscina nas aulas de educação física e projetos esportivos, mesmo no inverno.</li>
                        <li><strong>Redução da Pegada de Carbono:</strong> Substitui sistemas movidos a combustíveis fósseis ou aquecimento elétrico convencional por energia solar limpa.</li>
                        <li><strong>Conscientização Comunitária:</strong> O site funciona como um laboratório aberto, mostrando aos alunos como a física, a automação e a inclusão social se aplicam na prática.</li>
                    </ul>
                </div>
            </div>
        </section>

    </main>

    <!-- RODAPÉ -->
    <footer>
        <p>&copy; 2026 - Projeto Integrador: Automação da Piscina Térmica do CEP.</p>
        <p><small>Desenvolvido com foco em Óptica Aplicada, Robótica Sustentável e Acessibilidade Digital.</small></p>
    </footer>

    <!-- ==========================================================================
       8. JAVASCRIPT (LÓGICA E INTERATIVIDADE)
       ========================================================================== -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {

            /* --- Controles de Acessibilidade --- */
            const btnContrast = document.getElementById('toggle-contrast');
            const btnIncFont = document.getElementById('increase-font');
            const btnDecFont = document.getElementById('decrease-font');
            let currentFontSize = 100; // Porcentagem

            // Toggle de Alto Contraste
            btnContrast.addEventListener('click', () => {
                document.body.classList.toggle('high-contrast');
                const isContrast = document.body.classList.contains('high-contrast');
                btnContrast.setAttribute('aria-pressed', isContrast);
            });

            // Aumento/Diminuição de Fonte
            btnIncFont.addEventListener('click', () => {
                if (currentFontSize < 140) {
                    currentFontSize += 10;
                    document.documentElement.style.fontSize = `${currentFontSize}%`;
                }
            });

            btnDecFont.addEventListener('click', () => {
                if (currentFontSize > 80) {
                    currentFontSize -= 10;
                    document.documentElement.style.fontSize = `${currentFontSize}%`;
                }
            });

            /* --- Lógica do Simulador da Automação da Piscina --- */
            const sliderPlaca = document.getElementById('temp-placa');
            const sliderPiscina = document.getElementById('temp-piscina');
            const valPlaca = document.getElementById('val-placa');
            const valPiscina = document.getElementById('val-piscina');
            const statusTexto = document.getElementById('status-bomba-texto');
            const indicador = document.getElementById('indicador-bomba');

            function atualizarSimulacao() {
                const tempPlacaVal = parseInt(sliderPlaca.value, 10);
                const tempPiscinaVal = parseInt(sliderPiscina.value, 10);

                valPlaca.textContent = tempPlacaVal;
                valPiscina.textContent = tempPiscinaVal;

                // Lógica de Automação:
                // Se a temperatura do coletor solar for pelo menos 5°C superior à da piscina, liga a bomba.
                if (tempPlacaVal >= tempPiscinaVal + 5) {
                    statusTexto.textContent = "Bomba LIGADA (Aquecendo a piscina)";
                    statusTexto.style.color = "#22c55e";
                    indicador.classList.add('active');
                } else {
                    statusTexto.textContent = "Bomba DESLIGADA (Diferencial insuficiente de temperatura)";
                    statusTexto.style.color = "inherit";
                    indicador.classList.remove('active');
                }
            }

            sliderPlaca.addEventListener('input', atualizarSimulacao);
            sliderPiscina.addEventListener('input', atualizarSimulacao);

            // Inicialização
            atualizarSimulacao();
        });
    </script>
</body>
</html>
