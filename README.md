## Preparação do Ambiente

- Visual Studio Code;
- Google Chrome
- Node.js

## Console.log - A primeira coisa que você vai ver

Sempre que quisermos exibir uma mensagem, ou até mesmo debugar parte do código de maneira rápida, podemos usar o método abaixo:

```JavaScript
console.log(mensagem);
console.log("Isso é uma mensagem em texto"); // String
console.log(123.4); // Number
```

[^1]: Note que o conteúdo das mensagens impressas pelo método console.log só serão exibidas no console.

Nessa primeira caixa de código, foram inseridos pequenos comentários, abaixo deixo demonstrado como fazê-los de forma correta:

```JavaScript
// Esse é um comentário de linha

/* Esse é
um comentário
de bloco
console.log(mensagem);
*/
```

Comentários são trechos de texto/código que serão ignorados pela engine do JavaScript.
Utilize-os com sabedoria para deixar seu código mais legível ou fazer anotações para lembrar no futuro.

### Exercício 1

```JavaScript
console.log(
  `Meu nome é ${Jonathan}, e eu estou estudando as ${23} horas e ${45} minutos`
);
```

## JavaScript no Navegador, Node.js e HTML

Para rodarmos código JavaScript, podemos utilizar qualquer navegador, utilizando a função **ferramentas do programador**, no Chrome basta utilizar a tecla f12 para acessá-la.

Podemos também utilizar o console Node.js previamente instalado em nossa máquina, no entanto podem existir algumas funções que não estarão disponíveis no Node.js, como por exemplo o método `alert()`.

### Utilizando JavaScript no seu HTML

Existem duas formas para inserirmos código JavaScript dentro de uma página HTML.

1. **Internamente** utilizando a tag `<script></script>` e inserindo todo o código JavaScript dentro do próprio index.html

2. **Externamente** utilizando o código abaixo que insere uma fonte externa para um arquivo de extensão **_.js_**

```HTML
<script src="js/script.js"></script>
```

#### Localização da tag "script" dentro do index.html

Como o navegador renderiza o HTML com um fluxo padrão de leitura, ou seja, de cima para baixo, se o código JavaScript estiver antes do conteúdo, o navegador precisará interpreta-lo por inteiro antes de seguir com a renderização da página, podendo ocasionar em lentidão no carregamento total da página, por isso, mesmo que seja possível encontrar arquivos HTML estruturados dessa forma, inserir a tag `<script></script>` dentro da tag `<head></head>` não é considerada uma boa prática.
O ideal é inserir a tag `<script></script>` ao final do conteúdo da página, dentro da tag `<body></body>` conforme o exemplo abaixo:

```HTML
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <title>Minha primeira página HTML com JavaScript</title>
  </head>
  <body>
    <script>
      // Seu script deve ficar no final conteúdo da tag body
      console.log("Olá, mundo!");
    </script>
  </body>
</html>
```

## Variáveis

Variável é um conceito presente em todas as linguagens de programação que consiste em salvar um tipo de dado na memória em tempo de execução do código.

No JavaScript podemos declarar variáveis de 2 formas:

```JavaScript
var nomeDaVariavel1 = "dado1";
let nomeDaVariavel2 = "dado2";
```

Declarar variáveis com `var` caiu em desuso e não é considerada uma boa pratica hoje, porém ainda é possível encontrarmos código legado que utilize e essa forma.

Podemos modificar a informação contida na variável a qualquer momento, basta que seja atribuído um novo dado nessa variável, conforme abaixo:

```JavaScript
let nomeDaVariavel2 = "novo Dado"
```

Ainda é possível armazenar dados de uma terceira maneira:

```JavaScript
const nomeDaVariavel4 = "dado imutável"
```

No entanto, conforme tentei deixar claro acima, se trata de uma "variável" constante, pois não é possível altera-la no tempo de execução futuro, e sempre deve ser inicializada.

### Tipos de Dados

Existem diversos tipos de tipos de dados que podem ser armazenados em variáveis, abaixo cito alguns deles:

1. Dados Primitivos

   1. number

      - integers
        Números inteiros.
      - float-point
        Números com casas decimais.
      - infinity
        Valor maior do que JavaScript pode representar.
      - NaN (Not-a-Number)
        Valor numérico que não pode ser calculado ou é indefinido.

   2. string
      Conjunto de caracteres (palavra).

   3. boolean

      - true
      - false

   4. undefined
      A variável foi declarada, mas _não foi inicializada_.
   5. symbol
      Veremos a frente no curso

