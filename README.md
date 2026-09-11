# site-acessibilidade <!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Guia Digital Sênior - Navegue com Segurança e Tranquilidade</title>
  <!-- Importando Fontes Amigáveis do Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
  
  <style>
    /* ==========================================================
       1. VARIÁVEIS DE ESTILO E TEMA (TOM PASTEL E ALTO CONTRASTE)
       ========================================================== */
    :root {
      /* Nova Paleta Rosa Pastel e Suave */
      --bg-color: #fdf2f8; /* Rosa bem clarinho de fundo */
      --card-bg: #ffffff;
      --text-color: #331a1a; /* Marrom escuro para melhor leitura no rosa */
      --text-muted: #6b4f4f;
      --primary-color: #d1629d; /* Rosa principal suave mas visível */
      --primary-hover: #b94f86; /* Rosa mais escuro para hover */
      --accent-color: #8c71b6; /* Roxo suave para acentos */
      --warning-bg: #fffbf0;
      --warning-border: #f9d87d;
      --warning-text: #8c5d12;
      --success-bg: #ecfdf5;
      --success-border: #82e0b5;
      --success-text: #065f46;
      --danger-bg: #fff1f2;
      --danger-border: #fca5a5;
      --danger-text: #991b1b;
      --border-color: #e9cedb; /* Rosa pastel suave para bordas */
      --shadow: 0 6px 15px rgba(209, 98, 157, 0.1); /* Sombra com toque de rosa */
      
      /* Tipografia */
      --font-heading: 'Montserrat', sans-serif;
      --font-body: 'Open Sans', sans-serif;
      --base-font-size: 19px;
      --focus-ring: 4px solid #f9d87d;
    }

    /* Alternador de Alto Contraste (via Checkbox CSS) - Mantido */
    #toggle-contrast:checked ~ .app-container {
      --bg-color: #000000;
      --card-bg: #121212;
      --text-color: #ffffff;
      --text-muted: #e2e8f0;
      --primary-color: #ffff00;
      --primary-hover: #e6e600;
      --accent-color: #00ffff;
      --warning-bg: #332b00;
      --warning-border: #ffff00;
      --warning-text: #ffffff;
      --success-bg: #003311;
      --success-border: #00ff66;
      --success-text: #ffffff;
      --danger-bg: #330000;
      --danger-border: #ff3333;
      --danger-text: #ffffff;
      --border-color: #ffffff;
      --shadow: 0 0 0 2px #ffffff;
    }

    /* Alternador de Texto Ampliado (via Checkbox CSS) - Mantido */
    #toggle-text-size:checked ~ .app-container {
      --base-font-size: 24px;
    }

    /* ==========================================================
       2. REGRAS GERAIS E TIPOGRAFIA
       ========================================================== */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: var(--font-body);
      background-color: var(--bg-color);
      color: var(--text-color);
      font-size: var(--base-font-size);
      line-height: 1.7;
      transition: background-color 0.3s ease, color 0.3s ease, font-size 0.2s ease;
    }

    h1, h2, h3, .summary-title {
      font-family: var(--font-heading);
      font-weight: 700;
    }

    /* Ocultar checkboxes utilitários */
    .state-toggle {
      display: none;
    }

    /* ==========================================================
       3. BARRA DE ACESSIBILIDADE FIXA NO TOPO
       ========================================================== */
    .accessibility-bar {
      background-color: #2d1822; /* Marrom bem escuro com toque de rosa */
      color: #ffffff;
      padding: 12px 20px;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 15px;
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: 0 3px 10px rgba(0,0,0,0.2);
    }

    .accessibility-title {
      font-size: 1.1rem;
      font-family: var(--font-heading);
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .accessibility-controls {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
    }

    .btn-access {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background-color: #523741;
      color: #ffffff;
      padding: 10px 18px;
      border-radius: 20px; /* Bordas mais arredondadas */
      font-size: 0.95rem;
      font-weight: bold;
      cursor: pointer;
      border: 2px solid #7c5866;
      user-select: none;
      transition: all 0.2s;
    }

    .btn-access:hover, .btn-access:focus {
      background-color: #7c5866;
      border-color: #d1629d;
      outline: var(--focus-ring);
    }

    #toggle-contrast:checked ~ .accessibility-bar .btn-contrast,
    #toggle-text-size:checked ~ .accessibility-bar .btn-text-size {
      background-color: #d1629d;
      color: #ffffff;
      border-color: #ffffff;
    }

    /* ==========================================================
       4. ESTRUTURA E CONTAINER PRINCIPAL
       ========================================================== */
    .app-container {
      max-width: 960px;
      margin: 0 auto;
      padding: 30px 20px;
    }

    header.main-header {
      background-color: var(--card-bg);
      border: 2px solid var(--border-color);
      border-radius: 20px; /* Mais arredondado */
      padding: 40px 30px;
      margin-bottom: 30px;
      text-align: center;
      box-shadow: var(--shadow);
    }

    header.main-header h1 {
      font-size: 2.3rem;
      color: var(--primary-color);
      margin-bottom: 15px;
      line-height: 1.2;
    }

    header.main-header p {
      color: var(--text-muted);
      font-size: 1.2rem;
      max-width: 750px;
      margin: 0 auto;
    }

    /* Badge explicativo */
    .badge-info {
      display: inline-block;
      background-color: var(--warning-bg);
      color: var(--warning-text);
      border: 2px solid var(--warning-border);
      padding: 10px 20px;
      border-radius: 50px;
      font-weight: bold;
      margin-top: 20px;
      font-size: 1rem;
    }

    /* ==========================================================
       5. NAVEGAÇÃO DE TÓPICOS (MENU RÁPIDO)
       ========================================================== */
    .quick-nav {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
      margin-bottom: 40px;
    }

    .nav-card {
      background-color: var(--card-bg);
      border: 2px solid var(--border-color);
      border-radius: 15px;
      padding: 20px;
      text-align: center;
      text-decoration: none;
      color: var(--text-color);
      font-weight: 600;
      font-family: var(--font-heading);
      box-shadow: var(--shadow);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 12px;
      transition: transform 0.2s, border-color 0.2s, background-color 0.2s;
    }

    .nav-card:hover, .nav-card:focus {
      transform: translateY(-4px);
      border-color: var(--primary-color);
      background-color: #fdf2f8; /* Leve rosa ao passar o mouse */
      outline: var(--focus-ring);
    }

    /* Usando ícones grandes como imagens simbólicas */
    .nav-card .topic-image-placeholder {
      font-size: 3.5rem;
      margin-bottom: 5px;
    }

    /* ==========================================================
       6. SEÇÕES DE DICAS (ACCORDION USANDO <details>)
       ========================================================== */
    .section-title {
      font-size: 1.8rem;
      margin-bottom: 20px;
      color: var(--primary-color);
      display: flex;
      align-items: center;
      gap: 12px;
      padding-bottom: 10px;
    }

    .topic-card {
      background-color: var(--card-bg);
      border: 2px solid var(--border-color);
      border-radius: 18px;
      margin-bottom: 22px;
      box-shadow: var(--shadow);
      overflow: hidden;
    }

    details {
      width: 100%;
    }

    summary {
      padding: 24px 30px;
      font-size: 1.35rem;
      font-weight: 600;
      cursor: pointer;
      list-style: none;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background-color: var(--card-bg);
      color: var(--text-color);
      user-select: none;
    }

    summary::-webkit-details-marker {
      display: none;
    }

    summary:hover, summary:focus {
      background-color: rgba(209, 98, 157, 0.05); /* Toque rosa pastel */
      outline: var(--focus-ring);
    }

    summary .summary-title {
      display: flex;
      align-items: center;
      gap: 16px;
    }

    summary .chevron {
      font-size: 1.5rem;
      color: var(--primary-color);
      transition: transform 0.3s ease;
    }

    details[open] summary .chevron {
      transform: rotate(180deg);
    }

    details[open] summary {
      border-bottom: 2px solid var(--border-color);
      background-color: rgba(209, 98, 157, 0.08); /* Rosa mais visível */
    }

    .card-content {
      padding: 30px;
    }

    /* Placeholder para imagem dentro do conteúdo */
    .content-image-section {
      text-align: center;
      margin-bottom: 20px;
      padding: 15px;
      background-color: #fdf2f8;
      border-radius: 10px;
      font-size: 5rem; /* Ícone bem grande */
      color: var(--primary-color);
      border: 2px solid var(--border-color);
    }

    /* Caixa de Alerta dentro das dicas */
    .alert-box {
      border-radius: 12px;
      padding: 18px 24px;
      margin: 18px 0;
      border-left: 6px solid;
    }

    .alert-danger {
      background-color: var(--danger-bg);
      border-color: var(--danger-border);
      color: var(--danger-text);
    }

    .alert-warning {
      background-color: var(--warning-bg);
      border-color: var(--warning-border);
      color: var(--warning-text);
    }

    .alert-success {
      background-color: var(--success-bg);
      border-color: var(--success-border);
      color: var(--success-text);
    }

    .alert-box strong {
      display: block;
      font-size: 1.15rem;
      margin-bottom: 8px;
    }

    .step-list {
      margin-left: 25px;
      margin-top: 15px;
    }

    .step-list li {
      margin-bottom: 15px;
      padding-left: 5px;
    }

    /* ==========================================================
       7. QUIZ INTERATIVO (SEM JAVASCRIPT - PURE CSS)
       ========================================================== */
    .quiz-section {
      background-color: var(--card-bg);
      border: 4px solid var(--accent-color); /* Roxo pastel para o quiz */
      border-radius: 20px;
      padding: 35px;
      margin-top: 50px;
      margin-bottom: 50px;
      box-shadow: var(--shadow);
    }

    .quiz-header {
      text-align: center;
      margin-bottom: 28px;
    }

    .quiz-header h2 {
      font-size: 1.8rem;
      color: var(--accent-color);
    }

    .quiz-question {
      background-color: #f9f6fd; /* Fundo roxo bem clarinho */
      border: 2px solid var(--accent-color);
      border-radius: 15px;
      padding: 25px;
      margin-bottom: 25px;
    }

    .quiz-question p.question-text {
      font-weight: 700;
      font-family: var(--font-heading);
      font-size: 1.25rem;
      margin-bottom: 18px;
    }

    .quiz-options {
      display: flex;
      flex-direction: column;
      gap: 14px;
    }

    /* Esconder o rádio real para criar botões grandes acessíveis */
    .quiz-options input[type="radio"] {
      position: absolute;
      opacity: 0;
      width: 0;
      height: 0;
    }

    .quiz-label {
      display: block;
      background-color: var(--card-bg);
      border: 2px solid var(--border-color);
      border-radius: 12px;
      padding: 16px 20px;
      cursor: pointer;
      font-weight: 600;
      transition: all 0.2s;
    }

    .quiz-label:hover {
      border-color: var(--accent-color);
      background-color: #f9f6fd;
    }

    .quiz-options input[type="radio"]:focus + .quiz-label {
      outline: var(--focus-ring);
    }

    /* Resposta Feedback via CSS */
    .feedback {
      display: none;
      margin-top: 18px;
      padding: 16px 20px;
      border-radius: 10px;
      font-weight: bold;
    }

    /* Seletores CSS para exibir resposta correta/incorreta */
    #q1-correct:checked ~ .feedback-correct {
      display: block;
      background-color: var(--success-bg);
      color: var(--success-text);
      border: 2px solid var(--success-border);
    }

    #q1-wrong1:checked ~ .feedback-wrong1,
    #q1-wrong2:checked ~ .feedback-wrong2 {
      display: block;
      background-color: var(--danger-bg);
      color: var(--danger-text);
      border: 2px solid var(--danger-border);
    }

    #q1-correct:checked + .quiz-label {
      border-color: var(--success-border);
      background-color: var(--success-bg);
    }
    #q1-wrong1:checked + .quiz-label,
    #q1-wrong2:checked + .quiz-label {
      border-color: var(--danger-border);
      background-color: var(--danger-bg);
    }

    /* ==========================================================
       8. SEÇÃO DE CONTATOS E EMERGÊNCIA
       ========================================================== */
    .emergency-section {
      background-color: var(--danger-bg);
      border: 3px solid var(--danger-border);
      border-radius: 20px;
      padding: 30px;
      color: var(--danger-text);
      margin-bottom: 50px;
    }

    .emergency-section h2 {
      font-size: 1.6rem;
      margin-bottom: 15px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .emergency-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 20px;
      margin-top: 20px;
    }

    .emergency-card {
      background-color: var(--card-bg);
      color: var(--text-color);
      border: 2px solid var(--danger-border);
      padding: 20px;
      border-radius: 12px;
      text-align: center;
      transition: transform 0.2s;
    }

    .emergency-card:hover {
      transform: scale(1.03);
    }

    .emergency-card strong {
      display: block;
      font-size: 1.15rem;
      margin-bottom: 6px;
      font-family: var(--font-heading);
    }

    .emergency-card span {
      font-size: 1.6rem;
      font-weight: bold;
      color: var(--danger-text); /* Vermelho escuro */
    }

    /* ==========================================================
       9. RODAPÉ
       ========================================================== */
    footer {
      text-align: center;
      padding: 40px 20px;
      border-top: 2px solid var(--border-color);
      color: var(--text-muted);
      margin-top: 50px;
    }

    /* Responsividade */
    @media (max-width: 600px) {
      .accessibility-bar {
        flex-direction: column;
        align-items: stretch;
      }
      .accessibility-controls {
        justify-content: space-between;
      }
      header.main-header h1 {
        font-size: 1.9rem;
      }
      summary {
        font-size: 1.2rem;
        padding: 20px;
      }
      .nav-card {
        padding: 15px;
      }
      .nav-card .topic-image-placeholder {
        font-size: 2.8rem;
      }
    }
  </style>
