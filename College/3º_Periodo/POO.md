 title: Programação orientada por objetos (Puc-Minas - 3º Período)
author: Arthur P. Braga

## Notes

####  Pensar na hora de modelar a classe:

1. Atributo ou método?
2. static? final?
3. Visibilidade
4. Revisa o fluxo de sistema

---

## Aula 1 - 04/02

#### Apresentação da disciplina

#### Revisão de conceitos

- **Valor**: Dado atribuido a uma posição na memória para ser operado/usado. Valor é usado no programa. Valor representa um dado contido em uma posição na memória.
- **Variável**: Nome dado à representação do valor. "Ponteiro para o valor".
- **Tipo da variável**: Indica como a variável vai ser usada. Também indica quanto espaço vai usar na memória.
- **Vetores e matrizes**: Para alocar mais de uma variável, criar um conjunto de variáveis, do mesmo tipo e relacionadas.
- **Métodos**: Conjunto de instruções com uma finalidade.

---

## Aula 2 - 05/02

#### Criação de um sisteminha do jogo de dados (Par ou Ímpar)

*Só pra ter uma ideia de POO.* 

---

## Aula 3 - 11/02

#### Fundamentos de POO

*Orientação por objetos abstrai o mundo real utilizando objetos que interagem entre si.*

**Análise orientada para objetos** (OOA/AOO): Examina os requisitos de um sistema de uma perspectiva de classes e objetos, usando o vocabulário do domínio do problema.

**Projeto orientado por objetos** (OOD/DOO): Projeto no qual o processo da decomposibilidade em objetos é utilizado e modelos físicos e lógicos de objetos são descritos.

**Programação orientada por objetos** (OOP/POO): Implementar o planejamento.

- POO, segundo *Alan Kay:*
  - Troca de mensagens
  - Proteção e retenção local e ocultamento do estado (dados) ou processo
  - Associação tardia e dinâmica de tudo o que for possível

**Procedural x POO**

- Procedural: Instruções executadas em um fluxo que visa o desempenho de uma tarefa específica.
- POO: Conjunto de objetos que interagem entre si, porém preserva sua individualidade e tem um papel específico na execução de uma tarefa.

#### Análise e projeto OO

**Tipo abstrato de dados** (TDA): reúne na mesma estrutura, informações sobre dados, e comportamento de uma entidade representada a partir do mundo real.

**Classe**: Descrição padronizada de um tipo abstrato de dados. Modela um conjunto de entidades do mundo real que possuem características e comportamentos semelhantes.  É o esquema/representação/modelo de uma "entidade genéria". Constituída por atributos e métodos. Ex: Classe caneta, classe carro... 

**Objeto:** É a instância de uma classe, é um "exemplar" daquela classe. Ex: Classe usuário - Objeto João.

---

## Aula 4 - 12/02

#### Exercício de modelação de classe

**UML**: Linguagem de modelagem universal.

---

## Aula 5 - 18/02

#### Modularidade

É a divisão do sistema em partes distintas. Um módulo é um **grupo de comandos** com uma **função/propósito** bem definida e o mais **idependente** possível em relação ao resto do algoritmo. *Unidade identificável na compilação.*

Consequentemente mais seguro, pois divide o sistema e permite modificar um lugar sem alterar o outro. Facilitando o desenvolvimento e reúso da solução;

##### Coesão

As classes precisam ser coesas, não pode ter pontas soltas (precisa ter ligação com o sistema, e de forma lógica/inteligente). Um sistema com alta coesão:

- Facilita e acelera a manutenção;
- Reduz efeitos colaterais e propagação de erros;
- Dependência deve ser intra-modular: uso e dependência resumidas ao máximo nas estruturas internas ao módulo.

##### Abstração 

Uma classe deve incluir somente os atributos de importância em um contexto **particular**. Precisa ter os atributos (dados) necessários para a utilização daquela entidade no sistema. 

- Conceito da caixa-preta: Entrada e saída bem conhecidas, mas com detalhes ocultos.
- *A ideia principal é não ser necessário saber os detalhes do funcionamento de um objeto para utilizá-lo.*

#### Encapsulamento

**Proteger!** É o princípio da ocultação de informação e do conceito de caixa preta. Seguir regras (validações) para manter os dados...

- Proteger os dados do acesso direto a partir de um código externo (oculta). Garantindo que as regras sejam seguidas, permitindo o acesso e uso deles somente da forma correta/definida.
- Os atributos de uma classe só deveriam ser acessador e modificados por meio de seus métodos, deixando os atributos sempre 'private'. Geralmente usando getters e setters (métodos de acesso) para retornar e setar os valores. Isso impede alterações indevidas, por exemplo.

---

## Aula 6 - 19/02

#### Getters and Setters

#### Atividade prática

---

## Aula 7 - 25/02

#### Revisão/Discussão da atividade proposta

#### Construtor

Método especial responsável pela implementação de ações necessárias para criar um objeto. Instruções pré-definidas para que uma classe sempre seja criada de maneira válida.

---

## Aula 8 - 26/02

#### Atributos 'de classe' - static

Atributos que dizem respeito à toda coleção de objetos, e não a um objeto específico. Compartilhado por todos os objetos daquela classe.

- Escopo local (delimitado pela visibilidade declarada);
- Tempo de vida global (vai ficar vivo enquanto o programa rodar);
- Inicializado pelo 1º objeto ou pelo carregamento da classe.

