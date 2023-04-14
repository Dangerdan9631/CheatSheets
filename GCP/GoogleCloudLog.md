# Google Cloud Log Cheatsheet
https://cloud.google.com/logging/docs/view/logging-query-language

* Query cannot exceed 20,000 characters
* Query is case-insensitive, except in regex's.

## Query Syntax
`expression = ["NOT"] comparison { ("AND" | "OR") ["NOT"] comparison }`
Comparison is either single value or a Boolean expression

## Boolean Operators
Order of operations
* `NOT` `OR` `AND`
  ```
  a OR NOT b AND NOT c OR d
  (a OR (NOT b)) AND ((NOT c) OR d)
  ```

Examples
* `resource.type = "gae_app" AND severity = ERROR`
* `resource.type = "gae_app" OR resource.type = "gce_instance"`
* `resource.type = ("gae_app" OR "gce_instance")`
* `resource.type = "gae_app" AND (severity = ERROR or "error")`
* `resource.type = "gae_app" AND NOT severity = ERROR`

`AND` operator can be ommited
* `resource.type = "gae_app" AND severity = ERROR`
* `resource.type = "gae_app" severity = ERROR`

`NOT` operator can be replaced with `-`
* `resource.type = "gae_app" AND NOT severity = ERROR`
* `resource.type = "gae_app" -severity = ERROR`

Log views only support `AND` and `NOT`

## Comparisons
`[FIELD_NAME] [OP] [VALUE]`

### FIELD_NAME
`FIELD_NAME` is a path name of a field in a log entry
* `resource.type`
* `resource.labels.zone`
* `resource.labels.project_id`
* `insertId`
* `jsonPayload.httpRequest.protocol`
* `labels.[KEY]`
  * keys are case sensitive

Use quotes in path name to escape special characters.
* `labels."compute.googleapis.com/resource_id"`

### OP
`OP` is a comparison operator
* `=` - equal
* `!=` - not equal
* `>` `<` `>=` `<=` - numeric ordering
* `:` - "has" - matches any substring in the log entry field
* `=~` - regular expression search for a pattern
* `!~` - regular expression search not for a pattern
See [Regular Expressions](RegularExpressions.md).

### VALUE
`VALUE` is a number, string, function, or parenthesized expression.

For JSON null values use `NULL_VALUE`

If `VALUE` is a parenthesized Boolean combination of comparisons, then the comparison operator is applied to each element
* `jsonPayload.cat = ("longhair" OR "shorthair")`
* `jsonPayload.animal : ("nice" AND "pet")`

### Missing Fields
Queries for fields that are not a part of a log entry's payload or labels are missing.
* If the field is defined directly in the log entry type, the field is defaulted.
* Other fields are undefined and error the query.

To test for a missing or defaulted field use the `:*` comparison.
* `operation.id:*`

## Object and Array Types
* Scalar fields hold a single value.
* Objects store a collection of named values.
* Arrays store a list of values of the same type.

Comparisons performed on an array field is equivalent to `OR`ing the comparison against each of the array's elements.

```json
{
  "shoeSize": [ 8.5, 9, 6 ]
}
```
`jsonPayload.shoeSize < 7` is equivalent to `8.5 < 7 OR 9 < 7 OR 6 < 7`

## Comments
Comments start with two dashes `--` and continue to the end of the line.

## Log Entry Field Path Identifiers
* httpRequest
  * cacheFillBytes
  * cacheHit
  * cacheLookup
  * cacheValidatedWithOriginServer
  * latency
  * protocol
  * referer
  * remoteIp
  * requestMethod
  * requestSize
  * requestUrl
  * responseSize
  * serverIp
  * status
  * userAgent
* insertId
* jsonPayload
  * {variable}
* labels
  * {variable}
* logName
* metadata
  * systemLabels
  * userLabels
* operation
  * id
  * producer
  * first
  * last
* protoPayload
  * @type
  * {variable}
* receiveTimestamp
* resource
  * type
  * labels
* severity
* sourceLocation
  * file
  * line
  * function
* spanId
* textPayload
* timestamp
* trace