2. object

   1. Objetos literais
      Lista de propriedades e métodos.
      Exemplo: `const objeto = {nome: 'Jonathan', idade: 31}
   1. null
      A variável _foi inicializada_ **vazia**.
   1. array
      Lista com variáveis.
      Exemplo: `const array = ['Jonathan' 123, true];

3. function
   Bloco de código a ser executado.

### Identificador

O nome das variáveis é chamado de **_identificador_**. A seguir algumas regras para nomear identificadores:

- _Podem_ começar com **letra**, **\_**, ou **$**;
- _Podem_ conter letras e números;
- _Podem_ conter acentos e símbolos;
- _Não podem_ começar com **números**;
- _Não podem_ conter - ou espaços;
- _Não podem_ conter palavras reservadas;
- _Não podem_ ser redeclaradas com `let`.
- _Devem_ possuir identificadores **significativos**.

Ainda sobre nomeação de identificadores, é importante destacar que JavaScript é **_Case-Sensitive_**, ou seja, letras maiúsculas e minúsculas são diferenciadas.
No exemplo abaixo, temos 2 variáveis diferentes:

```JavaScript
let N = "dado";
let n = "dado";
```

Podemos utilizar o método `typeof` para que o JavaScript nos informe qual tipo de dado está contido dentro de uma determinada variável.

```JavaScript
typeof "John"                 // Retorna "string"
typeof 3.14                   // Retorna "number"
typeof NaN                    // Retorna "number"
typeof false                  // Retorna "boolean"
typeof [1,2,3,4]              // Retorna "object"
typeof {name:'John', age:34}  // Retorna "object"
typeof function() {}          // Retorna "function"
typeof undefined              // Retorna "undefined"
typeof null                   // Retorna "object"
```

### Utilizando variáveis

```JavaScript
const primeiroNumero = 5;
const segundoNumero = 10;
const conta = primeiroNumero + segundoNumero; // 15

const nome = "John";
let saldacao = "Olá, meu nome é "
// Concatenação de dados
const apresentacao = saldacao + nome // "Olá, meu nome é Jonathan"

let idade = 31;

// Interpolação de dados
const apresentacaoCompleta = `${saldacao}${nome} tenho ${idade} anos` // "Olá, meu nome é Jonathan tenho 31 anos"
```

1. Concatenação:

   - A concatenação envolve a simples junção de strings usando o operador de adição (+)
   - Ela cria uma nova string combinando as strings originais em ordem.
   - Não permite a inserção direta de valores de variáveis ou expressões em uma string.
     Você precisa garantir que todas as partes a serem combinadas sejam strings.
   - Exemplo de concatenação:
     ```JavaScript
     let nome = "John";
     let sobrenome = "Doe";
     let nomeCompleto = nome + " " + sobrenome; // "John Doe"`
     ```

2. Interpolação:

   - A interpolação de strings é uma forma mais moderna e legível de criar strings compostas, especialmente quando você precisa incluir valores de variáveis ou expressões no meio de uma string.
   - Ela é geralmente realizada usando template literals, que são strings delimitadas por crases (`` ` ``) e permitem a inclusão de expressões JavaScript dentro da string usando `${}`.
   - Exemplo de interpolação:
     ```JavaScript
     let nome = "John";
     let sobrenome = "Doe";
     let nomeCompleto = `${nome} ${sobrenome}`; // "John Doe"
     ```

A principal vantagem da interpolação é que ela torna o código mais legível quando você precisa incorporar valores de variáveis em uma string, pois elimina a necessidade de concatenar manualmente strings e variáveis. Além disso, as template literals também suportam formatação avançada, como quebras de linha e expressões mais complexas, tornando-as uma opção poderosa para criar strings dinamicamente em JavaScript.

#### Exercício 2

```JavaScript
const nome = "John";
const sobrenome = "doe";
let idade = 31;
let peso = 89;
let altura = 1.89;
const imc = peso / (altura * altura);

// concatenação de strings
console.log("Meu nome é " + nome + " " + sobrenome + ", tenho " + idade + " e meu IMC é " + imc);

// Interpolação de strings
console.log( `Meu nome é ${nome} ${sobrenome}, tenho ${idade} e meu IMC é ${imc}`);
```

