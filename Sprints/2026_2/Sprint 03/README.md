# Análise Estatística e Regressão Linear: Escolaridade vs. Expectativa de Vida

**Sprint 03 - Ciência da Computação | 1CCPK 2026**

**Disciplina:** Modelagem Linear para Aprendizado de Máquinas

## Visão Geral

Este repositório contém o projeto acadêmico de Estatística e Ciência de Dados desenvolvido para analisar a relação entre a escolaridade média da população (`Schooling`) e a expectativa de vida (`Life expectancy`) de diferentes países.

O objetivo principal do trabalho é conectar conceitos da estatística descritiva e inferencial à construção e interpretação de um modelo preditivo de Aprendizado de Máquina Supervisionado.

## Estrutura do Projeto

O projeto foi desenvolvido em um único arquivo no Google Colab, dividido em 4 etapas práticas:

| Seção | Conteúdo |
|---|---|
| Questão 01 | Probabilidade de valores acima da mediana (Distribuição Normal) |
| Questão 02 | Probabilidade no intervalo média ± 2 desvios-padrão |
| Questão 03 | Modelagem de Regressão Linear Simples (Schooling x Life expectancy) |
| Questão 04 | Organização, clareza e interpretação geral dos resultados |

## Principais Resultados

- **Tamanho da Amostra:** 2938 registros (2768 após tratamento de valores nulos nas colunas utilizadas)
- **Média da Expectativa de Vida:** 69,22 anos
- **Desvio-Padrão:** 9,52 anos
- **Coeficiente de Correlação de Pearson (r):** 0,752 (forte associação linear)
- **Equação da Reta Preditiva:** Expectativa de Vida = 44,11 + 2,10 × Escolaridade
- **Coeficiente de Determinação (R²):** 0,5655 (56,55% de variância explicada)

## 🛠️ Tecnologias Utilizadas

- **Linguagem:** Python 3.x
- **Ambiente:** Google Colab / Jupyter Notebook
- **Bibliotecas:** Pandas, SciPy, Matplotlib, Scikit-Learn

## Arquivos no Repositório

- `Life_Expectancy_Data.csv`: Base de dados utilizada no projeto.
- `SPRINT_3.ipynb`: Notebook com todo o código, saídas e gráficos dos Exercícios 01 a 04.
- `README.md`: Documentação e resumo do projeto.

## Integrantes do Grupo

- Felipe Pereira Restivo - RM: 570712
- Gabriel Rodrigues Zappelloni - RM: 572060
- Kenichi Caio Yamamoto - RM: 569815
- Maykon de Lima Silva – RM: 574022
- Rodger Costa Rios - RM: 571438

*Projeto acadêmico desenvolvido para a avaliação da Challenge Sprint.*
