# Atividade de revisão e prática — Estruturas de dados

**Objetivo:** verificar a compreensão das estruturas estudadas e, principalmente, praticar suas implementações antes do desafio final.

## Orientações

- Responda às questões teóricas **com suas próprias palavras**. Quando solicitado, descreva o raciocínio em vez de escrever código.
- Nas questões práticas, implemente as estruturas e teste todas as operações. Não basta copiar a implementação do curso: adapte-a às regras apresentadas.
- Você pode consultar o material das aulas e a documentação, mas deve conseguir explicar o funcionamento do código que entregar.   
- Use **JavaScript** para implementar as estruturas. Os contratos de interface ao final estão escritos em **TypeScript** apenas para apresentar a ideia de interfaces: converse com seu mentor sobre essa sintaxe antes de utilizá-la. Se decidir usar `implements` de verdade, o arquivo deverá ser TypeScript (`.ts`).
- Não utilize bibliotecas externas para implementar as estruturas.

## Parte 1 — Questões teóricas

### 1. Arrays

O que é um array? Como podemos acessar, adicionar e remover elementos dele? Explique o papel dos índices nessas operações.

É uma estrutura que armazena dados em  uma coleção, sendo eles apenas em sequência de elementos do mesmo tipo e com só um nome de variável.
Podemos acessar, adiconar e remover elementos através do índice com 0,1, 2, 3, 4 ... . Ele  funciona como um endereço para buscar oque desejamos.


### 2. Percorrendo um array

Imagine que você tem um array com 100 números e precisa descobrir qual é o maior. Como resolveria esse problema utilizando apenas um loop, sem recorrer a funções prontas de busca ou ordenação? **Descreva o algoritmo textualmente**, passo a passo, sem escrever código.

1- Definir o valor inicial como referência
2- Criar uma estrutura de repetição para percorrer o array do primeiro até o último elemento
3- Para cada valor analisado na posição atual, comparamos se ele é maior que o atual numero armazenado na variável maiorValor.
4- Se ele for maior, substituimos o conteúdo da variável maiorValor pelo numero atual, que a partir desse momento passa a ser o maior. Se ele for menor, não fazemos nada e mantemos a variável maiorValor como já estava
5- O loop segue para o próximo elemento da array, repetindo a verificação e atualização até chegar ao final da lista.
6- Após o loop finalizar o percurso até o ultimo elemento, o valor que restar armazenado na variável maiorValor será o maior número da array.


### 3. Filas (FIFO)

O que é uma fila e como funciona o princípio FIFO? Dê um exemplo de utilização no desenvolvimento de software.

O termo FIFO vem de First in, First out. Significa "Primeiro a entrar, primeiro a sair"
Ele funciona igual uma fila na vida real (como uma fila de mercado ou banco).
Enfileirar: Novos elementos entram sempre pelo final da fila.
Desenfileirar: Os elementos são removidos sempre pela frente, ou seja, o início da fila.
Exemplo: Uma fila de pedidos no ifood. Ele se baseia na ordem de chegada dos pedidos, logo, o primeiro a chegar deve ser o prmeiro a sair.


### 4. Pilhas (LIFO)

O que é uma pilha e como funciona o princípio LIFO? Qual é a principal diferença entre uma pilha e uma fila?

O termo LIFO vem de Last in, first out. Traduzido do inglês, Ultimo a entrar, primeiro a sair.
O funcionamento é comparável a uma pilha de livros ou pratos na vida real.
Empilhar (Push): Novos elementos são adicionados sempre no topo da pilha.
Desempilhar (Pop): Os elementos são sempre removidos pelo topo da pilha.
Regra: O último elemento a ser adicionado é sempre o primeiro a ser removido. Para acessar um elemento que está no fundo, é necessário remover todos os elementos acima dele.

A principal diferença entre uma pilha e uma fila, é que na fila é sempre o primeiro que foi adicionado que vai sair antes. Já na pilha é o contrário, o primeiro a entrar é o ultimo a sair e o ultimo a entrar é o primeiro a sair.


### 5. Pilhas na prática

Imagine que você está desenvolvendo uma funcionalidade para desfazer as últimas alterações realizadas pelo usuário (Ctrl+Z). Por que uma pilha seria uma boa estrutura para resolver esse problema? Como funcionaria?

 Ela seria uma boa opção porque a operação só reverte a ultima modificação feita pelo usuário, sem risco de perder alterações anteriores. Além disso, o comportamento do usuário exige a lógica LIFO (Last in, First out). Então a ação mais recente é a que deve ser revertida. 


### 6. Listas ligadas

O que é uma lista ligada? Explique como seus elementos são organizados e como um elemento se conecta ao próximo.

É uma estrutura de dados linear composta por uma sequência de elementos chamados de nodes ou nós. Na lista ligada, os nós podem ficar espalhados em qualquer lugar da memória e são conectados por meio de ponteiros. 
Cada elemento é composto de no minimo duas partes: 
Dado - É a informação que se deseja armazenar
Ponteiro ou referência - É um endereço que aponta apenas para o próximo nó da sequência.


