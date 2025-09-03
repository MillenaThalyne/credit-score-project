# Credit Score Project 💳 

## Documentação 🗒️
>**Autor**: Millena Thalyne <br>
>**Linguagem**: Python <br>
>**Curso**: Cientista de Dados EBAC

### Descrição 
O credit score é uma pontuação que mede a credibilidade financeira de uma pessoa com base em seu histórico de pagamentos, dívidas e uso de crédito. Ele serve para prever o risco de inadimplência e auxilia instituições financeiras a decidir sobre a concessão de crédito e definir condições de empréstimos. <br> O projeto que estou iniciando aborda esse tema, utilizando uma base de dados com informações de clientes para desenvolver um modelo preditivo capaz de estimar a probabilidade de um cliente se tornar inadimplente. <br> 
Esse notebook será separado em quatro partes: 
- **Bibliotecas e Leitura de Dados**: Bibliotecas Python utilizadas para rodar esse notebook, juntamente com a leitura da base de dados;
- **Pré-Processamento de Dados**: Realização de tratamento de nulos, tipagem e padronização de dados;
- **Análise de Dados**: Análise univariada das variáveis numéricas, análise bivariada entre duas variáveis a fim de responder algumas perguntas pertinentes nos nossos dados [3.2] e análise de correlação juntamente com a matriz de correlação dos dados em visualização "heatmap" (mapa de calor);
- **Separação de Bases de Treino e Teste**: Padronização de variáveis categóricas utilizando Label e One-Hot Encoders e separação das amostras de treino (70%) e teste (30%) para posterior utilização em modelo de Machine Learning. Além disso, também realizei o balanceamento da classe Credit Score utilizando o método de *Oversampling* SMOTE.

### Base de Dados
*   **Age** : Idade dos nossos clientes.

*   **Income** : Salário Mensal.

*   **Gender** : Gênero.

*   **Education** : Nível de escolaridade dos clientes.

*   **Marital** : Status Civilmente.

*   **Number of Children** : Quantidade de filhos.

*   **Home** : Tipo de residência, alugada ou própria.

*   **Credit Score** : Nossa variável preditora, o score de crédito dos clientes. <br>

