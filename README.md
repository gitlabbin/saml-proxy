# saml-proxy

A SAML 2.0 auth providing reverse proxy with fancy features like roundrobin
load balancing, a buffer for retrying requests, a Hystrix-style circuit breaker,
and rate limiting.

Credit where credit is due:
- github.com/crewjam/saml for the fantastic SAML+ library
- github.com/vulcand/oxy for most of the higher-level network components

## Roadmap
- Add optional mutual TLS authentication
- Support custom entity descriptor

## Get up and running
Install deps:
`dep ensure`

Build:
`go build`

Configure your stuff based on `config.yaml.example`

Create your cert and key

```openssl req -x509 -newkey rsa:2048 -keyout myservice.key -out myservice.cert -days 365 -nodes -subj "/CN=myservice.example.com"```

Compile and run with path to `config.yaml` as the first argument
