# cybrid_api_id.ApplicationsIdpApi

All URIs are relative to *https://id.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_bank_application**](ApplicationsIdpApi.md#delete_bank_application) | **DELETE** /api/bank_applications/{client_id} | Delete Application
[**delete_organization_application**](ApplicationsIdpApi.md#delete_organization_application) | **DELETE** /api/organization_applications/{client_id} | Delete Application


# **delete_bank_application**
> delete_bank_application(client_id)

Delete Application

Deletes an application.Required scope: **bank_applications:execute**

### Example

* Bearer (JWT) Authentication (BearerAuth):
* OAuth Authentication (oauth2):

```python
import time
import cybrid_api_id
from cybrid_api_id.api import applications_idp_api
from cybrid_api_id.model.error_response import ErrorResponse
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
    api_instance = applications_idp_api.ApplicationsIdpApi(api_client)
    client_id = "client_id_example" # str | Identifier for the application.

    # example passing only required values which don't have defaults set
    try:
        # Delete Application
        api_instance.delete_bank_application(client_id)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling ApplicationsIdpApi->delete_bank_application: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **client_id** | **str**| Identifier for the application. |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth), [oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Application discarded |  -  |
**403** | Invalid scope |  -  |
**404** | application not found |  -  |
**401** | Unauthorized - Authentication failed,  |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_organization_application**
> delete_organization_application(client_id)

Delete Application

Deletes an application.Required scope: **organization_applications:execute**

### Example

* Bearer (JWT) Authentication (BearerAuth):
* OAuth Authentication (oauth2):

```python
import time
import cybrid_api_id
from cybrid_api_id.api import applications_idp_api
from cybrid_api_id.model.error_response import ErrorResponse
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
    api_instance = applications_idp_api.ApplicationsIdpApi(api_client)
    client_id = "client_id_example" # str | Identifier for the application.

    # example passing only required values which don't have defaults set
    try:
        # Delete Application
        api_instance.delete_organization_application(client_id)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling ApplicationsIdpApi->delete_organization_application: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **client_id** | **str**| Identifier for the application. |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth), [oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Application disacarded |  -  |
**401** | Unauthorized - Authentication failed,  |  -  |
**403** | Invalid scope |  -  |
**404** | application not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

