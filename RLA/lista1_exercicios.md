# Unifor
**Discuplina** Raciocínio Lógico algorítmico<br>
**Orientador** Prof.Ricardo Carubbi

## Lista 1 de exercícios

### Exercício 3
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um numero: }}
B --> C[/num/]
C --> D{num > 0}
D --N--> E{{O numero deve ser positivo}}
E --> J([FIM])
D --S--> F[resto = num % 2]
F --> G{Resto == 0}
G --N--> H{{Numero Impar}}
G --S--> I{{Numero Par}}
H --> J
I --> J
```

```
ALGORITMO verificar_par_impar
DECLARE num, resto INTEIRO
ESCREVA "Digite um numero: "
LEIA num
SE num > 0 ENTAO
	resto = num % 2
	SE resto == 0 ENTAO
		ESCREVA "Numero Par"
	SENAO
		ESCREVA "Numero Impar"
SENAO
	ESCREVA "O numero deve ser positivo"
FIM
```
