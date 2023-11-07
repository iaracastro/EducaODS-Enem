## Análise dos Dados do ENEM e ODS em Educação
Este repositório é dedicado à análise dos dados do Exame Nacional do Ensino Médio (ENEM) em relação aos Objetivos de Desenvolvimento Sustentável (ODS) no contexto da educação. Aqui, exploramos diversos aspectos, desde fatores socioeconômicos até diferenças regionais e de diversidade.

### Objetivos:
- Investigar as disparidades educacionais no Brasil utilizando os dados do ENEM.
- Relacionar o desempenho no exame com os ODS em educação.
- Fornecer insights para políticas públicas voltadas para a educação.

### Ideias da Análise:
- Desempenho por região e correlação com indicadores socioeconômicos.
- Diversidade de gênero e áreas de conhecimento.
- Acessibilidade e desempenho de candidatos com deficiência.

## Extração de Dados:
Através da plataforma do INEP: https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados e baixamos os Microdados do Enem 2022. Daí, haviam 4 pastas:

- DADOS
- DICIONÁRIOS
- INPUTS
- LEIA-ME E DOCUMENTOS TÉCNICOS
- PROVAS E GABARITOS

Na primeira pasta, haviam os csv's com os dados do ENEM 2022 EM "MICRODADOS_ENEM_2022.csv", onde temos as informações de cada candidato por número de inscrição das colunas descritas na pasta de dicionários. E os arquivos com as respostas dos estudantes em "QUEST_HAB_ESTUDO.CSV" do questionário sobre os hábitos de estudo na pandemia.

Na segunda pasta, havia o dicionário de variáveis na aba "MICRODADOS_ENEM_2022", o dicionário referente aos itens da prova como código da questão, área do conhecimento, se o item foi abandonado, níveis de dificuldade, entre outros na aba "ITENS_PROVA_2022" e por último havia o dicionário referente aos hábitos de estudo durante a pandemia na aba "QUEST_HAB_ESTUDO".

Na terceira pasta, havia alguns arquivos em .sas e .r para auxiliar na leitura dos dados. Que não utilizaremos.

Na quarta pasta, haviam os editais, informações sobre o cálculo da nota, a metodologia utilizada, a estrutura do exame, entre outros em PDF. Que também não nos aprofundaremos.

Na última pasta, temos os arquivos com as provas e gabaritos em PDF's que não serão utilizado.


## Limpeza de Dados:
Após uma leitura inicial dos dados, decidimos importar as seguintes colunas:

- 'NU_INSCRICAO'
- 'TP_FAIXA_ETARIA'
- 'TP_SEXO'
- 'TP_COR_RACA'
- 'TP_NACIONALIDADE'
- 'TP_ST_CONCLUSAO'
- 'TP_ANO_CONCLUIU'
- 'TP_ESCOLA'
- 'TP_ENSINO'
- 'IN_TREINEIRO',
- 'CO_MUNICIPIO_ESC'
- 'TP_PRESENCA_CN'
- 'TP_PRESENCA_CH'
- 'TP_PRESENCA_LC'
- 'TP_PRESENCA_MT'
- 'NU_NOTA_CN'
- 'NU_NOTA_CH'
- 'NU_NOTA_LC'
- 'NU_NOTA_MT',
- 'TP_STATUS_REDACAO',
- 'NU_NOTA_REDACAO'
- 'Q001'
- 'Q002'
- 'Q003'
- 'Q004'
- 'Q005'
- 'Q006'
- 'Q024'
- 'Q025'

A partir daí, começamos extraindo com Pandas os dados em "MICRODADOS_ENEM_2022.csv" que inicialmente continham 3.476.105 linhas e 76 colunas. Pelo fato dos dados serem muito grandes, analisamos o número de alunos que estiveram presentes nos dois dias de prova e que responderam o questionário sobre os hábitos de estudo durante a pandemia, através de um merge nos dois datasets de dados na coluna "NU_INSCRICAO" que é comum a ambos.

![teste](https://github.com/iaracastro/EDUCAODS-ENEM/blob/main/Imagens/pizza.png?raw=true)

