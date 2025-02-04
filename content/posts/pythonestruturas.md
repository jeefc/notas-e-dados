---
title: "Estruturas de Controle em Python"
date: '2025-02-04T00:18:49-03:00'
draft: false
description: "Um guia prático sobre estruturas de controle em Python: condicionais, loops e boas práticas."
tags: ["Python", "programação", "estruturas de controle"]
categories: ["Estudos"]
---

## Estruturas de Controle em Python

As **estruturas de controle** em Python permitem controlar o fluxo de execução do programa com base em **condições** e **repetições**. Neste post, veremos os principais conceitos com exemplos práticos.

---

## 📌 Comentários em Python  

Comentários ajudam na legibilidade do código e são ignorados pelo interpretador.

- Comentários de **linha única** usam `#`:
```python
# Isso é um comentário
print("Olá, mundo!")  # Comentário no final da linha
```

- Comentários de **múltiplas linhas** usam `'''` ou `"""`:
```python
'''
Este é um comentário de múltiplas linhas.
Ele pode ser usado para documentar o código.
'''
```

---

## ⚡ Estruturas Condicionais

### 🛠️ `if`: Estrutura de Seleção Simples  

Usamos `if` para executar um bloco de código apenas se uma condição for verdadeira.

```python
valor = float(input("Entre com um valor: "))
if valor > 0:
    print(valor, "é maior do que zero.")
```

### 🔄 `if-else`: Estrutura de Seleção com Dois Ramos  

O `else` permite executar um código alternativo quando a condição do `if` não for atendida.

```python
valor = float(input("Entre com um valor: "))
if valor > 0:
    print(valor, "é maior do que zero.")
else:
    print(valor, "é menor ou igual a zero.")
```

### 🔗 `if-elif-else`: Estrutura de Seleção com Múltiplos Ramos  

Se tivermos mais de duas possibilidades, podemos usar `elif`:

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

### 🔍 Condições Compostas  

Podemos combinar condições com `and`, `or` e intervalos:

```python
if 10 <= valor <= 20:
    print(valor, "está dentro do intervalo [10,20].")

if (valor < 0) or (valor > 30):
    print(valor, "está fora do intervalo [0,30].")
```

---

## 🔄 Estruturas de Repetição

### 🔁 `while`: Repetição Indefinida  

Usamos `while` quando **não sabemos quantas vezes** a repetição deve ocorrer.

```python
indice = 1
while indice <= 10:
    print(indice, end=' ')
    indice += 1
print()  # Quebra de linha
```

Exemplo: **Cálculo de fatorial usando `while`**

```python
num = int(input('Digite um número inteiro positivo: '))
i = 1
fat = 1
while i <= num:
    fat *= i
    i += 1
print('O fatorial de', num, '=', fat)
```

### 🔄 `for`: Repetição Definida  

Usamos `for` quando **sabemos quantas vezes** queremos repetir algo.

```python
for i in range(1, 11):  
    print(i, end=' ')  # Imprime números de 1 a 10
print()
```

#### 🧮 Criando Listas com `range()`

A função `range()` gera sequências numéricas:

```python
print(list(range(5)))          # [0, 1, 2, 3, 4]
print(list(range(8, 13)))      # [8, 9, 10, 11, 12]
print(list(range(1, 30, 5)))   # [1, 6, 11, 16, 21, 26]
print(list(range(5, -14, -3))) # [5, 2, -1, -4, -7, -10, -13]
```

Exemplo: **Cálculo de fatorial usando `for`**

```python
num = int(input('Digite um número inteiro positivo: '))
fat = 1
for i in range(1, num + 1):
    fat *= i
print('O fatorial de', num, '=', fat)
```

---

## 🎯 Conclusão  

As **estruturas de controle** são fundamentais para construir programas dinâmicos e eficientes. Neste post, cobrimos:

✅ Condicionais: `if`, `if-else`, `if-elif-else`  
✅ Laços de repetição: `while` e `for`  
✅ Função `range()` para gerar sequências  

---