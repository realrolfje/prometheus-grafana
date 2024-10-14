FROM prom/prometheus:latest

# Copy custom Prometheus configuration
COPY prometheus.yml /etc/prometheus/prometheus.yml

# Declare Prometheus data directory as a volume
VOLUME ["/prometheus"]