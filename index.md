<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Conquistadores de Boros</title>
    <meta name="description" content="Fabula Ultima RPG inspirado em Final Fantasy Tactics">
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Crimson+Text:ital,wght@0,400;0,600;1,400&display=swap');
        
        :root {
            --primary-gold: #D4AF37;
            --deep-blue: #1a237e;
            --royal-purple: #4a148c;
            --dark-brown: #3e2723;
            --parchment: #f5f2e8;
            --shadow-dark: rgba(0,0,0,0.3);
            --gradient-royal: linear-gradient(135deg, var(--deep-blue), var(--royal-purple));
            --gradient-gold: linear-gradient(135deg, #FFD700, var(--primary-gold));
            --gradient-parchment: linear-gradient(135deg, #f5f2e8, #e8dcc0);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Crimson Text', serif;
            background: var(--gradient-royal);
            color: var(--parchment);
            overflow-x: hidden;
            min-height: 100vh;
            position: relative;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 80%, rgba(212, 175, 55, 0.1) 0%, transparent 50%),
                        radial-gradient(circle at 80% 20%, rgba(74, 20, 140, 0.1) 0%, transparent 50%);
            pointer-events: none;
            z-index: -1;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            text-align: center;
            padding: 60px 0;
            position: relative;
        }

        .logo {
            font-family: 'Cinzel', serif;
            font-size: 3.5rem;
            font-weight: 700;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px var(--shadow-dark);
            animation: glow 3s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 10px rgba(212, 175, 55, 0.5)); }
            to { filter: drop-shadow(0 0 20px rgba(212, 175, 55, 0.8)); }
        }

        .subtitle {
            font-size: 1.3rem;
            color: rgba(245, 242, 232, 0.9);
            font-style: italic;
            margin-bottom: 40px;
        }

        .game-description {
            background: var(--gradient-parchment);
            color: var(--dark-brown);
            padding: 40px;
            border-radius: 15px;
            margin: 40px 0;
            box-shadow: 0 10px 30px var(--shadow-dark);
            border: 3px solid var(--primary-gold);
            position: relative;
        }

        .game-description::before {
            content: '';
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            background: var(--gradient-gold);
            border-radius: 20px;
            z-index: -1;
            opacity: 0.3;
        }

        .game-description h2 {
            font-family: 'Cinzel', serif;
            font-size: 2rem;
            color: var(--royal-purple);
            margin-bottom: 20px;
            text-align: center;
        }

        .game-description p {
            font-size: 1.1rem;
            line-height: 1.8;
            text-align: justify;
        }

        .characters-section {
            margin: 60px 0;
        }

        .section-title {
            font-family: 'Cinzel', serif;
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .characters-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .character-card {
            background: var(--gradient-parchment);
            border-radius: 20px;
            padding: 25px;
            color: var(--dark-brown);
            box-shadow: 0 15px 35px var(--shadow-dark);
            border: 3px solid var(--primary-gold);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .character-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(212, 175, 55, 0.2), transparent);
            transition: left 0.5s;
        }

        .character-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 25px 50px var(--shadow-dark);
        }

        .character-card:hover::before {
            left: 100%;
        }

        .character-portrait {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            margin: 0 auto 20px;
            border: 4px solid var(--primary-gold);
            overflow: hidden;
            position: relative;
            box-shadow: 0 5px 15px var(--shadow-dark);
        }

        .character-portrait img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .character-name {
            font-family: 'Cinzel', serif;
            font-size: 1.5rem;
            font-weight: 600;
            text-align: center;
            color: var(--royal-purple);
            margin-bottom: 10px;
        }

        .character-class {
            text-align: center;
            font-weight: 600;
            color: var(--primary-gold);
            background: var(--deep-blue);
            padding: 5px 15px;
            border-radius: 20px;
            margin-bottom: 15px;
            display: inline-block;
            width: 100%;
        }

        .character-stats {
            margin: 20px 0;
        }

        .stat-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .stat-name {
            font-weight: 600;
            color: var(--dark-brown);
        }

        .stat-value {
            background: var(--deep-blue);
            color: white;
            padding: 2px 8px;
            border-radius: 10px;
            font-weight: 600;
        }

        .character-abilities {
            margin-top: 15px;
        }

        .abilities-title {
            font-weight: 600;
            color: var(--royal-purple);
            margin-bottom: 10px;
        }

        .ability {
            background: rgba(26, 35, 126, 0.1);
            padding: 8px 12px;
            border-radius: 8px;
            margin-bottom: 5px;
            border-left: 3px solid var(--primary-gold);
        }

        .game-features {
            background: rgba(245, 242, 232, 0.1);
            padding: 40px;
            border-radius: 15px;
            margin: 60px 0;
            border: 2px solid rgba(212, 175, 55, 0.3);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .feature {
            text-align: center;
            padding: 20px;
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            color: var(--primary-gold);
        }

        .feature h3 {
            font-family: 'Cinzel', serif;
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--primary-gold);
        }

        footer {
            text-align: center;
            padding: 40px 0;
            margin-top: 60px;
            border-top: 2px solid rgba(212, 175, 55, 0.3);
        }

        .cta-button {
            background: var(--gradient-gold);
            color: var(--dark-brown);
            padding: 15px 40px;
            border: none;
            border-radius: 30px;
            font-family: 'Cinzel', serif;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px var(--shadow-dark);
            margin: 20px 10px;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px var(--shadow-dark);
            filter: brightness(1.1);
        }

        @media (max-width: 768px) {
            .logo {
                font-size: 2.5rem;
            }
            
            .characters-grid {
                grid-template-columns: 1fr;
            }
            
            .game-description {
                padding: 25px;
            }
        }

        .floating-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: var(--primary-gold);
            border-radius: 50%;
            animation: float 6s infinite ease-in-out;
            opacity: 0.7;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0; }
            50% { transform: translateY(-100px) rotate(180deg); opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="floating-particles" id="particles"></div>
    
    <div class="container">
        <header>
            <h1 class="logo">A origem de todo mal</h1>
            <p class="subtitle">Os conquistadores de Boros</p>
        </header>

        <section class="game-description">
            <h2>O Reino Precisa de Heróis</h2>
            <p>
                Em um mundo onde a magia e a estratégia se encontram, quatro heróis únicos devem unir suas forças para salvar o reino de Astoria. 
                Inspirado nos clássicos RPGs táticos, este jogo combina narrativa envolvente com combate estratégico em turnos. 
                Cada decisão importa, cada movimento pode determinar o destino de seu esquadrão. 
                Explore masmorras antigas, desvende mistérios arcanos e domine o campo de batalha com táticas precisas.
            </p>
        </section>

        <section class="characters-section">
            <h2 class="section-title">Os Quatro Heróis</h2>
            
            <div class="characters-grid">
                <div class="character-card">
                    <div class="character-portrait">
                        <img src="https://images.unsplash.com/photo-1578662996442-48f60103fc96?w=300&h=300&fit=crop&crop=face" alt="Sir Gareth" onerror="this.src='https://via.placeholder.com/300x300/1a237e/D4AF37?text=Knight'">
                    </div>
                    <h3 class="character-name">Sir Gareth</h3>
                    <div class="character-class">Cavaleiro Templário</div>
                    
                    <div class="character-stats">
                        <div class="stat-bar">
                            <span class="stat-name">Força</span>
                            <span class="stat-value">95</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Defesa</span>
                            <span class="stat-value">90</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Velocidade</span>
                            <span class="stat-value">60</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Mana</span>
                            <span class="stat-value">40</span>
                        </div>
                    </div>
                    
                    <div class="character-abilities">
                        <div class="abilities-title">Habilidades Especiais:</div>
                        <div class="ability">🛡️ Escudo Sagrado - Protege aliados</div>
                        <div class="ability">⚔️ Golpe Divino - Dano sagrado massivo</div>
                        <div class="ability">✨ Aura de Coragem - Aumenta moral da equipe</div>
                    </div>
                </div>

                <div class="character-card">
                    <div class="character-portrait">
                        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=300&h=300&fit=crop&crop=face" alt="Lyra Moonwhisper" onerror="this.src='https://via.placeholder.com/300x300/4a148c/D4AF37?text=Mage'">
                    </div>
                    <h3 class="character-name">Lyra Moonwhisper</h3>
                    <div class="character-class">Arquimaga Elemental</div>
                    
                    <div class="character-stats">
                        <div class="stat-bar">
                            <span class="stat-name">Força</span>
                            <span class="stat-value">35</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Defesa</span>
                            <span class="stat-value">45</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Velocidade</span>
                            <span class="stat-value">75</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Mana</span>
                            <span class="stat-value">100</span>
                        </div>
                    </div>
                    
                    <div class="character-abilities">
                        <div class="abilities-title">Habilidades Especiais:</div>
                        <div class="ability">🔥 Meteoro - Devastação em área</div>
                        <div class="ability">❄️ Nevasca Glacial - Congela inimigos</div>
                        <div class="ability">⚡ Tempestade Arcana - Múltiplos raios</div>
                    </div>
                </div>

                <div class="character-card">
                    <div class="character-portrait">
                        <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=300&h=300&fit=crop&crop=face" alt="Thane Swiftarrow" onerror="this.src='https://via.placeholder.com/300x300/2e7d32/D4AF37?text=Archer'">
                    </div>
                    <h3 class="character-name">Thane Swiftarrow</h3>
                    <div class="character-class">Batedor Élfico</div>
                    
                    <div class="character-stats">
                        <div class="stat-bar">
                            <span class="stat-name">Força</span>
                            <span class="stat-value">70</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Defesa</span>
                            <span class="stat-value">55</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Velocidade</span>
                            <span class="stat-value">95</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Mana</span>
                            <span class="stat-value">60</span>
                        </div>
                    </div>
                    
                    <div class="character-abilities">
                        <div class="abilities-title">Habilidades Especiais:</div>
                        <div class="ability">🏹 Tiro Certeiro - Nunca erra o alvo</div>
                        <div class="ability">🌿 Camuflagem Natural - Torna-se invisível</div>
                        <div class="ability">💨 Rajada de Flechas - Múltiplos ataques</div>
                    </div>
                </div>

                <div class="character-card">
                    <div class="character-portrait">
                        <img src="https://images.unsplash.com/photo-1494790108755-2616c17ca6dd?w=300&h=300&fit=crop&crop=face" alt="Seraphina" onerror="this.src='https://via.placeholder.com/300x300/f57c00/D4AF37?text=Healer'">
                    </div>
                    <h3 class="character-name">Seraphina</h3>
                    <div class="character-class">Clériga da Luz</div>
                    
                    <div class="character-stats">
                        <div class="stat-bar">
                            <span class="stat-name">Força</span>
                            <span class="stat-value">45</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Defesa</span>
                            <span class="stat-value">70</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Velocidade</span>
                            <span class="stat-value">65</span>
                        </div>
                        <div class="stat-bar">
                            <span class="stat-name">Mana</span>
                            <span class="stat-value">90</span>
                        </div>
                    </div>
                    
                    <div class="character-abilities">
                        <div class="abilities-title">Habilidades Especiais:</div>
                        <div class="ability">💫 Cura Divina - Restaura HP totalmente</div>
                        <div class="ability">🌟 Ressurreição - Revive aliados caídos</div>
                        <div class="ability">⭐ Bênção Celestial - Buffs permanentes</div>
                    </div>
                </div>
            </div>
        </section>

        <section class="game-features">
            <h2 class="section-title">Características do Jogo</h2>
            
            <div class="features-grid">
                <div class="feature">
                    <div class="feature-icon">⚔️</div>
                    <h3>Combate Tático</h3>
                    <p>Sistema de combate em turnos com posicionamento estratégico e terrain effects</p>
                </div>
                
                <div class="feature">
                    <div class="feature-icon">📚</div>
                    <h3>História Épica</h3>
                    <p>Narrativa envolvente com escolhas que afetam o desenrolar da aventura</p>
                </div>
                
                <div class="feature">
                    <div class="feature-icon">🎯</div>
                    <h3>Classes Únicas</h3>
                    <p>Cada personagem possui habilidades e progressão de classe exclusivas</p>
                </div>
                
                <div class="feature">
                    <div class="feature-icon">🏰</div>
                    <h3>Mundo Vasto</h3>
                    <p>Explore reinos místicos, masmorras antigas e cidades prósperas</p>
                </div>
            </div>
        </section>

        <footer>
            <button class="cta-button" onclick="startGame()">Iniciar Aventura</button>
            <button class="cta-button" onclick="showTrailer()">Ver Trailer</button>
            <p style="margin-top: 30px; opacity: 0.8;">
                © 2024 Legends of Astoria. Embarque nesta jornada épica.
            </p>
        </footer>
    </div>

    <script>
        // Função para criar partículas flutuantes
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 20;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 4 + 4) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Função para iniciar o jogo (placeholder)
        function startGame() {
            alert('🎮 Prepare-se para uma aventura épica! O jogo será lançado em breve...');
            
            // Adiciona efeito visual
            document.body.style.animation = 'glow 0.5s ease-in-out';
            setTimeout(() => {
                document.body.style.animation = '';
            }, 500);
        }

        // Função para mostrar trailer (placeholder)
        function showTrailer() {
            alert('🎬 Trailer épico em desenvolvimento! Fique ligado nas redes sociais...');
        }

        // Efeito de hover nos cards dos personagens
        function addCardEffects() {
            const cards = document.querySelectorAll('.character-card');
            
            cards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-10px) scale(1.02)';
                    this.style.boxShadow = '0 25px 50px rgba(0,0,0,0.3)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                    this.style.boxShadow = '0 15px 35px rgba(0,0,0,0.3)';
                });

                // Efeito de click
                card.addEventListener('click', function() {
                    const characterName = this.querySelector('.character-name').textContent;
                    alert(`⚡ ${characterName} está pronto para a batalha!`);
                });
            });
        }

        // Animação suave de scroll
        function smoothScrollToSection(targetId) {
            const target = document.getElementById(targetId);
            if (target) {
                target.scrollIntoView({
                    behavior: 'smooth',
                    block: 'start'
                });
            }
        }

        // Efeito de digitação para o título
        function typeWriterEffect() {
            const title = document.querySelector('.logo');
            const text = title.textContent;
            title.textContent = '';
            
            let i = 0;
            const typeInterval = setInterval(() => {
                if (i < text.length) {
                    title.textContent += text.charAt(i);
                    i++;
                } else {
                    clearInterval(typeInterval);
                }
            }, 100);
        }

        // Detecta scroll para animações
        function handleScroll() {
            const cards = document.querySelectorAll('.character-card');
            const triggerBottom = window.innerHeight / 5 * 4;
            
            cards.forEach(card => {
                const cardTop = card.getBoundingClientRect().top;
                
                if (cardTop < triggerBottom) {
                    card.style.opacity = '1';
                    card.style.transform = 'translateY(0)';
                } else {
                    card.style.opacity = '0';
                    card.style.transform = 'translateY(50px)';
                }
            });
        }

        // Inicialização quando a página carrega
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            addCardEffects();
            
            // Adiciona transição inicial aos cards
            const cards = document.querySelectorAll('.character-card');
            cards.forEach(card => {
                card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            });
            
            // Event listener para scroll
            window.addEventListener('scroll', handleScroll);
            handleScroll(); // Chama uma vez para aplicar estado inicial
            
            // Efeito de entrada suave
            document.body.style.opacity = '0';
            setTimeout(() => {
                document.body.style.transition = 'opacity 1s ease';
                document.body.style.opacity = '1';
            }, 100);
        });

        // Função para alternar tema (Easter egg)
        let clickCount = 0;
        document.querySelector('.logo').addEventListener('click', function() {
            clickCount++;
            if (clickCount === 5) {
                document.body.style.filter = 'hue-rotate(180deg)';
                alert('🌈 Modo mágico ativado!');
                setTimeout(() => {
                    document.body.style.filter = '';
                    clickCount = 0;
                }, 3000);
            }
        });
    </script>
</body>
</html>
