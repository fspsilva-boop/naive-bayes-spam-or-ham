# Classificador Naive Bayes - SMS Spam Detecção

Este projeto implementa um **classificador Naive Bayes** do zero em Python para identificar se uma mensagem SMS é **spam** ou **ham (não spam)**.  

## Conceito

O algoritmo **Naive Bayes** é baseado no **Teorema de Bayes**, que calcula a probabilidade de uma mensagem pertencer a uma classe (spam ou ham) com base nas palavras que ela contém.  
A suposição "ingênua" (naive) é que as palavras são **independentes entre si**, o que simplifica os cálculos:

$$
P(\text{Spam}|\text{Mensagem}) = \frac{P(\text{Mensagem}|\text{Spam}) \cdot P(\text{Spam})}{P(\text{Mensagem})}
$$

Em outras palavras, o modelo estima a probabilidade de uma mensagem ser spam considerando a frequência das palavras em mensagens de spam e não spam.

## Estrutura do Projeto

1. **Pré-processamento dos dados**
   - Remoção de caracteres especiais.
   - Separação do conjunto em mensagens de **treinamento**.
   - Construção de um **vocabulário** com todas as palavras únicas.

2. **Cálculo das Probabilidades**
   - Estima-se:
     - $$P(\text{Spam})$$ e $$P(\text{Ham})$$
     - $$P(\text{palavra}|\text{Spam})$$ e $$P(\text{palavra}|\text{Ham})$$
   - Utiliza-se **suavização de Laplace** (α = 1) para evitar probabilidades zero.

3. **Classificação de novas mensagens**
   - A função `classify(message)` calcula:
     - $$P(\text{Spam}|\text{mensagem})$$
     - $$P(\text{Ham}|\text{mensagem})$$
   - Retorna o rótulo com maior probabilidade.

  

