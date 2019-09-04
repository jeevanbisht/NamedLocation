---
title: "Delete Named Location"
description: "Delete a named location."
localization_priority: Normal
---

# Delete Policy

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Delete a [Named Location](../resources/NamedLocation.md).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Policy.ReadWrite.ConditionalAccess    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |


## HTTP request
```http
DELETE /namedLocations/{id}
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
The following example deletes a named location.

##### Request
Here is an example of the request.

```http
DELETE https://graph.microsoft.com/beta/namedLocations/{id}
```

##### Response
Here is an example of the response.

```http
HTTP/1.1 204 No Content
```