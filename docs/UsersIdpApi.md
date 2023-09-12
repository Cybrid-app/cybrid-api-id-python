# cybrid_api_id.UsersIdpApi

All URIs are relative to *https://id.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_user**](UsersIdpApi.md#create_user) | **POST** /api/users | Create user
[**list_user**](UsersIdpApi.md#list_user) | **GET** /api/users | List users


# **create_user**
> User create_user(post_user)

Create user

Creates a user.  

### Example

* Bearer (JWT) Authentication (BearerAuth):
* OAuth Authentication (oauth2):

```python
import time
import cybrid_api_id
from cybrid_api_id.api import users_idp_api
from cybrid_api_id.model.user import User
from cybrid_api_id.model.post_user import PostUser
from pprint import pprint
# Defining the host is optional and defaults to https://id.sandbox.cybrid.app
# See configuration.py for a list of all supported configuration parameters.
configuration = cybrid_api_id.Configuration(
    host = "https://id.sandbox.cybrid.app"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): BearerAuth
configuration = cybrid_api_id.Configuration(
    access_token = 'YOUR_BEARER_TOKEN'
)

# Configure OAuth2 access token for authorization: oauth2
configuration = cybrid_api_id.Configuration(
    host = "https://id.sandbox.cybrid.app"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with cybrid_api_id.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = users_idp_api.UsersIdpApi(api_client)
    post_user = PostUser(
        email="email_example",
    ) # PostUser | 

    # example passing only required values which don't have defaults set
    try:
        # Create user
        api_response = api_instance.create_user(post_user)
        pprint(api_response)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling UsersIdpApi->create_user: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **post_user** | [**PostUser**](PostUser.md)|  |

### Return type

[**User**](User.md)

### Authorization

[BearerAuth](../README.md#BearerAuth), [oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | User created |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_user**
> UserList list_user()

List users

Retrieve a list users.  Required scope: **users:read**

### Example

* Bearer (JWT) Authentication (BearerAuth):
* OAuth Authentication (oauth2):

```python
import time
import cybrid_api_id
from cybrid_api_id.api import users_idp_api
from cybrid_api_id.model.user_list import UserList
from pprint import pprint
# Defining the host is optional and defaults to https://id.sandbox.cybrid.app
# See configuration.py for a list of all supported configuration parameters.
configuration = cybrid_api_id.Configuration(
    host = "https://id.sandbox.cybrid.app"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): BearerAuth
configuration = cybrid_api_id.Configuration(
    access_token = 'YOUR_BEARER_TOKEN'
)

# Configure OAuth2 access token for authorization: oauth2
configuration = cybrid_api_id.Configuration(
    host = "https://id.sandbox.cybrid.app"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with cybrid_api_id.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = users_idp_api.UsersIdpApi(api_client)
    page = ListRequestPage(0) # int | The page index to retrieve. (optional)
    per_page = ListRequestPerPage(1) # int | The number of entities per page to return. (optional)
    guid = "guid_example" # str | Comma separated guids to list users for. (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # List users
        api_response = api_instance.list_user(page=page, per_page=per_page, guid=guid)
        pprint(api_response)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling UsersIdpApi->list_user: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **int**| The page index to retrieve. | [optional]
 **per_page** | **int**| The number of entities per page to return. | [optional]
 **guid** | **str**| Comma separated guids to list users for. | [optional]

### Return type

[**UserList**](UserList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth), [oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | list users |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

