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
[^1]:Note que o conteúdo das mensagens impressas pelo método console.log só serão exibidas no console.

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
#### Exercício 1

Utilizando o método acima, imprima no console uma mensagem com seu nome e a hora que você está estudando:

<details>
<summary>Alerta de spoiler</summary>

```JavaScript
console.log(
  `Meu nome é ${Jonathan}, e eu estou estudando as ${23} horas e ${45} minutos`
);
```

</details>

## Navegador, Node.js e HTML
Para rodarmos código JavaScript, podemos utilizar qualquer navegador, utilizando a função **ferramentas do programador**, no Chrome basta utilizar a tecla f12 para acessá-la.

Podemos também utilizar o console Node.js previamente instalado em nossa máquina, no entanto podem existir algumas funções que não estarão disponíveis no Node.js, como por exemplo o método `alert()`.
#### Utilizando JavaScript no seu HTML

Existem duas formas para inserirmos código JavaScript dentro de uma página HTML.

1. **Internamente** utilizando a tag `<script></script>` e inserindo todo o código JavaScript dentro do próprio index.html

2. **Externamente** utilizando o código abaixo que insere uma fonte externa para um arquivo de extensão ***.js***
```HTML
<script src="js/script.js"></script>
```

##### Localização da tag "script" dentro do index.html

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
#### Tipos de Dados

Existem diversos tipos de tipos de dados que podem ser armazenados em variáveis, abaixo cito alguns deles:

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

5. object
	- Objetos literais
		Lista de propriedades e métodos. Ex.: {nome: 'Jonathan', idade: 31}
	- null
		A variável _foi inicializada_ **vazia**.
	- array
		Lista de variáveis. 
		Exemplo: 
		```JavaScript
		const estudante = ['Jonathan' 123, true];
		```

6. function
	Bloco de código a ser executado.

##### Identificador

O nome das variáveis é chamado de **_identificador_**.  A seguir algumas regras para nomear identificadores:

- _Podem_ começar com **letra**, **\_**, ou **$**;
- _Podem_ conter letras e números;
- _Podem_ conter acentos e símbolos;
- _Não podem_ começar com **números**;
- _Não podem_ conter - ou espaços;
- _Não podem_ conter palavras reservadas;
- _Não podem_ ser redeclaradas com `let`.
- _Devem_ possuir identificadores **significativos**.

Ainda sobre nomeação de identificadores, é importante destacar que JavaScript é ***Case-Sensitive***, ou seja, letras maiúsculas e minúsculas são diferenciadas.
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
        ```javascript
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

