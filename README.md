# Previsão de Churn de Clientes em uma Empresa de Telecom

## Visão Geral do Projeto

Este projeto tem como objetivo principal prever a rotatividade (churn) de clientes de uma empresa de telecomunicações. A previsão de Churn é um desafio crucial para o negócio, pois permite que a empresa identifique clientes em risco de saída e implemente estratégias de retenção de forma proativa, otimizando recursos e aumentando a receita.

Para isso, foram construídos e comparados três modelos de machine learning - Árvore de Decisão, Random Forest e K-Nearest Neighbors (KNN) - para determinar qual deles oferece o melhor desempenho para a tarefa.

## Análise e Pré-processamento de Dados

A etapa inicial de exploração e tratamento dos dados foi fundamental. As principais ações realizadas foram:

* **Tratamento de Dados Categóricos:** Variáveis como tipo de contrato e serviço de internet foram convertidas em um formato numérico através da técnica de `One-Hot Encoding`.
* **Análise de Multicolinearidade:** Foi identificada uma forte correlação entre a variável `tenure` e `Charges.Total` (`0.8255`). Para evitar redundância e melhorar a performance dos modelos, as variáveis com alta multicolinearidade foram removidas.
* **Normalização de Dados:** Variáveis numéricas foram normalizadas para que tivessem a mesma escala, um passo essencial para o modelo KNN.

## Modelagem e Avaliação

Três modelos de classificação foram treinados e avaliados. O desempenho foi medido com base em métricas como acurácia, precisão e recall.

| Modelo | Acurácia | Precisão | Recall |
| :--- | :---: | :---: | :---: |
| Árvore de Decisão | `79,1%` | `60,9%` | `50,9%` |
| Random Forest | `80,5%` | `69,3%` | `47,2%` |
| KNN | `78,0%` | `61,2%` | `46,1%` |

### **Melhor Modelo**

O modelo **Random Forest** foi o mais robusto, apresentando a maior acurácia (`80,5%`) e a maior precisão (`69,3%`). Sua alta precisão o torna a melhor escolha para o negócio, pois minimiza o risco de gastar recursos de retenção em clientes que não iriam sair.

## Variáveis Mais Influentes

A análise de importância de features do modelo Random Forest revelou que as três variáveis mais importantes para prever o Churn são:

1.  **`tenure`**: O tempo de permanência do cliente na empresa. Clientes com maior tempo de contrato são menos propensos a dar Churn.
2.  **`Charges.Monthly`**: O valor da cobrança mensal. Contas mais altas estão correlacionadas com uma maior probabilidade de Churn.
3.  **`InternetService_Fiber optic`**: O tipo de serviço de internet. Clientes com serviço de fibra ótica apresentaram uma tendência maior a dar Churn.

## Como Usar o Projeto

1.  Clone este repositório para a sua máquina local.
2.  Instale as dependências usando `pip install -r requirements.txt`.
3.  Abra o notebook `Previsao_Churn_Telecom.ipynb` no Google Colab ou em seu ambiente de desenvolvimento preferido.
4.  Execute as células para reproduzir a análise e o treinamento dos modelos.
