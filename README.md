# Gerador de Documentos em PDF

Este projeto permite a criação automática de diferentes tipos de declarações e documentos PDF com base em informações fornecidas por formulários HTML. Utilizando a biblioteca [pdfMake](http://pdfmake.org/), é possível gerar documentos customizados, como atestados e declarações, com um simples clique.

## Funcionalidades

Este projeto inclui diversas funcionalidades, como:

<ul>
  <li>Gerar Atestado de Capacidade Técnica</li>
  <li>Gerar Declaração de Não Utilização de Recursos</li>
  <li>Gerar Declaração de Cumprimento de Artigos de Lei</li>
  <li>Gerar Declaração de Ausência de Destinação de Recursos</li>
  <li>Gerar Termo de Compromisso para Coordenadores</li>
  <li>Gerar múltiplos PDFs automaticamente com um botão</li>
</ul>

## Estrutura do Código

O código é organizado em diversas funções JavaScript que coletam informações de formulários HTML e geram PDFs usando `pdfMake`. Veja a seguir os detalhes de algumas dessas funções:

### Principais Funções

<ol>
  <li>
    <b>Função <code>generateAtestadoPDF()</code>:</b> Gera um Atestado de Capacidade Técnica com informações como nome do dirigente, CPF, CNPJ, entidade e detalhes da proposta.
  </li>
  <li>
    <b>Função <code>generateDeclaracaoNaoUtilizacaoRecursosPDF()</code>:</b> Cria uma declaração de que os recursos não serão utilizados para fins diferentes do especificado.
  </li>
  <li>
    <b>Função <code>generateDeclaracaoLeiPDF()</code>:</b> Gera uma declaração de cumprimento dos artigos da Lei nº 13.019/2014.
  </li>
  <li>
    <b>Função <code>generateDeclaracaoAusenciaRecursosPDF()</code>:</b> Declara que os recursos não serão usados para despesas não permitidas.
  </li>
  <li>
    <b>Função <code>generateTermoCompromissoCoordenadorPDF()</code>:</b> Gera um termo de compromisso indicando um Coordenador Geral.
  </li>
  <li>
    <b>Função <code>generateAllPDFs()</code>:</b> Gera todos os PDFs de uma vez, chamando cada uma das funções separadamente.
  </li>
</ol>

### Funções Auxiliares

<ul>
  <li><code>formatarCPF(campo)</code>: Formata o CPF no formato "xxx.xxx.xxx-xx".</li>
  <li><code>formatDate()</code>: Retorna a data atual formatada como "DD/MM/AAAA".</li>
  <li><code>mostrarCoordenador(resposta)</code>: Mostra ou oculta os campos do Coordenador Geral com base na resposta do usuário.</li>
</ul>

## Como Usar

1. Inclua o código JavaScript e o HTML em sua página web.
2. Certifique-se de que a biblioteca <a href="http://pdfmake.org/">pdfMake</a> está corretamente referenciada no seu projeto.
3. Preencha os campos no formulário HTML e clique no botão "Gerar PDF" para baixar os documentos gerados.
4. Use o botão para gerar múltiplos PDFs automaticamente, ou selecione individualmente qual declaração deseja gerar.

### Exemplo de Formulário HTML

```html
<form>
  <label for="dirigente">Nome do Dirigente:</label>
  <input type="text" id="dirigente" name="dirigente" />

  <label for="cpf">CPF:</label>
  <input type="text" id="cpf" name="cpf" oninput="formatarCPF(this)" />

  <label for="entidade">Entidade:</label>
  <input type="text" id="entidade" name="entidade" />

  <!-- Adicione outros campos conforme necessário -->

  <button id="botaoGerarPDF">Gerar PDFs</button>
</form>

<script src="pdfmake.min.js"></script>
<script src="vfs_fonts.js"></script>
<script src="seu-script.js"></script>
