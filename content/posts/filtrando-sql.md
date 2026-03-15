---
title: "SQL: Filtrando Dados com WHERE, AND, OR e IN"
date: 2025-02-03T15:00:00-03:00
draft: false
description: "Aprenda a filtrar resultados em consultas SQL usando WHERE, operadores lógicos e padrões de busca."
tags: ["SQL"]
categories: ["Estudos"]
TocOpen: true
---

## Filtrando dados com WHERE

Na maioria das situações, você não quer todos os dados de uma tabela — quer apenas os que atendem a alguma condição. Para isso existe o `WHERE`.

```sql
SELECT name, age
FROM employees
WHERE age > 30;
```

Esse exemplo retorna apenas os funcionários com mais de 30 anos. Simples assim.

---

## Operadores de comparação

Dentro do `WHERE`, você pode usar os operadores abaixo para comparar valores:

| Operador | Significado |
|---|---|
| `=` | igual a |
| `<>` ou `!=` | diferente de |
| `>` | maior que |
| `<` | menor que |
| `>=` | maior ou igual |
| `<=` | menor ou igual |

### Excluindo um valor específico

Quando você quer tudo, exceto um valor:

```sql
SELECT * FROM STATION_DATA
WHERE year != 2010;
```

`!=` e `<>` fazem a mesma coisa — ambos significam "diferente de".

### Selecionando um intervalo com BETWEEN

Para buscar registros dentro de um range de valores, use `BETWEEN`:

```sql
SELECT * FROM STATION_DATA
WHERE year BETWEEN 2005 AND 2010;
```

Retorna todos os registros de 2005 até 2010, **incluindo os extremos**.

### Buscando por padrão de texto com LIKE

Quando você sabe apenas parte do valor que está procurando, use `LIKE`:

```sql
SELECT * FROM customers WHERE name LIKE 'J%';
```

Retorna todos os clientes cujo nome começa com "J". Os curingas funcionam assim:

- `%` — substitui qualquer sequência de caracteres (inclusive nenhum).
- `_` — substitui exatamente um caractere.

Então `LIKE 'J_n%'` encontra "Jon", "Jan", mas não "John" (quatro letras antes do padrão não bate).

---

## Combinando condições

### AND — todas as condições precisam ser verdadeiras

```sql
SELECT * FROM STATION_DATA
WHERE year >= 2005 AND year <= 2010;
```

Só retorna registros onde o ano é 2005, 2006, 2007, 2008, 2009 ou 2010.

Se quiser excluir os extremos:

```sql
SELECT * FROM STATION_DATA
WHERE year > 2005 AND year < 2010;
```

Agora retorna apenas 2006, 2007, 2008 e 2009.

### OR — pelo menos uma condição precisa ser verdadeira

```sql
SELECT * FROM STATION_DATA
WHERE year = 2005 OR year = 2010;
```

Retorna os registros do ano 2005 e do ano 2010, ignorando os outros anos.

### IN — checando contra uma lista

Quando você tem vários valores para comparar, `IN` é mais limpo do que encadear vários `OR`:

```sql
SELECT * FROM orders WHERE status IN ('Completed', 'Pending');
```

Equivalente a `status = 'Completed' OR status = 'Pending'`, mas mais legível — especialmente quando a lista tem muitos itens.

---

## Resumo rápido

- `WHERE` filtra os registros retornados pela consulta.
- `BETWEEN` seleciona intervalos (incluindo os extremos).
- `LIKE` busca por padrões em textos.
- `AND` exige que todas as condições sejam verdadeiras.
- `OR` aceita qualquer condição verdadeira.
- `IN` compara contra uma lista de valores.