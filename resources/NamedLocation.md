---
title: "Named Locations API"
description: "Represents a Named Location."
localization_priority: Normal
---


# Methods

| Method | Return  Type | Description |
|:---------------------|:----------|:-------:|
| Get 	  | Named Location |Read properties of a Named Location  object. |
| Create 	| Named Location |Create a new Named Location object. |
| Update  |	None	|Update Named Location object. |
| Delete  |	None	|Delete Named Location object. |
| List   	| Named Location |Collection of all Named Location objects in the organization. |


# Named Location 

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an Azure AD NamedLocation. Named Location are customm rules that define Network Locations.


#### namedLocation

| Property   | Type|Description|Read-Only|
|:---------------|:--------|:----------|:-------:|
|`createdDateTime`|`DateTimeOffset` | creation datetime of the location |✓|
|`modifiedDateTime`|`DateTimeOffset` | last modification datetime of the location |✓|
|`displayName`|`String`| human-readable name of the location ||

#### countryNamedLocation

| Property   | Type|Description|Read-Only|
|:---------------|:--------|:----------|:-------:|
|`countriesAndRegions`|`Collection of strings`| List of countries and/or regions in two-letter format specified by ISO 3166-2||
|`includeUnknownCountriesAndRegions`|`Boolean`| True if IP addresses that don't map to a country or region should be included in the named location||

#### ipNamedLocation

| Property   | Type|Description|Read-Only|
|:---------------|:--------|:----------|:-------:|
|`ipRanges`|`Collection of IP addresses in CIDR format`| List of strings of IP address ranges in IPv4 CIDR format (e.g. 1.2.3.4/32) or any allowable IPv6 format from IETF RFC5962||
|`isTrusted`|`Boolean`| is this location explicitly trusted||


**Errors:**

|Scenario|Method|Code|Message|
|--------|------|----|-------|
|User doesn't have appropriate permission scope|All|403|Your account does not have access to this action. Please contact your global administrator to request access.|
|Tenant not licensed for this functionality|All|403|Your tenant is not licensed for this functionality. Please refer to your license agreement to determine which conditional access functionality is available at your license level.|
|Invalid location details|POST,PATCH|400|The supplied JSON for your location is invalid. Please correct it and try your query again.|
|Conflicting location types|POST,PATCH|400|The supplied JSON for your policy's conditions contains both IP ranges and countries/regions. A location may only contain one or the other. Please correct it and try your query again.|
|Invalid IP range(s)|POST,PATCH|400|The supplied JSON contains one or more invalid IP address ranges. Please correct your ranges to use CIDR format such as x.x.x.x/x and try your query again.|





#### iPv4CidrRange

> IPv4 range in CIDR format. Inherits from ipRange.

|Property|Type|Description|
|-|-|-|
|`cidrAddress`|`String`|IPv4 address in CIDR format|

#### iPv6CidrRange

> IPv6 range in CIDR format. Inherits from ipRange.

|Property|Type|Description|
|-|-|-|
|`cidrAddress`|`String`|IPv6 address in CIDR format|
