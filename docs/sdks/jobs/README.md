# Jobs
(*Jobs*)

## Overview

Endpoints related to jobs.

### Available Operations

* [Submit](#submit) - Send your job requests
* [AnswerMFA](#answermfa) - Provide MFA code
* [GetDocumentFile](#getdocumentfile) - Get raw file

## Submit

Provide a job code along with its input parameters to execute it

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/jobs/submit" method="post" path="/jobs/submit" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;
using Deck.SDK.Models.Requests;
using System.Collections.Generic;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

PostJobsSubmitRequest req = new PostJobsSubmitRequest() {
    JobCode = "FetchDocuments",
    Input = new Dictionary<string, string>() {
        { "access_token", "access-development-6599f8dd-1a1c-4586-39d1-08ddb97283f7" },
        { "key1", "value1" },
        { "someProperty", "someValue" },
    },
};

var res = await sdk.Jobs.SubmitAsync(req);

// handle response
```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `request`                                                               | [PostJobsSubmitRequest](../../Models/Requests/PostJobsSubmitRequest.md) | :heavy_check_mark:                                                      | The request object to use for the request.                              |

### Response

**[PostJobsSubmitResponse](../../Models/Requests/PostJobsSubmitResponse.md)**

### Errors

| Error Type                                                | Status Code                                               | Content Type                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| Deck.SDK.Models.Errors.BadRequestJobResponseException     | 400                                                       | application/json                                          |
| Deck.SDK.Models.Errors.BadRequestJobResponseException     | 400                                                       | text/json                                                 |
| Deck.SDK.Models.Errors.AlreadyRunningJobResponseException | 409                                                       | application/json                                          |
| Deck.SDK.Models.Errors.AlreadyRunningJobResponseException | 409                                                       | text/json                                                 |
| Deck.SDK.Models.Errors.APIException                       | 4XX, 5XX                                                  | \*/\*                                                     |

## AnswerMFA

Call this endpoint to send your MFA code

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/jobs/mfa/answer" method="post" path="/jobs/mfa/answer" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

MfaAnswerRequest? req = null;

var res = await sdk.Jobs.AnswerMFAAsync(req);

// handle response
```

### Parameters

| Parameter                                                       | Type                                                            | Required                                                        | Description                                                     |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| `request`                                                       | [MfaAnswerRequest](../../Models/Components/MfaAnswerRequest.md) | :heavy_check_mark:                                              | The request object to use for the request.                      |

### Response

**[PostJobsMfaAnswerResponse](../../Models/Requests/PostJobsMfaAnswerResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |

## GetDocumentFile

Returns the raw file for the document with the provided document ID

### Example Usage

<!-- UsageSnippet language="csharp" operationID="post_/jobs/documents/file" method="post" path="/jobs/documents/file" -->
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

RawDocumentRequest? req = null;

var res = await sdk.Jobs.GetDocumentFileAsync(req);

// handle response
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [RawDocumentRequest](../../Models/Components/RawDocumentRequest.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[PostJobsDocumentsFileResponse](../../Models/Requests/PostJobsDocumentsFileResponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | application/json                            |
| Deck.SDK.Models.Errors.ErrorMessageResponse | 400                                         | text/json                                   |
| Deck.SDK.Models.Errors.APIException         | 4XX, 5XX                                    | \*/\*                                       |