# Projeto de Machine Learning: Manutenção Preditiva

## 1. Objetivo

Este projeto tem como objetivo aplicar técnicas de Machine Learning para identificar possíveis falhas em máquinas com base em dados operacionais dos equipamentos.

A proposta é desenvolver e comparar modelos de classificação capazes de prever falhas, contribuindo para estratégias de manutenção preditiva, redução de paradas inesperadas e melhoria da confiabilidade operacional.

## 2. Dataset

Foi utilizado o **AI4I 2020 Predictive Maintenance Dataset**, disponibilizado pela UCI Machine Learning Repository.

**Fonte dos dados:** https://archive.ics.uci.edu/dataset/601/ai4i+2020+predictive+maintenance+dataset

O conjunto de dados contém informações operacionais das máquinas, incluindo:

- Temperatura do ar.
- Temperatura do processo.
- Velocidade de rotação.
- Torque.
- Desgaste da ferramenta.

A variável-alvo utilizada foi `Machine failure`, que indica a ocorrência ou não de falha na máquina.

- `0`: ausência de falha.
- `1`: ocorrência de falha.

## 3. Metodologia

O desenvolvimento do projeto foi realizado por meio das seguintes etapas:

1. Carregamento e compreensão do conjunto de dados.
2. Análise exploratória dos dados.
3. Verificação e tratamento dos dados.
4. Preparação das variáveis para a modelagem.
5. Separação dos dados em conjuntos de treinamento e teste.
6. Treinamento dos algoritmos de classificação.
7. Avaliação e comparação dos modelos.
8. Interpretação dos resultados e elaboração das conclusões.

O projeto utiliza a abordagem de **Machine Learning supervisionado**, com foco em classificação binária, pois a variável-alvo indica duas possibilidades: ocorrência ou ausência de falha.

## 4. Modelos utilizados

Foram utilizados quatro modelos para comparar o desempenho na identificação de falhas:

- **Dummy Classifier (Baseline):** modelo de referência utilizado para estabelecer um desempenho inicial.
- **Regressão Logística:** algoritmo de classificação utilizado como referência entre os modelos preditivos.
- **Árvore de Decisão:** algoritmo que utiliza regras de decisão para classificar os dados.
- **Random Forest:** algoritmo que combina várias árvores de decisão para produzir previsões.

## 5. Métricas de avaliação

Os modelos foram avaliados utilizando as seguintes métricas:

- **Acurácia (Accuracy):** proporção de previsões corretas em relação ao total de previsões.
- **Precisão (Precision):** proporção das previsões de falha que realmente correspondem a falhas.
- **Recall:** proporção das falhas reais identificadas corretamente pelo modelo.
- **F1-score:** média harmônica entre Precisão e Recall.
- **ROC-AUC:** avalia a capacidade do modelo de distinguir entre máquinas com falha e sem falha em diferentes limiares de classificação.

Como o conjunto de dados apresenta desbalanceamento entre as classes, a acurácia não deve ser utilizada isoladamente. O Recall, o F1-score e a ROC-AUC ajudam a compreender melhor o desempenho dos modelos na identificação de falhas.

## 6. Como executar

1. Acesse o notebook do projeto no Google Colab.
2. Execute as células na ordem apresentada, do início ao fim.
3. Aguarde a execução das etapas de carregamento, tratamento dos dados, treinamento e avaliação dos modelos.
4. Analise as tabelas, os gráficos e as métricas geradas para comparar o desempenho dos algoritmos.

**Observação:** os resultados apresentados neste README correspondem à execução realizada durante o desenvolvimento do projeto. Alterações nos dados, nas configurações ou no ambiente de execução podem influenciar os resultados.

## 7. Resultados e análise

### 7.1 Comparação dos modelos

A tabela apresenta os resultados obtidos pelos quatro modelos avaliados no projeto.

