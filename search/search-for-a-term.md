# search for a term
## How to use Panviva `GET Search` endpoint and search for a keyword.

This document shows how to use term query parameter to search Panviva documents for a specified keyword.

This search term does not necessarily have to be a exact string match. You can use some expressions and construct the search keyword as suits to your requirement.

Following examples will give you necessary the details to get you started.

- wildcards (Multi characters)

    `/operations/search?term=support*`
    
    Above example will match `support, supports, supported...`

- wildcards (Single characters)

    `/operations/search?term=supp?rt`

    Above example will match `support`

- Regular expressions

    `/operations/search?term=/sup{2}ort/`

    Above example will match `support`

- Fuzziness search

    `/operations/search?term=suport~`


    `/operations/search?term=suport~1`

    Above example will match `support, supports, supported`

- Boolean operators

    `/operations/search?term=support AND desktop`


    `/operations/search?term=support OR desktop`



## When using a standard Http client.

1. Construct your http client with necessary headers and token as advised in [Panviva developer portal](https://dev.panviva.com).

2. Replace the `{term}` in following url with the **search term** you want to search Panviva with and make the HTTP request.

    `/operations/search?term={term}`

    Ex : 
    ```HTTP
    https://api.panviva.com/v3/sample-tenant/operations/search?term=example
    ```

## When using .Net SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-dotnet-sdk).

2. Replace the `{term}` in following snippet with the **search term** you want to search Panviva with and make the request to Panviva SDK.

    ```c#
    var queryModel = new GetSearchQueryModel
    {
        term = "{term}"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

## When using Node SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{term}` in following snippet with the **search term** you want to search Panviva with and make the request to Panviva SDK.

    ```Js
    panvivaClient
    .search('{term}')
    .then((response) => 
    {
        console.log(response);
    })
    .catch((ex) => console.error(ex));
    ```

## When using Python SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{term}` in following snippet with the **search term** you want to search Panviva with and make the request to Panviva SDK.

    ```python
    term_to_search = '{term}'
    api_response = api_instance.operations_search(instance, term_to_search)
    ```