---
title: "Estruturas de Controle em Python"
date: '2025-02-04T00:18:49-03:00'
draft: false
description: "Como usar condicionais e loops em Python para controlar o fluxo do seu programa."
tags: ["python", "programação"]
categories: ["Estudos"]
TocOpen: true
---

## Estruturas de Controle em Python

Estruturas de controle definem o caminho que o programa vai percorrer: se ele vai executar um bloco de código ou não, e quantas vezes vai repetir uma operação. Em Python, isso é feito com condicionais e loops.

---

## Comentários

Antes de entrar nos exemplos, vale lembrar: comentários são ignorados pelo Python e servem para explicar o código.

```python
# Isso é um comentário de linha única

'''
Isso é um comentário
de múltiplas linhas.
'''
```

---

## Condicionais

### if

Executa um bloco de código só se a condição for verdadeira.

```python
valor = float(input("Entre com um valor: "))
if valor > 0:
    print(valor, "é maior do que zero.")
```

Se `valor` for menor ou igual a zero, nada acontece.

### if / else

Adiciona um caminho alternativo caso a condição seja falsa.

```python
valor = float(input("Entre com um valor: "))
if valor > 0:
    print(valor, "é maior do que zero.")
else:
    print(valor, "é menor ou igual a zero.")
```

### if / elif / else

Quando há mais de duas possibilidades, use `elif` para checar condições adicionais:

```python
nota = float(input("Digite sua nota: "))

if nota >= 9:
    print("Aprovado com distinção!")
elif nota >= 7:
    print("Aprovado")
elif nota >= 5:
    print("Recuperação")
else:
    print("Reprovado")
```

O Python testa as condições de cima para baixo e para quando encontra a primeira verdadeira.

### Condições compostas

Você pode combinar condições com `and` e `or`:

```python
if 10 <= valor <= 20:
    print(valor, "está dentro do intervalo [10, 20].")

if valor < 0 or valor > 30:
    print(valor, "está fora do intervalo [0, 30].")
```

---

## Loops

### while — repete enquanto a condição for verdadeira

Use `while` quando não sabe com antecedência quantas vezes vai repetir.

```python
indice = 1
while indice <= 10:
    print(indice, end=' ')
    indice += 1
print()
```

Saída: `1 2 3 4 5 6 7 8 9 10`

Cuidado: se a condição nunca se tornar falsa, o loop roda para sempre. Sempre garanta que algo dentro do loop vai mudar o estado da condição.

**Exemplo prático — fatorial com while:**

```python
num = int(input('Digite um número inteiro positivo: '))
i = 1
fat = 1
while i <= num:
    fat *= i
    i += 1
print('O fatorial de', num, '=', fat)
```

### for — repete um número definido de vezes

Use `for` quando sabe quantas iterações quer fazer, ou quando quer percorrer uma sequência.

```python
for i in range(1, 11):
    print(i, end=' ')
print()
```

Saída: `1 2 3 4 5 6 7 8 9 10`

### range()

`range()` gera sequências numéricas. Ele aceita até três argumentos: `range(início, fim, passo)`.

```python
range(5)           # 0, 1, 2, 3, 4
range(8, 13)       # 8, 9, 10, 11, 12
range(1, 30, 5)    # 1, 6, 11, 16, 21, 26
range(5, -14, -3)  # 5, 2, -1, -4, -7, -10, -13
```

O valor de `fim` nunca é incluído. Passo negativo percorre a sequência de trás para frente.

**Exemplo prático — fatorial com for:**

```python
num = int(input('Digite um número inteiro positivo: '))
fat = 1
for i in range(1, num + 1):
    fat *= i
print('O fatorial de', num, '=', fat)
```

---

## Resumo

| Estrutura | Quando usar |
|---|---|
| `if` | Executar algo apenas se uma condição for verdadeira |
| `if/else` | Dois caminhos possíveis |
| `if/elif/else` | Três ou mais caminhos possíveis |
| `while` | Repetir enquanto uma condição for verdadeira |
| `for` | Repetir um número definido de vezes ou percorrer uma sequência |