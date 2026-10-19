# Atividade sobre Agentes Inteligentes

- **Data da Aula:** 19/10/2026
- **Professora:** Kadidja Valéria
- **Disciplina:** Inteligência Artificial, Linguagens Formais e Autômatos
- **Estudante:** Victor Silva Amador
- **Turma:** N-1

---

## Exercício 2.3

Para cada afirmação a seguir, indica-se o julgamento de **Verdadeiro (V)** ou **Falso (F)**, acompanhado de justificativa formal e exemplo ou contraexemplo, explicitando as hipóteses utilizadas.

### a. Um agente que detecta apenas informações parciais sobre o estado não pode ser perfeitamente racional.

* **Julgamento:** **Falso (F)**
* **Justificativa:** A racionalidade perfeita depende da **maximização do desempenho esperado** com base na sequência de percepções recebidas até o momento e no conhecimento prévio do agente, e **não da onisciência** ou da posse de informação perfeita do estado real do ambiente. Mesmo em ambientes parcialmente observáveis, um agente pode agir de forma totalmente racional ao tomar as melhores decisões possíveis com a informação parcial disponível.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Um agente limpador de pó em um ambiente com duas salas ($A$ e $B$) possui apenas sensor de sujeira local, mas não possui sensor de localização (não sabe em qual sala está). Se a sua regra for "se a sala atual estiver suja, limpe; se limpa, mova-se para a outra", ele maximiza o retorno esperado de limpeza com base unicamente em suas percepções parciais, atuando de maneira perfeitamente racional.

---

### b. Existem ambientes de tarefa nos quais nenhum agente reativo puro pode comportar-se racionalmente.

* **Julgamento:** **Verdadeiro (V)**
* **Justificativa:** Agentes reativos puros (reflexos simples) tomam decisões baseando-se **apenas na percepção atual**, ignorando o histórico de percepções. Em ambientes parcialmente observáveis que exigem memória do passado para resolver ambiguidade de estados (loops infinitos ou falta de informação crítica), agentes reativos puros entram em ciclos ineficientes ou realizam ações incorretas, falhando em maximizar a medida de desempenho.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Um robô aspirador em um labirinto parcialmente observável sem sensores de orientação precisa saber se acabou de virar à esquerda ou se já visitou determinado corredor para não ficar preso em um loop infinito. Um agente reativo puro sem memória ficará alternando perpetuamente entre os mesmos dois estados.

---

### c. Existe um ambiente de tarefa em que todo agente é racional.

* **Julgamento:** **Verdadeiro (V)**
* **Justificativa:** Se a medida de desempenho for construída de tal forma que qualquer ação tomada pelo agente resulte na pontuação máxima possível (ou se o conjunto de ações não interferir no resultado final), então qualquer agente, independentemente de sua função de agente ou comportamento, será racional.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Um ambiente onde a medida de desempenho atribui a mesma pontuação constante para qualquer sequência de estados (por exemplo, pontuação $+100$ incondicional), ou um ambiente onde a única ação possível é `Nenhum-Op`.

---

### d. A entrada para o programa de agente é a mesma que a entrada para a função de agente.

* **Julgamento:** **Falso (F)**
* **Justificativa:** A **função de agente** é uma descrição matemática abstrata que mapeia toda a **história/sequência completa de percepções** $P^*$ para uma ação $A$. Por outro lado, o **programa de agente** roda em uma arquitetura física real e recebe como entrada apenas a **percepção atual** $p$, gerenciando internamente sua própria memória/estado para manter o histórico se necessário.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Em um jogo de xadrez, a função de agente recebe como entrada a lista de todos os lances e tabuleiros desde o início da partida. O programa do agente recebe como entrada apenas a imagem/estado visual do tabuleiro no turno atual.

---

### e. Toda função de agente é implementável por uma combinação de programa/máquina.

