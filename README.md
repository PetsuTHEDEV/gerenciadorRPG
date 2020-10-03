# Gerenciador de RPG - PROGRAMAÇÃO

  Aqui vamos detalhar algumas tarefas que o programador
  ter que desenvolver e pensar na hora de programar,
  como desenvolvimento do chat e etc.
  
## Itens para Programar

- [ ] Desenvolver o chat para contar as histórias do RPG
- [ ] Criar opções para o chat (Fala, Sussurro, Narração)
- [ ] Defenir a dois tipo de usuário: 
(Mestre: Teria opções de gerenciar o RPG, Player: Participar da história e fazer missões)
- [ ] Desenvolver comandos para o Mestre
- [ ] Criar um sistema de Inventário 
- [ ] Itens funcionais
- [ ] Criar um sistema de Monstro
- [ ] Sistema de missões

# Survive My World - SCRIPT

_Esse documento é apenas uma base, tudo pode ser mudado durante a criação do jogo, número e cálculos são apenas exemplos, durante a criação que vamos realmente fazer os cálculos reais. Nem tudo que foi colocado aqui deve ser seguido como regra, mas apenas como meta que precisamos no mínimo se aproximar._

**Descrição:** É um jogo de RPG, onde sua trama passa em grande parte em um chat, onde jogadores podem comunicarem em buscar de resolver o problema atribuídos por um mestre dono da mesa, esse mestre tem uma única função criar um mundo imaginário e fazer teste aos aventureiros para ver o nível de inteligência que todos tem para resolver os problemas proposto. Há também a possibilidade de o mestre passar um problema e apenas uma pessoa responder. Como, por exemplo, digamos que o grupo optou a abrir um baú, seria mais interessante que o personagem que tenha uma sorte maior abra o baú para encontrar itens melhores.

**Janela:** Seria interessante uma janela dividida ao meio uma para o chat e a outra parte para a situações que vão ser ilustradas. Isso na tela dos roleplayers, mas o mestre vai ser uma parte para o chat e outra para as opções que eles vão controlar a história dos roleplayers.

## Mecânicas:

**Roleplayer:**
- Conversar no chat com os outros Player
- Criar ficha para o personagem.
- Votar nas escolhas oferecida pelo Mestre
- Gerenciar itens do Inventário
- Usar os itens do inventário
- Atacar contra Monstro
- Defender do Monstro
- Alterar configuração de Áudio

**Mestre:**
- Controlar turno dos players. (Pula turno)
- Mandar Situação para players.
- Gerar Itens para os players.
- Gerar Monstro para os players.
- Dar Opções de Escolhas
- Expulsar um player.
- Controlar Monstro.
- Alterar configuração de Áudio.
- Girar dado.
- Matar player.

## Mapa de navegação do Jogo:

Menu < --------- > Jogar < ---------- > Criar Sala < -------- > Escolher Modo < ------ > Tela do RPG – Mestre

Menu < --------- > Jogar < ---------- > Entrar Sala < ------ > Criar ficha < --------- >Tela do RPG – Roleplayer

Menu < ---------> Instruções

Menu < --------- > Sair

## Sistemas do RPG

### Atributos

Atributos são as qualidades e característica que são próprias para cada player. Então, vamos desenvolver
um padrão inicial para cada player, ou vamos fazer com que ele ganhe pontos para gastar com quais atributos ele mais deseja. Esses atributos vão influencia bastante no jogo. Por exemplo: Caso o player opte em ser um cara com 100 de armadura, que vai ser um dos atributos adicionados, então ele vai ser considerado um tanque. Danos como armas, socos ou quaisquer coisas nesse estilo, não causaram muito efeito nesse player, porém, outro atributo é resistência mágica e se o player optou em armadura, a resistência mágica dele é muito baixa, sendo assim ele vai morrer muito fácil para magia.
	
**OFENCISO**
	
- Ataque: São a força do ataque normal de cada player, ele não é bom conta armadura como já explicado, todos vão ter no mínimo 20 de ataque, que é o dano que vai ser causado em um monstro em média.
- Magia: São a força magica de personagens mágicos, ele não é bom com personagem que tem resistência mágica.
- Roubo de vida: dependendo do dano causado uma porcentagem vai ser adicionada como regeneração na vida do personagem.
- Sangramento: Ao ataque marca o personagem para leva dano ao longo do turno.
	
**DEFENSIVO**
	
- Armadura: Esse atributo tem como objetivo diminui o dano de ataque que os monstros causaram, ele não é muito efetivo contra danos mágicos.
- Vida: A vida é um atributo que diferente da armadura que reduz o dano de ataque, a vida apenas aumenta sua vida padrão e perde a qualidade exata do ataque. Ao seja, é a vida adicional.
- Regeneração de Vida: É a quantidade de vida regenerada pelo personagem, essa é exclusiva para alguns personagens, sua vida é regenerada por turno dependendo de quanto tempo demorou para chegar no seu turno.
- Resistência Mágica: É igual a armadura, porém, ele vai diminui o dano de magia causado por monstros, ele não é muito efetivo contra dano de ataque.

**NEUTRO**

- Inteligência: Você tem a capacidade de melhorar equipamentos, melhorando o que o que determinado item de ataque ou defensivo faz, o bônus de melhora vai depender do nível de inteligência que você tem. Só funciona fora de batalhas e você só pode melhora item uma vez a cada 5 níveis.
- Sorte: Aumenta a sorte de encontrar um item bom, caso essa o personagem que abra o baú.
- Fé: Você ganha bônus em algum de seus atributos em um turno que você está prestes sê a morrer, quanto maior a fé, maior é esse bônus.
- Agilidade: Você torna-se mais rápido sendo capaz de desviar de ataque de monstro que serão direcionado até você, você com muita agilidade como já disse pode desviar de ataque, mas com um pouco de agilidade você pode diminuir o dano causado em você com ataque que pegaram de raspão. **OBSERVAÇÃO:** a cada 10 pontos de armadura você diminui 5 pontos de agilidade.

