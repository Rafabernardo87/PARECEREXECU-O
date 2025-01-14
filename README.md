<!DOCTYPE html>
<html>
<head>
  <title>PARECER RECURSAL - EXECUÇÃO</title>
  <style>
    /* Importa a fonte IBM Plex Sans */
    @import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@400;600&display=swap');

    /* Aplica a fonte ao corpo e elementos de texto */
    body {
      font-family: 'IBM Plex Sans', sans-serif;
      margin: 0;
      padding: 0;
    }

    .container {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      padding: 16px;
    }

    .form-section {
      width: 65%;
    }

    .result-section {
      width: 30%;
      margin-left: 16px;
    }

    #resultadoTexto {
      white-space: pre-wrap;
      background-color: #f9f9f9;
      padding: 16px;
      border: 1px solid #ddd;
      border-radius: 4px;
      height: auto;
      overflow-y: auto;
    }

    button {
      font-family: 'IBM Plex Sans', sans-serif;
    }

    .spacing {
      margin-bottom: 16px;
    }
  </style>
  <script>
    function selecionarTexto() {
      const elemento = document.getElementById("resultadoTexto");

      if (document.body.createTextRange) {
        const range = document.body.createTextRange();
        range.moveToElementText(elemento);
        range.select();
      } else if (window.getSelection) {
        const range = document.createRange();
        range.selectNode(elemento);
        window.getSelection().removeAllRanges();
        window.getSelection().addRange(range);
      }

      document.execCommand("copy");
      alert("Resultado copiado para a área de transferência!");
    }

    function obterOpcaoSelecionada() {
      const valorExecutado = document.getElementById("valorExecutado").value || "N/A";
      const condenacaoSolidaria = document.querySelector('input[name="condenacaoSolidaria"]:checked')?.value || "N/A";
      const responsabilidade = document.querySelector('input[name="responsabilidade"]:checked')?.value || "N/A";
      const responsavelPolo = document.querySelector('input[name="responsavelPolo"]:checked')?.value || "N/A";
      const houveBloqueio = document.querySelector('input[name="houveBloqueio"]:checked')?.value || "N/A";
      const valorTransferido = document.querySelector('input[name="valorTransferido"]:checked')?.value || "N/A";
      const execucaoDevida = document.querySelector('input[name="execucaoDevida"]:checked')?.value || "N/A";
      const motivoExecucao = document.getElementById("motivoExecucao").value.trim() || "N/A";
      const impugnarEmbargar = document.querySelector('input[name="impugnarEmbargar"]:checked')?.value || "N/A";
      const garantirValor = document.querySelector('input[name="garantirValor"]:checked')?.value || "N/A";
      const motivoDispensa = document.getElementById("motivoDispensa").value.trim() || "N/A";
      const resumoInicial = document.getElementById("resumoInicial").value.trim() || "N/A";
      const resumoSentenca = document.getElementById("resumoSentenca").value.trim() || "N/A";
      const resumoAcordao = document.getElementById("resumoAcordao").value.trim() || "N/A";
      const resumoDecisao = document.getElementById("resumoDecisao").value.trim() || "N/A";
      const parecerFinal = document.querySelector('input[name="parecerFinal"]:checked')?.value || "N/A";
      const motivoParecer = document.getElementById("motivoParecer").value.trim() || "N/A";

      const resultado = `
    • VALOR EXECUTADO:
      
        R$ ${valorExecutado}

    • CONDENAÇÃO SOLIDÁRIA:
      
        ${condenacaoSolidaria}

    • RESPONSABILIDADE:
      
        ${responsabilidade}

    • RESPONSÁVEL ESTÁ NO POLO:
      
        ${responsavelPolo}

    • HOUVE BLOQUEIO:
      
        ${houveBloqueio}

    • VALOR TRANSFERIDO:
      
        ${valorTransferido}

    • EXECUÇÃO É DEVIDA:
      
        ${execucaoDevida}

    • MOTIVO DA EXECUÇÃO:
      
        ${motivoExecucao}

    • IMPUGNAR/EMBARGAR:
      
        ${impugnarEmbargar}

    • NECESSÁRIO GARANTIR O VALOR:
      
        ${garantirValor}

    • MOTIVO DA DISPENSA:
      
        ${motivoDispensa}

    • BREVE RESUMO DA INICIAL:
      
        ${resumoInicial}

    • BREVE RESUMO DA SENTENÇA:
      
        ${resumoSentenca}

    • BREVE RESUMO DO ACÓRDÃO:
      
        ${resumoAcordao}

    • BREVE RESUMO DA DECISÃO:
      
        ${resumoDecisao}

    • PARECER FINAL DO ESCRITÓRIO:
      
        ${parecerFinal}

    • MOTIVO DO PARECER:
      
        ${motivoParecer}
      `;

      document.getElementById("resultadoTexto").innerText = resultado;
    }
  </script>
