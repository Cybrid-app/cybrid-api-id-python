# cybrid_api_id.CustomerTokensIdpApi

All URIs are relative to *https://id.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_customer_token**](CustomerTokensIdpApi.md#create_customer_token) | **POST** /api/customer_tokens | Create customer access token


# **create_customer_token**
> CustomerToken create_customer_token(post_customer_token)

Create customer access token

Creates a customer JWT access token.  Required scopes: **customers:write** and **customers:read**

### Example

* Bearer (JWT) Authentication (BearerAuth):
* OAuth Authentication (oauth2):

```python
import time
import cybrid_api_id
from cybrid_api_id.api import customer_tokens_idp_api
from cybrid_api_id.model.customer_token import CustomerToken
from cybrid_api_id.model.post_customer_token import PostCustomerToken
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
    api_instance = customer_tokens_idp_api.CustomerTokensIdpApi(api_client)
    post_customer_token = PostCustomerToken(
        customer_guid="customer_guid_example",
        scopes=[
            "customers:read",
        ],
    ) # PostCustomerToken | 

    # example passing only required values which don't have defaults set
    try:
        # Create customer access token
        api_response = api_instance.create_customer_token(post_customer_token)
        pprint(api_response)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling CustomerTokensIdpApi->create_customer_token: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **post_customer_token** | [**PostCustomerToken**](PostCustomerToken.md)|  |

### Return type

[**CustomerToken**](CustomerToken.md)

### Authorization

[BearerAuth](../README.md#BearerAuth), [oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Customer token created |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

