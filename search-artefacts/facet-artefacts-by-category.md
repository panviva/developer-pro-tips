# Facet Artefacts by Category
## How to use Panviva `GET Search Artefact` endpoint and facet artefacts by category.

This document shows how to use `facet` query parameter to search and group Panviva Digital Orchestrator Responses for a specific category.

## When using a standard Http client.

1. Construct your http client with necessary headers and token as advised in [Panviva developer portal](https://dev.panviva.com).

2. Use the following URL components to make the HTTP request. The `*` value passed to the `advancedquery` parameter ensures that the faceting will occur on all artefacts without any natural language search.

    `/operations/artefacts/nls?advancedquery=*&facet=category/name`

    Ex : 
    ```HTTP
    https://api.panviva.com/v3/sample-tenant/operations/artefact/nls?advancedquery=*&facet=category/name
    ```

## When using .Net SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-dotnet-sdk).

2. Use the following snippet to make the HTTP request. The `*` value passed to the `AdvancedQuery` property ensures that the faceting will occur on all artefacts without any natural language search.

    ```c#
    var queryModel = new GetSearchArtefactsQueryModel
    {
        AdvancedQuery = "*"
        Facet = "category/name"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

## When using Node SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Use the following snippet to make the HTTP request. The `*` value passed to the `advancedquery` attribute ensures that the faceting will occur on all artefacts without any natural language search.

    ```Js
    panvivaClient
    .searchArtefacts({
        advancedquery = "*",
        facet = "category/name"
    }).then((response) => {
        console.log(response);
    }).catch((ex) => console.error(ex));
    ```

## When using Python SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-python-sdk).

2. Use the following snippet to make the HTTP request. The `*` value passed to the `advancedquery` parameter ensures that the faceting will occur on all artefacts without any natural language search.

    ```python
    query_to_search = '*'
    facet_expression = 'category/name'
    api_response = api_instance.operations_artefact_nls(instance, advancedquery=query_to_search, facet=facet_expression)
    ```