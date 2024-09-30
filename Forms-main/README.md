# Gerador de Documentos em PDF
Este projeto é um gerador de documentos em PDF com base em dados fornecidos por formulários HTML. Ele utiliza a biblioteca pdfMake para gerar os arquivos PDF, permitindo a criação automática de vários tipos de declarações e documentos com base nas informações inseridas pelo usuário.

Funcionalidades
Este projeto inclui várias funcionalidades para gerar PDFs diferentes, como:

Gerar Atestado de Capacidade Técnica
Gerar Declaração de Não Utilização de Recursos
Gerar Declaração de Cumprimento de Artigos de Lei
Gerar Declaração de Ausência de Destinação de Recursos
Gerar Termo de Compromisso para Coordenadores
Gerar PDFs automaticamente a partir de um botão que chama todas as funções de geração de PDF
Como o Código Funciona
Estrutura
O código é composto por diversas funções JavaScript, que:

Coletam dados de campos de formulários HTML (por exemplo, nome, CPF, CNPJ, entidade, etc.).
Montam esses dados em uma estrutura de conteúdo para a criação de um PDF usando a biblioteca pdfMake.
Geram o PDF correspondente ao tipo de declaração solicitada.
Oferecem a opção de gerar múltiplos PDFs em sequência.
Principais Funções
Função generateAtestadoPDF():

Gera um Atestado de Capacidade Técnica com as informações fornecidas, incluindo o nome do dirigente, CPF, CNPJ, e detalhes do projeto.
Função generateDeclaracaoNaoUtilizacaoRecursosPDF():

Gera uma Declaração de Não Utilização de Recursos, indicando que os recursos não serão usados para outros fins além do especificado.
Função generateDeclaracaoLeiPDF():

Gera uma declaração específica relacionada ao cumprimento de Artigos de Lei, com base na Lei nº 13.019/2014.
Função generateDeclaracaoAusenciaRecursosPDF():

Gera uma Declaração de Ausência de Destinação de Recursos, confirmando que os recursos não serão usados para despesas não permitidas.
Função generateTermoCompromissoCoordenadorPDF():

Gera um Termo de Compromisso relacionado a um Coordenador Geral de Programa, especificando suas responsabilidades.
Função generateAllPDFs():

Gera todos os PDFs de uma vez, chamando as funções individualmente com intervalos de tempo.
Formatação e Geração de PDFs
Todas as funções de geração de PDF utilizam o pdfMake.createPdf(docDefinition).download(...) para baixar o arquivo PDF no navegador do usuário. O documento é formatado com margens, títulos centralizados e conteúdo justificado.

Funções Auxiliares
Função formatarCPF(): Formata o CPF do usuário no formato "xxx.xxx.xxx-xx".
Função formatDate(): Retorna a data atual formatada no formato DD/MM/AAAA.
Função mostrarCoordenador(resposta): Mostra ou oculta campos relacionados ao Coordenador Geral com base na resposta do usuário.
Como Usar
Inclua o código em uma página HTML com formulários que contenham os seguintes campos de entrada:
Nome do dirigente
CPF, RG, CNPJ, e outros dados relacionados à entidade
Adicione um botão com o ID botaoGerarPDF, que ao ser clicado chamará a função generateAllPDFs() para gerar todos os PDFs.
Certifique-se de que a biblioteca pdfMake está corretamente incluída no projeto, com um <script> apontando para o arquivo pdfmake.min.js e o vfs_fonts.js.
Preencha os campos no formulário e clique no botão "Gerar PDFs".
Dependências
pdfMake: Biblioteca JavaScript para gerar PDFs diretamente no navegador.




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



Observações
Certifique-se de que os campos do formulário HTML tenham IDs correspondentes aos utilizados nas funções JavaScript para coletar corretamente os dados.
O botão Gerar PDFs chama todas as funções em sequência, gerando múltiplos arquivos PDF.
Caso algum campo obrigatório esteja vazio, as funções irão alertar o usuário antes de tentar gerar o PDF.
Contribuições
Sinta-se à vontade para contribuir com melhorias neste projeto, adicionando novos tipos de declarações ou otimizando o código para casos específicos.
