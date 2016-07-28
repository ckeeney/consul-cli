# consul-cli

This is a fork of [Cisco's consul-cli client](https://github.com/CiscoCloud/consul-cli).  

You can set the --consul command line flag with the environment variable `CONSUL_CLI_CONSUL`.
 
## Example docker-compose.yml:
```yml
# docker-compose.yml
version: '2'

services:
  consul:
    image: consul
    command: agent -server -dev

  consul-cli
    image: cliffordkeeney/consul-cli
    depends_on:
      - consul
    environment:
      - CONSUL_CLI_CONSUL=consul:8500
    command: agent members
```
 
 and running `docker-compose run consul-cli agent members` just works.
 
 Support for setting other consul-cli options via environment variables is not yet done.
 
 Below is the original readme from [https://github.com/CiscoCloud/consul-cli](https://github.com/CiscoCloud/consul-cli) 
 

[![Build Status](https://travis-ci.org/CiscoCloud/consul-cli.svg)](https://travis-ci.org/CiscoCloud/consul-cli)

Command line interface to [Consul HTTP API](https://consul.io/docs/agent/http.html)

## Subcommands

| Command | Synopsis |
| ------- | -------- |
| [acl](https://github.com/CiscoCloud/consul-cli/wiki/ACL) | Consul /acl endpoint
| [agent](https://github.com/CiscoCloud/consul-cli/wiki/Agent) | Consul /agent endpoint
| [catalog](https://github.com/CiscoCloud/consul-cli/wiki/Agent) | Consul /catalog endpoint
| [check](https://github.com/CiscoCloud/consul-cli/wiki/Check) | Consul /agent/check endpoint
| [coordinate](https://github.com/CiscoCloud/consul-cli/wiki/Coordinate) | Consul /coordinate endpoint
| [health](https://github.com/CiscoCloud/consul-cli/wiki/Health) | Consul /health endpoint
| [kv](https://github.com/CiscoCloud/consul-cli/wiki/KV) | Consul /kv endpoint
| [service](https://github.com/CiscoCloud/consul-cli/wiki/Service) | Consul /agent/service endpoint
| [session](https://github.com/CiscoCloud/consul-cli/wiki/Session) | Consul /session endpoint
| [status](https://github.com/CiscoCloud/consul-cli/wiki/Status) | Consul /status endpoint
