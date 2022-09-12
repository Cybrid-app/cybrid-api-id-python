# cybrid_api_id.BankApplicationsIdpApi

All URIs are relative to *https://id.demo.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_bank_application**](BankApplicationsIdpApi.md#create_bank_application) | **POST** /api/bank_applications | Create bank application
[**list_bank_applications**](BankApplicationsIdpApi.md#list_bank_applications) | **GET** /api/bank_applications | List bank applications


# **create_bank_application**
> ApplicationWithSecret create_bank_application(post_bank_application)

Create bank application

Creates a bank OAuth2 application.  Required scope: **banks:write**

### Example

* Bearer (JWT) Authentication (BearerAuth):
* OAuth Authentication (oauth2):

```python
import time
import cybrid_api_id
from cybrid_api_id.api import bank_applications_idp_api
from cybrid_api_id.model.post_bank_application import PostBankApplication
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
    api_instance = bank_applications_idp_api.BankApplicationsIdpApi(api_client)
    post_bank_application = PostBankApplication(
        name="name_example",
        bank_guid="bank_guid_example",
    ) # PostBankApplication | 

    # example passing only required values which don't have defaults set
    try:
        # Create bank application
        api_response = api_instance.create_bank_application(post_bank_application)
        pprint(api_response)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling BankApplicationsIdpApi->create_bank_application: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **post_bank_application** | [**PostBankApplication**](PostBankApplication.md)|  |

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
**201** | bank application created |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_bank_applications**
> ApplicationList list_bank_applications()

List bank applications

Retrieve a list of bank OAuth2 applications.  Required scope: **banks:read**

### Example

* Bearer (JWT) Authentication (BearerAuth):
* OAuth Authentication (oauth2):

```python
import time
import cybrid_api_id
from cybrid_api_id.api import bank_applications_idp_api
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
    api_instance = bank_applications_idp_api.BankApplicationsIdpApi(api_client)
    page = ListRequestPage(0) # int | The page index to retrieve. (optional)
    per_page = ListRequestPerPage(1) # int | The number of entities per page to return. (optional)
    bank_guid = "bank_guid_example" # str | Bank guid to list applications for. (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # List bank applications
        api_response = api_instance.list_bank_applications(page=page, per_page=per_page, bank_guid=bank_guid)
        pprint(api_response)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling BankApplicationsIdpApi->list_bank_applications: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **int**| The page index to retrieve. | [optional]
 **per_page** | **int**| The number of entities per page to return. | [optional]
 **bank_guid** | **str**| Bank guid to list applications for. | [optional]

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
**200** | list bank applications |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

