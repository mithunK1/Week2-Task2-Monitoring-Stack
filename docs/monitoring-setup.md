# Monitoring Stack Setup

## Install Helm
helm version

## Install Stack
bash monitoring/install-monitoring.sh

## Get Grafana Password
kubectl get secret grafana -o jsonpath="{.data.admin-password}" | base64 --decode

## Access Grafana
kubectl port-forward svc/grafana 3000:80
Open http://localhost:3000

Username: admin
Password: (from previous command)

## Access Prometheus
kubectl port-forward svc/prometheus-server 9090:80
Open http://localhost:9090

## Import Dashboard
Import backend-dashboard.json in Grafana.