Úteis para implementar contadores ou identificadores de autoincremento. Também usado para constantes (**Economia de memória**). Declarados com a palavra chave **'static'**.

Exemplos: Armazenar última matrícula de um aluno cadastrado no sistema, poderia servir para criar a próxima (levando em consideração que a matrícula é uma sequência).

**Atributos finais ou selados (final):** Não podem mudar de valor após inicializados.*

*Nomenclatura em maiúsculo quando a variável é 'static final'.*

#### Métodos 'de classe' - static

São funções que não dependem de nenhuma variável de instância, quando invocados executam uma função sem a dependência do conteúdo de um objeto ou a execução da instância de uma classe, conseguindo chamar direto qualquer **método** da classe.

**Obs:** Se uma classe só possui métodos e atributos estáticos, logo ela é considerada uma **classe estática**, nunca irá precisar de instância. Ex: System, Math (Libs de funções) - Integer.parseInt (Manipulação de tipos) - Conversor de medidas...

---

## Aula 9 - 04/03

#### Relacionamento entre classes

Objetos compostos

Geralmente objetos não funcionam sozinhos, usam e comunicam com outros objetos. Isso leva á: 

- Reduzir custos - Aumentar confiabilidade - Modularidade => alto grau de reusabilidade.

##### Associação

Objeto usa outro, mas não tem relação de pertinência, um não pertence à outro. Ex: Um carro usa uma estrada

##### Agregação

Objeto definido em termos dos seus componentes (um contém). Ex: Turma contém alunos.

- A existência da "parte" faz sentido, mesmo não existindo o "todo". Ex: Alunos -> Turma; Atleta -> Time.
- Representação UML: Losango (no lado do "todo").

##### Composição

O objeto é formado por outros objetos (está contido). Dependência do tempo de vida entre parte e todo, um só existe se o outro existir (Relacionamento mais forte). Ex: Um livro é formado por capítulos; Um pedido é formado por vários itens.

- A existencia da parte não faz sentido sem o todo!
- Representação UML:  Losango preenchido (no lado do "todo");
- Se o objeto todo for apagado, as partes também são.

![image-20210610194007147](/home/arthur/Documentos/Programming_Study/imgs/3_Periodo/image-20210610194007147.png)

---

## Aula 10 - 05/03

#### Cardinalidade

##### Um para um

Único objeto de cada lado. Ex: Curso tem um coordenador.

<img src="../../imgs/3_Periodo/POO/Cardinalidade_1to1.png">

##### Um para muitos

Um dos lados pode ter múltiplos objetos. Ex: Um departamento possui muitos professores, mas um professor está alocado a um departamento apenas.

<img src="../../imgs/3_Periodo/POO/Cardinalidade_1ton.png">

##### Muitos para muitos

Podem haver múltiplos objetos em ambos os lados. Ex: Um aluno pode realizar emprestimos de vários livros. Cada livro pode, a seu tempo, ser emprestado para vários alunos.

<img src="../../imgs/3_Periodo/POO/Cardinalidade_NtoN.png">

Pode gerar uma classe de associação. Ex: Empréstimo.

<img src="../../imgs/3_Periodo/POO/ClasseRelacionamento.png">

##### Cardinalidade na UML

<img src="../../imgs/3_Periodo/POO/CardinalidadeUML.png">

##### Implementação de relações

Unidirecional ou bidirecional?
- Unidirecionais sugerem a implementação de atributos apenas na origem (uma das partes). Ou seja, somente uma das partes vai ter uma referência da outra parte;
- Em alguns casos exigem análise mais aprofundada.

---

## Aula 11 - 11/03

#### Modularidade - Acoplamento

Cenário ideal: Manter baixo acoplamento.

##### Indicadores

- Tamanho da classe, quanto maior, mais coisas ela está fazendo. *Quantidade de parâmetros e métodos públicos*. Geralmente quando tem mais métodos, significa que tem mais objetos utilizando/dependendo dela;
- Visibilidade. Uso de parâmetros x Uso de variáveis globais. Mesmo os parâmetros sendo um possível indicador de acoplamento, usar parâmetros é ainda mais desacoplado que a chamada de variáveis globais por outras classes... 
- Flexibilidade. Facilidade na chamada (Especialização - Subclasse).

#### Destrutores

##### Coletor de lixo

Processo que libera automaticamente memória que não está sendo mais utilizada. Java -> Garbage collector.

- Eliminam a necessidade de se desalocar memória explicitamente ("manualmente");
- Eliminam o vazamento de memória;
- Eliminam referências pendentes (dangling - Ponteiros que não estão apontando pra ninguém).

##### Destructors

São métodos especiais invocados quando um objeto é finalizado, para garantir que não ficará nenhum resto mortal do objeto.

- Só há um destrutor por classe;
- Um destrutor não tem parâmetros;
- Não deve ser chamado diretamente. É chamado de forma indireta (quando um objeto é finalizado);
- É autônomo.

Objetivo principal: Liberação de recursos usados pelo objeto. Ex: Memória, conexão de rede, conexão com banco de dados...

A classe Object em Java tem um método **finalize**. Ele é executado automaticamente quando a área do objeto da classe que a contem estiver para ser liberada pelo coletor.

Pode escrever o finalize para sua própria classe, passando regras de finalização particulares da sua classe. Ex: close() pro Scanner...

---

## Aula 12 - 12/03

#### Exercícios de implementação e UML

---

## Aula 13 - 18/03

#### Revisão do exercício para prova

---

