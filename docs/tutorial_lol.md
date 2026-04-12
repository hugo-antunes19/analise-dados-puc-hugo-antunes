# O Básico de League of Legends (LoL)

Bem-vindo ao glossário e tutorial de introdução! Este documento serve como material de apoio para que qualquer pessoa consiga interpretar a nossa **Análise do Cenário Competitivo**, mesmo não sendo especialista em *esports*.

---

## 1. O Objetivo do Jogo (O Nexus)
League of Legends é jogado por duas equipes de **5 jogadores**.
O objetivo de cada equipe é atravessar o mapa circular — dividido pelo Time Azul (Blue) e Time Vermelho (Red) — e destruir a construção central da base inimiga, conhecida como **Nexus**. Quem quebra o Nexus, vence a partida. O conceito de "Result" do nosso dataset marca exatamente quem alcançou isso (0 para derrota, 1 para vitória).

---

## 2. O Mapa e as Posições (Lanes)
Para alcançar o Nexus inimigo, o campo de batalha é divido em três caminhos principais (rotas) e uma selva densa cruzando entre eles. Cada um dos 5 jogadores assume uma **posição específica** com responsabilidades distintas (algo evidente nos gráficos de DPM e KDA do nosso trabalho):

* **Top (Rota Superior):** Uma rota longa e isolada. Geralmente habitada por "Tanques" ou "Lutadores", personagens focados em sobrevivência e combate corpo a corpo árduo. É uma posição metódica.
* **Mid (Rota do Meio):** O caminho mais curto até a base inimiga. Dominada por Magos ou Assassinos muito fortes, capazes de aplicar dano mágico altíssimo (*burst*) rapidamente e que andam pelo mapa para ajudar outras rotas.
* **Bot (Rota Inferior) ou ADC:** Rota ocupada pelos Atiradores de Dano Físico (Attack Damage Carry). É o jogador mais frágil da equipe, mas que, no final da partida, dará o maior volume de dano por minuto (DPM) batendo à distância.
* **Sup (Suporte):** Joga frequentemente junto com o ADC na rota inferior. Não foca em causar dano, mas em curar, proteger e controlar a visão do mapa (espalhando wards pelo escuro). Possui alto número de assistências.
* **Jng (Selva):** O elemento surpresa. Não fica em uma rota fixa, mas caça monstros gigantes escondidos no nevoeiro entre as rotas para ganhar ouro. Ele vagueia ativamente pelas 3 posições emboscando adversários indefesos.

---

## 3. A Economia (Gold) e Itemização
Como qualquer RPG de fantasia, os jogadores precisam evoluir seus campeões para ficarem mais fortes durante a partida.
- **Ouro (Gold):** É obtido ao abater monstros, tropas (minions), destruir construções e eliminar adversários. Com o Ouro, o jogador volta à loja da sua base e compra **itens** mágicos ou espadas que amplificam exponencialmente seu poder.
- **Gold Diff (Diferença de Ouro):** Como os dois times começam com a exata mesma quantidade de dinheiro, a equipe que joga melhor "acumula mais ouro". Ficar "mil moedas de ouro (1k)" na frente do adversário, por exemplo, significa que sua equipe tem itens melhores antes das grandes lutas. O momento dos **15 minutos de partida** (representado no dataset por `golddiffat15`) costuma ser o melhor termômetro para saber qual time "ganhou" a fase de rotas inicial do jogo.

---

## 4. Combates Interpessoais (Kills, Deaths e Assists)
O combate contra jogadores rende o maior bônus de Ouro e expulsa o inimigo do mapa temporariamente para que o time deleque objetivos macro.
* **Kills (Abates):** O ato de abater o personagem comandado por um humano inimigo.
* **Deaths (Mortes):** A quantidade de vezes que você foi abatido.
* **Assists (Assistências):** Entregue a quem ajudou a causar dano ou curar o aliado que cometeu o abate final.
* **KDA:** Uma sigla que soma seus *Abates + Assistências* divididos pelas *Suas Mortes*. Mede o quão eficiente você é em ajudar o time sem ser um peso repassando dinheiro pro adversário.
* **CKPM (Combined Kills per Minute):** Uma estatística super comum do Esports, soma todas as eliminações do time Azul com as do time Vermelho e divide pela duração da partida em minutos. Basicamente mostra quão violenta e "ensanguentada" é a liga de cada país e o estilo de jogo daquela temporada.

