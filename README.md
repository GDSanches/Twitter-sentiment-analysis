# Twitter-sentiment-analysis

Nessa atividade, o objetivo foi desenvolver um modelo para analisar o sentimento de tweets sobre o IFG, classificando-os em três categorias de polaridade: positivo (1), negativo (-1) e neutro (0). Para isso, utilizei o dataset disponível em scanuto.com/IFG.csv e apliquei técnicas de pré-processamento e classificação para avaliar o desempenho de diferentes modelos.

## Pré-processamento dos dados
O primeiro passo foi realizar o pré-processamento dos tweets. Utilizei a técnica de TfIdfVectorizer, que transforma o texto em uma matriz de características. O TF-IDF (Term Frequency-Inverse Document Frequency) é uma técnica comum para representação de texto, que ajuda a identificar a importância relativa de cada palavra em relação a um corpus de documentos. A parametrização padrão foi utilizada, sem ajustes extras.

## Modelos de Classificação
Em seguida, apliquei três modelos de classificação para prever o sentimento dos tweets:

kNN (k-Nearest Neighbors): O kNN foi configurado com a distância euclidiana, uma métrica simples que calcula a proximidade entre os pontos no espaço vetorial.

Árvore de Decisão: A árvore de decisão é um modelo baseado em uma estrutura hierárquica de decisões binárias, onde o objetivo é dividir os dados em regiões que agrupam instâncias com características semelhantes.

Random Forest: Utilizei o Random Forest, que consiste em um conjunto de árvores de decisão, buscando aumentar a robustez e precisão do modelo.

## Ajuste de Hiperparâmetros
Para melhorar a performance de cada classificador, ajustei os hiperparâmetros de cada modelo. Para o kNN, testei diferentes valores de k (quantidade de vizinhos) e diferentes métricas de distância. Na Árvore de Decisão, busquei ajustar o máximo de profundidade da árvore e o critério de divisão dos nós. Para o Random Forest, ajustei o número de árvores (n_estimators) e a profundidade máxima das árvores.

A validação cruzada em 5 dobras (5-fold cross-validation) foi realizada para cada modelo, garantindo que os ajustes de parâmetros fossem realizados de forma robusta, minimizando o risco de overfitting e proporcionando uma avaliação mais confiável da performance.

Avaliação dos Modelos
Após a validação cruzada, calculei as métricas de desempenho para os três modelos. As métricas utilizadas foram:

Precisão: A proporção de tweets classificados corretamente como positivos, negativos ou neutros.
Revocação: A proporção de tweets realmente positivos, negativos ou neutros que foram corretamente identificados.
Macro-F1: A média da pontuação F1 para cada classe, sem levar em conta o número de instâncias em cada classe. A pontuação F1 é a média harmônica entre precisão e revocação.
Acurácia: A proporção de acertos totais (tanto positivos, negativos quanto neutros).
Essas métricas são importantes porque oferecem uma visão mais completa do desempenho do modelo, levando em consideração diferentes aspectos da classificação.

## Matriz de Confusão e Curva ROC
Para uma análise mais detalhada, apresentei a matriz de confusão e a curva ROC dos métodos em um dos splits de validação cruzada. A matriz de confusão permite verificar quantos exemplos de cada classe foram corretamente ou incorretamente classificados. A curva ROC ajudou a avaliar a capacidade de cada modelo em discriminar as classes, com a área sob a curva (AUC) indicando a eficácia do modelo. Quanto maior a área, melhor o modelo se comporta em distinguir entre as classes.
