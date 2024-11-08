# Modelo de Predição de Doença do Coração

Este repositório contém o código e recursos necessários para construir um modelo preditivo de doença cardíaca usando técnicas de aprendizado de máquina. O modelo foi treinado com dados públicos e otimizado usando Grid Search e SMOTE para melhorar a precisão em um conjunto de dados desbalanceado. Após o treinamento, o modelo é exportado para o formato PMML, facilitando a implementação em sistemas de produção.

## 1. Descrição do Projeto

Este projeto busca prever a presença de doenças cardíacas em pacientes com base em vários fatores clínicos, como idade, colesterol, e resultados de testes. Utilizou-se árvore de decisão como algoritmo principal, aplicando Grid Search para encontrar a melhor combinação de hiperparâmetros e SMOTE para balanceamento dos dados.

## 2. Pré-Processamento dos Dados

O conjunto de dados original é carregado, e algumas etapas de pré-processamento são realizadas:

- Renomeação das colunas: para nomes mais intuitivos.
- Tratamento de valores categóricos: substituição de valores numéricos por rótulos textuais.
- Remoção de duplicatas e de valores inconsistentes (por exemplo, remoção de registros com valores inválidos na coluna avaliacaoTesteEsforco).
- Identificação e tratamento de outliers: remoção de outliers com base no IQR.
- As colunas são divididas em categóricas e contínuas, e gráficos são gerados para análise de distribuições e identificação de outliers.

## 3. Treinamento e Avaliação do Modelo

O modelo usa uma árvore de decisão, ajustada com os melhores hiperparâmetros determinados pelo GridSearchCV.

- Pipeline de pré-processamento: variáveis categóricas são codificadas com OneHotEncoder, e variáveis numéricas são padronizadas com StandardScaler.
- SMOTE: utilizado para balancear a distribuição da variável de saída.
- Validação cruzada: RepeatedStratifiedKFold é aplicado para garantir que o desempenho seja consistente.

A acurácia e outros indicadores de desempenho são exibidos, incluindo:

- Matriz de Confusão: para avaliação visual dos erros de classificação.
- Relatório de Classificação: com métricas detalhadas como precisão, recall e F1-score.

## 4. Exportação para PMML

O modelo treinado e o pipeline de pré-processamento são exportados para o formato PMML (modelo_heart_disease.pmml), permitindo fácil integração com sistemas de produção.