# OpenAPI misc
Not organized notes on Swagger/OpenAPI.

# FAQ from Me.

## What's the difference between Swagger and OpenAPI?

OpenAPI is the new open organization taking over Swagger.

## Should we use OpenAPI v3?

No. Probably we should use its older major version, v2 for now.
v2.3.1 might be the latest version available.

There's no JSON Schema for each minor version of v2 in their repository https://github.com/OAI/OpenAPI-Specification/tree/master/schemas but [swagger-codegen](https://github.com/swagger-api/swagger-codegen) seems support upto v2.3.1 (but not v2.4.0) 

They announced that the version 3.0 is ready on [their blog post](https://swagger.io/blog/announcing-openapi-3-0/)
In the blog post thay says that

    In the short term — nothing. You can continue to use Swagger 2.0 with any of the Swagger tooling, SwaggerHub, or any other platform that supports the 2.0 spec. We will continue to support the use of 2.0 specs for the foreseeable future.
    We are working on tools to help in the process on transitioning to 3.0 now, so keep an eye out for what’s coming next.

https://github.com/OAI/OpenAPI-Specification/tree/master/schemas

As the blog said, [the specification of version 3.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md) has been ready but its' JSON Schema (or something new integrated with it) seems not yet in [their git repository](https://github.com/OAI/OpenAPI-Specification/tree/master/schemas).



## How to run Swagger editor on my local env?

Run their Docker image with the following command and access http://localhost:8001.

```sh
PORT=8001
docker run -d -p "${PORT}":8080 swaggerapi/swagger-editor
```

The docker image named `swaggerapi/swagger-editor` is distributed via [DockerHub](https://hub.docker.com/r/swaggerapi/swagger-editor/)
and here's [its github repository.](https://github.com/swagger-api/swagger-editor)

## How to customize my (Java/Golang etc) code that swagger-codegen generates?

See the code around them.
- https://github.com/swagger-api/swagger-codegen/tree/master/modules/swagger-codegen/src/main/java/io/swagger/codegen/languages
- https://github.com/swagger-api/swagger-codegen/tree/master/modules/swagger-codegen/src/main/resources

## How to validate the written API document?

Use [pajv](https://www.npmjs.com/package/pajv), and [their JSON Schema](https://github.com/OAI/OpenAPI-Specification/blob/master/schemas/v2.0/schema.json).

```sh
curl https://raw.githubusercontent.com/OAI/OpenAPI-Specification/master/schemas/v2.0/schema.json -o schema.json
pajv -s schema.json -d your-swagger.yaml
```


