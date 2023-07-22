# Desafio de Cientista de Dados: Previsão de Preço de Veículos

## Objetivo

O projeto tem como objetivo desenvolver um modelo de Machine Learning capaz de prever o preço de veículos com base em diversas características fornecidas de dois datasets: 
Um dataset para treinamento chamado cars_training composto por 29584 linhas, 28 colunas de informação (features) e a variável a ser prevista (“preco”). 
Um segundo dataset para teste chamado de cars_test composto por  9862 linhas e 28 colunas, sendo que este dataset não possui a coluna “preco”. 

 . Além disso, também buscamos responder às seguintes perguntas de negócios:

1.Qual o melhor estado cadastrado na base de dados para se vender um carro de marca popular e por quê?
2.Qual o melhor estado para se comprar uma picape com transmissão automática e por quê?
3.Qual o melhor estado para se comprar carros que ainda estejam dentro da garantia de fábrica e por quê?

## Datasets

Os datasets cars_train, cars_test, deste projeto, contêm informações detalhadas sobre diversos veículos, incluindo características técnicas, marca, modelo, idade, entre outras.

## Análise Exploratória

### Dataset de treino:

1. **Quantidade de Dados (`count`)**:
   - A maior parte das colunas tem 29.584 entradas. Contudo, a coluna `num_fotos` possui apenas 29.407 entradas, indicando que alguns veículos podem não ter informações sobre o número de fotos.

2. **Num_fotos**:
   - Média de 10,32 fotos por veículo.
   - Varia entre um mínimo de 8 fotos e um máximo de 21.
   - 50% dos veículos (mediana) têm 8 fotos, mas há veículos (75% quartil) com até 14 fotos.

3. **Ano_de_fabricacao**:
   - Média de fabricação dos veículos é 2016.
   - O veículo mais antigo é de 1985 e o mais recente de 2022.
   - 50% dos veículos foram fabricados até 2018.

4. **Hodômetro**:
   - Em média, os veículos rodaram 58.430 km.
   - Há veículos com apenas 100 km e outros com até 390.065 km.

5. **Num_portas**:
   - Em média, os veículos possuem cerca de 4 portas.
   - Varia entre 2 e 4 portas.
   - 75% dos veículos têm 4 portas.

6. **Dono_aceita_troca**:
   - 74% dos proprietários aceitam trocas.

7. **Veiculo_único_dono**:
   - 35% dos veículos tiveram apenas um dono.

8. **Revisoes_concessionaria**:
   - 31% dos veículos tiveram suas revisões feitas em concessionárias.

9. **Ipva_pago**:
   - 66% dos veículos estão com o IPVA pago.

10. **Veiculo_licenciado**:
    - 54% dos veículos estão licenciados.

11. **Garantia_de_fábrica**:
    - Apenas 15% dos veículos ainda possuem garantia de fábrica.

12. **Revisoes_dentro_agenda**:
    - 20% dos veículos tiveram suas revisões feitas dentro da agenda recomendada.

13. **Veiculo_alienado**:
    - Parece que nenhum veículo da lista está alienado (valor máximo e média são 0).

14. **Preço**:
    - O preço médio dos veículos é aproximadamente 133.024 unidades monetárias (presumindo que seja em reais ou outra moeda).
    - Há veículos tão baratos quanto cerca de 9.870 e outros tão caros quanto 1.359.813.

**Conclusão**:
Os dados parecem descrever uma variedade de veículos, desde os mais antigos até os mais recentes, com diferentes históricos de uso e condições. A maioria dos veículos é mais recente (pós-2015), tem 4 portas, e rodou uma quantidade moderada de km. Além disso, a maior parte dos proprietários aceita trocas, mas apenas uma pequena porcentagem dos veículos ainda possui garantia de fábrica.

### Dataset de teste:

1. **num_fotos**:
   - Varia de 8 a 21 fotos.
   - A maioria dos veículos tem 8 fotos (50% dos veículos, mediana).
   - Em média, os veículos têm aproximadamente 10,32 fotos.
   - Há uma variação (desvio padrão) de cerca de 3,46 no número de fotos por veículo.

2. **ano_de_fabricacao**:
   - Os veículos foram fabricados entre 1988 e 2022.
   - A mediana do ano de fabricação é 2018, ou seja, 50% dos veículos foram fabricados em 2018 ou depois.
   - Em média, os veículos foram fabricados em 2016,7 (aproximadamente).

3. **ano_modelo**:
   - Os modelos dos veículos variam de 2007 a 2023.
   - Em média, o ano do modelo é aproximadamente 2017,8.
   - Metade dos veículos têm 2018 como ano do modelo.

4. **hodometro**:
   - A quilometragem varia de apenas 100 km a 381.728 km.
   - A mediana da quilometragem é de 56.742 km.
   - Em média, os veículos rodaram aproximadamente 58.237 km.

5. **num_portas**:
   - Os veículos têm entre 2 e 4 portas.
   - A grande maioria (75% ou mais) tem 4 portas.

6. **dono_aceita_troca**:
   - 74,1% dos proprietários aceitam troca (valor médio de 0,741).
   
7. **veiculo_único_dono**:
   - 35,2% dos veículos tiveram apenas um único dono.
   
8. **revisoes_concessionaria**:
   - Apenas 31% dos veículos tiveram suas revisões feitas na concessionária.

9. **ipva_pago**:
   - 66,6% dos veículos estão com o IPVA pago.

10. **veiculo_licenciado**:
    - 54,2% dos veículos estão licenciados.

11. **garantia_de_fábrica**:
    - Apenas 14,4% dos veículos ainda possuem garantia de fábrica.

12. **revisoes_dentro_agenda**:
    - 20,2% dos veículos tiveram suas revisões realizadas dentro da agenda recomendada.

13. **veiculo_alienado**:
    - Nenhum veículo é alienado (todos têm valor 0 para essa característica).

**Conclusões**:
A maioria dos veículos nesta tabela têm 4 portas, com uma mediana de 56.742 km rodados. A maioria foi fabricada recentemente, com uma mediana no ano de 2018. Enquanto muitos proprietários aceitam trocas (74,1%), apenas uma pequena porcentagem dos veículos ainda possui garantia de fábrica ou fez revisões na concessionária. A maioria dos veículos está com o IPVA pago e está licenciada. Além disso, é interessante notar que nenhum veículo é alienado.

## Modelagem

Foi empregado um processo iterativo de modelagem, onde diferentes algoritmos e técnicas de pré-processamento foram testados. O desempenho do modelo foi avaliado usando métricas padrão, como RMSE (Root Mean Squared Error), e o modelo final foi selecionado com base em sua performance no conjunto de validação.

## Requisitos

Você precisará de Python 3 e pip. É altamente recomendado utilizar ambientes virtuais
com o virtualenv e o arquivo `requirements.txt` para instalar os pacotes dependências
do desafio:

bash
$ pip3 install virtualenv
$ virtualenv venv -p python3
$ source venv/bin/activate
$ pip install -r requirements.txt


Windows

bash
> pip3 install virtualenv
> virtualenv ..\venv -p python3
> ..\venv\Scripts\activate
> pip install -r requirements.txt


MacOS

bash
> python3 -m pip install virtualenv
> python3 -m virtualenv venv # create a new venv in ./venv
> source ./venv/bin/activate # activate your new venv
> pip install -r requirements.txt


1. Clone o repositório:
   ```sh
   git clone [link-do-repositório]
