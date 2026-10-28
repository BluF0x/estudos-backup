---
tags:
  - hardware
aliases:
  - cache
creation: 2025-11-13T15:02:00
---
# Overview

Uma memória cache é uma memória intermediaria entre a memória principal (RAM) e registradores. Memórias cache são mais rápidas que as memórias principais, porém são mais caras.

## Tipos de cache 

### N1, N2, e N3
Cache N1 são rápidas, porém pequenas 


## Mapeamento de memória 

Como as memórias cache são menores que a memória principal por questão de custo, é necessário mapear os dados da memória principal para o cache.

### Mapeamento direto 

O mapeamento direto associa cada endereço da memória principal com uma linha no cache, porém como a memória principal é maior que a memória cache, múltiplos elementos são associados a cada linha de cache. Ou seja, a memória principal é agrupada em blocos do tamanho da memória cache, e a posição de cada elemento no bloco é a posição ocupada no cache. 
Para achar a posição de um elemento de memória no cache, é usado a seguinte fórmula:
*posição = endereço do bloco % quantidade de linhas do cache* 

<html>
  <head>
    <title>Two Images Full Width</title>
  </head>
  <body style="margin: 0; padding: 0;">

    <div style="display: flex; width: 100%;">
      <img src="Pasted image 20251113154831.png" alt="Image 1" style="width: 50%; height: 100%; object-fit: cover;">
      <img src="Pasted image 20251113154845.png" alt="Image 2" style="width: 50%; height: 100%; object-fit: cover;">
    </div>

  </body>
</html>

Como múltiplos endereços podem ocupar uma mesma linha de cache, é necessário saber qual bloco está sendo armazenado. Para isso é usada uma ***tag***, que consiste dos bits mais significativos do endereço.

Para verificar se o bloco já foi armazenado no cache, é usado um bit de verificação: 1 significa que há dados, e 0 significa que não há dados.
![[Pasted image 20251113170329.png]]

### Mapeamento associativo


## Cache Blocking 



# Fontes 
[[DEC7123_Modulo_18_Memoria_cache_1.pdf]]
[[DEC7123_Modulo_19_Memoria_cache_2.pdf]]
[[DEC7123_Modulo_20_Memoria_cache_3.pdf]]

https://www.youtube.com/watch?v=r-tiD2MYnWE