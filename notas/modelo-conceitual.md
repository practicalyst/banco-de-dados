# Modelo Conceitual 

## Diagrama Entidade Relacionamento (DER)

Uma maneira conceitual de representar graficamente o minimundo a partir da especificação textual.

**Entidades são representadas com retângulos, atributos com elipses e relacionamento com losangos.**

[Descrição completa do modelo entidade relacionamento (MER)](https://www.devmedia.com.br/mer-e-der-modelagem-de-bancos-de-dados/14332)

Nessa página vou focar em assuntos presumindo que você já saiba o básico e consiga "ler" um DER.

### O que é uma chave?

No DER é necessário que cada entidade seja identificada de maneira única, por isso sempre devemos escolher um atributo ou um conjunto de atributos para que seja seu identificador único. 

No caso de mais de um atributo, essa chave será chamada de chave-composta.



### Tipos de relacionamentos entre entidades


#### Relacionamento 1..n ou 1..* (um para muitos): 

Uma das entidades envolvidas pode referenciar várias unidades da outra, porém, do outro lado cada uma das várias unidades referenciadas só pode estar ligada uma unidade da outra entidade. Por exemplo, em um sistema de plano de saúde, um usuário pode ter vários dependentes, mas cada dependente só pode estar ligado a um usuário principal. Note que temos apenas duas entidades envolvidas: usuário e dependente. O que muda é a quantidade de unidades/exemplares envolvidas de cada lado.

#### Relacionamento n..n ou *..* (muitos para muitos): 

Neste tipo de relacionamento cada entidade, de ambos os lados, podem referenciar múltiplas unidades da outra. Por exemplo, em um sistema de biblioteca, um título pode ser escrito por vários autores, ao mesmo tempo em que um autor pode escrever vários títulos. Assim, um objeto do tipo autor pode referenciar múltiplos objetos do tipo título, e vice versa.

#### Relacionamento 1..1 (um para um): 

Cada uma das duas entidades envolvidas referenciam obrigatoriamente apenas uma unidade da outra. Por exemplo, em um banco de dados de currículos, cada usuário cadastrado pode possuir apenas um currículo na base, ao mesmo tempo em que cada currículo só pertence a um único usuário cadastrado.

### Participação total ou parcial

Quando uma entidade é "obrigada" estar relacionada com outra, temos uma relação de participação total, representada por linhas duplas. 

Parcial estabelece a não obrigatoriadade e é representada com linhas simples.

![Imagem demonstrando as relações de participação total ou parcial](/img/total-ou-parcial.png)

## Resumo dos Elementos do Diagrama

![Resumo dos Elementos 1](/img/resumo-elementos1.png)
![Resumo dos Elementos 2](/img/resumo-elementos2.png)