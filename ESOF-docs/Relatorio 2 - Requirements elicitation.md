# Elicitação de Requisitos

## Requisitos

## Requisitos e Características Específicos

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

## Contribuição do Grupo
* [José Costa](https://github.com/zecst19) 
* [Nuno Freitas](https://github.com/nunofreitas96) 
* [Rui Paiva](https://github.com/ruivop) 
* [Tiago Silva](https://github.com/tadias) 
