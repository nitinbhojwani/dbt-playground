Welcome to your new dbt project!

### Using the starter project

Try running the following commands:
- dbt run
- dbt test


### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices

## Setup:
1. Setup Postgres for local testing
```
docker run --name postgres -p 5432:5432 -e 
POSTGRES_PASSWORD=password -e POSTGRES_USER=postgres -d postgres

docker exec -it postgres /bin/bash

psql -U postgres

CREATE DATABASE jaffle_shop

# -- exit psql and docker container
```

2. Try dbt debug to see checks pass:
```
dbt debug --profile jaffle_shop -t dev --profiles-dir .
```

3. Load seed data present in `data` directory. Data is sourced from https://github.com/emilieschario/jaffle_shop:

```
dbt seed --profile jaffle_shop -t dev --profiles-dir .
```
