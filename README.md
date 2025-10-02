# Joquenp-
#Código para se jogar joquenpô(Pedra Papel Tesoura)
#Code to play rock paper scissors (In Brazilian Portuguese)

from time import sleep
from random import randint
fim = bool(False)
cont = bool(True)
comp = int(0)
pontuacaojog = int(0)
pontuacaocomp = int(0)
print("-><-"*15)
print("Bem-Vindo ao JOQUENPÔ")
while not fim:
    while cont:
        print("-><-" * 15)
        jog = str(input("""Qual a sua jogada? \n-Papel \n-Tesoura \n-Pedra\n-Sair \n->""")).lower().strip()
        if jog != "sair":
            comp = randint(1,3) # 1-Papel 2-Tesoura 3-Pedra
            print("pensando...............")
            sleep(1)
            if comp == 1:
                print("Papel!!!")
            elif comp ==2:
                print("Tesoura!!!")
            else:
                print("Pedra!!!")
            sleep(1)
            match jog:
                case "papel":
                    if comp == 1:
                        print("Empate! Tente novamente!")
                    elif comp ==2:
                        print("Perdeu! Vamos de novo!")
                        pontuacaocomp = pontuacaocomp + 1
                    else:
                        print("Ganhou! Vamos mais uma vez?")
                        pontuacaojog = pontuacaojog + 1
                case "tesoura":
                    if comp == 1:
                        print("Ganhou! Vamos mais uma vez?")
                        pontuacaojog = pontuacaojog + 1
                    elif comp == 2:
                        print("Empate! Tente novamente!")
                    else:
                        print("Perdeu! Vamos de novo!")
                        pontuacaocomp = pontuacaocomp + 1
                case "pedra":
                    if comp == 1:
                        print("Perdeu! Vamos de novo!")
                        pontuacaocomp = pontuacaocomp + 1
                    elif comp == 2:
                        print("Ganhou! Vamos mais uma vez?")
                        pontuacaojog = pontuacaojog + 1
                    else:
                        print("Empate! Tente novamente!")
                case _:
                    print("Por favor certifique-se que escolha uma das opções e que escreveu certo.")
        else:
            fim = True
            cont = False
        print("-><-" * 15)
        print(">--( computador {}x{} jogador )--<".format(pontuacaocomp, pontuacaojog))
        sleep(1)
print("-><-"*15)
print("Obrigado por jogar! Até a próxima!")
print("-><-"*15)
