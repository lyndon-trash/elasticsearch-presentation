# What is ES
- search index
- document
- index before query

### Advantage
- speed and scalability
- relevance/score
- full-text index
- could RDS do this? yeah


# Work We Need
### Data team
- profile and clean
- manually change if needed
- aggregate data into a normalized form

### Product team (backend)
- prepare the index
```
- know the query beforehand
- denormalize if needed
- recreate the index if there are new requirements
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


# What can we do with ES
- score

# What cant we do with ES
- joins
- queries without index
