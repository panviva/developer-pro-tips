# Developer-pro-tips
A collection of pro-tips when using Panviva's APIs directly or via its connectors.

# Prerequisites
### To use this, you must have:

1. Access to a Panviva instance (also known as a tenant)
2. A developer account on the Panviva developer portal ([dev.panviva.com](https://dev.panviva.com))
3. An active Panviva API subscription (also known as an API plan) and valid Panviva API credentials

If you are not a customer or need help visit [www.panviva.com/support](https://www.panviva.com/support).

### How to get credentials

Follow the steps below to get your `API key` & `instance name`.

To get your API key you must:

1. Sign into the Panviva developer portal at [dev.panviva.com](https://dev.panviva.com)
2. Navigate to your profile (click your name then click "Profile" from the top navigation bar)
3. Your should now see your API key under "Your Subscriptions" section of your profile.

To get your instance name you must:

1. Sign into the Panviva developer portal at [dev.panviva.com](https://dev.panviva.com)
2. Navigate to your API (click "APIs" from the top navigation bar)
3. You should now see your API instance under your API suite (look for "_The instance name for the API Suite is_")

You can use the techniques documented here with any application which can handle REST API calls, or you can use following toolkit provided by Panviva.

- [.Net SDK](https://github.com/panviva/toolkit-dotnet-sdk)
- [Python SDK](https://github.com/panviva/toolkit-python-sdk)
- [node SDK](https://github.com/panviva/toolkit-node-sdk)
- [php SDK](https://github.com/panviva/toolkit-php-sdk)

# Pro-Tips table of content


|#| Endpoint       | Method           | Link  |
| -----| ------------- |-------------| -----|
|a.|Search API| Search for a term | [link](search/search-for-a-term.md) |
||| Search for term with a filter | [link](search/search-for-a-term-with-filter.md) |
||| Filter date ranges | [link](search/filter-date-ranges.md) |
||| Filter if property exists | [link](search/filter-if-property-exists.md) |
||| Filter if property is missing | [link](search/filter-if-property-is-missing.md) |
||| Filter with conditional operators | [link](search/filter-with-conditional-operators.md) |
||| Filer with regular expressions | [link](search/filer-with-regular-expressions.md) |
||| Negative search | [link](search/negative-search.md) |
|b.|Search Artefacts API| Search by a query | [link](search-artefacts/search-for-a-query.md) |
||| Search by a query (Lucene) | [link](search-artefacts/search-for-a-query-lucene.md) |
||| Filter by a document ID | [link](search-artefacts/filter-artefacts-by-panviva-document-id.md) |
||| Filter by category | [link](search-artefacts/filter-artefacts-by-category.md) |
||| Filter by metadata | [link](search-artefacts/filter-artefacts-by-metadata.md) |
||| Filter by date range | [link](search-artefacts/filter-artefacts-by-date-range.md) |
||| Facet by category | [link](search-artefacts/facet-artefacts-by-category.md) |