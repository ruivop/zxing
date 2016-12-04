# Verificação e Validação

**Conteúdos**
- [Introdução](#introdução)
- [Testabilidade do Software](#testabilidade-do-software)
      - [Controlabilidade](#controlabilidade)
      - [Observabilidade](#observabilidade)
      - [Isolabilidade](#isolabilidade)
      - [Separação de Responsabilidades](#separação-de-responsabilidades)
      - [Compreensibilidade](#compreensibilidade)
      - [Heterogeneidade](#heterogeneidade)      
- [Estatísticas de Teste](#estatísticas-de-teste)
- [Identificação de um Bug](#identificação-de-um-bug)
- [Contribuição do Grupo](#contribuição-do-grupo)

## Introdução

A verificação e validação de um projeto são etapas importantes na conceção de um software. A verificação é o processo que assegura que o projeto final está conforme foi especificado nos seus requerimentos. A validação, por outro lado, assegura através de testes que o produto final satisfaz o que é esperado que faça, no seu respetivo âmbito.

## Testabilidade do Software

A Testabilidade do Software é o grau de suporto de testes, para um certo artefacto da aplicação, dado um certo contexto. Se a testabilidade de um artefacto é alta, então encontrar falhas no sistema (se este as tiver) através de testes é mais fácil.

Testabilidade não é uma propriedade intrínseca de um artefacto de sofware e não pode ser medida diretamente. É sim uma propriedade extrínseca que resulta da interdependência do software a testar e dos objetivos do teste, dos métodos de teste, e dos recursos.

Um grau mais baixo de testabilidade resulta num maior esforço por parte dos testes, e nalguns casos mais extremos a falta de testabilidade pode impossibilitar o teste de certas partes do software.

O *zxing* utiliza vários casos de teste diferentes para cada tipo de código no seu arsenal de descodificação.

A Testabilidade de componentes de software é determinada por fatores como:

### Controlabilidade

A Controlabilidade corresponde à possibilidade de controlar o estado de uma componente sob teste.

Neste projeto a controlabilidade (em módulos) é elevada, visto que cada módulo de descodificação não depende de outros que sejam alterados por esse input ao teste (imagem). No entanto, visto que estamos a falar de descodificar códigos gerados de formas diferentes por entidades diferentes, pode aferir-se que uma total controlabilidade é impossível, visto que o módulo deve ser capaz de descodificar todos os casos, não sendo possível testá-los todos. Mas, em geral, os testes permitem exercitar as capacidades totais de uma determinada módulo.
      
Em relação a cada componente (classe) em teste (CUT), a controlabilidade é extremamente pequena, visto apenas serem feitos teste de mais alto nível. Cada input (imagem) vai afetar vários componentes, assim não sendo possível saber se algum deles errou e em que caso, ou ainda se há erros em cadeia que originam num resultado correto. 


### Observabilidade

A Observabilidade é a possibilidade de observar os resultados dos testes, quer estes sejam intermédios ou finais.

A observabilidade, neste projeto, é média visto que com um determinado input não é possível saber com exatidão se a computação foi bem efetuada. Por exemplo se o input (uma imagem) for menos visível, um teste, apesar de ter feito a computação da imagem corretamente, pode dar um resultado negativo. No entanto, em todos os testes aos módulos há uma tolerância de erros (numero máximo/mínimo de descodificações bem/mal sucedidas de um conjunto de imagens). Assim, e apesar de não ser um resultado binário, dá um grau de certeza médio de que um determinado módulo está a funcionar corretamente.

### Isolabilidade

Isolabilidade é a possibilidade de uma componente ser testada isoladamente.

Consideramos que a isolabilidade dentro deste projeto é absoluta quando falamos de módulos diferentes, expetando aqueles que interagem com mais de que um módulo. No que concerne a componentes (de cada módulo), estas não são testadas, pelo que não é possível isola-las.  Ainda assim, há testes a componentes mais particulares e que não dependem de mais componentes, como é o caso de componentes de estorturas de dados ou funções de matemática, sendo essas totalmente isoláveis.

### Separação de Responsabilidades

O grau de separação de responsabilidades das componentes sob teste incide sobre se estas têm uma única responsabilidade e se esta está bem definida.

Pela análise do código pudemos concluir que cada componente tem um objetivo muito especifico. Dentro de cada módulo a estortura é muito semelhante havendo componentes para codificar, descodificar e detetar códigos de barras. Componentes gerais a todos os módulos têm também funções muito particulares e fáceis de serem testadas. Assim consideramos que a separação de responsabilidades foi concebida de forma correta, contribuindo para uma maior testabilidade e organização do projeto.

### Compreensibilidade

Compreensibilidade corresponde ao grau de legibilidade da componente sob teste, por clareza intrínseca ou documentação disponível. Em geral, tudo se encontra com nomes compreensíveis e fáceis de perceber a sua finalidade. Apesar de não ser um projeto com elevado número de contribuidores, este é usado como componente em vários outros e por isso toma grande importância cria-lo de uma maneira clara e concisa. Podemos também ver que o código se encontra bem documentado a partir do respetivo [javadoc](https://zxing.github.io/zxing/apidocs/). Enquanto que a documentação não expande na explicação dos vários códigos diferentes, achamos isso adequado uma vez que eles podem ter elevado grau de complexidade e é necessário manter uma documentação breve mas que explique o suficiente. 

### Heterogeneidade

A heterogeneidade determina o grau em que o uso de diversas tecnologias requer diversos casos de teste. O projeto em si não faz uso de um número elevado de tecnologias diferentes pois há o objetivo de o manter o mais simples possível, tal como provado pelo sua [página de dependências](https://zxing.github.io/zxing/dependency-management.html). A partir desta também podemos ver que se recorre a JUnit de maneira a facilitar a realização de testes unitários. Independentemente de tal, é necessário a realização de um elevado número de casos de teste pois a aplicação pode ler variados tipos de códigos diferentes associados a diferentes tipos de tecnologia.

## Estatísticas de Teste

Para obter as estatísticas de teste deste projecto foram utilizadas as ferramentas JUnit, EclEmma e Codacy.

###Número de testes 

Através da utilização da ferramenta JUnit verificámos a execução de todos os testes, sendo que todos os testes correram correctamente à exceção de três que foram ignorados, isto porque durante a compilação do programa um dos ficheiros contidos no programa não tinha as permissões necessárias. 
O projecto usufrui de 408 testes, um número que achamos considerável aquando o tamaho do projecto.

![Program Tests in JUnit](/ESOF-docs/resources/JUnitTests.png)

###Cobertura

Utilizando EclEmma pudemos observar que os teste efectuados cobrem 93.8% do código total. Devido a este facto achamos que o código está suficientemente coberto pelos testes visto que estes abrangem mais que 80% do código.

![Coverage in EclEmma](/ESOF-docs/resources/Coverage.png)

###Outras estatísticas

Utilizámos o Codacy para examinar ainda outros aspectos do código do programa. Examinando as estátitiscas podemos observar que o código é muito seguro e robusto visto quenão tem nenhum problema de compatibilidade ou segurança, além de o código não utilizado e problemas de performance são minímos. No entanto o código é extremamente propenso a erros. Quando investigámos porquê apercebemo-nos que o criador do projecto têm uma tendencia a não privatizar as variáveis o que leva a um risco elevado de encapsulamento das mesmas.

![Statistics in Codacy](/ESOF-docs/resources/Statistics.png)

## Identificação de um Bug

O bug em análise é o bug [#649](https://github.com/zxing/zxing/issues/649) listado nas *issues* do projeto *zxing*. O problema em questão surge quando se tenta codificar código ASCII de um *non printable character* em *code 128* (uma simbologia de códigos de barras de alta densidade), situação esta em que é lançada a esceção de caracter inválido, no entanto *code 128* suporta todos os caracteres ASCII.
Após análise do bug, verificou-se que o problema é o seguinte: em ASCII, dentro dos *non printable characters*, a codificação apenas suporta o caracter do espaço (hex:20), e nao suporta os caracteres desde o 0 até ao 1F.



## Contribuição do Grupo
* [José Costa](https://github.com/zecst19): 
* [Nuno Freitas](https://github.com/nunofreitas96): 
* [Rui Paiva](https://github.com/ruivop): 
* [Tiago Silva](https://github.com/tadias): 
