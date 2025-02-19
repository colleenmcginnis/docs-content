# Collect application data [apm-collect-application-data]


## Language-specific options [_language_specific_options]

Use Elastic APM agents or an OpenTelemetry language SDK to instrument a service in the language its written in:

* [**Elastic APM agents**](../../../solutions/observability/apps/elastic-apm-agents.md): Elastic APM agents are instrumentation libraries written in the same language as your service.
* [**OpenTelemetry**](../../../solutions/observability/apps/use-opentelemetry-with-apm.md): OpenTelemetry is an open source set of APIs, SDKs, tooling, and integrations that enable the capture and management of telemetry data from your services and applications.

    * This option includes Elastic Distributions of OpenTelemetry, which are customized versions of [OpenTelemetry language SDKs](https://opentelemetry.io/docs/languages/) that are optimized to work with an Elastic backend.


**Not sure which method is right for you?** Compare the available options below.


### Capabilities [_capabilities]

|  | Elastic APM agent | Elastic Distribution of OpenTelemetry |
| --- | --- | --- |
| **Support level** | Fully supported | Mixed support<br>*Refer to the* [*availability table*](../../../solutions/observability/apps/collect-application-data.md#apm-collect-data-availability) |
| **Data protocol** | Elastic protocol | [OpenTelemetry protocol (OTLP)](https://opentelemetry.io/docs/specs/otel/protocol/) |
| **Central configuration** | Supported<br>*Refer to* [*APM agent central configuration*](../../../solutions/observability/apps/apm-agent-central-configuration.md) | Not supported |


### Availability [apm-collect-data-availability]

|     |     |     |
| --- | --- | --- |
| **Language** | **Elastic APM agent** | **Elastic Distributions of OpenTelemetry (EDOT)** |
| **Android** | Android agent | ![Not available](../../../images/observability-cross.svg "") |
| **Go** | Go agent | ![Not available](../../../images/observability-cross.svg "") |
| **iOS** | iOS agent | ![Not available](../../../images/observability-cross.svg "") |
| **Java** | Java agent | EDOT Java |
| **.NET** | .NET agent | [preview] EDOT .NET |
| **Node.js** | Node.js agent | [preview] EDOT Node.js |
| **PHP** | PHP agent | [preview] EDOT PHP |
| **Python** | Python agent | [preview] EDOT Python |
| **Ruby** | Ruby agent | ![Not available](../../../images/observability-cross.svg "") |


## Service-specific options [_service_specific_options]

Elastic also offers several tools to help you collect data from specific services:

* **Kubernetes**: The Elastic APM attacher for Kubernetes simplifies the instrumentation and configuration of your application pods. Read more in the [APM attacher for Kubernetes docs](https://www.elastic.co/guide/en/apm/attacher/current/apm-attacher.html).
* **AWS Lambda Functions**: Helps you monitor your AWS Lambda functions. Read more in the [APM Architecture for AWS Lambda docs](https://www.elastic.co/guide/en/apm/lambda/current/aws-lambda-arch.html).
* [8.15.0] **Jaeger**: Helps you to switch an existing Jaeger setup from the default Jaeger backend to the {{stack}}. Read more in [Integrate with Jaeger](../../../solutions/observability/apps/integrate-with-jaeger-deprecated.md).






