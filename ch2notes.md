# Chapter 2 
Supervised Machine Learning Algorithms
- [x] Some sample dataset
- [x] k-Nearest Neighbors
- [x] Linear models
- [x] Naive Bayes Classifiers
- [x] Decision trees
- [x] Ensembles of decision trees
- [x] Kernelized support vector machines
- [ ] Neural networks (deep learning)

Uncertainty estimates from classifiers
- [ ] The decision function
- [ ] Predicting probabilities
- [ ] Uncertainty in multiclass classification

## Supervised Machine Learning Algorithms
### Naive Bayes Classifiers
- No ipynb required.

These models learn parameters by looking at each feature individually and collect simple per-class statistics from each feature. They are faster in training than linear models, but they are worse in generalization.

There are three types of naive Bayes classifiers in scikit-learn:
- GaussianNB (for continuous data)
- BernoulliNB (assumes binary data). Counts how often every feature of each class is not zero.
- MultinomialNB (assumes count data)

MultinomialNB and BernoulliNB have a single parameter called alpha, which controls the complexity of the model. A large alpha means a less complex model.

GaussianNB se usa más comúnmente para datos de altas dimensiones.

### Decision Trees
- Los árboles de decisión son muy usados para tareas de regresión y clasificación. Básicamente, estos modelos aprenden de acuerdo con declaraciones if-else.

**Controlling complexity of decision trees**

### Ensembles of Decision Trees
- Los ensambles son métodos que combinan múltiples modelos de ML para crear mejores modelos. Los dos ensambles más usados para un amplio rango de datos para clasificación y regresión son:
  - Random forests
  - Gradient boosted regression trees

#### Random forests
- Decision trees tend to overfit the training data. Random forests are one way to address this problem.
- A random forest is a collection of decision trees.
- To build a tree, first take a *bootstrap sample* of the data. The decision tree is then build on the bootstrap sample.
- A critical parameter for the creation of the random forest is **max_features**.
- In real applications, often hundreds or thousands of trees are used for random forests.

#### Gradient boosted regression trees
- Despite its name, these models can be used for regression and classification.
- Combines multiple decision trees to create a more powerful model.
- A diferencia del random forest, el gradient boosting crea los árboles de forma secuencial, intentando corregir los errores de los anteriores.
- Gradient boosted usa árboles pequeños, con profundidad de 1 a 5.

### Kernelized SVM
- En español, SVM se podría escribir como Máquina de Soporte Vectorial.
- Las kernelized sería lo mismo: Máquinas de Soporte Vectorial con Kernel.
- Los modelos lineales tienen ciertas desventajas en espacios de bajas dimensiones. Por ejemplo, un modelo lineal para clasificación solo puede separar puntos usando una línea.
  - Se pueden añadir parámetros no lineales para mejorar los modelos lineales. Esto expande el conjunto de atributos de entrada tomando, por ejemplo, uno de los atributos, atr1, y tomando atr1^2 como una nueva característica. 
    - El *kernel trick* es una técnica para hacer lo anterior: cálcula los productos escalares de los data points para la representación expandida de atributos, sin calcular realmente la expansión.
    - Existen dos formas de mapear los datos a un espacio de altas dimensiones:
      1. Kernel polinómico.
      2. Kernel de función de base radial o Kernel Gaussiano.
          -  El parámetro gamma controla el ancho del kernel Gaussiano, lo cual determina la escala que da el significado de cercanía entre puntos.
             -  Low gamma implica low complexity.
          -  El parámetro C es un parámetro de regularización. Límita la importancia de cada punto.
             -  C pequeño significa un modelo muy restrictivo.
- Durante el entrenamiento, la SVM aprende cuales son los datos importantes para la frontera de decisión entre dos clases. Solo un conjunto de todos los datos son los más relevantes: los que yacen en el borde entre las clases. Tales puntos se conocen como *vectores de soporte*, de ahí el nombre de máquinas de soporte vectorial.
- SVM son muy sensitivas al ajuste de los parámetros y a la escala de los datos. En particular, SVMs requieren que todas las cracterísticas varien en una escala similar. Si este no es el caso, los datos tienen que llevar un proceso previo.
  - Un método para reescalar los datos en kernelized SVMs, es que todos los atributos tengan valores entre 0 y 1.
#### Fortalezas y debilidades
- Kernelized SVMs permiten fronteras de decisión complejas, aún si los datos tienen pocos atributos.
- Son eficientes para bajas y altas dimensiones, es decir, para datos con muchos y pocos atributos.
- No son muy buenos para grandes cantidades de datos.
- Una desventaja es que requieren un cuidado particular para el preprocesamiento de los datos y el ajuste de los parámetros. Es por esto que en su lugar se usan decision trees y random forests. 
- Es difícil entender por qué una predicción en particular es la que es.

### Neural Networks (Deep Learning)
- *Multilayer perceptrons* (MLPs) o en español, ...
- MLPs también son conocidos como (vanilla) feed-forward neural networks, or just neural networks (redes neuronales).
- MLPs se pueden entender como una generalización de los modelos lineales que realizan múltiples etapas de procesamiento para llegar a un resultado.


## Uncertainty estimates from classifiers



