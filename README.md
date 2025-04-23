# DIAGNOSTICO-BIM-MP-RO
from pathlib import Path

# Caminho do arquivo HTML
file_path = Path("/mnt/data/formulario_bim_diagnostico.html")

# Conteúdo do arquivo HTML atualizado
html_content = '''<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Diagnóstico Preliminar BIM</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f6f9;
      color: #333;
    }
    header {
      background-color: #004080;
      color: white;
      padding: 20px 30px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    header img {
      height: 50px;
    }
    h1 {
      text-align: center;
      padding: 20px;
      color: #004080;
    }
    form {
      max-width: 1000px;
      margin: 0 auto;
      background-color: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0px 4px 12px rgba(0,0,0,0.1);
    }
    .section-title {
      background-color: #e3eefd;
      padding: 10px;
      margin-top: 30px;
      border-left: 5px solid #004080;
      font-weight: bold;
    }
    .question {
      margin: 20px 0;
    }
    .question label {
      display: block;
      margin-bottom: 10px;
      font-weight: bold;
    }
    .options {
      display: flex;
      gap: 20px;
      margin-bottom: 10px;
    }
    .textarea-group {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }
    textarea {
      width: 100%;
      padding: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
      resize: vertical;
    }
    button {
      margin-top: 30px;
      background-color: #004080;
      color: white;
      padding: 12px 25px;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
    }
    button:hover {
      background-color: #003060;
    }
  </style>
</head>
<body>
  <header>
    <img src="https://upload.wikimedia.org/wikipedia/commons/2/2b/SENAI_logo.png" alt="SENAI">
    <img src="https://www.mpro.mp.br/image/layout_set_logo?img_id=248733&t=1701100754206" alt="Ministério Público de Rondônia">
  </header>
  <h1>Diagnóstico Preliminar - Maturidade BIM</h1>
  <form method="POST" action="https://formsubmit.co/leone.leitao@fiero.org.br">
    <input type="hidden" name="_captcha" value="false">
    <input type="hidden" name="_next" value="https://fiero.org.br/obrigado.html">
    <script>
      const perguntas = [
        { pilar: 'Política', texto: '1) Existe iniciativa formalizada da Prefeitura para promover/fomentar a Transformação Digital?' },
        { pilar: 'Política', texto: '2) Existe iniciativa formalizada da Alta Gestão da Instituição para Implantação do BIM?' },
        { pilar: 'Pessoas', texto: '3) O número de técnicos que atuam diretamente na elaboração /contratação/fiscalização de projetos e obras atende a demanda de atividades em andamento na instituição?' },
        { pilar: 'Pessoas', texto: '4) Existe suporte técnico de profissional de TI para solução de problemas da área de projetos e obras?' },
        { pilar: 'Pessoas', texto: '5) Existe setor de geoprocessamento na Instituição?' },
        { pilar: 'Pessoas', texto: '6) Na composição da equipe técnica atual existe ao menos 1 servidor efetivo?' },
        { pilar: 'Pessoas', texto: '7) Na equipe técnica existe profissional com conhecimento em BIM?' },
        { pilar: 'Processos', texto: '8) A instituição possui macro fluxo de trabalho mapeado e oficializado?' },
        { pilar: 'Processos', texto: '9) Os setores de projetos e obras possuem micro fluxo de trabalho mapeado e oficializado?' },
        { pilar: 'Processos', texto: '10) Existe manual de apresentação de projetos?' },
        { pilar: 'Processos', texto: '11) Existe manual de elaboração de projetos?' },
        { pilar: 'Processos', texto: '12) Existem protocolos de comunicação/colaboração oficialmente estabelecidos?' },
        { pilar: 'Tecnologia', texto: '13) Os hardwares disponíveis são adequados para uso de softwares BIM?' },
        { pilar: 'Tecnologia', texto: '14) A instituição possui softwares BIM adequados para realização das atividades?' },
        { pilar: 'Tecnologia', texto: '15) A instituição possui equipamentos compatíveis com o BIM?' },
        { pilar: 'Tecnologia', texto: '16) A instituição possui rede local para compartilhamento e gestão das informações?' }
      ];
      document.addEventListener("DOMContentLoaded", () => {
        const form = document.querySelector("form");
        let currentPilar = '';
        perguntas.forEach((pergunta, i) => {
          if (pergunta.pilar !== currentPilar) {
            const section = document.createElement("div");
            section.className = "section-title";
            section.textContent = pergunta.pilar;
            form.appendChild(section);
            currentPilar = pergunta.pilar;
          }
          const container = document.createElement("div");
          container.className = "question";
          container.innerHTML = `
            <label>${pergunta.texto}</label>
            <div class="options">
              <label><input type="radio" name="q${i}" value="Sim"> Sim</label>
              <label><input type="radio" name="q${i}" value="Não"> Não</label>
              <label><input type="radio" name="q${i}" value="Na"> N/A</label>
            </div>
            <div class="textarea-group">
              <textarea name="q${i}_positiva" placeholder="Síntese Positiva..."></textarea>
              <textarea name="q${i}_negativa" placeholder="Síntese Negativa..."></textarea>
              <textarea name="q${i}_complemento" placeholder="Complementação..."></textarea>
            </div>
          `;
          form.appendChild(container);
        });
        const button = document.createElement("button");
        button.type = "submit";
        button.textContent = "Enviar Diagnóstico";
        form.appendChild(button);
      });
    </script>
  </form>
</body>
</html>
'''

# Salvando o arquivo
file_path.write_text(html_content, encoding="utf-8")

file_path.name
