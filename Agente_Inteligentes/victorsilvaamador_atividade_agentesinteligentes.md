# Atividade sobre Agentes Inteligentes

* **Data da Aula:** 19/10/2026
* **Professora:** Kadidja Valéria
* **Disciplina:** Inteligência Artificial, Linguagens Formais e Autômatos
* **Estudante:** Victor Silva Amador
* **Turma:** N-1

---

## Exercício 2.3 — Análise de Racionalidade

Para cada afirmação a seguir, indica-se o julgamento de **Verdadeiro (V)** ou **Falso (F)**, acompanhado de justificativa formal e exemplo ou contraexemplo, explicitando as hipóteses utilizadas.

### a. Um agente que detecta apenas informações parciais sobre o estado não pode ser perfeitamente racional.

* **Julgamento:** **Falso (F)**
* **Justificativa:** A racionalidade perfeita depende da **maximização do desempenho esperado** com base na sequência de percepções recebidas até o momento e no conhecimento prévio do agente, e **não da onisciência** ou da posse de informação perfeita do estado real do ambiente. Mesmo em ambientes parcialmente observáveis, um agente pode agir de forma totalmente racional ao tomar as melhores decisões possíveis com a informação parcial disponível.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Um agente limpador de pó em um ambiente com duas salas ($A$ e $B$) possui apenas sensor de sujeira local, mas não possui sensor de localização (não sabe em qual sala está). Se a sua regra for "se a sala atual estiver suja, limpe; se limpa, mova-se para a outra", ele maximiza o retorno esperado de limpeza com base unicamente em suas percepções parciais, atuando de maneira perfeitamente racional.

### b. Existem ambientes de tarefa nos quais nenhum agente reativo puro pode comportar-se racionalmente.

* **Julgamento:** **Verdadeiro (V)**
* **Justificativa:** Agentes reativos puros (reflexos simples) tomam decisões baseando-se **apenas na percepção atual**, ignorando o histórico de percepções. Em ambientes parcialmente observáveis que exigem memória do passado para resolver ambiguidade de estados (loops infinitos ou falta de informação crítica), agentes reativos puros entram em ciclos ineficientes ou realizam ações incorretas, falhando em maximizar a medida de desempenho.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Um robô aspirador em um labirinto parcialmente observável sem sensores de orientação precisa saber se acabou de virar à esquerda ou se já visitou determinado corredor para não ficar preso em um loop infinito. Um agente reativo puro sem memória ficará alternando perpetuamente entre os mesmos dois estados.

### c. Existe um ambiente de tarefa em que todo agente é racional.

* **Julgamento:** **Verdadeiro (V)**
* **Justificativa:** Se a medida de desempenho for construída de tal forma que qualquer ação tomada pelo agente resulte na pontuação máxima possível (ou se o conjunto de ações não interferir no resultado final), então qualquer agente, independentemente de sua função de agente ou comportamento, será racional.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Um ambiente onde a medida de desempenho atribui a mesma pontuação constante para qualquer sequência de estados (por exemplo, pontuação $+100$ incondicional), ou um ambiente onde a única ação possível é `Nenhum-Op`.

### d. A entrada para o programa de agente é a mesma que a entrada para a função de agente.

* **Julgamento:** **Falso (F)**
* **Justificativa:** A **função de agente** é uma descrição matemática abstrata que mapeia toda a **história/sequência completa de percepções** $P^*$ para uma ação $A$. Por outro lado, o **programa de agente** roda em uma arquitetura física real e recebe como entrada apenas a **percepção atual** $p$, gerenciando internamente sua própria memória/estado para manter o histórico se necessário.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Em um jogo de xadrez, a função de agente recebe como entrada a lista de todos os lances e tabuleiros desde o início da partida. O programa do agente recebe como entrada apenas a imagem/estado visual do tabuleiro no turno atual.

### e. Toda função de agente é implementável por uma combinação de programa/máquina.

