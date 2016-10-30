# Elicitação de Requisitos

## Requisitos
O processo de gestão de requisitos neste projeto é, atualmente, apenas a manutenção de código.  Os novos módulos, que foram, ao longo do tempo, sendo adicionados ao projeto, eram “plugins” e quase todas as propostas eram aceites, não havendo para isso um processo formal.

O feedback dos utilizadores foi, numa fase inicial, moderadamente importante para o desenvolvimento do projeto, no entanto, este foi diminuindo nos passados anos, visto que foi dada uma maior prioridade á manutenção de código. Este feed back era obtido principalmente no fórum e em comentários em diversos sites e plataformas, não sendo concebido, para este efeito, qualquer tipo de entrevistas ou documentos formais.

Uma nova feature que se pretenda desenvolver deve ser reportada no fórum, para que a comunidade fique a par do desenvolvimento paralelo do projeto. Para a adição de novas features, deve ser feito um fork do projeto, o seu desenvolvimento nesse repositório e um posterior pull request para o ramo principal (único ativo). Se assim o entender, o responsável pode aceitar o novo código.



## Requisitos e Características Específicos

###Requisitos Funcionais
O projecto *zxing* foi desenvolvido, desde o início, para que pudesse executar 2 funções principais: ler a informação existente em códigos QR de uma e duas dimensões, e construir códigos QR a partir de informação fornecida. 


### Requisitos não funcionais
####Requisitos de Qualidade
**Eficiência de Performance**
Foi de grande importância durante o desenvolvimento do projecto que qualquer software que utilizasse a biblioteca conseguisse descodificar e criar um código QR com rapidez.

**Consistência**
O projecto foi desenvolvido de modo a garantir que a partir de todas as plataformas utilizadas funcionasse da mesma forma e eficientemente.

**Compatibilidade**
Desde o ínicio da criação da biblioteca que esteve em conta o seu funcionamento em várias plataformas.

**Capacidade de Manutenção**
Apesar de o projecto não ter tido nas suas origens nenhum plano para assegurar a manutenção da biblioteca, a atenção à comunicação e tamanho relativo do projecto dos utilizadores e estado publico do código permitiu que fosse atualizado sem grandes complicações.

**Segurança**
Todos os níveis do software são completamente públicos, sem ter havido nenhuma preocupação em proteger o acesso ao código.

## Casos de Uso

O projeto *zxing* consiste, maioritariamente, em 3 plataformas. A app para Android chamada "*Barcode Scanner*", um site de descodificação de códigos QR e outro de codificação.

###Barcode Scanner
Os diagramas seguintes mostram os principais casos de uso da aplicação para Android "Barcode Scanner", do site de Descodificão e Codificação respetivamente

![zxing Barcode Scanner Use Cases](/ESOF-docs/resources/barcode scanner new.png)


Com a opção Compartilhar o utilizador pode partilhar, através de um código QR um contacto, um texto simples ou um código já existente. Em Histórico é possível ver a lista de códigos analisados previamente. Em configurações todas as definições da app podem ser alteradas. Em ajuda está um pequeno guia de utilização. E ao analisar um código, dependendo se for um endereço de e-mail, ou um URL, ou coordenadas GPS, é-nos permitido, enviar um mail ou adicionar o endereço aos contactos, ou aceder ao URL no browser predefinido ou partilhar o link, ou vizualizar no mapa a sítio para onde as coordenadas apontam.

![zxing Descodification Use Cases](/ESOF-docs/resources/decoder.png)


Ao inserir um URL ou fazer upload de uma imagem de um código QR, e submetendo-o, são-nos dadas ao informações mais técnicas. Ao contrário da app que nos permite interagir com o resultado, este descodificador dá-nos informações como: o formato do código, ou o texto ou os bytes em RAW ou o tipo de informação (nº de telefone, e-mail, URL).

![zxing Codification Use Cases](/ESOF-docs/resources/code generator new.png)

Com o site gerador de Códigos, temos de selecionar que tipo de conteúdo queremos codificar (informação de contacto, endereço de e-mail, evento no calendário, localização GPS, nº de telefone, SMS, texto, URL ou informações de rede Wifi), o tamanho do código (pequeno, médio ou grande), o fator de correção de erros ( a correção de erros corresponde à habilidade do código de sofrer "dano", ou seja, a sua capacidade de ser analisado manter-se mesmo que parte seja obstruido ou removido, e varia entre L, M, Q e H) e *character encoding* (pode ser UTF-8, ISO-8859-1 e Shift_JIS). 

## Modelo de Domínio

O contexto em que este software opera segue o modelo apresentado a seguir. A classe conceptual *Hints* refere-se a tudo a que o descodificador usa para identificar o código introduzido de uma maneira mais rápida, uma vez que podem ser aceites vários formatos.

![zxing Domain Model](/ESOF-docs/resources/domainmodel.png)

## Contribuição do Grupo
* [José Costa](https://github.com/zecst19) 
* [Nuno Freitas](https://github.com/nunofreitas96) 
* [Rui Paiva](https://github.com/ruivop) 
* [Tiago Silva](https://github.com/tadias) 
