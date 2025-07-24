# Predição de Sintomas Osteomusculares em Docentes com Machine Learning

Este repositório contém o código e os dados do trabalho acadêmico intitulado **"Avaliação da Saúde Docente com Base em Dados de Pesquisa sobre Problemas Osteomusculares"**, desenvolvido como parte da disciplina de *Inteligência Computacional em Saúde* na **Universidade Federal do Espírito Santo (UFES)**.

O projeto tem como objetivo **prever a incidência de sintomas osteomusculares em professores da rede pública de Santa Catarina** utilizando técnicas de **Machine Learning**, com base em dados demográficos e ocupacionais coletados por meio do **Questionário Nórdico de Sintomas Osteomusculares**.

---

## Abstract

Este trabalho propõe um modelo de Machine Learning para predizer a incidência de sintomas osteomusculares em docentes, com base em dados demográficos e ocupacionais. Após pré-processamento e codificação *one-hot* de variáveis categóricas, sete classificadores supervisionados foram avaliados: **Decision Tree, SVM, Regressão Logística, Random Forest, KNN, Gaussian NB e MLPClassifier**. O modelo **Random Forest** destacou-se com a melhor acurácia no teste (81,8%) e maior F1-Score (0,769), demonstrando boa generalização e ausência de overfitting. A análise **SHAP** indicou que fatores como cidade, regime de trabalho e idade são os mais influentes na predição. Os resultados evidenciam o potencial do uso de modelos preditivos para apoiar ações preventivas na saúde docente.

---

## Estrutura do Repositório

---

## Video de apresentação
https://youtu.be/cfMIZJXhVaE

## Metodologia

### Dados
- Fonte: Dados fornecidos pelo Prof. Ricelli Endrigo Ruppel da Rocha (IFSC), coletados via **Questionário Nórdico de Sintomas Osteomusculares**.
- Tamanho: 218 registros válidos.
- Variáveis analisadas:
  - **Demográficas**: cidade, sexo, idade, estado civil, filhos, escolaridade.
  - **Ocupacionais**: tempo de atuação, vínculo de trabalho, carga horária semanal, turnos, número de alunos por turma, pluriemprego.
- Variável-alvo: `sintomas_osteomusculares` (Sim/Não).

### Pré-processamento
- Conversão de dados categóricos para numéricos.
- Aplicação de **One-Hot Encoding** para evitar hierarquias artificiais entre categorias.
- Divisão dos dados: 80% treino, 20% teste.

### Modelos Avaliados
1. Decision Tree
2. SVM (SVC)
3. Regressão Logística
4. Random Forest
5. KNN
6. Gaussian NB
7. MLPClassifier (Rede Neural)

### Avaliação
- Métricas: Acurácia, Precisão, Recall, F1-Score, Matriz de Confusão.
- Validação cruzada com `CV=15` para otimização de hiperparâmetros.
- Análise de explicabilidade com **SHAP**.

---

## Resultados

| Modelo | Acurácia (Teste) | F1-Score |
|--------|------------------|----------|
| **Random Forest** | **0.818** | **0.769** |
| SVM | 0.758 | 0.692 |
| Logistic Regression | 0.758 | 0.692 |
| Gaussian NB | 0.758 | 0.692 |
| KNN | 0.697 | 0.643 |
| MLPClassifier | 0.697 | 0.643 |
| Decision Tree | 0.727 | 0.640 |

 **Random Forest foi o melhor modelo**, com alta acurácia e bom equilíbrio entre precisão e recall.

---

## Principais Conclusões

- O **Random Forest** é o modelo mais eficaz para prever sintomas osteomusculares em docentes.
- Fatores ocupacionais como **pluriemprego, carga horária elevada e múltiplos turnos** são fortemente associados ao risco.
- A análise **SHAP** confirmou que variáveis como **cidade, regime de trabalho e idade** são as mais influentes.
- Modelos como **KNN e MLPClassifier** apresentaram **forte overfitting**, indicando que não generalizam bem para pequenos conjuntos de dados.
- O uso de **validação cruzada (CV=15)** foi crucial para ajuste de hiperparâmetros em um dataset pequeno.

---

## Como Reproduzir

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/saude-docente-ml.git
