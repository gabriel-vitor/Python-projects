import sys
import random
import time

#Nesse primeiro projeto, o professor da disciplina não perimitiu utilizar funçoes (modularizar o código), porque o assunto ainda não tinha sido dado.
#Sendo assim, esse projeto ficou muito extenso. Como a discplina era introdutória e eu era iniciante, há algumas más práticas como por exemplo, algumas
#variáveis iniciadas em letra maiuscula.

#In this first project, the teacher of the subject did not perimit to use functions (modularize the code), because the subject had not yet been given.
#This being so, this project became very extensive. As the discpline was introductory and I was a beginner, there are some bad practices like, for example, some
#variables started in capital letters.

print('='*100)
print("Olá, bem vindo ao jogo Super Trunfo!")

print('='*100)

opcao = 0           #Criei uma variável igualando a zero para ser usada no laço de repetição while

while opcao != 2:     #o laço irá rodar enquanto a variável "opçao" for diferente de 2, pois esse número é referente a opção de sair do jogo
    print("Digite:")
    print("[1] para ler as informações de jogo")
    print('[2] para sair do jogo')
    print('[3] para iniciar o jogo')

    opcao = str(input('Digite o número da sua opção: '))   #esse input serve para o usuário escolher sua opção

    if opcao == '1':           #através do if, será possível mostrar as informações do jogo caso o usuário digite 1
        print('=' * 100)
        print(" O Jogo Super Trunfo consiste em colocar dois jogadores para disputarem personagens de cartas.")
        print(" O tema escolhido é sobre Pokemons, e terá como atributos Força, Defesa e Vida. O jogo será ")
        print(" composto por 2 jogadores, que deverão informar seus nicknames e o número máximo de rodadas.")
        print(" Cada jogador receberá três cartas por rodada e cada carta terá um identificador.")
        print('=' * 100)

    elif opcao == '2': #para sair do programa por inteiro, importei a biblioteca nativa  sys do python e utilizei uma função aqui.
        print('='*100)
        print("Saindo do jogo...")
        sys.exit(0)

    elif opcao == '3':   #utilizando o break, a opção 3 sai do laço e vai para o código onde o jogo começa
        break
    else:
        print('='*100)
        print('Informação Inválida. Você só pode digitar os números 1, 2 ou 3.')  #aqui serve para evitar erros de digitos de outros números ou letras
        print('='*100)

print('Iniciando o jogo...')

Jogador1 = str(input('Jogador 1, digite o seu nick: ')) #aqui será feito o cadastro dos jogadores
Jogador2 = str(input('Jogador 2, digite o seu nick: '))

#os jogadores serão armazenados nessa lista para o sorteio.

Jogadores = [Jogador1, Jogador2]     

numero_minimo = 3   #o número mínimo de rodadas

# este while será responsável pela escolha do usuário do número de partidas. Caso o número digitado seja inferior ao valor mínimo de 3, será
# solictidado que o usuário escolha um número igual ou maior que 3. 

while numero_minimo == 3:
    numero_maximo = int(input('Digite o número de rodadas que deseja jogar:'))
    if numero_maximo >= numero_minimo:  
        print('Vamos lá!')
        break
    else:
        print('Número inválido. Só é permitido jogar três rodadas ou mais. Digite outro número')

#baralho de cartas

Cartas = ['Pikachu', 'Raichu', 'Squirtle', 'Bulbasaur', 'Charmander', 'Charizard','Kakuna', 'Weedle', 'Pidgey', 'Pidgeotto',
'Rattata','Raticate','Golem','Onix','Hitmonchan','Tangela','Dragonair','Dragonite','Mew','Mewtwo']

#Inicio das rodadas

print('Game Start!!')
print('-'*100)
print('Suas cartas serão mostradas por 10 segundos e a selecionada por mais 5 segundos.')

print('-'*100)

#distribuição de cartas
#o laço vai de zero até o número de rodadas escolhido

contador = 0
variaveldecontrole = 1
Pontuacao1 = 0      #a pontuação foi igualada a zero para que os valores sejam acumulados dentro do while futuramente
Pontuacao2 = 0

#este while será responsável pela decisão do usuário após o final da partida, se ele deseja jogar novamente ou encerrar o jogo

