## Operadores de Comparação

Os operadores de comparação são utilizados para comparar valores em JavaScript. Eles retornam um valor booleano (verdadeiro ou falso) com base na comparação. Aqui estão os operadores essenciais:

- **Igual (`==`)**
  O operador de igualdade verifica se dois valores são iguais, _realizando coerção_ de tipo se necessário. Isso significa que ele pode considerar dois valores de tipos diferentes como iguais,.

- **Estritamente Igual ( `===` )**
  O operador estritamente igual verifica se dois valores são iguais e têm o mesmo tipo de dado. Ele não realiza coerção de tipo, garantindo que os valores sejam idênticos em valor e tipo, por esse motivo damos prioridade para o uso desse operador

- **Maior que (`>`)**
  O operador maior que verifica se o valor à esquerda é maior que o valor à direita.

- **Maior ou igual a (`>=`)**
  O operador maior ou igual a verifica se o valor à esquerda é maior ou igual ao valor à direita.

- **Menor que (`<`)**
  O operador menor que verifica se o valor à esquerda é menor que o valor à direita.

- **Menor ou igual a (`<=`)**
  O operador menor ou igual a verifica se o valor à esquerda é menor ou igual ao valor à direita.

- **Diferente de (`!=`)**
  O operador diferente de verifica se dois valores não são iguais, _realizando coerção_ de tipo, se necessário.

- **Estritamente Diferente de (`!==`)**
  O operador estritamente diferente de verifica se dois valores não são iguais e têm tipos diferentes.

**_Devemos evitar o máximo o uso de operadores que realizam coerção de tipo_**

## Operadores Lógicos

### Operadores Lógicos Básicos

- `&&` (E Lógico): Retorna verdadeiro se ambas as expressões forem verdadeiras.
- `||` (OU Lógico): Retorna verdadeiro se pelo menos uma das expressões for verdadeira.
- `!` (NÃO Lógico): Inverte o valor de verdade de uma expressão.

### Precedência de Operadores

- `!` possui a maior precedência, seguido por `&&` e `||`.
- Você pode usar parênteses para controlar a ordem de avaliação.

### Avaliação Curta de Circuitos

JavaScript usa a avaliação curta de circuitos, o que significa que, no caso de `&&` e `||`, a segunda expressão pode não ser avaliada se o resultado já for conhecido. Isso pode ser útil para evitar erros.

### Tabelas de Verdade

- É útil entender as tabelas de verdade para operadores lógicos, pois isso ajuda a prever o resultado de expressões complexas.

![[Truth Table AND.png]]

![[Truth Table OR.png]]

Lembre-se de que operadores lógicos são fundamentais para criar lógica condicional em JavaScript, permitindo que você tome decisões com base em diferentes condições. Praticar e entender como esses operadores funcionam é crucial para a programação eficaz em JavaScript.

## Valores Lógicos

Em JavaScript, além dos **valores lógicos literais** `true` e `false`, muitos outros valores podem ser avaliados em contextos de avaliação condicional.

### Valores que podem ser avaliados como `false`

1. `0`: O número zero é considerado `false` em contextos de avaliação condicional.

2. `""` (String vazia): Uma string vazia é considerada `false`.

3. `null`: A ausência de valor, representada por `null`, é avaliada como `false`.

4. `undefined`: Variáveis não inicializadas ou propriedades inexistentes são avaliadas como `false`.

5. `NaN` (Not-a-Number): Valores NaN resultantes de operações matemáticas inválidas são avaliados como `false`.

### Valores que podem ser avaliados como `true`

1. Números diferentes de zero: Qualquer número que não seja zero é avaliado como `true`.

2. Strings não vazias: Qualquer string que contenha caracteres é avaliada como `true`.

3. Objetos: Qualquer objeto, incluindo arrays e funções, é avaliado como `true`.

4. Arrays vazios: Embora um array vazio não contenha elementos, ele é avaliado como `true` porque é um objeto.

5. Funções: As funções são sempre avaliadas como `true`.

6. Qualquer objeto com propriedades: Mesmo que um objeto esteja vazio, se ele tiver pelo menos uma propriedade, será avaliado como `true`.
