# Airflow CI/CD

CI/CD pipeline for Airflow

## Setup Airflow Web server locally

An easy way to setup Airflow server locally is to use Docker and the popular Docker image `puckel/docker-airflow`.

* Mount your local DAGs folder to the container so you can edit the DAGs file with your preferred IDE

```bash
# Run Airflow container and mount your local DAGs folder
docker run -itd -v /Users/codigube/Documents/my-projects/airflow-quickstart/dags:/usr/local/airflow/dags -p 8080:8080 --name airflow  puckel/docker-airflow:latest
```

After container is up running, you can log into container to test Airflow with CLI

```bash
# Log into container
docker exec -it airflow  bash
```

Or go to `localhost:8080` to check the UI.

## DAGs and Unit tests

NOTE: Make sure that you have Airflow installed for Python usage

```bash
pip install apache-airflow
```

* `hello_world_dag.py`
* `utils.py`

Added unit test for `utils.py`

* `unitls.py`

Run unit tests

```bash
python -m unittest discover -s dags -p "*_test.py"
```

## Setup Concourse