| Modelo | Acurácia | Precisão | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Baseline (Dummy Classifier) | 0.9660 | 0.0000 | 0.0000 | 0.0000 | 0.5000 |
| Regressão Logística | 0.8245 | 0.1418 | 0.8235 | 0.2419 | 0.9069 |
| Árvore de Decisão | 0.9585 | 0.4324 | 0.7059 | 0.5363 | 0.8456 |
| Random Forest | 0.9800 | 0.8889 | 0.4706 | 0.6154 | 0.9676 |

### 7.2 Interpretação dos resultados

O **Baseline (Dummy Classifier)** apresentou acurácia de 96,60%, mas obteve precisão, Recall e F1-score iguais a zero. Esse resultado demonstra que um modelo pode apresentar alta acurácia sem identificar corretamente as falhas, especialmente quando existe desbalanceamento entre as classes. A ROC-AUC de 0,5000 indica ausência de capacidade discriminatória acima do acaso.

A **Regressão Logística** apresentou Recall de 82,35% e ROC-AUC de 0,9069, indicando boa capacidade de discriminação entre as classes e a maior proporção de falhas reais identificadas entre os modelos avaliados. Entretanto, a precisão de 14,18% e o F1-score de 24,19% indicam dificuldade em equilibrar a detecção de falhas com a redução de falsos alarmes.

A **Árvore de Decisão** apresentou acurácia de 95,85%, precisão de 43,24%, Recall de 70,59%, F1-score de 53,63% e ROC-AUC de 0,8456. Seu desempenho foi intermediário em comparação com os demais modelos.

A **Random Forest** obteve a maior acurácia, de 98,00%, a maior precisão, de 88,89%, o maior F1-score, de 61,54%, e a maior ROC-AUC, de 0,9676. Esses resultados indicam uma excelente capacidade de discriminação entre as classes e o melhor equilíbrio entre precisão e Recall segundo o F1-score entre os modelos avaliados. Entretanto, seu Recall de 47,06% mostra que parte das falhas reais não foi identificada.

### 7.3 O que os resultados demonstram

Os resultados demonstram que a avaliação de modelos de Machine Learning deve considerar diferentes métricas, e não apenas a acurácia.

A Random Forest apresentou o melhor desempenho geral segundo a acurácia, a precisão, o F1-score e a ROC-AUC. Sua ROC-AUC de 0,9676 indica elevada capacidade de distinguir máquinas com falha de máquinas sem falha em diferentes limiares de classificação.

Por outro lado, a Regressão Logística apresentou o maior Recall, de 82,35%, identificando uma proporção maior das falhas reais no limiar utilizado. Essa característica pode ser importante em aplicações nas quais deixar de identificar uma falha representa um risco operacional significativo. Entretanto, sua baixa precisão indica a necessidade de avaliar o impacto dos falsos alarmes.

A diferença entre o Recall da Random Forest e sua ROC-AUC não representa necessariamente uma contradição: o Recall é calculado em um limiar específico, enquanto a ROC-AUC considera o desempenho em diferentes limiares.

### 7.4 Conclusão

O projeto permitiu aplicar as principais etapas de um fluxo de Machine Learning supervisionado, desde a preparação e análise dos dados até o treinamento, a avaliação e a interpretação dos modelos.

Entre os algoritmos avaliados, a Random Forest apresentou os melhores resultados gerais nas métricas de acurácia, precisão, F1-score e ROC-AUC, sendo uma alternativa promissora para a identificação de falhas em máquinas.

Entretanto, o Recall de 47,06% indica que ainda existe espaço para melhorar a identificação das falhas reais. A Regressão Logística, apesar de apresentar menor precisão, obteve o maior Recall entre os modelos avaliados.

Como próximos passos, recomenda-se investigar ajustes no limiar de classificação, avaliar a matriz de confusão e testar estratégias para melhorar a identificação das falhas, verificando o impacto dessas mudanças na quantidade de falsos alarmes.

Conclui-se que o Machine Learning apresenta potencial para apoiar estratégias de manutenção preditiva, desde que os modelos sejam avaliados de acordo com os objetivos operacionais e validados antes de uma eventual aplicação prática.
