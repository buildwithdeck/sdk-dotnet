# ConnectionPublicTokenExchangeResponse


## Fields

| Field                                                                               | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `AccessToken`                                                                       | *string*                                                                            | :heavy_minus_sign:                                                                  | The access token associated with the connection data is being requested for         |
| `ConnectionId`                                                                      | *string*                                                                            | :heavy_minus_sign:                                                                  | The Deck Connection ID for the connection associated with the returned access token |
| `Fields`                                                                            | List<[LinkConnectRequestField](../../Models/Components/LinkConnectRequestField.md)> | :heavy_check_mark:                                                                  | List of non-sensitive values provided from the Link session by the user             |