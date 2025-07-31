# Deck.SDK


<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

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
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security schemes globally:

| Name       | Type   | Scheme  |
| ---------- | ------ | ------- |
| `ClientId` | apiKey | API key |
| `Secret`   | apiKey | API key |

You can set the security parameters through the `security` optional parameter when initializing the SDK client instance. The selected scheme will be used by default to authenticate with the API for all operations that support it. For example:
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
<!-- End Authentication [security] -->

<!-- Start Error Handling [errors] -->
## Error Handling

Handling errors in this SDK should largely match your expectations. All operations return a response object or throw an exception.

By default, an API error will raise a `Deck.SDK.Models.Errors.APIException` exception, which has the following properties:

| Property      | Type                  | Description           |
|---------------|-----------------------|-----------------------|
| `Message`     | *string*              | The error message     |
| `Request`     | *HttpRequestMessage*  | The HTTP request      |
| `Response`    | *HttpResponseMessage* | The HTTP response     |

When custom error responses are specified for an operation, the SDK may also throw their associated exceptions. You can refer to respective *Errors* tables in SDK docs for more details on possible exception types for each operation. For example, the `SubmitAsync` method throws the following exceptions:

| Error Type                                                | Status Code | Content Type     |
| --------------------------------------------------------- | ----------- | ---------------- |
| Deck.SDK.Models.Errors.BadRequestJobResponseException     | 400         | application/json |
| Deck.SDK.Models.Errors.BadRequestJobResponseException     | 400         | text/json        |
| Deck.SDK.Models.Errors.AlreadyRunningJobResponseException | 409         | application/json |
| Deck.SDK.Models.Errors.AlreadyRunningJobResponseException | 409         | text/json        |
| Deck.SDK.Models.Errors.APIException                       | 4XX, 5XX    | \*/\*            |

### Example

```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;
using Deck.SDK.Models.Errors;
using Deck.SDK.Models.Requests;
using System.Collections.Generic;

var sdk = new DeckSDK(security: new Security() {
    ClientId = "<YOUR_API_KEY_HERE>",
    Secret = "<YOUR_API_KEY_HERE>",
});

try
{
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
}
catch (Exception ex)
{
    if (ex is BadRequestJobResponseException)
    {
        // Handle exception data
        throw;
    }
    else if (ex is BadRequestJobResponseException)
    {
        // Handle exception data
        throw;
    }
    else if (ex is AlreadyRunningJobResponseException)
    {
        // Handle exception data
        throw;
    }
    else if (ex is AlreadyRunningJobResponseException)
    {
        // Handle exception data
        throw;
    }
    else if (ex is Deck.SDK.Models.Errors.APIException)
    {
        // Handle default exception
        throw;
    }
}
```
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Select Server by Index

You can override the default server globally by passing a server index to the `serverIndex: int` optional parameter when initializing the SDK client instance. The selected server will then be used as the default on the operations that use it. This table lists the indexes associated with the available servers:

| #   | Server                           | Description      |
| --- | -------------------------------- | ---------------- |
| 0   | `https://sandbox.deck.co/api/v1` | Deck Sandbox API |
| 1   | `https://live.deck.co/api/v1`    | Deck API         |

#### Example

```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;
using Deck.SDK.Models.Requests;
using System.Collections.Generic;

var sdk = new DeckSDK(
    serverIndex: 1,
    security: new Security() {
        ClientId = "<YOUR_API_KEY_HERE>",
        Secret = "<YOUR_API_KEY_HERE>",
    }
);

PostJobsSubmitRequest req = new PostJobsSubmitRequest() {
    JobCode = "FetchDocuments",
    Input = new Dictionary<string, string>() {
        { "someProperty", "someValue" },
        { "access_token", "access-development-6599f8dd-1a1c-4586-39d1-08ddb97283f7" },
        { "key1", "value1" },
    },
};

var res = await sdk.Jobs.SubmitAsync(req);

// handle response
```

### Override Server URL Per-Client

The default server can also be overridden globally by passing a URL to the `serverUrl: string` optional parameter when initializing the SDK client instance. For example:
```csharp
using Deck.SDK;
using Deck.SDK.Models.Components;
using Deck.SDK.Models.Requests;
using System.Collections.Generic;

var sdk = new DeckSDK(
    serverUrl: "https://live.deck.co/api/v1",
    security: new Security() {
        ClientId = "<YOUR_API_KEY_HERE>",
        Secret = "<YOUR_API_KEY_HERE>",
    }
);

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
<!-- End Server Selection [server] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->