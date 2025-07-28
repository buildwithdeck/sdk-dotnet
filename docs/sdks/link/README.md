# Link
(*Link*)

## Overview

These endpoints are used by the Link widget. They can also be used for creating your own UX experience and connecting data from utility data sources.

### Available Operations

* [CreateToken](#createtoken) - Create a Link Token for running a Link session
* [GetInfo](#getinfo) - Get client information
* [SearchSources](#searchsources) - Search sources
* [SelectAccount](#selectaccount) - Select accounts
* [GetToken](#gettoken) - Get information about a previously created link_token

## CreateToken

Returns a Link Token to be used in a Link session, customized with options for controlling which sources to make available.

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/token/create" method="post" path="/link/token/create" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

LinkTokenCreateRequest? req = null;

var res = await sdk.Link.CreateTokenAsync(req);

// handle response
```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `request`                                                                   | [LinkTokenCreateRequest](../../Models/Components/LinkTokenCreateRequest.md) | :heavy_check_mark:                                                          | The request object to use for the request.                                  |

### Response

**[PostLinkTokenCreateResponse](../../Models/Requests/PostLinkTokenCreateResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## GetInfo

Returns information about the client currently using Datadeck for connecting data from a utility data source. The client name and logo are displayed on the first screen of the Datadeck Link widget.

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/info" method="post" path="/link/info" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

LinkTokenRequestResponse? req = null;

var res = await sdk.Link.GetInfoAsync(req);

// handle response
```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [LinkTokenRequestResponse](../../Models/Components/LinkTokenRequestResponse.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[PostLinkInfoResponse](../../Models/Requests/PostLinkInfoResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## SearchSources

Returns a list of data sources based on a few search parameters

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/sources" method="post" path="/link/sources" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

LinkSourcesRequest? req = null;

var res = await sdk.Link.SearchSourcesAsync(req);

// handle response
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [LinkSourcesRequest](../../Models/Components/LinkSourcesRequest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[PostLinkSourcesResponse](../../Models/Requests/PostLinkSourcesResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## SelectAccount

Call this endpoint to select which accounts to consider, when receiving AccountSelectionRequired status from webhook

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/account/select" method="post" path="/link/account/select" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

LinkAccountSelectRequest? req = null;

var res = await sdk.Link.SelectAccountAsync(req);

// handle response
```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [LinkAccountSelectRequest](../../Models/Components/LinkAccountSelectRequest.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[PostLinkAccountSelectResponse](../../Models/Requests/PostLinkAccountSelectResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## GetToken

Returns the associated parameters that were used when creating a link_token

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/token/get" method="post" path="/link/token/get" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

LinkTokenRequestResponse? req = null;

var res = await sdk.Link.GetTokenAsync(req);

// handle response
```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [LinkTokenRequestResponse](../../Models/Components/LinkTokenRequestResponse.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[PostLinkTokenGetResponse](../../Models/Requests/PostLinkTokenGetResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |