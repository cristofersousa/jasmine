![](https://camo.githubusercontent.com/d3afdfc8b8075b9daf5109c4af7b8b07ab2d7c04/68747470733a2f2f7261776769746875622e636f6d2f6a61736d696e652f6a61736d696e652f6d61737465722f696d616765732f6a61736d696e652d686f72697a6f6e74616c2e737667)

# Testes Unitários com JavaScript 

*[via  @cristofersousa](https://twitter.com/cristofersousa)*

> Proposta desse repositório é auxiliar quem está iniciando no universo de testes front-end adotando as biblioteca **Jasmine** e **Karma**.

Minha proposta com esse guia é fazer um estudo empírico com exemplos e exercícios guiados,
detalhando todos os recursos que a lib oferece para fazermos
testes unitários engloobando a importância de usarmos funções puras, para facilitar a adesão do TDD. 


- [Documentação Oficial](https://jasmine.github.io/)
- [Repositório Oficial](https://github.com/jasmine/jasmine)

## Sumário

- [Suites](#suites)
- [Specs](#specs)
- Expectations
- Matchers
- toBe
- toEqual
- toMatch
- toBeDefined
- toBeUndefined
- toBeNull
- toBeTruthy
- toBeFalsy
- toContain
- toBeLessThan
- toBeGreaterThan
- toThrow
- toThrowError
- Falha manual (Fail)
- afterEach
- beforeEach
- beforeAll
- afterEach
- aninhando Suites
- desabilitando Suites
- desabilitando testes
- Spies
- spyOn
- toHaveBeenCalled
- toHaveBeenCalleTimes
- toHaveBeenCalledWith
- and.callThrough
- and.returnValue
- and.returnValues
- and.callFak
- and.throwError
- calls.any
- and.callFake
- calls.count- calls.argsFor
- calls.allArgs
- calls.all
- calls.mostRecent
- calls.first
- calls.reset
- createSpy
- createSpyObj
- Objeto 'jasmine'
- jasmine.any
- jasmine.anything
- jasmine.objectContaining
- jasmine.arrayContaining
- jasmine.stringMatching
- Jasmine Clock


 





## Suites

- Suites de testes servem para definir o escopo do que será testado.
- Uma aplicação é composta por diversas `suítes` de testes.
- No Jasmine, a suíte é uma função global JavaScript chamada `describe`
que possui sempre dois parâmetros, que seriam sua descrição e os testes(specs).

**Ex:** 
Vamos supor que estou fazendo um teste de um programa que deverá
fazer uma operação de soma, ele deve validar se o retorno da minha 
função realmente é a soma do parametroA + parametroB.



```
//es5

describe("Operação de Adição", function() {
  it("Eu espero que essa operação faça uma soma", function() {
    expect(Calculator.sum(1,1)).toBe(2);
  });
}

```


```
//es6

describe("Operação de Adição", () => {
  it("Eu espero que essa operação faça uma soma", () => {
    expect(Calculator.sum(1,1)).toBe(2);
  });
}

```


## Specs

- Specs são os testes que validam uma suíte de testes
- Assim como as suítes, ela é uma função global JavaScript chamada `it`, que contém:
  - Dois parâmetros; 
  - Uma descrição;
  - Uma função.
- Dentro do segundo parâmetro, é onde adicionamos as verificações (expectations)
- Podemos adicionar quantas Specs desejarmos dentro da nossa suíte.

> Exemplo:  Vamos fazer um teste, crie uma function que simule operações algébricas. 

    - a. Ela tem que fazer uma operação de divisão;
    - b. Se na operação de divisão o valor não for maior que zero retornar `error`;
    
    function calculator(a,b) {
      if ( b == 0 ) {
        throw new Error('Parameter b must be greater than 0(zero).');
    }

    return (a / b) ;
    }


```
//nosso teste com es5

-- apenas com uma suíte
describe("Operação de Adição", function() {
  it("Eu espero que essa operação faça uma divisão com retorno positivo", function() {
    expect(calculator(25,5)).toBe(5);
  });
}

-- com várias suítes
describe("Operação de Divisão", function() {
  it("Eu espero que essa operação faça uma divisão com retorno positivo", function() {
    expect(Calculator.divide(25,5)).toBe(5);
  });
  it("Eu espero que essa operação retorne null or undefined", function() {
    expect(Calculator.divide(9,0)).toEqual('Parameter b must be greater than 0(zero).');
  });
}

```


```
//es6

describe("Operação de Adição", () => {
  it("Eu espero que essa operação faça uma soma", () => {
    expect(Calculator.sum(1,9)).toBe(10);
  });
}

```