## Aula 14 - 19/03

#### Prova

---

## Aula 15 - 26/03

#### Especialização / Herança

Reaproveitamento de código. Mais alto nível de abstração. Especializar uma classe genérica. Ex: Um professor é uma *pessoa*. Um aluno é uma *pessoa*.

Essa especialização tradicionalmente é implementada por meio do mecanismo de herança - Classe mãe e classe filha.

> Classes filhas herdam métodos e atributos públicos ou protegidos da classe mãe.
>
> Classes filhas podem sobrescrever métodos herdados -> especialização - @Override  

<img src="../../imgs/3_Periodo/POO/Heranca-UML.png" style="width:90%">

*Todo construtor da classe filha chama o da mãe, só devemos escolher qual construtor usar!* A palavra *super* representa o construtor da classe mãe, e eles são diferenciados pela parametrização.

---

## Aula 16 - 08/04

#### Exercício prático

---

## Aula 17 - 09/04

#### Polimorfismo

Definimos *Polimorfismo* como um princípio a partir do qual as classes derivadas de uma única classe base são capazes de invocar os métodos que, embora apresentem a mesma assinatura, comportam-se de maneira diferente para cada uma das classes derivadas.

Com o *Polimorfismo*, os mesmos atributos e objetos podem ser utilizados em objetos distintos, porém, com implementações lógicas diferentes.

Em outras palavras: O polimorfismo permite que referências de tipos de classes mais abstratas representem o comportamento das classes concretas que referenciam. Assim, é possível tratar vários tipos de maneira homogênea. O termo polimorfismo é originário do grego e significa "muitas formas". 

**Método abstract:** É o método de uma classe **abstrata** que não possui implementação. Na classe **abstrata**, é definido o **método abstrato** com palavra reservada abstract e sua assinatura. Isso é implementado quando o código depende 100% de particulares/regras das classes filhas. *É só uma ideia*.

---

## Aula 18 - 15/04

#### Exercício prático

---

## Aula 19 - 16/04

#### Herança múltipla

Capacidade de uma classe herdar de duas ou mais superclasses. Ou seja, combinar características de várias classes na definição de uma nova classe.

*Exemplo hipotético: Uma pessoa é um mamífero e um bípede.*

Heranca_Multipla

<img src="../../imgs/3_Periodo/POO/Heranca_Multipla.png" style="width:60%">

*O que é foodtruck? Herança múltipla das classes Caminhão e Restaurante :)*

- Porém se herda de duas, depende de duas, ou seja, aumenta o acoplamento.
- Outro problema é a ambiguidade, piora o encapsulamento: 

<img src="../../imgs/3_Periodo/POO/Problema1_HerancaMultipla.png" style="width:90%">

Mesmo se vc fizer um Override para unificar esse *avançar*, isso é ruim, pois piora a abstração, muda a regra fixa da classe mãe.

E o problema não acaba por aí:

- Métodos de nomes iguais e visibilidades diferentes.
- Propriedades de mesmo nome.

##### Problema do diamante

Qual equals ele vai  usar?

<img src="../../imgs/3_Periodo/POO/class-multiple-inheritance-diamond.png" style="width:30%">

##### Solução

*O ornitorrinco é a prova de uma herança divina. Ou seja, há solução :)*

Porém, nem Java permite herança multipla :)

<img src="../../imgs/3_Periodo/POO/Solucao_HerancaMultipla.png" style="width:80%">

---

## Aula 20 - 22/04

#### Interface

Em seu significado **conceitual** é a *"parte visível de um módulo a outros módulos"*. Tudo o que é *public* é a interface de uma classe.

- Coesão: A interface deve oferecer um grupo de métodos coerentes;
- Abstração: Se uma interface é definida e sempre é mantida, o sistema ganha em extensibilidade e em baixo acoplamento. Ou seja, se ela for atualizada... todas as classes que estiverem utilizando ela, utilizarão as atualizações.

Exemplo mundo real: Um controle remoto, a parte visível são todos os botões para o usuário utilizar e controlar a televisão.

##### what is

É uma entidade do nosso projeto usada para definir um protocolo de comportamento que pode ser implementado por qualquer classe em qualquer hierarquia de classes.

- São declaradas, mas não podem ser instanciadas.

- Abstração: implementação fica a cargo de cada especialização da interface.

Basicamente é um contrato que define **tudo o que uma classe deve fazer** se quiser ter um determinado **status**. Ou seja, obrigações que uma classe precisa fazer para ser considerada uma classe válida do tipo definido. Exemplo: Para a classe calculadora ser considerada realmente uma calculadora, ela precisa saber somar, dividir, multiplicar... Ex2: Para a classe Jogo ser considerada um jogo, ela deve saber calcular o preço dele...

O **benefício** é que se temos classes com comportamento similares, logo temos o mesmo conjunto de métodos, mesmo que tenham implementações diferente. 

> Então temos os mesmos métodos, com os mesmos nomes (com a mesma assinatura), porém com implementações particulares e específicos de cada classe que "assina esse contrato", que utiliza a interface. Isso é vantagem por que dessa forma temos uma **comunicação padronizada**. E isso facilita MUITO para o programador. Isso trás:
>
> - Flexibilidade
> - "Polimorfismo"
> - Baixo acoplamento. Utilizamos os "mesmos comandos" definidos pela interface para várias classes 

##### Aplicação

<img src="../../imgs/3_Periodo/POO/Exemplo_1UsoInterface.png" style="width:80%">