* **Julgamento:** **Falso (F)**
* **Justificativa:** Existem limitações teóricas da computabilidade e limitações de recursos físicos (tempo e memória). O conjunto de todas as funções de agente possíveis de uma sequência de percepções para ações é não-enumerável/infinito, enquanto o conjunto de programas de computador executáveis é enumerável. Além disso, certas funções exigem processamento de instâncias indecidíveis (Problema da Parada de Turing) ou utilizam tabelas de tamanho impraticável (maior do que o número de átomos no universo).
* **Exemplo / Contraexemplo:**
  * *Contraexemplo:* Uma função de agente que exige analisar uma sequência arbitrária de código e decidir se ele vai entrar em um loop infinito antes de escolher a ação `Sim` ou `Não` é incomputável.

### f. Suponha que um agente selecione sua ação uniformemente ao acaso do conjunto de ações possíveis. Existe um ambiente de tarefa determinista em que esse agente é racional.

* **Julgamento:** **Verdadeiro (V)**
* **Justificativa:** Em um ambiente de tarefa determinista no qual todas as ações possíveis produzem resultados idênticos quanto à pontuação de desempenho, selecionar qualquer ação aleatoriamente trará o resultado ótimo esperado, satisfazendo o critério de racionalidade.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Um ambiente determinista no qual o agente tem como ações `Girar_Esquerda` e `Girar_Direita`, e a medida de desempenho premia apenas o tempo de funcionamento da bateria sem importar a orientação da câmera.

### g. É possível para um dado agente ser perfeitamente racional em dois ambientes de tarefa distintos.

* **Julgamento:** **Verdadeiro (V)**
* **Justificativa:** Um agente é definido pelo seu mapeamento interno e comportamento. Se o mesmo comportamento maximizar o resultado esperado sob a medida de desempenho de dois ambientes com dinâmicas ou estruturas de recompensa distintas, o agente será perfeitamente racional em ambos.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* O agente aspirador de pó com a regra simples "se sujo, limpe; senão, mova para o outro lado" é perfeitamente racional tanto em um ambiente onde limpar dá $+1$ ponto e mover dá $0$ pontos, quanto em um ambiente onde limpar dá $+10$ pontos e mover dá $-1$ ponto (desde que a sujeira surja na mesma taxa).

### h. Todo agente é racional em um ambiente não observável.

* **Julgamento:** **Falso (F)**
* **Justificativa:** Um ambiente não observável significa que o agente não recebe percepções. No entanto, o agente ainda possui seu conhecimento prévio sobre a estrutura do ambiente e as consequências de suas ações. Agentes que executam sequências de ações cegas porém eficientes (baseadas no estado de crença) serão racionais, enquanto agentes que realizam ações nocivas ao seu objetivo esperado serão irracionais.
* **Exemplo / Contraexemplo:**
  * *Contraexemplo:* Um limpador automático de ruas em um ambiente não observável que escolhe acelerar cegamente em direção a uma parede em vez de seguir um padrão de varredura pré-programado seguro e abrangente.

### i. Um agente jogador de pôquer perfeitamente racional nunca perde.

* **Julgamento:** **Falso (F)**
* **Justificativa:** O pôquer é um jogo de informação imperfeita (ambiente parcialmente observável) e de natureza estocástica (depende do baralhamento das cartas). Racionalidade é sobre **tomar a decisão esperada ideal**, não sobre garantir o resultado final em cenários onde o acaso interfere. Um agente perfeitamente racional pode jogar a mão probabilisticamente perfeita e ainda assim perder devido à sorte do adversário em tirar a carta vencedora no *river*.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* O agente possui uma quadra de Reis (uma mão com $99.9\%$ de chance de vitória) e aposta tudo de forma racional. O oponente, jogando de forma totalmente irracional, pagou a aposta com uma mão ruim e consegue uma quadra de Ás na última carta sorteada do baralho, fazendo o agente racional perder a partida.

---

## Exercício 2.4 — PEAS e Classificação de Ambientes de Tarefa

### Caso 1 — Jogar futebol

