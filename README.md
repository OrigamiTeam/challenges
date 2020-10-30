# jr-fullstack-challenge

Bem vindo ao desafio de programação fullstack React + Node.js.

Pedimos que leia todas secções deste roteiro com atenção para maximizar suas chances de sucesso.

O teste a realizar consiste em elaborar uma forma de interação com uma playlist de músicas, respeitando algumas regras estabelecidas no plano contratado pelo utilizador. A implementação deve ser composta por duas aplicações:

1) Uma aplicação Web, utilizando React
2) Uma aplicação Backend, em Node

## Sumário

- [Roteiro](#roteiro)
- [Parâmetros da Avaliação](#parâmetros-de-avaliação)
- [Regras de Negócios](#regras-de-negócio)
- [Requisitos](#requisitos)

## Roteiro

O tempo disponível é de 48 horas para entregar o melhor software possível atendendo aos requisitos descritos nas próximas seções, respeitando os critérios tanto de completude quanto corretude. Seu desafio deverá ser disponibilizado por meio de um repositório pessoal de sua escolha (GitHub, Gitlab, BitBucket, etc). Ao finalizar, favor nos enviar um email juntamente com o link do repositório.

## Parâmetros de Avaliação

A avaliação do código será feita de acordo com os seguintes parâmetros em ordem de importância decrescente:

- Ausência de bugs
- Responsividade
- Código respeitando os princípios do React (sugestão de leitura: [Thinking in React](https://reactjs.org/docs/thinking-in-react.html))
- Formatação consistente e legível
- Clareza (objetividade)
- Desacoplamento
- Extensibilidade
- Manutenibilidade

### Opcionais

Os pontos a seguir são opcionais, mas apreciamos vê-los:

- Testes automatizados
- Documentação
- Demais tooling de desenvolvimento (como lint e CI/CD)
- Sistema deployed
- Tratamento de exceções

## Regras de negócio

O nosso sistema tem como finalidade permitir que os clientes reproduzam músicas ambientes em estabelecimentos comerciais, como supermercados, restaurantes, etc. Para tal, os **clientes** se associam a um determinado **plano** que provê um conjunto específicos de **músicas** que podem ser adicionadas numa **playlist**. Cada plano também deve estatabelecer uma quantidade máxima de músicas que pode ser adicionada.

Considere que para a primeira versão o sistema tenha esses dois **planos** possíveis:

| Plan   | Playlist size |
|--------|---------------|
| Basic  | 3             |
| Gold   | 5             |

Considere que tenhamos as seguintes **músicas** disponíveis:

| Music    | Plan  |
|----------|-------|
| Orient   | Basic |
| Chiptune | Gold  |
| EDM      | Basic | 
| Chillout | Gold  |
| Dubstep  | Gold  |
| Winter   | Basic |
| Summer   | Basic |
| Ocarina  | Gold  |

Todas as músicas do plano `Basic` também são disponíveis para utilizadores do plano `Gold`, e as músicas do plano `Gold` não são disponíveis para o plano `Basic`.
Nós sabemos que o sistema pode crescer e novos planos podem ser adicionamos no futuro.

## Requisitos

### Frontend

### Frontend adminstrativo

Precisamos de um frontend em um utilizador com permissões de acesso `admin` possa adicionar novas músicas aos planos já existentes e cadastrar novos clientes.

- Para o cadastro de música, deve ser possível inserir num formulário o nome da música e o plano associado.
- Para o cadastro de um cliente, deve ser fornecido o email, senha e o plano dele.

### Frontend para os clientes

Precisamos também de um frontend para os clientes, em que ele possa efetuar login, visualizar todas as músicas disponíveis no sistema, e selecionar as músicas que deseja salvar na playlist dele. Lembre-se de respeitar os limites do plano dele e deixar explícito na experiência do utilizador.

### Interface

Não há exigência de layout em que a interface deve ser apresentada. O importante é atentar para as consequências de usabilidade de suas escolhas. Algumas idéias:

- pode-se exibir uma tabela com as músicas e checkbox para selecionar a música a ser tocada na playlist
- pode-se atualizar a playlist com drag and drop

### Backend

Alguns requisitos quanto às tecnologias a serem usadas no backend:

- Precisa ser desenvolvido com Node.js
- Precisa usar o banco de dados Postgres
- Deve prover uma api REST ou GraphQL
