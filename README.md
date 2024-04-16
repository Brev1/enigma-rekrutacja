# Enigma - Recruitment Task

My idea for implementing the recruitment task <i>zadrekr-devops-junior 2024.pdf</i>

### I. Containerized tools used to build the project:
1. `nginx:1.21.1` Nginx with static website and selfsigned certificate.
2. `prom/prometheus:latest` Prometheus for storing metrics.
3. `nginx/nginx-prometheus-exporter:latest` - nginx-prometheus-exporter for reading stub_status page metrics exposed by NGINX, and exporting them to Prometheus.
4. `quay.io/martinhelmich/prometheus-nginxlog-exporter:latest` - prometheus-nginxlog-exporter for reading nginx logs and export metrics to Prometheus.
5. `quay.io/prometheus/blackbox-exporter:latest` - blackbox-exporter for probing of endpoint over HTTPS to read Certificate expiration date and exporting data do Prometheus.
6. `grafana/grafana:latest` - Grafana to visualize data.

### II. Before starting the project:
Make sure you do not have any working local services that uses ports:
* `80/443, 4040, 9113, 3000, 9090, 9115`

### III. How to get it working:
1. Clone repository to your working directory:
<pre>git clone https://github.com/Brev1/enigma-rekrutacja.git</pre>

2. (Optional) Modify .env file or leave it as default:

<pre>
GF_SECURITY_ADMIN_USER=change-me
GF_SECURITY_ADMIN_PASSWORD=change-me
</pre>

3. Start the project
<pre>
docker compose up -d
</pre>

4. Open Grafana via entering `localhost:3000` in your browser and check out "Nginx Monitoring" dashboard.

### IV. What should I avoid but done:
* Added certs to repo
* Added .env to repo

### V. Special thanks:
Nginx static website template:
* https://www.tooplate.com/view/2129-crispy-kitchen

Github repos:
* https://github.com/nginxinc/nginx-prometheus-exporter
* https://github.com/martin-helmich/prometheus-nginxlog-exporter
* https://github.com/prometheus/blackbox_exporter

Grafana dashboards:
* https://grafana.com/grafana/dashboards/12708-nginx/
* https://grafana.com/grafana/dashboards/15947-nginx-log-metrics-m/
* https://grafana.com/grafana/dashboards/13230-certificate-monitor/
