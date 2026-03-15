---
title: "F-strings e input() em Python"
date: 2025-02-04T03:12:24-03:00
draft: false
description: "Como formatar strings de forma moderna com f-strings e como capturar dados do usuário com input()."
tags: ["Python", "programação", "f-strings"]
categories: ["Estudos"]
---

## F-strings em Python

F-strings são a forma mais prática de embutir variáveis dentro de um texto em Python. Para usá-las, basta colocar um `f` antes das aspas e envolver as variáveis em `{}`.

```python
nome = "João"
idade = 25
print(f"O nome do aluno é {nome} e ele tem {idade} anos.")
```

Saída: `O nome do aluno é João e ele tem 25 anos.`

Antes das f-strings, o jeito comum era usar `.format()` ou o operador `%`, que são mais verbosos:

```python
# Com .format()
print("O nome do aluno é {} e ele tem {} anos.".format(nome, idade))

# Com %
print("O nome do aluno é %s e ele tem %d anos." % (nome, idade))
```

As três formas produzem o mesmo resultado, mas a f-string é mais limpa e fácil de ler — especialmente quando você tem muitas variáveis.

Você também pode fazer operações diretamente dentro das chaves:

```python
preco = 49.9
print(f"Total: R$ {preco * 1.1:.2f}")  # Aplica 10% e formata com 2 casas decimais
```

Saída: `Total: R$ 54.89`

---

## Capturando dados com input()

`input()` pausa o programa e espera o usuário digitar algo. Quando o usuário pressiona Enter, o valor digitado é retornado como **string**.

```python
nome = input("Digite seu nome: ")
print(f"Olá, {nome}!")
```

Como o retorno é sempre string, se você precisar de um número, precisa converter explicitamente:

```python
idade = int(input("Digite sua idade: "))
altura = float(input("Digite sua altura: "))
```

- `int()` converte para número inteiro.
- `float()` converte para número decimal.

Se o usuário digitar algo que não pode ser convertido (por exemplo, letras onde se espera um número), o Python vai lançar um erro. Por enquanto, basta saber que isso pode acontecer — tratamento de erros fica para um próximo post.

---

## Resumo

- Use f-strings com `f"texto {variavel}"` para montar strings de forma simples.
- `input()` sempre retorna uma string — converta com `int()` ou `float()` quando precisar de números.