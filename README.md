# ==============================
# EXERCÍCIO 1 — Classe Livro
# ==============================
class Livro:
    def __init__(self, titulo, autor, num_pag, pag_atl):
        self.Titulo = titulo
        self.Autor = autor
        self.Num_pag = num_pag
        self.Pag_atl = 0

    def abrir_livro(self):
        self.Pag_atl = 1
        print(f"O livro {self.Titulo} foi aberto na página {self.Pag_atl}.")

    def ler_pag(self):
        if self.Pag_atl == 0:
            print("Abra o livro antes de começar a ler!!")
            return

        if self.Pag_atl > self.Num_pag:
            print("Você terminou o livro!")
            return
        
        elif self.Pag_atl == self.Num_pag:
            print("Está é a sua última página!")
            return
        
        else:
            self.Pag_atl += 1
            print(f"A página atual é {self.Pag_atl}.")

    def exb_prg(self):
        if self.Pag_atl == 0:
            print("Abra o livro antes de começar a ler!!")
            return

        paginas = self.Num_pag - self.Pag_atl
        print(f"Faltam {paginas} a serem lidas!!")


# ==============================
# EXERCÍCIO 2 — Classe ContaBancaria
# ==============================
class ContaBancaria:
    def __init__(self, titular, saldo, num_conta):
        self.Titular = titular
        self.Saldo = saldo
        self.Num_conta = num_conta

    def depositar(self):  # corrigido
        valor = float(input("Digite o valor desejado a depositar: "))
        self.Saldo += valor
        print(f"O valor de {valor} reais foi depositado na sua conta!!")

    def sacar(self):
        valor = float(input("Digite o valor desejado a sacar: "))
        if valor > self.Saldo:
            print("Você não saldo suficiente na conta.")
            return

        self.Saldo -= valor
        print(f"O valor de {valor} reais foi retirado da sua conta!!")

    def consultar(self):
        print(f"O saldo na conta é {self.Saldo} reais.")

    def exb_extrt(self):
        print(f"Titular: {self.Titular}")
        print(f"Saldo: {self.Saldo}")
        print(f"Conta: {self.Num_conta}")
