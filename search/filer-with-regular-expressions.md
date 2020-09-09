# Filter with regular expressions
## How to use Panviva `GET Search` endpoint and search for documents with **filters** and **regular expressions**.

This document shows how to use term query parameter and search Panviva documents with filters and how to add regular expressions logic as filter values. These filters can be any attribute value of the intended search data.

In this example we'll use the attribute `classification`. You can read [this](search/filterable-fields.md) document and select any other attribute that you want to filter with this pattern.


> Note : These  `+` , `-` , `=` , `&&` , `||` , `>` , `<` , `!` , `(` , `)` , `{` , `}` , `[` , `]` , `^` , `"` , `~` , `*` , `?` , `:` , `\` , `/` special characters are reserved and  must be escaped with `\` when you want to use them withing the regular expressions.

## When using a standard Http client.

1. Construct your http client with necessary headers and token as advised in [Panviva developer portal](https://dev.panviva.com).

2. The `{attributeValue}` in following example will be the **regular expression** you want to construct your logic with. Fill them according to your requirement and make the HTTP request.

    `/operations/search?term=data.attributes.classification:\/{attributeValue}\/`

    Ex : 
    ```HTTP
    https://api.panviva.com/v3/sample-tenant/operations/search?term=data.attributes.classification:\/web\?enabled\/
    ```

## When using .Net SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-dotnet-sdk).

2. The `{attributeValue}` in following example will be the **regular expression** you want to construct your logic with. Fill them according to your requirement and make the request to Panviva SDK.

    ```c#
    var queryModel = new GetSearchQueryModel
    {
        term = "data.attributes.classification:\/{attributeValue}\/"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

    Ex:
    ```c#
    var queryModel = new GetSearchQueryModel
    {
        term = "data.attributes.classification:\/web\?enabled\/"
    }

    var response = await _queryHandler.HandleAsync(queryModel);
    ```

## When using Node SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. The `{attributeValue}` in following example will be the **regular expression** you want to construct your logic with. Fill them according to your requirement and make the request to Panviva SDK.

    ```Js
    panvivaClient
    .search('data.attributes.classification:\/{attributeValue}\/')
    .then((response) => 
    {
        console.log(response);
    })
    .catch((ex) => console.error(ex));
    ```

    Ex: 
    ```Js
    panvivaClient
    .search('data.attributes.classification:\/web\?enabled\/')
    .then((response) => 
    {
        console.log(response);
    })
    .catch((ex) => console.error(ex));
    ```

## When using Python SDK.

1. Construct your Panviva client with necessary URLs and Keys as advised in [here](https://github.com/panviva/toolkit-node-sdk).

2. The `{attributeValue}` in following example will be the **regular expression** you want to construct your logic with. Fill them according to your requirement and make the request to Panviva SDK.

    ```python
    term_to_search = 'data.attributes.classification:\/{attributeValue}\/'
    api_response = api_instance.operations_search(instance, term_to_search)
    ```

    Ex:
    ```python
    term_to_search = 'data.attributes.classification:\/web\?enabled\/'
    api_response = api_instance.operations_search(instance, term_to_search)
    ```