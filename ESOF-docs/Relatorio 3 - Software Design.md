# Design de Software

**Conteúdos**
- [Introdução](#introdução)
- [Vista Lógica](#vista-lógica)
- [Vista de Desenvolvimento](#vista-de-desenvolvimento)
- [Vista Física](#vista-física)
- [Vista de Processo](#vista-de-processo)
- [Contribuição do Grupo](#contribuição-do-grupo)

##Introdução

Arquitetura de software é forma como os componentes de um projeto estão organizados: as suas relações mutuas e com o ambiente, e os princípios que regem o seu desenvolvimento e evolução. Assim, com este relatório, é possível saber como o projeto está organizado, a alto nível, tendo uma noção bastante concreta do projeto. Para melhor compreensão, utilizamos diagramas UML.  Usamos, também, o modelo 4+1, que permite uma criar uma imagem completa do projeto. De mencionar também que a elicitação de requerimentos (vista “+1”), já foi feita no relatório anterior.

Relativamente ao padrão de desenho utilizado, apesar de não haver informação concreta acerca deste e depois de uma análise ao código, pensamos que foi utilizado o MVC. Este parece-nos o mais adequando, visto haver múltiplas formas de interagir com os dados e há possivelmente interações futuras e que não são conhecidas (novos códigos de barras). Este é um assunto visto com mais profundidade na vista lógica.

Por fim, neste relatório focamo-nos na aplicação android, visto ser esta a mais acessível a futuras alterações e a que não envolve tantos conhecimentos técnicos acerca de códigos de barras.



##Vista Lógica

Existem vários tipos de códigos de barras 1d e 2d. Cada um tipo de código de barras pode ter um protocolo de leitura diferente. Ora o projeto foca-se em descodificar e produzir daca um destes tipos de código e tratá-lo como devidamente. O core do projeto, foca-se na descodificação e geração de imagens (de imagens para resultados interpretáveis, ou vice-versa, respetivamente). Para cada código existe um package. Os códigos de barras suportados são e os seus packages no core são:

- Produto 1D: oned;
- Industrial 1D: oned;
- QR codes: qrcode; 
- Data Matrix: datamatrix;
- Aztec: aztec;
- MaxiCode: maxicode;
- PDF417: pdf417.
  
Para além destes packages há vários outros packages:

- client – encapsula diferente resultados da leitura. Ou seja, cada tipo de resultado (que é uma string) tem um diferente tipo de classe (para encapsular se essa string representa um email, um contacto, uma localização, um url…);
- common – que contém uma série de estruturas de dados/ algoritmos necessários para o projeto, por exemplo BitArray, DecoderResult ou StringUtils;
- multi – que tenta detetar mais que um código em uma imagem.
No entanto, o objeto deste trabalho é a analise do código da aplicação android, que faz uso do core de zxing. Esta aplicação tem também vários packages:

- clipboard – que implementa o copiar colar;
- camera – que inicia, configura e ativa certas funcionalidades da camara;
- encode – responsável por criar códigos conforme o input do utilizador;
- history – responsável pelo histórico da aplicação;
- result – responsável por desencadear uma ação especifica para cada tipo de código (url, e-mail, contacto…);
- share – para partilhar o contudo do resultado de um determinado código;
- wifi – responsável por ligar/desligar/configurar o wifi.
  
Apesar de não estar explicito, pensamos que este projeto usa o modelo MVC (Model View Controler). O Controler é o core de zxing, visto que faz o processamento das imagens e o que pode alterar o estado do Model (quando encontra um código de barras numa imagem). O são os packages da aplicação android, que são controlados por Activities (android.app.Activity) e que permitem que View tenha possa mostrar o estado atual da aplicação. View é intrínseco ao android e permite que uma determinada Activity tenha um determinado layout, mostrando-o.

![zxing Logial View Diagram](/ESOF-docs/resources/vista%20logica.bmp)


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
