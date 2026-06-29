# Análise Exploratória e Predição de NPS utilizando Ciência de Dados

## Objetivo do Projeto

Este projeto tem como objetivo analisar os principais fatores que influenciam a satisfação dos clientes por meio do Net Promoter Score (NPS), identificando os principais motivos que levam um cliente a se tornar um detrator e propondo uma solução preditiva baseada em Machine Learning para antecipar essa classificação antes da aplicação da pesquisa de satisfação.

Ao longo do projeto foram realizadas análises exploratórias orientadas ao negócio, buscando responder às seguintes perguntas:

- Quais fatores parecem mais críticos para a satisfação?
- O que mais gera detratores?
- Existe algum ponto de ruptura na experiência do cliente?
- Que tipo de cliente tende a apresentar NPS mais alto ou mais baixo?

Como etapa complementar, foi desenvolvido um modelo de Inteligência Artificial capaz de prever a categoria de NPS (Promotor, Neutro ou Detrator) a partir de informações operacionais da jornada do cliente.

---

## Descrição da Base de Dados

A base utilizada contém informações históricas referentes aos pedidos realizados pelos clientes, contemplando indicadores operacionais, logísticos e de atendimento.

As principais variáveis disponíveis são:

### Dados do cliente

- customer_id
- customer_age
- customer_region
- customer_tenure_months

### Dados do pedido

- order_id
- order_value
- items_quantity
- discount_value
- payment_installments

### Dados logísticos

- delivery_time_days
- delivery_delay_days
- freight_value
- delivery_attempts

### Atendimento ao cliente

- customer_service_contacts
- complaints_count
- resolution_time_days

### Indicadores de negócio

- repeat_purchase_30d
- csat_internal_score

### Variável alvo

- nps_score (0 a 10)

Durante a etapa de modelagem, o NPS foi transformado nas categorias oficiais:

- Promotor (9 e 10)
- Neutro (7 e 8)
- Detrator (0 a 6)

---

## Metodologia Utilizada

O projeto foi dividido em quatro etapas principais.

### 1. Tratamento dos Dados

- Importação da base
- Análise de valores ausentes
- Verificação de inconsistências
- Criação de novas variáveis
- Classificação do NPS

---

### 2. Análise Exploratória dos Dados (EDA)

Foi realizada uma análise exploratória orientada ao negócio, utilizando gráficos e indicadores para compreender o comportamento do NPS.

Entre as análises realizadas destacam-se:

- Distribuição do NPS
- Estatísticas descritivas
- Heatmap de correlação
- NPS por região
- NPS por atraso na entrega
- NPS por reclamações
- NPS por contatos com atendimento
- NPS por tempo de resolução
- NPS por recompra

Ao final da EDA foram identificados os principais fatores associados à satisfação dos clientes, evidenciando que problemas operacionais, especialmente atrasos na entrega e dificuldades no atendimento, possuem forte influência na formação de clientes detratores.

---

### 3. Modelagem Preditiva

Como proposta de aplicação prática da Ciência de Dados, foi desenvolvido um modelo supervisionado de classificação utilizando o algoritmo Random Forest Classifier.

Objetivo do modelo:

Prever se um cliente será:

- Promotor
- Neutro
- Detrator

antes mesmo da aplicação da pesquisa de satisfação.

As principais etapas foram:

- Seleção das variáveis explicativas
- Separação dos dados em treino e teste
- Treinamento do modelo
- Avaliação por meio de métricas de classificação
- Análise da importância das variáveis
- Simulação de novos clientes

---

### 4. Aplicação no Negócio

O modelo pode ser utilizado como ferramenta de apoio à tomada de decisão, permitindo identificar clientes com maior risco de insatisfação antes da realização da pesquisa de NPS.

Com essa informação, a empresa pode realizar ações preventivas, como:

- Priorizar entregas críticas
- Antecipar contatos com o cliente
- Agilizar a resolução de problemas
- Oferecer compensações comerciais
- Reduzir o número de detratores

---

## Principais Resultados

A análise demonstrou que os fatores mais relacionados à redução do NPS são:

- Atraso na entrega;
- Quantidade de reclamações;
- Número de contatos com o atendimento;
- Tempo para resolução de problemas.

Os resultados sugerem uma cadeia de eventos em que atrasos operacionais aumentam as reclamações, elevam a demanda por atendimento e reduzem significativamente a satisfação dos clientes.

Além disso, verificou-se que a região geográfica possui baixa capacidade explicativa para o NPS, indicando que a experiência do cliente é influenciada principalmente pela qualidade da operação.

## Tecnologias Utilizadas

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib

---

## Estrutura do Projeto

```
tech_challenge_1/
│
├── data/
│   └── desafio_nps_fase_1.csv
│
├── notebooks/
│   ├── analise_exploratoria_dados.ipynb
│   └── modelo_nps.ipynb
│
├── models/
│   └── modelo_random_forest_nps.pkl
│
├── README.md
│
└── requirements.txt
```

---

## Como Reproduzir os Resultados

### 1. Clone o repositório

```bash
git clone https://github.com/GabrielButti/tech_challenge_1.git
```

### 2. Acesse a pasta

```bash
cd tech_challenge_1
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

Ou instale manualmente:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

### 4. Execute os notebooks

1. Abra o Jupyter Notebook ou Google Colab.

```bash
jupyter notebook
```

2. Execute inicialmente o notebook de Análise Exploratória.

```
analise_exploratoria_dados.ipynb
```

3. Em seguida, execute o notebook de Modelagem Preditiva.

```
modelo_nps.ipynb
```
