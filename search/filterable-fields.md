# Filterable-fields and attributes in Panviva `GET Search` endpoint

When you want to add a filter to your search query you can use the parameters documented here.

The sample json payload of the filterable object is as follows.

```json
{
   "data":[
      {
         "type":"document",
         "id":"123",
         "links":{
            "self":"https://api.panviva.com/v2/viva-bank/document/123"
         },
         "attributes":{
            "name":"Content development guidelines",
            "language":"en-US",
            "classification":"SupportPoint 7.0 release",
            "layout":"leftTabsMedium",
            "updatedDate":"2020-02-21T15:03:07.57Z"
         }
      }
   ]
}

```

Here are all the fields you can filter these results from.


- Type
    - Possible values = `"document"` , `"folder"` , `"file"` ,  `"container"`, `"image"`
    - filter attribute structure = `data.type:`
    - example query = `data.type:document`

- Id
    - Possible values =  Valid Panviva resource ID
    - filter attribute structure = `data.id:`
    - example query = `data.id:1234`

- Name
    - Possible values =  Any String
    - filter attribute structure = `data.attributes.name:`
    - example query = `data.attributes.name:Example Document Name`

- Language
    - Possible values =  Valid Language-Country code
    - filter attribute structure = `data.attributes.language:`
    - example query = `data.attributes.language:en-US`

- Classification
    - Possible values =  Any String
    - filter attribute structure = `data.attributes.classification:`
    - example query = `data.attributes.classification:SupportPoint 7.0 release`

- layout
    - Possible values =  DocumentResourceLayout in Panviva.SupportPoint as string
    - filter attribute structure = `data.attributes.layout:`
    - example query = `data.attributes.layout:leftTabsMedium`

- UpdatedDate
    - Possible values =  String date in `yyyy-mm-dd` format
    - filter attribute structure = `data.attributes.updatedDate:`
    - example query = `data.attributes.updatedDate:2020-02-18`

- Language
    - Possible values =  Valid Language-Country code
    - filter attribute structure = `data.attributes.language:`
    - example query = `data.attributes.language:en-US`