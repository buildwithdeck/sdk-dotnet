# Connections
(*Connections*)

## Overview

### Available Operations

* [InvalidateAccessToken](#invalidateaccesstoken) - Invalidate access_token
* [UpdateWebhook](#updatewebhook) - Update the webhook url for a connection

## InvalidateAccessToken

Rotate the access_token associated with a connection. The endpoint returns a new access_token and immediately invalidates the previous access_token.

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/connection/access_token/invalidate" method="post" path="/connection/access_token/invalidate" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

AccessTokenRequest? req = null;

var res = await sdk.Connections.InvalidateAccessTokenAsync(req);

// handle response
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [AccessTokenRequest](../../Models/Components/AccessTokenRequest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[PostConnectionAccessTokenInvalidateResponse](../../Models/Requests/PostConnectionAccessTokenInvalidateResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## UpdateWebhook

Decide where the webhook event should be sent to for a specific connection.

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/connection/webhook/update" method="post" path="/connection/webhook/update" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

WebhookUpdateRequest? req = null;

var res = await sdk.Connections.UpdateWebhookAsync(req);

// handle response
```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `request`                                                               | [WebhookUpdateRequest](../../Models/Components/WebhookUpdateRequest.md) | :heavy_check_mark:                                                      | The request object to use for the request.                              |

### Response

**[PostConnectionWebhookUpdateResponse](../../Models/Requests/PostConnectionWebhookUpdateResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |