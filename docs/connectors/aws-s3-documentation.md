---
id: aws-s3-documentation
title: AWS S3 (version v2.*.*)
sidebar_label: AWS S3
---

## abort_multipart_upload

Abort a multipart upload: http://docs.amazonwebservices.com/AmazonS3/latest/API/mpUploadAbort.html
To verify that all parts have been removed, so you don't get charged for the part storage, you should call the List Parts operation and ensure the parts list is empty.

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### Key (required)

**Type:** string

#### uploadId

Upload ID identifying the multipart upload whose part is being uploaded.

**Type:** string

</details>

## complete_multipart_upload

Complete a multipart upload by assembling previously uploaded parts: http://docs.amazonwebservices.com/AmazonS3/latest/API/mpUploadComplete.html

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### Key (required)

**Type:** string

#### uploadId

Upload ID identifying the multipart upload whose part is being uploaded.

**Type:** string

#### x-amz-request-payer

**Type:** string

</details>

## copy_object

Create a copy of an object that is already stored in Amazon S3: http://docs.amazonwebservices.com/AmazonS3/latest/API/RESTObjectCOPY.html

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### Key (required)

**Type:** string

#### Cache-Control

Specifies caching behavior along the request/reply chain.

**Type:** string

#### Content-Disposition

Specifies presentational information for the object.

**Type:** string

#### Content-Encoding

Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field.

**Type:** string

#### Content-Language

The language the content is in.

**Type:** string

#### Content-Type

A standard MIME type describing the format of the object data.

**Type:** string

#### Expires

The date and time at which the object is no longer cacheable.

**Type:** string

#### x-amz-acl

The canned ACL to apply to the object.

**Type:** string

#### x-amz-copy-source

The name of the source bucket and key name of the source object, separated by a slash (/). Must be URL-encoded.

**Type:** string

#### x-amz-copy-source-if-match

Copies the object if its entity tag (ETag) matches the specified tag.

**Type:** string

#### x-amz-copy-source-if-modified-since

Copies the object if it has been modified since the specified time.

**Type:** string

#### x-amz-copy-source-if-none-match

Copies the object if its entity tag (ETag) is different than the specified ETag.

**Type:** string

#### x-amz-copy-source-if-unmodified-since

Copies the object if it hasn't been modified since the specified time.

**Type:** string

#### x-amz-copy-source-server-side-encryption-customer-algorithm

Specifies the algorithm to use when decrypting the source object (e.g., AES256).

**Type:** string

#### x-amz-copy-source-server-side-encryption-customer-key

Specifies the customer-provided encryption key for Amazon S3 to use to decrypt the source object. The encryption key provided in this header must be one that was used when the source object was created.

**Type:** string

#### x-amz-copy-source-server-side-encryption-customer-key-MD5

Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

**Type:** string

#### x-amz-grant-full-control

Gives the grantee READ, READ_ACP, and WRITE_ACP permissions on the object.

**Type:** string

#### x-amz-grant-read

Allows grantee to read the object data and its metadata.

**Type:** string

#### x-amz-grant-read-acp

Allows grantee to read the object ACL.

**Type:** string

#### x-amz-grant-write-acp

Allows grantee to write the ACL for the applicable object.

**Type:** string

#### x-amz-meta-

A map of metadata to store with the object in S3.

**Type:** string

#### x-amz-metadata-directive

Specifies whether the metadata is copied from the source object or replaced with metadata provided in the request.

**Type:** string

#### x-amz-object-lock-legal-hold

Specifies whether you want to apply a Legal Hold to the copied object.

**Type:** string

#### x-amz-object-lock-mode

The Object Lock mode that you want to apply to the copied object.

**Type:** string

#### x-amz-object-lock-retain-until-date

The date and time when you want the copied object's Object Lock to expire.

**Type:** string

#### x-amz-request-payer

**Type:** string

#### x-amz-server-side-encryption

The Server-side encryption algorithm used when storing this object in S3 (e.g., AES256, aws:kms).

**Type:** string

#### x-amz-server-side-encryption-aws-kms-key-id

Specifies the AWS KMS key ID to use for object encryption. All GET and PUT requests for an object protected by AWS KMS will fail if not made via SSL or using SigV4. Documentation on configuring any of the officially supported AWS SDKs and CLI can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingAWSSDK.html#specify-signature-version

**Type:** string

#### x-amz-server-side-encryption-customer-algorithm

Specifies the algorithm to use to when encrypting the object (e.g., AES256).

**Type:** string

#### x-amz-server-side-encryption-customer-key

Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value is used to store the object and then it is discarded; Amazon does not store the encryption key. The key must be appropriate for use with the algorithm specified in the x-amz-server-side​-encryption​-customer-algorithm header.

**Type:** string

#### x-amz-server-side-encryption-customer-key-MD5

Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

**Type:** string

#### x-amz-storage-class

The type of storage to use for the object. Defaults to 'STANDARD'.

**Type:** string

#### x-amz-tagging

The tag-set for the object destination object this value must be used in conjunction with the TaggingDirective. The tag-set must be encoded as URL Query parameters

**Type:** string

#### x-amz-tagging-directive

Specifies whether the object tag-set are copied from the source object or replaced with tag-set provided in the request.

**Type:** string

#### x-amz-website-redirect-location

If the bucket is configured as a website, redirects requests for this object to another object in the same bucket or to an external URL. Amazon S3 stores the value of this header in the object metadata.

**Type:** string

</details>

## copy_part_in_multipart

Upload a part by copying data from an existing object as data source: http://docs.amazonwebservices.com/AmazonS3/latest/API/mpUploadUploadPartCopy.html

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### Key (required)

**Type:** string

#### partNumber

Part number of part being uploaded. This is a positive integer between 1 and 10,000.

**Type:** integer

#### uploadId

Upload ID identifying the multipart upload whose part is being uploaded.

**Type:** string

#### x-amz-copy-source

The name of the source bucket and key name of the source object, separated by a slash (/). Must be URL-encoded.

**Type:** string

#### x-amz-copy-source-if-match

Copies the object if its entity tag (ETag) matches the specified tag.

**Type:** string

#### x-amz-copy-source-if-modified-since

Copies the object if it has been modified since the specified time.

**Type:** string

#### x-amz-copy-source-if-none-match

Copies the object if its entity tag (ETag) is different than the specified ETag.

**Type:** string

#### x-amz-copy-source-if-unmodified-since

Copies the object if it hasn't been modified since the specified time.

**Type:** string

#### x-amz-copy-source-range

The range of bytes to copy from the source object. The range value must use the form bytes=first-last, where the first and last are the zero-based byte offsets to copy. For example, bytes=0-9 indicates that you want to copy the first ten bytes of the source. You can copy a range only if the source object is greater than 5 GB.

**Type:** string

#### x-amz-copy-source-server-side-encryption-customer-algorithm

Specifies the algorithm to use when decrypting the source object (e.g., AES256).

**Type:** string

#### x-amz-copy-source-server-side-encryption-customer-key

Specifies the customer-provided encryption key for Amazon S3 to use to decrypt the source object. The encryption key provided in this header must be one that was used when the source object was created.

**Type:** string

#### x-amz-copy-source-server-side-encryption-customer-key-MD5

Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

**Type:** string

#### x-amz-request-payer

**Type:** string

#### x-amz-server-side-encryption-customer-algorithm

Specifies the algorithm to use to when encrypting the object (e.g., AES256).

**Type:** string

#### x-amz-server-side-encryption-customer-key

Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value is used to store the object and then it is discarded; Amazon does not store the encryption key. The key must be appropriate for use with the algorithm specified in the x-amz-server-side​-encryption​-customer-algorithm header.

**Type:** string

#### x-amz-server-side-encryption-customer-key-MD5

Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

**Type:** string

</details>

## create_bucket

Creates a new bucket. http://docs.amazonwebservices.com/AmazonS3/latest/API/RESTBucketPUT.html

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### x-amz-acl

The canned ACL to apply to the bucket.

**Type:** string

#### x-amz-bucket-object-lock-enabled

Specifies whether you want S3 Object Lock to be enabled for the new bucket.

**Type:** string

#### x-amz-grant-full-control

Gives the grantee READ, READ_ACP, and WRITE_ACP permissions on the object.

**Type:** string

#### x-amz-grant-read

Allows grantee to read the object data and its metadata.

**Type:** string

#### x-amz-grant-read-acp

Allows grantee to read the object ACL.

**Type:** string

#### x-amz-grant-write

Allows grantee to create, overwrite, and delete any object in the bucket.

**Type:** string

#### x-amz-grant-write-acp

Allows grantee to write the ACL for the applicable object.

**Type:** string

</details>

## create_bucket_in_region



<details><summary>Parameters</summary>

#### Bucket (required)

Name of bucket to create.

**Type:** STRING

#### Region (required)

