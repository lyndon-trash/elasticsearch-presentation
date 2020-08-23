# Notes


## What is ES
- search index
- document
- index before query

## Advantage
- speed and scalability
- relevance/score
- full-text index



## Work We Need
### Data team
- profile and clean
- aggregate data into a normalized form

### Product team (backend)
- prepare the index
```
recreate the index if there are new requirements
```
- pull data from data warehous
- formulate the query
```
- score/sort
- restrict access
```
- serve the data via REST

### Product team (frontend)
- invoke via REST
