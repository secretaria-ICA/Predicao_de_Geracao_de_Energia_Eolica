<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Predição de Geração de Energia Eólica

#### Aluno: [Tales Simões Mattos](https://github.com/Talesbr/ProjetoBI)
#### Orientadora: [Manoela Rabello Kohler](https://github.com/manoelakohler).


---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o código](https://github.com/Talesbr/ProjetoBI). <!-- caso não aplicável, remover esta linha -->




---

### Resumo

<!-- trocar o texto abaixo pelo resumo do trabalho, em português -->

A geração de energia eólica com uso de aerogeradores tem se tornado uma das principais formas de geração de energia elétrica renovável, apresentando crescimento expressivo ao longo dos últimos anos, onde em 2020 existia 17,8 GW de capacidade instalada no Brasil, sendo o equivalente a 10,1% da Matriz Elétrica Brasileira, e com um total de emissões evitadas em 2020 de 21,2 milhões de toneladas de CO2, sendo equivalente à emissão anual de cerca de 21 milhões de automóveis de passeio.

A Energia eólica vem a ser a energia produzida a partir da energia cinética do vento (massas de ar em movimento) e do aquecimento eletromagnético do Sol (energia solar), que, juntos, movimentam as pás de captadores, onde a energia cinética do vento normalmente é convertida em energia mecânica por moinhos e cataventos, ou em energia elétrica por turbinas eólicas (ou aerogeradores).

Este trabalho buscou utlilizar uma rede neural LSTM (Long Short Term Memory) para avaliar a predição de geração de energia elétrica proveniente de um aerogerador, utilizando os dados coletados referentes a um ano de produção deste aerogerador e utilizando a rede para prever a geração para os meses seguintes. 

A aplicação de um modelo de redes neurais em LSTM (Long Short Term Memory) apresentou resultados satisfatórios para a base de dados utilizada, obtida do www.kaggle.com, https://www.kaggle.com/theforcecoder/wind-power-forecasting?select=Turbine_Data.csv.

### Abstract <!-- Opcional! Caso não aplicável, remover esta seção -->

<!-- trocar o texto abaixo pelo resumo do trabalho, em inglês -->

The generation of wind energy using wind turbines has become one of the main forms of renewable electricity generation, showing significant growth over the past few years, where in 2020 there was 17.8 GW of installed capacity in Brazil, equivalent to 10.1% of the Brazilian Electricity Matrix, and with a total avoided emissions in 2020 of 21.2 million tons of CO2, equivalent to the annual emission of around 21 million passenger cars.

Wind energy is the energy produced from the kinetic energy of the wind (moving air masses) and the electromagnetic heating of the Sun (solar energy), which together move the pickup blades, where the kinetic energy of the wind it is usually converted into mechanical energy by windmills and weathervanes, or into electrical energy by wind turbines.

This work use a neural network LSTM (Long Short Term Model) to evaluate the prediction of electricity generation from a wind turbine, using data collected for one year of production of this wind turbine and using the network to predict the generation for the following months.

The application of a neural network model in LSTM (Long Short Term Model) presented satisfactory results for the database used, obtained from www.kaggle.com, https://www.kaggle .com/theforcecoder/wind-power-forecasting?select=Turbine_Data.csv.

### 1. Introdução


Energia eólica é a energia cinética derivada da força dos ventos, que pode ser utilizada para várias finalidades, incluindo a produção de eletricidade a partir de aerogeradores, onde os ventos movimentam as hélices das turbinas eólicas, gerando força mecânica, que depois é convertida em energia elétrica por meio de um gerador. 

Atualmente a energia eólica é a segunda fonte renovável mais utilizada no mundo, depois da energia hídrica, onde segundo os dados da Agência Internacional de Energia Renovável (IRENA), a capacidade total instalada de geradores eólicos atingiu 732,41 GW em 2020, impulsionado pela sua fonte de energia inesgotável, que é o vento, e pelo fato de não emitir poluentes, gases de efeito estufa e nem gerar resíduos, apresentando ainda as vantagens de não haver custos associados à obtenção de uma matéria-prima, diferente do que ocorre com combustíveis fósseis.

Uma das desvantagens da geração de energia eólica é a sua intermitência, onde por esta razão se torna de fundamental importância tentar prever o comportamento de sua geração, diretamente relacionada ao regime dos ventos. O objetivo deste trabalho foi avaliar a geração de energia eólica de um aerogerador, tomando por base os dados registrados de geração de energia de janeiro de 2018 a março de 2020 com intervalos de 10 minutos, buscando realizar a previsão da geração com base nestes registros, através do uso de uma Redes Neurais LSTM (Long Short Term Model)


### 2. Modelagem

Inicialmente foi realizado o pré-tratamento da base de dados, composta por mais de 118.000 registros de 22 atributos, contemplando o registro da geração de energia obtida pelo aerogerador, desde de janeiro de 2018 a março de 2020, onde após o tratamento foi identificado que os dados do ano de 2018 possuíam muitas ausências de informações, onde optou-se por utilizar os dados do ano de 2019 (52.600 registros), sendo os dados referentes ao ano de 2020 (4.700 registros) utilizados para testar os resultados. Foi testada uma rede neural LSTM e utilizado o indicador de acurácia R2.

A implementação da rede LSTM foi realizada utilizando a biblioteca Keras, sendo a rede configurada com 3 camadas conectadas, adicionadas camadas de eliminação (dropout) após cada camada LSTM oculta, buscando evitar o problema de overfitting. Foram testados os parâmetros da rede e suas configuraçãoes em diversas rodadas, chegando a uma configuração da rede que se entendeu ser a ideal, conforme a tabela abaixo, e para as configurações de aprendizagem, foi utilizado o otimizador ADAM.

![image](https://user-images.githubusercontent.com/83325612/142867864-dea2f7e4-3fd3-4013-8d7a-d96a65625a8e.png)


### 3. Resultados

Após a aplicação da rede neural os resultados do modelo testado foram satisfatórios para a previsão de geração de energia com alto valor de R2 de 0,94, tentou-se utilizar também o parâmetro MAPE mas este não se mostrou adequado para a base de dados utilizada.

### 4. Conclusões

Este trabalho propôs a aplicação de um rede neural LSTM para previsão da geração de energia eólica produzida por um aerogerador, onde após o pré-tratamento da base de dados com o registro histórico dos anos de 2018, 2019 e até o mês de março de 2020, optou-se por excluir os dados do ano de 2018, pois apresentavam muitos dados ausentes, que poderiam representar tanto a ausência de ventos quanto longos períodos de manutenção, sendo utilizado o ano de 2019 para o treinamento da rede e os dados do ano de 2020 utilizados para a base de treino e previsão da geração futura.

A aplicação da rede neural LSTM a base de dados de registros de geração de energia eólica de um aerogerador apresentou um resultado satisfatório quanto a previsão da geração, conforme apresentado no gráfico abaixo e no resultado do parâmetro R2.  

![image](https://user-images.githubusercontent.com/83325612/142870065-697c72dc-a034-4d25-a9c7-2728dd2217b4.png)

A título de trabalhos futuros entende-se que a aplicação em outras bases de dados de outros aerogeradores permitirá confirmar a efetividade da rede aplicada, principalmente pela variação do regime de ventos existente em cada região, podendo ainda implementar a associação de redes neurais LSTM com arquiteturas autoenconders e redes convolucionais.

---

Matrícula: 192.671.010

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
