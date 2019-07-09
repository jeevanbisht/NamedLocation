---
title: "Delete a Named Location Entity."
description: "Delete a Named Location Entity."
localization_priority: Normal
---

# Delete Policy

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Delete a [Named Location Entity](../resources/NamedLocation.md).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Policy.ReadWrite.ConditionalAccess    |

## HTTP request
NameLocation (Common endpoint)
```http
DELETE /namedLocations/{id}
```

IPNamedLocation
```http
DELETE /ipnamedLocations/{id}
```

CountryNamedLocation
```http

DELETE /countrynamedLocations/{id}
```
## Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| Authorization  | string  | Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns `204 No Content` response code. If unsuccessful...

## Example
The following example deletes a policy.

##### Request
Here is an example of the request.

```http
DELETE https://canary.graph.microsoft.com/testidentityprotectionservices/namedlocations/00b32017-8d7c-42d4-81a9-3a94f3b96326

```

##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```http
HTTP/1.1 204 No Content
```

