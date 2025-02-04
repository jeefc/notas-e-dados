---
title: "SQL: Filtrando Dados com WHERE, AND, OR e IN"
date: 2025-02-03T15:00:00-03:00
draft: false
description: "Entenda como aplicar filtros em consultas SQL usando WHERE, operadores lógicos e padrões de busca."
tags: ["SQL"]
categories: ["Estudos"]
---

## SQL: Filtrando Dados com WHERE, AND, OR e IN  

Ao trabalhar com bancos de dados, muitas vezes precisamos recuperar apenas um subconjunto de informações. Para isso, utilizamos o **comando `WHERE`**, que permite definir condições dentro de uma consulta `SELECT`.  

### 🔍 Usando `WHERE` para Filtrar Resultados  

O comando `WHERE` é usado para especificar quais registros devem ser retornados com base em uma condição.  

```sql
SELECT name, age
FROM employees
WHERE age > 30;
```

Esse comando retorna todos os funcionários com idade superior a 30 anos.  

### ⚡ Operadores Comuns  

Os operadores mais usados em `WHERE` são:  

- **`=`, `>`, `<`, `>=`, `<=`, `<>`**: Para comparações básicas.  

#### ❌ Operador de negação  

Para excluir um valor específico, podemos usar `!=` ou `<>`:

```sql
SELECT * FROM STATION_DATA
WHERE year != 2010;
```
Ou, de forma equivalente:

```sql
SELECT * FROM STATION_DATA
WHERE year <> 2010;
```

Ambas as consultas retornam todos os registros **exceto** aqueles onde o ano é 2010.  

#### 📅 `BETWEEN`: Selecionando Intervalos  

Se precisarmos buscar registros dentro de um intervalo de valores, podemos usar `BETWEEN`:

```sql
SELECT * FROM STATION_DATA
WHERE year BETWEEN 2005 AND 2010;
```

Essa consulta retorna todos os registros entre os anos **2005 e 2010**, incluindo ambos.  

#### 🔎 `LIKE`: Buscando Padrões  

Quando queremos encontrar registros com base em padrões de texto, usamos `LIKE`.  

```sql
SELECT * FROM customers WHERE name LIKE 'J%';
```

Nesse caso, a consulta retorna **todos os clientes cujo nome começa com "J"**.  

- `%` representa **qualquer sequência de caracteres**.  
- `_` representa **um único caractere**.  

Por exemplo, `LIKE 'J_n%'` retornaria nomes como **"John"**, mas não **"Jordan"**.  

---

## 🎯 Combinando Condições: `AND`, `OR` e `IN`  

### ✅ `IN`: Comparação com uma Lista de Valores  

Se quisermos verificar se um valor pertence a um conjunto específico, podemos usar `IN`:

```sql
SELECT * FROM orders WHERE status IN ('Completed', 'Pending');
```

Essa consulta retorna todos os pedidos que estão com status **"Completed"** ou **"Pending"**.  

### 🔗 `AND`: Múltiplos Critérios  

O operador `AND` exige que **todas** as condições sejam verdadeiras para que um registro seja retornado.  

```sql
SELECT * FROM STATION_DATA
WHERE year >= 2005 AND year <= 2010;
```

Se quisermos **excluir** os anos 2005 e 2010, podemos remover os `=`:

```sql
SELECT * FROM STATION_DATA
WHERE year > 2005 AND year < 2010;
```

Agora, apenas os anos **2006, 2007, 2008 e 2009** serão retornados.  

### 🔀 `OR`: Qualquer Critério Aceito  

Diferente do `AND`, o `OR` retorna registros se **pelo menos uma** das condições for verdadeira.  

```sql
SELECT * FROM STATION_DATA
WHERE year = 2005 OR year = 2010;
```

Aqui, a consulta retornará **todos os registros do ano 2005 e do ano 2010**.  

---

## 🔥 Conclusão  

Dominar o uso do `WHERE` e seus operadores auxilia na **extração precisa de dados** em bancos de dados SQL.  

- Use `BETWEEN` para intervalos.  
- Utilize `LIKE` para buscas por padrões.  
- Combine `AND`, `OR` e `IN` para filtros mais poderosos.  

Saber estruturar bem essas consultas pode melhorar o desempenho e a eficiência ao trabalhar com grandes volumes de dados.