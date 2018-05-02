---

copyright:
  years: 2017
lastupdated: "2017-10-03"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 供应商容器
`SoftLayer_Container_Network_CdnMarketplace_Vendor` 集合包含供应商 API 利用的属性。 


`SoftLayer_Container_Network_CdnMarketplace_Vendor` 类  
* `vendorName`：当前 IBM Cloud CDN 提供者的名称。  
* `featureSummary`：供应商功能的简要摘要。  
* `features`：供应商支持的功能列表。  
* `status`：指示供应商是否为通过 IBM Cloud 提供的可用选项。


通过调用 `listVendors` API 显示可用供应商及其功能的列表：

```php
$vendors = $client->listVendors();
``` 
上面的 API 调用生成的输出类似以下内容：
```php
SoftLayer_Container_Network_CdnMarketplace_Vendor Object
(
    [vendorName] => akamai
    [featureSummary] => Performance, Reliability and Scale
    [features] => Web Delivery, Content Caching, Content Purge, HTTP/HTTPS Support
    [status] => ACTIVE
)

```