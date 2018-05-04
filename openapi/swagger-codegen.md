# Swagger Codegen

Swagger codegen provies a rich [README](https://github.com/swagger-api/swagger-codegen) which is very easy to understand.

<!-- vim-markdown-toc GFM -->

* [How to run the public Docker image.](#how-to-run-the-public-docker-image)
* [How to show options for each language.](#how-to-show-options-for-each-language)

<!-- vim-markdown-toc -->


## How to run the public Docker image.

- https://hub.docker.com/r/swaggerapi/swagger-generator/ (official web service)
- https://hub.docker.com/r/swaggerapi/swagger-codegen-cli/ (official CLI)

```sh
docker run --rm -v ${PWD}:/local swaggerapi/swagger-codegen-cli \
  generate \
  -l go \
  -i https://api.slack.com/specs/openapi/v2/slack_web.json \
  -c /local/config-go.json \
  -o /local/api
```

`config-go.json` is composed of keys and values described by `config-help` command.

## How to show options for each language.

Use config-help

```sh
docker run --rm -v ${PWD}:/local swaggerapi/swagger-codegen-cli config-help -l go
```

It shows the list of avaiable options like below.
```
CONFIG OPTIONS
  packageName
    Go package name (convention: lowercase). (Default: swagger)

  hideGenerationTimestamp
    Hides the generation timestamp when files are generated. (Default: true)

  packageVersion
    Go package version. (Default: 1.0.0)

  withXml
    whether to include support for application/xml content type and include XML annotations in the model (works with libraries that provide support for JSON and XML) (Default: false)
```