while variaveldecontrole ==1:
    print(''*100)
    while contador < numero_maximo:     #a partir desse while começa o embaralhamento das cartas, a distribuição e o ínicio da disputa

        random.shuffle(Cartas)

        print(Jogador1)

        atributoforca0 = random.randint(0,100)
        atributodefesa0 = random.randint(0,100)
        atributovida0 = random.randint(0,100)

        #os atributos serão adicionados numa lista.
        #uma lista será criada para cada carta.
        #o primeiro indice é referente ao nome da carta, utilizei a lista do baralho de cartas e o indice zero.
        #o fato das cartas esterem sendo embaralhadas no começo do laço evita que elas se repitam com o mesmo índice.

        Carta1 = [Cartas[0], 'Força:', atributoforca0, 'Defesa:', atributodefesa0, 'Vida:', atributovida0] 
        print(Carta1)

        atributoforca1 = random.randint(0,100)         #os atributos da primeira carta
        atributodefesa1 = random.randint(0,100)
        atributovida1 = random.randint(0,100)


        Carta2 = [Cartas[1], 'Força:', atributoforca1, 'Defesa:', atributodefesa1, 'Vida:', atributovida1]
        print(Carta2)
        
        atributoforca2 = random.randint(0,100)          #a variável dos atributos da segunda carta terão nomes diferentes
        atributodefesa2 = random.randint(0,100)         #para evitar que se repitam. O mesmo irá acontecer com as demais
        atributovida2 = random.randint(0,100)

        
        Carta3 = [Cartas[2], 'Força:', atributoforca2, 'Defesa:', atributodefesa2, 'Vida:', atributovida2]
        print(Carta3)
        print('='*100)
        time.sleep(10)
        print("\n"*100)

        print(Jogador2)


        atributoforca3 = random.randint(0,100)
        atributodefesa3 = random.randint(0,100)
        atributovida3 = random.randint(0,100)

        
        Carta4 = [Cartas[3],'Força:', atributoforca3, 'Defesa:', atributodefesa3, 'Vida:', atributovida3]
        print(Carta4)

        atributoforca4 = random.randint(0,100)
        atributodefesa4 = random.randint(0,100)
        atributovida4 = random.randint(0,100)

        
        Carta5 = [Cartas[4],'Força:', atributoforca4, 'Defesa:', atributodefesa4, 'Vida:', atributovida4]
        print(Carta5)

        atributoforca5 = random.randint(0,100)
        atributodefesa5 = random.randint(0,100)
        atributovida5 = random.randint(0,100)

        
        Carta6 = [Cartas[5],'Força:', atributoforca5, 'Defesa:', atributodefesa5, 'Vida:', atributovida5]
        print(Carta6)
        print('='*100)
        time.sleep(10)
        print("\n"*100)

    #a partir daqui, será feito o sorteio dos jogadores
    # #logo em seguida terá um input para a escolha do atributo e dentro desse input um if com outro input para a escolha das cartas.    

        sorteio = random.choice(Jogadores)
        if sorteio == Jogadores[0]:
            print('o jogador sorteado é o Jogador 1: ', Jogador1)
            escolha_atributo = int(input('escolha seu atributo \n [1]Força \n [2]Defesa \n [3]Vida'))
            if escolha_atributo == 1:
                print('o atributo escolhido foi Força')
                print('suas cartas são \n {} \n {} \n {}'.format(Carta1, Carta2, Carta3))
                escolha_carta1 = int(input('Escolha sua carta [1] Primeira [2] Segunda [3] Terceira: '))
                if escolha_carta1 == 1:
                    print('A carta do jogador 1 é:', Carta1)
                    escolhida1 = Carta1                      #foi criada uma variável para receber o valor da lista Carta1 e o mesmo se repete 
                    time.sleep(5)                            #para as outras cartas
                    print("\n"*100)

                elif escolha_carta1 == 2:
                    print('A carta do jogador 1 é:', Carta2)
                    escolhida1 = Carta2             
                    time.sleep(5)
                    print("\n"*100)             # esta linha de código serve para limpar a tela. Ela se repete em algumas partes do código.

                elif escolha_carta1 == 3:
                    print('A carta do jogador 1 é:', Carta3)
                    escolhida1 = Carta3
                    time.sleep(5)
                    print("\n"*100)
                
                print('='*100)
                print('Jogador 2, suas cartas são \n {} \n {} \n {}'.format(Carta4, Carta5, Carta6))
                print('-'*100)
                print('a carta do seu oponente é: ', escolhida1)
                print('-'*100)
                escolha_carta2 = int(input('Jogador 2, escolha sua carta [1] Primeira [2] Segunda [3] Terceira:')) #o jogador oposto escolhe a carta
                if escolha_carta2 == 1:
                    print('a carta do jogador 2 é:', Carta4)
                    escolhida2 = Carta4
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 2:
                    print('a carta do jogador 2 é:', Carta5)
                    escolhida2 = Carta5
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 3:
                    print('a carta do jogador 2 é:', Carta6)
                    escolhida2 = Carta6
                    time.sleep(5)
                    print("\n"*100)

                if escolhida1[2] > escolhida2[2]:                 # os valores são comparados utilizando o o indice da lista referente a carta 
                    print('Vitória do Jogador 1:', Jogador1)      # que foi transformada na variável "escolhida1" e "escolhida2".
                    Pontuacao1 += escolhida1[2]                   # a pontuação do vencedor se torna o valor do atributo escolhido.
                elif escolhida1[2] == escolhida2[2]:
                    print('deu empate!')
                elif escolhida1[2] < escolhida2[2]:
                    print('Vitória do Jogador 2:', Jogador2)
                    Pontuacao2 += escolhida2[2]
                

            elif escolha_atributo == 2:                         
                print('o atributo escolhido foi Defesa')
                print('suas cartas são \n {} \n {} \n {}'.format(Carta1, Carta2, Carta3))
                escolha_carta1 = int(input('Escolha sua carta [1] Primeira [2] Segunda [3] Terceira: '))
                if escolha_carta1 == 1:
                    print('A carta do jogador 1 é:', Carta1)
                    escolhida1 = Carta1
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 2:
                    print('A carta do jogador 1 é:', Carta2)
                    escolhida1 = Carta2
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 3:
                    print('A carta do jogador 1 é:', Carta3)
                    escolhida1 = Carta3
                    time.sleep(5)
                    print("\n"*100)
                
                print('='*100)
                print('Jogador 2, suas cartas são \n {} \n {} \n {}'.format(Carta4, Carta5, Carta6))
                print('-'*100)
                print('a carta do seu oponente é: ', escolhida1)
                print('-'*100)
                escolha_carta2 = int(input('Jogador 2, escolha sua carta [1] Primeira [2] Segunda [3] Terceira:'))
                if escolha_carta2 == 1:
                    print('a carta do jogador 2 é:', Carta4)
                    escolhida2 = Carta4
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 2:
                    print('a carta do jogador 2 é:', Carta5)
                    escolhida2 = Carta5
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 3:
                    print('a carta do jogador 2 é:', Carta6)
                    escolhida2 = Carta6
                    time.sleep(5)
                    print("\n"*100)

                if escolhida1[4] > escolhida2[4]:
                    print('Vitória do Jogador 1:', Jogador1)
                    Pontuacao1 += escolhida1[4]
                elif escolhida1[4] == escolhida2[4]:
                    print('deu empate!')
                elif escolhida1[4] < escolhida2[4]:
                    print('Vitória do Jogador 2:', Jogador2)               
                    Pontuacao2 += escolhida2[4]

            elif escolha_atributo == 3:
                print('o atributo escolhido foi Vida')
                print('suas cartas são \n {} \n {} \n {}'.format(Carta1, Carta2, Carta3))
                escolha_carta1 = int(input('Escolha sua carta [1] Primeira [2] Segunda [3] Terceira: '))
                if escolha_carta1 == 1:
                    print('A carta do jogador 1 é:', Carta1)
                    escolhida1 = Carta1
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 2:
                    print('A carta do jogador 1 é:', Carta2)
                    escolhida1 = Carta2
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 3:
                    print('A carta do jogador 1 é:', Carta3)
                    escolhida1 = Carta3
                    time.sleep(5)
                    print("\n"*100)
                
                print('='*100)
                print('Jogador2, suas cartas são \n {} \n {} \n {}'.format(Carta4, Carta5, Carta6))
                print('-'*100)
                print('a carta do seu oponente é: ', escolhida1)
                print('-'*100)
                escolha_carta2 = int(input('Jogador 2, escolha sua carta [1] Primeira [2] Segunda [3] Terceira:'))
                if escolha_carta2 == 1:
                    print('a carta do jogador 2 é:', Carta4)
                    escolhida2 = Carta4
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 2:
                    print('a carta do jogador 2 é:', Carta5)
                    escolhida2 = Carta5
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 3:
                    print('a carta do jogador 2 é:', Carta6)
                    escolhida2 = Carta6
                    time.sleep(5)
                    print("\n"*100)

                if escolhida1[6] > escolhida2[6]:
                    print('Vitória do Jogador 1:', Jogador1)
                    Pontuacao1 += escolhida1[6]
                elif escolhida1[6] == escolhida2[6]:
                    print('deu empate!')
                elif escolhida1[6] < escolhida2[6]:
                    print('Vitória do Jogador 2:', Jogador2)               
                    Pontuacao2 += escolhida2[6]

    #a partir daqui, começa a vez do jogador 2 caso ele seja sorteado. Todo o código é repetido, invertendo apenas os valores
    #das variáveis e do índice das listas.

        else:        

            print('o jogador sorteado é o Jogador 2: ', Jogador2)
            escolha_atributo = int(input('escolha seu atributo \n [1]Força \n [2]Defesa \n [3]Vida'))
            if escolha_atributo == 1:
                print('o atributo escolhido foi Força')
                print('suas cartas são \n {} \n {} \n {}'.format(Carta4, Carta5, Carta6))
                escolha_carta2 = int(input('Escolha sua carta [1] Primeira [2] Segunda [3] Terceira: '))
                if escolha_carta2 == 1:
                    print('A carta do jogador 2 é:', Carta4)
                    escolhida2 = Carta4
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 2:
                    print('A carta do jogador 2 é:', Carta5)
                    escolhida2 = Carta5
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 3:
                    print('A carta do jogador 2 é:', Carta6)
                    escolhida2 = Carta6
                    time.sleep(5)
                    print("\n"*100)
                
                print('='*100)
                print('Jogador 1, suas cartas são \n {} \n {} \n {}'.format(Carta1, Carta2, Carta3))
                print('-'*100)
                print('a carta do seu oponente é: ', escolhida2)
                print('-'*100)
                escolha_carta1 = int(input('Jogador 1, escolha sua carta [1] Primeira [2] Segunda [3] Terceira:'))
                if escolha_carta1 == 1:
                    print('a carta do jogador 1 é:', Carta1)
                    escolhida1 = Carta1
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 2:
                    print('a carta do jogador 1 é:', Carta2)
                    escolhida1 = Carta2
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 3:
                    print('a carta do jogador 1 é:', Carta3)
                    escolhida1 = Carta3
                    time.sleep(5)
                    print("\n"*100)

                if escolhida2[2] > escolhida1[2]:
                    print('Vitória do Jogador 2:', Jogador2)
                    Pontuacao2 += escolhida2[2]
                elif escolhida2[2] == escolhida1[2]:
                    print('deu empate!')
                elif escolhida2[2] < escolhida1[2]:
                    print('Vitória do Jogador 1:', Jogador1)
                    Pontuacao1 += escolhida1[2]
                

            elif escolha_atributo == 2:
                print('o atributo escolhido foi Defesa')
                print('suas cartas são \n {} \n {} \n {}'.format(Carta4, Carta5, Carta6))
                escolha_carta2 = int(input('Escolha sua carta [1] Primeira [2] Segunda [3] Terceira: '))
                if escolha_carta2 == 1:
                    print('A carta do jogador 2 é:', Carta4)
                    escolhida2 = Carta4
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 2:
                    print('A carta do jogador 2 é:', Carta5)
                    escolhida2 = Carta5
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 3:
                    print('A carta do jogador 2 é:', Carta6)
                    escolhida2 = Carta6
                    time.sleep(5)
                    print("\n"*100)
                
                print('='*100)
                print('jogador 1, suas cartas são \n {} \n {} \n {}'.format(Carta1, Carta2, Carta3))
                print('-'*100)
                print('a carta do seu oponente é: ', escolhida2)
                print('-'*100)
                escolha_carta1 = int(input('Jogador 1, escolha sua carta [1] Primeira [2] Segunda [3] Terceira:'))
                if escolha_carta1 == 1:
                    print('a carta do jogador 1 é:', Carta1)
                    escolhida1 = Carta1
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 2:
                    print('a carta do jogador 1 é:', Carta2)
                    escolhida1 = Carta2
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 3:
                    print('a carta do jogador 1 é:', Carta3)
                    escolhida1 = Carta3
                    time.sleep(5)
                    print("\n"*100)

                if escolhida2[4] > escolhida1[4]:
                    print('Vitória do Jogador 2:', Jogador2)
                    Pontuacao2 += escolhida2[4]
                elif escolhida2[4] == escolhida1[4]:
                    print('deu empate!')
                elif escolhida2[4] < escolhida1[4]:
                    print('Vitória do Jogador 1:', Jogador1)               
                    Pontuacao1 += escolhida1[4]

            elif escolha_atributo == 3:
                print('o atributo escolhido foi Vida')
                print('suas cartas são \n {} \n {} \n {}'.format(Carta4, Carta5, Carta6))
                escolha_carta2 = int(input('Escolha sua carta [1] Primeira [2] Segunda [3] Terceira: '))
                if escolha_carta2 == 1:
                    print('A carta do jogador 2 é:', Carta4)
                    escolhida2 = Carta4
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 2:
                    print('A carta do jogador 2 é:', Carta5)
                    escolhida5 = Carta5
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta2 == 3:
                    print('A carta do jogador 2 é:', Carta6)
                    escolhida2 = Carta6
                    time.sleep(5)
                    print("\n"*100)
                
                print('='*100)
                print('Jogador 1, suas cartas são \n {} \n {} \n {}'.format(Carta1, Carta2, Carta3))
                print('-'*100)
                print('a carta do seu oponente é: ', escolhida2)
                print('-'*100)
                escolha_carta1 = int(input('Jogador 1, escolha sua carta [1] Primeira [2] Segunda [3] Terceira:'))
                if escolha_carta1 == 1:
                    print('a carta do jogador 1 é:', Carta1)
                    escolhida1 = Carta1
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 2:
                    print('a carta do jogador 2 é:', Carta2)
                    escolhida1 = Carta2
                    time.sleep(5)
                    print("\n"*100)

                elif escolha_carta1 == 3:
                    print('a carta do jogador 1 é:', Carta3)
                    escolhida1 = Carta3
                    time.sleep(5)
                    print("\n"*100)

                if escolhida2[6] > escolhida1[6]:
                    print('Vitória do Jogador 2:', Jogador2)
                    Pontuacao2 += escolhida2[6]
                elif escolhida2[6] == escolhida1[6]:
                    print('deu empate!')
                elif escolhida2[6] < escolhida1[6]:
                    print('Vitória do Jogador 1:', Jogador1)               
                    Pontuacao1 += escolhida1[6]

        contador = contador + 1  #o contador é somado a ele mesmo com o valor de 1 para que chegue até o número de rodadas escolhido e ecerrando o laço
        if contador < numero_maximo:
            print('-'*100)
            print('Próxima rodada!')  
            print('-'*100)
        else:
            print('Rodada encerrada')                 
                                 
    if Pontuacao1 > Pontuacao2:
        print('Jogador 1 venceu a partida!!', Jogador1)
        print('Pontuacao:', Pontuacao1)
        print('Jogador 2 perdeu :(', Jogador2)
        print('Pontuação: ', Pontuacao2)

    elif Pontuacao1 == Pontuacao2:
        print('ops, parece que temos um empate')

    elif Pontuacao1 < Pontuacao2:
        
        print('Jogador 2 venceu a partida!!', Jogador2)
        print('Pontuação:', Pontuacao2)
        print('Jogador 1 perdeu :(', Jogador1)
        print('Pontuação:', Pontuacao1)

    variaveldecontrole = int(input('deseja iniciar uma nova partida? [1] Sim / [2] Não:  '))
    if variaveldecontrole == 1:
        print('*'*100)
        print('iniciando nova partida')
        print('*'*100)
        contador = 0              #para que a partida se inicie, é preciso zerar o contador, senão a disputa dos jogadores será ignorada.
    else:
        print('*'*100)
        print('Encerrando o jogo')
        print('*'*100)







             
            







    
                
                
    
    

    
                
                






     

    
