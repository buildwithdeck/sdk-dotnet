# Connection
(*Connection*)

## Overview

Manage connections

### Available Operations

* [ExchangePublicToken](#exchangepublictoken) - Exchange public token for an access token
* [GetContext](#getcontext) - Get connection status details
* [GetAccounts](#getaccounts) - Get the connection list of account numbers
* [SelectAccounts](#selectaccounts) - Update the list of accounts to be considered
* [UpdateAutoRefresh](#updateautorefresh) - Update connection stream config
* [Refresh](#refresh) - Request manual refresh
* [Destroy](#destroy) - Delete all data related to a connection, losing access to it.

## ExchangePublicToken

Exchange a Link public_token for an API access_token. Link hands off the public_token client-side via the onSuccess callback once a user has successfully created a connection.

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/connection/public_token/exchange" method="post" path="/connection/public_token/exchange" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

ConnectionPublicTokenExchangeRequest? req = null;

var res = await sdk.Connection.ExchangePublicTokenAsync(req);

// handle response
```

### Parameters

| Parameter                                                                                               | Type                                                                                                    | Required                                                                                                | Description                                                                                             |
| ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| `request`                                                                                               | [ConnectionPublicTokenExchangeRequest](../../Models/Components/ConnectionPublicTokenExchangeRequest.md) | :heavy_check_mark:                                                                                      | The request object to use for the request.                                                              |

### Response

**[PostConnectionPublicTokenExchangeResponse](../../Models/Requests/PostConnectionPublicTokenExchangeResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## GetContext

Get connection status details

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/connection/context" method="post" path="/connection/context" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

AccessTokenRequest? req = null;

var res = await sdk.Connection.GetContextAsync(req);

// handle response
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [AccessTokenRequest](../../Models/Components/AccessTokenRequest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[PostConnectionContextResponse](../../Models/Requests/PostConnectionContextResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## GetAccounts

Get the connection list of account numbers

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/connection/accounts" method="post" path="/connection/accounts" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

AccessTokenRequest? req = null;

var res = await sdk.Connection.GetAccountsAsync(req);

// handle response
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [AccessTokenRequest](../../Models/Components/AccessTokenRequest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[PostConnectionAccountsResponse](../../Models/Requests/PostConnectionAccountsResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## SelectAccounts

Update the list of accounts to be considered

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/connection/accounts/select" method="post" path="/connection/accounts/select" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

SelectConnectionAccountsRequest? req = null;

var res = await sdk.Connection.SelectAccountsAsync(req);

// handle response
```

### Parameters

| Parameter                                                                                     | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `request`                                                                                     | [SelectConnectionAccountsRequest](../../Models/Components/SelectConnectionAccountsRequest.md) | :heavy_check_mark:                                                                            | The request object to use for the request.                                                    |

### Response

**[PostConnectionAccountsSelectResponse](../../Models/Requests/PostConnectionAccountsSelectResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## UpdateAutoRefresh

You can control which individual connections need to be regularly refreshed or not.

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/connection/auto_refresh/update" method="post" path="/connection/auto_refresh/update" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

AutoRefreshUpdateRequest? req = null;

var res = await sdk.Connection.UpdateAutoRefreshAsync(req);

// handle response
```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [AutoRefreshUpdateRequest](../../Models/Components/AutoRefreshUpdateRequest.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[PostConnectionAutoRefreshUpdateResponse](../../Models/Requests/PostConnectionAutoRefreshUpdateResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## Refresh

This will initiate a new session for refreshing the data related to a connection.

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/connection/refresh" method="post" path="/connection/refresh" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

RefreshConnectionRequest? req = null;

var res = await sdk.Connection.RefreshAsync(req);

// handle response
```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [RefreshConnectionRequest](../../Models/Components/RefreshConnectionRequest.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[PostConnectionRefreshResponse](../../Models/Requests/PostConnectionRefreshResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## Destroy

Delete all data related to a connection, losing access to it.

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/connection/destroy" method="post" path="/connection/destroy" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

AccessTokenRequest? req = null;

var res = await sdk.Connection.DestroyAsync(req);

// handle response
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [AccessTokenRequest](../../Models/Components/AccessTokenRequest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[PostConnectionDestroyResponse](../../Models/Requests/PostConnectionDestroyResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |