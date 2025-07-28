# JobsDocuments
(*JobsDocuments*)

## Overview

### Available Operations

* [List](#list) - List documents

## List

Returns a list of documents available for the connection associated with the provided link token

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/jobs/documents/list" method="post" path="/jobs/documents/list" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

var res = await sdk.JobsDocuments.ListAsync();

// handle response
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `JobGuid`                                                           | *string*                                                            | :heavy_minus_sign:                                                  | N/A                                                                 |
| `AccessTokenRequest`                                                | [AccessTokenRequest](../../Models/Components/AccessTokenRequest.md) | :heavy_minus_sign:                                                  | N/A                                                                 |

### Response

**[PostJobsDocumentsListResponse](../../Models/Requests/PostJobsDocumentsListResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |