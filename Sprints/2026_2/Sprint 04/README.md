# Classificação da Produção de Energia Renovável com Modelo Linear

**Challenge Sprint 4 – Modelagem Linear para Aprendizado de Máquina**

## Integrantes

| Nome | RM |
|---|---|
| Felipe Pereira Restivo | 570712 |
| Gabriel Rodrigues Zappelloni | 572060 |
| Kenichi Caio Yamamoto | 569815 |
| Maykon de Lima Silva | 574022 |
| Rodger Costa Rios | 571438 |

## Vídeo de apresentação

[Assista no YouTube](COLE_AQUI_O_LINK_DO_VIDEO)

---

## Sobre o projeto

Este projeto classifica a produção de energia renovável em três categorias (**Low**, **Medium** e **High**) usando a **Regressão Logística**, um modelo de classificação linear do scikit-learn. O desempenho do modelo foi comparado em dois cenários de divisão dos dados:

- **Cenário 1:** 60% treino / 40% teste
- **Cenário 2:** 85% treino / 15% teste

**Dataset:** [Renewable Energy Production Dataset (2010–2020)](https://www.kaggle.com/datasets/itsrohithere/renewable-energy-production-dataset-2010-2020/data), com 1000 registros e 11 colunas.

## Estrutura do repositório

| Arquivo | Descrição |
|---|---|
| `MLAM_SPRINT_04.ipynb` | Notebook com todo o código, os resultados e as análises |
| `Renewable_Energy_Data.csv` | Base de dados utilizada |
| `imagens/matriz_correlacao.png` | Matriz de correlação |
| `imagens/matriz_confusao_cenario1.png` | Matriz de confusão do Cenário 1 |
| `imagens/matriz_confusao_cenario2.png` | Matriz de confusão do Cenário 2 |
| `imagens/metricas.csv` | Acurácia, precisão e recall dos dois cenários |
| `imagens/variacao_acuracia.csv` | Variação da acurácia em 30 divisões diferentes dos dados |

## Como executar

1. Abra o notebook no [Google Colab](https://colab.research.google.com/).
2. Envie o arquivo `Renewable_Energy_Data.csv` pelo ícone de pasta na barra lateral.
3. Vá em **Ambiente de execução → Executar tudo**.

Bibliotecas utilizadas: `pandas`, `matplotlib`, `seaborn` e `scikit-learn`, todas já instaladas no Colab.

---

## Etapas e resultados

### 1. Análise do dataset

A variável-alvo `Energy_Class` foi convertida para números respeitando a ordem das classes (Low = 0, Medium = 1, High = 2). Em seguida, construímos a matriz de correlação entre as features numéricas e a classe.

![Matriz de correlação](imagens/matriz_correlacao.png)

Apenas a `Efficiency_Ratio` mostrou alguma correlação com a classe (0,21). Mesmo assim, optamos por usar **todas as features numéricas**: ao testar o modelo retirando uma feature por vez, vimos que algumas delas, mesmo com correlação quase nula, ajudam na classificação quando combinadas com as outras. Por exemplo, sem a `Temperature_C`, a acurácia cai de 79,0% para 73,8%.

### 2. Modelo

A **Regressão Logística** é um modelo linear porque sua decisão se baseia em uma soma ponderada das features. Por isso, a fronteira que separa as classes é sempre reta: uma reta, um plano ou um hiperplano, dependendo do número de features. Antes do treinamento, as features foram padronizadas com o `StandardScaler`, para ficarem na mesma escala.

Os dois cenários usaram as mesmas condições (mesmas features, mesmo modelo, `random_state=42` e divisão estratificada). A única diferença foi o tamanho do conjunto de teste.

### 3. Avaliação

| Cenário | Acurácia | Precisão (macro) | Recall (macro) |
|---|---|---|---|
| Cenário 1 (60/40) | 79,0% | 81,5% | 72,1% |
| Cenário 2 (85/15) | 78,0% | 77,3% | 73,2% |

Como referência, um modelo que sempre respondesse a classe mais comum (High) acertaria **48,6%**.

**Recall por classe:**

| Classe | Cenário 1 | Cenário 2 |
|---|---|---|
| Low | 52% | 63% |
| Medium | 67% | 62% |
| High | 97% | 95% |

| Cenário 1 (60/40) | Cenário 2 (85/15) |
|---|---|
| ![Matriz de confusão – Cenário 1](imagens/matriz_confusao_cenario1.png) | ![Matriz de confusão – Cenário 2](imagens/matriz_confusao_cenario2.png) |

**Variação em 30 divisões diferentes dos dados:**

| Cenário | Média | Desvio padrão | Mínimo | Máximo |
|---|---|---|---|---|
| Cenário 1 (60/40) | 79,2% | 3,4 p.p. | 70,8% | 84,2% |
| Cenário 2 (85/15) | 80,0% | 2,8 p.p. | 74,0% | 86,0% |

## Conclusão

A Regressão Logística alcançou cerca de **79% de acurácia**, bem acima da referência de 48,6%, com resultados semelhantes nos dois cenários. Ao repetir os experimentos com 30 divisões diferentes, as médias ficaram muito próximas, o que indica que, neste dataset, a proporção entre treino e teste teve pouco impacto no resultado.

A principal limitação do modelo é a classe **Low**, que tem menos exemplos e é frequentemente confundida com a classe Medium. Para melhorar esse resultado, poderiam ser testados modelos não lineares ou técnicas para equilibrar as classes durante o treinamento.