Em Java:

- Possuem prioritariamente declarações (assinaturas) de métodos e atributos constantes (public statis final). *Não é muito recomendável utilizar atributos na interface, aumenta o acoplamento;*
- Podem incorporar outras interfaces, utilizando-se extends;
- São 'assinadas' por meio do uso de *implements*;
- Java permite implementação de múltiplas interfaces e combinação de herança.

##### Utilizando interfaces

*Como ela pode ajudar a resolver um problema :)*

###### 1º exemplo

"Um banco possui 4 tipos de funcionários: atendimento em caixa, analistas financeiros, gerentes de contas e diretores..."

>  A primeira ideia é criar uma classe *Funcionario*, com classes para cada tipo de funcionário herdando dela.

Evoluindo o sistema: "Agora o sistema interno do banco pode ser acessado por gerentes e diretores que desejam observar dados dos clientes ou indicativos de desempenho dos funcionários subordinados, Este acesso é feito por meio de uma senha numérica de 4 dígitos"

> Logo pensamos em um método "autenticar" ou "login" para as duas classes (gerentes e diretores). Porém, dessa forma não podemos usar a funcionalidade com esse polimorfismo, pois a classe *Funcionario* não tem esse método.
>
> <img src="../../imgs/3_Periodo/POO/Erro_Polimorfismo.png" style="width:80%">
>
> Podemos resolver esse problema com uma sobrecarga, MAS se surgir um novo cargo com acesso ao login a manutenção fica o ó, vai ter que criar várias versões do método...
>
> Outra alternativa é um novo nível de abstração:
>
> <img src="../../imgs/3_Periodo/POO/Nivel_Abstracao.png" style="width:70%">
>
> Muito bom :)

Evoluindo o sistema mais ainda: "Haverá uma integração dos sistemas e agora os clientes podem acessar os próprios dados usando o mesmo sistema."

> Agora não tem como a classe *Cliente* herdar da classe de autenticação, pois ela não é um funcionário. Logo a proposta é criar um "contrato" que estabeleça o comportamento de qualquer classe autenticável (*Interface*).
>
> ```java
> interface IAutenticavel {
> 	boolean autenticar(String pwd)
> }
> ```
>
> <img src="../../imgs/3_Periodo/POO/Exemplo_UsoInterface.png" style="width:80%">

---

## Aula 21 - 23/04

#### Substituindo herança por composição

Com herança ainda temos um certo nível de acoplamento e perde um pouco de encapsulamento. 

Por meio do uso de interfaces e composição de classes, podemos **injetar** comportamento em classes. *(Injeção de dependência)*.

- Delegação de responsabilidades;
- **Mudança de comportamento** em tempo de execução.

##### Exemplo

Um banco oferece três tipos de contas a seus clientes: conta corrente, poupança e investimentos. Com 3 operações básicas: Sacar, depositar e consultar saldo.

*Herança básica:*

<img src="../../imgs/3_Periodo/POO/Exemplo_HerancaBasica.png" style="width:80%">

*Pra melhorar:*

<img src="../../imgs/3_Periodo/POO/Exemplo_InjecaoComposicao.png" style="width:100%">

Isso permite que cada conta, obrigatoriamente, tenha os métodos definidos na interface (comportamento semelhante), porém com implementações diferente. Pois, a forma de saque é diferente entre uma conta corrente, investimento e poupança, por exemplo. Sem contar que podemos alterar o tipo da conta em tempo de execução, sem problemas.

---

## Aula 22 - 29/04

#### Prática de composição

---

## Aula 23 - 20/04

#### Para que usar interface?

1. Capturar **similaridades** entre classes **não relacionadas;**
2. **Declarar métodos** que uma ou mais classes devem **inevitavelmente** implementar;
3. Revelar interfaces sem revelar os objetos que a implementam: útil em pacotes de componentes;
4. Programação remota / uso de serviços.
5. Alternativa para herança múltipla
6. Composição 

#### Herança x Interface: regras de Coad

1. Subclasse denota "é um" e não "tem papel de" ou "tem um";
2. Uma instância de uma subclasse nunca precisará mudar para outra subclasse;
3. Uma subclasse deve estender, e não sobrescrever ou anular as responsabilidades da classe mãe. Ou seja, a subclasse deve ter coisas novas;
4. Uma subclasse não estende as capacidades de uma classe utilitária (*ferramenta para problemas genéricos*);
5. Para uma classe do problema tratado, a subclasse especializa um papel, transação ou dispositivo.

---

## Aula 24 - 06/05

#### Polimorfismo [continuação]

Existem 4 tipos de polimorfismo:

- Polimorfismo universal
  - de inclusão 
  - Paramétrico
- Polimorfismo ad hoc
  - Coerção
  - Sobrecarga

---

#### Polimorfismo ADHOC

Alguma coisa sob demanda - se destina à um fim específico - fazemos para uma classe específica, e não necessáriamente funciona para classes além dessa.

##### Polimorfismo Coerção (cast)

Cast = Accio (Harry Potter) :zap:

Conversão de tipo explícita definida pelo programador, ou seja, transforma um objeto de um tipo, em outro. Só será aceita se houver alguma relação de parentesco entre as classes. Exemplo:

- Tipos básicos - Conversão de *int to double* 
  - divisao = (double) num1/num2
- Conversão classe mãe -> classe filha.

```Java
Figura x;
Retangulo X;
x = new Retangulo(4,5);
y = (Retangulo)(x);
System.out.println(y.getAltura());
```

