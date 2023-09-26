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

## Arquitetura de 3 Esquemas

Uma abordagem que permite visualizar as diferentes visões em níveis de abstrações diferentes.

- Nível interno - armazenamento físico do BD
- Nível conceitual 
- Nível externo - visão do usuário

A arquitetura de 3 esquemas pode ser usada para explicar melhor o conceito de independência de dados, que pode ser definida como a capacidade alterar o esquema em um nível sem ter de alterar o esquema no nível mais alto.

## Modelo Conceitual

Os principais assuntos do modelo conceitual giram em torno de entidades, atributos e relacionamentos.

Entidade são os objetos em discursos, por exemplo, uma entidade chamada Professor terá **atributos** como nome, cpf, salário, etc. 

Uma entidade por si só não é grande vantagem, por isso associamos com outras entidades através de um relacionamento. Exemplo, Professor é associado com a entidade Departamento.

### Diagrama Entidade Relacionamento (ER)

Uma maneira conceitual de representar graficamente o minimundo a partir da especificação textual.

**Entidades são representadas com retângulos, atributos com elipses e relacionamento com losangos.**

![Exemplo de Um Modelo Conceitual - Diagrama Entidade Relacionamento](/img/exemplo-modelo-conceitual.png)

Veja mais em [Modelo Conceitual](/notas/modelo-conceitual.md)

## Modelo Relacional

Aqui sim já se trata de um modelo de implementação (representativo).

Para mapear um diagrama conceitual para um diagrama relacional, precisamos de 7 etapas.

### Etapa 1 - Entidades fortes:
- Crie uma relação para cada entidade forte e inclua todos os atributos simples
- Inclua apenas atributos simples de um atributo composto
- Escolha um dos atributos chave como __chave primária__ da nova relação.
- Se a chave escolhida for composta, o conjunto de atributos simples que a compõe formarão a chave primária

### Etapa 2 - Entidades fracas:
- Crie uma relação para cada entidade fraca e inclua todos os atributos simples
- Inclua como atributos de chave estrangeira da relação, os atributos de chave primária da relação que corresponde à entidade proprietária
- Escolha a chave estrangeira e um atributo chave parcial como chave primária da nova relação

### Etapa 3 - Relacionamentos Binários 1:N
- Identifique a R1 que representa a entidade participante no lado N do relacionamento
- Inclua como Chave Estrangeira em R1 a chave primária de R2, que representa à outra entidade participante do relacionamento

### Etapa 4 - Relacionamentos Binários N:N
- Crie uma nova relação R3 para cada relacionamento N:N
- Inclua como __chave estrangeira__ em R3 as chaves primárias das relações R1 e R2, que representam as entidades participantes no relacionamento
- A chave primária de R3 será formada pela combinação das chaves estrangeiras em R3

### Etapa 5 - Relacionamentos Binários 1:1
- Identifique as relações que correspondem às entidades participantes
- Existem 3 estratégias: 
    - Mesclagem: consiste em mesclar as entidades e o relacionamento em uma única relação
    - Chave estrangeira: consiste em mapear o relacionamento 1:1 como participante de um relacionamento 1:N
    - Referência cruzada: consiste em mapear o relacionamento 1:1 como relacionamento N:N

### Etapa 6 - Atributos multivalorados
- Crie uma nova relação para cada atributo multivalorado A
- A nova relação incluirá um atributo de A, mais o atributo da chave primária da relação que representa a entidade ou relacionamento que tenha A como atributo multivalorado. 

### Etapa 7 - Relacionamento de alto grau
- Crie uma relação R3 para cada relacionamento n-ário, em que n > 2
- Inclua como chave estrangeira em R3 as chaves primárias das relações que representam as entidades participantes
- A chave primária de R3 é a combinação de todas as chaves estrangeiras que referenciam as relações das entidades participantes