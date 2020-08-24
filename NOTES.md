# Search
- "search" is a central comcept to the application

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
--- highly customizable
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
- customize the index (multiple index, same fields)
- scale infinitely
- could RDS do this? yeah

# What cant we do with ES
- joins
- queries without index
