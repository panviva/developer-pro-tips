# Filter Artefacts by Panviva Document ID
## How to use Panviva `GET Search Artefact` endpoint and filter artefacts of a Panviva Document.

This document shows how to use `filter` query parameter to search and filter Panviva Digital Orchestrator Responses for a specific Panviva Document.

The values should be a postive integer value.


## When using a standard Http client.

1. Construct your http client with necessary headers and token as advised in [Panviva developer portal](https://dev.panviva.com).

2. Replace the `{panvivaDocumentId}` in the following url with the **Panviva Document ID** you want to filter Panviva Digital Orchestrator Responses with and make the HTTP request. The `*` value passed to the `advancedquery` parameter ensures that the filtering will occur on all artefacts without any natural language search.

    `/operations/artefacts/nls?advancedquery=*&filter=panvivaDocumentId eq {panvivaDocumentId}`

    Ex : 
    ```HTTP
    https://api.panviva.com/v3/sample-tenant/operations/artefact/nls?advancedquery=*&filter=panvivaDocumentId eq 8576
    ```

## When using .Net SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-dotnet-sdk).

2. Replace the `{panvivaDocumentId}` in the following snippet with the **Panviva Document ID** you want to filter Panviva Digital Orchestrator Responses with and make the HTTP request. The `*` value passed to the `AdvancedQuery` property ensures that the filtering will occur on all artefacts without any natural language search.

    ```c#
    var queryModel = new GetSearchArtefactsQueryModel
    {
        AdvancedQuery = "*"
        Filter = "panvivaDocumentId eq {panvivaDocumentId}"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

## When using Node SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{panvivaDocumentId}` in the following snippet with the **Panviva Document ID** you want to filter Panviva Digital Orchestrator Responses with and make the HTTP request. The `*` value passed to the `advancedquery` attribute ensures that the filtering will occur on all artefacts without any natural language search.

    ```Js
    panvivaClient
    .searchArtefacts({
        advancedquery = "*",
        filter = "panvivaDocumentId eq {panvivaDocumentId}"
    }).then((response) => {
        console.log(response);
    }).catch((ex) => console.error(ex));
    ```

## When using Python SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-python-sdk).

2. Replace the `{panvivaDocumentId}` in the following snippet with the **Panviva Document ID** you want to filter Panviva Digital Orchestrator Responses with and make the HTTP request. The `*` value passed to the `advancedquery` parameter ensures that the filtering will occur on all artefacts without any natural language search.

    ```python
    query_to_search = '*'
    filter_expression = 'panvivaDocumentId eq {panvivaDocumentId}'
    api_response = api_instance.operations_artefact_nls(instance, advancedquery=query_to_search, filter=filter_expression)
    ```