---

## 5. Os Objetivos Estratégicos do Mapa
O LoL não se resume a procurar lutas. Ele é sobre dominar territórios.
* **Torres (Towers):** Fortalezas que atiram e defendem cada rota. Cada time possui até 11 torres. Elas devem ser destruídas progressivamente para abrir caminho até o Nexus. 
* **Barão Nashor (Baron):** Um chefão colossal que nasce no rio aos 20 minutos de jogo. O time que derrotá-lo recebe a glória máxima permanente na forma de purpura flamejante que energiza magicamente suas próprias tropas (minions), sendo a ferramenta obrigatória da maioria das partidas para engolir as fortalezas inimigas de uma vez.
* **Dragões (Dragons):** Chefões secundários menores. Cada equipe vai caçá-los para acumular melhorias passivas de força (dano, resistência, velocidade) permanentes para seu esquadrão.

---

## 6. Dinâmica do Competitivo (Draft e Lados)
Antes de os competidores adentrarem a arena (no "Summoner's Rift"), as duas equipes ficam em uma tela estatística prévia escolhendo quais avatares usarão (os **Campeões**) e banindo ("vetando") os campeões preferidos do oponente.
* **Picks:** O campeão que você trancou para usar.
* **Bans:** O campeão que você proibiu previamente que qualquer integrante jogue.
* **Blue/Red Side:** Geograficamente, o time **Azul** é obrigado a escolher o primeiro campeão abertamente, garantindo na sorte a presença do "melhor campeão do patch", mas dando a chance do oponente contra-atacar a tática. O time **Vermelho**, na ponta contrária da base, escolhe por último de todos, servindo como a "Última Barreira". Há anos essa dinâmica cria estatísticas imensas de vantagens territoriais discutidas globalmente e no projeto de pesquisa.

---

## 7. Contexto Histórico das Regiões (Ligas Major)
Ao longo da pesquisa, cruzamos dados focados explicitamente no **Tier 1** global de League of Legends, o patamar mais reverenciado do esporte eletrônico. O jogo se organiza em Ligas Fechadas regionais, cada uma com culturas, finanças e ritmos de jogo historicamente endêmicos à sua cultura:

* **LCK (Coreia do Sul):** A meca sagrada do LoL. Historicamentes, os sul-coreanos dominam os Títulos Mundiais adotando a fórmula do "jogo limpo" absoluto: um esporte cadenciado pela perfeição micromecânica, sem margem para riscos inconsequentes, focado em estrangular a economia do oponente sem derramar uma gota de sangue desnecessária. Por isso, ditam até hoje as métricas com os **mais baixos índices de CKPM (Violência)** e maiores metragens de ouro (*Gold Diff*).
* **LPL (China):** O polo antitético em comportamento à LCK que também possui o maior orçamento global. Os chineses ditam suas vitórias pelo engajamento forçado; jogam pelo famoso *Team Fight* (as grandes pancadarias em equipe no centro do mapa), abraçando o caos constante para subjugar oponentes.
* **LEC (Europa):** Conhecidos por quebrar moldes táticos e surpreender a dominância asiática esporadicamente, possuem um estilo que balança entre o passivo engarrafamento norte-americano e metodologias criativas singulares de campeões (picks exóticos fora da curva).
* **LCS (EUA/América do Norte) e CBLOL (Brasil):** O bloco américo compreende os bastiões de alta popularidade e engajamento da internet. Históricamente são as regiões mais fracas do ponto de vista competitivo, não tendo conquistado nenhum título internacional relevante.

---
*Com essas informações consolidadas, você é capaz de interpretar absolutamente quaisquer dos Boxplots, Histogramas e Matrizes disponíveis no notebook exploratório da nossa pesquisa. Boa leitura!*
