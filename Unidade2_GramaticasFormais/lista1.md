Exercícios Comentados — Aulas 01 e 02
Linguagens Formais, Alfabeto, Linguagens e Gramáticas
Disciplina: Linguagens Formais e Autômatos Objetivo: revisar os conceitos fundamentais de alfabeto, palavras, linguagens e gramáticas, desenvolvendo também a capacidade de interpretar e ler a notação matemática.

Orientação ao estudante: primeiro leia e compreenda o exercício comentado. Em seguida, tente resolver o exercício proposto sem consultar o gabarito. Ao final do material, confira suas respostas.

1. Alfabeto
Exercício comentado
Considere o conjunto:

Σ
=
0
,
1

Pergunta: o que significa esse conjunto?

Resolução passo a passo
O símbolo 
Σ
 é utilizado para representar um alfabeto.

Um alfabeto é um conjunto finito de símbolos que podem ser utilizados para construir palavras.

Neste caso:

Σ
=
0
,
1

O alfabeto possui dois símbolos:

0
1
Como se lê?
Podemos ler:

"Sigma é o conjunto formado pelos símbolos zero e um."

Ou:

"O alfabeto Sigma é formado pelos símbolos 0 e 1."

Atenção
Os elementos 0 e 1 são símbolos individuais.

Não devemos confundir:

0
com:

01
O primeiro é um símbolo.

O segundo é uma sequência de símbolos, ou seja, uma palavra.

Exercício para o estudante
Considere:

Σ
=
a
,
b
,
c

Responda:

Quantos símbolos existem no alfabeto?
Quais são os símbolos?
O símbolo a pertence ao alfabeto?
O símbolo d pertence ao alfabeto?
Escreva uma palavra formada por símbolos desse alfabeto.
2. Palavras sobre um alfabeto
Exercício comentado
Considere:

Σ
=
a
,
b

Verifique quais das sequências abaixo são palavras construídas sobre esse alfabeto:

abba
abc
baab
d
Resolução
Uma palavra é uma sequência finita de símbolos pertencentes ao alfabeto.

Nosso alfabeto é:

Σ
=
a
,
b

Palavra abba
Observe:

a b b a
Todos os símbolos pertencem ao alfabeto.

Portanto:

a
b
b
a
∈
Σ
∗

Como se lê?
"abba pertence ao conjunto de todas as palavras construídas sobre Sigma."

Palavra abc
Observe:

a b c
O símbolo c pertence ao alfabeto?

Não.

Temos:

c
∉
Σ

Portanto:

a
b
c
∉
Σ
∗

Palavra baab
Observe:

b a a b
Todos os símbolos pertencem a:

Σ
=
a
,
b

Logo:

b
a
a
b
∈
Σ
∗

Palavra d
O símbolo d não pertence ao alfabeto.

Portanto:

d
∉
Σ
∗

Exercício para o estudante
Considere:

Σ
=
0
,
1

Classifique cada sequência como palavra válida ou não válida:

Sequência	Válida?	Justificativa
0101		
00110		
012		
111		
10a		
3. Pertinência de símbolos e palavras
Exercício comentado
Considere:

Σ
=
a
,
b
,
c

Determine se:

a
∈
Σ

e se:

a
b
∈
Σ

Resolução
Primeiro analisamos:

a
∈
Σ

O símbolo a está dentro do conjunto?

Sim.

Portanto:

a
∈
Σ

Agora observe:

ab
ab possui dois símbolos:

a b
Portanto, ab é uma palavra, e não um símbolo individual do alfabeto.

Assim:

a
b
∉
Σ

Porém:

a
b
∈
Σ
∗

Como se lê?
a
∈
Σ

Lemos:

"a pertence a Sigma."

Já:

a
b
∈
Σ
∗

Lemos:

"ab pertence ao conjunto de todas as palavras sobre Sigma."

Conceito importante
Não confunda:

a
∈
Σ

com:

a
b
∈
Σ

O primeiro representa um símbolo.

O segundo representa uma palavra.

Exercício para o estudante
Considere:

Σ
=
0
,
1

Determine se as afirmações são verdadeiras ou falsas:

0
∈
Σ
1
∈
Σ
01
∈
Σ
01
∈
Σ
∗
2
∈
Σ
101
∈
Σ
∗
Justifique cada resposta.

4. Linguagem
Exercício comentado
Considere:

Σ
=
a
,
b

e a linguagem:

L
=
a
,
a
b
,
a
b
b

O que é 
L
?
Uma linguagem é um conjunto de palavras.

Neste exemplo:

a
ab
abb
são as palavras que pertencem à linguagem.

Verificando ab
Queremos saber:

a
b
∈
L
?

Observe a linguagem:

L
=
a
,
a
b
,
a
b
b