[![Gráfico](https://img.shields.io/badge/Dados-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/dados/CREDIT_SCORE_PROJETO_PARTE1.csv)
## Pré-Processamento de Dados 🎲
Nessa etapa, foi desenvolvido o tratamento dos dados para nulos, tipagem e padronização. <br>
- **Nulos**: A única variável que precisou de tratamento foi a "Age" (idade), onde ela possuia 21% dos seus dados nulos. Com isso, para seu tratamento, realizei a substituição desses dados faltantes pela mediana dos dados, uma vez que a quantidade era consideravelmente alta e correria o risco de inviabilizar no resultado final;
- **Tipagem**: As variáveis que precisaram de ajustes foi a "Age" e "Income" (Idade e Renda). Para a variável de idade, precisou apenas transformar para o tipo inteiro, enquanto a de renda precisou seguir algumas etapas antes de transformar para o tipo flutuante, pois seus dados estavam registrados como caracter (exemplo, '50.000,00'). Por isso, primeiro foi necessário a exclusão das aspas simples e o ponto, e substituição da vírgula por ponto para, assim, poder realizar a transformação para tipo flutuante.
- **Padronização**: Essa etapa não foi realizada, pois não houve necessidade, uma vez que os registros estavam de acordo com o esperado.
## Análise de Dados 📊
Nessa etapa, foi realizado a análise das variáveis de maneira mais aprofundada, através da Análise Univariável, Bivaráda e de Correlação. 
- **Analisando Outliers**: Nessa análise, foi verificado um único ponto discrepante na variável Number of Children (número de filhos), porém não foi necessário tratamento, uma vez que não representa um erro, apenas um registro divergente dos demais; <br>
  [![Gráfico](https://img.shields.io/badge/Boxplots-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/boxplots%20numericos.png)
- **Análise Univariada**: Essa análise foi realizada nas variáveis numéricas Age, Income e Number of Children:
  - Number of Children: A partir da análise, foi notado que a maior concentração de clientes não possue filhos (59%), seguido por 1-2 filhos (19-18%) e 3 filhos (3%); <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/num%20filhos.png)
  - Age: Após essa análise, foi concluído que a maior concentração de clientes é entre 30-39 anos (51%), seguido pelas idades entre 40-49 (23%), 20-29 (19%) e 50+ (9%); <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/idades.png)
  - Income: A partir da análise, essa variável se mostrou bastante equilibrada e com um pico de registros na renda de R$80.000 e R$100.000, com média e mediana de aproximadamente R$84.000. <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/renda1.png)
- **Análise Bivariana**: Essa análise foi separada em algumas questões pertinentes na nossa base de dados, sendo elas respondidas, como:
  * Existe relação entre a idade e o status civil? - Sim, existe uma maior concentração de clientes *casados*, principalmente a partir dos 45 anos e tendo um pico aos 36 anos (23 pessoas); <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/idade%20e%20civil.png)
  * Qual a relação entre o score de crédito e o nível de escolaridade? - Existe uma concentração muito grande de pessoas com um Score de crédito alto nos níveis escolares Bacharel, Mestrando e Doutor, com foco nos mestres (36 pessoas); <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/escola%20e%20creditoscore.png)
  * O salário parece influenciar na idade? - Sim, de acordo com a análise, é uma relação forte, onde, conforme a idade aumenta, o salário tende a aumentar; <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/idade%20e%20renda.png)
  * O salário parece influenciar no Score de Crédito? - Sim, conforme o salário é maior, mais pessoas tendem a ter Score de crédito alto; <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/renda%20e%20creditscore.png)
  * Clientes com casa própria tendem a ter um score mais alto? - Sim, a concentração de pessoas com casa própria que possuem Score de crédito alto é muito maior que as que não possuem; <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/casa%20e%20creditscore.png)
  * O número de filhos influencia no score de crédito? - Aparentemente não, pois independente do número de filhos, pode-se encontrar diversas pessoas com Score de crédito alto. Porém, a concentração maior está naqueles que não possuem filhos (talvez por ser a classe com maior número de registros); <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/filhos%20e%20creditscore.png)
  * O número de filhos influencia no salário? - De acordo com a análise, não. Essas variáveis não possuem uma relação forte; <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/filhos%20e%20renda.png)
  * A educação tem relação no aumento do salário? - Sim, conforme o nível escolar aumenta, maior o salário. Tendo uma distribuição equilibrada para as pessoas com somente o ensino médio e o pico dos maiores salário em quem possue mestrado. <br>
  [![Gráfico](https://img.shields.io/badge/Visualização-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/renda%20e%20escola.png)
* **Análise de Correlação**: A *primeira* matriz de correlação mostrou que as relações mais fortes são entre as variáveis:
  * Credit Score ↔ Casa Própria: p = 0.855 
  * Renda ↔ Credit Score: p = 0.744 
  * Estado Civil ↔ Casa Própria: p = 0.708 
  * Renda ↔ Casa Própria: p = 0.705 <br>
  [![Gráfico](https://img.shields.io/badge/Matriz_1-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/matriz%20corr%201.png) <br>
Já na *segunda* matriz de correlação (após a realização do tratamento utilizando Label e One-Hot Encoders), tivemos as relações mais fortes entre:
  * Solteiro ↔ Alugada: p = 0.708 
  * Renda ↔ Alugada: p = -0.705 <br>
  [![Gráfico](https://img.shields.io/badge/Matriz_2-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/matriz%20corr%202.png)
## Treino e Teste & Balanceamento de Classe 👾
Nessa etapa, foi separada as bases de treino e teste, juntamente com o balanceamento da classe Credit Score, utilizando a função SMOTE, uma vez que a variável estava muito desbalanceada para a classe com alto Score de crédito (69% dos total). <br>
[![Gráfico](https://img.shields.io/badge/Proporção-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/proporcao%20classe.png) [![Gráfico](https://img.shields.io/badge/Distribuição-blue?style=flat&logo=bar-chart&logoColor=pink)](https://github.com/MillenaThalyne/credit-score-project/blob/main/visualiza%C3%A7%C3%B5es/distribuicao%20classe.png) <br>
Após o tratamento, a variável de Credit Score contou com 81 registros por classe.
