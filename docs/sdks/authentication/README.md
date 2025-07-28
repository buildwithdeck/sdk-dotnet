# Authentication
(*Links.Authentication*)

## Overview

### Available Operations

* [GetMfaQuestion](#getmfaquestion) - Get the security question
* [AnswerMfa](#answermfa) - Provide MFA code

## GetMfaQuestion

Call this endpoint when receiving the connection status MfaQuestion, to get the text of the MFA security question

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/authentication/mfa/get" method="post" path="/link/authentication/mfa/get" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

LinkTokenRequestResponse? req = null;

var res = await sdk.Links.Authentication.GetMfaQuestionAsync(req);

// handle response
```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [LinkTokenRequestResponse](../../Models/Components/LinkTokenRequestResponse.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[PostLinkAuthenticationMfaGetResponse](../../Models/Requests/PostLinkAuthenticationMfaGetResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## AnswerMfa

Call this endpoint to send your MFA code, when receiving MfaCodeRequired or MfaCodeInvalid status from webhook

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/link/authentication/mfa/answer" method="post" path="/link/authentication/mfa/answer" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

SecurityQuestionAnswerSaveRequest? req = null;

var res = await sdk.Links.Authentication.AnswerMfaAsync(req);

// handle response
```

### Parameters

| Parameter                                                                                         | Type                                                                                              | Required                                                                                          | Description                                                                                       |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `request`                                                                                         | [SecurityQuestionAnswerSaveRequest](../../Models/Components/SecurityQuestionAnswerSaveRequest.md) | :heavy_check_mark:                                                                                | The request object to use for the request.                                                        |

### Response

**[PostLinkAuthenticationMfaAnswerResponse](../../Models/Requests/PostLinkAuthenticationMfaAnswerResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |