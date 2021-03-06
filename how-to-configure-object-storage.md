---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-05-21"

keywords: object storage, bucket, configuration, details, updating

subcollection: CDN

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:term: .term}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:external: target="_blank" .external}
{:generic: data-hd-programlang="generic"}
{:download: .download}
{:DomainName: data-hd-keyref="DomainName"}

# Configuring IBM Cloud Object Storage for CDN
{: #configure-ibm-cloud-object-storage-for-cdn}

To make use of objects stored in {{site.data.keyword.cloud}} Object Storage, you must set the value of the "acl" property (that is, the access control list) for each object in your bucket for "public-read" access.

To install any necessary clients or tools, refer to [For developers of IBM Cloud Object Storage](/docs/cloud-object-storage/basics?topic=cloud-object-storage-gs-dev). This guide assumes you have installed the official AWS command line interface, which is compatible with {{site.data.keyword.cloud_notm}} Object Storage S3 API.

The example code below shows how to set "public-read" access for all the objects in your bucket, using the command line interface.

```
$ export ENDPOINT="YOUR_ENDPOINT"
$ export BUCKET="YOUR_BUCKET"
$ KEYS=( "$(aws --endpoint-url "$ENDPOINT" s3api list-objects --no-paginate --query 'Contents[].{key: Key}' --output text --bucket "$BUCKET")" )
$ for KEY in "${KEYS[@]}"
  > do
  >   aws --endpoint-url "$ENDPOINT" s3api put-object-acl --bucket "$BUCKET" --key "$KEY" --acl "public-read"
  > done
```

For more information on how to use {{site.data.keyword.cloud_notm}} Object Storage please refer to [Accelerate delivery of static files using a CDN](/docs/tutorials?topic=solution-tutorials-static-files-cdn).
