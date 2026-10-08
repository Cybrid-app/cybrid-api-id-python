# AccessToken


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | Identifier of the access token. | 
**application_client_id** | **str** | Client ID of the application the token was issued to. | 
**application_guid** | **str, none_type** | Guid of the organization, bank or customer the issuing application belongs to. | 
**resource_owner_type** | **str, none_type** | Type of the resource owner: user, or application for customer tokens owned by a bank application. | 
**resource_owner_guid** | **str, none_type** | Guid of the user, or of the bank that owns the owning application. | 
**created_at** | **datetime** | ISO8601 datetime the token was created at. | 
**expires_in** | **int, none_type** | Lifetime of the token in seconds. Null for tokens that do not expire. | 
**revoked_at** | **datetime, none_type** | ISO8601 datetime the token was revoked at. Null for tokens that are not revoked. | 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


