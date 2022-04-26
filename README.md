## Média móvel de crianças internadas por Covid-19 e por SRAG no Ceará

Este repositório traz raspagem, tratamento e análise de dados de internação por Covid-19 e Síndrome Respiratória Aguda Grave (SRAG) em leitos infantis  de Enfermaria e UTI no Ceará a partir da API do IntegraSUS, plataforma da Secretaria da Saúde do Estado (Sesa). Os arquivos gerados foram utilizados na matéria [Ceará tem tem maior média de crianças internadas por síndromes respiratórias desde 2020](https://www.opovo.com.br/noticias/ceara/2022/04/26/ceara-tem-tem-maior-media-de-criancas-internadas-por-sindromes-respiratorias-desde-2020.html), publicada no Jornal O POVO no dia 26 de abril de 2022 e de autoria de Marcela Tosi, repórter do núcleo de Cotidiano.

--------------------------------------

### Fonte e coleta de dados:

- [Painel Histórico de Internações por SRAG / COVID-19](https://integrasus.saude.ce.gov.br/#/indicadores/indicadores-coronavirus/historico-internacoes-covid)

### Metodologia

Inicialmente, foram raspados os dados de internação por Covid-19/SRAG no Ceará desde o início do ano de 2020, salvos no arquivo `20220425_21h12m_dados_internacao_total.csv`. Em seguida, os dados foram filtrados pelos leitos infantis — foco desta análise — ativos e ocupados.

Calculou-se, então, a média móvel (7 dias) de leitos ativos e a média móvel (7 dias) de leitos ocupados — ou seja, de crianças efetivamente internadas —, com o objetivo de não se trabalhar apenas com a taxa de ocupação (apesar de também calcularmos esse valor), e evitar possíveis distorções pela variação causada pela abertura ou pelo fechamento de leitos ao longo dos dias.

### Arquivos gerados:

**_Dataframes_**
 - `20220425_21h12m_dados_internacao_total.csv`:  série histórica de leitos ativos e ocupados em Enfermaria e UTI voltadas para pacientes com Covid-19 e/ou SRAG, por dia, unidade de saúde e perfil de paciente, desde o início da pandemia de Covid-19 no Ceará até o dia 25 de abril de 2022;
 - `df_arquivo_leitos_infantis_grafico.csv`: série histórica de leitos infantis ativos e ocupados em Enfermaria e UTI voltados para Covid-19 e/ou SRAG, além da média móvel (7 dias) para cada um deles, por dia, desde o início da pandemia de Covid-19 no Ceará até o dia 25 de abril de 2022;
 - `df_filtro_omicron.csv`: dados relativos aos leitos infantis, com filtro de tempo entre 23 de dezembro de 2021, quando foi informado oficialmente que a variante Ômicron havia sido identificada no Ceará, até o dia 25 de abril de 2022;
 - `df_leitos_por_hospital.csv`: dados de internação infantil por Covid-19 e/ou SRAG no dia 25 de abril de 2022 com especificação das unidades de saúde.
 
 **_Visualização_**
- [Média móvel de crianças internadas por Covid-19 e por SRAG no Ceará](https://public.flourish.studio/visualisation/8576383/)

--------------------------------------

#### Como utilizar:

Para executar o notebook com a coleta e processamento dos dados, é necessário um ambiente com *Python3* e dependências que podem ser instaladas via [Pip](https://pypi.org/project/pip/): 
```{python}
!pip install pandas
!pip install simplejson
!pip install DateTime
!pip install plotly
```

### A central DATADOC

A Central de Jornalismo de Dados do O POVO (DATADOC) alia tecnologia e técnicas diversas de análises de dados para produzir um jornalismo de precisão para que você forme sua opinião com segurança. Nosso objetivo é fazer com que todos tenham acesso aos dados utilizados nas notícias que produzimos.

A DATADOC é composta por uma equipe de três jornalistas (sendo uma infografista), uma desenvolvedora front-end e um cientista da computação que coletam, enriquecem e disponibilizam as bases e códigos de cada reportagem para um jornalismo transparente e baseado em evidências.

 --------------------------------------
#### 🔥📰👩🏻‍💻 Se você gostou do nosso material, apoie assinando o OP+ e acompanhando o nosso trabalho.

#### 📝📨 Para feedback, dúvidas ou sugestões: datadoc@opovodigital.com

--------------------------------------
 
🗓️🕵🏻 Confira também outras produções recentes da central DATADOC: A reportagem ***Ceará ocupa a 24º posição nacional, em representatividade de gênero na política*** mostrou que, em relação a representatividade de gênero, o Ceará fica à frente apenas do Mato Grosso, Mato Grosso do Sul e Goiás. A matéria está [disponível no O POVO+](https://bit.ly/38qHm11).