# Desafio de Cientista de Dados: Previsão de Preço de Veículos

## Objetivo

O projeto tem como objetivo desenvolver um modelo de Machine Learning capaz de prever o preço de veículos com base em diversas características fornecidas. Além disso, também buscamos responder às seguintes perguntas de negócios:

1.Qual o melhor estado cadastrado na base de dados para se vender um carro de marca popular e por quê?
2.Qual o melhor estado para se comprar uma picape com transmissão automática e por quê?
3.Qual o melhor estado para se comprar carros que ainda estejam dentro da garantia de fábrica e por quê?


## Estrutura do Repositório

- `data/`: Diretório contendo os datasets utilizados.
- `notebooks/`: Jupyter notebooks com análises exploratórias e modelagem.
- `src/`: Scripts de apoio e funções auxiliares.
- `models/`: Modelos treinados salvos para reuso.
- `README.md`: Descrição e instruções sobre o projeto.

## Datasets

Os datasets cars_train, cars_test, deste projeto, contêm informações detalhadas sobre diversos veículos, incluindo características técnicas, marca, modelo, idade, entre outras.



## Análise Exploratória

Uma análise exploratória dos dados foi realizada para entender as distribuições, tendências e relações entre as variáveis. Especial atenção foi dada às perguntas de negócios mencionadas acima.

## Modelagem

Foi empregado um processo iterativo de modelagem, onde diferentes algoritmos e técnicas de pré-processamento foram testados. O desempenho do modelo foi avaliado usando métricas padrão, como RMSE (Root Mean Squared Error), e o modelo final foi selecionado com base em sua performance no conjunto de validação.

## Instruções para Rodar o Projeto

1. Clone o repositório:
   ```sh
   git clone [link-do-repositório]
