#Relatório 1

#Zxing

##Descrição do Projeto

Zxing("Zebra Crossing") é uma plataforma open-source de processamento de códigos de barras 1D/2D implementada em Java com portabilidade para : c++, iphone, aobjc, ationscript, jruby.

![Zxing example](https://lh6.ggpht.com/Ax3eaBtJt0CVdY_lfFlGYg2RKdovXNVNzr91n_u22OKZu1WqIW-iQ44WR0Nmn5PkyKY=h900)

O Zxing tem uma aplicação para Android, que descodifica imagens em tempo real, e vários Websites para codificção e descodificação de QR Codes. QR Codes são códigos de barras bidimensionais que são convertidos em texto.

O desenvolvimento do projeto está já praticamente terminado sendo a principal atividade actualmente a correcção de bugs. Este já existe há 9 anos (desde 2007) e foi desenvolvido maioritarimente pelo esforço de duas pessoas, sendo [Sean Owen](https://github.com/srowen) o principal desenvolvedor, tomando este também o papel de controlo de qualidade do projeto, controlando assim as submissões feitas.

Existe um [fórum](https://groups.google.com/forum/#!forum/zxing) com o objetivo de contactar os desenvolvedores. São lançadas [várias versões da plataforma](https://github.com/zxing/zxing/releases) apesar de agora menos regularmente.

O projeto está licenciado sob a [licença Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).

##Processo de Desenvolvimento


O modelo utilizado ao longo do desenvolvimento e ainda utilizado é o de um projeto simples e pequeno. O principal desenvolvedor é também o que mantém o projeto, ou seja, torna possível a distribuição da aplicação assim como organiza e adiciona novo código que tanto pode adicionar novas funcionalidades como correcções ao código já existente. Seguindo o modelo simples já referido, não se viu necessário recorrer ao uso de branches e todos os **pushes são diretamente feitos para master**.

Recorre-se ao uso de **automação de testes de maneira** a poupar tempo e não repetir várias vezes a mesma tarefa. Um dos pontos principais no desenvolvimento deste projeto é o recurso a ***continuous integration*** (CI), ou seja, juntar várias vezes as cópias funcionais de diferentes pessoas para uma principal que irá conter todas as mudanças, tudo isto feito as vezes quanto necessárias de maneira a manter a o projeto o mais atualizado possível. Os testes automados contribuem para essa prática. Assim, há sempre uma versão da aplicação atualizada pronta a ser utilizada com o que foi adicionado recentemente, sendo assim criado código robusto que facilita integração.

O projeto tomou este caminho maioritarimente pela razão que o desenvolvedor não achou necessário recorrer a métodos mais complexos e, no início do desenvolvimeto do projeto, ferramentas como github, git e maven não estavam avançadas de maneira satisfatória, o que dificultava a colaboração entre pessoas.

##Análise Crítica
###Opiniões
Este é um projeto de **grande visibilidade**, veja-se, por exemplo, a aplicação oficial ([Barcode Scanner](https://play.google.com/store/apps/details?id=com.google.zxing.client.android&hl=pt-PT)), que tem mais de 100 milhões de downloads. Este número permite ter um grande *feed back* dos problemas e sugestões em relação à aplicação, que usa a biblioteca. Adicionalmente, a biblioteca, em si, também é muito conhecida e utilizada quando o assunto é [códigos de barras](https://pt.wikipedia.org/wiki/C%C3%B3digo_de_barras). Permitindo, assim, a existênca de uma vasta gama de *tutoriais* explicatic
vos do funcionamento do projeto.

Ainda na parte positiva, este projeto não é muito extenso e foi concebido por uma equipa pequena, e por isso está **bem organizado** e é fácil compreender onde está uma determinada classe, tornando o processo de utilização e alteração do código mais fácil. Para além disto, temos o **apoio de um [contribuidor](https://github.com/srowen)** que esteve no processo de desenvolvimento, desde o principio, e que está disponível para responder a todas as perguntas sobre o projeto.

Por outro lado, o projeto é já **antigo e está pouco ativo**, portanto não temos um suporte da comunidade tão variado como desejado. A atividade atual do projeto também é visível nos apenas **12** ***issues***. Como consequência não sabemos o que corrigir no projeto, visto que estas *issues* envolvem um grande conhecimento técnico sobre o tema da descodificação de [códigos de barras](https://pt.wikipedia.org/wiki/C%C3%B3digo_de_barras). Por fim, consideramos, como ponto negativo, o facto de **não existirem** ***branches*** e do novo código (p.e. novas *features* e *bug fixes*) ser diretamente integrado no *master*. Assim, não permitindo que diferentes equipas a conceber diferentes *fetures* trabalharem isoladamente.

###Alternativas

O facto de este projeto, desde o ínicio,ter sido mantido e melhorado regularmente apenas por duas pessoas e não ser muito extenso, fez com que não sofresse de problemas que outros projetos teriam de resolver, como por exemplo problemas de comunicação entre elementos da equipa e uma grande acumulação de erros não tratados.

No entanto a utilização do modelo de **desenvolvimento e entrega incremental** permitiria determinar mais facilmente prioridades na melhoria do software e ter mais feedback no que já foi feito, algo fulcral pois a dimensão da equipa traz dificuldades em analisar com eficiência todas as caraterísticas do projeto. 
De facto os criadores do projeto adoptaram uma estratégia semelhante, pedindo aos utilizadores da plataforma para discutirem qualquer dúvida ou bug encontrado num fórum específico e têm feito pequenos updates no projeto mediante o comentado nesse fórum.

Também seria possível a utilização do **modelo em cascata** que permitiria uma boa partição de cada fase do projeto mas este modelo iria falhar em dois aspetos fulcrais: poderia ser demasiado inflexível perante as sugestões dos utilizadores, algo que os programadores que se encontram neste momento a desenvolver e manter o projeto têm muito em conta, e a dimensão da equipa é pequena o suficiente para ser fácil organizar o trabalho necessário sem particionar o projeto.

Finalmente o modelo de **Espiral de Boehm** seria uma boa alternativa para organizar o projeto e assegurar a continua evolução da plataforma, sem aumentar os riscos. No entanto como o projeto está na sua fase final achamos que a utilização de um modelo tão complexo é desnecessária.

##Contribuição do Grupo
* [José Costa](https://github.com/zecst19) 25%
* [Nuno Freitas](https://github.com/nunofreitas96) 25%
* [Rui Paiva](https://github.com/ruivop) 25%
* [Tiago Silva](https://github.com/tadias) 25%

##Identificação do Grupo

Grupo:
* [José Costa](https://github.com/zecst19) (up201402717@fe.up.pt)
* [Nuno Freitas](https://github.com/nunofreitas96) (up201404739@fe.up.pt)
* [Rui Paiva](https://github.com/ruivop) (up201405136@fe.up.pt)
* [Tiago Silva](https://github.com/tadias) (up201404689@fe.up.pt)
