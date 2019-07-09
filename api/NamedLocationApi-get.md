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
