# Recurrent-Networks-RNN

project coursera

Redes Neurais Recorrentes são modelos de Aprendizado Profundo com estruturas simples e um mecanismo de feedback embutido, ou em outras palavras, a saída de uma camada é adicionada à próxima entrada e realimentada na mesma camada.

A Rede Neural Recorrente é um tipo especializado de Rede Neural que resolve a questão de manter o contexto de dados sequenciais - como dados meteorológicos, estoques, genes, etc. Em cada etapa iterativa, a unidade de processamento obtém uma entrada e o estado atual da rede e produz uma saída e um novo estado que é realimentado na rede.

No entanto, este modelo tem alguns problemas. É muito caro do ponto de vista computacional manter o estado por uma grande quantidade de unidades, ainda mais por um longo período de tempo. Além disso, as redes recorrentes são muito sensíveis às mudanças em seus parâmetros. Como tal, eles estão sujeitos a diferentes problemas com seu otimizador de Gradiente Descendente - eles crescem exponencialmente (Gradiente Explosivo) ou caem para perto de zero e se estabilizam (Gradiente Desaparecido), ambos problemas que prejudicam muito a capacidade de aprendizado de um modelo.

## Long Short-Term Memory - LSTM

A Long Short-Term Memory, como era chamada, era uma abstração de como a memória do computador funciona. Ele é "empacotado" com qualquer unidade de processamento implementada na Rede Recorrente, embora fora de seu fluxo, e é responsável por manter, ler e enviar informações para o modelo. O funcionamento é simples: você tem uma unidade linear, que é a própria célula de informação, cercada por três portas logísticas responsáveis pela manutenção dos dados. Uma porta é para inserir dados na célula de informação, uma é para enviar dados da célula de entrada e a última é para manter ou esquecer os dados, dependendo das necessidades da rede.

Graças a isso, não só resolve o problema de manter estados, pois a rede pode escolher esquecer os dados sempre que a informação não é necessária, mas também resolve os problemas de gradiente, já que as portas logísticas têm uma derivada muito boa.

## LSTM Arquitetura

A Long Short-Term Memory é composta por uma unidade linear rodeada por três portas logísticas. O nome desses portões varia de lugar para lugar, mas os nomes mais comuns para eles são:

 - a porta de "entrada" ou "gravação", que lida com a gravação de dados na célula de informação
 - a porta de "saída" ou "leitura", que lida com o envio de dados de volta para a rede recorrente
 - o Gate "Keep" ou "Forget", que cuida da manutenção e modificação dos dados armazenados na célula de informação

![Drag Racing](Dragster.jpg)