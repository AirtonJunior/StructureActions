# Structure Actions
<b>TCC:</b> FERRAMENTA COMPUTACIONAL PARA CÁLCULO DE COMBINAÇÕES DE AÇÕES EM ESTRUTURAS DE CONCRETO<br>
<b>Desenvolvido por:</b> Jose Airton Cardoso Araujo Junior e Lucas de Oliveira Nunes<br>
<b>Universidade:</b> Universidade Nove de Julho<br>
<b>Departamento:</b> Engenharia Civil<br>
<b>Orientador:</b> Prof.º Me. Jorge Alberto Cecin<br>


Ao desenvolver a ferramenta computacional, foi pensada para ter uma boa usabilidade, para que qualquer pessoa, mesmo com pouco conhecimento em utilizar computador conseguisse trabalhar nela. Com isso foi utilizado o padrão do sistema operacional Windows e alguns botões com imagem para ser mais fácil de usar.
Para as pessoas que sabe mexer em computador, é possível acessar a maioria dos comados através de “atalhos” ao clicar em teclas especificas no teclado, os atalhos podem ser encontrados na ferramenta. 
Outro recurso é a criação de um importador em formato CSV (ponto e vírgula), para a ferramenta entender o arquivo de importação foi criado siglas, geralmente elas estarão entre parentes e servem para informar cada determinado item, que será apresentado no Capítulo 8.2 ARQUIVO DE IMPORTAÇÃO. Para auxiliar em futuros ajustes é possível salvar os dados e importar futuramente.
Um item de ajuda foi criado onde pode encontrar todas as informações sobre a ferramenta, além de como utilizá-la e como criar o arquivo de importação. Para usar a feramente 

# Como Funciona
Ao iniciar a ferramenta ela exibe o Splash Screen por 3 segundos, nessa tela é exibido: nome da ferramenta, subtítulo do TCC, nome dos integrantes, nome do orientador e logo da Uninove.

Splash Screen

![Webserver UI](image/splashscreen.png "Splash Screen")
 
Depois do Splash Screen é aberto a Home (tela principal), toda a ferramenta funciona dentro dessa tela e é onde tem os principais botões como: criar um novo projeto, importar dados, salvar os dados, imprimir o resultado, organizar as janelas (telas internas), ajuda, entre outros.
É possível criar um projeto do zero ou importar os dados com o arquivo CSV que será explicado na próxima seção. Quando for salvar os dados é necessário estar com um projeto aberto, no caso de imprimir o resultado tem que estar com a página do resultado aberta.
Figura 7 – Tela Home
 

Ao clicar em importar (Abrir) ou apertar em Ctrl+O é aberta uma janela para a seleção de um arquivo CSV, após selecionado a ferramenta abre a janela de “Criar Novo” (essa janela é do tipo diagnostico que bloquei o restante da ferramenta até que ela seja fechada pelo botão “X” que cancela a operação ou pelo botão “AVANÇAR” para concluir a operação), o nome do arquivo é colocado no título da janela, nessa tela tem que ser selecionado o  “Tipo de Concreto Estrutural” e “Combinações de Ações (ELU)”, em seguida clicar no botão “AVANÇAR”. Com isso a ferramenta faz uma validação de todos os dados para identificar possíveis inconsistências de dados, caso encontre é aberto uma janela informada o que está errado e finaliza o processo de importação. 
Quando importado um arquivo sem erro a ferramenta abre a janela com a lista de ações que será explicada mais a diante. É possível evitar a janela “Criar Novo” inserindo a sigla do “Tipo de Concreto Estrutural” e “Combinações de Ações (ELU)” no nome do arquivo da seguinte forma: 
<nomedeidentificacao>_<SiglaTipodeConcretoEstrututal>_<SilgaCombinacaodeAcaoELU>.csv

Para o caso do “Tipo de Concreto Estrutural” de “Concreto Armado (CA)” e “Combinações de Ações (ELU)” “Normais (NO)” o nome do arquivo ficará algo como: “edificio_CA_NO.csv”.

Janela Criar Novo

![Webserver UI](image/criarnovo.png "Criar Novo")
   

Algo parecido ocorre ao clicar em novo ou apertar em Ctrl+N na tela de Home, porém não abre uma janela de seleção de arquivos, o título permanece com o texto “Criar Novo” e não é feito nenhuma validação, pois não tem dados para ser avaliados.
O “Tipo de Concreto Estrutural” serve para definir quais as combinações do ELS serão calculadas, conforme a norma. Para a “Combinações de Ações (ELU)” além de saber qual a combinação a ser utilizada também serve para definir os coeficientes de ponderação. Opções: 
- Tipo de Concreto Estrutural:
    - Concreto Simples (CS);
    - Concreto Armado (CA);
    - Concreto Protendido Nível 1 (Protensão Parcial - PP);
    - Concreto Protendido Nível 2 (Protensão Limitada - PL);
    - Concreto Protendido Nível 3 (Protensão Completa - PC).
