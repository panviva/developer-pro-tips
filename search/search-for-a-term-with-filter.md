# Search for term with a filter
## How to use Panviva `GET Search` endpoint and search for a keyword with a filter.

This document shows how to use term query parameter and search Panviva documents for a specified keyword plus a filter. These filters can be any attribute value of the intended search data.

In this example we'll use the attribute `classification`. You can read the schema in Panviva developer portal and select any other attribute that you want to filter with this pattern.

> Note : These  `+` , `-` , `=` , `&&` , `||` , `>` , `<` , `!` , `(` , `)` , `{` , `}` , `[` , `]` , `^` , `"` , `~` , `*` , `?` , `:` , `\` , `/` special characters are reserved and  must be escaped with `\` when you want to use them withing the syntax.

## When using a standard Http client.

1. Construct your http client with necessary headers and token as advised in [Panviva developer portal](https://dev.panviva.com).

2. Replace the `{term}` in following url with the **search term** and then `{attributeName}` and `{attributeValue}` with the **attribute parameter name and value** you want to filter the search and make the HTTP request.

    `/operations/search?term={term} AND data.attributes.{attributeName}:{attributeValue}`

    Ex : 
    ```HTTP
    https://api.panviva.com/v3/sample-tenant/operations/search?term=example AND data.attributes.classification:web\-enabled
    ```

## When using .Net SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-dotnet-sdk).

2. Replace the `{term}` in following snippet with the **search term** and then `{attributeName}` and `{attributeValue}` with the **attribute parameter name and value** you want to filter the search and make the request to Panviva SDK.

    ```c#
    var queryModel = new GetSearchQueryModel
    {
        term = "{term} AND data.attributes.{attributeName}:{attributeValue}"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

    Ex:
    ```c#
    var queryModel = new GetSearchQueryModel
    {
        term = "example AND data.attributes.classification:web\-enabled"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

## When using Node SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{term}` in following snippet with the **search term** and then `{attributeName}` and `{attributeValue}` with the **attribute parameter name and value** you want to filter the search and make the request to Panviva SDK.

    ```Js
    panvivaClient
    .search('{term} AND data.attributes.{attributeName}:{attributeValue}')
    .then((response) => 
    {
        console.log(response);
    })
    .catch((ex) => console.error(ex));
    ```

    Ex: 
    ```Js
    panvivaClient
    .search('example AND data.attributes.classification:web\-enabled')
    .then((response) => 
    {
        console.log(response);
    })
    .catch((ex) => console.error(ex));
    ```

## When using Python SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. Replace the `{term}` in following snippet with the **search term** and then `{attributeName}` and `{attributeValue}` with the **attribute parameter name and value** you want to filter the search and make the request to Panviva SDK.

    ```python
    term_to_search = '{term} AND data.attributes.{attributeName}:{attributeValue}'
    api_response = api_instance.operations_search(instance, term_to_search)
    ```

    Ex:
    ```python
    term_to_search = 'example AND data.attributes.classification:web\-enabled'
    api_response = api_instance.operations_search(instance, term_to_search)
    ```