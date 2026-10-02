# PostCustomerToken

Request body for customer token creation.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**customer_guid** | **str** | Customer guid the access token is being generated for. | 
**scopes** | **[str]** | List of the scopes requested for the access token. | 
**inherit_ip_allowlist** | **bool, none_type** | When true, the customer token inherits the IP allowlist of the bank API key that creates it. | [optional]  if omitted the server will use the default value of True
**ip_allowlist** | **[str], none_type** | List of public IPv4 addresses or CIDR ranges the customer token is restricted to. Combined with the inherited allowlist when inherit_ip_allowlist is true. | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


