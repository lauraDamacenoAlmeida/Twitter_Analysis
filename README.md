# Text visualization with tweets

Esse repositório foi criado para coletar tweets referente a um assunto específico, e com isso criar visualizações para facilitar a análise do que as pessoas estão falando sobre.
Esses códigos foram utilizados no meu artigo onde eu explico com mais detalhes a lógica utilizada e o que seria cada função criada, para acessar clique [aqui](https://lauradamacenoalmeida.github.io/2020/02/13/worcloud-anne-with-an-e.html).

## Requisitos
1. [TwitterSearch](https://twittersearch.readthedocs.io/en/latest/): para fazer a coleta de dados no Twitter

2. [Pandas](https://pandas.pydata.org/docs/): para leitura e manipulação de dados

3. [Nltk](https://www.nltk.org/): para processar e manipular dados textuais

4. [https://matplotlib.org/](https://matplotlib.org/): para criar o gráfico de barras

6. [Seaborn](https://seaborn.pydata.org/): para criar o gráfico de barras

7. [Wordcloud](https://github.com/amueller/word_cloud): para visualizar a nuvem de palavras com os dados do twitter

8. [Re](https://docs.python.org/3/library/re.html): para utilizarmos regex no código

9. [Unidecode](https://pypi.org/project/Unidecode/): 

10. [Json](https://docs.python.org/3/library/json.html): Para ler os dados do arquivo json


## Estrutura do projeto
Atualmente o projeto está dividido assim:

- Analysis_tweets.ipynb: contém o código construído.
- tweets.json: dados coletados do twitter gerados pelo arquivo acima.


## Entendendo a coleta e o processamento dos dados
Para você extrair os dados do Twitter, precisa colocar nos parâmetros: chave, chave secrete, token, token secreto, o assunto que você precisa e a lingua(se é em português: pt, se é em inglês: en, etc..) no seguinte método:

```
generate_tweet('xx','xx','xxx','xxx', 'assunto','pt')

```

Após isso os dados extraídos do twitter serão armazenados em um arquivo chamado 'tweets.json'

```
conteudo = open('tweets.json').read()

```

E depois esse arquivo é lido através da biblioteca json, e é necessário normalizá-lo por conta da estrutura que os dados estão vindo.

```
_json = json.loads(conteudo)
df = json_normalize(_json)

```
Após isso essas informações são transformadas em DataFrame para facilitar a manipulação dos dados.

```
df= pd.read_json(conteudo)

```

