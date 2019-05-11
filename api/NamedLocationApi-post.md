---
title: "Create Named Location Entity Object"
description: "Create a new Named Location Entity Object by specifying display name and minimum required parameters."
localization_priority: Normal
---

# Create Policy

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new [Named Location](../resources/NamedLocations.md) object by specifying display name, policy type, and policy description.

>Note: The policy details will be validated before being stored. If it does not pass validation, a 400 Bad Request will be returned.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Policy.ReadWrite.ConditionalAccess    |

## HTTP request

```http
POST /namedLocations
```
## Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| Authorization  | string  | Bearer {token}. Required. |
| Content-Type | application/json  | Nature of the data in the body of an entity. Required. |

## Request body
In the request body, provide a JSON representation of [Named Location](../resources/ConditionalAccessPolicies.md) object.

The following table shows the properties that are required when you create a policy.

| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|definition|String|The string version of the [policy](../resources/namedLoction.md) object.|
|displayName|String|A custom name for the Conditional Access Policy.|


## Response

If successful, this method returns `204` response code and [Named Location](../resources/NamedLocation.md) object in the response body. If unsuccessful, a `4xx` error will be returned with specific details.  

## Example
The following example creates a IP Named Location. Notice the string definition parameter
has escaped double quotes.

##### Request
Here is an example of the request.

```http
POST https://graph.microsoft.com/beta/ipNamedLocation/
 {
            "displayName": "Public Relations Office ",
            "modifiedDateTime": null,
            "createdDateTime": null,
            "isTrusted": false,
            "ipRanges": [
                {
                  "cidrAddress": "12.34.221.11/22"
                }
            ]
        }

```

##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```http
HTTP/1.1 204 No Content

```

-->