Note que todas as informações que não mudam (nome, sobrenome, formula imc) foram declaradas como `const` enquanto o restante foi declarado com `let`. Além disso, utilizando a interpolação de strings o código fica mais legível, por isso é assim que iremos utilizar daqui em diante.

## Operadores

### Aritméticos

1. `+` Adição ou Concatenação;
2. `-` Subtração;
3. `*` Multiplicação;
4. `/` Divisão;
5. `**` Potenciação;
6. `%` Resto da divisão (Módulo);
7. `++` Incremento de 1;
8. `--` Decremento de 1;

Operadores aritméticos seguem a mesma ordem de precedência da matemática

### Atribuição

1. `=` Atribui um valor;
2. `=+` Atribui um valor após efetuar uma adição;
3. `=-` Atribui um valor após efetuar uma subtração;
4. `=*` Atribui um valor após efetuar uma multiplicação;
5. `=**` Atribui um valor após efetuar uma potenciação;
6. `%=` Atribui um valor após efetuar o resto da divisão

## Strings

### Principais Métodos para Manipular Strings em JavaScript

1. **`length`**

   - Retorna o comprimento da string.

   `let texto = "Exemplo"; let comprimento = texto.length; // 7`

1. **`charAt(index)`**

   - Retorna o caractere na posição especificada pelo índice.

   ```Javascript
    let texto = 'JavaScript'; let caractere = texto.charAt(2); // "v"
   let texto = 'JavaScript'; let caractere = texto[2]; // "v"
   ```

1. **`slice(start, end)`**

   - Extrai uma parte da string com base nos índices de início e fim (o índice de fim não é inclusivo).

   ```Javascript
    let trecho = texto.slice(0, 5); // 'Mani'
   ```

1. **`indexOf(substring)`** e **`lastIndexOf(substring)`**

   - `indexOf()` retorna o primeiro índice onde a substring é encontrada na string.
   - `lastIndexOf()` retorna o último índice onde a substring é encontrada na string.

   ```Javascript
    let frase = 'JavaScript é incrível!'; let indice = frase.indexOf('é');      // 12 let ultimoIndice = frase.lastIndexOf('é'); // 15
   ```

1. **`split(separator, limit)`**

   - Divide uma string em um array de substrings com base no separador especificado.

   ```Javascript
    let frase = 'Esta é uma frase de exemplo'; let palavras = frase.split(' '); // ['Esta', 'é', 'uma', 'frase', 'de', 'exemplo']
   ```

1. **`startsWith(prefix)`** e **`endsWith(suffix)`**

   - Verifica se a string começa com o prefixo ou termina com o sufixo especificado.

   ```Javascript
    let texto = 'Olá, mundo!'; let comecaComOla = texto.startsWith('Olá');     // true let terminaComMundo = texto.endsWith('mundo!'); // true
   ```

1. **`includes(substring)`**

   - Verifica se a string contém a substring especificada.

   ```Javascript
    let frase = 'JavaScript é incrível!'; let contemIncrivel = frase.includes('incrível'); // true
   ```

1. **`replace(old, new)`**

   - Substitui a primeira ocorrência de uma substring antiga por uma nova.

   ```Javascript
    let texto = 'JavaScript é incrível!'; let novaFrase = texto.replace('incrível', 'fantástico'); // 'JavaScript é fantástico!'
   ```

1. **`toUpperCase()`** e **`toLowerCase()`**

   - Converte a string para maiúsculas ou minúsculas.

   ```Javascript
    let texto = 'Converter TEXTO'; let maiusculas = texto.toUpperCase(); // 'CONVERTER TEXTO' let minusculas = texto.toLowerCase(); // 'converter texto'
   ```

Ainda é possível transformarmos valores em string utilizando o método **`toString()`**

