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

### Arquitetura 1
- Épocas: **100**
- Otimizador de gradiente: **SGD** - `SGD(model.parameters(), lr=0.01, momentum=0.9)`  
- Dropout: **20%**

Configurações iniciais da rede: 
| Camada | Nós entrada | Nós saída | Dropout | Função de ativação |  
|--|--|--|--|--|
| 1 | **30** | 50| Sim | ReLu |
| 2 | 50 | 40| Sim | ReLu |
| 3 | 40 | 30| Sim | ReLu |
| 4 | 30 | 20| Sim | ReLu |
| 5 | 20 | **12**| Não | Softmax |

#### Resultados da arquitetura
- Acurácia: **14,4 %**
- [Arquivo de código fonte da implementação](https://github.com/lobokoch/ann/tree/main/arquitetura1)
- [Arquivo de resultado hidden.csv](https://github.com/lobokoch/ann/tree/main/arquitetura1)
-----------------------

### Arquitetura 2
- Épocas: **100**
- Otimizador de gradiente:  **Adam** - `Adam(model.parameters(), lr=0.003)`  
- Dropout: **20%**

Configurações iniciais da rede:   
| Camada | Nós entrada | Nós saída |  Dropout | Função de ativação |  
|--|--|--|--|--|
| 1 | **30** | 200| Sim | ReLu |
| 2 | 200 | 100| Sim | ReLu |
| 3 | 100 | 80| Sim | ReLu |
| 4 | 80 | **12**| Não | Softmax |

#### Resultados da arquitetura
- Acurácia: **61,6 %**
- [Arquivo de código fonte da implementação](https://github.com/lobokoch/ann/tree/main/arquitetura2)
- [Arquivo de resultado hidden.csv](https://github.com/lobokoch/ann/tree/main/arquitetura2)
-----------------------

## Conclusão

Com base nos resultados obtidos de acurácia baixa, mesmo testando com diferentes arquiteturas de redes neurais (apesar de estar apresentado apenas 4 arquiteturas nos resultados do trabalho, foram empregadas mais de 20 diferentes arquiteturas). Assim, supõem-se que a base do dataset possui anomalias e ruídos nos dados. A fim de aumentar a acurácia seria necessário empregar uma ampla exploração e transformação nos dados do dataset, bem como efetuar novos experimentos com diferentes arquiteturas de redes neurais.

Mas mesmo com resultados de acurácia baixos, foi perfeitamente possível compreender e explorar o funcionamento das redes neurais artificiais, tanto classificação binária quanto multi classes. O Python oferece uma ampla gama de bibliotecas, como o pytorch, sklearn, numpy e pandas para manipular os dados desde o carregamento do dataset no formato csv, aplicação das técnicas de redes neurais, cálculo e extração dos resultados e persistência dos resultados também em arquivo csv.




