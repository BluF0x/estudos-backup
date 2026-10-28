---
tags:
  - algoritmo
  - hardware
  - cache
aliases:
creation:
---
# Overview
***Cache Blocking*** é uma técnica de optimização de matrizes grandes ou que requerem acesso por coluna, aproveitando a localidade espacial e temporal de um cache.

A memória cache lê dados da RAM em blocos, e não bytes individuais, isso aumenta o *throughput* dos dados. Ao ler um *array* de mais de uma dimensão, os dados são armazenados na cache em sequência: ```a[n][1]: a[0][0], a[0][1], a[1][0], a[1][1]... ...a[n][1]```. Quando o *array* é acessado por linhas, os dados são acessados sequencialmente, aproveitando do principio de localidade espacial.

cache vazio -> itera o array -> cache miss -> cache lê e armazena a memória -> itera o array -> cache hit até o próximo miss

Porém quando um *array* é acessado por colunas o cache pula os bytes subsequentes, ocasionando no desperdício do resto da *cache line*. 




# Fontes 