```JavaScript
let numero = 42;
let stringNumero = numero.toString(); // '42'
let array = [1, 2, 3];
let stringArray = array.toString(); // '1,2,3'
let objeto = { nome: 'John', idade: 30 };
let stringObjeto = objeto.toString(); // '[object Object]'`
```

- O método `toString()` é comumente usado para converter objetos em strings.

Esses são alguns dos principais métodos para manipulação de strings em JavaScript. Existem muitos outros métodos e recursos que podem ser úteis dependendo da tarefa que você deseja realizar com strings.

## Numbers

### Principais Métodos para Manipular Numbers em JavaScript

1. **`Number.parseInt(string, radix)`**:

   - Converte uma string em um número inteiro usando a base especificada (radix).

   ```Javascript
    let numero = Number.parseInt('123', 10); // 123
   ```

2. **`Number.parseFloat(string)`**:

   - Converte uma string em um número de ponto flutuante.

   ```Javascript
    let numero = Number.parseFloat('3.14'); // 3.14
   ```

3. **`toFixed(digits)`**:

   - Formata um número com um número específico de casas decimais e retorna uma string.

   ```Javascript
    let numero = 3.14159; let stringFormatada = numero.toFixed(2); // '3.14'
   ```

4. **`isInteger()`**:

   - Verifica se um número é um número inteiro.

   ```Javascript
    let inteiro = 42; let naoInteiro = 3.14; Number.isInteger(inteiro);   // true Number.isInteger(naoInteiro); // false
   ```

5. **`Number.isNaN(value)`**:

   - Verifica se um valor é do tipo NaN (Not-a-Number).

   ```Javascript
    let naoNumero = 'texto'; let ehNaN = Number.isNaN(naoNumero); // false
   ```

### Métodos Matemáticos em `Math`:

O objeto `Math` fornece uma série de métodos matemáticos, como:

- `Math.abs(x)`: Retorna o valor absoluto de `x`.
- `Math.ceil(x)`: Arredonda `x` para o próximo número inteiro maior ou igual.
- `Math.floor(x)`: Arredonda `x` para o próximo número inteiro menor ou igual.
- `Math.round(x)`: Arredonda `x` para o número inteiro mais próximo.
- `Math.max(...args)`: Retorna o maior valor de um conjunto de valores.
- `Math.min(...args)`: Retorna o menor valor de um conjunto de valores.
- `Math.pow(base, expoente)`: Calcula a potência de `base` elevada a `expoente`.
- `Math.sqrt(x)`: Calcula a raiz quadrada de `x`.
- `Math.random()`: Gera um número pseudoaleatório entre 0 (inclusive) e 1 (exclusivo).

### Métodos para Conversão:

- `Number(value)`: Converte um valor em um número.
- `parseInt(string, radix)`: Converte uma string em um número inteiro com uma base especificada.
- `parseFloat(string)`: Converte uma string em um número de ponto flutuante.

### Métodos de Verificação:

- `isNaN(value)`: Verifica se um valor é NaN (Not-a-Number).
- `isFinite(value)`: Verifica se um valor é um número finito (não é Infinity ou -Infinity).

### Métodos de Formatação:

- `toPrecision(precision)`: Formata um número com uma precisão específica e retorna uma string.
- `toExponential(fractionDigits)`: Converte um número em notação exponencial e retorna uma string.

### Constantes Matemáticas em `Math`:

- `Math.PI`: Valor de π (pi).
- `Math.E`: Valor da constante de Euler (e).

Esses são apenas alguns exemplos dos muitos métodos e propriedades relacionados a números disponíveis em JavaScript. A escolha do método a ser usado depende das operações específicas que você deseja realizar em seus números e do formato desejado para os resultados.

### Exercício 3

```HTML
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Exercícios</title>
  </head>

  <body>
    <h1 id="user-number">O seu número é 0</h1>
    <p id="raiz-quadrada"></p>
    <p id="is-integer"></p>
    <p id="round-up"></p>
    <p id="round-down"></p>
    <p id="duas-casas"></p>

    <script>
      let userNumber = Number.parseFloat(window.prompt("Digite um número qualquer: "));
      document.getElementById("user-number").innerHTML = `O seu número é ${userNumber}`;
     
      document.getElementById("raiz-quadrada").innerHTML = `Raiz quadrada: ${userNumber ** (1 / 2)}`;
     
      document.getElementById("is-integer").innerHTML = `${userNumber} é inteiro: ${Number.isInteger(userNumber)}`;
     
      document.getElementById("round-up").innerHTML = `Arrendondado para cima: ${Math.round(userNumber)}`;
     
      document.getElementById("round-down").innerHTML = `Arredondado para baixo: ${Math.floor(userNumber)}`;
     
      document.getElementById("duas-casas").innerHTML = `Com duas casas decimais: ${userNumber.toFixed(2)}`;
    </script>
  </body>
