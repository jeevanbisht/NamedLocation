---
title: "List a collectoin of Named Location Entity."
description: "Retrieve all Named Location Entity objects in the directory."
localization_priority: Normal
---

# List Policies

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve all [Named Location Entity](../resources/NamedLocation.md) objects in the directory.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Policy.Read.ConditionalAccess or Policy.ReadWrite.ConditionalAccess   |

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

If successful, this method returns `200 OK` response code and [Named Location Entity](../resources/NamedLocation.md) objects in the response body. If unsuccessful...

## Example
The following example retrieves all policies.

##### Request
Here is an example of the request.

```http
GET https://graph.microsoft.com/beta/namedLocations/
```

##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```http
HTTP/1.1 200 OK

{
    "@odata.context": "https://canary.graph.microsoft.com/testidentityprotectionservices/$metadata#namedLocations",
    "@odata.count": 5,
    "value": [
        {
            "@odata.type": "#microsoft.graph.countryNamedLocation",
            "id": "18b24242-7d88-4314-ac53-e5a2f39b1b64",
            "displayName": " Country Named Location1 ",
            "modifiedDateTime": "2019-07-09T14:03:37.4501821Z",
            "createdDateTime": "2019-06-05T19:25:10.8867041Z",
            "countriesAndRegions": [
                "US",
                "GB",
                "IN"
            ],
            "includeUnknownCountriesAndRegions": false
        },
        {
            "@odata.type": "#microsoft.graph.countryNamedLocation",
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
            "@odata.type": "#microsoft.graph.countryNamedLocation",
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
            "@odata.type": "#microsoft.graph.countryNamedLocation",
            "id": "15b0a9e9-bc14-4db1-9852-b798f3457392",
            "displayName": " Country Named Location1 ",
            "modifiedDateTime": "2019-07-09T13:44:05.6758195Z",
            "createdDateTime": "2019-07-09T13:44:05.6758195Z",
            "countriesAndRegions": [
                "US",
                "GB"
            ],
            "includeUnknownCountriesAndRegions": false
        },
        {
            "@odata.type": "#microsoft.graph.ipNamedLocation",
            "id": "09a6271a-8b14-41a3-a191-cea3531b3ed8",
            "displayName": "Remote Offices",
            "modifiedDateTime": "2019-07-09T14:07:06.359865Z",
            "createdDateTime": "2019-07-09T14:06:12.2198099Z",
            "isTrusted": true,
            "ipRanges": [
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "6.5.4.3/18"
                }
            ]
        }
    ]
}

```


Request
Here is an example of the request.
```http
GET https://graph.microsoft.com/beta/namedLocations/
```
Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
```http
HTTP/1.1 200 OK
```
