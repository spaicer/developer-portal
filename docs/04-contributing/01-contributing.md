# Contributing a New AI Module or SRS

Contributors of new AI modules should consider the requirements described here to enable their on-boarding into the SPAICER platform. 

## Containerisation

AI modules must be packaged as containers based on the Open Container Initiative (OCI) standard (i.e., docker).
For this, the module must specify a Dockerfile which supports building container images.
The container should expose a standard HTTP(S) port (80 or 443) to enable the integration of the provided services. Ports like 8080 are also accetable.

The open port must expose an API based on OpenAPI. A Swagger-UI is quite desirable.

An example implementation of a continuous integration / continuous delivery (CI/CD) pipeline based on GitHub Actions is provided [here](./resources/publish-container.yaml). 

### Example Container

The example container provides an example for Node.js and for Python.
* https://github.com/spaicer/example-container

## Publishing

Container images must be published to an OCI-compliant registry accessible from the Internet.
We encourage the publication of images to the GitHub Container registry of the spaicer *(ghcr.io/spaicer/)* organization. 

An example implementation of a continuous integration / continuous delivery (CI/CD) pipeline based on GitHub Actions is provided [here](./resources/publish-container.yaml).

## Dependencies

Ideally, new AI modules should only reuse standard SPAICER runtime components based on the HTTP(S) protocol:
* Basic SPAICER platform services
* Other SPAICER AI modules

Dependencies on other runtime components should be requested by creating a new GitHub issue within the developer portal repository.

## Documentation

Any dependency to runtime components such as SPAICER platform services should be documented in the source repository of the AI module.

## Self-Description

### OpenAPI specification

AI modules should provide a self-description of the provided services based on the OpenAPI specification .

### Gaia-X

In oder to deliver a Gaia-X compliant platform and services, AI modules should additionally provide a Gaia-X self-description.
(cf. the [Gaia-X Architecture Document](https://www.gaia-x.eu/sites/default/files/2021-10/Gaia-X_Architecture_Document_2109.pdf)). 