<!-- Start SDK Example Usage [usage] -->
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