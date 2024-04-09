O Mercado: Segmentação RFM

Ficha Técnica: Projeto de Análise de Dados para Segmentação RFM.
_________________________________________________________________________________________________________________________________________

Resumo do projeto: 
Análise de dados de uma loja especializada em produtos alimentícios importados chamada “O Mercado”. Esta loja enfrenta problemas de fidelização e dificuldades de adaptação às novas preferências dos seus clientes por não tem uma estratégia eficaz para segmenta-los. Isto levou a uma perda de oportunidades de vendas e a um investimento ineficiente em marketing. Para a empresa, é fundamental abordar esses desafios para alcançar o crescimento sustentável, maximizar a lucratividade e identificar onde investir esforço para estrategias de marketing e retenção.
_________________________________________________________________________________________________________________________________________

Objetivo:
Preparar a base de dados disponibilizada pela empresa, aplicar a segmentação de clientes através do RFM, compreender o resultado da segmentação (em quais grupos a empresa pode concentrar esforços e/ou traçar estratégias de fidelização),  tirar conclusões que permitam à empresa tomar decisões, além de buscar informações importantes que estão ocultas nos dados.
_________________________________________________________________________________________________________________________________________

Equipe:
Projeto individual de Thaise Oliveira.
_________________________________________________________________________________________________________________________________________

Ferramentas e Tecnologias:
Ferramentas de dados: google sheets, google drive
Ferramentas de visualização: google sheets, notion, google slides.
Ferramentas de comunicação: loom, github
Tecnologias: chat gpt https://chat.openai.com/
_________________________________________________________________________________________________________________________________________

Processamento, preparação dos dados: 
>Copia das planilhas originais para meu drive para criação da planilha com todas as autorizações
>Identificação de dados nulos com a  =CONTAR.VAZIO, limpeza dos dados nulos com a formula =QUERY("SELECT * "), limpeza de dados duplicados e células em branco com ferramentas automatizadas do google sheets, por exemplo, filtro de repetição pelo id de transação. >Percepção dos dados fundamentais para analise RFM. Recencia (data da ultima compra) através da =MAX(FILTER) e DAYS. Valor: (total de compras por cliente) através da =SOMA de células na aba de resumo de compras e a frequencia (quantas compras por cliente) através da =CONT.SE
>Refinamento de dados na aba de transações, contagem de clientes únicos usando a formula =UNIQUE para solucionar a repetição de dados, criando novos dados importantes para o criação de dados fundamentais ao RFM: data da ultima compra, quantidade de compras totais. Da aba resumo de compras extrai o dado total de compras . >União das tabelas com =PROCV>Identificação de clientes sem dados fundamentais para a análise como salário e data da ultima compra, optei pela exclusão dos mesmos pois julguei que não teriam importância nos dados finais.
>Criação de novas variáveis interessantes para entendimento dos clientes e melhor organização dos dados como: idade, faixa etária (idoso, adulto e jovem), faixa salarial (alto, media ou baixa).

