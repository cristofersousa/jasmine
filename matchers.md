## Matchers


- Matchers(Comparações) são funções que retornam um valor booleano para ser verificado através de uma expectation(verificação)
- O Jasmine contém uma série de matchers implementados por padrão.
- É possível criar seu próprio matcher;
- Todo matcher pode ser negado através da palavra chave `not`, inserida entre uma expectation e um matcher.

#### Matchers existentes no Jasmine.

Temos 13 Matchers mas caso ache necessário ainda assim poderá criar o seu próprio Matcher.

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


## toBe

- Realiza a comparação com operador `====`, que compara o valor e também o tipo do objeto;
- Deve ser utilizado para comparar valores de forma mais efetiva pelo fato de também verificar o tipo do objeto;

```
describe('Testando o toBe', function() {
  var foo = true;
  var copyFoo = foo;
  var bar = "true";

  var obj1 = {
    valor: foo,  
  };

  var obj2 = {
    valor: foo,
  };

  it('deve validar o uso do toBe', function(){
    expect(foo).toBe(true);
    expect(CopyFoo).toBe(copyFoo);
    expect();
    expect();
    expect();
  })




});




```
