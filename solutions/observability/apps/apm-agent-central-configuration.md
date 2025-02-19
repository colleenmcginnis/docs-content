---
navigation_title: "Centrally configure APM agents in Kibana"
mapped_pages:
  - https://www.elastic.co/guide/en/observability/current/apm-agent-configuration.html
---



# APM agent central configuration [apm-agent-configuration]


::::{note}
APM agent central configuration is *not* compatible with [{{serverless-full}}](https://docs.elastic.co/serverless).

::::


APM Agent configuration allows you to fine-tune your APM agent configuration from within the Applications UI. Changes are automatically propagated to your APM agents, so there’s no need to redeploy.

To get started, choose the services and environments you wish to configure. The Applications UI will let you know when your APM agents have applied your configurations.

:::{image} ../../../images/observability-apm-agent-configuration.png
:alt: APM Agent configuration in Kibana
:class: screenshot
:::


## Precedence [_precedence]

Configurations set from the Applications UI take precedence over configurations set locally in each APM agent. However, if APM Server is slow to respond, is offline, reports an error, etc., APM agents will use local defaults until they’re able to update the configuration. For this reason, it is still essential to set custom default configurations locally in each of your APM agents.


## Supported configurations [_supported_configurations]

Each APM agent has a list of supported configurations. After selecting a Service name and environment in the Applications UI, a list of all supported configuration options, including descriptions and default values, will be displayed.

Supported configurations are also tagged with the ![dynamic config](../../../images/observability-dynamic-config.svg "") badge in each APM agent’s configuration reference:

Android agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/android/current/configuration.html)

Go agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/go/current/configuration.html)

iOS agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/swift/current/configuration.html)

Java agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/java/current/configuration.html)

.NET agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/dotnet/current/configuration.html)

Node.js agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/nodejs/current/configuration.html)

PHP agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/php/current/configuration.html)

Python agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/python/current/configuration.html)

Ruby agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/ruby/current/configuration.html)

Real User Monitoring (RUM) agent
:   [Configuration reference](https://www.elastic.co/guide/en/apm/agent/rum-js/current/configuration.html)


## APM Server configuration [_apm_server_configuration]

For most users, APM agent configuration should work out-of-the-box. If you run into trouble, it may be because you’re not using the {{es}} output, or because your {{es}} credentials don’t have sufficient privileges.

See [configure APM agent configuration](https://www.elastic.co/guide/en/apm/guide/current/configure-agent-config.html) to learn how to configure APM Server to avoid these problems.