- Combinações de Ações (ELU):
    - Normais (NO);
    - Especiais ou de Construção (EC);
    - Excepcionais (EX).

Após a configuração das informações iniciais é aberto a janela de lista de ações, nessa janela é informado as configurações anteriores, um botão chamado “NOVA AÇÃO” para criar uma ação, uma tabela para mostrar as ações inseridas e um botão chamado “RESULTADO”.
Na tabela é mostrado os campos fixos: Superfície, Descrição, Valor, Tipo de Ação, Efeito, Coeficiente de Ponderação (γ), Fator de Combinação (ψ0), Fator de Redução (ψ1) e Fator de Redução (ψ2). Também existe os campos variáveis que só mostra de acordo com o “Tipo de Concreto Estrutural” que são: Combinação Quase Permanentes de Serviço (CQP), Combinação Frequentes de Serviço (CF) e Combinação Raras de Serviço (CR).
Ao clicar na tabela em uma linha de uma ação existente abre a janela de inserção de ação, que será detalhada a seguir, as mudanças nessa janela é que no lugar do botão “SALVAR” tem um botão “ALTERAR” e um botão “DELETAR” é mostrado para fazer a exclusão da ação.
Figura 9 – Janela de Lista de Ações
  
Quando clica no botão “NOVA AÇÃO” é aberto uma janela do tipo diagnostico, com todas as informações que são necessárias para o cálculo e para separar os dados por superfície (elemento construtivo). Para um melhor entendimento a seguir a importância de cada dado:
•	Descrição: A descrição serve para a identificação das ações, em uma mesma superfície não pode existir descrições iguais, o valor informado deve ser alfanumérico de no mínimo 5 (cinco) caracteres;
•	Valor: É o valor numérico do esforço que a ação transmite para a superfície em kN.m;
•	Tipo de Ação: Deve ser checado umas das opções de acordo com a ação que está sendo configurada, esse valor é utilizado juntamente com outros dados para definir o valor do coeficiente de ponderação (γ), as opções são as seguintes:
o	Permanentes:
	Gerais (PG);
	Pretensão (PP);
	Recalques de apoio e retração (PR).
o	Variáveis:
	Gerais (VG);
	Temperatura (VT).
o	Excepcional:
	Excepcional (EX). 
•	Efeito: Informado se a ação permanente é “Desfavorável (D)” ou “Favorável (F)”, é utilizado para identificar o fator de ponderação; 
•	Superfície: Tem duas opções, primeiro criar uma superfície nova ou selecionar uma superfície já existente, todas as contas são feitas por superfície, o dado informado deve ser um valor alfanumérico de no mínimo 5 caracteres.
•	Combinações de Ações – ELU: Nessa parte tem que ser informada as combinações do Estado Limite de Serviço que a ação faz parte, é exibido as combinações que faz parte do “Tipo de Concreto Estrutural” de acordo com a norma; A janela do modelo para as ações permanente pode ser visualizada na figura a seguir: 
 
Figura 10 – Janela de Adição e Edição das Ações
 

As ações variáveis necessitam de mais informações, o fator de combinação e os fatores de redução, porém não necessita do efeito, com isso a janela abre mais uma opção onde deve informar a partir de uma tabela a categoria que a ação variável faz parte. Para as ações variáveis gerais tem as três opções de carga acidental e a opção do vento, quando é uma ação variável de temperatura só exibe a opção de temperatura. Conforme a figura a seguir que mostra a opção variável geral selecionada:
Figura 11 – Janela de Configuração das Ações – Ações Variáveis
 

Quando tenta inserir ou editar uma ação é feito uma validação dos dados, onde verifica se existe alguma configuração que não está de acordo com a norma ou com a configuração inicial.
Após inserir todas as informações pode ser visualizado o resultado com o memorial de cálculo ao clicar no botão “RESULTADO” na janela de lista de ações, nesse momento é feito uma verificação de inconsistência de dados por superfície e somente se tiver tudo de acordo é possível ver o resultado.
Para as combinações ELU é validado se existe no mínimo uma ação direta permanente e uma ação direta variável, no caso das combinações do ELS é verificado se existe uma ação permanente e uma variável independente do tipo direto ou indireto. Quando selecionado a combinação ELU “Excepcionais (EX)” é verificado se existe uma ação deste tipo. 
Figura 12 – Janela de Resultado
 

# Arquivo de Importação
O arquivo de importação é do tipo CSV que significa “comma-separated-values” (valores separados por vírgulas), porém na ferramenta foi utilizado uma variação desse tipo que em vez de usar a vírgula é utilizado o ponto e vírgula (;). Esse tipo de arquivo é utilizado para transferência de informações entre sistemas distintos, sabendo-se a estrutura dos dados qualquer sistema consegui interpretar, pois a sua leitura é como um arquivo de texto simples.
O Excel consegue gerar arquivos CSV, para o tipo separado por ponto e vírgula (;) deve-se “Salvar uma Cópia” e selecione a opção "CSV (Macintosh) (*.csv)" ou "CSV (MS-DOS) (*.csv)". Além de gerar o Excel consegui alterar esse tipo de arquivo, tornando a utilização desse tipo de arquivo muito versátil por muitas pessoas saber utilizar o Excel. A seguir um exemplo básico de CSV: 
Figura 13 – Exemplo de Arquivo CSV no Excel
  
