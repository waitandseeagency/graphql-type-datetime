# graphql-type-datetime [![npm version](https://badge.fury.io/js/graphql-type-datetime.svg)](http://badge.fury.io/js/graphql-type-datetime)

DateTime scalar type for [GraphQL.js](https://github.com/graphql/graphql-js), following the ISO 8601 format.

Ex: `2018-05-28T10:26:39.359Z`

## Usage

This package exports a DateTime scalar GraphQL.js type:

```js
import GraphQLDateTime from 'graphql-type-datetime';
```

### SDL with [GraphQL-tools](https://github.com/apollographql/graphql-tools)

When using the SDL with GraphQL-tools, define `GraphQLDateTime` as the resolver for the appropriate scalar type in your schema:

```js
import { makeExecutableSchema } from 'graphql-tools';
import GraphQLDateTime from 'graphql-type-datetime';

const typeDefs = `
scalar DateTime

type MyType {
  myField: DateTime
}

# ...
`;

const resolvers = {
  DateTime: GraphQLDateTime,
};

export default makeExecutableSchema({ typeDefs, resolvers });
```


## Dependency

To validate and parse the date with an ISO 8601 format, this library uses [Moment.js](https://github.com/moment/moment)

## Related

This repository is inspired by [graphql-type-json](https://github.com/taion/graphql-type-json) and [graphql-iso-date](https://github.com/excitement-engineer/graphql-iso-date)
