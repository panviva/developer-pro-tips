# Negative search
## How to use Panviva `GET Search` endpoint and search for documents which does not have a specific requirement.

This document shows how to use term query parameter and search Panviva documents which does not have a specific requirement.

In this example we'll use the attribute `updatedDate` range. YYou can read [this](search/filterable-fields.md) document and select any other attribute that you want to filter with this pattern.

## When using a standard Http client.

1. Construct your http client with necessary headers and token as advised in [Panviva developer portal](https://dev.panviva.com).

2. Replace the `{yourQuery}` in following url with the **query** you want to search with and make the HTTP request.

    `/operations/search?term=!({yourQuery})`

    Ex : 
    ```HTTP
    https://api.panviva.com/v3/sample-tenant/operations/search?term=!(data.attributes.updatedDate:[2020-05-01 TO 2020-08-01])
    ```

## When using .Net SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-dotnet-sdk).

2. Replace the `{yourQuery}` in following snippet with the **query** you want to search with and make the request to Panviva SDK.

    ```c#
    var queryModel = new GetSearchQueryModel
    {
        term = "search?term=!({yourQuery})"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

    Ex:
    ```c#
    var queryModel = new GetSearchQueryModel
    {
        term = "!(data.attributes.updatedDate:[2020-05-01 TO 2020-08-01])"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

## When using Node SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{yourQuery}` in following snippet with the **query** you want to search with and make the request to Panviva SDK.

    ```Js
    panvivaClient
    .search('search?term=!({yourQuery})')
    .then((response) => 
    {
        console.log(response);
    })
    .catch((ex) => console.error(ex));
    ```

    Ex: 
    ```Js
    panvivaClient
    .search('!(data.attributes.updatedDate:[2020-05-01 TO 2020-08-01])')
    .then((response) => 
    {
        console.log(response);
    })
    .catch((ex) => console.error(ex));
    ```

## When using Python SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{yourQuery}` in following snippet with the **query** you want to search with and make the request to Panviva SDK.

    ```python
    term_to_search = 'search?term=!({yourQuery})'
    api_response = api_instance.operations_search(instance, term_to_search)
    ```

    Ex:
    ```python
    term_to_search = '!(data.attributes.updatedDate:[2020-05-01 TO 2020-08-01])'
    api_response = api_instance.operations_search(instance, term_to_search)
    ```