* **Agente analisado:** Robô jogador de futebol (jogador de campo).
* **Objetivo e hipóteses:** Marcar gols no gol adversário, evitar gols no próprio gol e colaborar com o time; assume-se regras padrão de futebol e robôs físicos operando em campo.
* **P — Medida de desempenho:** Número de gols marcados contra o adversário, precisão nos passes, posse de bola, cumprimento das regras e vitória na partida.
* **E — Ambiente:** Campo de futebol, bola, companheiros de equipe, adversários, condições do gramado e do clima.
* **A — Atuadores:** Motores de deslocamento (rodas/pernas robóticas), atuadores de chute/passe, receptores de sinal de comunicação.
* **S — Sensores:** Câmeras visuais, sensores de proximidade, acelerômetros, giroscópios e receptores GPS/Sinal de posição.

| Propriedade | Classificação | Justificativa |
| :--- | :--- | :--- |
| **Observabilidade** | Parcialmente observável | O robô tem ponto de vista limitado e pode ter a visão da bola ou de jogadores bloqueada por outros participantes. |
| **Número de agentes** | Multiagente (cooperativo e competitivo) | Há companheiros de equipe (cooperação) e adversários (competição). |
| **Previsibilidade** | Estocástico | O comportamento de outros jogadores e a física do contato/chute contêm incerteza imprevista. |
| **Dependência entre decisões** | Sequencial | As decisões atuais (ex.: posicionamento) afetam as oportunidades futuras de gol durante o jogo. |
| **Mudança durante a decisão** | Dinâmico | O ambiente muda continuamente (jogadores e bola se movimentam) enquanto o agente delibera. |
| **Natureza dos elementos** | Contínuos | Posições, velocidades, força do chute e fluxo temporal são variáveis contínuas. |
| **Conhecimento do funcionamento** | Conhecido | As regras do futebol e as leis da física que governam o campo são conhecidas pelo agente. |

### Caso 2 — Explorar os oceanos subterrâneos de Titã

* **Agente analisado:** Submarino autônomo robótico explorador.
* **Objetivo e hipóteses:** Mapear o oceano subterrâneo de Titã (lua de Saturno), coletar amostras e identificar compostos orgânicos/sinais de vida; assume-se ambiente com atraso significativo de comunicação com a Terra.
* **P — Medida de desempenho:** Volume de área oceanográfica mapeada, quantidade de amostras relevantes analisadas, integridade e sobrevivência do robô, eficiência energética.
* **E — Ambiente:** Oceano subterrâneo líquido de Titã (água/amônia sob crosta de gelo), escuridão total, alta pressão, relevo submarino desconhecido.
* **A — Atuadores:** Hélices/propulsores aquáticos, braço robótico coletor, brocas, transmissores acústicos/de rádio.
* **S — Sensores:** Sonar, sensores de temperatura, medidores de pressão, espectrômetros de massa, sensores de condutividade/químicos.

| Propriedade | Classificação | Justificativa |
| :--- | :--- | :--- |
| **Observabilidade** | Parcialmente observável | Sensores ópticos não funcionam na escuridão/turvação total; a varredura por sonar tem alcance limitado. |
| **Número de agentes** | Agente único | Não há outros agentes inteligentes conhecidos atuando no ambiente. |
| **Previsibilidade** | Estocástico | Correntes marítimas imprevistas, colisões com estruturas não mapeadas ou falhas físicas tornam o ambiente incerto. |
| **Dependência entre decisões** | Sequencial | O consumo de bateria e a rota tomada afetam diretamente o alcance e a capacidade de retornar ou sobreviver. |
| **Mudança durante a decisão** | Dinâmico | Correntes de fluido e dinâmicas térmicas alteram o estado do ambiente enquanto o robô processa dados. |
| **Natureza dos elementos** | Contínuos | Profundidade, temperatura, pressão, velocidade de navegação e tempo são grandezas contínuas. |
| **Conhecimento do funcionamento** | Desconhecido | As propriedades exatas e a composição física/geológica do oceano subterrâneo de Titã são parcialmente desconhecidas previamente. |

### Caso 3 — Comprar livros usados de IA na Internet

