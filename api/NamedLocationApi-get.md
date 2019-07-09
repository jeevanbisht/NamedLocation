---
title: "Get Named Location Entity."
description: "Retrieve the properties of a Named Location Entity."
localization_priority: Normal
---

# Get Policy

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the properties of a [Named Location](../resources/NamedLocation.md).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Policy.Read.ConditionalAcces or  Policy.ReadWrite.ConditionalAccess   |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
Common EndPoint to query IPNamedLocation and CountryNamedLocation
GET /namedLocations/{id}

IPNamedLocations
GET /ipnamedLocations/{id}

CountryNamedLocations
GET /countyrnamedLocations/{id}
```
## Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| Authorization  | string  | Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns `200 OK` response code and a [Named Location](../resources/NamedLocation.md) object in the response body. If unsucccessful...

## Example
The following example retrieves a specific policy.

##### Request
Here is an example of the request.

```http
GET https://graph.microsoft.com/beta/namedLocations/<id>

```

##### Response
Here is an example of the response.
Note: Additonal metadata might be added when querying the common endpoint /namedlocations
The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```http

{
    "@odata.context": "https://graph.microsoft.com/testidentityprotectionservices/$metadata#namedLocations",
    "@odata.count": 3,
    "value": [
        {
            "@odata.type": "#microsoft.graph.countryNamedLocation",
            "id": "5958aa55-00cc-4af0-8b2f-e93567e60c53",
            "displayName": "AsiaOffices",
            "modifiedDateTime": null,
            "createdDateTime": null,
            "countriesAndRegions": [
                "AF",
                "AX"
            ],
            "includeUnknownCountriesAndRegions": false
        },
        {
            "@odata.type": "#microsoft.graph.ipNamedLocation",
            "id": "f38d8e56-aea6-4992-8282-26cfd00db70c",
            "displayName": "Public Relationks",
            "modifiedDateTime": null,
            "createdDateTime": null,
            "isTrusted": false,
            "ipRanges": [
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "12.34.221.11/2"
                }
            ]
        },
        {
            "@odata.type": "#microsoft.graph.ipNamedLocation",
            "id": "36eee644-d92c-4cc0-a12d-68303f9c4286",
            "displayName": "Redmond Office",
            "modifiedDateTime": null,
            "createdDateTime": null,
            "isTrusted": true,
            "ipRanges": [
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "12.12.1.2/24"
                }
            ]
        }
    ]
}
```

##### Request
Here is an example of the request.

```http
GET https://graph.microsoft.com/beta/ipnamedLocations/<id>

```

##### Response
Here is an example of the response.

```http

{
    "@odata.context": "https://canary.graph.microsoft.com/testidentityprotectionservices/$metadata#ipNamedLocations",
    "@odata.count": 2,
    "value": [
        {
            "id": "00b32017-8d7c-42d4-81a9-3a94f3b96326",
            "displayName": "Remote Offices",
            "modifiedDateTime": "2019-06-05T19:22:34.4081849Z",
            "createdDateTime": "2019-06-05T19:22:34.4081849Z",
            "isTrusted": true,
            "ipRanges": [
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "6.5.4.3/16"
                },
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "5.4.3.2/16"
                },
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "4.3.2.1/16"
                }
            ]
        },
        {
            "id": "02a51ffb-dfe5-455d-9d04-fe6811c7ed6b",
            "displayName": "IP Named Locations ",
            "modifiedDateTime": "2019-07-09T13:35:53.3996163Z",
            "createdDateTime": "2019-07-09T13:35:53.3996163Z",
            "isTrusted": false,
            "ipRanges": [
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "12.34.221.11/22"
                },
                {
                    "@odata.type": "#microsoft.graph.iPv6CidrRange",
                    "cidrAddress": "1001:0fc3:23fb:1234::0001/24"
                }
            ]
        }
    ]
}
```



##### Request
Here is an example of the request.

```http
GET https://graph.microsoft.com/beta/countrynamedLocations/<id>

```

##### Response
Here is an example of the response.

```http
{
    "@odata.context": "https://canary.graph.microsoft.com/testidentityprotectionservices/$metadata#countryNamedLocations",
    "@odata.count": 4,
    "value": [
        {
            "id": "18b24242-7d88-4314-ac53-e5a2f39b1b64",
            "displayName": "Remote Offices",
            "modifiedDateTime": "2019-06-05T19:30:44.0120563Z",
            "createdDateTime": "2019-06-05T19:25:10.8867041Z",
            "countriesAndRegions": [
                "IN",
                "US"
            ],
            "includeUnknownCountriesAndRegions": false
        },
        {
            "id": "1ce50e62-ab64-4966-9a19-2d609c3205d7",
            "displayName": "Remote Offices1",
            "modifiedDateTime": "2019-06-06T22:53:11.3245652Z",
            "createdDateTime": "2019-06-06T22:53:11.3245652Z",
            "countriesAndRegions": [
                "IN"
            ],
            "includeUnknownCountriesAndRegions": false
        },
        {
            "id": "105dc8b1-0930-4668-8ffa-1f1d586e3b38",
            "displayName": " Country Named Location1 ",
            "modifiedDateTime": "2019-07-09T13:41:03.5983142Z",
            "createdDateTime": "2019-07-09T13:41:03.5983142Z",
            "countriesAndRegions": [
                "US",
                "GB"
            ],
            "includeUnknownCountriesAndRegions": false
        },
        {
            "id": "15b0a9e9-bc14-4db1-9852-b798f3457392",
            "displayName": " Country Named Location1 ",
            "modifiedDateTime": "2019-07-09T13:44:05.6758195Z",
            "createdDateTime": "2019-07-09T13:44:05.6758195Z",
            "countriesAndRegions": [
                "US",
                "GB"
            ],
            "includeUnknownCountriesAndRegions": false
        }
    ]
}
```

