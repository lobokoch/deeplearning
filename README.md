# Trabalho Final: Deep Learning

**FUNDAÇÃO UNIVERSIDADE REGIONAL DE BLUMENAU**  
**CENTRO DE CIÊNCIAS EXATAS E NATURAIS**  
**DEPARTAMENTO DE SISTEMAS E COMPUTAÇÃO**  
**Professor: Luan Porfirio e Silva**  
**Disciplina: Deep Learning (Pós-graduação em Data Science)**  
**Aluno: Márcio Koch**  

## Objetivo do trabalho

Classificação de textos para análise de sentimentos
Base de dados

Istruções:

- O objetivo deste trabalho é criar um modelo binário de aprendizado de máquina para classificação de textos. Para isso, será utilizado a base de dados [IMDb](http://ai.stanford.edu/~amaas/data/sentiment/), que consiste de dados textuais de críticas positivas e negativas de filmes
- Uma vez treinado, o modelo deve ter uma função predict que recebe uma string como parâmetro e retorna o valor 1 ou 0, aonde 1 significa uma crítica positiva e 0 uma crítica negativa
- O pré-processamento pode ser desenvolvidado conforme desejar (ex.: remoção de stopwords, word embedding, one-hot encoding, char encoding)
- É preferível que seja empregado um modelo de recorrência (ex.: rnn, lstm, gru) para a etapa de classificação
- Documente o código (explique sucintamente o que cada função faz, insira comentários em trechos de código relevantes)
- **Atenção**: Uma vez treinado o modelo final, salve-o no diretório do seu projeto e crie uma célula ao final do notebook contendo uma função de leitura deste arquivo, juntamente com a execução da função predict

Sugestões:  
- Explorar a base de dados nas células iniciais do notebook para ter um melhor entendimento do problema, distribuição dos dados, etc
- Após desenvolver a estrutura de classificação, é indicado fazer uma busca de hiperparâmetros e comparar os resultados obtidos em diferentes situações

- [Arquivo de código fonte da implementação](deep_leraning_sentiment_analysis_using_lstm_pytorch.ipynb)
- [Arquivo de modelo treinado](state_dict.pt)

**NOTA**: O tipo de rede utilizada foi **LSTM**. 