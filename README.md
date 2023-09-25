# Anotações Banco de Dados

Uma breve descrição dos tópicos dentro da _modelagem de banco de dados_. 

Provavelmente eu escrevi a grade maioria dessas anotações enquanto revisava a matéria para a prova.

_Se houver alguma anotação mais detalhada sobre o assunto, você pode conferir clicando na linkagem ou abrindo a pasta /notas_

## O que é um banco de dados?

Um **banco de dados** é uma coleção de dados relacionados.

É diferente de um sistema de banco de dados.

Bancos de Dados possuem características que o diferenciam de outras coleções de dados, são elas:

- Realidade (representam o mundo real)
- Finalidade (propósito real)
- Coerência (mantém a coerência lógica da coleção)
- Compartibilidade (compartilhamento dos dados)

## Sistema de Banco de Dados (SBD)

Um **Sistema de Banco de Dados** é constituido de uma coleção de dados organizados (banco de dados), um modelo de dados que é a estrutura lógica de como os dados estão organizados e um software que provém acesso aos dados para os usuários e aplicações.

- Coleção de Dados
- Modelo de Dados
- Software Gerenciador de Banco de Dados (SGBD)

Para um projeto bem sucedido de um sistema de banco de dados, certas etapas de implementação devem ser seguidas. São elas:

- Análise do Minimundo (Especificação)
- Análise de Requisitos
- Projeto Conceitual
- Projeto Lógico 
- Projeto Físico
 
 ## O Sistema Gerenciador de Banco de Dados (SGBD)

O SGBD possui certas vantagens como por exemplo, acesso a múltiplos interfaces, disponibilidade elevada, backup e recuperação, garantia de padrões, etc.

Porém, em certos casos, usar um SGBD pode não ser tão viável.

### Onde não é viável usar um SGBD
Situações onde você encontra aplicações monousuário, alta especialização, custo proibitivo, requisitos muito rigorosos ou até mesmo aplicações de baixa complexidade.

## Modelo de Dados

O modelo de dados é a estrutura lógica pela qual os dados estão organizados.

Existem vários tipos de modelos de dados, por exemplo: rede, hierarquico, orientado a objetos e o foco dessa anotação, o modelo de dados relacional.

A graça e o pulo do gato aqui está na possibilidade de representar diferentes visões dependendo do usuário. Existem diferentes níveis de abstrações, do mais alto para o mais baixo.

- Conceitual (alto nível de abstração)
    - Como os usuários percebem
    - Conceitos de entidade, atribuito e relacionamento
    - NÃO DEPENDE DE MODELO DE IMPLEMENTAÇÃO


- Representativo (nível médio de abstração)
    - Modelo de implementação, no nosso caso, o relacional
    - Objetos, relação, tupla e coluna

- Físico (baixo nível de abstração)
    - Estrutura de armazenamento físico
    - Arquivo, registro, campo


## Modelo Conceitual

Os principais assuntos do modelo conceitual giram em torno de entidades, atributos e relacionamentos.

Entidade são os objetos em discursos, por exemplo, uma entidade chamada Professor terá **atributos** como nome, cpf, salário, etc. 

Uma entidade por si só não é grande vantagem, por isso associamos com outras entidades através de um relacionamento. Exemplo, Professor é associado com a entidade Departamento.

### Diagrama Entidade Relacionamento (ER)

Uma maneira conceitual de representar graficamente o minimundo a partir da especificação textual.

**Entidades são representadas com retângulos, atributos com elipses e relacionamento com losangos.**

![Exemplo de Um Modelo Conceitual - Diagrama Entidade Relacionamento](/img/exemplo-modelo-conceitual.png)

Veja mais em [Modelo Conceitual](/notas/modelo-conceitual.md)

