# Filter date ranges
## How to use Panviva `GET Search` endpoint and search for documents within a date range.

This document shows how to use term query parameter and search Panviva documents for a specific date range.

The dates should be in `yyyy-mm-dd` format and you can use char `*` as the max value. (for example if you use `*` as end date will give you everything from the start date)

## When using a standard Http client.

1. Construct your http client with necessary headers and token as advised in [Panviva developer portal](https://dev.panviva.com).

2. Replace the `{fromDate}` and `{toDate}` in following url with the **starting date** and **end date** you want to filter the search and make the HTTP request.

    `/operations/search?term=data.attributes.updatedDate:[{fromDate} TO {toDate}]`

    Ex : 
    ```HTTP
    https://api.panviva.com/v3/sample-tenant/operations/search?term=data.attributes.updatedDate:[2020-05-01 TO 2020-08-01]
    ```

## When using .Net SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-dotnet-sdk).

2. Replace the `{fromDate}` and `{toDate}` in following url with the **starting date** and **end date** you want to filter the search and make the request to Panviva SDK.

    ```c#
    var queryModel = new GetSearchQueryModel
    {
        term = "data.attributes.updatedDate:[{fromDate} TO {toDate}]"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

    Ex:
    ```c#
    var queryModel = new GetSearchQueryModel
    {
        term = "data.attributes.updatedDate:[2020-05-01 TO 2020-08-01]"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

## When using Node SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{fromDate}` and `{toDate}` in following url with the **starting date** and **end date** you want to filter the search and make the request to Panviva SDK.

    ```Js
    panvivaClient
    .search('data.attributes.updatedDate:[{fromDate} TO {toDate}]')
    .then((response) => 
    {
        console.log(response);
    })
    .catch((ex) => console.error(ex));
    ```

    Ex: 
    ```Js
    panvivaClient
    .search('data.attributes.updatedDate:[2020-05-01 TO 2020-08-01]')
    .then((response) => 
    {
        console.log(response);
    })
    .catch((ex) => console.error(ex));
    ```

## When using Python SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{fromDate}` and `{toDate}` in following url with the **starting date** and **end date** you want to filter the search and make the request to Panviva SDK.

    ```python
    term_to_search = 'data.attributes.updatedDate:[{fromDate} TO {toDate}]'
    api_response = api_instance.operations_search(instance, term_to_search)
    ```

    Ex:
    ```python
    term_to_search = 'data.attributes.updatedDate:[2020-05-01 TO 2020-08-01]'
    api_response = api_instance.operations_search(instance, term_to_search)
    ```