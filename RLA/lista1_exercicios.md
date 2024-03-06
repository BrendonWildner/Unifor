# Unifor
**Discuplina** Raciocínio Lógico algorítmico<br>
**Orientador** Prof.Ricardo Carubbi

## Lista 1 de exercícios

### Exercício 1
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado;

### Fluxograma
```mermaid
flowchart TD
A([INICIAR]) -->B{{Digite a nota 1: }}
B --> C[/nota1/]
C --> D{{Digite a nota 2: }}
D --> E[/nota2/]
%%Usar " " para adicionar simbolos sem interferência
E --> G["media = (nota1 + nota2) / 2"]
G --> H{media >= 7}
H --S--> I{{APROVADO}}
H --N--> J{{REPROVADO}}
```
###Pseudocódigo
```
DECLARE nota1, nota2, media FLUTUANTE
ESCREVER "Digite a nota 1:" 
LEIA nota1
ESCREVER "Digite a nota 2:" 
LEIA nota2
media = (nota1 + nota2 / 2)
SE media >= 7 ENTAO
	ESCREVER("APROVADO")
SENAO
	ESCREVER("REPROVADO")
```
### Exercício 2
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

###Fluxograma
```mermaid
flowchart TD
A([INICIAR]) --> B{{Digite seu salario: }}
B --> D[/salario/]
D --> E{salario <= 500}
E --N--> F[novo_salario = salario + salario * 0.1]
E --S--> G[novo_salario = salario + salario * 0.2]
F --> H{{"Seu novo salario: " + novo_salario}}
G --> H
```
###Pseudocódigo
```
DECLARAR salario, novo_salario FLUTUANTE
ESCREVER "Digite seu salario: "
LEIA salario
SE salario <= 500 ENTAO
	novo_salario = salario + salario * 0.2
	ESCREVER "Seu novo salario: " + novo_salario"
SENAO
	novo_salario = salario + salario * 0.1
	ESCREVER "Seu novo salario: " + novo_salario"
FIM
```

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
###Pseudocódigo
```
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

### Exercício 4
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite sua idade: }}
B --> C[/idade/]
C --> D{{idade >= 18}}
D --N--> F[idade_falta = 18 - idade]
F --> G{{Falta  + idade_falta + anos para tirar CNH.}}
D --S--> E{{Pode tirar CNH}}
G --> H([Fim])
E --> H
```
###Pseudocódigo
```
DECLARAR idade, idade_falta INTEIRO
ESCREVER "Digite sua idade: "
LEIA idade
SE idade >= 18 ENTAO
	ESCREVER "Pode tirar CNH"
SENAO
	idade_falta = 18 - idade
	ESCREVER "Falta " + idade_falta + " anos para tirar CNH"
FIM
```