* **Agente analisado:** Agente de software comprador/buscador de pechinchas.
* **Objetivo e hipóteses:** Localizar e adquirir edições específicas de livros de IA pelo menor preço total (preço do livro + frete) e na melhor condição aceitável.
* **P — Medida de desempenho:** Economia financeira atingida, qualidade/conservação do livro adquirido, tempo gasto na transação e sucesso na entrega.
* **E — Ambiente:** Lojas virtuais, marketplaces de livros usados (ex.: Estante Virtual, eBay, Amazon), APIs de e-commerce e conexões de rede.
* **A — Atuadores:** Envio de requisições HTTP/API para adicionar itens ao carrinho, preencher dados e efetuar ordem de compra.
* **S — Sensores:** Leitores de HTML/JSON, APIs de busca de preços, monitores de estoque e status do sistema.

| Propriedade | Classificação | Justificativa |
| :--- | :--- | :--- |
| **Observabilidade** | Parcialmente observável | O estado interno do vendedor (se o livro realmente existe e a real condição física) só é conhecido após o envio. |
| **Número de agentes** | Multiagente (competitivo) | Outros compradores (humanos ou bots) competem pelo mesmo estoque de livros usados. |
| **Previsibilidade** | Estocástico | Anúncios podem ser esgotados ou alterados por outros usuários sem aviso prévio. |
| **Dependência entre decisões** | Sequencial | Decidir esperar pelo preço baixar pode fazer com que outro comprador adquira o livro primeiro. |
| **Mudança durante a decisão** | Semidinâmico | Os preços e estoques não mudam a cada milissegundo, mas mudam durante a decisão do agente sem penalizar seu tempo de computação direta. |
| **Natureza dos elementos** | Discretos | Preço em centavos, páginas, ISBNs e quantidade em estoque são valores discretos. |
| **Conhecimento do funcionamento** | Conhecido | As regras de transação digital, funcionamento de carrinhos de compra e APIs são conhecidas. |

### Caso 4 — Jogar uma partida de tênis

* **Agente analisado:** Robô jogador de tênis (ou modelo em simulação).
* **Objetivo e hipóteses:** Vencer a partida de tênis rebatendo a bola dentro da quadra adversária respeitando as regras oficiais da modalidade.
* **P — Medida de desempenho:** Pontos e games vencidos, porcentagem de acertos dentro da quadra, menor número de erros não forçados.
* **E — Ambiente:** Quadra de tênis (saibro, grama ou rápida), rede, bola, raquete, oponente e condições do vento.
* **A — Atuadores:** Motores das articulações do braço robótico (para controlar o golpe) e sistema de mobilidade da base na quadra.
* **S — Sensores:** Câmeras de alta velocidade, sensores de rastreamento de trajetória da bola, giroscópios.

| Propriedade | Classificação | Justificativa |
| :--- | :--- | :--- |
| **Observabilidade** | Parcialmente observável | A rotação exata da bola (*spin*) e a intenção/estratégia do oponente não são visíveis diretamente. |
| **Número de agentes** | Multiagente (competitivo) | O adversário é um agente inteligente competindo ativamente para fazer o agente falhar. |
| **Previsibilidade** | Estocástico | Imperfeições no quique da bola, vento e ações do oponente introduzem aleatoriedade. |
| **Dependência entre decisões** | Sequencial | Cada golpe posiciona o adversário e condiciona a posição do agente para a jogada seguinte. |
| **Mudança durante a decisão** | Dinâmico | A bola se desloca em alta velocidade enquanto o agente calcula a trajetória de resposta. |
| **Natureza dos elementos** | Contínuos | Posição no espaço, velocidade da bola, ângulo da raquete e tempo são variáveis contínuas. |
| **Conhecimento do funcionamento** | Conhecido | As regras do tênis e a física dos impactos são bem compreendidas. |

### Caso 5 — Praticar tênis contra uma parede

* **Agente analisado:** Robô praticante de tênis.
* **Objetivo e hipóteses:** Manter sequências contínuas de rebatidas de bola contra uma parede para treino de precisão e controle.
* **P — Medida de desempenho:** Número de rebatidas consecutivas sem deixar a bola cair, precisão da área do impacto na parede.
* **E — Ambiente:** Parede vertical plana, piso da quadra, bola de tênis, vento.
* **A — Atuadores:** Motores do braço articulado e base móvel de posicionamento.
* **S — Sensores:** Câmeras de acompanhamento visual e sensores de posição do robô.

