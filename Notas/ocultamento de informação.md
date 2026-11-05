---
tags:
  - eng_software
  - software
aliases:
creation: 2026-10-28T17:00:00
fontes:
  - "[Valente - 2020 - Engenharia de Software Moderna.pdf](obsidian://zotflow?type=open-attachment&libraryID=22438711&key=ASZ6AFIR)"
type:
  - nota
---
# Overview

Um módulo (classe) deve esconder sua implementação, apenas expondo o necessário para seus clientes (usuários daquela classe) através de [[interface]]s. Isso ajuda com a manutenção do código pois os clientes precisam apenas saber os parâmetros da interface, assim caso a implementação mude não é necessário refatorar o código do cliente a não ser que a [[interface]] em si mude. 
[[@valenteEngenhariaSoftwareModerna2020#^YR6UFCPS|Marco Tulio de Oliveira Valente (2020), p. 90]]

![[@valenteEngenhariaSoftwareModerna2020#^93CUTNLE|Marco Tulio de Oliveira Valente, Engenharia de Software Moderna, (2020), p. 91]]


As vantagens de ocultamento de informação são as seguintes:
- **Escalamento**: Desenvolvedores em um time não precisam se preocupar com os específicos de cada classe, apenas com os parâmetros da [[interface]]. 
- **Flexibilidade**:  Caso seja necessário mudar a implementação de uma classe, não é necessário mudar seus clientes. 
- **Facilidade de entendimento**: É mais fácil um desenvolvedor começar a trabalhar em uma parte do sistema sem ter que entender o sistema como um todo. 

## Nota sobre get e set 

Getters e setters não necessariamente garantem ocultamento da informação ja que aumentam a complexidade da interface, e devem ser usados apenas caso necessário.
[[@valenteEngenhariaSoftwareModerna2020#^NRVTH3UQ|Marco Tulio de Oliveira Valente, Engenharia de Software Moderna, (2020), p. 93]]

## Exemplos

O código abaixo não possui coesão, já que a tabela **veiculos** é alterada diretamente em **main**.
```Java
import java.util.Hashtable;
 public class Estacionamento { 
 	public Hashtable<String, String> veiculos;
	
	public Estacionamento() { 
		veiculos = new Hashtable<String, String>(); 
	} 
	
	public static void main(String[] args) { 
		Estacionamento e = new Estacionamento();
		 e.veiculos.put("TCP-7030", "Uno"); 
		 e.veiculos.put("BNF-4501", "Gol"); 
		 e.veiculos.put("JKL-3481", "Corsa"); 
	} 
}
```

Isso é um problema, já que se o tipo de dado mudar, o código em **main** ficará obsoleto, e precisará ser refatorado. Para evitar isso, utiliza-se um método para alterar a variável que armazena os dados da classe, e essa mesma variável é privatizada evitando a alteração acidental da mesma fora pelos *clientes* da classe. 

```Java
import java.util.Hashtable;
public class Estacionamento { 
	private Hashtable<String,String> veiculos; 
	public Estacionamento() { 
		veiculos = new Hashtable<String, String>();
	} 
	
	public void estaciona(String placa, String veiculo) { 	
		veiculos.put(placa, veiculo); 
	} 
	public static void main(String[] args) { 
		Estacionamento e = new Estacionamento(); 
		e.estaciona("TCP-7030", "Uno"); 
		e.estaciona("BNF-4501", "Gol"); 
		e.estaciona("JKL-3481", "Corsa"); 
	} 
}
```

[[@valenteEngenhariaSoftwareModerna2020#^M947WEHZ|Marco Tulio de Oliveira Valente, Engenharia de Software Moderna, (2020), p. 91]]

#### Fontes 
VALENTE, Marco Tulio de Oliveira. **Engenharia de Software Moderna**. _[S.l.]_: Marco Tulio de Oliveira Valente, 2020.