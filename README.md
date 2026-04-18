# 🛡️ Detecção de Fraudes em Transações com Machine Learning

Este repositório contém um **Desafio de Projeto** focado em resolver um dos problemas mais clássicos e críticos do mercado financeiro e de Data Science: a **Detecção de Fraudes em Cartões de Crédito**.

🔗 O repositório foi construído focado em boas práticas de Ciência de Dados, Engenharia de Recursos (Feature Engineering) e otimização de métricas avançadas para dados altamente desbalanceados.

---

## 🎯 O Problema e o Objetivo
As fraudes em cartões de crédito representam uma parcela minúscula do total de transações diárias (geralmente menos de 0.2%). O grande desafio para os modelos de Machine Learning é aprender a diferenciar uma transação genuína de uma fraudulenta quando temos **pouquíssimos exemplos de fraudes** para aprender.

Se o modelo chutar que "tudo é normal", ele terá 99,8% de "Acurácia", mas na prática, falhará no seu único objetivo: encontrar a fraude. 
Portanto, o **objetivo deste projeto** é maximizar a métrica de **Recall** e **AUC** desenvolvendo modelos de previsão robustos que diminuam os Falsos Negativos (fraudes que passaram despercebidas).

---

## 🛠️ Tecnologias e Ferramentas Utilizadas
- **Linguagem:** Python 3.x
- **Ambiente:** Jupyter Notebook
- **Manipulação e Análise de Dados:** `pandas`, `numpy`
- **Machine Learning e Pipelines:** `scikit-learn`, `imbalanced-learn` (SMOTE)
- **Modelos Avançados:** `xgboost` (XGBClassifier), Random Forest, Logistic Regression
- **Visualização:** `matplotlib` e métricas de curva (ROC e Precision-Recall)

---

## 🧠 Metodologia e Abordagem

Para garantir que o modelo não sofresse com vazamento de dados (*data leakage*) e fosse capaz de generalizar, o projeto seguiu o seguinte fluxo:

1. **Feature Engineering e Limpeza:** 
   - Exclusão de features ruidosas (como a coluna `Time`).
   - Aplicação de `np.log1p` aliado ao `StandardScaler` na variável `Amount` (valor transacionado).
2. **Definição de Métricas Corretas:** 
   - A métrica base do projeto foi substituída de *Accuracy* para **Recall**, **F1-Score** e a área sob a curva **AUC**.
3. **Lidando com Classes Desbalanceadas:**
   - Implementação de **SMOTE** (Synthetic Minority Over-sampling Technique) para criação de dados sintéticos da classe minoritária.
   - *Ponto de Destaque Técnico:* O SMOTE foi aplicado rigorosamente **apenas aos dados de treino** (`x_train`, `y_train`), preservando a pureza dos dados de teste para validação real.
4. **Modelagem:**
   - Criação de um modelo base (*Baseline*) usando **Logistic Regression** e customização manual do *Threshold* de predição de probabilidade.
   - Utilização de **Modelos de Árvore e Ensemble** com destaque para o **XGBoost (Extreme Gradient Boosting)** otimizado com a métrica `logloss`.

---

## 🚀 Como visualizar ou executar o projeto

1. Clone o repositório para o seu ambiente local:
   ```bash
   git clone https://github.com/Douglas-Luiz-de-Oliveira-Rodrigues/deteccao-de-fraudes-em-transacoes.git
   ```
2. Instale as dependências (recomendado o uso de um ambiente virtual):
   ```bash
   pip install pandas numpy scikit-learn imbalanced-learn xgboost matplotlib 
   ```
3. Abra o arquivo `deteccao_de_fraudes_em_transacoes.ipynb` pelo Jupyter Notebook ou VS Code e execute as células sequencialmente.

---

## 👨‍💻 Autor

- **Douglas Luiz de Oliveira Rodrigues**
- [LinkedIn](https://www.linkedin.com/in/dlorodrigues/)
- [GitHub](https://github.com/Douglas-Luiz-de-Oliveira-Rodrigues)

---
> Projeto construído como portfólio de Data Science, focado em aplicação prática com dados do mundo real.