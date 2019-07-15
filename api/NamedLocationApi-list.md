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
    "@odata.context": "https://graph.microsoft.com/beta/adata#namedLocation",
    "values": [
        {
            "@odata.type": "#microsoft.graph.ipNamedLocation"
            "id": "91a40136-f30e-4154-8332-1c576b5bab81",
            "createdDateTime": "2018-01-25T12:34:59Z",
            "modifiedDateTime": "2018-01-28T19:23:04Z",
            "displayName": "Corporate Network",
            "isTrusted": true,
            "ipRanges": [
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "1.2.3.4/24"
                },
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "12.34.56.78/16"
                },
                {
                    "@odata.type": "#microsoft.graph.iPv6CidrRange",
                    "cidrAddress": "1001:0fc3:23fb:1234::0001/24"
                },
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "0.1.2.3/16"
                },
                {
                    "@odata.type": "#microsoft.graph.iPv6CidrRange",
                    "cidrAddress": "1002:abcd:0987::1234::0001/24"
                },
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "4.3.2.1/24"
                }
            ],
        },
        {
            "@odata.type": "#microsoft.graph.countryNamedLocation"
            "id": "8d1eeee9-3695-480d-8e4f-5139cddff38c",
            "createdDateTime": "2018-02-05T09:28:03Z",
            "modifiedDateTime": "2018-02-05T09:28:03Z",
            "displayName": "Banned Countries",
            "includeUnknownCountriesAndRegions": true,
            "countriesAndRegions": [
                "Russia",
                "China",
                "North Korea",
                "Nigeria"
            ]
        },
        {
            "@odata.type": "#microsoft.graph.ipNamedLocation"
            "id": "a90c20af-a36d-4370-afef-efcfc7c64300",
            "createdDateTime": "2018-03-08T15:42:20Z",
            "modifiedDateTime": "2018-03-08T15:42:20Z",
            "displayName": "Partner IP Ranges",
            "isTrusted": false,
            "ipRanges": [
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "9.8.7.6/16"
                },
                {
                    "@odata.type": "#microsoft.graph.iPv4CidrRange",
                    "cidrAddress": "8.7.6.5/24"
                }
            ],
        }
    ]
}

```
