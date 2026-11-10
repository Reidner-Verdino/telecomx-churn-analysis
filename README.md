# 📡 Telecom X — Análise e Previsão de Churn

Projeto de Data Science em duas partes, desenvolvido no Challenge Telecom X da [Alura](https://www.alura.com.br). O objetivo é entender por que os clientes cancelam o serviço e prever quais têm maior risco de evasão, para que a empresa possa agir antes do cancelamento.

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-ETL-150458?logo=pandas)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)

---

## 🗂️ Estrutura

| Parte | Conteúdo | Pasta |
|---|---|---|
| **1 — ETL e Análise Exploratória** | Extração via API, limpeza e tratamento dos dados, análise exploratória e recomendações | [`parte-1-etl-analise/`](parte-1-etl-analise/) |
| **2 — Modelo Preditivo** | Encoding, normalização, treino e avaliação de 3 modelos de classificação, importância das variáveis | [`parte-2-modelo-preditivo/`](parte-2-modelo-preditivo/) |

---

## 📊 Dados

- **7.043 clientes** e **20 variáveis** na base tratada (perfil, serviços contratados, contrato e cobrança)
- Variável alvo: `evasao` (cancelou ou não o serviço), com taxa de evasão de 31,5%

---

## 🤖 Resultado do modelo

| Modelo | Recall | F1-Score | AUC-ROC |
|---|---|---|---|
| ⭐ Regressão Logística (balanceada) | **71,2%** | **58,3%** | **0,76** |
| Random Forest | 59,8% | 56,3% | 0,76 |
| Árvore de Decisão | 69,9% | 56,9% | 0,71 |

A Regressão Logística foi escolhida por ter o melhor recall: ela identifica 71% dos clientes que de fato cancelaram, o que é o mais importante para uma ação de retenção.

---

## 🔍 Principais achados

- **Tipo de contrato:** a evasão chega a 45% nos contratos mensais, contra 10% nos de dois anos.
- **Tempo de casa:** clientes com menos de 12 meses cancelam quase o dobro (53% contra 28%).
- **Internet:** fibra óptica tem evasão de 40%, contra 27% no DSL.

---

## 🛠️ Tecnologias

Python · Pandas · NumPy · Matplotlib · Seaborn · Scikit-learn

---

## 🚀 Como executar

```bash
git clone https://github.com/Reidner-Verdino/telecomx-churn-analysis.git
cd telecomx-churn-analysis/parte-2-modelo-preditivo
pip install -r requirements.txt
jupyter notebook notebooks/TelecomX_Churn_Prediction.ipynb
```

Também é possível abrir os notebooks diretamente no [Google Colab](https://colab.research.google.com).

---

## 👤 Autor

**Reidner Verdino** · [GitHub](https://github.com/Reidner-Verdino)
