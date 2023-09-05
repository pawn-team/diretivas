# Diretiva Static e o seu uso:

Neste tutorial, vamos aprender sobre a diretiva `static` na linguagem Pawn, que é usada no SA-MP (San Andreas Multiplayer). A diretiva `static` é usada para criar variáveis e funções com algumas características especiais. Vamos explorar os principais pontos sobre o uso da diretiva `static`.

### O que é a diretiva `static`?

A diretiva `static` é usada para criar variáveis e funções que têm algumas propriedades especiais. Quando uma variável ou função é declarada como `static`, ela tem as seguintes características:

1. **Inicialização única**: Uma variável `static` é criada e inicializada apenas uma vez, mantendo seu valor inicial e endereço inicial ao longo do programa. Isso significa que, apenas quando você atribuir um novo valor à variável, ela manterá o mesmo endereço, porém valor final diferente.

2. **Escopo local**: A diretiva `static` deve ser usada no escopo local, substituindo as variáveis declaradas com `new`. Ela não deve ser usada no escopo global, a menos que você queira tornar uma função ou variavel como privada, que só poderá ser usada no arquivo em que foi declarada.

### Exemplos de uso da diretiva `static`

Vamos ver alguns exemplos de como usar a diretiva `static`:

1. **Variável estática**:
```pawn
main() {
	static myvar = 5;
	printf("Valor de myvar: %d", myvar);
}
```
Resultado: Valor de myvar: 5

2. **Variável estática em um loop**:
```pawn
main() {
	static i;
	for(i = 0; i < 10; i++) {
		static j = 10;
		printf("Valor de i: %d\nValor de j: %d\n", i, j--);
	}
}
```
Resultado:
Valor de i: 0
Valor de j: 10
Valor de i: 1
Valor de j: 9
...
Valor de i: 9
Valor de j: 1

3. **Função estática**:
```pawn
static stock Somar(a, b) {
	return (a + b);
}

#include "file2.pwn"
```
```pawn
// file2.pwn

main() {
	return Somar(5, 5);
}
```
Resultado: erro, função Somar é privada, só pode ser usada no arquivo em que foi declarada

### Dicas importantes sobre o uso da diretiva `static`

- A diretiva `static` é usada para criar variáveis e funções com propriedades especiais.
- Ela deve ser usada no escopo local, substituindo as variáveis declaradas com `new`.
- Evite usar `static` no escopo global, a menos que você queira tornar uma função ou variável privada.
- Lembre-se de que uma variável `static` só pode ser inicializada uma vez. Para alterar seu valor, atribua um novo valor a ela.

Espero que este tutorial tenha ajudado você a entender a diretiva `static` na linguagem Pawn.