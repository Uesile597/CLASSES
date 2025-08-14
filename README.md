# CLASSES
A resolução de dois problemas para criar um Livro e uma Conta Bancária.
# ==============================
# EXERCÍCIO 1 — Classe Livro
# ==============================

class Livro:
    def __init__(self, titulo, autor, num_pag, pag_atl):
        """
        Construtor da classe Livro.
        Parâmetros:
            titulo   -> Nome do livro
            autor    -> Autor do livro
            num_pag  -> Número total de páginas
            pag_atl  -> Página atual (não está sendo usado aqui, valor inicial é sempre 0)
        """
        self.Titulo = titulo     # Armazena o título do livro
        self.Autor = autor       # Armazena o autor do livro
        self.Num_pag = num_pag   # Armazena o número total de páginas
        self.Pag_atl = 0         # Página atual começa em 0 (livro fechado)

    def abrir_livro(self):
        """
        Abre o livro na página 1.
        """
        self.Pag_atl = 1
        print(f"O livro {self.Titulo} foi aberto na página {self.Pag_atl}.")

    def ler_pag(self):
        """
        Avança para a próxima página.
        Antes verifica se o livro está aberto (página atual > 0).
        """
        if self.Pag_atl == 0:  # Se ainda não foi aberto
            print("Abra o livro antes de começar a ler!!")
            return

        self.Pag_atl += 1  # Passa para a próxima página
        print(f"A página atual é {self.Pag_atl}.")

    def exb_prg(self):
        """
        Exibe quantas páginas faltam para terminar o livro.
        Antes verifica se o livro está aberto.
        """
        if self.Pag_atl == 0:
            print("Abra o livro antes de começar a ler!!")
            return

        paginas = self.Num_pag - self.Pag_atl
        print(f"Faltam {paginas} páginas a serem lidas!!")


# ==============================
# EXERCÍCIO 2 — Classe ContaBancaria
# ==============================

class ContaBancaria:
    def __init__(self, titular, saldo, num_conta):
        """
        Construtor da classe ContaBancaria.
        Parâmetros:
            titular   -> Nome do dono da conta
            saldo     -> Valor inicial
            num_conta -> Número da conta
        """
        self.Titular = titular
        self.Saldo = saldo
        self.Num_conta = num_conta

    def despositar(self):
        """
        Lê um valor via input e adiciona ao saldo.
        OBS: Nome do método está escrito errado, o correto seria 'depositar'.
        """
        valor = float(input("Digite o valor desejado a depositar: "))
        self.Saldo += valor
        print(f"O valor de {valor} reais foi depositado na sua conta!!")

    def sacar(self):
        """
        Lê um valor via input e retira do saldo se houver dinheiro suficiente.
        """
        valor = float(input("Digite o valor desejado a sacar: "))
        if valor > self.Saldo:
            print("Você não possui saldo suficiente na conta.")
            return

        self.Saldo -= valor
        print(f"O valor de {valor} reais foi retirado da sua conta!!")

    def consultar(self):
        """
        Exibe o saldo atual da conta.
        """
        print(f"O saldo na conta é {self.Saldo} reais.")

    def exb_extrt(self):
        """
        Exibe um extrato simples com titular, saldo e número da conta.
        """
        print(f"Titular: {self.Titular}")
        print(f"Saldo: {self.Saldo}")
        print(f"Conta: {self.Num_conta}")


# ==============================
# OBSERVAÇÕES GERAIS:
# ==============================
# - No Livro, o parâmetro 'pag_atl' não é usado no construtor.
# - Seria bom impedir que 'ler_pag' ultrapasse o total de páginas.
# - Em ContaBancaria, usar parâmetros em vez de 'input()' tornaria os métodos mais reutilizáveis.
# - Validar para evitar depósitos/saques negativos.
# - Corrigir nomes para seguir convenções do Python (snake_case).
