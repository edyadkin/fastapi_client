# client.StoreApi

All URIs are relative to *https://petstore.swagger.io/v2*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_order**](StoreApi.md#delete_order) | **DELETE** /store/order/{orderId} | Delete purchase order by ID
[**get_inventory**](StoreApi.md#get_inventory) | **GET** /store/inventory | Returns pet inventories by status
[**get_order_by_id**](StoreApi.md#get_order_by_id) | **GET** /store/order/{orderId} | Find purchase order by ID
[**place_order**](StoreApi.md#place_order) | **POST** /store/order | Place an order for a pet


# **delete_order**
> delete_order(order_id)

Delete purchase order by ID

For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors

### Example

```python
from __future__ import print_function
import time
import client
from client.rest import ApiException
from pprint import pprint

# Create an instance of the API class
api_instance = client.StoreApi()
order_id = 56 # int | ID of the order that needs to be deleted

try:
    # Delete purchase order by ID
    api_instance.delete_order(order_id)
except ApiException as e:
    print("Exception when calling StoreApi->delete_order: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **order_id** | **int**| ID of the order that needs to be deleted | 

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**400** | Invalid ID supplied |  -  |
**404** | Order not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_inventory**
> dict(str, int) get_inventory()

Returns pet inventories by status

Returns a map of status codes to quantities

### Example

* Api Key Authentication (api_key):
```python
from __future__ import print_function
import time
import client
from client.rest import ApiException
from pprint import pprint
configuration = client.Configuration()
# Configure API key authorization: api_key
configuration.api_key['api_key'] = 'YOUR_API_KEY'
# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['api_key'] = 'Bearer'

# Defining host is optional and default to https://petstore.swagger.io/v2
configuration.host = "https://petstore.swagger.io/v2"
# Create an instance of the API class
api_instance = client.StoreApi(client.AsyncApiClient(configuration))

try:
    # Returns pet inventories by status
    api_response = api_instance.get_inventory()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StoreApi->get_inventory: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

**dict(str, int)**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_order_by_id**
> Order get_order_by_id(order_id)

Find purchase order by ID

For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions

### Example

```python
from __future__ import print_function
import time
import client
from client.rest import ApiException
from pprint import pprint

# Create an instance of the API class
api_instance = client.StoreApi()
order_id = 56 # int | ID of pet that needs to be fetched

try:
    # Find purchase order by ID
    api_response = api_instance.get_order_by_id(order_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StoreApi->get_order_by_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **order_id** | **int**| ID of pet that needs to be fetched | 

### Return type

[**Order**](Order.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/xml

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**400** | Invalid ID supplied |  -  |
**404** | Order not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **place_order**
> Order place_order(body)

Place an order for a pet

### Example

```python
from __future__ import print_function
import time
import client
from client.rest import ApiException
from pprint import pprint

# Create an instance of the API class
api_instance = client.StoreApi()
body = client.Order() # Order | order placed for purchasing the pet

try:
    # Place an order for a pet
    api_response = api_instance.place_order(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StoreApi->place_order: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**Order**](Order.md)| order placed for purchasing the pet | 

### Return type

[**Order**](Order.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/xml

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**400** | Invalid Order |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

