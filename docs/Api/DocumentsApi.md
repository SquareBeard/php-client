# PDFGeneratorAPI\DocumentsApi

All URIs are relative to https://us1.pdfgeneratorapi.com/api/v3.

Method | HTTP request | Description
------------- | ------------- | -------------
[**mergeTemplate()**](DocumentsApi.md#mergeTemplate) | **POST** /templates/{templateId}/output | Generate document
[**mergeTemplates()**](DocumentsApi.md#mergeTemplates) | **POST** /templates/output | Generate document (multiple templates)


## `mergeTemplate()`

```php
mergeTemplate($template_id, $data, $name, $format, $output): \PDFGeneratorAPI\Model\InlineResponse2004
```

Generate document

Merges template with data and returns base64 encoded document or a public URL to a document. You can send json encoded data in request body or a public URL to your json file as the data parameter. NB! When the public URL option is used, the document is stored for 30 days and automatically deleted.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: JSONWebTokenAuth
$config = PDFGeneratorAPI\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PDFGeneratorAPI\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$template_id = 19375; // int | Template unique identifier
$data = new \PDFGeneratorAPI\Model\Data(); // \PDFGeneratorAPI\Model\Data | Data used to generate the PDF. This can be JSON encoded string or a public URL to your JSON file.
$name = My document; // string | Document name, returned in the meta data.
$format = pdf; // string | Document format. The zip option will return a ZIP file with PDF files.
$output = base64; // string | Response format. With the url option, the document is stored for 30 days and automatically deleted.

try {
    $result = $apiInstance->mergeTemplate($template_id, $data, $name, $format, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->mergeTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **template_id** | **int**| Template unique identifier |
 **data** | [**\PDFGeneratorAPI\Model\Data**](../Model/Data.md)| Data used to generate the PDF. This can be JSON encoded string or a public URL to your JSON file. |
 **name** | **string**| Document name, returned in the meta data. | [optional]
 **format** | **string**| Document format. The zip option will return a ZIP file with PDF files. | [optional] [default to &#39;pdf&#39;]
 **output** | **string**| Response format. With the url option, the document is stored for 30 days and automatically deleted. | [optional] [default to &#39;base64&#39;]

### Return type

[**\PDFGeneratorAPI\Model\InlineResponse2004**](../Model/InlineResponse2004.md)

### Authorization

[JSONWebTokenAuth](../../README.md#JSONWebTokenAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `mergeTemplates()`

```php
mergeTemplates($request_body, $name, $format, $output): \PDFGeneratorAPI\Model\InlineResponse2004
```

Generate document (multiple templates)

Allows to merge multiple templated with data and returns base64 encoded document or public URL to a document. NB! When the public URL option is used, the document is stored for 30 days and automatically deleted.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: JSONWebTokenAuth
$config = PDFGeneratorAPI\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PDFGeneratorAPI\Api\DocumentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$request_body = array(new \stdClass); // object[] | Data used to specify templates and data objects which are used to merge the template
$name = My document; // string | Document name, returned in the meta data.
$format = pdf; // string | Document format. The zip option will return a ZIP file with PDF files.
$output = base64; // string | Response format. With the url option, the document is stored for 30 days and automatically deleted.

try {
    $result = $apiInstance->mergeTemplates($request_body, $name, $format, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DocumentsApi->mergeTemplates: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **request_body** | [**object[]**](../Model/object.md)| Data used to specify templates and data objects which are used to merge the template |
 **name** | **string**| Document name, returned in the meta data. | [optional]
 **format** | **string**| Document format. The zip option will return a ZIP file with PDF files. | [optional] [default to &#39;pdf&#39;]
 **output** | **string**| Response format. With the url option, the document is stored for 30 days and automatically deleted. | [optional] [default to &#39;base64&#39;]

### Return type

[**\PDFGeneratorAPI\Model\InlineResponse2004**](../Model/InlineResponse2004.md)

### Authorization

[JSONWebTokenAuth](../../README.md#JSONWebTokenAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