</html>
```

## Arrays (Básico)

Um array é uma estrutura de dados que permite armazenar uma coleção de valores em uma única variável. O ideal é inserir em um array apenas um tipo de variável por uma questão de boa prática.
Abaixo algumas informações básicas sobre arrays:

- **Declaração**: Para criar um array, você pode usar colchetes `[]` e adicionar elementos separados por vírgulas.
  ```JavaScript
  let frutas = ['maçã', 'banana', 'laranja'];
  ```
- **Índices**: Os elementos em um array são acessados usando índices baseados em zero (o primeiro elemento é 0, o segundo é 1, e assim por diante).
  ```JavaScript
  let primeiraFruta = frutas[0]; // 'maçã'
  ```
- **Tamanho**: Você pode verificar o número de elementos em um array usando a propriedade `length`.
  ```JavaScript
  let tamanhoDoArray = frutas.length; // 3
  ```
- **Modificar Elementos**: Você pode modificar elementos em um array atribuindo um novo valor a um índice específico.
  ```JavaScript
  frutas[1] = 'pera'; // Modifica o segundo elemento para 'pera'
  ```

### Métodos

1. **`push(elemento)`**:

   - Adiciona um elemento ao final do array.

2. **`pop()`**:

   - Remove e retorna o último elemento do array.

3. **`shift()`**:

   - Remove e retorna o primeiro elemento do array.

4. **`unshift(elemento)`**:

   - Adiciona um elemento ao início do array.

5. **`splice(início, quantidade, elemento1, elemento2, ...)`**:

   - Altera o conteúdo de um array removendo, substituindo ou adicionando elementos.

6. **`concat(array)`**:

   - Combina dois ou mais arrays em um novo array.

7. **`slice(início, fim)`**:

   - Cria uma cópia superficial (shallow copy) de uma parte do array.

8. **`forEach(função)`**:

   - Executa uma função para cada elemento do array.

Esses métodos são essenciais para adicionar, remover, modificar e percorrer elementos em arrays em JavaScript, facilitando a manipulação de conjuntos de dados de forma eficiente.

**Iteração**

Além disso é possível fazermos percorrer os elementos de um array usando loops, como `for`, `while`, `for...of`, ou métodos de iteração, como `forEach()`.

**Arrays Multidimensionais**: Também é possível criar arrays de arrays para criar estruturas de dados multidimensionais conforme o exemplo abaixo:

`let matriz = [   [1, 2, 3],   [4, 5, 6] ];`

Arrays são uma parte fundamental da linguagem JavaScript e são amplamente utilizados para armazenar e manipular conjuntos de dados. Eles são versáteis e oferecem muitas opções para trabalhar com informações de forma eficaz.

## Funções

As funções são blocos de código reutilizáveis que realizam tarefas específicas. Aqui estão alguns conceitos básicos sobre funções em JavaScript:

- **Declaração de Função**: Você pode declarar uma função usando a palavra-chave `function`, seguida pelo nome da função e um par de parênteses.
  ```JavaScript
  function saudacao() {
  	console.log('Olá, Mundo!');
  }
  ```
- **Chamada de Função**: Para executar uma função, você a chama pelo nome seguido de parênteses.
  ```JavaScript
  saudacao(); // Chama a função saudacao e exibe 'Olá, Mundo!'
  ```
- **Parâmetros**: Funções podem receber parâmetros (valores de entrada) que são usados dentro da função, valores enviados para esses parâmetros são chamados de _argumentos_.
  ```JavaScript
  function saudacao(nome) {
  	console.log(`Olá, ${nome}!`);
  }
  saudacao('Alice'); // Chama a função com o parâmetro 'Alice' e exibe 'Olá, Alice!'
  ```
- **Valor de Retorno**: Funções podem retornar um valor usando a palavra-chave `return`. Isso permite que você obtenha um resultado após a execução da função.
  ```JavaScript
  function soma(a, b) {
    return a + b;
  }
  let resultado = soma(5, 3); // Chama a função e armazena o resultado (8) em 'resultado'
  ```
- **Escopo**: Funções têm escopo, o que significa que as variáveis declaradas dentro de uma função não são visíveis fora dela, a menos que sejam declaradas globalmente.
- **Funções Anônimas**: Funções anônimas são funções sem nome que podem ser atribuídas a variáveis ou usadas como argumentos para outras funções.
  ```JavaScript
  let minhaFuncao = function () {
    console.log("Isso é uma função anônima.");
  };
  ```
- **Arrow Functions**: A partir do ECMAScript 6 (ES6), você pode usar arrow functions para criar funções de forma mais concisa.
  ```JavaScript
  let soma = (a, b) => a + b;
  ```

Funções são uma parte fundamental da programação em JavaScript e são usadas para dividir o código em blocos reutilizáveis, facilitando a organização e a manutenção de programas. Elas permitem que você execute a mesma ação em diferentes partes do código com facilidade, e as funções anônimas e arrow functions são formas modernas e eficientes de criar funções em JavaScript.

## Objetos

Em JavaScript, objetos são estruturas de dados que permitem armazenar coleções de propriedades e métodos. Aqui estão alguns conceitos básicos sobre objetos em JavaScript:

- **Declaração de Objeto**: Você pode declarar um objeto usando chaves `{}` e definir propriedades e métodos dentro dele.

  ```JavaScript
  let pessoa = {
    nome: "Alice",
    idade: 30,

    saudacao: function () {
      console.log("Olá!");
    },
  };
  ```

- **Propriedades**: Propriedades são pares chave-valor que armazenam informações.
  ```JavaScript
  let pessoa = {
    nome: "Alice",
    idade: 30,
  };
  ```
- **Métodos**: Métodos são funções que estão associadas a objetos e podem ser chamadas para realizar ações.

  ```JavaScript
  let pessoa = {
    nome: "Alice",

    saudacao: function () {
      console.log("Olá!");
    },
  };
  ```

- **`this` Dentro de um método**: A palavra-chave `this` refere-se ao próprio objeto ao qual o método pertence. Isso permite que você acesse as propriedades do objeto dentro do método.

  ```JavaScript
  let pessoa = {
    nome: "Alice",

    saudacao: function () {
      console.log(`Olá, meu nome é ${this.nome}!`);
    },
  };
  pessoa.saudacao(); // Chama o método e exibe 'Olá, meu nome é Alice!'
  ```

- **Acesso às Propriedades e Métodos**: Você pode acessar as propriedades e métodos de um objeto usando a notação de ponto (`objeto.propriedade`) ou a notação de colchetes (`objeto['propriedade']`).
  ```JavaScript
  console.log(pessoa.nome); // 'Alice'
  pessoa.saudacao(); // Chama o método saudacao e exibe 'Olá!'
  ```
- **Adição e Modificação de Propriedades**: Você pode adicionar ou modificar propriedades de um objeto após sua criação.
  ```JavaScript
  pessoa.profissao = "Engenheira"; // Adiciona a propriedade 'profissao'
  pessoa.idade = 31; // Modifica a propriedade 'idade'
  ```
- **Objetos Aninhados**: Você pode criar objetos dentro de objetos para estruturar dados complexos.
  ```JavaScript
  let carro = {
    marca: "Toyota",
    modelo: "Camry",
    motor: {
      tipo: "V6",
      potencia: "300hp",
    },
  };
  ```

Objetos são uma parte essencial da linguagem JavaScript e são amplamente usados para organizar, armazenar e manipular dados. Eles são flexíveis e poderosos, permitindo a criação de estruturas de dados complexas e a definição de comportamentos personalizados por meio de métodos.

Crie um resumo explicando um pouco sobre tipos de dados imutáveis (atribuidos de uma variavel para outra por cópia) e tipos de dados mutáveis (atribuidos de uma variavel para outra por referencia), e explique um pouco sobre.
Além disso, explique e exemplifique spread de arrays

## Dados Imutáveis e Mutáveis

Em JavaScript, os tipos de dados podem ser divididos em duas categorias principais: Imutáveis e mutáveis

### Tipos de Dados Imutáveis

- **Imutáveis**: Os tipos de dados imutáveis são aqueles em que o valor não pode ser alterado após a criação da variável. Quando você atribui uma variável a outra, está fazendo uma cópia do valor, não uma referência ao mesmo valor. Os tipos de dados imutáveis incluem números, strings, valores booleanos, null, undefined, e símbolos.

**Exemplo:**

```JavaScript
let nome1 = "Alice";
let nome2 = nome1; // Cria uma cópia de 'Alice'
nome1 = "Bob"; // Altera 'nome1'
console.log(nome1); // 'Bob'
console.log(nome2); // 'Alice' (permanece inalterado)
```

### Tipos de Dados Mutáveis

- **Mutáveis**: Os tipos de dados mutáveis são aqueles em que o valor pode ser alterado após a criação da variável. Quando você atribui uma variável a outra, está fazendo uma referência ao mesmo objeto, não uma cópia do objeto. Os tipos de dados mutáveis incluem objetos e arrays.

**Exemplo:**

```JavaScript
let array1 = [1, 2, 3];
let array2 = array1; // Cria uma referência ao mesmo array
array1.push(4); // Altera 'array1'
console.log(array1); // [1, 2, 3, 4]
console.log(array2); // [1, 2, 3, 4] (também é alterado)
```

Para dados mutáveis, caso seja necessário criar uma cópia em vez de referenciá-los, podemos utilizar o **spread de arrays**.

### Spread de Arrays

O operador de spread (`...`) é usado para criar cópias superficiais (shallow copies) de arrays e objetos em JavaScript. Ele é frequentemente usado para criar novas estruturas de dados que se baseiam em estruturas existentes, garantindo que as originais não sejam afetadas.

#### Exemplo com Arrays:

```JavaScript
let array1 = [1, 2, 3];
let array2 = [...array1]; // Cria uma cópia superficial de 'array1'
array1.push(4); // Altera 'array1', mas não afeta 'array2'
console.log(array1); // [1, 2, 3, 4]
console.log(array2); // [1, 2, 3]
```

O operador de spread desempacota os elementos do array original e cria uma nova array com os mesmos elementos. Isso permite que você crie cópias independentes de arrays e evite efeitos colaterais indesejados.

O spread também pode ser usado para **mesclar** arrays:

```JavaScript
let array1 = [1, 2];
let array2 = [3, 4];
let mergedArray = [...array1, ...array2]; // Mescla os dois arrays
console.log(mergedArray); // [1, 2, 3, 4]
```

Em resumo, tipos de dados imutáveis são copiados por valor, enquanto tipos de dados mutáveis são copiados por referência. O operador de spread (`...`) é uma ferramenta útil para criar cópias de arrays e objetos e para mesclar múltiplos arrays em um único array. Ele é especialmente útil para evitar efeitos colaterais indesejados ao trabalhar com objetos e arrays em JavaScript.

### Exercício 4

```HTML
<!DOCTYPE html>
<html lang="pr-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN"
      crossorigin="anonymous"
    />
    <style>
      body {
        background: goldenrod;
        font-size: 20px;
        font-weight: 600;
      }
    </style>

    <title>Exercício 4</title>
  </head>
  <body>
    <div class="container">
      <form class="form" action="" method="get">
        <label for="nome" class="form-label">Nome:</label>
        <input type="text" class="form-control" id="nome" required />

        <label for="sobrenome" class="form-label">Sobrenome:</label>
        <input type="text" class="form-control" id="sobrenome" required />

        <label for="peso" class="form-label">Peso:</label>
        <input type="number" class="form-control" id="peso" required />

        <label for="altura" class="form-label">Altura em Cm</label>
        <input type="number" class="form-control" id="altura" required />

        <button type="submit" id="submit" class="btn btn-dark">Enviar</button>
      </form>
    </div>

    <div class="container resultado"></div>

    <script>
      function meuEscopo() {
        const form = document.querySelector(".form");
        const pessoas = [];

        function recebeEventoForm(evento) {
          evento.preventDefault();

          const nome = form.querySelector("#nome").value;
          const sobrenome = form.querySelector("#sobrenome").value;
          const peso = form.querySelector("#peso").value;
          const altura = form.querySelector("#altura").value;

          function criaPessoa(nome, sobrenome, peso, altura) {
            return { nome, sobrenome, peso, altura };
          } // Criei uma função construtora;

          pessoas.push(criaPessoa(nome, sobrenome, peso, altura)); //chamei a função construtora dentro do método push
          console.log(pessoas);
        }

        form.addEventListener("submit", recebeEventoForm);
      }
      meuEscopo();
    </script>
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```
