# KNN e SVM para classificação da resistência à compressão do concreto por ultrassom

Esse programa usa os algoritmos de aprendizado supervisionado k-Nearest Neighbors e Support Vector Mechine para classificação da resistência à compressão do concreto a partir de dados de ensaios de Velocidade de Pulso Ultrassônico (VPU). O problema é formulado como classificação multiclasse, em que cada amostra é atribuída a uma faixa de resistência à compressão.

Referência da base de dados: MATTHEWS, B.; ALLAIX, D.; WIJTE, S.; VULLINGS, M.. Advancing non-destructive concrete compressive strength estimation: Large-Scale datasets and machine learning framework. **NDT & E International**, v. 158, 103549, 2026. 

 ## Bibliotecas necessárias

 O código requer as seguintes bibliotecas (disponíveis via pip):
 
 * numpy
 * matplotlib
 * pandas
 * scikit-lean
 * seaborn

 ## Instruções

 Para executar o código, basta executar as células do JupyterNotebook na sequência. A metodologia consiste em:

 - Pré-processamento: remoção de instâncias com atributos ausentes, codificação de variáveis categóricas e padronização via `StandardScaler`
- Divisão treino/teste: 70/30, estratificada
- Seleção de hiperparâmetros: `GridSearchCV` com validação cruzada estratificada de 10 partições (*10-fold*), otimizado por F1-score ponderado
- Métricas de avaliação: acurácia global, precisão, recall, F1-score por classe e matriz de confusão.