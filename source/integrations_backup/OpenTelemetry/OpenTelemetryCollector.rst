OpenTelemetry Collector
============================

docker-compose.yaml
---------------------------------

.. code-block:: none

      services:
        otel-collector:
        image: otel/opentelemetry-collector-contrib:0.111.0
        container_name: otel-collector
        ports:
            - "4317:4317"     # OTLP gRPC
            - "4318:4318"     # OTLP HTTP
            - "13133:13133"   # Health check endpoint
        volumes:
            - ./otel-collector-config.yaml:/etc/otel-collector-config.yaml
        command: ["--config", "/etc/otel-collector-config.yaml"]

otel-collector-config.yaml
---------------------------------