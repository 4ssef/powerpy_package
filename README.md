
# pwerpy

This Python package, makes communication between Microsoft Power BI REST API and a client easier.

*Read this in other languages: [Español](https://github.com/4ssef/powerpy_package/blob/master/README_es.md).*

## Requirements
* Python >= 3.7 and < 4
## Installation
```bash
pip install pwerpy
```
## Before Using:
It's mandatory to have these in order to successfully use `pwerpy`, otherwise, you won't be able to make any request to Power BI REST API:
* Your Azure Active Directory (AD) Client ID
* Your Azure AD Username
* Your Azure AD Password
## Usage/Examples
Once you have your client ID and both workspace username and password, you're ready to go!

To get your Azure Active Directory tenant ID (tenant id)
```python
from pwerpy import powerpy

domain_name = 'YOUR_DOMAIN_NAME'

tenant_id = powerpy.get_tenant_id(domain_name)
```

To get your authentication access token, in order to request your Bearer authorization token
```python
from pwerpy import powerpy

tenant_id = 'YOUR_TENANT_ID'
client_id = 'YOUR_CLIENT_ID'
user = 'YOUR_WORKSPACE_USERNAME'
pwd = 'YOUR_WORKSPACE_PASSWORD'

access_token = powerpy.get_access_token(tenant_id, client_id, user, pwd)
```

To get your Bearer authorization token
```python
from pwerpy import powerpy

access_token = 'YOUR_ACCESS_TOKEN'

auth = powerpy.get_authorization_token(access_token)
```

To make a GET request
```python
from pwerpy import powerpy

url = 'YOUR_POWER_BI_REST_API_URL'
auth = 'YOUR_BEARER_AUTHORIZATION_TOKEN'

response = powerpy.get(url, auth)
```

To make a POST request
```python
from pwerpy import powerpy

url = 'YOUR_POWER_BI_REST_API_URL'
auth = 'YOUR_BEARER_AUTHORIZATION_TOKEN'

response = powerpy.post(url, auth)
```
These are the essential functions in order to communicate with Power BI REST API successfully.
## Functions
### powerpy
* get_tenant_id()
* get_access_token()
* get_authorization_token()
* get()
* post()
### skills
* get_token_usage()
* get_datasets_in_group()
* get_datasets_names_in_group()
* refresh_dataset_in_group_by_name()
* refresh_dataset_by_id()

## License

Pwerpy is licensed under the [MIT](https://choosealicense.com/licenses/mit/) license.

Copyright © 2022, Fernando Assef (4ssef)

