# Links
(*Links*)

## Overview

### Available Operations

* [Connect](#connect) - Connect with credentials
* [GetConnectionStatus](#getconnectionstatus) - Get the status of an attempted connection
* [ListAccounts](#listaccounts) - Return the list of accounts found while creating connection

## Connect

Sends credential information to a utility data source and attempts to create a connection request asynchronously.

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/connect" method="post" path="/link/connect" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

LinkConnectRequest? req = null;

var res = await sdk.Links.ConnectAsync(req);

// handle response
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [LinkConnectRequest](../../Models/Components/LinkConnectRequest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[PostLinkConnectResponse](../../Models/Requests/PostLinkConnectResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## GetConnectionStatus

Returns the connectivity status about a connection

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/connection/status" method="post" path="/link/connection/status" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

LinkTokenRequestResponse? req = null;

var res = await sdk.Links.GetConnectionStatusAsync(req);

// handle response
```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [LinkTokenRequestResponse](../../Models/Components/LinkTokenRequestResponse.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[PostLinkConnectionStatusResponse](../../Models/Requests/PostLinkConnectionStatusResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## ListAccounts

Return the list of accounts found while creating connection

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/account/list" method="post" path="/link/account/list" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

LinkTokenRequestResponse? req = null;

var res = await sdk.Links.ListAccountsAsync(req);

// handle response
```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [LinkTokenRequestResponse](../../Models/Components/LinkTokenRequestResponse.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[PostLinkAccountListResponse](../../Models/Requests/PostLinkAccountListResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |