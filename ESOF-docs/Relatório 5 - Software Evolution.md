# Evolução de Software

**Conteúdos**
- [Introdução](#introdução)
- [Identificação da Feature](#identificação-da-feature)
- [Desenvolvimento da Feature](#desenvolvimento-da-feature)
- [Pull Request](#pull-request)
- [Contribuição do Grupo](#contribuição-do-grupo)
- [Anexo(Análise Better Code Hub)](https://github.com/ruivop/zxing/blob/master/ESOF-docs/Documentos%20de%20apoio/Better%20Code%20Hub.pdf)


## Introdução

Uma vez que o zxing é um projeto já maioritariamente terminado, há poucos problemas e tarefas a desenvolver. No entanto, o projeto está aberto à implementação de novas funcionalidades, desde que estas sejam relevantes. No presente relatório serão descritos os processos de identificação, desenvolvimento e submissão de uma nova Feature no projeto zxing. 

## Identificação da Feature

Existem duas formas de selecionar uma nova feature a adicionar ao projeto, ou através da criação de algo totalmente novo  de raíz, ou através da resolução de um issue pré-existente. Devido à natureza do projeto (quase totalmente finalizado e com poucos issues) decidimos optar pela primeira opção.

Como nova feature a implementar escolhemos adicionar, ao histórico de análises um botão de ordenação desse mesmo histórico, sendo agora possível ordenar tanto cronologicamente como alfabéticamente e também inverter a ordem dos resultados.

## Desenvolvimento da Feature

### Identificação do código chave para a implementação da feature
Pela análise já anteriormente feita, já ficamos com uma bagagem suficiente para identificar o código que pretendíamos alterar. A aplicação *android* utiliza *Activities* para mostrar toda parte gráfica da aplicação. A *activity* principal (*CaptureActivity*) é responsável por iniciar o histórico (abrir a base de dados).

![CaptureActivity](/ESOF-docs/resources/CaptureActivity.png)
 
No entanto é na *Activity* do histórico (*HistoryActivity*), que a lista dos elementos dos elementos do histórico aparece. Logo seria aí que teríamos que acrescentar o código da nossa *feature*.
 
 ![builHistoryItems](/ESOF-docs/resources/builHistoryItems.png)
 
A partir da análise do código da classe *HistoryActivity* percebemos o método que atualizava o histórico era o método *builHistoryItems()*.
 
 ![Query](/ESOF-docs/resources/query.png)
 
Neste método era feita uma *query*, com a ordenação pretendida, à base de dados. Logo, seria aí que teríamos de mudar o código para implementar a nova feature. No entanto, também foram precisos botões para ordenar a lista do histórico de acordo com o desejado. No *android*, os *layouts* definem os sítios onde estão os botões e outros elementos visuais. Como tal para acrescentar um botão foi apenas preciso localizar o *layout* do menu do histórico. No entanto ainda teríamos que ter *listeners* que recebessem a informação de quando estes foram carregados, para desencadear o processo de atualização. 

A partir da análise do código encontramos a solução que residia no método *onOptionsItemSelected(MenuItem item)*, que recebia numa máquina de estados qual o botão que foi carregado.

 ![builHistoryItems](/ESOF-docs/resources/handler.png)


### Solução encontrada

Com os botões feitos e os respetivos os respetivos estados que eram ativados quando esses botões eram carregados, faltava agora encontrar uma solução que permitisse fazer com que cada um desses estados comunicasse com a *query* de ordenação. Para tal, foram criadas duas variáveis públicas e estáticas. Uma para a ordenação alfabeticamente->cronologicamente/cronologicamente->alfabeticamente e outra para poder alterar a ordem (inversa ou não).

Cada uma destas variáveis era alterada pelo respetivo botão, para um valor que era entendido pela *query*. Assim na *query* só precisava de haver uma concatenação das duas variáveis e assim ordenar os items do histórico, segundo o desejado.

 ![historyscreen](/ESOF-docs/resources/history1.png)  ![historyoptions](/ESOF-docs/resources/historyoptions1.png)

## Pull Request

A funcionalidade implementada foi enviada através do pull request [#1](https://github.com/ruivop/zxing/pull/1). Uma vez aprovada esta pull request, a funcionalidade implementada passa a fazer parte do código "oficial" do projeto.

##Contribuição do Grupo
* [José Costa](https://github.com/zecst19): 25%
* [Nuno Freitas](https://github.com/nunofreitas96): 25%
* [Rui Paiva](https://github.com/ruivop): 25%
* [Tiago Silva](https://github.com/tadias): 25%
