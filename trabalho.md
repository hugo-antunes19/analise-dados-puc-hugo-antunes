# Requisitos para o Desenvolvimento do MVP

## 1. Contexto
Escolha uma base de dados que não tenha sido utilizada em aula. Sugere-se usar uma das bases de dados disponibilizadas em algum dos repositórios a seguir:

* **UCI Machine Learning Repository:** [https://archive.ics.uci.edu/ml/datasets](https://archive.ics.uci.edu/ml/datasets)
* **Kaggle:** [https://www.kaggle.com/datasets](https://www.kaggle.com/datasets)
* **Google Datasets:** [https://datasetsearch.research.google.com/](https://datasetsearch.research.google.com/)

> **Dica:** Aproveite os filtros que os repositórios oferecem para encontrar com mais facilidade o dataset da sua preferência. Caso prefira usar um dataset que reflita um problema real da sua empresa (cuidado com a confidencialidade), será muito bem-vindo.

Você deverá trabalhar desde a **definição do problema** até a etapa de **pré-processamento de dados**, conforme o esquema visto na disciplina *Análise Exploratória e Pré-processamento de Dados*.

### Formato de Entrega (Google Colab)
Produza um notebook no Google Colab com as seguintes características:
1.  **Relatório:** O notebook servirá como relatório, descrevendo textualmente (utilizando células de texto) o contexto do problema e as operações com os dados.
2.  **Linguagem:** Utilize Python e bibliotecas apropriadas.
3.  **Boas Práticas:** Siga as boas práticas de codificação vistas no curso.
4.  **Estrutura:** O notebook deve seguir a estrutura proposta no [Template Oficial](https://colab.research.google.com/drive/13_0XG51W2p4Y0Y6x8zR4_G_hR5aX_G3Q?usp=sharing) (lembre-se de salvar uma cópia no seu Drive).

---

## 2. Observações Importantes
* **Dataset:** Pode ser qualquer um, desde que **não** tenha sido utilizado na disciplina.
* **Visualização:** Podem ser utilizadas as bibliotecas Python vistas em aula ou ferramentas de Visualização de Informação. Se usar ferramentas externas ao Python, anexe a figura do gráfico produzido no notebook.

---

## 3. Requisitos e Composição da Nota
| Critério | Pontuação | Descrição |
| :--- | :---: | :--- |
| **Execução sem erros** | 1,0 pt | O notebook deve ser executado do início ao fim sem erros no Google Colab. |
| **Documentação consistente** | 2,0 pts | Blocos de texto explicando cada etapa e decisão, contando uma história completa. |
| **Código limpo** | 1,0 pt | Legível e organizado, seguindo boas práticas de Engenharia de Software. |
| **Análise de dados** | 2,0 pts | Parágrafo após cada gráfico resumindo achados e pontos de atenção. |
| **Checklist** | 2,0 pts | Resposta às perguntas aplicáveis da checklist fornecida. |
| **Qualidade Geral** | 2,0 pts | Capricho e qualidade do trabalho como um todo. |

---

## 4. Checklist Sugerida

### 4.1. Definição do Problema
*Objetivo: Entender e descrever claramente o problema.*
* Qual é a descrição do problema?
* Este é um problema de aprendizado supervisionado ou não supervisionado?
* Que premissas ou hipóteses você tem sobre o problema?
* Que restrições ou condições foram impostas para selecionar os dados?
* Defina cada um dos atributos do dataset.

### 4.2. Análise de Dados
*Objetivo: Entender a informação disponível.*

#### Estatísticas Descritivas:
* Quantos atributos e instâncias existem?
* Quais são os tipos de dados dos atributos?
* Verifique as primeiras linhas do dataset. Algo chama a atenção?
* Há valores faltantes, discrepantes ou inconsistentes?
* Faça um resumo estatístico (mínimo, máximo, mediana, moda, média, desvio-padrão e nulos). O que você percebe?

#### Visualizações:
* Verifique a distribuição de cada atributo. (Ajuda a identificar necessidade de normalização/padronização).
* Se for classificação, verifique a distribuição das classes (balanceamento).
* Analise atributos individualmente ou combinados usando gráficos apropriados.

### 4.3. Pré-processamento de Dados
*Objetivo: Limpeza, tratamento e preparação.*
* Verifique operações interessantes: normalização, padronização, discretização, one-hot-encoding, etc.
* Trate (removendo ou substituindo) os valores faltantes.
* Realize outras transformações necessárias.
* Explique o passo a passo e justifique cada operação.
* *Dica:* Se necessário, volte à análise exploratória após o pré-processamento para novos insights.