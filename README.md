# Java Efetivo
Repositório com utilidades  e resumos relacionados ao livro que achei úteis e utilizarei no meu dia a dia.

# Templates

Disponibilizei templates, para o eclipse, que auxiliam a criação de classes e métodos baseados nos 3 primeiros capítulos do livro

## Como importar os Templates no Eclipse

- Window
- Preferences
- Java -> Editor -> Templates -> Import
- Selecionar arquivo templates-java-efetivo.xml

## Como utilizar os Templates

- Crie um arquivo java com o nome final e no pacote correto
- No arquivo criado, digite o caracter 'v' e em seguida 'control + espaço'

# Itens mais importantes

## Item 17: Reduza a mutabilidade das classes ao mínimo
1. Não forneça métodos que modificem o estado do objeto
2. Garanta que a classe não possa ser estendida
3. Faça com que todos os campos sejam finais
4. Faça com que todos os campos sejam privados
5. Garanta o acesso exclusivo a quaisquer componentes mutáveis

## Item 18: Prefira a composição à herança
1. Exemplo do Livro é: Criar um Set que armazene quantos elementos foram adicionados desde sua criação. (Resposta: Classe Wrapper)
2. Exemplo de implementação ruim de Herança: Properties

## Item 23: Dê preferência às hierarquias de classes em vez das classes tagged
1. Exemplo de implementação ruim: Classe Figura com um atributo Shape. Necessitando assim de um switch no método area

## Item 31: User os wildcards limitados para aumentar a flexibilidade da API
Como o título remete, é principalmente para definição de APIs.

Para métodos produtores, ou seja, que consomem elementos de uma lista, utilize **Collection<? extends E>**

Para métodos consumidores, utilize **Collection<? super E>**

## Item 39: Prefira as anotações aos padrões de nomenclatura
Desvantagens dos padrões de nomenclatura:
1. Erros de digitação provocam erros silenciosos
2. Não é possível assegurar que sejam utilizados nos elementos certos da aplicação.
3. Não fornecem uma boa maneira de associar os valores de parâmetros aos elementos do programa
   
## Item 41: Use as interfaces marcadoras para definir tipos
1. Se uma anotação for do tipo Type, avalie se não deveria ser uma interface marcadora.
2. Caso a anotação seja aplicada apenas as implementações de uma classe específica, interface marcadora é ideal.
3. Vai existir um ou mais métodos que deve receber apenas um tipo? Utilize Interface Marcadora.

## Item 42: Prefira os lambdas às classes anônimas

## Item 43: Dê preferência às referências para métodos em vez dos lambdas

| Tipo de referência        | Exemplo| Lambda correspondente  |
| ------------- |:-------------:| -----:|
| Estática      | Integer::parseInt | str -> Integer.parseInt(str) |
| Limitada      | Instant.now()::isAfter      |   Instant then = Instant.now(); t -> then.isAfter(t) |
| Ilimitada | String::toLowerCase      | str -> str.toLowerCase() |
| Construtor de classe      | TreeMap<K,V>::new |   () -> new TreeMap<K,V> |
| Construtor de array | int[]::new      |   len -> new int[len] |

## Item 44: Prefira o uso das interfaces funcionais padrão

Ex: UnaryOperator, BinaryOperator, Predicate, Function, Supplier, Consumer.