A palavra ab aparece no conjunto.

Portanto:

a
b
∈
L

Verificando ba
Agora:

b
a
∈
L
?

A palavra ba não aparece no conjunto.

Portanto:

b
a
∉
L

Como se lê?
a
b
∈
L

Lemos:

"ab pertence à linguagem L."

Já:

b
a
∉
L

Lemos:

"ba não pertence à linguagem L."

Exercício para o estudante
Considere:

L
=
0
,
01
,
011
,
0111

Determine se cada palavra pertence à linguagem:

0
∈
L
01
∈
L
0111
∈
L
10
∈
L
111
∈
L
011
∈
L
5. Descrevendo uma linguagem por padrão
Exercício comentado
Considere:

L
=
a
,
a
a
,
a
a
a
,
a
a
a
a
,
…

Qual é o padrão dessa linguagem?

Resolução
Observe as palavras:

a
aa
aaa
aaaa
aaaaa
...
Todas possuem apenas o símbolo a.

A quantidade de a pode aumentar indefinidamente.

Podemos representar essa linguagem por:

L
=
a
n
∣
n
≥
1

Como se lê?
A expressão:

a
n

pode ser lida:

"a elevado a n"

Nesse contexto, significa:

"n ocorrências do símbolo a."

Por exemplo:

a
1
=
a

a
2
=
a
a

a
3
=
a
a
a

a
4
=
a
a
a
a

O símbolo:

∣

pode ser lido como:

"tal que"

Assim:

a
n
∣
n
≥
1

pode ser lido:

"O conjunto das palavras formadas por n ocorrências de a, tal que n é maior ou igual a 1."

Exercício para o estudante
Considere:

L
=
b
n
∣
n
≥
1

Escreva as cinco primeiras palavras.
Explique o significado de 
b
n
.
A palavra bbbbbb pertence à linguagem?
A palavra vazia (
ε
) pertence à linguagem?
6. Linguagem vazia e palavra vazia
Exercício comentado
Explique a diferença entre:

∅

e:

ε

Resolução
Esses dois símbolos possuem significados diferentes.

Conjunto vazio
∅

representa um conjunto que não possui elementos.

Uma linguagem vazia pode ser representada por:

L
=
∅

Isso significa:

A linguagem não possui nenhuma palavra.

Palavra vazia
ε

representa uma palavra que possui zero símbolos.

Uma linguagem que contém somente a palavra vazia é:

L
=
ε

Essa linguagem possui uma palavra.

Essa palavra possui comprimento zero.

Portanto:

∅
≠
ε

Como se lê?
∅

Lemos:

"Conjunto vazio."

ε

Lemos:

"Épsilon" ou "palavra vazia".

Exercício para o estudante
Explique, com suas próprias palavras, a diferença entre:

A
L
=
∅

B
L
=
ε

Depois responda:

Qual delas possui uma palavra?
Qual delas não possui nenhuma palavra?
Qual é o comprimento da palavra 
ε
?
7. Estrutura de uma gramática
Exercício comentado
Considere:

G
=
(
V
,
T
,
P
,
S
)

com:

V
=
S

T
=
a
,
b

e:

P
=
S
→
a
S
,
 
S
→
b

O que significa cada componente?
Uma gramática formal é representada por:

G
=
(
V
,
T
,
P
,
S
)

V
 — Variáveis ou não terminais
Temos:

V
=
S

O símbolo S será utilizado durante a derivação.

T
 — Terminais
Temos:

T
=
a
,
b

Os terminais são os símbolos que podem aparecer na palavra final.

P
 — Produções
Temos:

P
=
S
→
a
S
,
 
S
→
b

São as regras utilizadas para transformar ou substituir os não terminais.

S
 — Símbolo inicial
O símbolo inicial é:

S

É por ele que a derivação começa.

Como se lê?
G
=
(
V
,
T
,
P
,
S
)

Pode ser lido:

"G é uma gramática formada pelo conjunto de variáveis V, conjunto de terminais T, conjunto de produções P e símbolo inicial S."

Exercício para o estudante
Considere:

G
=
(
S
,
A
,
0
,
1
,
P
,
S
)

com:

P
=
S
→
0
A
,
 
A
→
1

Identifique:

O conjunto de variáveis.
O conjunto de terminais.
O conjunto de produções.
O símbolo inicial.
Qual palavra pode ser gerada por essa gramática?
8. Como ler e aplicar uma produção
Exercício comentado
Considere a produção:

S
→
a
S

Como se lê?
Podemos ler:

"S produz aS."

Também podemos dizer:

"S pode ser substituído por aS."

O símbolo:

→

pode ser lido como:

"produz"

ou:

"é substituído por".

Aplicando a regra
Começamos com:

S

Aplicamos a produção:

