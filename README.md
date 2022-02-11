# otel-collector
Dev configuration for OpenTelemetry collector.

This runs a collector which receives traces from an application and sends them
to a local [Jaeger](https://www.jaegertracing.io/) instance, DataDog, or AWS X-Ray.

This is using the AWS Collector, which has support for additional
back end services in addition to OpenTelemetry.

```shell
docker-compose up aws-otel-collector
open https://localhost:16686/
```

For DataDog, add a `.env` file which sets DataDog environment vars, most important of
which is the API key:

```yaml
# SECRET ENV VARIABLES

DD_API_KEY="abc123"

# NON SECRET ENV VARIABLES
#
# The variables below are not secret and have default values, you can change them if you need to:

# You can enable or disable sending development env traces to Datadog
# by setting this variable with true or false (true enables, false disables).
DD_APM_ENABLED=true

DD_HOSTNAME=jake-dev
DD_HOST=jake-dev
DD_TAGS=environment:development
DD_ENV=development
DD_APM_ENV=development
```