### 7. Arrays × listas ligadas

Qual é a principal diferença entre um array e uma lista ligada? Em quais situações uma lista ligada poderia ser uma escolha interessante?

A principal diferença está na forma como os dados são organizados na memória, oque determina como eles são acessados e modificados. 
Na array, os elementos ficam armazenados lado a lado em um único bloco coninuo de memória. Isso permite calcular o endereço exato de qualquer item usando seu indice.
Já na lista ligada, os elementos(nós) ficam espalhados pelos endereços aleatórios na memória, conectados por ponteiros que indicam onde está o proximo nó.

É interessante usar a lista ligada quando você precisa apagar ou adicionar itens o tempo todo e não quer ter o trabalho de reorganizar toda a coleção e para funcionalidades como desfazer/refazer (ctrl+z/ctrl+y) em editores, botões de voltar/avançar em navegadores ou playlists de musicas que dão pra pular e voltar.


### 8. Mapas (Map)

O que é um `Map` e como ele organiza as informações? Comparando-o com as outras estruturas que você estudou, qual tende a ser mais eficiente para **buscar um valor conhecido** e por quê?

Um Map(mais conhecido como dicionário) é uma estrutura de dados que armazena informações em pares de chave. Onde cada chave é única e serve como identificador direto para acessar seu respectivo valor. Diferente de arrays e listas ligadas, a maioria das implementações modernas de map utiliza uma tabela hash.

O Map tende a ser o mais eficiente para buscar um valor conhecido, desde que esse valor seja usado como chave ou associado a alguma chave conehcida. Em vez de procurar item por item, o Map aplica uma função sobre a chave buscada. Essa operação calcula instantaneamente o endereço exato na memória onde o dado está guardado.


### 9. Conjuntos (Set)

O que é um `Set` e qual é sua principal característica? Imagine que você recebeu uma lista de placas de veículos contendo valores repetidos. Como poderia utilizar um `Set` para obter apenas as placas distintas?

Set (ou conjunto) é um tipo de coleção usada para armazenar valores únicos, onde nenhum elemento pode se repetir. Ele está presente na maioria das linguagens de programação modernas (como JavaScript, Python e Java).
Sua principal característica é a unicidade de elementos, ou seja, não permitir valores duplicados. Ao tentar inserir um item que já existe no set, ele simplesmente ignora a operação, mantendo apenas uma cópia de cada valor.

A forma mais comum e eficiente de remover itens repetidos é passar a lista original diretamente no começo do Set e depois converter ele de volta para uma lista ou array, caso você precise usar métodos tradicionais de listas novamente.


## Parte 2 — Questões práticas

**Regra geral:** nas três implementações, você deve decidir **quais parâmetros cada operação recebe e o que ela retorna**, justificando suas escolhas. Pense também nos casos de erro e crie exemplos de uso que demonstrem o comportamento esperado.

### 10. Implementação de uma pilha

Usando os conhecimentos que você aprendeu acerca dessa estrutura de dados, **implemente uma pilha** com as seguintes operações:

- `empilhar`
- `desempilhar`
- `topo`
- `estaVazia`
- `tamanho`
- `clonar`
- `reverter`
- `imprimir`

**Regras e restrições:**

1. Utilize um array como armazenamento interno. **O índice `0` deve representar o topo da pilha**.
2. A pilha deve manter uma **variável inteira de tamanho**, atualizada a cada inserção ou remoção. A operação `tamanho` deve consultar essa variável.
3. `topo` deve apenas consultar o elemento no topo, **sem removê-lo**.
4. Nas operações `empilhar`, `desempilhar`, `clonar` e `reverter`, faça os deslocamentos ou percursos necessários **manualmente, usando loops**. Não utilize métodos prontos de array para realizar essas tarefas (como `push`, `pop`, `shift`, `unshift`, `splice`, `reverse`, `slice` ou equivalentes).
5. `clonar` deve produzir uma **nova pilha independente**, com os mesmos elementos e na mesma ordem, sem modificar a original.
6. `reverter` deve **inverter a ordem dos elementos da própria pilha**.
7. Não permita `desempilhar` nem `clonar` quando a pilha estiver vazia. Defina como o programa comunica essas situações.
8. `imprimir` deve mostrar os elementos em ordem, identificando claramente qual é o topo.

**Teste, pelo menos:** empilhar três valores; consultar o topo; desempilhar; clonar e modificar uma das pilhas sem alterar a outra; reverter; tentar desempilhar e clonar uma pilha vazia.

### 11. Implementação de uma fila

Usando os conhecimentos que você aprendeu acerca dessa estrutura de dados, **implemente uma fila** com as seguintes operações:

- `inserir`
- `remover`
- `obterPrimeiro`
- `estaVazia`
- `tamanho`
- `clonar`
- `imprimir`

