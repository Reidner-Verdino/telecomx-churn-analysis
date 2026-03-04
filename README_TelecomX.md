# 📡 TelecomX — Análise de Evasão de Clientes (Churn)

Projeto desenvolvido como parte do **Challenge 2 de Data Science** da [Alura](https://www.alura.com.br).

---

## 📌 Contexto

A **Telecom X** enfrenta um alto índice de cancelamentos e precisa entender os fatores que levam à perda de clientes. Como assistente de análise de dados, fui responsável por coletar, tratar e analisar os dados utilizando Python e suas principais bibliotecas, extraindo insights valiosos para que a equipe de Data Science possa avançar para modelos preditivos e desenvolver estratégias de retenção.

---

## 🎯 Objetivo

Realizar uma análise exploratória completa (EDA) do dataset de clientes da Telecom X, identificando padrões e fatores associados ao churn, e gerar um relatório com conclusões e recomendações estratégicas.

---

## 🗂️ Estrutura do Projeto

```
TelecomX-Churn/
├── TelecomX_BR.ipynb              # Notebook principal com toda a análise
├── README.md                      # Este arquivo
└── imagens/                       # Gráficos gerados (após executar o notebook)
    ├── grafico_distribuicao_evasao.png
    ├── grafico_evasao_categoricas.png
    ├── grafico_evasao_numericas.png
    ├── grafico_boxplot_numericas.png
    ├── grafico_correlacao.png
    └── grafico_dispersao.png
```

---

## 🔄 Etapas do Projeto (ETL + EDA)

| # | Etapa | Descrição |
|---|-------|-----------|
| 1 | **Extração** | Carregamento dos dados via API (JSON) com `requests` e `pd.json_normalize()` |
| 2 | **Conhecendo o Dataset** | Exploração de colunas, tipos e dicionário de dados |
| 3 | **Verificação de Inconsistências** | Nulos, duplicatas, erros de tipo e categorias inesperadas |
| 4 | **Tratamento de Dados** | Conversões, remoção de nulos, preenchimento de valores ausentes |
| 5 | **Contas Diárias** | Criação da coluna `Conta_Diaria` (Conta_Mensal / 30) |
| 6 | **Padronização** | Tradução de colunas e valores para português; criação de variáveis derivadas |
| 7 | **Análise Descritiva** | Médias, desvios e comparativos por grupo de evasão |
| 8 | **Distribuição da Evasão** | Gráfico de barras e pizza da variável alvo |
| 9 | **Variáveis Categóricas** | Evasão por contrato, internet, pagamento, gênero etc. |
| 10 | **Variáveis Numéricas** | Histogramas e boxplots de tempo, conta mensal e total gasto |
| 11 *(Extra)* | **Correlação** | Matriz de correlação e gráfico de dispersão |
| 12 | **Relatório Final** | Conclusões, insights e recomendações estratégicas |

---

## 📊 Visualizações Geradas

- **Pizza + Barras** — Proporção de clientes que evadiram vs. permaneceram
- **Barras agrupadas (×6)** — Evasão por variáveis categóricas (contrato, internet, pagamento...)
- **Histogramas (×3)** — Distribuição de tempo de contrato, conta mensal e total gasto por evasão
- **Boxplots (×3)** — Comparativo de variáveis numéricas entre grupos Sim/Não
- **Heatmap** — Matriz de correlação entre variáveis numéricas
- **Dispersão** — Conta Mensal × Tempo de Contrato colorido por Evasão

---

## 🛠️ Tecnologias Utilizadas

| Biblioteca | Uso |
|---|---|
| `Python 3.x` | Linguagem principal |
| `Pandas` | Manipulação e análise de dados |
| `NumPy` | Cálculos numéricos |
| `Matplotlib` | Visualizações |
| `Seaborn` | Heatmap de correlação |
| `Requests` | Requisição à API |

---

## 🚀 Como Executar

### Opção 1 — Google Colab (recomendado)
1. Acesse [colab.research.google.com](https://colab.research.google.com)
2. Faça upload do arquivo `TelecomX_BR.ipynb`
3. Execute todas as células: `Runtime → Run all`

### Opção 2 — Localmente

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/telecomx-churn.git
cd telecomx-churn

# Instale as dependências
pip install pandas numpy matplotlib seaborn requests

# Abra o Jupyter
jupyter notebook TelecomX_BR.ipynb
```

---

## 🔍 Fonte dos Dados

Os dados são carregados diretamente da API oficial do desafio:

```
https://raw.githubusercontent.com/ingridcristh/challenge2-data-science/main/TelecomX_Data.json
```

**Estrutura do JSON:** aninhada em objetos `customer`, `phone`, `internet` e `account`.

### Dicionário de Dados

| Coluna | Descrição |
|--------|-----------|
| `ID_Cliente` | Identificador único do cliente |
| `Genero` | Gênero do cliente |
| `Idoso` | Se o cliente é idoso (1 = Sim, 0 = Não) |
| `Parceiro` | Se possui cônjuge/parceiro |
| `Dependentes` | Se possui dependentes |
| `Meses_Contrato` | Tempo de contrato em meses |
| `Servico_Telefone` | Possui serviço telefônico |
| `Multiplas_Linhas` | Possui múltiplas linhas |
| `Servico_Internet` | Tipo de internet (DSL, Fibra Ótica, Não) |
| `Seguranca_Online` | Possui segurança online |
| `Backup_Online` | Possui backup online |
| `Protecao_Dispositivo` | Possui proteção de dispositivo |
| `Suporte_Tecnico` | Possui suporte técnico |
| `Streaming_TV` | Possui streaming de TV |
| `Streaming_Filmes` | Possui streaming de filmes |
| `Tipo_Contrato` | Mensal, Anual ou Bienal |
| `Fatura_Digital` | Recebe fatura digital |
| `Metodo_Pagamento` | Forma de pagamento |
| `Conta_Mensal` | Valor cobrado mensalmente (R$) |
| `Total_Gasto` | Total acumulado pelo cliente (R$) |
| `Evasao` | ⚠️ **TARGET** — Se cancelou o serviço (Sim/Não) |

---

## 🔑 Principais Insights

| Fator de Risco | Impacto na Evasão |
|---|---|
| Contrato Mensal | 🔴 Muito Alto |
| Internet Fibra Ótica | 🔴 Alto |
| Menos de 12 meses de contrato | 🔴 Alto |
| Conta mensal elevada | 🟠 Moderado |
| Pagamento via Cheque Eletrônico | 🟠 Moderado |
| Poucos serviços contratados | 🟡 Relevante |

---

## ✅ Recomendações

1. Incentivar migração de contratos mensais para anuais/bienais com descontos.
2. Criar programa de retenção ativo nos primeiros 6 meses de contrato.
3. Investigar a satisfação com o serviço de Fibra Ótica.
4. Estimular cross-sell de serviços adicionais para aumentar o engajamento.
5. Migrar clientes para formas de pagamento automáticas.

---

## 👤 Autor

Desenvolvado como parte do Challenge 2 — Alura | Data Science

---

*© 2025 — Projeto educacional sem fins lucrativos*
