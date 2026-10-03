# PostOrganizationApplication

Request body for organization application creation.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | Name for the organization application. | 
**expires_at** | **datetime** | ISO8601 datetime the application expires at; must be in the future. | 
**ip_allowlist** | **[str]** | List of public IPv4 addresses or CIDR ranges to allowlist for API access. | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