| Propriedade | Classificação | Justificativa |
| :--- | :--- | :--- |
| **Observabilidade** | Completamente observável | Na prática individual contra a parede, a bola e a própria posição do robô estão inteiramente visíveis dentro do campo de visão. |
| **Número de agentes** | Agente único | A parede é um objeto físico inerte (parte do ambiente), não um agente com metas próprias. |
| **Previsibilidade** | Determinístico / Estocástico | Tendendo a determinístico se em ambiente fechado (física de quique previsível); estocástico com vento externo. |
| **Dependência entre decisões** | Sequencial | A força de uma rebatida determina a distância e velocidade com que a bola voltará no lance seguinte. |
| **Mudança durante a decisão** | Dinâmico | A bola continua em movimento enquanto o agente planeja seu movimento. |
| **Natureza dos elementos** | Contínuos | Trajetória, força e tempo são contínuos. |
| **Conhecimento do funcionamento** | Conhecido | As leis físicas da mecânica do quique na parede plana são completamente conhecidas. |

### Caso 6 — Realizar um salto de altura

* **Agente analisado:** Robô atleta de salto em altura.
* **Objetivo e hipóteses:** Ultrapassar a barra transversal sem derrubá-la, atingindo a maior altura possível e pousando no colchão de proteção.
* **P — Medida de desempenho:** Altura máxima superada com sucesso (sem derrubar a barra), número de tentativas bem-sucedidas.
* **E — Ambiente:** Pista de corrida de aproximação, fasquia (barra suporte), colchão de aterrissagem, gravidade.
* **A — Atuadores:** Pernas mecânicas de alta propulsão e articulações para flexão corporal durante a transposição da barra.
* **S — Sensores:** Telêmetros laser para medir a distância até a barra, acelerômetros, giroscópios e câmeras.

| Propriedade | Classificação | Justificativa |
| :--- | :--- | :--- |
| **Observabilidade** | Completamente observável | Toda a pista, a altura exata da barra e a posição do agente podem ser medidas com precisão total. |
| **Número de agentes** | Agente único | Durante a execução do salto em si, apenas o robô atua (seus concorrentes saltam em momentos separados). |
| **Previsibilidade** | Determinístico | A mecânica do salto obedece puramente às leis da física clássica de corpos rígidos e projéteis. |
| **Dependência entre decisões** | Sequencial | Os passos de corrida e o ponto de impulso determinam criticamente o sucesso da parábola do salto. |
| **Mudança durante a decisão** | Dinâmico | Durante a corrida e o salto no ar, a posição física do agente muda constantemente com o tempo. |
| **Natureza dos elementos** | Contínuos | Altura, velocidade de corrida, ângulo de impulso e aceleração são grandezas contínuas. |
| **Conhecimento do funcionamento** | Conhecido | As equações da física newtoniana e da gravidade que regem o salto são perfeitamente conhecidas. |

### Caso 7 — Participar de um leilão de um item, realizando lances

* **Agente analisado:** Agente de software leiloador / comprador.
* **Objetivo e hipóteses:** Arrematar o item desejado pelo menor valor possível, sem ultrapassar o limite orçamentário máximo estipulado.
* **P — Medida de desempenho:** Consecução da compra do item abaixo do valor estimado/teto orçamentário, margem de economia.
* **E — Ambiente:** Plataforma de leilão (servidor), livro de ofertas, cronômetro de lances, concorrentes.
* **A — Atuadores:** Envio de mensagem/comando para submeter um novo lance ($bid$).
* **S — Sensores:** Receptor de atualizações do leilão (lance atual, tempo restante, confirmações).

| Propriedade | Classificação | Justificativa |
| :--- | :--- | :--- |
| **Observabilidade** | Parcialmente observável | O valor máximo que os outros participantes estão dispostos a pagar e suas estratégias são ocultos. |
| **Número de agentes** | Multiagente (competitivo) | Outros participantes competem diretamente para vencer o mesmo leilão. |
| **Previsibilidade** | Estocástico | As decisões e o tempo de resposta dos outros agentes são imprevisíveis. |
| **Dependência entre decisões** | Sequencial | Um lance realizado altera o patamar mínimo do leilão e força os adversários a reagirem. |
| **Mudança durante a decisão** | Semidinâmico | O tempo corre no cronômetro do leilão (influenciando a decisão), mas o estado da oferta não muda a menos que um lance ocorra. |
| **Natureza dos elementos** | Discretos | O valor do lance é medido em incrementos monetários discretos e as rodadas ocorrem por eventos. |
| **Conhecimento do funcionamento** | Conhecido | As regras do leilão (ex.: leilão inglês, holandês ou de envelope fechado) são previamente estabelecidas e conhecidas. |

