#Errors

## Usability guidelines (error reported to the end user)

1) Be clear - use simple language, make sure user understands the problem
2) Be concise - Short and sweet wording makes it quick for user to process
3) Don't use technical jargon - No more error codes to be exposed to user. Must always translate from BE to FE
4) Give direction to user - help user to resolve the problem. (Bare minimum is "Please try again in a few minutes or contact us if the issue persists")
5) Provide relevant actions - Actions should try to provide a route to resolve the error (If no actions possible, then show OK to dismiss error)


Examples of good and bad user messages: https://uxplanet.org/how-to-write-good-error-messages-858e4551cd4

## Format of error Messages

For any error message, we follow [JSON API Standard](https://jsonapi.org/format/#errors) from now on.

When the back end knows what the error is, it should send either a 400 Bad Request or a 422 Unprocessable entity with the following structure for the body:

1) Just a string is enough to give enough information about the problem
```
errors: [
  {
    detail: ["errorCodeToTranslate"]
  }
]
```

2) More information are required, the second element of the array can be anything
```
errors: [
  {
    detail: ["errorCodeToTranslate", { moreInfo: true }]
  }
]
```

For instance, this is the error (400 Bad Request) that is sent in the POF when trying to publish a listing but some fields are missing:
```
errors: [
  {
    detail: [
        "property_flow_required_field_missing", 
        {
            internalReference: true,
            address: false,
            propertyType: false,
            marketingTitle: false,
            marketingDescription: false,
            locationDescription: false,
            owners: false,
            atLeastOneBed: false,
            atLeastTenProfImages: false,
            houseRules: false
        }
    ]
  }
]
```

All the other error codes (401, 403, 429, 500...) will have generic error message 
