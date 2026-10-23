# ai-comparison-svm-nn

Este repositório contém uma implementação prática e puramente matemática de dois dos algoritmos mais icônicos da Inteligência Artificial: Support Vector Machines (SVM) e Redes Neurais Artificiais (NN). 

O objetivo principal deste projeto é aplicar ambos os modelos no banco de dados MNIST (classificação de dígitos manuscritos de 0 a 9) para analisar e comparar o desempenho de cada abordagem, desenvolvendo tudo do zero utilizando apenas NumPy e Pandas.

---

## Diferencial do Projeto

Diferente de projetos que utilizam bibliotecas prontas como scikit-learn, TensorFlow ou PyTorch, este código foi construído focando na transformação de equações matemáticas diretamente em lógica de programação linear e matricial:
- Sem frameworks de ML: Toda a otimização e álgebra linear são resolvidas nativamente com operações de matrizes do NumPy.
- Foco conceitual: Código limpo e comentado para demonstrar o funcionamento interno de algoritmos de otimização e funções de custo.

---

## Modelos Implementados

### 1. Support Vector Machine (SVM) Linear
- Abordagem Multiclasse: Estratégia One-vs-One (OvO), treinando um comitê de 45 classificadores binários independentes para cobrir as 10 classes do MNIST.
- Otimização: Gradiente Descendente Estocástico (SGD) com suporte a atualizações refinadas.
- Função de Custo: Hinge Loss com Regularização L2 para maximização da margem geométrica.

### 2. Rede Neural (Single-Layer Perceptron)
- Arquitetura: Uma rede Perceptron de Camada Única, conectando diretamente as 784 features de entrada (pixels) aos 10 neurônios de saída (um para cada dígito).
- Algoritmo Central: Ajuste de pesos via Gradiente Descendente aplicado à camada de saída.
- Ativação e Custo: Saída processada via função Softmax para gerar probabilidades e otimizada através da perda de Entropia Cruzada (Cross-Entropy Loss).

---

## Técnicas de Otimização (Melhoria do Treino)

Para acelerar a convergência e garantir melhores taxas de acurácia no MNIST, ambos os modelos foram aprimorados com:
- Mini-batch Gradient Descent: O treino não é feito amostra por amostra e nem com o dataset inteiro de uma vez. Os dados são processados em pequenos lotes (mini-batches), equilibrando estabilidade matemática e velocidade computacional.
- Learning Rate Decay: Redução gradual e programada da taxa de aprendizado ao longo das épocas. Isso permite que os modelos deem passos largos no início do treino e passos refinados no final, evitando que os pesos oscilem indefinidamente longe do ponto ideal de convergência.

---

## Pipeline de Execução

1. Carga e Manipulação de Dados: Leitura e estruturação das matrizes de pixels com Pandas.
2. Pré-processamento: Normalização Z-score para garantir estabilidade e convergência rápida dos gradientes.
3. Treinamento Otimizado: Execução do loop de épocas utilizando mini-batches e decaimento de taxa de aprendizado.
4. Avaliação: Geração de métricas de acurácia e matriz de confusão para identificar onde ocorrem os maiores erros de predição (ex: confundir o dígito 4 com o 9).

---

## Tecnologias Utilizadas

- Python (Linguagem base)
- NumPy (Cálculo numérico, matrizes e álgebra linear)
- Pandas (Estruturação e carregamento do dataset)

---
