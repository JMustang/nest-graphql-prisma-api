<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest


# Implementando um servidor GraphQL usando Prisma, SQLite e Nest.js com Typescript

Nest.js é construído em Node.js e Express, que é sem dúvida a forma mais popular de construir servidores com JavaScript. Nest.js é uma estrutura JavaScript baseada em TypeScript para desenvolver e dimensionar microsserviços de back-end.

Sendo digitado estaticamente com TypeScript, ele permite que você execute várias tarefas JavaScript como uma escotilha de escape. Isso garante que seu código seja mais sólido.

Além disso, torna o código mais fácil de navegar. Isso ocorre porque tudo é fortemente tipado e mais escalável para grandes aplicativos. Isso fornece uma arquitetura de aplicativo pronta para uso que permite que desenvolvedores e equipes construam aplicativos altamente testáveis, escaláveis, pouco conectados e de fácil manutenção.

O Nest.js, como outros frameworks de back-end, foi projetado para oferecer uma experiência semelhante ao Angular. Como resultado, ao criar um novo aplicativo Nest.js, você será iniciado em um ambiente semelhante a um aplicativo Angular de front-end normal.

A principal diferença é que o que você acaba criando serão seus serviços de back-end. Você vai configurar um servidor, vinculá-lo a bancos de dados e fazer todas as tarefas típicas associadas a um aplicativo baseado em back-end.

# GraphQL

GraphQL é uma linguagem de consulta para acessar e modificar dados em APIs (fontes de dados interconectadas). É compatível com uma variedade de linguagens do lado do servidor, incluindo Next.js. O **GraphQL** permite consultar seus dados e receber os resultados necessários.

Você pode consultar vários recursos relacionados em uma única solicitação usando o **GraphQL**. Em outras palavras, você pode consultar relacionamentos. O **GraphQL** também permite consultar itens relacionados e receber uma resposta no mesmo formato da consulta.

Assim, ele é usado para carregar dados do servidor para o aplicativo cliente. Ele permite que você obtenha dados da API em seu aplicativo com mais eficiência do que métodos e serviços tradicionais, como SOAP e REST.

Por exemplo, se você estiver usando REST para acessar dois recursos, precisará de dois endpoints diferentes para solicitar dados de cada recurso. Isso também significa que quando uma solicitação é recebida, a API responde com toda a carga útil de dados dessa entidade. O **GraphQL** permite acessar muitos recursos com uma única solicitação.

O **GraphQL** possui um sistema de tipos que permite definir um esquema para seus dados. Por exemplo, um gráfico composto de nós e arestas pode ser usado para representar os dados em seu aplicativo. Os nós representam objetos. As arestas representam a relação entre esses objetos. Eles refletem os dados e os relacionamentos entre os dados em seu aplicativo.

O benefício do **GraphQL** é que ele permite que os clientes peçam exatamente o que desejam. Nada mais ou nada menos. Além disso, como não há dados redundantes, as solicitações e respostas são rápidas.

# Prisma

**Prisma** possui uma boa linguagem de modelagem para criar seu banco de dados. Ele também possui um robusto **GraphQL** ORM (mapeamento relacional de objetos) para trabalhar com bancos de dados em JavaScript. Além disso, facilita o desenvolvimento de APIs **GraphQL** com um banco de dados. Trabalhar com o **GraphQL** permite que os desenvolvedores busquem dados em seus aplicativos, enquanto o **Prisma** simplifica o processo de conexão de fontes de dados.

**Prisma** tem a vantagem de ser independente de banco de dados. Ele funciona com bancos de dados relacionais (SQL) e não relacionais (NoSQL), incluindo MySQL, PostgreSQL e MongoDB. Isso implica que podemos selecionar rapidamente um banco de dados ou trocar entre bancos de dados. Sem alterar nenhum código (talvez cerca de seis linhas que você deseja configurar para se conectar ao banco de dados específico).

O **Prisma** envolve seu banco de dados e o expõe como uma API **GraphQL**. Como resultado, ele fornece uma API **GraphQL** que pode ser usada para ler e gravar no banco de dados real, independentemente de estarmos usando SQL ou NoSQL.

# Objetivos

O guia se concentrará em colocar e executar um projeto de servidor simples. Usaremos tecnologias como **Prisma**, **Nest.js**, **GraphQL** e **SQLite** como banco de dados do projeto. Criaremos uma API **GraphQL** de postagens simples com todas as operações CRUD suportadas.

# Instalando a CLI do Nest.js

Nest.js fornece uma interface de linha de comando (CLI) que permite a criação de projetos e arquivos por meio da linha de comando. Um dos principais objetivos da CLI da estrutura Nest.js é fornecer aos desenvolvedores de back-end uma estrutura de código modular.

Isso ajuda no desenvolvimento e manutenção de padrões de arquitetura de software de negócios em grande escala. Além disso, ele fornece injeção de dependência diretamente da caixa para promover programas bem estruturados.

Executa o seguinte comando para instalá-lo globalmente.

```bash
npm i -g @nestjs/cli
```

inicializar um projeto Nest.js.

```bash
# voce pode nomear como achar melhor.
# depois de "nest new" ponha o nome do projeto.
nest new nest-graphql-prisma-api
```

O comando acima nos ajudará na estruturação do projeto. O comando gerará um projeto inicial do TypeScript e solicitará os detalhes do projeto, como nome, descrição, número da versão, cujo padrão é 0.0.0 e autor (provavelmente seu nome).

Ao concluir este procedimento, você terá um aplicativo Nest.js totalmente configurado. Incluindo todas as dependências instaladas no diretório **node modules**.

Ao executar o comando acima, você ainda pode selecionar o gerenciador de pacotes que deseja usar, que é **yarn** ou **npm**.

Quando o processo de instalação estiver concluído, uma pasta nest-graphql-prisma-api com todas as dependências do Nest.js será criada dentro do caminho que você executou o comando acima.