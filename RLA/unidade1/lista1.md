# UNIFOR
**Nome**: Nome do estudante <br>
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 (1 ponto)
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma (0,25 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número:}}
B --> C[\numero\]
C --> D{numero >= 0}
D --FALSE--> E[O número não é positivo!]
D --TRUE--> F[resto = numero % 2]
E --> Z([FIM])
F --> G{resto == 0}
G --FALSE--> H{{O número é impar!}}
G --TRUE--> I{{O número é par!}}
H --> Z
I --> Z
```

#### Pseudocódigo (0,5 ponto)
```
1  ALGORTIMO verifica_par_impar
2  DECLARE numero, resto: INTEIRO
3  ESCREVA "Digite um número: "
4  INICIO
4  LEIA numero
5  SE numero >= 0 ENTAO                  // verifica se o inteiro é positivo
6    resto = numero % 2                 // calcula o resto da divisão por 2
7    SE resto == 0 ENTAO                // verifica se o resto é igual a zero
8      ESCREVA "O número é par!"
9    SENAO
10     ESCREVA "O número é impar!"
11   FIM_SE
11  SENAO                                // caso inteiro for negativo (condição linha 5)
12    ESCREVA "O número deve ser postivo!"
13  FIM_SE
13 FIM
```

#### Teste de mesa (0,25 ponto)
| numero | numero >= 0 | resto | resto == 0 | Saída |
| -- | -- | -- | -- | -- | 
| -1 | F |   |   | "O número deve ser postivo!" |
| 0  | V | 0 | V | "O número é par!" |
| 13 | V | 1 | F | "O número é impar!" |
| 30 | V | 0 | V | "O número é par!" |

## Exercício 02 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. 
Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIAR]) --> B{{Digite seu salario: }}
B --> D[/salario/]
D --> E{salario <= 500}
E --N--> F[novo_salario = salario + salario * 0.1]
E --S--> G[novo_salario = salario + salario * 0.2]
F --> H{{'Seu novo salario: ', novo_salario}}
G --> H
```

#### Pseudocódigo (1.0 ponto)

```
Algoritmo ContaAprovacoes
DECLARAR salario, novo_salario: REAL
ESCREVER "Digite seu salario: "
LEIA salario
SE salario <= 500 ENTAO
	novo_salario = salario + salario * 0.2
	ESCREVER "Seu novo salario: R$", novo_salario
SENAO
	novo_salario = salario + salario * 0.1
	ESCREVER "Seu novo salario: R$", novo_salario
FIM
```

#### Teste de mesa (1.0 ponto)

|Entrada|Saída| 
|      --      |      --      |
|750|Seu novo salario: R$825,00|
|400|Seu novo salario: R$480,00|
|500|Seu novo salario: R$600,00|

## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

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

#### Pseudocódigo (1 ponto)

```
Algoritmo ContaAprovacoes
DECLARE nota1, nota2, media: REAL
ESCREVER "Digite a nota 1:" 
LEIA nota1
ESCREVER "Digite a nota 2:" 
LEIA nota2
media = (nota1 + nota2) / 2
SE media >= 7 ENTAO
	ESCREVER("APROVADO")
SENAO
	ESCREVER("REPROVADO")
```

#### Teste de mesa (1 ponto)

|Nota1|Nota2|Saída|
|  -  |  -  |  -  | 
| 5 | 8.5 |REPROVADO|
|8|9.3|APROVADO|
|10|5.5|APROVADO|

## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite sua idade: }}
B --> C[/idade/]
C --> D[idade >= 18]
D --N--> F[idade_falta = 18 - idade]
F --> G{{'Falta', idade_falta, 'anos para tirar CNH.'}}
D --S--> E{{Pode tirar CNH}}
G --> H([Fim])
E --> H
```

#### Pseudocódigo (1.0 ponto)

```
Algoritmo ContaAprovacoes
DECLARAR idade, idade_falta: INTEIRO
ESCREVER "Digite sua idade: "
LEIA idade
SE idade >= 18 ENTAO
	ESCREVER "Pode tirar CNH"
SENAO
	idade_falta = 18 - idade
	ESCREVER "Falta ", idade_falta, " anos para tirar CNH"
FIM
```

#### Teste de mesa (1.0 ponto)

| Entrada | Saída |
|      --      |      --      | 
| 20     | Pode tirar CNH      |
| 14   |Falta 4 anos para tirar CNH|
|17|Falta 1 anos para tirar CNH|
