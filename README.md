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

### 7.1 Comparação dos modelos

Os modelos de Machine Learning foram avaliados utilizando as métricas de acurácia, precisão, Recall, F1-score e ROC-AUC.

| Modelo | Acurácia | Precisão | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Baseline (Dummy Classifier) | 0.9660 | 0.0000 | 0.0000 | 0.0000 | 0.5000 |
| Regressão Logística | 0.8245 | 0.1418 | 0.8235 | 0.2419 | 0.9069 |
| Árvore de Decisão | 0.9585 | 0.4324 | 0.7059 | 0.5363 | 0.8456 |
| Random Forest | 0.9800 | 0.8889 | 0.4706 | 0.6154 | 0.9676 |

### 7.2 Interpretação dos resultados

O Baseline apresentou acurácia de 96,60%, mas não identificou corretamente nenhuma falha, conforme demonstrado pelas métricas de precisão, Recall e F1-score iguais a zero. Sua ROC-AUC de 0,5000 indica ausência de capacidade discriminatória acima do acaso.

A Regressão Logística apresentou Recall de 82,35% e ROC-AUC de 0,9069, demonstrando boa capacidade de distinguir máquinas com e sem falha e identificando a maior proporção de falhas reais entre os modelos avaliados. Entretanto, sua precisão de 14,18% e seu F1-score de 24,19% indicam dificuldades em equilibrar a detecção de falhas com a redução de falsos alarmes.

A Árvore de Decisão apresentou acurácia de 95,85%, precisão de 43,24%, Recall de 70,59%, F1-score de 53,63% e ROC-AUC de 0,8456, com desempenho intermediário nas métricas analisadas.

A Random Forest obteve a maior acurácia, de 98,00%, a maior precisão, de 88,89%, o maior F1-score, de 61,54%, e a maior ROC-AUC, de 0,9676. Esses resultados indicam excelente capacidade de discriminação entre as classes e um bom equilíbrio entre precisão e Recall em comparação com os demais modelos, embora seu Recall de 47,06% mostre que parte das falhas reais não foi identificada.

### 7.3 Conclusão

Os resultados demonstram o potencial da aplicação de técnicas de Machine Learning na manutenção preditiva. Entre os modelos avaliados, a Random Forest apresentou o melhor desempenho geral considerando acurácia, precisão, F1-score e ROC-AUC.

Apesar disso, a Regressão Logística apresentou o maior Recall, de 82,35%, identificando uma proporção maior das falhas reais, mas com maior quantidade de falsos alarmes.

Portanto, a escolha do modelo final depende das necessidades da aplicação. Em um cenário no qual deixar de identificar uma falha seja especialmente prejudicial, é importante priorizar a melhoria do Recall. Recomenda-se investigar ajustes de limiar de classificação, técnicas para lidar com o desbalanceamento das classes e validação adicional dos modelos antes de uma aplicação operacional.

O projeto permitiu aplicar as principais etapas de um fluxo de Machine Learning supervisionado, desde a preparação dos dados até o treinamento, a avaliação e a interpretação dos resultados.
