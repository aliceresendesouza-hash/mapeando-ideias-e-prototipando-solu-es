<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Documento do Projeto: Rotina da Persona</title>
  
  <style>
    /* ==========================================================================
       1. CSS RESET & BORDER-BOX (Garante layout estável e previsível)
       ========================================================================== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #f5f7fa;
      color: #2c3e50;
      line-height: 1.6;
      padding: 40px 20px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .container {
      max-width: 800px;
      width: 100%;
    }

    header {
      text-align: center;
      margin-bottom: 40px;
    }

    header h1 {
      font-size: 2.2rem;
      color: #1a252f;
      margin-bottom: 10px;
    }

    header p {
      color: #7f8c8d;
      font-size: 1.1rem;
    }

    /* ==========================================================================
       2. INTERAÇÃO E LAYOUT DOS CARDS (Uso de Pseudoclasses)
       ========================================================================== */
    .timeline {
      display: flex;
      flex-direction: column;
      gap: 20px;
      margin-bottom: 30px;
    }

    .card-situacao {
      background: white;
      border-radius: 8px;
      padding: 25px;
      box-shadow: 0 4px 6px rgba(0,0,0,0.05);
      border-left: 5px solid #bdc3c7;
      cursor: pointer;
      
      /* Transição suave para interações */
      transition: transform 0.2s, box-shadow 0.2s, border-color 0.2s;
    }

    /* :hover - Feedback visual ao passar o mouse */
    .card-situacao:hover {
      transform: translateX(5px);
      box-shadow: 0 6px 12px rgba(0,0,0,0.1);
    }

    /* Cores personalizadas para os períodos do dia usando classes de estado */
    .card-situacao.manha { border-left-color: #f1c40f; }
    .card-situacao.tarde { border-left-color: #e67e22; }
    .card-situacao.noite { border-left-color: #9b59b6; }

    .periodo-tag {
      font-size: 0.8rem;
      font-weight: bold;
      text-transform: uppercase;
      padding: 3px 8px;
      border-radius: 4px;
      background-color: #ecf0f1;
      display: inline-block;
      margin-bottom: 10px;
    }

    .card-situacao h2 {
      font-size: 1.3rem;
      margin-bottom: 15px;
      color: #34495e;
    }

    .detalhe-item {
      margin-bottom: 10px;
      font-size: 0.95rem;
    }

    .detalhe-item strong {
      color: #2c3e50;
    }

    /* ==========================================================================
       3. PAINEL DE CONTROLE DE LEITURA (JavaScript Estável)
       ========================================================================== */
    .painel-controle {
      background: #2c3e50;
      color: white;
      padding: 20px;
      border-radius: 8px;
      margin-top: 20px;
      text-align: center;
    }

    .btn-simular {
      background-color: #2ecc71;
      color: white;
      border: none;
      padding: 12px 24px;
      font-size: 1rem;
      font-weight: bold;
      border-radius: 6px;
      cursor: pointer;
      transition: background 0.2s;
      width: 100%;
      max-width: 300px;
    }

    /* :hover e :active do botão */
    .btn-simular:hover { background-color: #27ae60; }
    .btn-simular:active { transform: scale(0.98); }

    .log-status {
      margin-top: 15px;
      font-style: italic;
      color: #bdc3c7;
      min-height: 24px;
    }
  </style>
</head>
<body>

  <div class="container">
    <header>
      <h1>Situações do Cotidiano da Persona</h1>
      <p>Mapeamento de rotina e consequências do problema para o documento do grupo.</p>
    </header>

    <main class="timeline">
      
      <section class="card-situacao manha" tabindex="0">
        <span class="periodo-tag">Situação 1: Manhã (Estudo/Trabalho)</span>
        <h2>Tentativa de Organização Inicial</h2>
        <div class="detalhe-item"><strong>O que estava tentando fazer:</strong> Iniciar os estudos do dia organizando as abas do navegador, links de referência e materiais recebidos por e-mail.</div>
        <div class="detalhe-item"><strong>Como o problema aparece:</strong> O excesso de informações descentralizadas faz a persona esquecer onde guardou o link principal da aula e quais dados eram protegidos por privacidade.</div>
        <div class="detalhe-item"><strong>Consequência:</strong> Perda de 30 minutos preciosos apenas tentando se localizar, gerando frustração e atraso no cronograma planejado.</div>
      </section>

      <section class="card-situacao tarde" tabindex="0">
        <span class="periodo-tag">Situação 2: Tarde (Consumo/Tarefas)</span>
        <h2>Realizar uma Compra ou Cadastro Online</h2>
        <div class="detalhe-item"><strong>O que estava tentando fazer:</strong> Fazer a assinatura de uma plataforma de estudos ou comprar um e-book necessário para um trabalho acadêmico.</div>
        <div class="detalhe-item"><strong>Como o problema aparece:</strong> A página do e-commerce esconde os termos da LGPD, exibe preços confusos violando o CDC e o botão de leitura trava ao enviar o formulário.</div>
        <div class="detalhe-item"><strong>Consequência:</strong> Insegurança em fornecer dados pessoais, medo de cair em um golpe virtual e desistência da compra essencial.</div>
      </section>

      <section class="card-situacao noite" tabindex="0">
        <span class="periodo-tag">Situação 3: Noite (Revisão/Descanso)</span>
        <h2>Revisar Conteúdos e Compartilhar Materiais</h2>
        <div class="detalhe-item"><strong>O que estava tentando fazer:</strong> Revisar a matéria estudada e enviar um relatório final consolidado para o grupo do projeto.</div>
        <div class="detalhe-item"><strong>Como o problema aparece:</strong> Ao tentar subir os arquivos na plataforma acadêmica com conexões instáveis, o sistema aceita múltiplos cliques rápidos e gera arquivos duplicados corrompidos.</div>
        <div class="detalhe-item"><strong>Consequência:</strong> O grupo recebe o material errado ou incompleto, gerando ruído na comunicação e retrabalho para a persona antes de dormir.</div>
      </section>

    </main>

    <div class="painel-controle">
      <button id="btnSimular" class="btn-simular">Consolidar Dados no Relatório</button>
      <div id="logStatus" class="log-status">Clique para simular o salvamento estável no documento...</div>
    </div>
  </div>

  <script>
    const btnSimular = document.getElementById('btnSimular');
    const logStatus = document.getElementById('logStatus');
    
    let processando = false;
    let tempoId = null;

    btnSimular.addEventListener('click', () => {
      // Se houver clique rápido repetido, cancela o processo anterior e reinicia com segurança
      if (processando) {
        clearTimeout(tempoId);
        logStatus.innerText = "Operação anterior interrompida! Reiniciando gravação segura...";
      }

      processando = true;
      btnSimular.innerText = "Gravando...";
      
      if (!tempoId) {
        logStatus.innerText = "Processando as 3 situações da rotina e salvando no documento...";
      }

      // Simula a latência de salvamento estável de 2 segundos
      tempoId = setTimeout(() => {
        logStatus.innerHTML = "<strong>✓ Sucesso!</strong> As 3 situações cotidianas foram registradas sem duplicidade.";
        
        // Reseta os controladores de estado
        processando = false;
        tempoId = null;
        btnSimular.innerText = "Consolidar Dados no Relatório";
      }, 2000);
    });
  </script>

</body>
</html>mapeando ideias e prototipando soluções# mapeando-ideias-e-prototipando-solu-es
