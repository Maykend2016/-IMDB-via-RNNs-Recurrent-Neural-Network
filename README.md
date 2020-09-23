# IMDB-via-RNNs-Recurrent-Neural-Network
Classificação de sentimento em reviews de filmes com base do IMDB via RNNs (Recurrent Neural Networks)

Neste notebook iremos treinar uma Rede Neural Recorrent (RNN) para classificação de sentimento usando Keras (com Tensorflow como backend).

Base de dados do IMDB (https://www.kaggle.com/iarunava/imdb-movie-reviews-dataset)
Em seguida, carregaremos o conjunto de dados do IMDB. Na primeira vez, talvez tenhamos que baixar os dados, o que pode demorar um pouco. O conjunto de dados contém 50000 avaliações de filmes do Internet Movie Database, dividido em 25.000 avaliações para treinamento e 25.000 avaliações para testes. Metade dos comentários são positivos (1) e metade são negativos (0).

O conjunto de dados já foi pré-processado e cada palavra foi substituída por um índice inteiro.

As revisões são, portanto, representadas como sequências de comprimento variável de inteiros, como consta:

(Os índices de palavras começam em "3", como "1" é usado para marcar o início de uma revisão e "2" representa todas as palavras fora do vocabulário existente. "0" será usado posteriormente para preencher comentários mais curtos em um tamanho fixo .)

Mais informações e créditos originais:
Maas, Andrew L. and Daly, Raymond E. and Pham, Peter T. and Huang, Dan and Ng, Andrew Y. and Potts, Christopher, "Learning Word Vectors for Sentiment Analysis", em Proceedings of the 49th Annual Meeting of the Association for Computational Linguistics: Human Language Technologies, June, 2011. Portland, Oregon, USA. Association for Computational Linguistics. Pages 142 a150. Disponível em: http://www.aclweb.org/anthology/P11-1015

O que foi realizado até o momento?

No pré-processamento a variável nb_words estava com definição = 10000 a cerca do número de palavras, das quais são mais frequentes para se utilizar. Resolvi fazer um teste alterando para 20000 com intuito de cortar os textos a partir do maxlenght = 100 mediante ao seu comprimento máximo de palavras.

Note que na camada de LSTM, foi inserida toda a classe, visto que usei várias ativações, das quais à accuracy encontrava-se entre 78 a 83%, sem nenhum resultado satisfatório.

Para ultrapassar os 83% em nossa análise, foi necessário usar apenas 5 epochs com uma pequena alteração no validation_split com peso definido = 0.1. Assim, chegamos a 84.72% de melhoria.
