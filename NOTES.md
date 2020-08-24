# Search
- "search" is a central comcept to the application
- the culmination of all the work of the data team, the primary way of getting access to the candidate data

# Agenda
- basics of ES
- effort needed to build search
- capabilities and limitations

# What is ES
For our intents and purpose:
- document storage
```
- compare this with regular db
- row = document
- table = index
- column = field
--- basic: strings, numbers, dates, boolean, range, 
--- geo-spatial: lat/lng
--- complex: object/nested, arrays

https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-types.html
https://www.elastic.co/guide/en/elasticsearch/reference/current/range.html
```
- search engine
```
- performs analysis on the documents during insert
--- highly customizable (analyzers and tokenizers)
https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-analyzers.html
-- commonly used:
--- standard (whitespace)
--- edge n-gram (autocomplete)

--- multiple indexes for a single field
```
- the ELK stack has other features, but we are only taking advantage of the core functionality
```
- log aggregation
- application monitoring
- machine learning
- data analytics
```

# Work We Need
Before we begin running our searches, a ton of work happens in the background

### Data team
before we even prepare the ES indexes and serve the data, the data team will be working way ahead
- ingest data from various sources
- profile and cleanup the data
- ultimately: they will aggregate data into a normalized form into REDSHIFT

### Product team (backend)
Once the data team have it nice and tidy, the final phase of transforming the data into an application-consumable form begins

- prepare the index
```
- know the query beforehand, this will be provided in the specs
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
- customize the index (multiple index, same fields)
- scale infinitely
- could RDS do this? yeah

# What cant we do with ES
- joins
- queries without index
