# Importando biblioteca
from sklearn.linear_model import Perceptron

# Dados de entrada (Ensolarado, Final de Semana, Parque Lotado)
X = [
    [0, 0, 0], [0, 1, 0], [1, 0, 0], [1, 1, 0], 
    [0, 0, 1], [0, 1, 1], [1, 0, 1], [1, 1, 1]
]

# Saídas desejadas (Ir ao Parque?)
Y = [0, 1, 1, 1, 0, 0, 0, 0]

# Criando e treinando o perceptron
modelo = Perceptron()
modelo.fit(X, Y)

# Testando o modelo
print("Previsões para Ir ao Parque:")
testes = X
for teste in testes:
    previsao = modelo.predict([teste])
    print(f"Ensolarado: {teste[0]}, Final de Semana: {teste[1]}, Parque Lotado: {teste[2]} => Ir ao Parque? {'Sim' if previsao[0] == 1 else 'Não'}")