**Regras e restrições:**

1. Utilize um array como armazenamento interno. **O índice `0` deve representar o início da fila**, isto é, o primeiro elemento a sair.
2. A fila deve manter uma **variável inteira de tamanho**, atualizada a cada inserção ou remoção. A operação `tamanho` deve consultar essa variável.
3. `obterPrimeiro` deve apenas consultar o primeiro elemento, **sem removê-lo**.
4. Nas operações `inserir`, `remover` e `clonar`, faça os percursos e deslocamentos necessários **manualmente, usando loops**, sem utilizar métodos prontos de array que executem essas tarefas.
5. `clonar` deve produzir uma **nova fila independente**, mantendo a ordem de atendimento e sem modificar a original.
6. Não permita `remover` nem `clonar` quando a fila estiver vazia. Defina como o programa comunica essas situações.
7. `imprimir` deve mostrar a ordem dos elementos, identificando claramente o início e o fim da fila.

**Teste, pelo menos:** inserir três valores; consultar o primeiro; remover; clonar e modificar uma das filas sem alterar a outra; tentar remover e clonar uma fila vazia.

### 12. Implementação de uma lista simplesmente encadeada

Usando os conhecimentos que você aprendeu acerca dessa estrutura de dados, **implemente uma lista simplesmente encadeada** com as seguintes operações:

- `adicionar`
- `remover`
- `inserirNaPosicao`
- `removerNaPosicao`
- `substituirElementoNaPosicao`
- `posicaoDe`
- `obterDe`
- `imprimir`
- `tamanho`

**Regras e restrições:**

1. Crie uma classe `ListaEncadeada` e uma classe `No` (nó). **A classe `No` não deve ter operações de manipulação da lista.**
2. **Não utilize arrays para armazenar os elementos da lista.** Os elementos devem estar ligados por referências entre nós.
3. `adicionar` deve inserir um elemento **no final da lista, sem loops**. Pense em quais referências a classe precisará manter para que isso seja possível.
4. `remover` deve retirar a **primeira ocorrência de um valor informado**, se existir.
5. `inserirNaPosicao`, `removerNaPosicao`, `substituirElementoNaPosicao`, `posicaoDe` e `obterDe` devem operar sobre a lista percorrendo os nós quando necessário. Use **loops**, sem métodos prontos de arrays.
6. As posições começam em `0`. Para consultar, remover ou substituir, uma posição válida vai de `0` a `tamanho - 1`. 
7. Não permita consultar, remover ou substituir em posições inválidas, nem remover elementos de uma lista vazia. Se uma busca não encontrar o valor, comunique isso de forma clara.
8. `imprimir` deve apresentar a sequência dos nós, do primeiro ao último. A operação `tamanho` deve informar a quantidade atual de nós.

**Teste, pelo menos:** adicionar três valores; inserir no começo, no meio e no final; remover por valor e por posição; substituir um valor; buscar um valor existente e um inexistente; consultar posições válidas e inválidas; operar sobre uma lista vazia.

## Parte 3 — Contratos das estruturas (para discussão com o mentor)

A ideia dos contratos abaixo é **mostrar quais operações cada estrutura deve oferecer, sem decidir por você seus parâmetros e retornos**.

> **Atenção:** `interface` e `implements` são recursos do **TypeScript**, não do JavaScript puro. Neste esqueleto, `Function` é apenas uma marcação provisória para uma operação cuja assinatura você deverá definir. **Não é uma tipagem recomendada para um projeto final.** Antes de implementar em TypeScript, substitua `Function` por assinaturas com parâmetros e retornos adequados. Se trabalhar em JavaScript, use os nomes das operações como referência, sem copiar `interface` ou `implements`.

```ts
interface IPilha {
  empilhar: Function;
  desempilhar: Function;
  topo: Function;
  estaVazia: Function;
  tamanho: Function;
  clonar: Function;
  reverter: Function;
  imprimir: Function;
}

interface IFila {
  inserir: Function;
  remover: Function;
  obterPrimeiro: Function;
  estaVazia: Function;
  tamanho: Function;
  clonar: Function;
  imprimir: Function;
}

interface IListaEncadeada {
  adicionar: Function;
  remover: Function;
  inserirNaPosicao: Function;
  removerNaPosicao: Function;
  substituirElementoNaPosicao: Function;
  posicaoDe: Function;
  obterDe: Function;
  imprimir: Function;
  tamanho: Function;
}

// Exemplo de declaração de classe em TypeScript:
// class Pilha implements IPilha { /* sua implementação */ }
// class Fila implements IFila { /* sua implementação */ }
// class ListaEncadeada implements IListaEncadeada { /* sua implementação */ }
```

**Na entrega**, explique por que escolheu os parâmetros e os retornos de cada operação. Procure manter um comportamento consistente para operações parecidas, como `topo` e `obterPrimeiro`, ou tentativas de remover elementos de estruturas vazias.
