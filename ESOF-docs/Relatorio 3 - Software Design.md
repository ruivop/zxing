# Design de Software

**Conteúdos**
- [Introdução](#introdução)
- [Vista Lógica](#vista-lógica)
- [Vista de Desenvolvimento](#vista-de-desenvolvimento)
- [Vista Física](#vista-física)
- [Vista de Processo](#vista-de-processo)
- [Contribuição do Grupo](#contribuição-do-grupo)

##Introdução
  Arquitetura de software é forma como os componentes de um projeto estão organizados: as suas relações mutuas e com o ambiente, e os princípios que regem o seu desenvolvimento e evolução. Assim, com este relatório, é possível saber como o projeto está organizado, a alto nível, tendo uma noção bastante concreta do projeto. Para melhor compreensão, utilizamos diagramas UML.  Utilizamos também o modelo 4+1, que permite uma criar uma imagem completa do projeto. De mencionar também que a elicitação de requerimentos (vista “+1”), já foi feita no relatório anterior.
  
Relativamente ao padrão de desenho utilizado, apesar de não haver informação concreta acerca deste e depois de uma análise ao código, pensamos que foi utilizado o MVC. Este parece-nos o mais adequando, visto haver múltiplas formas de interagir com os dados e há possivelmente interações futuras e que não são conhecidas (novos códigos de barras). Este é um assunto visto com mais profundidade na vista lógica.

Por fim, neste relatório focamo-nos na aplicação android, visto ser esta a mais acessível a futuras alterações e a que não envolve tantos conhecimentos técnicos acerca de códigos de barras.


##Vista Lógica

##Vista de Desenvolvimento

![zxing Implementation View Diagram](/ESOF-docs/resources/implementation_view.png)


A interacção principal é feita entre a câmara do dispositivo e o descodificador que interpreta o que recebeu da câmara. Para certos tipos de códigos, como por exemplo um código de barras de um produto, é necessária obter dados de produtos que são provenientes da *Google Product Search* ou *Web Search*, e que por isso não são mantidos na aplicação em si. Tendo em conta a simplicidade da aplicação não se recorre ao uso de camadas e tal parece uma abordagem correta visto o objetivo final dela, que é uma análise rápida e eficiente de uma imagem recebida que pode ser identificada como vários tipos de códigos diferentes. 

##Vista Física

##Vista de Processo

Através do diagrama de atividades da App para Android é possível perceber a sequência de processos e as suas interações.

![zxing Process View Diagram](/ESOF-docs/resources/processview.png)

Quando a App é iniciada a câmara do dispositivo também o é, e na parte superior do ecrã está o menu que permite aceder às definições,
entre outras opções. A partir desse momento é possível analisar um código e depois da análise é possível usá-lo, dependendo do seu formato
(texto, URL, etc) ou voltar ao menu inicial com a câmara inicializada. É possível sair da App a qualquer altura do seu uso. 

##Contribuição do Grupo
* [José Costa](https://github.com/zecst19): 25%
* [Nuno Freitas](https://github.com/nunofreitas96): 25%
* [Rui Paiva](https://github.com/ruivop): 25%
* [Tiago Silva](https://github.com/tadias): 25%
