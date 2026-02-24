# Naive-Bayes-Spam-Classifier

Implementación de un sistema de filtrado de correo no deseado (SPAM) basado en modelos probabilísticos de Bayes Ingenuo. El proyecto utiliza el dataset Enron para entrenar y validar la capacidad de generalización del modelo frente a datos no vistos.

### Contribuciones y Evolución:

- **Optimización de Hiperparámetros**: Evaluación comparativa entre clasificadores de distribución Bernoulli y Multinomial, determinando que la frecuencia de términos (Multinomial) es más relevante para este dominio que la simple presencia/ausencia.
- **Ingeniería de Características**: Implementación de esquemas de *Bolsa de Palabras* y *Bigramas* ($ngram\_range=(1, 2)$) para capturar contextos semánticos (ej. "click here") que las palabras individuales ignoran.
- **Ajuste de Suavizado y Umbrales**: Aplicación de suavizado de Laplace ($\alpha = 0.003$) para evitar el problema de la probabilidad cero y configuración de un umbral de decisión extremo ($>0.999...$) para maximizar la precisión.

### Donde se analiza:

- **Dilema Precisión vs. Recall**: Se prioriza una precisión del **99.61%** para garantizar que ningún correo legítimo (HAM) se pierda, asumiendo un coste en el *recall* (algunos correos de SPAM se filtran a la bandeja de entrada).
- **Vulnerabilidad a Técnicas de Evasión**: Estudio de casos de *Bayesian Poisoning*, donde el atacante introduce términos neutros para diluir la probabilidad de SPAM y evadir el filtro.
- **Rendimiento Estadístico**: El modelo final alcanza un **F1-Score del 97.81%** en el conjunto de test (Enron6), demostrando una robustez alta frente a patrones comerciales complejos.

**Uso de tecnologías**: Python, Scikit-learn, Matplotlib (Curvas P-R), Pandas, Procesamiento de Lenguaje Natural (NLP).
