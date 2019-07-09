---
title: "Update Policy"
description: "Update properties in a preexisting Conditional Access Policy."
localization_priority: Normal
---

# Update Policy

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update properties in a preexisting [Conditional Access Policy](../resources/ConditionalAccessPolicies.md).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Directory.AccessAsUser.All    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |

## HTTP request

IPNamedLocations
```http
PATCH /ipnamedlocations/{id}
```
CountryNamedLocations
```http
PATCH /countrynamedlocations/{id}
```

## Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| Authorization  | string  | Bearer {token}. Required. |
| Content-Type | application/json  | Nature of the data in the body of an entity. Required. |

## Request body
In the request body, provide a JSON object with the parameters that need to be updated. The following table shows the possible parameters.

## JSON representation
Here is a sample JSON representation of the countryNamedLocation  type.

```json
{
    "@odata.context": "https://canary.graph.microsoft.com/testidentityprotectionservices/$metadata#countryNamedLocations/$entity",
    "id": "18b24242-7d88-4314-ac53-e5a2f39b1b64",
    "displayName": " Country Named Location1 ",
    "modifiedDateTime": "2019-07-09T14:01:39.5554284Z",
    "createdDateTime": "2019-06-05T19:25:10.8867041Z",
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
The following example updates the Country.

##### Request
Here is an example of the request. Where we update the Policy displayName
PATCH https://graph.microsoft.com/beta/countrynamedlocations/{id}

```http
PATCH https://canary.graph.microsoft.com/testidentityprotectionservices/countrynamedlocations/18b24242-7d88-4314-ac53-e5a2f39b1b64
     {
 
    "displayName": " Country Named Location1 ",
     "countriesAndRegions": [
        "US",
        "GB",
        "IN"
    ],
    "includeUnknownCountriesAndRegions": false
        }

```

##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```http
HTTP/1.1 204 No Content
```
