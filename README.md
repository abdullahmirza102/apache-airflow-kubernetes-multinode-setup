# Apache Airflow Setup on Kubernetes Multi Node Cluster

This repository provides the resources and instructions required for deploying Apache Airflow on a Kubernetes multi-node cluster.  
It is suitable for cloud environments (GCP, AWS, Azure) or self-hosted clusters, and includes all essential YAML files for setting up Airflow and its backend dependencies.

## About Apache Airflow

[Apache Airflow](https://airflow.apache.org/) is an open-source platform used to programmatically author, schedule, and monitor workflows.  
It enables scalable automation of data pipelines and tasks and integrates well with containerized/cloud environments via Kubernetes.

## Repository Contents

- **Step-by-step deployment guide:**  
  [`apache_airflow_setup_k8s.docx`](./apache_airflow_setup_k8s.docx) – Comprehensive instructions for installation and configuration.
- **Kubernetes YAML files:**  
  - [`airflow-pv.yaml`](./airflow-pv.yaml): Persistent Volume setup for Airflow  
  - [`postgres-deployment.yaml`](./postgres-deployment.yaml): Postgres database deployment  
  - [`postgres-pv.yaml`](./postgres-pv.yaml): Persistent Volume for Postgres
  - [`values.yaml`](./values.yaml): Airflow Helm chart configuration

## Quick Start

1. **Clone the repository:**
   ```bash
   git clone https://github.com/abdullahmirza102/apache-airflow-kubernetes-multinode-setup.git
   cd apache-airflow-kubernetes-multinode-setup
   ```

2. **Follow the guide:**  
   Open `apache_airflow_setup_k8s.docx` for detailed installation steps.

3. **Apply the Kubernetes YAML files:**  
   For example, to set up persistent volumes:
   ```bash
   kubectl apply -f airflow-pv.yaml
   kubectl apply -f postgres-pv.yaml
   ```

4. **Deploy backend services:**  
   ```bash
   kubectl apply -f postgres-deployment.yaml
   ```

5. **Configure and install Airflow using Helm:**  
   Edit `values.yaml` if needed, then run:
   ```bash
   helm install airflow -f values.yaml stable/airflow
   ```

## Documentation

See [`apache_airflow_setup_k8s.docx`](./apache_airflow_setup_k8s.docx) for a complete installation and configuration walkthrough.

## Contributing

Feel free to open issues or pull requests for improvements and clarifications.

## License

MIT
