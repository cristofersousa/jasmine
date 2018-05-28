## Expectations

- Verificações servem para validar um resultado de um teste;
- Jasmine possui uma função global JavaScript chamada `expect`, que recebe um parâmetro como argumento, que ẽ o resultado a ser verificado.
- O `expect` deve ser utilizado em conjunto com uma comparação (matcher),
que conterá o valor a ser comparado.
- Uma Spec poderã conter uma ou mais verificações
-  Uma boa prática é sempre manter as verificações no final da função.


```
// teste com sucesso
describe ('Expect', function() {
    it('Deve garantir que 1 + 1 é 2 ', function() {
        expect(1+1).toBe(2);
    });
});


//teste com falha
describe ('Expect', function() {
    it('Deve garantir que 1 + 1 é 2 ', function() {
        expect(1+1).toBe(2);
    });
});

```
