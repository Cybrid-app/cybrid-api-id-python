# Authorization


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | Identifier of the user authorization. | 
**user_guid** | **str** | Guid of the user. | 
**resource_type** | **str** | Type of the resource the authorization is on. | 
**resource_guid** | **str** | Guid of the resource the authorization is on. | 
**portal** | **str, none_type** | Portal the authorization routes to. Null for authorizations that have no portal. | 
**allowed_scopes** | **[str]** | The list of scopes that the user is allowed to request. | 
**disabled_at** | **datetime, none_type** | ISO8601 datetime the authorization was disabled at. Null for enabled authorizations. | 
**created_at** | **datetime** | ISO8601 datetime the record was created at. | 
**updated_at** | **datetime** | ISO8601 datetime the record was last updated at. | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


