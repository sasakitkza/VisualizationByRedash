# Visualization By Redash

Data infrastructure to visualize data and logs obtained from APIs

## List of tools

- Database
  - MongoDB
  - PostgreSQL
- Visualization
  - Metabase
  - Re:dash
- Data collection & pipeline
  - Logstash
  - embulk
  - Digdag
- Query engine
  - Presto
- Workflow management
  - Apache Airflow

## Usage

### Start the containers

1. Run in the directory directly under `VisualizationByRedash`.  
  `docker-compose up -d`
2. Go to the VisualizationByRedash/redash directory.  
  `cd redash`
3. Create a Reddash tables only on the first run.  
  `docker-compose run --rm server create_db`
4. Run  
  `docker-compose up -d`

### Start Embulk jobs

1. Go to the VisualizationByRedash/embulk directory.  
  `cd embulk`
2. Run Embulk job by specifying yml　or liquid file in `work` folder.

## Handing API Tokens

### Logstash

- Put the authentication information in bash_profile and pass it as an environment variable.

### Embulk

- Under consideration.