:arrow_down:

##### Polimorfismo Sobrecarga

Criação de diversos método com o mesmo nome, mas diferentes parâmetros de entrada (e, algumas vezes, saída). *Ações diferentes!*

Não é universal: somente para os tipos/classes para os quais foi implementada a sobrecarga.

###### Sobrecarga de operadores

```Java
int a, b, c;
String s, t;
////////////////
x = y + z;
s = t + "ontem";
```

###### Sobrecarga de métodos

``` java
String nome = "Arthur";
int resposta = 42; // Quem pegou a referência?
System.out.println(nome);
System.out.println(resposta);
// &&
int diffDias(Data a, Data b);
int diffDias(Data outra);
```

---

####  Polimorfismo universal

##### Polimorfismo Paramétrico

<img src="../../imgs/3_Periodo/POO/Cenario_PolimorfismoParametrico.png" style="width:100%">

Logo, precisamos de uma abstração baseada em códigos genéricos:

- Valores/objetos serão manipulados de forma similar independente do seu tipo/classe.

A genericidade é atingida por:

- Uso de classes ou tipos básicos como parâmetros em classes parametrizadas -> <T>
- Mecanismo de implementação que substitua implícita ou explicitamente a operação parametrizada quando necessário.

> Classes e métodos polimórficos - genéricos - usados explicitamente para que a classe genérica resolva suas operações.
>
> Substituição implícita (padrões) ou explícita (parâmetros) de métodos.

Exemplo:

``` java
public class ListaGenerica<T extends Comparable<T>> {
    private T[] dados;// Se criarem essa lista do tipo 'Pizza', será um array de pizzas
    private int capacidade;
    private int quantidade;
    
    public boolean addInList(T novo) {// Consigo add qualquer tipo na lista 
        if (this.quantidade < this.capacidade) {
            dados[this.quantidade] = novo;
            this.quantidade++;
            return true;
        }
        return false;
    }
    
    public T search(T quem) {// Consigo buscar qualquer dado de qualquer tipo na lista
        for(int i = 0; i < this.quantidade; i++) {
            if (this.dados[i].equals(quem))
                return this.dados[i];
        }
        return null;
    }
    
    public T greatest() {
        T aux = dados[0];
        if (this.quantidade > 0) {
            for(int i = 0; i < this.quantidade; i++) {
                if (dados[i].compareTo(aux) > 0)
                    aux = dados[i];
            }
        }
        return aux;
    }
}
```

> O **Comparable** permite que você diga uma regra de comparação para a classe que implementar essa **interface**, como uma espécie de regra padrão ou regra oficial - implementada pelo método **compareTo** - enquanto que se você quiser fugir dessa regra padrão, você pode criar suas classes comparadoras, que vão extender a classe **Comparator** fazendo cada uma a sua própria. *Comparação implícita.*

**Comparator** (comparação explícita), uma interface para criar uma ou mais regras de comparação. A única coisa necessária é criar uma classe que implementa ele, e escrever o/os método de comparação. E para utilizar é só passar sua instância e utilizar o método criado de comparação.

E melhor ainda, para não ter que implementar uma classe inteira só para um objetivo tão específico, podemos utilizar a **função lambda** (programação funcionar). Exemplo:

``` java
Comparator<Pessoa> comparadorMatric = 
    (Pessoa p1, Pessoa p2) -> (p1.geMatricula() - p2.getMatricula());
//////////
maiorPessoa = minhaTurma.greatest(comparadorMatric);
```

###### Comparator x Comparable

**Comparable:** Se você tem controle sobre o código-fonte da classe, você pode implementar essa interface nela para definir uma estratégia de ordenação padrão. Exemplo: se você tem uma classe de *Pessoa*, você pode implementar *Comparable* nela definindo uma ordenação pelo nome, pois é um critério muito utilizado para ordenar *Pessoas*, logo, pode ser o padrão (natural).

**Comparator:** É útil quando você precisa criar ordenações personalizadas. Você pode ter uma classe com uma estratégia de ordenação padrão (implementando *Comparable* nela) e em situações que forem necessárias ordenar de forma diferente, criar *n* classes que implementam *Comparator* para atender a esses casos que a ordenação padrão da classe não atenda. Seguindo o exemplo da classe *Pessoa* que ordena por padrão pelo nome, pode acontecer que em uma situação específica você precise ordenar, por exemplo, *Pessoas* por idade decrescente e pelo nome da mãe. Aí você implementa um *Comparator* para esta classe.

Resumo:

- Você tem uma estratégia padrão de ordenação e pode alterar a classe? **Comparable** é uma boa opção.
- Você precisa definir várias estratégias de ordenação ou não tem condições de definir a estratégia padrão de ordenação na classe porquê não pode alterá-la? **Comparator**.

---

## Aula 25 - 07/05

#### Polimorfismo na prática

---

#### Serializable

A **serialização** em Java é o processo no qual a instância de um objeto é transformada em uma sequência de bytes e é útil quando precisamos enviar objetos pela rede, salvar no disco, ou comunicar de uma JVM com outra. Isso porque o estado atual do objeto é “congelado” e na outra “ponta” nós podemos “descongelar” este objeto sem perder nenhuma informação.

Para habilitar a **serialização** de terminada classe você deve explicitamente implementar a interface Serializable. Esta interface é apenas de marcação, pois não tem nenhum método a ser implementado, serve apenas para que a JVM saiba que aquela determinada Classe está hábil para ser serializada.

