# cybrid_api_id.OrganizationApplicationsIdpApi

All URIs are relative to *https://id.demo.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_organization_application**](OrganizationApplicationsIdpApi.md#create_organization_application) | **POST** /api/organization_applications | Create organization application
[**list_organization_applications**](OrganizationApplicationsIdpApi.md#list_organization_applications) | **GET** /api/organization_applications | List organization applications


# **create_organization_application**
> ApplicationWithSecret create_organization_application(post_organization_application)

Create organization application

Create an organization OAuth2 application.  Required scope: **organizations:write**

### Example

* Bearer (JWT) Authentication (BearerAuth):
* OAuth Authentication (oauth2):

```python
import time
import cybrid_api_id
from cybrid_api_id.api import organization_applications_idp_api
from cybrid_api_id.model.post_organization_application import PostOrganizationApplication
from cybrid_api_id.model.application_with_secret import ApplicationWithSecret
from pprint import pprint
# Defining the host is optional and defaults to https://id.demo.cybrid.app
# See configuration.py for a list of all supported configuration parameters.
configuration = cybrid_api_id.Configuration(
    host = "https://id.demo.cybrid.app"
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
    host = "https://id.demo.cybrid.app"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with cybrid_api_id.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = organization_applications_idp_api.OrganizationApplicationsIdpApi(api_client)
    post_organization_application = PostOrganizationApplication(
        name="name_example",
    ) # PostOrganizationApplication | 

    # example passing only required values which don't have defaults set
    try:
        # Create organization application
        api_response = api_instance.create_organization_application(post_organization_application)
        pprint(api_response)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling OrganizationApplicationsIdpApi->create_organization_application: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **post_organization_application** | [**PostOrganizationApplication**](PostOrganizationApplication.md)|  |

### Return type

[**ApplicationWithSecret**](ApplicationWithSecret.md)

### Authorization

[BearerAuth](../README.md#BearerAuth), [oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | organization application created |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_organization_applications**
> ApplicationList list_organization_applications()

List organization applications

Retrieve a list of organization OAuth2 applications.  Required scope: **organizations:read**

### Example

* Bearer (JWT) Authentication (BearerAuth):
* OAuth Authentication (oauth2):

```python
import time
import cybrid_api_id
from cybrid_api_id.api import organization_applications_idp_api
from cybrid_api_id.model.application_list import ApplicationList
from pprint import pprint
# Defining the host is optional and defaults to https://id.demo.cybrid.app
# See configuration.py for a list of all supported configuration parameters.
configuration = cybrid_api_id.Configuration(
    host = "https://id.demo.cybrid.app"
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
    host = "https://id.demo.cybrid.app"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with cybrid_api_id.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = organization_applications_idp_api.OrganizationApplicationsIdpApi(api_client)
    page = ListRequestPage(0) # int | The page index to retrieve. (optional) if omitted the server will use the default value of 0
    per_page = ListRequestPerPage(10) # int | The number of entities per page to return. (optional) if omitted the server will use the default value of 10

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # List organization applications
        api_response = api_instance.list_organization_applications(page=page, per_page=per_page)
        pprint(api_response)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling OrganizationApplicationsIdpApi->list_organization_applications: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **int**| The page index to retrieve. | [optional] if omitted the server will use the default value of 0
 **per_page** | **int**| The number of entities per page to return. | [optional] if omitted the server will use the default value of 10

### Return type

[**ApplicationList**](ApplicationList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth), [oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | list organization applications (per_page parameter set) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

