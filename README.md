# Reconhecimento de entidades nomeadas

## Case
Uma grande empresa de advocacia está em busca de soluções tecnológicas para otimizar o processamento de documentos jurídicos e aprimorar a gestão dos processos em andamento.

Atualmente, o escritório lida com um volume significativo de contratos, petições, jurisprudências e outros documentos legais, sem uma forma eficiente de extrair automaticamente informações críticas desses textos, como nomes das partes envolvidas, datas relevantes e dispositivos legais citados.

Com isso, faz-se nescessário o desenvolvimento de um modelo de IA especializado em Reconhecimento de Entidades Nomeadas (NER), capaz de identificar e classificar automaticamente essas informações em textos jurídicos. Com essa solução, advogados e equipes jurídicas terão acesso mais rápido a dados essenciais, otimizando o tempo de análise, reduzindo o risco de erro humano e facilitando a gestão dos processos de forma mais eficiente.



## Rotulando os dados no formato IOB
O formato BIO/IOB ,abreviação de inside, outside, beginning, é um formato de marcação comum para marcar tokens em uma tarefa de agrupamento em linguística computacional (por exemplo, reconhecimento de entidade nomeada).

- O prefixo B antes de uma tag indica que a tag é o início de um pedaço
- O prefixo I antes de uma tag indica que a tag está dentro de um pedaço.
- O prefixo O indica que um token não pertence a nenhuma entidade/pedaço.

Exemplo:


| **palavra** |     **label** |
|------------:|--------------:|
|     ACORDAO |             O |
|    CONSELHO | B-ORGANIZACAO |
|    ESPECIAL | I-ORGANIZACAO |
|          DF |       B-LOCAL |
