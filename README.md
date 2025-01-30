# Reconhecimento de entidades nomeadas

## Case
Uma grande empresa de advocacia está em busca de soluções tecnológicas para otimizar o processamento de documentos jurídicos e aprimorar a gestão dos processos em andamento.

Atualmente, o escritório lida com um volume significativo de contratos, petições, jurisprudências e outros documentos legais, sem uma forma eficiente de extrair automaticamente informações críticas desses textos, como nomes das partes envolvidas, datas relevantes e dispositivos legais citados.

Com isso, faz-se nescessário o desenvolvimento de um modelo de IA especializado em Reconhecimento de Entidades Nomeadas (NER), capaz de identificar e classificar automaticamente essas informações em textos jurídicos. Com essa solução, advogados e equipes jurídicas terão acesso mais rápido a dados essenciais, otimizando o tempo de análise, reduzindo o risco de erro humano e facilitando a gestão dos processos de forma mais eficiente.

## Etapas

### 1. Leitura dos dados e teste de modelos da biblioteca spacy

Primeiramente, no arquivo  teste_spacy.ipynb, foi feita a descompactação e leitura dos textos no arquivo textos.zip. Em seguida foi feito um teste com modelos prontos da biblioteca spacy para o reconhecimento de entidades. 
Com isso, foi possível perceber que os modelos prontos não seriam suficientes para o reconhecimento das entidades dos textos jurídicos. Dessa forma, foi feita a tokenização dos textos através do arquivo Gerador_de_textos_tokenizados.ipynb e em seguida feita a exportação do resultado em um arquivo CSV, chamado palavras.csv.


### 2. Rotulando os dados no formato IOB

Com essas informações, será necessário treinar um modelo para reconhecer as entidades em cada palavra. Para isso, as palavras devem ser rotuladas corretamente. O processo de rotulação foi realizado em uma planilha do Google Sheets e seguiu o formato BIO/IOB. 

O formato BIO/IOB, abreviação de inside, outside, beginning, é um formato de marcação comum para marcar tokens em uma tarefa de agrupamento em linguística computacional (por exemplo, reconhecimento de entidade nomeada). O processo de rotulação utiliza o seguinte esquema:

- O prefixo B antes de uma tag indica que a tag é o início de um pedaço
- O prefixo I antes de uma tag indica que a tag está dentro de um pedaço.
- O prefixo O indica que um token não pertence a nenhuma entidade/pedaço.

Assim, para rotular uma expressão, utiliza-se o prefixo B ou I, seguido de um hífen e do nome do rótulo. 

Exemplo:


| **palavra** |     **label** |
|------------:|--------------:|
|     ACORDAO |             O |
|    CONSELHO | B-ORGANIZACAO |
|    ESPECIAL | I-ORGANIZACAO |
|          DF |       B-LOCAL |

Esse processo foi repetido para cada palavra do documento.

Após a rotulação, o arquivo pôde ser baixado no formato .tsv acessando "Arquivo" > "Baixar" > "Valores Separados por Tabulações", gerando o arquivo palavras_IOB.tsv.


