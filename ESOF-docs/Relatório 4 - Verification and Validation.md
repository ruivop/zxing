# Verificação e Validação

**Conteúdos**
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

## Testabilidade do Software

A Testabilidade do Software é o grau de suporto de testes, para um certo artefacto da aplicação, dado um certo contexto. Se a testabilidade de um artefacto é alta, então encontrar falhas no sistema (se este as tiver) através de testes é mais fácil.

Testabilidade não é uma propriedade intrínseca de um artefacto de sofware e não pode ser medida diretamente. É sim uma propriedade extrínseca que resulta da interdependência do software a testar e dos objetivos do teste, dos métodos de teste, e dos recursos.

Um grau mais baixo de testabilidade resulta num maior esforço por parte dos testes, e nalguns casos mais extremos a falta de testabilidade pode impossibilitar o teste de certas partes do software.

O *zxing* utiliza vários casos de teste diferentes para cada tipo de código no seu arsenal de descodificação.

A Testabilidade de componentes de software é determinada por fatores como:

### Controlabilidade

A Controlabilidade corresponde à possibilidade de controlar o estado de uma componente sob teste. 

### Observabilidade

A Observabilidade é a possibilidade de observar os resultados dos testes, quer estes sejam intermédios ou finais.

### Isolabilidade

Isolabilidade é a possibilidade de uma componente ser testada isoladamente.

### Separação de Responsabilidades

O grau de separação de responsabilidades das componentes sob teste incide sobre se estas têm uma única responsabilidade e se esta está bem definida.

### Compreensibilidade

Compreensibilidade corresponde ao grau de legibilidade da componente sob teste, por clareza intrínseca ou documentação disponível.

### Heterogeneidade

A Heterogeneidade determina o grau em que o uso de diversas tecnologias requer diversos casos de teste.

## Estatísticas de Teste

Para obter as estatísticas de teste deste projecto foram utilizadas as ferramentas JUnit, EclEmma e Codacy.

###Número de testes 

Através da utilização da ferramenta JUnit verificámos a execução de todos os testes, sendo que todos os testes correram correctamente à exceção de três que foram ignorados, isto porque durante a compilação do programa um dos ficheiros contidos no programa não tinha as permissões necessárias. \n
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
