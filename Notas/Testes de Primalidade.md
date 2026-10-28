---
tags:
  - software
  - algoritmo
  - matemática
aliases:
creation: 2025-11-05T17:03:00
---
# Visão Geral 

Um teste de primalidade é um algoritmo para verificar se um número é primo. 

# Algoritmos
## Divisão por tentativa
A divisão por tentativa checa todos os números de 2 até $\sqrt{n}$, caso o resto seja 0, o número não é impar. 

***Algoritmo em C:***
```C
bool trialDivision(int n) {
	for (int i = 2; i*i <= n; i++) {
		if (n % i == 0) {
			return false;
		}
	}
	return true;
}
```

---
- [ ] Otimizar código implementando i\*i ⏬ 
***Algoritmo em MIPS-ASM***
```asm
is_prime_simple:
	li $t0, 2 					# i
	li $v0, 1					# resultado padrão é primo	
	bgt $a0, $v0, prime_loop	# if n > 1 ? continue : return 0
	move $v0, $0				# caso n for < 1, n não é primo
prime_loop:	
	beqz $v0, end_prime			# if $t0 >= $a0 || $v0 == 0 { return }
	bge $t0, $a0, end_prime		# se um número não deu resto, n não é primo
	div $t1, $a0, $t0				
	addi $t0, $t0, 1
	mfhi $t2 					# Move o resultado do restante da divisão para $t2
	movz $v0, $t2, $t2			# Move 0 para $v0 caso o restante for 0
	j prime_loop
end_prime: jr $ra

```

### Por que checar até $\sqrt{n}$ ?
Um número composto qualquer pode ser dado pela seguinte equação $n = a \cdot b$. Já que $a = \frac{n}{b}$ ou $\quad b = \frac{n}{a}$, então $a$ e $b$ são inversamente proporcionais, ou seja, quando um aumenta o outro diminui. O ponto de "equilíbrio" entre $a$ e $b$, ou seja, o número máximo que ambos podem alcançar simultaneamente, é a raiz quadrada de $n$, após esse ponto $a$ repete múltiplos de $b$ e vice-versa. 

Para chegar a conclusão que o maior número que $a$ e $b$ podem ocupar simultaneamente podemos levar em conta que: 
$a = b$
$n = a \cdot a$
$n = a²$
$\sqrt{n} = a$

Isso pode ser provado com uma prova por contradição: 
$se$
$a,b > \sqrt{n}$  
$então$
$a \cdot b > \sqrt{n} \cdot \sqrt{n}$
$a \cdot b > n$
Considerando que $n = a \cdot b$, então $a \cdot b > n$ é falso, ou seja, $a$ ou $b$ devem ser menor que a raiz quadrada de $n$.
Como os fatores de um número se espelham, não há necessidade de checar números maiores que a raiz do próprio número para encontrar o número primo.


# Fontes 
GitHub. **Algorithms for Competitive Programming.** 2024. Disponível em: https://cp-algorithms.com/algebra/primality_tests.html. Acesso em: 25 nov. 2025.