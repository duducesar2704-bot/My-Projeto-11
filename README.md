# My-Projeto-11
from datetime import datetime
from dateutil.relativedelta import relativedelta


def calcular_montante(capital, taxa_juros, meses):
    taxa_decimal = taxa_juros / 100
    montante = capital * (1 + taxa_decimal) ** meses
    return montante

try:
    tipo = input("Digite o tipo de investimento: ")
    capital = float(input("Digite o capital inicial (R$): "))
    taxa = float(input("Digite a taxa de juros mensal (%): "))
    meses = int(input("Digite o número de meses: "))

  
    data_aplicacao = datetime.now()

    
    data_vencimento = data_aplicacao + relativedelta(months=meses)


    montante = calcular_montante(capital, taxa, meses)

  
    print("\n--- RESULTADO ---")
    print(f"Tipo de investimento: {tipo}")
    print(f"Capital inicial: R$ {capital:.2f}")
    print(f"Taxa de juros: {taxa:.2f}% ao mês")
    print(f"Prazo: {meses} meses")
    print(f"Montante final: R$ {montante:.2f}")
    print(f"Data da aplicação: {data_aplicacao.strftime('%d/%m/%Y')}")
    print(f"Data de vencimento: {data_vencimento.strftime('%d/%m/%Y')}")

except ValueError:
    print("Erro: Por favor, insira valores numéricos válidos para capital, taxa e meses.")
except Exception as e:
    print(f"Ocorreu um erro inesperado: {e}")
