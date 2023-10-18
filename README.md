#Exercício 1: dados
import random

class dado:
    def _init_(self,faces):
        self.faces = faces

def rolar(self):
    num = random.randint(1,self.faces)
    return num
    
dado_1 = dado(6)
dado_2 = dado(8)
dado_3 = dado(12)
count = 0

while count<3:
    input('pressione "ENTER" para jogar o dado de 6 faces:')
    roll = rolar(dado_1)
    print(roll)
    count+=1
else:
    count = 0

while count<3:
    input('pressione "ENTER" para jogar o dado de 8 faces:')
    roll = rolar(dado_2)
    print(roll)
    count+=1
else:
    count = 0

while count<3:
    input('pressione "ENTER" para jogar o dado de 12 faces:')
    roll = rolar(dado_3)
    print(roll)
    count+=1
else:
    print('Jogadas finalizadas')

#Exercício 2: Calculadora

class calculadora:
    def _init_(self,resultado):
        self.resultado = resultado
    
    def somar(self,num1,num2):
        self.resultado = num1 + num2
        return self.resultado
        
    def subtrair(self,num1,num2):
        self.resultado = num1 - num2
        return self.resultado
    
    def multiplicar(self,num1,num2):
        self.resultado = num1 * num2
        return self.resultado
    
    def dividir(self,num1,num2):
        if num2 == 0:
            print("divisão por 0")
            self.resultado = -1
            return self.resultado
        else:
            self.resultado = num1/num2
            return self.resultado

instancia = calculadora(0)

num1 = int(input("informe o primeiro número: "))

num2 = int(input("informe o segundo número: "))

instancia.somar(num1,num2)
print("soma = {:.2f}".format(instancia.resultado))

instancia.subtrair(num1,num2)
print("subtração = {:.2f}".format(instancia.resultado))

instancia.multiplicar(num1,num2)
print("multiplicação = {:.2f}".format(instancia.resultado))

instancia.dividir(num1,num2)
print("divisão = {:.2f}".format(instancia.resultado))

#Exercício 3: Cadastro

class CadastroCliente:
    def _init_(self,nome,sobrenome,data_nascimento,email,cpf,senha):
        self.nome = nome
        self.sobrenome = sobrenome
        self.data_nascimento = data_nascimento
        self.email = email
        self.cpf = cpf
        self.senha = senha
    
    def consulta(self):
        print("Nome: ",self.nome," ",self.sobrenome)
        print("Data de nascimento: ",self.data_nascimento)
        print("Email: ",self.email)
        print("CPF: ",self.cpf)

    def verificação(self,vlogin,vsenha):
        if vlogin == self.email and vsenha == self.senha:
            return True
        else:
            return False
            
nome = input('Informe seu nome: ')
sobrenome = input('Informe seu sobrenome: ')
data_nascimento = input("Informe sua data de nascimento: ")
email = input('Informe seu email: ')
cpf = input("Informe seu cpf: ")
senha = input("Informe uma senha: ")

cadastro = CadastroCliente(nome,sobrenome,data_nascimento,email,cpf,senha)

count = 0

while count<3:
  
    vlogin = input("Informe o email da sua conta: ")
    vsenha = input("Informe a senha da  sua conta: ")
    
    verificar = cadastro.verificação(vlogin,vsenha)
    
    if verificar == True:
        cadastro.consulta()
        break
    else:
        print("Senha ou usuário incorretos")
        count+=1
else:
    print("Falha ao realizar o login")

#Exercício 4: Corrida

import random

class Competidor:
    def _init_(self,nome):
        self.nome = nome
        self.pos = 0

    def get_pos(self):
        self.pos +=1
        return self.pos 
    

    def atualizar(self,grid):
        rodar = random.randint(2,6)
        self.pos += rodar
        if self.pos % 5 == 0 :
            self.pos -= 1
        elif self.pos == 7 or self.pos == 17:
            self.pos += 2
        elif self.pos == 13:
            self.pos == 0
        elif self.pos>=20:
            pass
        else:
            self.pos == self.pos
        for i in range(len(grid)):
            i += self.pos 
            if grid[i] != '*' and grid[i] != self.nome:
                print(grid[i],'disputando posição com ',self.nome)
                rodar = random.randint(0,10)
                if rodar % 2==0:
                    print(self.nome,'ultrapassou',grid[i])
                    grid[i] = self.nome
                    print(grid)
                    break
                else:
                    print(grid[i],' manteve a posição')
                    print(grid)
                    break
            else:    
                grid[i] = self.nome
                print(grid)
                break


nome1 = input('informe o nome do primeiro piloto: ')
piloto_1=Competidor(nome1)

nome2 = input('informe o nome do segundo piloto:')
piloto_2 = Competidor(nome2)

nome3 = input('informe o nome do terceiro piloto: ')
piloto_3 = Competidor(nome3)

nome4 = input('informe o nome do quarto competidor: ')
piloto_4 = Competidor(nome4)

nome5 = input('informe o nome do quinto piloto: ')
piloto_5 = Competidor(nome5)

grid = ['*']*20
tamanho=len(grid)
while grid[tamanho-1] == '*':
    print('RODADA DE ',piloto_1.nome)
    piloto_1.atualizar(grid)
    piloto_1.get_pos()
    print("posição atual: ",piloto_1.pos)
    print('')
    
    input("tecle ENTER para próxima rodada")
    print('RODADA DE ',piloto_2.nome)
    piloto_2.atualizar(grid)
    piloto_2.get_pos()
    print("posição atual: ",piloto_2.pos)
    print('')

    input("tecle ENTER para próxima rodada")
    print('RODADA DE ',piloto_3.nome)
    piloto_3.atualizar(grid)
    piloto_3.get_pos()
    print("posição atual: ",piloto_3.pos)
    print('')

    input("tecle ENTER para próxima rodada")
    print('RODADA DE ',piloto_4.nome)
    piloto_4.atualizar(grid)
    piloto_4.get_pos()
    print("posição atual: ",piloto_4.pos)
    print('')

    input("tecle ENTER para próxima rodada")
    print('RODADA DE ',piloto_5.nome)
    piloto_5.atualizar(grid)
    piloto_5.get_pos()
    print("posição atual: ",piloto_5.pos)
    print(" ")
    
    input("tecle ENTER para próxima volta")
else:
    print('POLE POSITION')
    grid.reverse()
    pole=[]
    for a in range(3):
        for i in range(len(grid)):
            if grid[i] != '*' and grid[i] not in(pole):    
                pole.append(grid[i])
    
    for p in range(len(pole)):
        print(pole[p],'-',p + 1,' lugar')