### Comparação Final

1. **O que muda entre jogar tênis contra outra pessoa e praticar contra uma parede?**
   * **Número de Agentes:** Contra uma pessoa o ambiente é **multiagente competitivo**, exigindo modelagem adversarial das intenções do oponente. Contra a parede é um ambiente de **agente único**, onde a parede reage de forma passiva segundo leis físicas simples.
   * **Observabilidade e Previsibilidade:** Jogar contra uma pessoa introduz **parcial observabilidade e comportamento estocástico/estratégico**, enquanto a parede oferece um ambiente **totalmente observável e altamente determinístico**.

2. **Por que comprar livros usados pode exigir decisões com informações incompletas?**
   * Porque o comprador não tem acesso visual direto ao estado físico real do livro (presença de grifos, desgaste ou páginas faltantes) e nem ao estado interno do vendedor (confiabilidade, prazos reais de envio). Trata-se de um ambiente de **informação imperfeita / parcialmente observável**.

3. **Como outros agentes influenciam futebol e leilões?**
   * No **futebol**, os outros agentes criam dinâmicas **cooperativas** (passes e táticas de equipe) e **competitivas** (bloqueios e desarmes), tornando o ambiente altamente dinâmico, estocástico e dependente de estratégias coletivas.
   * Nos **leilões**, a presença de outros agentes cria uma disputa **estratégica e competitiva**, onde os lances de terceiros mudam o preço de reserva, exigindo que o agente tome decisões sob incerteza quanto à disposição de pagar dos concorrentes.

---

## Exercício 2.5 — Conceitos Fundamentais e Síntese

### Definições Conceituais e Exemplos

#### Agente
* **Definição:** Entidade capaz de perceber seu ambiente por meio de sensores e atuar sobre esse ambiente através de atuadores. Ele busca processar suas percepções para selecionar e executar ações de maneira contínua.
* **Exemplo:** Um termostato inteligente que lê a temperatura do ar via sensor térmico e aciona o motor do ar-condicionado.

#### Função de Agente
* **Definição:** Mapeamento matemático abstrato que associa qualquer sequência/histórico completo de percepções recebidas pelo agente até o momento a uma ação correspondente a ser executada.
* **Exemplo:** Uma tabela conceitual que mapeia todas as combinações passadas de posições e sujeiras verificadas por um aspirador para a ação de "limpar" ou "mover".

#### Programa de Agente
* **Definição:** A implementação concreta em código executável ou arquitetura de software que roda sobre uma estrutura física, recebendo a percepção atual e devolvendo a ação imediata do agente.
* **Exemplo:** Um script em linguagem Python executado em um microcontrolador Raspberry Pi de um carrinho robótico.

#### Racionalidade
* **Definição:** Propriedade de uma tomada de decisão que escolhe a ação esperada para maximizar uma medida de desempenho pré-definida, considerando o histórico de percepções e o conhecimento prévio construído.
* **Exemplo:** Um sistema de navegação GPS que calcula a rota com o menor tempo médio de viagem esperado diante do tráfego reportado no momento.

#### Autonomia
* **Definição:** Capacidade do agente de aprender, adaptar-se e tomar decisões corretas com base em sua própria experiência no ambiente, dependendo minimamente de conhecimento embutido pelo criador.
* **Exemplo:** Um robô aspirador de pó de última geração que mapeia a casa sozinho via LIDAR sem precisar de uma planta da casa pré-programada.

#### Agente Reativo (Reflexo Simples)
* **Definição:** Agente que seleciona suas ações baseando-se unicamente na percepção atual imediata, ignorando o histórico passado de percepções através de regras de condição-ação.
* **Exemplo:** Uma porta automática de shopping que se abre imediatamente ao detectar a presença física de alguém pelo sensor de movimento.