Region in which to create bucket. This must match the region specified in the connector configuration.

**Type:** STRING

#### x-amz-acl

The canned ACL to apply to the object.

**Type:** STRING

#### x-amz-bucket-object-lock-enabled

Specifies whether you want S3 Object Lock to be enabled for the new bucket.

**Type:** STRING

#### x-amz-grant-full-control

Gives the grantee READ, READ_ACP, and WRITE_ACP permissions on the object.

**Type:** STRING

#### x-amz-grant-read

Allows grantee to read the object data and its metadata.

**Type:** STRING

#### x-amz-grant-read-acp

Allows grantee to read the object ACL.

**Type:** STRING

#### x-amz-grant-write

Allows grantee to create, overwrite, and delete any object in the bucket.

**Type:** STRING

#### x-amz-grant-write-acp

Allows grantee to write the ACL for the applicable object.

**Type:** STRING

</details>

## delete_bucket



*This operation has no parameters*

## delete_object

Remove the null version (if there is one) of an object and insert a delete marker, which becomes the latest version of the object: http://docs.amazonwebservices.com/AmazonS3/latest/API/RESTObjectDELETE.html 
If there isn't a null version, Amazon S3 does not remove any objects.

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### Key (required)

**Type:** string

#### versionId

VersionId used to reference a specific version of the object.

**Type:** string

#### x-amz-bypass-governance-retention

Indicates whether S3 Object Lock should bypass Governance-mode restrictions to process this operation.

**Type:** string

#### x-amz-mfa

The concatenation of the authentication device's serial number, a space, and the value that is displayed on your authentication device.

**Type:** string

#### x-amz-request-payer

**Type:** string

</details>

## get_object

Retrieve objects from Amazon S3: http://docs.amazonwebservices.com/AmazonS3/latest/API/RESTObjectGET.html

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### Key (required)

**Type:** string

#### If-Match

Return the object only if its entity tag (ETag) is the same as the one specified, otherwise return a 412 (precondition failed).

**Type:** string

#### If-Modified-Since

Return the object only if it has been modified since the specified time, otherwise return a 304 (not modified).

**Type:** string

#### If-None-Match

Return the object only if its entity tag (ETag) is different from the one specified, otherwise return a 304 (not modified).

**Type:** string

#### If-Unmodified-Since

Return the object only if it has not been modified since the specified time, otherwise return a 412 (precondition failed).

**Type:** string

#### Range

Downloads the specified range bytes of an object. For more information about the HTTP Range header, go to http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.35.

**Type:** string

#### response-cache-control

Sets the Cache-Control header of the response.

**Type:** string

#### response-content-disposition

Sets the Content-Disposition header of the response

**Type:** string

#### response-content-encoding

Sets the Content-Encoding header of the response.

**Type:** string

#### response-content-language

Sets the Content-Language header of the response.

**Type:** string

#### response-content-type

Sets the Content-Type header of the response.

**Type:** string

#### response-expires

Sets the Expires header of the response.

**Type:** string

#### versionId

VersionId used to reference a specific version of the object.

**Type:** string

</details>

## list_buckets



*This operation has no parameters*

## list_objects

Returns some or all (up to 1000) of the objects in a bucket. You can use the request parameters as selection criteria to return a subset of the objects in a bucket. http://docs.amazonwebservices.com/AmazonS3/latest/API/RESTBucketGET.html

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### delimiter

A delimiter is a character you use to group keys.

**Type:** string

#### encoding-type

**Type:** string

#### prefix

Limits the response to keys that begin with the specified prefix.

**Type:** string

#### x-amz-request-payer

**Type:** string

</details>

## list_parts_for_multipart_upload

List the parts that have been uploaded for a specific multipart upload: http://docs.amazonwebservices.com/AmazonS3/latest/API/mpUploadListParts.html

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### Key (required)

**Type:** string

#### max-parts

Sets the maximum number of parts to return.

**Type:** string

#### part-number-marker

Specifies the part after which listing should begin. Only parts with higher part numbers will be listed.

**Type:** string

#### uploadId

Upload ID identifying the multipart upload whose part is being uploaded.

**Type:** string

</details>

## put_object

Add an object to a bucket: http://docs.amazonwebservices.com/AmazonS3/latest/API/RESTObjectPUT.html

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### Key (required)

**Type:** string

#### Cache-Control

Specifies caching behavior along the request/reply chain.

**Type:** string

#### Content-Disposition

Specifies presentational information for the object.

**Type:** string

