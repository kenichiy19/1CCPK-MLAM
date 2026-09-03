# Avaliação: Modelos de Classificação

Checkpoint 01 - Ciência da Computação | 1CCPK 2026

Disciplina: Modelagem Linear para Aprendizado de Máquinas


## 1. Título e Objetivo do Projecto
**Desenvolvimento de um Fluxo Completo de Classificação em Machine Learning**  
O objetivo deste trabalho é aplicar, analisar e comparar diferentes algoritmos de classificação do `scikit-learn` (Regressão Logística e Árvore de Decisão) seguindo rigorosamente as etapas de ciência de dados: desde a carga e inspeção inicial de um arquivo CSV até a validação, métricas de acurácia, matriz de confusão e interpretação de limitações.

---

## 2. Integrantes do Grupo e RMs
* **Felipe Pereira Restivo** — RM: `570712`
* **Gabriel Rodrigues Zappelloni** — RM: `572060`
* **Kenichi Caio Yamamoto** — RM: `569815`
* **Maykon de Lima Silva** — RM: `574022`
* **Rodger Costa Rios** — RM: `571438`

**Turma:** `1CCPK`  
**Data:** `02/09/2026`

---

## 3. Tema e Dataset Escolhidos (Exercício 3)
* **Tema Principal:** Detecção de Doença de Parkinson por Medidas de Voz (Biomédico / Saúde).
* **Dataset Escolhido:** **Parkinsons Data Set**, obtido do *UCI Machine Learning Repository*. O conjunto de dados é composto por uma gama de medidas de voz biométricas de 31 pessoas, sendo 28 com a doença de Parkinson.

---

## 4. Fonte dos Dados
* **Repositório Oficial:** [UCI Machine Learning Repository - Parkinsons Dataset](https://archive.ics.uci.edu/dataset/174/parkinsons)
* O arquivo correspondente foi disponibilizado e carregado via script Python como `parkinsons.data` (ou lido diretamente da URL oficial do repositório).

---

## 5. Descrição da Variável-Alvo
* A coluna alvo original identifica o status de saúde do paciente.
* No escopo da classificação binária:
  * `1` (ou classe positiva): Paciente diagnosticado com Doença de Parkinson.
  * `0` (ou classe negativa): Indivíduo saudável (sem Parkinson).

---

## 6. Etapas Realizadas na Implementação
O notebook estruturou o fluxo completo de ponta a ponta:
1. **Carga de Dados:** Importação do arquivo CSV utilizando `pandas`.
2. **Inspeção Inicial:** Verificação de dimensões, tipos de dados e uso de memória.
3. **Qualidade dos Dados:** Checagem de valores ausentes (`NaN`), percentuais e contagem de registros duplicados.
4. **Análise Exploratória (EDA):** Geração de estatísticas descritivas, análise da distribuição da variável-alvo e plotagem de gráficos com `matplotlib` e `seaborn`.
5. **Separação de Atributos:** Divisão em matriz de preditores (`X`) e vetor alvo (`y`).
6. **Divisão de Treino e Teste:** Amostragem estratificada (`train_test_split` com `test_size=0.25` e `random_state=42`) para preservar a proporção das classes.
7. **Pré-processamento:** Tratamento de nulos, conversão categórica e escalonamento numérico por meio de `Pipeline` e `ColumnTransformer`, evitando vazamento de dados (*data leakage*).
8. **Treinamento de Modelos:** Instanciação e ajuste dos algoritmos lineares e baseados em árvores utilizando `random_state=42`.
9. **Avaliação:** Cálculo da acurácia e construção das matrizes de confusão.
10. **Conclusão:** Interpretação dos resultados em Markdown e discussão sobre as limitações dos modelos.

---

## 7. Algoritmos Utilizados
* **Regressão Logística (`LogisticRegression`):** Modelo linear supervisionado utilizado para classificação binária.
* **Árvore de Decisão (`DecisionTreeClassifier`):** Modelo não-linear baseado em regras de divisão hierárquica dos dados.
* *(Ambos pertencentes estritamente à biblioteca `scikit-learn`)*.

---

## 8. Principais Resultados
* **Regressão Logística:** Apresentou excelente capacidade de generalização e maior estabilidade na separação das classes biométricas nesta divisão específica.
* **Árvore de Decisão:** Permitiu uma boa interpretação visual das regras de decisão, mas tendeu a apresentar leve sobreajuste (*overfitting*) em comparação ao modelo linear na ausência de restrições severas de profundidade.
* **Métricas:** Todas as acurácias obtidas foram devidamente acompanhadas por suas respectivas matrizes de confusão e interpretações textuais detalhadas em células Markdown.
