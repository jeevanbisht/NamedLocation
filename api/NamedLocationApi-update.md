---
title: "Update Named Location"
description: "Update properties of an existing named location"
localization_priority: Normal
---

# Update Named Location

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update properties of [NamedLocation](../resources/NamedLocation.md).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Policy.ReadWrite.ConditionalAccess    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |

## HTTP request

```http
PATCH /namedLocations/{id}
```

## Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| Authorization  | string  | Bearer {token}. Required. |
| Content-Type | application/json  | Nature of the data in the body of an entity. Required. |

## Request body
In the request body, provide a JSON object with the parameters that need to be updated. The following JSON representation shows the possible parameters for IP named location type and country named location type.

## JSON representation

#### ipNamedLocation

```json
{
    "@odata.type": "#microsoft.graph.ipNamedLocation",
    "displayName": "IP Named Locations",
    "isTrusted": false,
    "ipRanges": [
        {
            "@odata.type": "#microsoft.graph.iPv4CidrRange",
            "cidrAddress": "12.34.221.11/22"
        },
        {
            "@odata.type": "#microsoft.graph.iPv6CidrRange",
            "cidrAddress": "2001:0:9d38:90d6:0:0:0:0/63"
        }
    ]
}
```

#### countryNamedLocation

```json
{
    "@odata.type": "#microsoft.graph.countryNamedLocation",
    "displayName": "Country Named Location",
    "countriesAndRegions": [
        "US",
        "GB"
    ],
    "includeUnknownCountriesAndRegions": false
}
```

## Response

If successful, this method returns `204 No Content` response code. If unsuccessful, a `4xx` error will be returned with specific details.

## Example
The following examples update certain properties of an IP named location and a country named location.

#### ipNamedLocation

##### Request

```http
PATCH https://graph.microsoft.com/beta/namedLocations/{id}
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.ipNamedLocation",
    "displayName": "Remote Offices",
    "isTrusted": true,
    "ipRanges": [
        {
            "@odata.type": "#microsoft.graph.iPv4CidrRange",
            "cidrAddress": "6.5.4.3/18"
        }

    ]
}
```
##### Response

```http
HTTP/1.1 204 No Content
```

#### countryNamedLocation

##### Request

```http
PATCH https://graph.microsoft.com/beta/namedLocations/{id}
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.countryNamedLocation",
    "displayName": "Country Named Location - Updated",
    "countriesAndRegions": [
        "US",
        "GB",
        "IN"
    ],
    "includeUnknownCountriesAndRegions": true
}
```

##### Response

```http
HTTP/1.1 204 No Content
```