Figura 14 – Exemplo de Arquivo CSV no Editor de Texto

Para a Ferramenta entender o arquivo de importação é preciso que na primeira linha tenha um cabeçalho com os seguintes campos: superfície, tipo, descricao, valor, efeito, fator, cqp, cf e cr. Nas demais linhas as informações correspondentes de cada ações, sendo uma ação por linha. Basicamente o arquivo de importação salva todas as ações a parti de uma planilha orientada, logo isso ajuda o usuário a inserir de forma mais prática as ações.
A seguir a explicação de cada um dos itens do cabeçalho:
- superfície – Informa a superfície que a ação está situada, é um valor alfanumérico de no mínimo 5 caracteres;
- tipo – Informa o tipo de ação, um dos tipos a seguir:
    - PG – Permanente Geral; 
o	PP – Permanente de Protensão (Utilizado quando o Tipo de Concreto Estrutural for um dos 3 níveis de Concreto Protendido); 
o	PR – Permanente de Recalques de Apoio e Retração;
o	VG – Variável Geral;
o	VT – Variável de Temperatura;
o	EX – Excepcional (Utilizado somente para a Combinações Excepcionais do ELU).
•	descricao – Informa uma descrição para identificação da ação, é um valor alfanumérico de no mínimo 5 caracteres;
•	valor – Informa o valor da força atuante na estrutura em kN.m, é um valor numérico;
•	efeito – Serva para identificar o fator de ponderação da ação permanente, utilize um dos tipos a seguir:
o	D – Desfavorável;
o	F – Favorável;
o	OBS.: Vazio para as ações variáveis. 
•	fator – Serve para identificar os fatores de combinação e redução para as ações variáveis, utilize um dos tipos a seguir:
o	Para VG – Variável Geral:
	A1 – Cargas acidentais de edifícios: Locais em que não há predominância de pesos e de equipamentos que permanecem fixos por longos períodos de tempo, nem de elevadas concentrações de pessoas (Edificações residenciais, de acesso restrito);
	A2 – Cargas acidentais de edifícios: Locais em que há predominância de pesos de equipamentos que permanecem fixos por longos períodos de tempo, ou de elevadas concentrações de pessoas (Edificações comerciais, de escritórios e de acesso público);
	A3 – Cargas acidentais de edifícios: Bibliotecas, arquivos, depósitos, oficinas e garagens;
	V – Vento: Pressão dinâmica do vento nas estruturas em geral.
o	Para VT – Variável de Temperatura:
	T – Temperatura: Variações uniformes de temperatura em relação à média anual local 
o	OBS.: Vazio para as ações permanentes. 	
•	cqp: Informa se a ação é para ser utilizada no cálculo de “Combinação quase permanente”, somente para “Concreto Protendido Nível 1 (Protensão Parcial - PP)”. Utilize um dos tipos a seguir:
o	S – Sim;
o	N – Não;
o	OBS.: Vazio para os demais Tipo de Concreto Estrutural.
•	cf: Informa se a ação é para ser utilizada no cálculo de “Combinação frequente”, para todos os Tipos de Construção Estrutural com exceção da “Concreto Simples (CS)”. Utilize um dos tipos a seguir: 
o	S – Sim;
o	N – Não;
o	OBS.: Vazio para os demais Tipo de Concreto Estrutural.
•	cr: Informa se a ação é para ser utilizada no cálculo de “Combinação rara”, somente para “Concreto Protendido Nível 3 (Protensão Completa - PC)”. Utilize um dos tipos a seguir: 
o	S – Sim;
o	N – Não;
o	OBS.: Vazio para os demais Tipo de Concreto Estrutural.

A seguir exemplo do cabeçalho no Excel e no Editor de Texto:
Figura 15 – Exemplo do Cabeçalho no Excel
 
Figura 16 – Exemplo do Cabeçalho no Editor de Texto
 



<form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top">
<input type="hidden" name="cmd" value="_s-xclick" />
<input type="hidden" name="hosted_button_id" value="9RFKTYR4NUUU8" />
<input type="image" src="https://www.paypalobjects.com/pt_BR/BR/i/btn/btn_donateCC_LG.gif" border="0" name="submit" title="PayPal - The safer, easier way to pay online!" alt="Faça doações com o botão do PayPal" />
<img alt="" border="0" src="https://www.paypal.com/pt_BR/i/scr/pixel.gif" width="1" height="1" />
</form>

https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=9RFKTYR4NUUU8&source=url


