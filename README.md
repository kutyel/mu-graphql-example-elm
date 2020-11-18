# mu-graphql-example-elm 🌳

![Elm CI]

![preview]

This Elm example aims to demonstrate how to implement both frontend and backend in a schema-first, typesafe, and functional way.

To run this example, you need to run the [GraphQL server] example (with [Stack]):

```sh
$ cd backend && stack run library
```

And, in another terminal, this project:

```sh
$ cd frontend && yarn && yarn codegen && yarn start
```

## This example demonstrates how to use:

- [x] Queries
  - Combine queries and selection sets (search authors by name and books by title)
  - Handle errors and loading state
- [x] Mutations
  - Create a new entity related to an existing one (submit a book with an existing author)
  - Compose Tasks to create several new entities with relations (submit a book with a new author)
- [x] Subscriptions
  - Subscribe and unsubscribe with GraphQL via Elm ports and WebSocket API
  - Build GraphQL queries and decode arbitrary JSON strings using the same generated `SelectionSet`s

## This example does not demonstrate:

- User input ~~validation~~ parsing best practices
- Routing best practices
- Debouncing user input
- Client-side validation before submitting a form

## Other technical notes:

- [elm-graphql] also supports code-generation from introspection files, local schema files, and remote servers with introspection enabled _(it usually is)_.
- both [elm-graphql] and [elm-app] can be installed as global dependencies, but we don't consider it a good practice, because it immediately becomes harder to maintain versions.
- old generated files are removed by [elm-graphql] automatically, we don't need to worry about it.

  [elm ci]: https://github.com/kutyel/mu-graphql-example-elm/workflows/Elm%20CI/badge.svg
  [preview]: docs/preview.png
  [mu-haskell]: https://github.com/higherkindness/mu-haskell
  [stack]: https://docs.haskellstack.org/en/stable/README/#how-to-install
  [elm-graphql]: https://github.com/dillonkearns/elm-graphql/
  [elm-app]: https://github.com/halfzebra/create-elm-app
