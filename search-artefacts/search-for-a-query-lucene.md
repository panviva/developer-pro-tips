# Search Artefacts - Lucene Syntax
## How to use Panviva `GET Search Artefact` endpoint and search artefacts by a query.

This document shows how to use `advancedquery` query parameter to search Panviva Digital Orchestrator Responses for a specified query using the Lucene query syntax.

As this endpoint uses natural language search, this search query does not necessarily have to be a exact string match.

### Escaping special characters

Special characters that require escaping include the following:  
`+ - & | ! ( ) { } [ ] ^ " ~ * ? : \ /`  

### Encoding unsafe and reserved characters in URLs

Ensure all unsafe and reserved characters are URL encoded.

Unsafe characters are ``" ` < > # % { } | \ ^ ~ [ ]``. Reserved characters are `; / ? : @ = + &`.

## Examples

Following examples will give you necessary the details to get you started.

- wildcards (Multi characters)

    `/operations/artefacts/nls?advancedquery=support*`
    
    Above example will match `support, supports, supported...`

    `/operations/artefacts/nls?advancedquery=*`
    
    Above example will match all search results.

- Regular expressions

    `/operations/artefact/nls?advancedquery=/(annually|monthly)/`

    Above example will match `annually` or `monthly`

- Fuzziness search

    `/operations/artefact/nls?advancedquery=suport~`

    `/operations/artefact/nls?advancedquery=suport~1`

    Above examples will match `support, supports, supported`

- Boolean operators

    `/operations/search?term=support AND desktop`

    `/operations/search?term=support OR desktop`

- Term boosting

    `operations/artefact/nls?advancedquery=support service^2`
    
    Above examples will rank the documents containing the term `service` twice as highly.

- Fielded search

    `operations/artefact/nls?advancedquery=panvivaDocumentId:654`

    `operations/artefact/nls?advancedquery=category/name:("feature" "how to")`

    Above examples will match the values for the specified fields with the provided values.

## When using a standard Http client.

1. Construct your http client with necessary headers and token as advised in [Panviva developer portal](https://dev.panviva.com).

2. Replace the `{advancedquery}` in the following url with the **query** you want to search Panviva Digital Orchestrator Responses with and make the HTTP request.

    `/operations/artefacts/nls?advancedquery={advancedquery}`

    Ex : 
    ```HTTP
    https://api.panviva.com/v3/sample-tenant/operations/artefact/nls?advancedquery=example
    ```

## When using .Net SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-dotnet-sdk).

2. Replace the `{advancedquery}` in the following snippet with the **query** you want to search Panviva Digital Orchestrator Responses with and make the request to Panviva SDK.

    ```c#
    var queryModel = new GetSearchArtefactsQueryModel
    {
        AdvancedQuery = "{advancedquery}"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

## When using Node SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{advancedquery}` in following snippet with the **query** you want to search Panviva Digital Orchestrator Responses with and make the request to Panviva SDK.

    ```Js
    panvivaClient
    .searchArtefacts({
        advancedquery = "{advancedquery}"
    }).then((response) => {
        console.log(response);
    }).catch((ex) => console.error(ex));
    ```

## When using Python SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-python-sdk).

2. Replace the `{advancedquery}` in following snippet with the **query** you want to search Panviva Digital Orchestrator Responses with and make the request to Panviva SDK.

    ```python
    query_to_search = '{advancedquery}'
    api_response = api_instance.operations_artefact_nls(instance, advancedquery=query_to_search)
    ```