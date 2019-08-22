# sequelize-to-json-schemas

Convert Sequelize models into various JSON Schema variants. Uses the Strategy Pattern.

## Available Strategies

- JSON Schema v7
- OpenAPI v3

> More strategies welcome, [examples found here](https://github.com/alt3/sequelize-to-json-schemas/tree/master/lib/strategies)

## Installation

```bash
npm install @alt3/sequelize-to-json-schemas
```

## Example

```javascript
const { SchemaManager, JsonSchema7Strategy, OpenApi3Strategy } = require('sequelize-to-json-schema');
const schemaManager = new SchemaManager();

// generate a JSON Schema Draft-07 model schema
let schema = SchemaManager.generate(userModel, new JsonSchema7Strategy());

// and/or the OpenAPI 3.0 equivalent
schema = SchemaManager.generate(userModel, new OpenApi3Strategy());
```

## Additional Information

- understandable code
- compatible with Sequelize v4 and v5
- generates valid schemas (test suite using [ajv](https://github.com/epoberezkin/ajv) and [Swagger Parser](https://github.com/APIDevTools/swagger-parser) validators)

## License

This project is released under [MIT LICENSE](LICENSE.txt).

## Contributing

Please refer to the [guidelines for contributing](./CONTRIBUTING.md).
