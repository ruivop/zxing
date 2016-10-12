#Relatório 1

#Zxing

##Descrição do Projeto

Zxing("Zebra Crossing") é uma plataforma open-source de processamento de códigos de barras 1D/2D implementada em Java com portabilidade para : c++, iphone, aobjc, ationscript, jruby.

![Zxing example](https://lh6.ggpht.com/Ax3eaBtJt0CVdY_lfFlGYg2RKdovXNVNzr91n_u22OKZu1WqIW-iQ44WR0Nmn5PkyKY=h900)

O Zxing tem uma aplicação para Android, que descodifica imagens em tempo real, e vários Websites para codificção e descodificação de QR Codes. QR Codes são códigos de barras bidimensionais que são convertidos em texto.

O desenvolvimento do projeto está já praticamente terminado sendo a principal atividade actualmente a correcção de bugs. Este já existe há 9 anos (desde 2007) e foi desenvolvido maioritarimente pelo esforço de duas pessoas, sendo [Sean Owen](https://github.com/srowen) o principal desenvolvedor, tomando este também o papel de controlo de qualidade do projeto, controlando assim as submissões feitas.

Existe um [fórum](https://groups.google.com/forum/#!forum/zxing) com o objetivo de contactar os desenvolvedores. São lançadas [várias versões da plataforma](https://github.com/zxing/zxing/releases) apesar de agora menos regularmente.

O projeto está licenciado sob a [licença Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).

##Processso de Desenvolvimento


O modelo utilizado ao longo do desenvolvimento e ainda utilizado é o de um projeto simples e pequeno. O principal desenvolvedor é também o que mantém o projeto, ou seja, torna possível a distribuição da aplicação assim como organiza e adiciona novo código que tanto pode adicionar novas funcionalidades como correcções ao código já existente. Seguindo o modelo simples já referido, não se viu necessário recorrer ao uso de branches e todos os pushes são diretamente feitos para master.

Recorre-se ao uso de automação de testes de maneira a poupar tempo e não repetir várias vezes a mesma tarefa. Um dos pontos principais no desenvolvimento deste projeto é o recurso a continuous integration (CI), ou seja, juntar várias vezes as cópias funcionais de diferentes pessoas para uma principal que irá conter todas as mudanças, tudo isto feito suficientes vezes quanto necessárias até num mesmo dia. Os testes automados contribuem para essa prática. Assim, há sempre uma versão da aplicação atualizada pronta a ser utilizada com o que foi adicionado recentemente, sendo assim criado código robusto que facilita integração.

##Análise Crítica

##Contribuição do Grupo

##Identificação do Grupo

Grupo:
* [José Costa](https://github.com/zecst19) (up201402717@fe.up.pt)
* [Nuno Freitas](https://github.com/nunofreitas96) (up201404739@fe.up.pt)
* [Rui Paiva](https://github.com/ruivop) (up201405136@fe.up.pt)
* [Tiago Silva](https://github.com/tadias) (up201404689@fe.up.pt)