* **Julgamento:** **Falso (F)**
* **Justificativa:** Existem limitações teóricas da computabilidade e limitações de recursos físicos (tempo e memória). O conjunto de todas as funções de agente possíveis de uma sequência de percepções para ações é não-enumerável/infinito, enquanto o conjunto de programas de computador executáveis é enumerável. Além disso, certas funções exigem processamento de instâncias indecidíveis (Problema da Parada de Turing) ou utilizam tabelas de tamanho impraticável (maior do que o número de átomos no universo).
* **Exemplo / Contraexemplo:**
  * *Contraexemplo:* Uma função de agente que exige analisar uma sequência arbitrária de código e decidir se ele vai entrar em um loop infinito antes de escolher a ação `Sim` ou `Não` é incomputável.

---

### f. Suponha que um agente selecione sua ação uniformemente ao acaso do conjunto de ações possíveis. Existe um ambiente de tarefa determinista em que esse agente é racional.

* **Julgamento:** **Verdadeiro (V)**
* **Justificativa:** Em um ambiente de tarefa determinista no qual todas as ações possíveis produzem resultados idênticos quanto à pontuação de desempenho, selecionar qualquer ação aleatoriamente trará o resultado ótimo esperado, satisfazendo o critério de racionalidade.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* Um ambiente determinista no qual o agente tem como ações `Girar_Esquerda` e `Girar_Direita`, e a medida de desempenho premia apenas o tempo de funcionamento da bateria sem importar a orientação da câmera.

---

### g. É possível para um dado agente ser perfeitamente racional em dois ambientes de tarefa distintos.

* **Julgamento:** **Verdadeiro (V)**
* **Justificativa:** Um agente é definido pelo seu mapeamento interno e comportamento. Se o mesmo comportamento maximizar o resultado esperado sob a medida de desempenho de dois ambientes com dinâmicas ou estruturas de recompensa distintas, o agente será perfeitamente racional em ambos.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* O agente aspirador de pó com a regra simples "se sujo, limpe; senão, mova para o outro lado" é perfeitamente racional tanto em um ambiente onde limpar dá $+1$ ponto e mover dá $0$ pontos, quanto em um ambiente onde limpar dá $+10$ pontos e mover dá $-1$ ponto (desde que a sujeira surja na mesma taxa).

---

### h. Todo agente é racional em um ambiente não observável.

* **Julgamento:** **Falso (F)**
* **Justificativa:** Um ambiente não observável significa que o agente não recebe percepções. No entanto, o agente ainda possui seu conhecimento prévio sobre a estrutura do ambiente e as consequências de suas ações. Agentes que executam sequências de ações cegas porém eficientes (baseadas no estado de crença) serão racionais, enquanto agentes que realizam ações nocivas ao seu objetivo esperado serão irracionais.
* **Exemplo / Contraexemplo:**
  * *Contraexemplo:* Um limpador automático de ruas em um ambiente não observável que escolhe acelerar cegamente em direção a uma parede em vez de seguir um padrão de varredura pré-programado seguro e abrangente.

---

### i. Um agente jogador de pôquer perfeitamente racional nunca perde.

* **Julgamento:** **Falso (F)**
* **Justificativa:** O pôquer é um jogo de informação imperfeita (ambiente parcialmente observável) e de natureza estocástica (depende do baralhamento das cartas). Racionalidade é sobre **tomar a decisão esperada ideal**, não sobre garantir o resultado final em cenários onde o acaso interfere. Um agente perfeitamente racional pode jogar a mão probabilisticamente perfeita e ainda assim perder devido à sorte do adversário em tirar a carta vencedora no *river*.
* **Exemplo / Contraexemplo:**
  * *Exemplo:* O agente possui uma quadra de Reis (uma mão com $99.9\%$ de chance de vitória) e aposta tudo de forma racional. O oponente, jogando de forma totalmente irracional, pagou a aposta com uma mão ruim e consegue uma quadra de Ás na última carta sorteada do baralho, fazendo o agente racional perder a partida.