</head>
<body>

  <!-- CONTROLES ACESSÍVEIS COM CHECKBOX (CSS PURO) -->
  <input type="checkbox" id="toggle-contrast" class="state-toggle" aria-label="Alternar Alto Contraste">
  <input type="checkbox" id="toggle-text-size" class="state-toggle" aria-label="Alternar Tamanho do Texto">

  <!-- BARRA DE ACESSIBILIDADE FIXA NO TOPO -->
  <div class="accessibility-bar" role="region" aria-label="Controles de Acessibilidade">
    <div class="accessibility-title">
      <span>🛡️ Guia Digital Rosa Sênior</span>
    </div>
    <div class="accessibility-controls">
      <label for="toggle-text-size" class="btn-access btn-text-size" tabindex="0" role="button" aria-pressed="false">
        <span>🔍</span> Texto Maior
      </label>
      <label for="toggle-contrast" class="btn-access btn-contrast" tabindex="0" role="button" aria-pressed="false">
        <span>👁️</span> Alto Contraste
      </label>
    </div>
  </div>

  <div class="app-container">

    <!-- CABEÇALHO PRINCIPAL -->
    <header class="main-header">
      <h1>Sua Segurança Digital com Tranquilidade</h1>
      <p>Aprenda a navegar na internet, usar o WhatsApp e o banco no celular sem medo de golpes. Dicas fáceis e diretas.</p>
      <div class="badge-info">
        💡 Clique ou toque nos assuntos abaixo para ver as dicas.
      </div>
    </header>

    <!-- NAVEGAÇÃO RÁPIDA (Com "Imagens" Simbólicas) -->
    <nav class="quick-nav" aria-label="Menu Rápido de Tópicos">
      <a href="#whatsapp" class="nav-card">
        <div class="topic-image-placeholder">📱</div> <!-- Imagem simbólica -->
        <span>Golpes no WhatsApp</span>
      </a>
      <a href="#banco" class="nav-card">
        <div class="topic-image-placeholder">🏛️</div> <!-- Imagem simbólica -->
        <span>Banco e Ligações</span>
      </a>
      <a href="#senhas" class="nav-card">
        <div class="topic-image-placeholder">🔐</div> <!-- Imagem simbólica -->
        <span>Criar Senhas Seguras</span>
      </a>
      <a href="#links" class="nav-card">
        <div class="topic-image-placeholder">✉️</div> <!-- Imagem simbólica -->
        <span>Links e Mensagens</span>
      </a>
    </nav>

    <!-- SEÇÃO DE DICAS PRINCIPAIS -->
    <main>
      <h2 class="section-title">📘 Suas Dicas de Proteção</h2>

      <!-- TÓPICO 1: WHATSAPP -->
      <article class="topic-card" id="whatsapp">
        <details open>
          <summary>
            <div class="summary-title">
              <span style="font-size: 1.8rem;">📱</span>
              <span>1. Como evitar Golpes no WhatsApp?</span>
            </div>
            <span class="chevron">▼</span>
          </summary>
          <div class="card-content">
            <!-- Imagem interna da seção -->
            <div class="content-image-section">👤</div>
            
            <p>O WhatsApp é a forma mais comum de golpistas tentarem te enganar. Eles tentam se passar por pessoas conhecidas para pedir dinheiro.</p>

            <div class="alert-box alert-danger">
              <strong>🚨 O Golpe do "Falso Parente" (Filho/Neto):</strong>
              <p>Uma pessoa te manda mensagem com um número novo, mas usa a foto de um parente seu. Ela diz que mudou de número e que precisa urgentemente de um Pix para pagar uma conta ou problema.</p>
            </div>

            <div class="alert-box alert-success">
              <strong>✅ O que fazer para não cair:</strong>
              <ul class="step-list">
                <li><strong>Nunca envie dinheiro na hora!</strong></li>
                <li>Tente ligar para o número <strong>antigo</strong> do seu parente por voz ou vídeo.</li>
                <li>Fale com outra pessoa da família para confirmar se a história é verdadeira.</li>
                <li>Nunca faça Pix para contas com nomes de pessoas que você não conhece.</li>
              </ul>
            </div>
          </div>
        </details>
      </article>

      <!-- TÓPICO 2: BANCOS E LIGAÇÕES -->
      <article class="topic-card" id="banco">
        <details>
          <summary>
            <div class="summary-title">
              <span style="font-size: 1.8rem;">🏛️</span>
              <span>2. Falsas Ligações de Gerentes de Banco</span>
            </div>
            <span class="chevron">▼</span>
          </summary>
          <div class="card-content">
            <!-- Imagem interna da seção -->
            <div class="content-image-section">📞</div>

            <p>Os golpistas conseguem falsificar o número de telefone do banco e são muito educados e convincentes ao falar.</p>

            <div class="alert-box alert-danger">
              <strong>🚨 O que eles dizem no golpe:</strong>
              <p>Eles ligam dizendo que houve uma "compra suspeita de valor alto" no seu cartão ou uma tentativa de invasão na conta. Eles pedem para você confirmar sua senha ou fazer um Pix de teste.</p>
            </div>

            <div class="alert-box alert-success">
              <strong>✅ Regras de Ouro de Segurança:</strong>
              <ul class="step-list">
                <li><strong>O banco NUNCA liga pedindo sua senha por telefone.</strong></li>
                <li><strong>O banco NUNCA pede para você fazer Pix</strong> para cancelar compras ou "proteger" sua conta.</li>
                <li>Se receber essa ligação, <strong>desligue o telefone na hora!</strong></li>
                <li>Ligue você mesmo para o número oficial que está atrás do seu cartão físico para confirmar.</li>
              </ul>
            </div>
          </div>
        </details>
      </article>

      <!-- TÓPICO 3: SENHAS SEGURAS -->
      <article class="topic-card" id="senhas">
        <details>
          <summary>
            <div class="summary-title">
              <span style="font-size: 1.8rem;">🔐</span>
              <span>3. Como criar e cuidar de Senhas Fortes?</span>
            </div>
            <span class="chevron">▼</span>
          </summary>
          <div class="card-content">
            <!-- Imagem interna da seção -->
            <div class="content-image-section">📝</div>

            <p>Usar senhas iguais para tudo ou datas de nascimento conhecidas facilita a ação de hackers.</p>

            <div class="alert-box alert-warning">
              <strong>💡 Dica simples para senhas fortes e fáceis:</strong>
              <p>Crie uma frase misturando palavras, números e símbolos. Exemplo: <code>GostoDeCafe@2025!</code>. É fácil para você lembrar e difícil para outros adivinharem.</p>
            </div>

            <ul class="step-list">
              <li><strong>Não anote senhas em papéis soltos</strong> ou na capinha do celular.</li>
              <li>Se precisar anotar, guarde o caderno num local seguro e trancado em casa.</li>
              <li>Nunca compartilhe suas senhas com estranhos, mesmo que digam ser de confiança.</li>
            </ul>
          </div>
        </details>
      </article>

      <!-- TÓPICO 4: LINKS E SMS -->
      <article class="topic-card" id="links">
        <details>
          <summary>
            <div class="summary-title">
              <span style="font-size: 1.8rem;">✉️</span>
              <span>4. Cuidados com Links e Mensagens de Texto</span>
            </div>
            <span class="chevron">▼</span>
          </summary>
          <div class="card-content">
            <!-- Imagem interna da seção -->
            <div class="content-image-section">🖱️</div>

            <p>Você pode receber mensagens de texto (SMS) ou no WhatsApp de números estranhos com promessas ou ameaças urgentes.</p>

            <div class="alert-box alert-danger">
              <strong>⚠️ Atenção:</strong> Quase sempre esses links levam para sites falsos que tentam roubar seus dados do cartão ou instalar vírus.
            </div>

            <div class="alert-box alert-success">
              <strong>✅ Como agir com segurança:</strong>
              <ul class="step-list">
                <li><strong>NÃO CLIQUE</strong> em links azuis de mensagens de desconhecidos.</li>
                <li>Apague mensagens sobre prêmios de sorteios que você não participou ou encomendas que você não fez.</li>
              </ul>
            </div>
          </div>
        </details>
      </article>

      <!-- QUIZ INTERATIVO (Com Visual Roxo Pastel) -->
      <section class="quiz-section">
        <div class="quiz-header">
          <h2>🎯 Teste Seu Conhecimento!</h2>
          <p>Selecione a resposta correta para aprender mais.</p>
        </div>

        <div class="quiz-question">
          <p class="question-text">Pergunta: Você recebe um WhatsApp do número novo do seu filho pedindo um Pix urgente de R$ 300,00 para pagar uma conta. O que você faz?</p>

          <div class="quiz-options">
            <input type="radio" id="q1-wrong1" name="quiz1">
            <label for="q1-wrong1" class="quiz-label">A) Faço o Pix na hora para ajudar meu filho.</label>
            <div class="feedback feedback-wrong1">
              ❌ Incorreto! Isso pode ser um golpe. Nunca mande dinheiro sem confirmar por voz antes.
            </div>

            <input type="radio" id="q1-correct" name="quiz1">
            <label for="q1-correct" class="quiz-label">B) Ligo para o número antigo dele por voz ou vídeo para confirmar.</label>
            <div class="feedback feedback-correct">
              🎉 EXCELENTE! Resposta Correta! Confirmar por voz para o número que você já conhece é a ação mais segura.
            </div>

            <input type="radio" id="q1-wrong2" name="quiz1">
            <label for="q1-wrong2" class="quiz-label">C) Respondo pedindo os dados do cartão de crédito.</label>
            <div class="feedback feedback-wrong2">
              ❌ Incorreto! Nunca envie dados bancários por mensagem.
            </div>
          </div>
        </div>
      </section>

      <!-- SEÇÃO DE EMERGÊNCIA (Vermelho Pastel) -->
      <section class="emergency-section">
        <h2>🚑 Caiu em um golpe? Mantenha a calma e aja!</h2>
        <p>Se você suspeita que foi vítima de uma fraude, siga estes passos rapidamente:</p>

        <div class="emergency-grid">
          <div class="emergency-card">
            <strong>1º Ligue para seu Banco</strong>
            <p>Bloqueie o cartão e cancele o Pix.</p>
          </div>
          <div class="emergency-card">
            <strong>2º Avise a Polícia</strong>
            <p>Ligue para o número:</p>
            <span>190</span>
          </div>
          <div class="emergency-card">
            <strong>3º Avise os Familiares</strong>
            <p>Peça ajuda para resolver a situação.</p>
          </div>
        </div>
      </section>
    </main>

    <!-- RODAPÉ -->
    <footer>
      <p><strong>Guia Digital Sênior Rosa</strong> — Sua segurança é a nossa prioridade.</p>
      <p style="margin-top: 10px; font-size: 0.95rem;">Dica: Salve esta página nos favoritos do seu navegador para ler sempre que tiver dúvidas!</p>
    </footer>

  </div>

</body>
</html>
