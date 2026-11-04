---
tags:
  - eng_software
  - software
aliases:
creation: 2026-10-28T17:00:00
fontes:
  - "[Valente - 2020 - Engenharia de Software Moderna.pdf](obsidian://zotflow?type=open-attachment&libraryID=22438711&key=ASZ6AFIR)"
---
# Overview

Um módulo (classe) deve esconder sua implementação, apenas expondo o necessário para seus clientes (usuários daquela classe) através de [[interface]]s. Isso ajuda com a manutenção do código pois os clientes precisam apenas saber os parâmetros da interface, assim caso a implementação mude não é necessário refatorar o código do cliente a não ser que a [[interface]] em si mude. 
[[Source/My Library/@valenteEngenhariaSoftwareModerna2020.md#^YR6UFCPS|Marco Tulio de Oliveira Valente (2020), p. 90]]

As vantagens de ocultamento de informação são as seguintes:
- **Escalamento**: Desenvolvedores em um time não precisam se preocupar com os específicos de cada classe, apenas com os parâmetros da [[interface]]. 
- **Flexibilidade**:  Caso seja necessário mudar a implementação de uma classe, não é necessário mudar seus clientes. 
- **Facilidade de entendimento**: É mais fácil um desenvolvedor começar a trabalhar em uma parte do sistema sem ter que entender o sistema como um todo. 

## Nota sobre get e set 

Getters e setters não necessariamente garantem ocultamento da informação ja que aumentam a complexidade da interface, e devem ser usados apenas caso necessário.

“[…] o conteúdo do capítulo aplica-se a outras unidades de modularização, incluindo aquelas menores do que classes, como métodos e funções; e também a unidades maiores, como pacotes e componentes.”([Valente, 2020](zotero://select/library/items/MJB36T5H))

#### Fontes 
VALENTE, Marco Tulio de Oliveira. **Engenharia de Software Moderna**. _[S.l.]_: Marco Tulio de Oliveira Valente, 2020.