S
⇒
a
S

Podemos aplicar novamente:

a
S
⇒
a
a
S

E novamente:

a
a
S
⇒
a
a
a
S

Portanto:

S
⇒
a
S
⇒
a
a
S
⇒
a
a
a
S

Atenção
A derivação ainda não terminou.

Por quê?

Porque ainda existe um não terminal:

S

Uma derivação termina quando não existem mais não terminais.

Exercício para o estudante
Considere:

S
→
0
S

Começando com 
S
:

Aplique a regra uma vez.
Aplique a regra duas vezes.
Aplique a regra três vezes.
Escreva a sequência completa de derivação.
9. Derivação completa de uma palavra
Exercício comentado
Considere a gramática:

G
:
{
S
→
a
S
S
→
b

Queremos gerar:

aab
Passo 1 — Começar pelo símbolo inicial
S

Passo 2 — Produzir o primeiro a
Utilizamos:

S
→
a
S

Então:

S
⇒
a
S

Passo 3 — Produzir o segundo a
Ainda temos:

S

Aplicamos novamente:

S
→
a
S

Logo:

a
S
⇒
a
a
S

Passo 4 — Produzir b
Agora temos:

aaS
Queremos terminar com b.

Utilizamos:

S
→
b

Então:

a
a
S
⇒
a
a
b

Derivação completa
S
⇒
a
S
⇒
a
a
S
⇒
a
a
b

Como se lê?
Podemos ler:

"S deriva aS."

"aS deriva aaS."

"aaS deriva aab."

O símbolo:

⇒

representa uma derivação, ou seja, uma aplicação de uma regra de produção.

Quando termina?
A palavra final é:

aab
Não existe mais S.

Portanto, a derivação terminou.

Exercício para o estudante
Utilizando:

G
:
{
S
→
a
S
S
→
b

gere:

a
a
a
b

Escreva todos os passos da derivação.

10. Identificando palavras geradas por uma gramática
Exercício comentado
Considere:

G
:
{
S
→
0
S
S
→
1

Pergunta:

A palavra 001 pode ser gerada pela gramática?

Passo 1 — Começamos
S

Queremos gerar:

001
O primeiro símbolo é 0.

Utilizamos:

S
→
0
S

Portanto:

S
⇒
0
S

Passo 2
Ainda precisamos produzir:

01
Aplicamos novamente:

S
→
0
S

Então:

0
S
⇒
00
S

Passo 3
Agora queremos produzir 1.

Utilizamos:

S
→
1

Logo:

00
S
⇒
001

Derivação completa
S
⇒
0
S
⇒
00
S
⇒
001

Portanto:

001
∈
L
(
G
)

Como se lê?
001
∈
L
(
G
)

Lemos:

"001 pertence à linguagem gerada pela gramática G."

E a palavra 101?
Observe a gramática:

S
→
0
S

ou:

S
→
1

A regra que produz 1 encerra a derivação.

Portanto, não conseguimos gerar:

101
porque depois de produzir 1 não podemos voltar a produzir 0.

Logo:

101
∉
L
(
G
)

Exercício para o estudante
Considere novamente:

G
:
{
S
→
0
S
S
→
1

Determine se cada palavra pode ser gerada:

1
01
001
0001
101
1001
Para as palavras que podem ser geradas, apresente a derivação completa.

Gabarito Comentado
Exercício 1
Considere:

Σ
=
a
,
b
,
c

Respostas
O alfabeto possui 3 símbolos.
Os símbolos são:
a
,
 
b
,
 
c

Sim:
a
∈
Σ

Não:
d
∉
Σ

Exemplos de palavras válidas:
a
ab
abc
bca
cab
Comentário
Uma palavra pode possuir um ou vários símbolos, desde que todos pertençam ao alfabeto.

Exercício 2
Para:

Σ
=
0
,
1

Sequência	Resposta	Justificativa
0101	Válida	Todos os símbolos são 0 ou 1
00110	Válida	Todos os símbolos são 0 ou 1
012	Não válida	2 não pertence ao alfabeto
111	Válida	Todos os símbolos pertencem ao alfabeto
10a	Não válida	a não pertence ao alfabeto
Exercício 3
Para:

Σ
=
0
,
1

1.
0
∈
Σ

Verdadeiro.

2.
1
∈
Σ

Verdadeiro.

3.
01
∈
Σ

Falso.

01 é uma palavra, não um símbolo individual.

4.
01
∈
Σ
∗

Verdadeiro.

5.
2
∈
Σ

Falso.

6.
101
∈
Σ
∗

Verdadeiro.

Todos os símbolos de 101 pertencem ao alfabeto.

Exercício 4
Para:

L
=
0
,
01
,
011
,
0111

Palavra	Pertence a 
L
?
0	Sim
01	Sim
0111	Sim
10	Não
111	Não
011	Sim
Comentário
Uma palavra pertence à linguagem quando ela é um dos elementos definidos no conjunto.

Exercício 5
L
=
b
n
∣
n
≥
1

As cinco primeiras palavras são:

b
bb
bbb
bbbb
bbbbb
O símbolo:

b
n

representa n ocorrências de b.

A palavra:

bbbbbb
possui seis b.

Logo:

b
b
b
b
b
b
=
b
6

e:

b
b
b
b
b
b
∈
L

Já:

ε
∉
L

porque a condição determina:

n
≥
1

Exercício 6
A
L
=
∅

Não possui nenhuma palavra.

B
L
=
ε

Possui exatamente uma palavra:

ε

Essa palavra possui comprimento:

|
ε
|
=
0

Resposta
∅
≠
ε

Exercício 7
Considere:

G
=
(
S
,
A
,
0
,
1
,
P
,
S
)

com:

P
=
S
→
0
A
,
 
A
→
1

Respostas
Variáveis:

V
=
S
,
A

Terminais:

T
=
0
,
1

Produções:

P
=
S
→
0
A
,
 
A
→
1

Símbolo inicial:

S

Palavra gerada
Começamos:

S

Aplicamos:

S
→
0
A

Então:

S
⇒
0
A

Agora:

A
→
1

Logo:

0
A
⇒
01

Portanto:

01

Exercício 8
Aplicando:

S
→
0
S

três vezes:

S
⇒
0
S
⇒
00
S
⇒
000
S

Resposta
000
S

Atenção
A derivação ainda não terminou porque existe o não terminal:

S

Exercício 9
Para gerar:

aaab
temos:

S
⇒
a
S
⇒
a
a
S
⇒
a
a
a
S
⇒
a
a
a
b

Portanto:

a
a
a
b
∈
L
(
G
)

Como pensar?
Cada aplicação:

S
→
a
S

adiciona um a.

Quando já temos a quantidade necessária de a, utilizamos:

S
→
b

para finalizar.

Exercício 10
Gramática:

G
:
{
S
→
0
S
S
→
1

1. 1
Sim:

S
⇒
1

2. 01
Sim:

S
⇒
0
S
⇒
01

3. 001
Sim:

S
⇒
0
S
⇒
00
S
⇒
001

4. 0001
Sim:

S
⇒
0
S
⇒
00
S
⇒
000
S
⇒
0001

5. 101
Não.

Depois que utilizamos:

S
→
1

a derivação termina.

Não é possível produzir outro 0 ou 1.

6. 1001
Não.

A gramática permite:

zero ou mais 0
+
um 1 final
Portanto, palavras válidas possuem o formato:

000...001
A palavra 1001 começa com 1 e depois possui outros símbolos, o que não é permitido.

Resumo dos conceitos
Conceito	Significado
Σ
Alfabeto
a, b, 0, 1	Símbolos
w
Palavra
L
Linguagem
Σ
∗
Conjunto de todas as palavras sobre 
Σ
, incluindo 
ε
ε
Palavra vazia
∅
Conjunto vazio
w
∈
L
A palavra 
w
 pertence à linguagem
w
∉
L
A palavra 
w
 não pertence à linguagem
G
Gramática
V
Variáveis/não terminais
T
Terminais
P
Produções
S
Símbolo inicial
→
Produção/regra
⇒
Derivação
Checklist de estudo
Antes de avançar para os próximos conteúdos, verifique se você consegue:

 Explicar o que é um alfabeto.
 Identificar os símbolos de um alfabeto.
 Diferenciar símbolo de palavra.
 Explicar o que é uma linguagem.
 Verificar se uma palavra pertence a uma linguagem.
 Interpretar 
Σ
∗
.
 Diferenciar 
∅
 de 
ε
.
 Interpretar 
w
∈
L
.
 Identificar os componentes de uma gramática.
 Ler uma regra como 
S
→
a
S
.
 Realizar uma derivação passo a passo.
 Identificar quando uma derivação termina.
 Determinar se uma palavra pode ser gerada por uma gramática.
Desafio final
Considere:

G
:
{
S
→
a
S
S
→
b

Responda sem consultar o gabarito:

1.
A palavra b pode ser gerada?

2.
A palavra ab pode ser gerada?

3.
A palavra aab pode ser gerada?

4.
A palavra aaab pode ser gerada?

5.
A palavra aba pode ser gerada?

6.
Escreva a derivação completa de aaaab.

7.
Descreva, com suas palavras, o padrão das palavras geradas por essa gramática.

Dica: observe o que acontece quando aplicamos várias vezes 
S
→
a
S
 e, finalmente, utilizamos 
S
→
b