[Link DevMedia](https://www.devmedia.com.br/use-a-serializacao-em-java-com-seguranca/29012)

---

## Aula 26 - 13/05

#### Prática

---

## Aula 27 - 14/05

#### Programação defensiva

Conceito baseado na noção de direção defenciva: *"Se alguém fizer algo perigoso, você está preparado para evitar consequências. (...) Você assume a responsabilidade pela sua saúde, mesmo que o erro seja do outro motorista."*

Ideia principal na programação: Problemas inevitavelmente acontecerão. Seu código/programa estará preparado para lidar com eles.

<img src="../../imgs/3_Periodo/POO/programation-defencisa.png" style="width:90%">

##### Princípios de McConnell

- "Garbage in, nothing out" (lixo entra, nada sai) - Muito comum em jogos;
- "Garbage in, error message out" (lixo entra, mensagem de erro sai);
- "No garbage allowed in" (Não deixamos nenhum lixo entrar).

###### Verificar dados

*Verificar dados de todas as fontes externas: Arquivos, usuários, rede || Faixas de valores para tipos numéricos (int, float, ...) || Formato de texto em Strings (comprimento, valores restritos, ...). Ou seja, se usar algo de fora, verifique.*

###### Verificar parâmetros

Verificar parâmetros nas chamadas de métodos. Semelhante ao anterior, mas dados vêm de outros locais: métodos, atributos de outras classes ... *Testar o parâmetro dentro da função*.

Evita-se propagação de valores incorretos.

###### Decida previamente o tratamento

Decidir desde o momento do projeto como tratar as entradas que apresentem problemas. Assim que detectado o dado inválido, haja conforme planejado. Cada caso é um caso, diferentes abordagens se adequam a diferentes situações.

:arrow_down:

##### Programação por contrato

Toda interfaces de componentes de software devem ser especificadas de maneira formal, precisa e verificável. No contrato tem especificando o tratamento de erro

- Pré-condições - garante que só entrego o que pediu caso as entradas estiverem conforme o contrato (estipulado na interface). Ou seja, se recebeu tudo certo, deveria retornar corretamente. A premissa é: se eu sei o que receber, eu sei o que testar;
- Pós-condições. A premissa é: se eu sei o que pode sair, eu sei o que testar.
- Invariantes: Condições que não controlamos. Ex: Falha na conexão, servidor fora do ar, dados vazios...

> 1. Método chamado (pré-condições) -> ou executa (pós-condições), ou falha.
> 2. Falha: situação excepcional. *Tratamento varia com o tipo de erro.*

<img src="../../imgs/3_Periodo/POO/programation-por-contrato.png" style="width:90%">

---

## Aula 28 - 20/05

#### Tratamento formal de falhas

- Separa tratamento do erro do código esperado
- Propaga erros na pilha de chamada de funções
- Agrupa e diferencia tipos de erros
- Pode-se produzir Exception ou Erro em Java

#### Exceções

Maneira específica de sinalizar erros ou eventos inesperados a um código. Ajudam a impedir que condições de erro sejam propagadas pelo código.

> Não são ignoráveis

Podem reduzir a complexidade do código e melhorar a legibilidade. *Centralizam o tratamento de problemas.*

> Mas devem ser usadas responsavelmente. Não é só dar um log e seguir a vida.

##### Tratamento de exceções

``` Java
try {
    ... // bloco de código padrão
}
catch (Exception e) {
    ... // bloco de tratamento de erros. Pode ter mais de um.
}
finally { // algumas linguagens oferencem finally
    ... // bloco que será sempre executado
}
```

##### Entendendo exceções

1. Exceção é lançada - *É criado um objeto do tipo da exceção.*
   - Ambiente de execução procura um catch para tratamento desta exceção.
2. Método em execução não tem este catch 
   - Procura-se o tratamento no método que chamou o método atual... e assim sucessivamente
3. Não é encontrado nenhum bloco catch
   - Mensagem de exceção sem tratamento para usuário. Interrompe-se a execução do programa.

##### Como saber qual exception tratar?

1. Ler a documentação da classe/métodos utilizados dentro do bloco que deseja tratar. Geralmente tem informando a exception que pode estourar.
2. Entenda o cenário para conseguir prever o cenário ruim.
3. Quebra a cara e descobre :kissing_closed_eyes:

> Sempre é bom tratar exception em específico, tratamentos personalizados. No último cenário que colocamos um catch com a *Exception* genérica.

<img src="../../imgs/3_Periodo/POO/howException.png" style="width:90%">

> throws -> Na assinatura do método pode ser especificado uma exception com o *throws*. Dessa forma estamos delegando o tratamento dessa exception para o método que utilizar este. 
>
> throw -> Lança uma exceção, mas não exige que ela seja tratada por seus chamadores. Ele **transfere o controle do fluxo** para os métodos chamadores. Ele usa o que se chama *unchecked exception*, ou seja, uma exceção é lançada mas nada obriga ela ser tratada. É tratado em tempo de execução.

##### Se algo deu errado, o que fazer?

Possíveis retorno e tratamentos (cada um terá seus cenários adequados de utilização):

1. Retorno de valor neutro

   - Ao acontecer o problema, retorne um valor neutro, válido, que não cause propagação de erro.

   - Ex: String vazia; Inteiro de valor 0; Ponteiro para elemento *null*.

2. Substituição pelo próximo valor válido

   - Pule para a próxima ocorrência
   - Ex: Playlist de áudio, vídeo ou imagens; Várias leituras de um dispositivo/sensor; Geração de listas e outros conjuntos.

3. Retornar a última resposta válida

   - Repetir a última resposta válida ou ignorar a tentativa atual, mantendo o estado do objeto.
   - Ex: Escolha de um canal inexistente na TV; Usar a mesma textura anterior, caso falte uma textura (por exemplo, uma cena 3D); Manter uma nota em caso de alteração inválida.

4. Atribuição de valor válido próximo
   - Calcular um valor válido próximo e atribuir ao objeto, mantendo sua consistência.
   - Ex: Tentar acertar o relógio para 22h75 -> 22h59; Mudar para um canal não existente (mudar para o primeiro ou para o último); Lançar nota maior que a máxima.
5. Uso de códigos de erro
   - Método usual quando não há exceções
   - Problema principal: semântica do código
   - Ex: Posição -1 ou exceção de objeto não encontrado em uma busca numa coleção?
   - Uso de uma variável de estado e retorno do código de erro no método.
6. Registro de erro em *logs*
   - Caso seja uma condição não tratável:
     - Capturar e tratar a exceção (robustez!)
     - Gerar uma mensagem de log com a ocorrência
   - Evitar:
     - Log de "qualquer coisa"
     - Gravar no log e propagar a exceção

##### Aspectos de desempenho

Tratamento de exceções é demorado. Se um erro pode ser processado localmente, trate-o, ao invés de lançar uma exceção.

Propagação de exceções devem ser evitadas em **casos esperados**: fim de arquivo, por exemplo.

Exceções são úteis quando dados de entrada não podem ser completamente verificados.

---

## Aula 29 - 21/05

#### [Exceções na prática]

---

## Aula 30 - 27/05

#### Princípios SOLID

https://medium.com/desenvolvendo-com-paixao/o-que-%C3%A9-solid-o-guia-completo-para-voc%C3%AA-entender-os-5-princ%C3%ADpios-da-poo-2b937b3fc530

https://www.youtube.com/watch?v=6SfrO3D4dHM

https://medium.com/backticks-tildes/the-s-o-l-i-d-principles-in-pictures-b34ce2f1e898

Pilares da POO para que um projeto siga os princípios que nortearam o surgimento do paradigma.

- Reúso
- Manutenibilidade - Legibilidade
- Flexibilidade
- Extensibilidade

<img src="../../imgs/3_Periodo/POO/SOLID.png" style="width:90%">

##### Single responsibility

"Uma classe deve ter apenas um motivo para mudar"

Uma classe deve ter uma única responsabilidade.

-  "Responsabilidade": motivo para mudança;
- Coesão
- Encapsulamento

:arrow_down:

##### Open/Closed principle

Software deve ser aberto para extensão, mas fechado para modificação.

- Mudanças apenas para correção de código;
- Extensão: classes abstratas e interfaces

Ou seja, o código deve ser estruturado para que qualquer nova funcionalidade que venha ser necessário não tenha que alterar o código original, o fluxo original, somente agragar.

> Refatoração é considerada melhoria.

*Relação com herança e polimorfismo*

:arrow_down:

##### Liskov substitution

Objetos que fazem parte de um programa podem ser substituídos por instâncias de seus subtipos sem prejuízo para a correção do programa. *Relação com herança.*

- Programação por contrato
  - Fornecedor provê produto mediante pagamento
  - Cliente paga pelo produto e o recebe
  - Ambas as partes devem obedecer certas regras
- Fornecedor impõe pré-condições
- Cliente tem a garantia de certas pós-condições
- Invariantes (regras que não variam)

> Violação comum do LSP: verificação de tipo em tempo de execução.
>
> Violação sutil: uso da herança desconsiderando o comportamento. Ex: quadrado herdando de retângulo.
>
> ``` Java
> Rectangle x = new Square(5);
> x.setHeight(8);
> ```

Em resumo: herança deve considerar "é-um" para **comportamento** do objeto.

<img src="../../imgs/3_Periodo/POO/liskov-substituition.png" style="width:90%">

:arrow_down:

##### Interface segregation

Evitar interfaces "pesadas" (violação de coesão).

O acúmulo de funções em uma interface pode torná-la não-coesa e forçar comportamentos não comuns a uma classe.

Segregar o papel da interface

- "Serviço" usado por um outro objeto

> Atenção para herança, composição e associação

<img src="../../imgs/3_Periodo/POO/interface-segregation-1.png" style="width:90%">

<img src="../../imgs/3_Periodo/POO/interface-segregation2.png" style="width:90%">

Melhorou, mas uma porta não tem papel de temporizador.

<img src="../../imgs/3_Periodo/POO/interface-segregation3.png" style="width:90%">

:arrow_down:

##### Dependency inversion

"Módulo de alto nível não devem depender de módulos de baixo nível. Ambos devem depender de abstrações."

- Nenhuma variável deve conter referência para uma classe concreta;
- Nenhuma classe deve derivar de uma classe concreta;
- Nenhum método deve sobrescrever métodos implementados em sua classe base. Somente abstratos.

``` java
// Violação DIP
public class Interruptor
{
  private Ventilador _ventilador;
  
  public void Acionar()
  {
    if(!_ventilador.Ligado)
      _ventilador.Ligar();
    else
      _ventilador.Desligar();
  }
}

public class Ventilador
{  
  public bool Ligado {get; set; }
  
  public void Ligar() { ... }
  
  public void Desligar() { ... }
}

// Princípio aplicado
interface IDispositivo
{
  bool Ligado { get; set; }
  void Acionar();
  void Ligar();
  void Desligar();
}

public class Ventilador : IDispositivo
{  
  public bool Ligado { get; set; }
  
  public void Acionar ()
  {
    if (!this.Ligado)
      this.Ligar();
    else
      this.Desligar();
  }
  
  public void Ligar() { ... }
  
  public void Desligar() { ... }
}

public class Lampada : IDispositivo
{  
  public bool Ligado { get; set; }
  
  public void Acionar ()
  {
    if (!this.Ligado)
      this.Ligar();
    else
      this.Desligar();
  }
  
  public void Ligar() { ... }
  
  public void Desligar() { ... }
}

public class Interruptor
{
  private readonly IDispositivo _dispositivo;
  
  public void AcionarDispositivo()
  {
    _dispositivo.Acionar();
  }
}
```



---

## Aula 31 - 28/05

#### Enumerações

Conjunto de constantes nomeadas para definição de um tipo de dado. Recurso presente nas técnicas e linguagens mais básicas de programação, ou seja, não é algo próprio do POO.

Em java, ganha características de tipo abstrato de dados.

- Conjunto de constantes
  - Um objeto do tipo enumerável só pode representar um dos valores definidos no conjunto.
- Útil se um tipo possui um número fixo de valores + válidos pré-definidos.

##### Exemplos

1. Código de status
   - Aluno aprovado, reprovado, em exame especial...
   - Pedido faturado, pendente, em rota de entrega...
2. Códigos de erro
   - Sucesso, valor inválido, arquivo não encontrado...
3. Valores conhecidos pré-definidos
   - Dias da semana
   - Meses do ano
   - Classificação de livros (CDD)
   - Cores/modelos de um produto

#### Enum em Java

Lista de identificadores de valores:

- Identificadores são membros de classe público do tipo enumerável definido;
- Tipo / classe dos identificadores é o mesmo tipo/classe definida pelo enum;
- Por padrão, costuma-se usar letras maiúsculas nos nomes de valores enumeráveis. 

``` Java
public enum Naipe {
    COPAS,
    OURO,
    PAUS,
    ESPADAS
}
```

##### Enum e TAD 

*Tipo abstrato de dados*.

Enumerações em Java são tipos de classe. Tem comportamento semelhante a classes de Java.

Têm propriedades que enumerações não têm em outras linguagens de programação.

- Construtores e outros métodos;
- Atributos de instância;
- Implementação de interfaces.

> Em Java: Enumerações herdam implicitamente de *Enum*, que por sua vez implementa Serializable e Comparable.
>
> - ordinal()
> - compareTo(enumeravel)
> - valueOf(valor)
>   - name()
> - values()

E melhor, podem ser declarados atributos para os tipos enumeráveis.

- Construtores devem associar valores a estes atributos.
- Construtores são executados no momento da declaração do enumerável na programa. :

```Java
public enum Naipe {
    COPAS("♥"),
    OURO("♦"),
    PAUS("♣"),
    ESPADAS("♠");
    
    private String simbolo;
    private String cor;
    
    Naipe(String simb) {
        this.simbolo = simb;
    }
    
    @Override
    public String toString() {
        return this.simbolo;
    }
    
    public String cor() {
        String nome = this.name().toLowerCase();
        
        switch(nome) {
            case "copas":
            case "ouros":
                return "Vermelho";
            default:
                return "Preto";
        }
    }
}
```

##### Enumeráveis x constantes

Se temos enumeráveis, continuamos usando valores constantes (static final)?

SIM! São coisas diferentes:

- Constantes: valor constante usado por objetos;
- Enum: listas de valores possíveis.
  - Operações associadas.

---

## Aula 32 - 04/06

#### Coleções em Java - JCF Streams

Coleções são objetos que representam um grupo de objetos tratados como uma única entidade. Ou seja, conseguimos fazer operações na coleção inteira.

Java collection framework (JCF)

- Arquitetura de componentes para permitir manipulação de coleções de maneira independente e abstrata.

##### JCF Objetivos

- Promoção do reuso de componentes de software
- redução do esforço de programação
- Favorecer desempenho
- Interoperabilidade entre sistemas diferentes

##### JCF Recursos

- Interfaces e implementações genéricas (listas, tabelas, ... genéricas)
- Implementações legadas (retrofit)
- Implementações concorrentes
- Algoritmos comuns (.sort, ...)

<img src="../../imgs/3_Periodo/POO/jcf-colecoes.png" style="width:90%">

<img src="../../imgs/3_Periodo/POO/JCF-Recursos.png" style="width:90%">

#### Streams

<img src="../../imgs/3_Periodo/POO/streams1.png" style="width:90%">

<img src="../../imgs/3_Periodo/POO/streams2.png" style="width:90%">

<img src="../../imgs/3_Periodo/POO/streams3.png" style="width:90%">

##### Streams x Coleções

<img src="../../imgs/3_Periodo/POO/streams-colecoes.png" style="width:90%">

##### Exemplo 

<img src="../../imgs/3_Periodo/POO/exemplo1_streams.png" style="width:90%">

<img src="../../imgs/3_Periodo/POO/exemplo2_stream.png" style="width:90%">

---

## Revisão atividades - 10/06

<img src="../../imgs/3_Periodo/POO/revisaoAtividades10-06.png" style="width:90%">

