

# Regressão linear com PIB e Índice ABCR

Investigação da relação entre a atividade econômica brasileira e o fluxo de veículos nas rodovias pedagiadas por meio de uma regressão linear simples em Python, no período de 2006 a 2025.

Checkpoint 02 - Ciência da Computação | 1CCPK 2026

Disciplina: Modelagem Linear para Aprendizado de Máquinas

## Objetivo

Verificar se o índice de volume do PIB permite estimar o Índice ABCR de fluxo total de veículos. O trabalho inclui:

- a pesquisa e a organização dos dados;
- a análise da correlação entre os indicadores;
- o treinamento de um modelo de regressão linear;
- a avaliação do modelo em um conjunto de teste.

## Fontes dos dados

| Indicador | Fonte | Série utilizada |
| --- | --- | --- |
| Índice de volume do PIB | [IBGE – Tabela 1620 do SIDRA](https://sidra.ibge.gov.br/tabela/1620) | Brasil, PIB a preços de mercado, série encadeada trimestral sem ajuste sazonal (média de 1995 = 100). Obtida pela API do SIDRA. |
| Índice ABCR | [ABCR – Índice ABCR](https://melhoresrodovias.org.br/indice-abcr_2/) | Planilha `abcr_0826.xlsx`, aba (C) Original, coluna Brasil – TOTAL, série mensal sem ajuste sazonal (1999 = 100). |

Data de acesso: 07/10/2026.

## Estrutura do repositório

```
├── README.md
├── MLAM - CP 02 - 2SEM.ipynb          # notebook com código, gráficos e análises
└── dados/
    ├── abcr_0826.xlsx                # planilha original da ABCR
    ├── abcr_mensal_brasil_total.csv  # série mensal extraída da planilha
    ├── pib_trimestral_sidra.csv      # série trimestral do PIB (SIDRA)
    └── base_pib_abcr_2006_2025.csv   # base anual utilizada no modelo
```

## Metodologia

1. **Coleta:** o PIB trimestral foi obtido pela API do SIDRA. A série mensal da ABCR foi extraída da planilha histórica.
2. **Organização da base:** o PIB anual corresponde à média dos quatro trimestres, e o Índice ABCR anual, à média dos doze meses. Foram mantidos apenas os anos completos em ambas as séries, o que resultou em 20 anos (2006–2025).
3. **Análise da relação:** foram feitos um gráfico de dispersão e o cálculo da correlação de Pearson.
4. **Treinamento:** foi usada a classe `LinearRegression` do scikit-learn, com `PIB_indice` como entrada e `ABCR_indice` como saída. A divisão foi cronológica e sem embaralhamento: treino de 2006 a 2021 e teste de 2022 a 2025.
5. **Avaliação:** o modelo foi avaliado no conjunto de teste com MAE, MSE e R².

## Resultados

- **Correlação de Pearson:** 0,964
- **Equação ajustada:** ABCR = −56,784 + 1,215 × PIB

| Métrica (teste) | Valor |
| --- | --- |
| MAE | 4,948 |
| MSE | 25,939 |
| R² | 0,485 |

| Ano | Observado | Previsto | Erro |
| --- | --- | --- | --- |
| 2022 | 154,12 | 159,46 | −5,34 |
| 2023 | 163,49 | 166,47 | −2,98 |
| 2024 | 168,88 | 174,10 | −5,22 |
| 2025 | 173,12 | 179,38 | −6,26 |

## Conclusão

Os resultados mostram uma associação linear positiva muito forte entre o PIB e o fluxo de veículos nas rodovias pedagiadas entre 2006 e 2025. No teste, o modelo teve erro médio de 4,95 pontos, cerca de 3% dos valores observados, mas superestimou o fluxo em todos os anos. Esse viés se explica pela extrapolação para valores de PIB acima da faixa de treino, pela amostra de teste reduzida e por uma possível mudança de patamar após a pandemia.

Assim, o PIB acompanha bem a tendência de longo prazo do fluxo rodoviário, mas não é suficiente, sozinho, para previsões precisas. A correlação elevada indica associação, e não causalidade.

## Integrantes do Grupo

    Felipe Pereira Restivo - RM: 570712
    Kenichi Caio Yamamoto - RM: 569815
    Maykon de Lima Silva – RM: 574022
    Rodger Costa Rios - RM: 571438

*Projeto acadêmico desenvolvido para a avaliação do Checkpoint 02.*
