# Análise do Cenário Competitivo de League of Legends (2015-2026)

Este projeto apresenta o Produto Mínimo Viável (MVP) de **Análise de Dados e Boas Práticas** (PUC-Rio). O foco principal é realizar uma ampla análise exploratória de dados sobre as partidas profissionais de *League of Legends* (Tier 1 Global) ocorridas entre os anos de **2015 e 2026**.

**Autor:** Hugo Leandro Antunes  
**Dataset Utilizado:** [Oracle's Elixir - LoL Esports Match Data](https://oracleselixir.com/)

---

## 🎯 Descrição do Problema

A proposta desta pesquisa (uma análise exploratória descritiva e não supervisionada) é investigar o comportamento e a evolução das principais ligas mundiais aos longos dos últimos anos. Não tratamos de uma variável-alvo preditiva única, mas sim da exploração das estruturas da base de dados e suas particularidades para testar suposições famosas do maior jogo de *esport* do planeta.

**Principais Questões Investigadas:**
- Como as principais ligas ao redor do mundo (LCK, LPL, LEC, LCS, CBLOL) se diferenciam em termos de ritmo de combate e agressividade?
- Quais as grandes alterações no estilo de jogo ao decorrer de uma década de atualizações?
- Qual a correlação entre capturar vantagens de recursos nos primeiros 15 minutos e assegurar a vitória na partida?

---

## 💡 Hipóteses da Análise

Ao longo deste projeto, tentamos testar e validar diversas métricas de desempenho abordadas nos fóruns do jogo:

1. **Ligas Asiáticas (LPL e LCK):** A China e a Coreia possuem estilos de jogo notavelmente diferentes? E como isso se distancia da letargia ou caos das Ligas Ocidentais (Europa e Brasil)? Esperamos visualizar isso em índices como DPM e Kills.
2. **Aceleração do Meta:** A duração média das partidas profissionais está caindo com os anos? A nossa hipótese é de que ao longo do tempo, as desenvolvedoras alteraram o jogo e o puniram os "jogos parados", forçando dinâmicas agressivas que encurtam as disputas.
3. **Efeito Bola de Neve (Snowball):** Ficar rico ou matar nos primeiros 15 minutos de partida é suficiente para confirmar o resultado? Investigamos que o ganho inicial financeiro `golddiffat15` domina a matriz de correlação de vitórias do conjunto.
4. **Viés da Arena (Blue/Red Side):** O Time Azul, com vantagem para o controle da "Primeira Escolha" no *Draft/Pick* detém vantagens estruturais significativas sobre o Time Vermelho na probabilidade de vitória final?

---

## 🗄️ Tratamento de Dados e Otimização da RAM

Com os dados publicamente empilhantados desde 2015 pelo *Oracle's Elixir*, estamos lidando com dezenas de gigabytes de logs estatísticos de todas as ligas (amadoras ou secundárias do globo). 

O projeto teve o **cuidado técnico** de arquitetar os tratamentos dos dados contornando ativamente as limitações na memória RAM livre que são ofertadas pelo Google Colab:
- **Restrição de Major Leagues:** Para concentrar as métricas ao ecossistema "Tier 1" internacional — sem poluir com jogos de ranque acadêmico —, processamos estritamente os eventos do: `LCK`, `LPL`, `LEC`, `LCS` e `CBLOL`.
- **Compressão Dinâmica:** Foram estipulados dezenas de *dict maps* nos "tipos e restrições" do *Pandas* logo na leitura (ex: conversores `float32`, `int8`, `category`). 
- **Separação Obrigatória:** O repositório original mistura linhas de avaliação de times inteiros (5 participantes), junto de avaliação segmentada dos jogadores individuais (1 na lane). Estes domínios (`participantid`) foram isolados forçadamente para evitar somas indevidas de médias e distorções dos Boxplots e das Matrizes, que poderiam induzir a erros fatais para tomadas de decisão.
- Exonerações constantes de *Dataframes Root* temporários por meio de limpeza do Garbage Collector (`gc.collect()`).

---

## 📖 Documentação de Apoio

Ciente de que estatísticas detalhadas como FPS (*First Blood*), CSPM (*Creep Score/Min.*), CKPM (*Combines Kills*) até *DPM* podem facilmente causar confusão textual ou não soarem óbvias para o corretor caso ele(a) não tenha contato prévio com este esporte interativo, formulamos um pequeno material explicativo:

📚 **Para a compreensão global do nosso Notebook recomendou-se a Leitura:**   
👉 **[Glossário e Tutorial Básico de League of Legends](docs/tutorial_lol.md)**

Nele constam descrições super claras dos objetivos estruturais do jogo (como são as Rotas e suas dinâmicas) e das estatísticas cruciais citadas acima — e nas análises de Ouro, Monstros e Combate.

---

## 🚀 Como Executar a Análise

1. Realize o Clone via Git das pastas principais deste repositório na sua máquina. 
2. Os dados já foram mapeados ou se localizam internamente na pasta de bases (ou nos links originais *cloud* caso você decida carregar individualmente todos os *.zip* originais).
3. Todo código fundamental em execução, além da exploração gráfica interativa (Matplotlib e Seaborn) se encontra rodando no artefato principal: **`analise_exploratoria.ipynb`**. Certifique-se de executar no Python (`3.10+`) ou localmente com Jupyter seguindo sistematicamente a compilação sequencial visível no sistema para não se esgoelar de limite o *Buffer/RAM* do PC em virtude da falta dos expurgues que atrelamos periodicamente às etapas da análise.
