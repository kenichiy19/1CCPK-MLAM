# Vulnerabilidade Social nos Municípios Brasileiros | Desafio CitizenTech

**Global Solution 2 – Ciência da Computação | 1CCPK 2026**

Disciplina: Modelagem Linear para Aprendizado de Máquinas

## Problema e objetivo

O acesso a informações sobre serviços públicos, documentos e direitos não é igual para todos, e tende a ser mais difícil justamente para a população mais vulnerável. Dentro do desafio CitizenTech, e tendo como caso norteador o **Citizen Assist AI**, um assistente digital de apoio ao cidadão, este trabalho busca responder:

> **Quais fatores socioeconômicos se associam à vulnerabilidade social nos municípios brasileiros, e como esses resultados podem orientar onde priorizar uma solução de apoio ao cidadão?**

Para isso, foram aplicadas técnicas de probabilidade, testes de hipóteses, análise bivariada, regressão linear simples e múltipla e regressão logística.

**ODS relacionados:** 10 (Redução das desigualdades), 4 (Educação de qualidade) e 11 (Cidades e comunidades sustentáveis).

## Base de dados

- **Fonte:** PNUD; Ipea; FJP. *Atlas do Desenvolvimento Humano no Brasil* – Censo Demográfico (1991, 2000 e 2010).
- **Acesso:** https://www.atlasbrasil.org.br/acervo/biblioteca (acesso em 9 nov. 2026).
- **Período utilizado:** 2010, o mais recente disponível por município nessa base.
- **Registros:** 5.565 municípios brasileiros.

| Variável | Descrição | Papel |
|---|---|---|
| PPOB | % da população vulnerável à pobreza | Variável principal |
| T_ANALF18M | Taxa de analfabetismo – 18 anos ou mais (%) | Explicativa |
| P_FORMAL | Grau de formalização do trabalho (%) | Explicativa |
| T_BANAGUA | % da população em domicílios com banheiro e água encanada | Explicativa |
| PRIORITARIO | 1 se PPOB ≥ 50%; 0 caso contrário (criada pelos autores) | Variável binária |

## Estrutura do repositório

```
dados/
  censo_total_1991_2010.xlsx      → base original do Atlas
  base_municipios_2010.csv        → base tratada, gerada pelo notebook 01
notebooks/
  01_preparacao_dados.ipynb       → leitura, filtro, limpeza e criação da variável PRIORITARIO
  02_analises.ipynb               → probabilidade, testes e regressões
relatorio/
  relatorio_estatistico_GS_MLAM.pdf → relatório estatístico
README.md
```

## Como executar

Os notebooks foram desenvolvidos no **Google Colab** e já estão salvos com as saídas das análises.

1. Abra o notebook `01_preparacao_dados.ipynb` no Google Colab.
2. Execute as células em ordem. Quando solicitado, envie o arquivo `dados/censo_total_1991_2010.xlsx`.
3. Ao final, o notebook gera e baixa o arquivo `base_municipios_2010.csv`.
4. Abra o notebook `02_analises.ipynb` e execute as células em ordem. Quando solicitado, envie o arquivo `base_municipios_2010.csv`.

Para obter os mesmos resultados, os sorteios utilizam semente fixa (`random_state = 42`).

## Principais resultados

- A vulnerabilidade se distribui em **dois grandes grupos de municípios**, de menor e de maior vulnerabilidade, o que torna a média nacional (43,99%) pouco representativa.
- O **analfabetismo** apresentou correlação forte com a vulnerabilidade (r = 0,88) e explicou cerca de **77%** da sua variação.
- Com o **analfabetismo, o trabalho formal e o saneamento**, a regressão múltipla explicou cerca de **86%** da variação da vulnerabilidade.
- A **regressão logística** classificou corretamente **94,97%** dos municípios de teste como prioritários ou não.
- **2.415 municípios (43,4%)** tinham metade ou mais da população vulnerável à pobreza e foram classificados como prioritários.
- **Recomendação:** priorizar esses municípios e desenvolver uma solução acessível a pessoas com baixa alfabetização, com conteúdos sobre trabalho e serviços básicos.

## Limitações

- Os dados se referem a **2010** e não representam a situação atual dos municípios.
- O PPOB é uma **medida aproximada** da necessidade de apoio ao cidadão.
- Os resultados indicam **associação, e não causalidade**.
- A **Distribuição Normal** e os **modelos lineares** são aproximações do comportamento real dos dados.
- Os resultados descrevem **municípios**, e não indivíduos.

## Tecnologias Utilizadas
* **Linguagem:** Python
* **Processamento:** Pandas (leitura, filtragem e estruturação dos dados) e NumPy (operações numéricas)
* **Análise estatística:** SciPy (Distribuição Normal, testes de hipóteses e teste F)
* **Modelagem:** scikit-learn (regressão linear simples e múltipla, regressão logística e divisão treino/teste)
* **Visualização:** Matplotlib e Seaborn (histogramas, gráficos de dispersão, mapas de calor e matriz de confusão)
* **Ambiente:** Google Colab

## Integrantes do Grupo

Kenichi Caio Yamamoto - RM: 569815

Rodger Costa Rios - RM: 571438

---
*Documentação desenvolvida como parte da Global Solution do desafio CitizenTech, com foco na priorização de soluções de apoio ao cidadão em municípios vulneráveis.*