#### Content-Encoding

Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field.

**Type:** string

#### Content-Language

The language the content is in.

**Type:** string

#### Content-Length

Size of the body in bytes. This parameter is useful when the size of the body cannot be determined automatically.

**Type:** string

#### Content-MD5

The base64-encoded 128-bit MD5 digest of the part data.

**Type:** string

#### Content-Type

A standard MIME type describing the format of the object data.

**Type:** string

#### Expires

The date and time at which the object is no longer cacheable.

**Type:** string

#### x-amz-acl

The canned ACL to apply to the object.

**Type:** string

#### x-amz-grant-full-control

Gives the grantee READ, READ_ACP, and WRITE_ACP permissions on the object.

**Type:** string

#### x-amz-grant-read

Allows grantee to read the object data and its metadata.

**Type:** string

#### x-amz-grant-read-acp

Allows grantee to read the object ACL.

**Type:** string

#### x-amz-grant-write-acp

Allows grantee to write the ACL for the applicable object.

**Type:** string

#### x-amz-meta-

A map of metadata to store with the object in S3.

**Type:** string

#### x-amz-object-lock-legal-hold

Specifies whether you want to apply a Legal Hold to the copied object.

**Type:** string

#### x-amz-object-lock-mode

The Object Lock mode that you want to apply to the copied object.

**Type:** string

#### x-amz-object-lock-retain-until-date

The date and time when you want the copied object's Object Lock to expire.

**Type:** string

#### x-amz-request-payer

**Type:** string

#### x-amz-server-side-encryption

The Server-side encryption algorithm used when storing this object in S3 (e.g., AES256, aws:kms).

**Type:** string

#### x-amz-server-side-encryption-aws-kms-key-id

Specifies the AWS KMS key ID to use for object encryption. All GET and PUT requests for an object protected by AWS KMS will fail if not made via SSL or using SigV4. Documentation on configuring any of the officially supported AWS SDKs and CLI can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingAWSSDK.html#specify-signature-version

**Type:** string

#### x-amz-server-side-encryption-customer-algorithm

Specifies the algorithm to use to when encrypting the object (e.g., AES256).

**Type:** string

#### x-amz-server-side-encryption-customer-key

Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value is used to store the object and then it is discarded; Amazon does not store the encryption key. The key must be appropriate for use with the algorithm specified in the x-amz-server-side​-encryption​-customer-algorithm header.

**Type:** string

#### x-amz-server-side-encryption-customer-key-MD5

Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

**Type:** string

#### x-amz-storage-class

The type of storage to use for the object. Defaults to 'STANDARD'.

**Type:** string

#### x-amz-tagging

The tag-set for the object destination object this value must be used in conjunction with the TaggingDirective. The tag-set must be encoded as URL Query parameters

**Type:** string

#### x-amz-website-redirect-location

If the bucket is configured as a website, redirects requests for this object to another object in the same bucket or to an external URL. Amazon S3 stores the value of this header in the object metadata.

**Type:** string

</details>

## upload_part_in_multipart

Upload a part in a multipart upload: http://docs.amazonwebservices.com/AmazonS3/latest/API/mpUploadUploadPart.html
Note: After you initiate multipart upload and upload one or more parts, you must either complete or abort multipart upload in order to stop getting charged for storage of the uploaded parts. Only after you either complete or abort multipart upload, Amazon S3 frees up the parts storage and stops charging you for the parts storage.

<details><summary>Parameters</summary>

#### Bucket (required)

**Type:** string

#### Key (required)

**Type:** string

#### Content-Length

Size of the body in bytes. This parameter is useful when the size of the body cannot be determined automatically.

**Type:** string

#### Content-MD5

The base64-encoded 128-bit MD5 digest of the part data.

**Type:** string

#### partNumber

Part number of part being uploaded. This is a positive integer between 1 and 10,000.

**Type:** integer

#### uploadId

Upload ID identifying the multipart upload whose part is being uploaded.

**Type:** string

#### x-amz-request-payer

**Type:** string

#### x-amz-server-side-encryption-customer-algorithm

Specifies the algorithm to use to when encrypting the object (e.g., AES256).

**Type:** string

#### x-amz-server-side-encryption-customer-key

Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value is used to store the object and then it is discarded; Amazon does not store the encryption key. The key must be appropriate for use with the algorithm specified in the x-amz-server-side​-encryption​-customer-algorithm header.

**Type:** string

#### x-amz-server-side-encryption-customer-key-MD5

Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

**Type:** string

</details>

