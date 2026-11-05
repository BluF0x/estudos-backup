---
tags:
  - eng_software
  - software
aliases:
creation: 2026-10-28T18:11:00
fontes:
  - "[Valente - 2020 - Engenharia de Software Moderna.pdf](obsidian://zotflow?type=open-attachment&libraryID=22438711&key=ASZ6AFIR)"
type:
  - nota
---
# Overview

Coesão signifique que uma classe deve cumprir apenas uma responsabilidade, e não deve implementar funções que não são sua responsabilidade.
> [[@valenteEngenhariaSoftwareModerna2020#^CEJHY3TL|Marco Tulio de Oliveira Valente, Engenharia de Software Moderna, (2020), p. 94]]

## Exemplo 

Classe não coesa
```C++
class Carrinho {
public:
	adicionarItem();
	
	efetuarCompra();
	
	gerenciarPagamento();
	
	emitirRecibo();

}
```

#### Fontes 
VALENTE, Marco Tulio de Oliveira. **Engenharia de Software Moderna**. _[S.l.]_: Marco Tulio de Oliveira Valente, 2020.
[^valenteEngenhariaSoftwareModerna2020]:  Marco Tulio de Oliveira Valente, *Engenharia de Software Moderna* (2020).
