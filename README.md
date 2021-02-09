# Using redocly to hide internal APIs (using swagger petstore example)

This is the swagger petstore with one additional custom tag -- x-internal -- that can be used to generate openapi specs with and without internal APIs. The details of how this works are described [here](https://redoc.ly/docs/resources/hide-apis/)

To run this example, first [install openapi-cli](https://redoc.ly/docs/cli/) from Redocly (requires npm):

```
npm install -g @redocly/openapi-cli
```

Then run the following commands from this directory:

```
openapi bundle -o dist/external.json src/main/resources/openapi.yaml
openapi bundle --skip-decorator=internal/remove-internal-operations -o dist/internal.json src/main/resources/openapi.yaml
```

Two openapi specs will be generated, `dist/internal.json` and `dist/external.json`