Analise exploratória:
>Para transformar os dados em gráficos através de identificação e separação de variáveis categóricas, as qualitativas: nominais (nivel educacional, estado civil, resposta campanha) e ordinais (faixa salarial, faixa etária) categorias numéricas: discretos (idade, total de filhos, salário em dólar) contínuos (ainda não se aplica nesta análise.
>Cálculo do quartil para aplicação de segmentação:  uso da =QUARTIL para gerar uma nota numérica que será o limite para cada 1/4  de clientes. Usando essas valores a atribuição desses quartis foram aplicados em recencia, valor e frequencia para criação das notas de e frequencia a =IFS(celula ≤quartil 1; 1 celula ≤quartil 2; 2 celula ≤quartil 3; 3 celula ≤quartil 4; 4. foi usada, mas para o calculo da nota de recencia o quartil menor tem a nota mais alta pois indica que tem menos dias que não compra, ficando  =IFS(celula ≤quartil 1; 4 e assim por diante.

Análise RFM e apresentação dos dados :
> Necessária a criação de uma média entre nota de frequencia e valor para aplicação da segmentação, um cálculo de média foi usado para isso. PS: aqui surgiu uma variavel numérica continua, a média entre frequencia e valor e eu optei por deixar ela com os numeros quebrados mesmo pois muitos 1,5. 2,5. 3,5 ao que não senti necessidade de arredondar.
>Atribuição da segmentação por quartil através da =IFS( E (celula≥nota; celula≥nota); “segmentação”; foi necessário muitos ajustes manuais na fórmula através de testes para as atribuições funcionarem corretamente de acordo com as notas calculadas e atribuídas, senti necessidade de adicionar uma terceira variavel para "com potencial" porque ele estava sendo anulado. Descobri um erro na formula =IF no quartil que eu estava usando strings na nota e estava dando erro na segmentação (no quartil não), por ex no quartil 1 a formula foi de =IFS(W2<=71; "1"; pra W2<=71; 1;
> Seguindo o material base que usei pra seguimentar os dados, fez mais sentido por segmento fiel com frequencia/recencia mais alta de todos os outros seguimentos pois o cliente fiél seria o que sempre responde as campanhas, promoçoes, os que engajam. Ficando assim no topo do seguimento clientes com potencial a ser fidelizado e fies em último tendo a menor porcentagem de clientes.
>Uma nova análise exploratória : com a RMF calculada e segmentada tem mais dados para analisar e mais gráficos para gerar, nesse momento seleciono quais deles serão importantes mostrar para apresentar os dados e soluções encontrados. Usei o modelo de tipos de variáveis para segmentar os dados dos clientes em dados sociais e dados economicos. Com essa analise fechada e usando o parametro que escolhi para segmentae vi que realmente os clientes fiés são a minoria e resolvi apresentar como se fosse uma corrida pra "subir" eles, porém sem largar os que estão no topo e ao mesmo tempo estimular o potencial em jovens que são minoria mais acho promissor começar a investir neles de alguma forma, com foco na qualidade, quantidade não é qualidade principalmente perante um público AA.
> Para calculo do quartil e segmentação usei links externos importantes que se encontram no final desse documento, assim como os links da apresentação dos dados, slide e planilha gerados.
_________________________________________________________________________________________________________________________________________

Resultados e Conclusões:
Com a segmentação feita vemos que a fidelidade é realmente o maior problema mas em contrapartida os clientes com potencial para serem fidelizados esta no topo do escopo. Além disso a média de frequencia de 10 compras por cliente durante 2 anos pode ser melhorada.
Considerando as análises anteriores somadas a essa sugiro como foco para o público adulto e idoso:
Ofereçer um programa de fidelidade com os melhores produtos como premiação e recomendar outros bons produtos, aos promissores, aproxima-los da marca oferecendo testes gratuitos, por exemplo, de produtos infantis para os que têm filhos. Premição os campeões, para manter-los sempre comprando e quem sabe fidelizando com esses prêmios. Recomendar vinhos e queijos de maior valor para os fiéis mais idosos avaliarem e engajarem pois eles têm maiores salários.
Clientes que precisam de atenção e que não podem perder são sobretudo jovens e adultos:
Reativa-los, ofereçer aos jovens ofertas limitadas em produtos semelhantes aos que foram comprados anteriormente ou oferecer novos produtos parecidos, é bom construir um relacionamento que gere valor rapidamente, apesar de serem a minoria os jovens têm melhores salários que os adultos e indicam para outros jovens promissores futuramente podendo se tornarem um cliente fiel.

_________________________________________________________________________________________________________________________________________
Limitações/Próximos Passos:
Dificuldade sobre a forma mais eficiente e limpa de unificar as tabelas e ter um maior entendimento dos dados. 
Lentidão e travamento da planilha chegando a demorar 2hrs para me retornar o valor de uma formula simples. 
Exclusão de dados essenciais não recuperáveis por meio de histórico do arquivo. 
Dificuldade para formular valores para segmentação por quartil e fazer a formula funcionar corretamente nos dados.

Soluções: Estudar melhor forma de unificar a tabela antes de prosseguir com o projeto pois pode ser necessário exclusão de dados durante o processo. Otimização de softwares, hardwares, navegador e na própria planilha para que não haja lentidão no processo. Fazer copias imaculadas e copias de teste da planilha. 
Realizar mais testes de formula em planilhas testes para não arriscar os dados a planilha original.
_________________________________________________________________________________________________________________________________________
Links de interesse:
Planilha: [proj-1_thai_o-mercado](https://docs.google.com/spreadsheets/d/1FgHo30Yu-r-k_8_hDgnPQPx4jH0O1PM9WiUEjgwRleU/edit?usp=sharing) - Planilhas Google
Fonte de dados: https://drive.google.com/drive/folders/1ScPgRiUxdDVXZZARTZW6GjJS7kU2zsSL
Segmentação RFM usada: [RFM para conhecer seus clientes: o que é e como aplicar](https://mateusguerra.com.br/rfm-para-conhecer-seus-clientes/#segmentos) | Mateus Guerra 
Como fazer a pontuação por quartil:[ A análise RFM para segmentação de clientes](https://vidadeproduto.com.br/analise-rfm/#Pontuacao_por_Quartil) | Vida de Produto
