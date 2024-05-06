# Dockerized Airflow Data Pipeline

## Description

This project involves the development of a Dockerized Apache Airflow data pipeline that fetches user data from two different sources and inserts it into a PostgreSQL database. The data sources include the RandomUser API and an existing MySQL database. The pipeline consists of two separate DAGs (Directed Acyclic Graphs) to handle the data transfer operations.

## Table of Contents
- [Requirements](#requirements)
- [Technology Stack](#technology-stack)
- [Data Sources](#data-sources)
- [Architecture](#architecture)
- [Deploy the Solution](#deploy-the-solution)
- [Step-by-Step Guide](#step-by-step-guide)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Requirements
- Docker
- Docker Compose
- Apache Airflow
- PostgreSQL
- MySQL

## Technology Stack
- **Apache Airflow**: Workflow orchestration platform to manage data pipelines.
- **PostgreSQL**: Target database for storing data.
- **MySQL**: Source database for existing user data.
- **Docker**: Containerization platform for deploying the Airflow pipeline.

## Data Sources
- **RandomUser API**: Used to fetch random user data.
- **MySQL Database**: Existing database containing user data.

## Architecture
The architecture includes two separate Airflow DAGs:

1. **RandomUser API to PostgreSQL**: This DAG fetches random user data from the RandomUser API and inserts it into the PostgreSQL database.
2. **MySQL to PostgreSQL**: This DAG transfers data from the existing MySQL database to the PostgreSQL database.

The data is modeled in a PostgreSQL table named `mytable`, which includes various user attributes such as `_id`, `gender`, `name_title`, `name_first`, `name_last`, etc.

## Deploy the Solution
1. Clone the repository:
    ```shell
    git clone https://github.com/yourusername/etl-dockerized-data-pipeline.git
    cd etl-dockerized-data-pipeline
    ```

2. Start the Docker containers for Airflow, PostgreSQL, and MySQL:
    ```shell
    docker-compose up
    ```

## Step-by-Step Guide
### RandomUser API to PostgreSQL

- **DAG Name**: `user_data_to_postgres`
- **Task Name**: `fetch_and_insert_data`
  
This task fetches random user data from the RandomUser API and inserts it into the PostgreSQL database.

### MySQL to PostgreSQL

- **DAG Name**: `mysql_to_postgres`
- **Task Name**: `transfer_data`
  
This task transfers data from the MySQL database to the PostgreSQL database.

## Usage
- Access the Airflow web UI at [http://localhost:8080](http://localhost:8080).
- Trigger the DAGs manually or set up a schedule for automated execution.

## Contributing
If you'd like to contribute to the project, please follow the standard GitHub workflow:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and submit a pull request.

## License
This project is licensed under the [MIT License](LICENSE).

---

Happy coding! If you have any questions or feedback, please feel free to open an issue on GitHub.