#### Agente Baseado em Modelo
* **Definição:** Agente que mantém um estado interno para rastrear aspectos não observáveis do ambiente atual, atualizando esse modelo conforme o tempo passa e as percepções mudam.
* **Exemplo:** Um carro autônomo que memoriza a presença de um pedestre atrás de um caminhão blindado, mantendo a parada mesmo sem enxergá-lo diretamente.

#### Agente Baseado em Objetivos
* **Definição:** Agente que combina informações sobre o estado do ambiente com descrições de metas/objetivos para escolher ações ou planejar caminhos que o levem a atingir esse destino desejado.
* **Exemplo:** Um software de rotas de entrega que gera o trajeto otimizado para conseguir visitar todas as 10 paradas do dia.

#### Agente Baseado em Utilidade
* **Definição:** Agente que utiliza uma função de utilidade para quantificar o quão "satisfeito" ou eficiente ele estará em cada estado final, permitindo balancear objetivos conflitantes (ex.: tempo vs. custo).
* **Exemplo:** Um robô de negociação financeira que decide entre duas ações avaliando o equilíbrio ideal entre potencial de lucro e risco de perda.

#### Agente com Aprendizagem
* **Definição:** Agente dividido em elemento de execução, crítica, aprendizado e gerador de problemas, permitindo que ele aprenda com os erros, ganhe experiência e melhore sua atuação ao longo do tempo.
* **Exemplo:** Um algoritmo de recomendação de vídeos (como o do YouTube) que ajusta suas sugestões conforme a taxa de retenção dos usuários.

---

### Síntese com Autômatos

* **Caso escolhido:** Caso 5 — Praticar tênis contra uma parede.
* **3 Estados Internos:** $S = \{\text{Aguardando\_Quique}, \text{Preparando\_Golpe}, \text{Ajustando\_Posicao}\}$.
* **3 Percepções:** $P = \{\text{Bola\_Quicou}, \text{Bola\_Fora\_De\_Alcance}, \text{Trajetoria\_Alinhada}\}$.
* **3 Ações:** $A = \{\text{Executar\_Golpe}, \text{Mover\_Para\_Direita}, \text{Ajustar\_Postura}\}$.

#### Duas Regras de Transição ($Estado\_Atual + Percepção \rightarrow Proximo\_Estado + Ação$):

1. $\text{Aguardando\_Quique} + \text{Bola\_Quicou} \rightarrow \text{Preparando\_Golpe} + \text{Ajustar\_Postura}$
2. $\text{Preparando\_Golpe} + \text{Trajetoria\_Alinhada} \rightarrow \text{Ajustando\_Posicao} + \text{Executar\_Golpe}$

#### Explicação e Limitação:
* **Como os estados internos representam informação passada:** O estado interno `Preparando_Golpe` guarda o histórico de que a bola já passou pela fase de trajetória e quicou no chão recentemente. Isso evita que o agente tente rebatê-la prematuramente no ar antes do tempo correto do impacto.
* **Limitação da simplificação:** Um autômato finito simplifica o tempo e o espaço em eventos discretos. No tênis real, a física da bola, a força do golpe, a velocidade e os ângulos de rotação (*spin*) são grandezas físicas contínuas e dinâmicas que exigem equações diferenciais e controle contínuo, tornando a modelagem por máquina de estados finitos rígida demais para situações de imprevistos.

---

## Referências

* **Material-base:** RUSSELL, Stuart; NORVIG, Peter. *Inteligência Artificial: uma abordagem moderna*. 4. ed. Rio de Janeiro: GEN LTC, 2022. Capítulo 2 — Agentes Inteligentes.
* **Referências adicionais:**
  * RICH, Elaine; KNIGHT, Kevin; NAIR, Shivashankar B. *Inteligência Artificial*. 3. ed. Porto Alegre: Bookman, 2010.
  * HOPCROFT, John E.; MOTWANI, Rajeev; ULLMAN, Jeffrey D. *Introdução à Teoria de Autômatos, Linguagens e Computação*. 2. ed. Rio de Janeiro: Elsevier, 2002.