</head>
<body>
  <div class="container">
    <div class="form-section">
      <h1>PARECER RECURSAL - EXECUÇÃO</h1>
      <form>
        <div class="spacing">
          <label>Valor Executado:</label>
          <input type="text" id="valorExecutado" placeholder="Ex.: 6.026,69">
        </div>

        <div class="spacing">
          <label>Condenação Solidária:</label><br>
          <input type="radio" name="condenacaoSolidaria" value="Sim"> Sim
          <input type="radio" name="condenacaoSolidaria" value="Não"> Não
        </div>

        <div class="spacing">
          <label>Responsabilidade:</label><br>
          <input type="radio" name="responsabilidade" value="Fabricante"> Fabricante
          <input type="radio" name="responsabilidade" value="Marketplace"> Marketplace
          <input type="radio" name="responsabilidade" value="ML Site"> ML Site
          <input type="radio" name="responsabilidade" value="ML Loja"> ML Loja
          <input type="radio" name="responsabilidade" value="Luiza Cred"> Luiza Cred
        </div>

        <div class="spacing">
          <label>Responsável está no polo:</label><br>
          <input type="radio" name="responsavelPolo" value="Sim"> Sim
          <input type="radio" name="responsavelPolo" value="Não"> Não
        </div>

        <div class="spacing">
          <label>Houve bloqueio:</label><br>
          <input type="radio" name="houveBloqueio" value="Sim"> Sim
          <input type="radio" name="houveBloqueio" value="Não"> Não
        </div>

        <div class="spacing">
          <label>Valor Transferido:</label><br>
          <input type="radio" name="valorTransferido" value="Sim"> Sim
          <input type="radio" name="valorTransferido" value="Não"> Não
          <input type="radio" name="valorTransferido" value="Não se aplica"> Não se aplica
        </div>

        <div class="spacing">
          <label>Execução é devida:</label><br>
          <input type="radio" name="execucaoDevida" value="Sim"> Sim
          <input type="radio" name="execucaoDevida" value="Não"> Não
          <input type="radio" name="execucaoDevida" value="Em Partes"> Em Partes
        </div>

        <div class="spacing">
          <label>Motivo da execução:</label><br>
          <textarea id="motivoExecucao" rows="4" cols="50"></textarea>
        </div>

        <div class="spacing">
          <label>Vamos impugnar ou embargar:</label><br>
          <input type="radio" name="impugnarEmbargar" value="Sim"> Sim
          <input type="radio" name="impugnarEmbargar" value="Não"> Não
        </div>

        <div class="spacing">
          <label>É necessário garantir o valor?</label><br>
          <input type="radio" name="garantirValor" value="Sim"> Sim
          <input type="radio" name="garantirValor" value="Não"> Não
        </div>

        <div class="spacing">
          <label>Motivo da dispensa:</label><br>
          <textarea id="motivoDispensa" rows="4" cols="50"></textarea>
        </div>

        <div class="spacing">
          <label>Breve resumo da inicial:</label><br>
          <textarea id="resumoInicial" rows="4" cols="50"></textarea>
        </div>

        <div class="spacing">
          <label>Breve resumo da sentença:</label><br>
          <textarea id="resumoSentenca" rows="4" cols="50"></textarea>
        </div>

        <div class="spacing">
          <label>Breve resumo do acórdão:</label><br>
          <textarea id="resumoAcordao" rows="4" cols="50"></textarea>
        </div>

        <div class="spacing">
          <label>Breve resumo da decisão:</label><br>
          <textarea id="resumoDecisao" rows="4" cols="50"></textarea>
        </div>

        <div class="spacing">
          <label>Parecer final do escritório:</label><br>
          <input type="radio" name="parecerFinal" value="Dispensar e pagar"> Dispensar e pagar
          <input type="radio" name="parecerFinal" value="Dispensar e convolar"> Dispensar e convolar
          <input type="radio" name="parecerFinal" value="Embargar/impugnar"> Embargar/impugnar
          <input type="radio" name="parecerFinal" value="Questionar responsável por e-mail"> Questionar responsável por e-mail
        </div>

        <div class="spacing">
          <label>Motivo do parecer:</label><br>
          <textarea id="motivoParecer" rows="4" cols="50"></textarea>
        </div>

        <button type="button" onclick="obterOpcaoSelecionada()">Gerar Parecer</button>
        <button type="button" onclick="selecionarTexto()">Copiar Resultado</button>
      </form>
    </div>

    <div class="result-section">
      <h2>Resultado:</h2>
      <pre id="resultadoTexto"></pre>
    </div>
  </div>
</body>
</html>
