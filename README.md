# Detecção de Mudanças em Cidades

Este repositório contém código de um trabalho da disciplina de Processamento
Digital de Imagens do DCC/UFMG (2019/01) ministrada pelo professor Jefersson
Alex dos Santos.

O [enunciado][enunciado] pede a criação de um programa para detectar mudanças
das imagens de satélite ao longo do tempo. O dataset pode ser obtido em seu
[site oficial][onera].

As imagens foram obtidas pelo satélite Sentinel-2 entre 2015 e 2018
e são compostas por amostras em 13 bandas. São imagens de 24 localidades,
das quais para 14 existe o valor _ground truth_ conhecido.

Este trabalho foi feito por:

- [Douglas Ludgério](https://github.com/douglaslud) ()
- [Flávio Coutinho](https://github.com/fegemo) (2019679021)
- [Ricardo de Oliveira](https://github.com/Tsuchiryu) (2012055294)

## Lista de Tarefas

1. ( ) Entender toda a especificação
1. ( ) Entender o formato de captura (as 13 bandas) do satélite Sentinel-2
   - Fontes: [engsat.com.br](http://www.engesat.com.br/sentinel-2/)
   - Fontes: [Sentinel-2 na Wikipedia](https://en.wikipedia.org/wiki/Sentinel-2)
1. ( ) Escolher uma cidade como exemplo que tenha _ground truth_: Águas Claras?
1. ( ) Segmentar cada banda em t1 usando SLIC
   - Isso vai gerar 13 imagens
   - **Dúvida:** devemos segmentar apenas em t1 e usar as mesmas regiões para t2?
1. ( ) Extrair características de textura de cada superpixel em cada banda
1. ( ) Classificar cada superpixel/banda em mudança ou não (distância euclidiana)
   - **Dúvida:** a classificação pode/deve ser feita por um limiar experimental ou deve haver algo mais rebuscado (eg, rede convolucional)?
1. ( ) Gerar mapa binário de mudanças em cada banda
   - **Dúvida:** o mapa binário é simplesmente todos os superpixels classificados como mudança?
1. ( ) Combinar os mapas binários por banda
1. ( ) Comparar a combinação das bandas com o _ground truth_ (via acurácia)
   - **Dúvida:** há 10 imagens sem _ground truth_... não será possível fazer esta etapa, certo?
1. ( ) Executar passos 2-8 com +1 cidade até acabar todas
1. ( ) Relatar as escolhas de parâmetros/métodos para cada cidade
1. ( ) Implementar um script para avaliação do detector
   - **Dúvida:** para avaliar usaremos as acurácias das cidades que temos _ground truth_? Aí podemos ter o valor das acurácias, média, desvio padrão, coeficiente de correlação etc.?
   - **Dúvida:** como avaliar as imagens sem _ground truth_?
1. ( ) Documentar o trabalho (execução do "classificador final")
1. ( ) Produzir e formatar relatório final (3 páginas no máximo)
