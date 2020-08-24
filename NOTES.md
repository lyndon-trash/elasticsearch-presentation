# Search
- "search" is a central concept/functionality to the application that i think it is something work discussing
- also used for autocomplete when we can
- the culmination of all the work of the data team, the primary way of getting access to the candidate data
- when a user searches for a candidate, this is the first place that he or she goes to

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



## QUESTIONS BEFORE PROCEEDING


# What can we do with ES
why did we even choose ES? cant we just use a regular database?

- PERFORM COMPLEX QUERIES WITH MINIMAL EFFORT
```
queries are unsurprisingly just documents that describe other documents
```

- CUSTOMIZE THE SORTING
```
add weights to influence the sort
some fields are more important than others
we can even remove the score for filters
```

- SCALE INFINITELY
```
- add nodes as our data grows
- shard and replicate our data for even better performance
```

# What cant we do with ES
- JOINS
```
joins are not scalable
we work around this limitation by doing data denormalization
```

- AD HOC QUERIES
```
also not scalable

let say a new requirement comes in? 
we need to recreate the index if the current index cant support the new query
```