### Inventário e Itens

Precisamos criar um inventário com 9 slots(Ou menos), onde vai colocado os itens encontrados em grupo, podemos definir se os itens vão ser gerados igualmente para os participantes ou quem abrir o baú vai encontrar. Quando um item é encontrado ele é adicionado em um slot vazio, o player pode usar esse item durante. Caso o slot esteja cheio ele pode ou comprar um bolsa (Porém, nas versões futuras) ou jogar o item fora.

**OFENSIVO**

- Espada: +10 de dano de ataque, não ativável.
- Faca: +5 de dano de ataque, não ativável.
- Cajado de Luz: +10 de magia, ativável (Causa cegueira)
- Cajado de Planta: +5 de magia, ativável (Causa enraizamento)

**DEFENSIVO**

- Escudo: +20 de armadura
- Armadura: +50 de armadura
- Capa de Fogo: +20 de resistência mágica, ativável (Deixa o inimigo em chamas, Comba com sangramento)
- Capa de Invisibilidade: +5 de resistência mágica (Deixa invisível, pode ser atingido por golpes diretos, mas em área)

**NEUTRO**

- Porção de vida: Ativável (+ 100 da vida)
- Porção de Força: Ativável (+50 Ataque)
- Amuleto do Sol: Ativável (+60 vidas adicional por grupo)
- Amuleto de Fuga: Ativável (Deixa invulnerável, mas não pode atacar)

### Monstro

Monstros são na verdade controlados pelo mestre de mesa, ele que escolhe quem o monstro vai atacar, qual ataque o 
monstro vai usar e como o monstro vai se defender, a luta contra o monstro sempre vai ser em grupo. Os monstros 
vão ter atributos iguais os personagens, porém, claro que vão ser mais forte, já que a luta vai ser em grupo. Existem 4 
níveis de monstro. (Básico, Normais, Forte e os Boss) e matando o monstro que os personagens vão aumentar seus atributos. 
Além dos níveis dos monstros, temos também a tipo de monstro, habilidade e características especiais de cada monstros.

#### OBSERVAÇÕES

- Temos monstro que foca um alvo e temos monstro que ataque em área, os que focam um alvo devera focar primeiramente o personagem que está na frente e vai causar todo o dano que ele tem, já o que ataca quem área vai dividir o dano nós três da frente, mas sendo o maior dano no da frente.
	
- Temos habilidade de cada monstro, onde eles podem causar paralisia, sangramento, loucura, cura... Que escolhe quando usar essa habilidade é o mestre.
	
- Temos também cada tipo de monstro os que dão dano mágico, os que dão dano fico, os que tem os dois e os que roubam vida dos oponentes.

### Posicionamento

O sistema de posicionamento foi adicionado para cada personagem antes da luta escolher um lugar para se 
posicionar antes de uma luta, para criar uma dinâmica de classes uteis como tanque na frente, soldados 
atrás dos tanques, magos atrás com suporte ao lado.
	
Uma vez que os monstros atacaram quem estão na frente, ou seja, os tanques e soldados que tem mais resistência. 
E suporte e magos vão dar dano ou vida adicional.

 
### Condições

	Condições são estados alterados do personagem, causados por uma situação, devido a algum ataque de um monstro.

**Ruins**

- Atordoado: Você fica parado sem poder atacar por dois 
ou três turnos.
- Loucura: Você ataca um dos aliados mais próximo por
dois turnos.
- Cego: Você ainda pode atacar, mas não vai poder escolher
em quem e pode atingir um de seus amigos. Dura dois turnos.
- Preso: Você não pode se mover então sofrerá mais dano, 
mas pode usar habilidade de proteção e ataque.
- Fraqueza: seus ataques darem menos dano e você recebera
mais danos.
- Sangramento: Você leva danos aos poucos durante três turnos.

**Boas**

- Invulnerável: Você não sofrerá dano durante dois turnos.
- Velocista: Sua agilidade aumentara, fazendo com que você
não seja acertado.
- Invisível: Você ficara invisível e poderá atacar, sem ser
atacado por tiro direcionado a você.
- Vingador: Você vai retribuir todo o dano que você levou.
- Absorção: Você vai absorver todo o dano causado em você 
durante dois turnos e vai mandar de voltar. 

### Classes

As classes vão deixar o RPG mais interessante e foi o mais recomendado para adicionar ao RPG, então vamos 
tentar adicionar algumas classes dependendo dos ambientes escolhidos para ele. Temos algumas classes com
algumas habilidades e atributos exclusivos para elas, então vamos para algumas classes.

1. Espadachim: Agilidade+, Ataque+ 
- Q- Dash em direção ao inimigo causando dano.
- Ult- Acerta quatro golpes rápidos e causa 4x, o dano).

2.Necromante: +Magia +Resistência Mágica 
- Q- Amaldiçoa um corpo (fraqueza)
- Ult – ressuscita seus aliados por 2 turnos)


### Lutas

O sistema de luta vai ser o mais difícil, pois, nele que vamos adicionar a parte que vai ter a mecânica do jogo,
a luta de turnos, onde cada um ter sua vez de jogar e tem também as habilidades, classes e itens que vão 
ajudar a matar o monstro e ganhar experiência para passar desafios futuros. 
