# Projeto de Machine Learning: Manutenção Preditiva

## 1. Objetivo

Este projeto tem como objetivo aplicar técnicas de aprendizado de máquina para identificar possíveis falhas em máquinas industriais, utilizando dados de temperatura, rotação, torque e desgaste de ferramentas.

## 2. Dataset

Foi utilizado o AI4I 2020 Predictive Maintenance Dataset, disponibilizado publicamente pelo UCI Machine Learning Repository.

Fonte: https://archive.ics.uci.edu/dataset/601/ai4i+2020+predictive+maintenance+dataset

## 3. Metodologia

O projeto contempla análise exploratória dos dados, verificação de valores ausentes e inconsistências, preparação das variáveis, divisão dos dados em treinamento e teste e validação cruzada estratificada.

## 4. Modelos avaliados

- Dummy Classifier (baseline)
- Regressão Logística
- Árvore de Decisão
- Random Forest

A Random Forest também é submetida à otimização de hiperparâmetros por GridSearchCV, utilizando o F1-score como critério de seleção.

## 5. Métricas

Os modelos são avaliados por precisão, recall, F1-score e ROC-AUC. A matriz de confusão é utilizada para examinar os erros de classificação.

## 6. Como executar

1. Abra o notebook no Google Colab.
2. Execute as células na ordem apresentada.
3. Certifique-se de que há acesso à internet para baixar o dataset.
4. Consulte as tabelas, os gráficos e as conclusões produzidas pelo notebook.

## 7. Resultados e conclusão

Esta seção será preenchida após a execução dos experimentos, com os resultados obtidos, a comparação dos modelos, as principais variáveis identificadas e as limitações da análise.
