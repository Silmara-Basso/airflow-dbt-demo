### Aiflow Schedule lab

In this lab I loaded data from some files into PostgreSQL scheduled via Airflow (Astro) using BashOperator and Cosmos.
I didn't start from scratch, I used [this repository](https://github.com/astronomer/airflow-dbt-demo) from Astronomer itself

## To run these DAGs locally:

1. Download the [Astro CLI](https://github.com/astronomer/astro-cli)
2. Download and run [Docker](https://docs.docker.com/docker-for-mac/install/)
3. Clone [this repository](https://github.com/Silmara-Basso/airflow-dbt-demo.git) and `cd` into it.
4. Activate the virtual environment
5. Create the .env wirh profiles.yml environmental variables
4. Run `astro dev start` to spin up a local Airflow environment and run the accompanying DAGs on your machine.
![CDocker Containers](./images/Docker_containers.png)


## Notes
- To use these DAGs, Airflow 2.2+ is required. These DAGs have been tested with Airflow 2.2.0.
- If you make changes to the dbt project, you will need to run `dbt compile` in order to update the `manifest.json` file.
This may be done manually during development, as part of a CI/CD pipeline, or as a separate step in a production pipeline
run *before* the Airflow DAG is triggered.

Final result after a few attempts
![AirFlow Dags](./images/Airflow.png)

I used harlequin to view persisted data in Postgre
'pip install harlequin-postgres'

![Querying Postgre](./images/codigo.png)