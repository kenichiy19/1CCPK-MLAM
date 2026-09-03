# Documentação Técnica: Análise de Dados OPS-SAT

Global Solution - Ciência da Computação | 1CCPK 2026 

Disciplina: Modelagem Linear para Aprendizado de Máquinas

## Visão Geral
Este repositório contém a documentação e os scripts desenvolvidos para o projeto de otimização operacional do CubeSat OPS-SAT. A solução utiliza técnicas de ciência de dados para converter telemetria bruta em insights estratégicos, permitindo maior eficiência na gestão de energia, comunicação e integridade estrutural do ativo espacial.

## Escopo da Solução
A solução foi estruturada para monitorar os três pilares fundamentais da operação:
* **Energia:** Análise univariada de consumo e tensão para diagnóstico de performance energética.
* **Comunicação:** Mapeamento do fluxo de pacotes de dados por meio de distribuições de frequência.
* **Status Operacional:** Detecção de anomalias térmicas e comportamentais críticas para suporte à tomada de decisão automática.

## Metodologia de Análise
O processamento dos dados foi conduzido em etapas, com foco em rigor estatístico:
1. **Fase de Definição:** Classificação e estruturação das variáveis de entrada (`n_peaks` e `duration`).
2. **Fase de Processamento (Sessão 4):** Aplicação de medidas de tendência central, dispersão e separatrizes para mapear o comportamento nominal e as caudas da distribuição.
3. **Fase de Insights (Sessão 5):** Tradução dos resultados estatísticos em protocolos operacionais de alta eficiência.

## Principais Resultados e Protocolos
A análise resultou na definição de dois protocolos críticos:
* **Regra de Ouro dos 5 Minutos:** Protocolo de priorização de dados vitais (telemetria e imagens) nos primeiros 3 minutos de enlace, garantindo sucesso na transmissão dentro do intervalo de segurança estatística (mediana de 225 segundos).
* **Gestão Dinâmica de Solo:** Recomendação para a transição de janelas fixas para a alocação dinâmica de estações terrestres, otimizando o tempo de antena e reduzindo custos operacionais ao liberar infraestrutura conforme a interrupção de portadora do satélite.

## Tecnologias Utilizadas
* **Linguagem:** Python
* **Processamento:** Pandas (análise e estruturação de dados)
* **Visualização:** Matplotlib e Seaborn (análise de distribuição e histogramas)
* **Ambiente:** Google Colab

---
*Documentação desenvolvida como parte da Global Solution para otimização de sistemas aeroespaciais.*
