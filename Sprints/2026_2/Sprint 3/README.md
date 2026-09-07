# Análise Estatística e Regressão Linear: Experiência vs. Salário

Sprint 03 - Ciência da Computação | 1CCPK 2026

Disciplina: Modelagem Linear para Aprendizado de Máquinas

## Visão Geral
Este repositório contém o projeto acadêmico de Estatística e Ciência de Dados desenvolvido para analisar a relação entre o tempo de experiência profissional (`YearsExperience`) e a remuneração salarial (`Salary`).

O objetivo principal do trabalho é conectar conceitos da estatística descritiva e inferencial à construção e interpretação de um modelo preditivo de Aprendizado de Máquina Supervisionado.

## Estrutura do Projeto

O projeto foi desenvolvido em um único arquivo no Google Colab, dividido em 4 etapas práticas:

* **Exercício 01 — Entendimento dos Dados:** Organização da base, limpeza de informações e cálculo de métricas básicas (como média e variação) para entender o perfil inicial dos salários.
* **Exercício 02 — Análise de Padrões:** Verificação do comportamento da amostra para conferir a porcentagem de salários que ficam dentro da faixa mais comum.
* **Exercício 03 — Criação do Modelo de Previsão:** Construção do gráfico e da linha de tendência que calcula a estimativa de salário a partir dos anos de experiência.
* **Exercício 04 — Interpretação dos Resultados:** Explicação sobre por que escolhemos essa informação para o modelo, avaliação da sua precisão e identificação dos seus limites práticos.

## Principais Resultados

* **Tamanho da Amostra:** 30 observações
* **Média Salarial ($\mu$):** R$ 76.004,00
* **Desvio-Padrão ($\sigma$):** R$ 27.414,43
* **Coeficiente de Correlação de Pearson ($r$):** $0,9782$ (forte associação linear)
* **Equação da Reta Preditiva:** $\text{Salário} = 24.848,20 + 9.449,96 \times \text{Experiência}$
* **Coeficiente de Determinação ($R^2$):** $0,9570$ ($95,70\%$ de variância explicada)

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.x
* **Ambiente:** Google Colab / Jupyter Notebook
* **Bibliotecas:** Pandas, NumPy, Matplotlib, Scikit-Learn

## Arquivos no Repositório

* `Salary_Data.csv`: Base de dados utilizada no projeto.
* `SPRINT_3.ipynb`: Notebook com todo o código, saídas e gráficos dos Exercícios 01 a 04.
* `README.md`: Documentação e resumo do projeto.

## Integrantes do Grupo

* Felipe Pereira Restivo - RM: 570712
* Gabriel Rodrigues Zappelloni - RM: 572060
* Kenichi Caio Yamamoto - RM: 569815 
* Maykon de Lima Silva – RM: 574022 
* Rodger Costa Rios - RM: 571438

*Projeto acadêmico desenvolvido para a avaliação da Challenge Sprint.*
