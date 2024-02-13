
![Domain Driven Design não é para qualquer time !](https://media.licdn.com/dms/image/C4E12AQGg_xiTXf4mvA/article-cover_image-shrink_720_1280/0/1635337494376?e=2147483647&v=beta&t=kDfNvjpvLQc8NzuRp18L49cuJLiBFb2OrBUJvL76-Mk)

# **Domain Driven Design (DDD)**
O DDD não se limita especificamente à arquitetura ou à tecnologia; trata-se mais de uma filosofia que enfatiza o desenvolvimento de software orientado pelos aspectos do negócio e a concentração na entrega de valor.

Em resumo, o DDD tem o objetivo de atacar a complexidade no coração do software.

## Como remover a complexidade da aplicação?

Para isso, precisamos nos basear nos **3 pilares**.
 - **Linguagem universal** - ubiqua, ela se refere a documentação do codigo fonte e do processo de comunicação com o cliente.
 -  **Visão tática** - é nesse momento que atacamos o coração do software, levantando as complexidades do negocio e as complexidades técnicas.
 - **Visão estratégica** - foca na definição de contextos limitados e subdomínios, organizando o sistema para alinhar com os objetivos do negócio e facilitar a integração e comunicação entre equipes.

**Observação:** acredito que as os pilares de visão estratégica e tática estão interligadas.

## Como essa filosofia do DDD é aplicada no mundo real?
Precisamos entender a **linguagem** da empresa, fazer um software é mudar como as pessoas trabalham, dito isso, levantamento de requisito, descobrir o problema principal a se suprir, formas de falar, agir e reagir.

Dai leva o pensamento, se você realmente sabe o que é DDD, que não é apenas criar pastas escrito Domain, Application e Infra.

Então vamos por partes, o que seria o Domain? Basicamente é a razão do negocio existir, o coração, mas para ele funcionar temos muito chão pela frente.
Uma das soluções é transformar o dominio em subdominios e a partir disso aplica o **Bounded context**.


### Uma pausa rápida para explicar o que é Bounded context (contexto limitado)
São uma maneira de delimitar fronteiras lógicas entre diferentes subdomínios de um sistema, cada um com suas próprias regras, terminologias e modelos conceituais
  
**Exemplo:** Existem dois setores fundamentais: **Vendas** e **Logística**. Esses dois Bounded Contexts operam com suas próprias regras de negócio e modelos de domínio. **Vendas** é responsável por montar um pedido, enquanto **Logística** cuida do envio do pedido. Apesar de suas diferenças, eles estão integrados entre si através de conceitos compartilhados, como o **Pedido**, permitindo uma operação coesa.

### Como eu consigo delimitar os meus contextos?
Delimitar contextos não é simples; há sempre uma zona cinza sem respostas claras e diversos caminhos possíveis, com muitos aspectos implícitos envolvidos.

![Domain-Driven Design — Contextos Delimitados | by Diego Moura | Medium](https://miro.medium.com/v2/resize:fit:772/1*hgkRmH3OO9-yCu1JhPDteA.png)

### Quais sao os sinais que você está em um contexto X ou no contexto Y?
 Em resumo, quando utiliza nomes diferentes para descrever a mesma coisa.
 - Em uma empresa B2B, diferentes departamentos referem-se ao mesmo usuário de maneiras distintas: enquanto a empresa e o setor financeiro chamam o usuário de "cliente", os especialistas referem-se a ele como "aluno". Isso ilustra que, às vezes, coisas iguais são conhecidas por nomes diferentes. Por outro lado, pode ocorrer o inverso, onde coisas diferentes recebem o mesmo nome.

 ## Mas afinal, o que essas tantas faladas pastas significam?
**Domain** - Regra de negocios, calcular taxa de juros  
**Application** - Gerenciar fluxo da aplicacao, receber um valor a financiar, chamar o dominio, calcular juros, gravar no banco e enviar um email.
**Infraestrutura** - Mundo externo. Banco de dados, envio de email, publicacao na fila, caching


## Dominio anemico x Dominio rico
**Domínio Anêmico** - é caracterizado por modelos com pouca ou nenhuma lógica de negócios, atuando principalmente como transportadores de dados (Uso apenas de GetSet). 
**Domínio Rico** - incorpora a lógica de negócios diretamente nos modelos, promovendo um design orientado ao comportamento que facilita a manutenção e a evolução do sistema. 

A escolha entre um domínio anêmico e um rico impacta diretamente na expressividade e na capacidade de encapsulamento da lógica de negócios da aplicação.
 


#### Algumas palavras chaves do DDD, que ajudam a solucionar problemas de dominio
 - Agregados
 - Entidades
 - Objetos de valor
 - Servicos de dominio
 - Eventos de dominio
 - Repositorios
 - DTO


### Vamos falar um pouco mais sobre o Aggregate root
Um **Aggregate Root** é uma entidade central dentro de um Aggregate, que agrupa objetos associados e garante a consistência das operações realizadas sobre esse grupo.

**Exemplo:** Em uma loja virtual serve como exemplo perfeito: ao adicionar itens ao carrinho, o Pedido atua como o Aggregate Root. Ele é a entidade principal que encapsula e controla o acesso aos itens relacionados, conduzindo todas as operações pertinentes, como adição de itens e cálculo do total. De maneira similar, em uma biblioteca onde um usuário deseja pegar livros emprestados, o **Usuário** se torna o Aggregate Root, centralizando o controle sobre as operações de empréstimo.


#### Por fim, uma reflexão em realação ao que foi estudado
A gente usa clean code, padrões de projeto, DDD, mas utilizamos isso porque sabemos que no final do dia temos que resolver o problema do cliente.
