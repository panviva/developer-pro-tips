# Search Artefacts for a query
## How to use Panviva `GET Search Artefact` endpoint and search artefacts by a query.

This document shows how to use `simplequery` query parameter to search Panviva Digital Orchestrator Responses for a specified keyword.

As this endpoint uses natural language search, this search query does not necessarily have to be a exact string match.

Following examples will give you necessary the details to get you started.

## When using a standard Http client.

1. Construct your http client with necessary headers and token as advised in [Panviva developer portal](https://dev.panviva.com).

2. Replace the `{simplequery}` in the following url with the **query** you want to search Panviva Digital Orchestrator Responses with and make the HTTP request.

    `/operations/artefacts/nls?simplequery={simplequery}`

    Ex : 
    ```HTTP
    https://api.panviva.com/v3/sample-tenant/operations/artefact/nls?simplequery=example
    ```

## When using .Net SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-dotnet-sdk).

2. Replace the `{simplequery}` in the following snippet with the **query** you want to search Panviva Digital Orchestrator Responses with and make the request to Panviva SDK.

    ```c#
    var queryModel = new GetSearchArtefactsQueryModel
    {
        SimpleQuery = "{simplequery}"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

## When using Node SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{simplequery}` in following snippet with the **query** you want to search Panviva Digital Orchestrator Responses with and make the request to Panviva SDK.

    ```Js
    panvivaClient
    .searchArtefacts({
        simplequery = "{simplequery}"
    }).then((response) => {
        console.log(response);
    }).catch((ex) => console.error(ex));
    ```

## When using Python SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-python-sdk).

2. Replace the `{simplequery}` in following snippet with the **query** you want to search Panviva Digital Orchestrator Responses with and make the request to Panviva SDK.

    ```python
    query_to_search = '{simplequery}'
    api_response = api_instance.operations_artefact_nls(instance, query_to_search)
    ```