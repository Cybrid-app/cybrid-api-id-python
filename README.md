# cybrid-api-id-python
# Welcome

Welcome to the Cybrid platform; enabling turnkey crypto banking services!

In these documents, you will find information on the operations provided by our platform, as well as details on how our REST API operates more generally.

Our complete set of APIs allows you to manage all your resources: your Organization, your banks and your identities. The complete set of APIs can be found on the following pages:

| API                                                            | Description                  |
|----------------------------------------------------------------|------------------------------|
| [Organization API](https://organization.demo.cybrid.app/api/schema/swagger-ui) | APIs to manage organizations |
| [Bank API](https://bank.demo.cybrid.app/api/schema/swagger-ui)                 | APIs to manage banks         |
| [Identities API](https://id.demo.cybrid.app/api/schema/swagger-ui)                     | APIs to manage identities    |

When you're ready, [request access](https://www.cybrid.xyz/access) to your Dashboard to view and administer your Organization. Once you've logged in, you can begin creating Banks, either for sandbox or production usage, and start enabling your customers to leverage DeFi and web3 with confidence.

If you have any questions, please contact [Support](mailto:support@cybrid.app) at any time so that we can help.

## Authentication

The Cybrid Platform uses OAuth 2.0 Bearer Tokens to authenticate requests to the platform. Credentials to create Organization and Bank tokens can be generated via your Dashboard ([request access](https://www.cybrid.xyz/access)).

An Organization Token applies broadly to the whole Organization and all of its Banks, whereas, a Bank Token is specific to an individual Bank.

Both Organization and Bank tokens can be created using the OAuth Client Credential Grant flow. Each Organization and Bank has its own unique Client ID and Secret that allows for machine-to-machine authentication.

**Never share your Client ID or Secret publicly or in your source code repository**

Your Client ID and Secret can be exchanged for a time-limited Bearer Token by interacting with the Cybrid Identity Provider or through interacting with the **Authorize** button in this document:

```
curl -X POST https://id.demo.cybrid.app/oauth/token -d '{
    \"grant_type\": \"client_credentials\",
    \"client_id\": \"<Your Client ID>\",
    \"client_secret\": \"<Your Secret>\",
    \"scope\": \"<Your requested scopes -- space separated>\"
  }' -H \"Content-Type: application/json\"
```

## Scopes

The Cybrid platform supports the use of scopes to control the level of access a token is limited to. Scopes do not grant access to resources; instead, they provide limits, in support of the least privilege principal.

The following scopes are available on the platform and can be requested when generating either an Organization or a Bank token. Generally speaking, the _Read_ scope is required to read and list resources, the _Write_ scope is required to update a resource and the _Execute_ scope is required to create a resource.

| Resource      | Read scope         | Write scope          | Execute scope     | Token Type         |
|---------------|--------------------|----------------------|-------------------|--------------------|
| Organizations | organizations:read | organizations:write  |                   | Organization/ Bank |
| Banks         | banks:read         | banks:write          | banks:execute     | Organization/ Bank |
| Customers     | customers:read     | customers:write      | customers:execute | Bank               |
| Assets        | prices:read        |                      |                   | Bank               |
| Accounts      | accounts:read      |                      | accounts:execute  | Bank               |
| Prices        | prices:read        |                      |                   | Bank               |
| Symbols       | prices:read        |                      |                   | Bank               |
| Quotes        | quotes:read        |                      | quotes:execute    | Bank               |
| Trades        | trades:read        |                      | trades:execute    | Bank               |

## Organizations

An Organization is meant to model the organization partnering with Cybrid to use our platform.

An Organization does not directly interact with customers. Instead, an Organization has one or more banks, which encompass the financial service offerings of the platform.

## Banks

A Bank is owned by an Organization and can be thought of as an environment or container for Customers and product offerings. An example of a Bank would be your customer facing banking website, or an internal staging environment for testing and integration.

An Organization can have multiple banks, in sandbox or production environments. A sandbox Bank will be backed by stubbed data and process flows. For instance, identity record and funding source processes will be simulated rather than performed.

## Customers

Customers represent your banking users on the platform. At present, we offer support for Individuals as Customers.

Customers must be verified in our system before they can play any part on the platform. See the Identity Records section for more details on how a customer can be verified.

Customers must also have an account to be able to transact. See the Accounts APIs for more details on setting up accounts for the customer.


This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: v0.14.8
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >=3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
import cybrid_api_id
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import cybrid_api_id
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import cybrid_api_id
from pprint import pprint
from cybrid_api_id.api import bank_applications_idp_api
from cybrid_api_id.model.application_list import ApplicationList
from cybrid_api_id.model.application_with_secret import ApplicationWithSecret
from cybrid_api_id.model.list_request_page import ListRequestPage
from cybrid_api_id.model.list_request_per_page import ListRequestPerPage
from cybrid_api_id.model.post_bank_application import PostBankApplication
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

    try:
        # Create bank application
        api_response = api_instance.create_bank_application(post_bank_application)
        pprint(api_response)
    except cybrid_api_id.ApiException as e:
        print("Exception when calling BankApplicationsIdpApi->create_bank_application: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *https://id.demo.cybrid.app*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*BankApplicationsIdpApi* | [**create_bank_application**](docs/BankApplicationsIdpApi.md#create_bank_application) | **POST** /api/bank_applications | Create bank application
*BankApplicationsIdpApi* | [**list_bank_applications**](docs/BankApplicationsIdpApi.md#list_bank_applications) | **GET** /api/bank_applications | List bank applications
*OrganizationApplicationsIdpApi* | [**create_organization_application**](docs/OrganizationApplicationsIdpApi.md#create_organization_application) | **POST** /api/organization_applications | Create organization application
*OrganizationApplicationsIdpApi* | [**list_organization_applications**](docs/OrganizationApplicationsIdpApi.md#list_organization_applications) | **GET** /api/organization_applications | List organization applications


## Documentation For Models

 - [Application](docs/Application.md)
 - [ApplicationList](docs/ApplicationList.md)
 - [ApplicationWithSecret](docs/ApplicationWithSecret.md)
 - [ApplicationWithSecretAllOf](docs/ApplicationWithSecretAllOf.md)
 - [ListRequestPage](docs/ListRequestPage.md)
 - [ListRequestPerPage](docs/ListRequestPerPage.md)
 - [PostBankApplication](docs/PostBankApplication.md)
 - [PostOrganizationApplication](docs/PostOrganizationApplication.md)


## Documentation For Authorization


## BearerAuth

- **Type**: Bearer authentication (JWT)


## oauth2

- **Type**: OAuth
- **Flow**: application
- **Authorization URL**: 
- **Scopes**: 
 - **banks:write**: banks write
 - **banks:read**: banks read
 - **organizations:write**: organizations write
 - **organizations:read**: organizations read


## Author

support@cybrid.app


## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in cybrid_api_id.apis and cybrid_api_id.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from cybrid_api_id.api.default_api import DefaultApi`
- `from cybrid_api_id.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import cybrid_api_id
from cybrid_api_id.apis import *
from cybrid_api_id.models import *
```

