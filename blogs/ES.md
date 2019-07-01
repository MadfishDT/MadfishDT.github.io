## Elastic Search Querys

## Data Input
- [Add Data](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-index_.html)
```
    POST twitter/_doc/
    {
        "user" : "kimchy",
        "post_date" : "2009-11-15T14:12:12",
        "message" : "trying out Elasticsearch"
    }
```

## Index/Doc Delete
- [Delete Index or Doc](https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-delete-index.html)

```js
    DELETE twitter/
```

```js
    DELETE twitter/doc
```

## Delete Data in Doc
- [Add Data](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-index_.html)
- `POST twitter/_delete_by_query`
- remove all data with 'match_all' query keyword
```js
    POST twitter/_doc/
    {
        "query": {
            "match_all": {}
        }
    }
```

- remove data with date range
- lt: less than '<'
- gt: great than '>'
- lte: less than and equal'<='
- gte: great than and equal'>='

```js
{
  "query": {
     "range" : {
            "dateTime" : {
                "gte": "2015-01-01",
                "lt" :  "2019-05-01"
            }
        }
  }
}
```


