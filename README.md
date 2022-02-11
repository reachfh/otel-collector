# otel-collector
Configuration for OpenTelemetry collector.

This runs a collector which receives traces from an application and sends them
to a local Jaeger instance, DataDog, or AWS X-Ray.

For DataDog, add a `.env` file with your key:

```yaml
# SECRET ENV VARIABLES
#
# The variables below are empty for security reasons, you can copy this key from other services,
# since there is no vault file created for datadog yet:

DD_API_KEY="abc123"

# NON SECRET ENV VARIABLES
#
# The variables below are not secret and have default values, you can change it if you need to:

# you can enable or disable sending development env traces to Datadog
# by setting this variable with true or false (true enables, false disables).
DD_APM_ENABLED=true

DD_HOSTNAME=jake-dev
DD_HOST=jake-dev
DD_TAGS=environment:development
DD_ENV=development
DD_APM_ENV=development
```
