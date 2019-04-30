---
id: aws-kinesis-firehose-documentation
title: AWS Kinesis Firehose (version v1.*.*)
sidebar_label: AWS Kinesis Firehose
---

## create_delivery_stream

Creates a Kinesis Data Firehose delivery stream. https://docs.aws.amazon.com/firehose/latest/APIReference/API_CreateDeliveryStream.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream. This name must be unique per AWS account in the same AWS Region. If the delivery streams are in different accounts or different Regions, you can have multiple delivery streams with the same name.

**Type:** STRING

#### DeliveryStreamType

The delivery stream type. This parameter can be one of the following values: DirectPut: Provider applications access the delivery stream directly. KinesisStreamAsSource: The delivery stream uses a Kinesis data stream as a source.

**Type:** STRING

#### ElasticsearchDestinationConfiguration

The destination in Amazon ES. You can specify only one destination.

**Type:** OBJECT

#### ExtendedS3DestinationConfiguration

The destination in Amazon S3. You can specify only one destination.

**Type:** OBJECT

#### KinesisStreamSourceConfiguration

When a Kinesis data stream is used as the source for the delivery stream, a  KinesisStreamSourceConfiguration containing the Kinesis data stream Amazon Resource Name (ARN) and the role ARN for the source stream.

**Type:** OBJECT

#### RedshiftDestinationConfiguration

The destination in Amazon Redshift. You can specify only one destination.

**Type:** OBJECT

#### S3DestinationConfiguration

[Deprecated] The destination in Amazon S3. You can specify only one destination.

**Type:** OBJECT

#### SplunkDestinationConfiguration

The destination in Splunk. You can specify only one destination.

**Type:** OBJECT

#### Tags

A set of tags to assign to the delivery stream. A tag is a key-value pair that you can define and assign to AWS resources. Tags are metadata. For example, you can add friendly names and descriptions or other types of information that can help you distinguish the delivery stream. For more information about tags, see Using Cost Allocation Tags in the AWS Billing and Cost Management User Guide. You can specify up to 50 tags when creating a delivery stream.

**Type:** ARRAY

</details>

## delete_delivery_stream

Deletes a delivery stream and its data. https://docs.aws.amazon.com/firehose/latest/APIReference/API_DeleteDeliveryStream.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream.

**Type:** STRING

</details>

## describe_delivery_stream

Describes the specified delivery stream and gets the status. For example, after your delivery stream is created, call DescribeDeliveryStream to see whether the delivery stream is ACTIVE and therefore ready for data to be sent to it.  https://docs.aws.amazon.com/firehose/latest/APIReference/API_DescribeDeliveryStream.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream.

**Type:** STRING

#### ExclusiveStartDestinationId

The ID of the destination to start returning the destination information.  Kinesis Data Firehose supports one destination per delivery stream.

**Type:** STRING

#### Limit

The limit on the number of destinations to return. You can have one destination per delivery stream.

**Type:** INTEGER

</details>

## list_delivery_streams

Lists your delivery streams in alphabetical order of their names. https://docs.aws.amazon.com/firehose/latest/APIReference/API_ListDeliveryStreams.html

<details><summary>Parameters</summary>

#### DeliveryStreamType

The delivery stream type. This can be one of the following values: DirectPut: Provider applications access the delivery stream directly. KinesisStreamAsSource: The delivery stream uses a Kinesis data stream as a source. This parameter is optional. If this parameter is omitted, delivery streams of all types are returned.

**Type:** STRING

</details>

## list_tags_for_delivery_stream

Lists the tags for the specified delivery stream. This operation has a limit of five transactions per second per account.  https://docs.aws.amazon.com/firehose/latest/APIReference/API_ListTagsForDeliveryStream.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream whose tags you want to list.

**Type:** STRING

</details>

## put_record

Writes a single data record into an Amazon Kinesis Data Firehose delivery stream. To write multiple data records into a delivery stream, use PutRecordBatch. Applications using these operations are referred to as producers.  https://docs.aws.amazon.com/firehose/latest/APIReference/API_PutRecord.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream.

**Type:** STRING

#### Record (required)

The record.

**Type:** OBJECT

</details>

## put_record_batch

Writes multiple data records into a delivery stream in a single call, which can achieve higher throughput per producer than when writing single records. To write single data records into a delivery stream, use PutRecord. Applications using these operations are referred to as producers.  https://docs.aws.amazon.com/firehose/latest/APIReference/API_PutRecordBatch.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream.

**Type:** STRING

#### Records (required)

One or more records.

**Type:** ARRAY

</details>

## start_delivery_stream_encryption

Enables server-side encryption (SSE) for the delivery stream.  https://docs.aws.amazon.com/firehose/latest/APIReference/API_StartDeliveryStreamEncryption.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream for which you want to enable server-side encryption (SSE).

**Type:** STRING

</details>

## stop_delivery_stream_encryption

Disables server-side encryption (SSE) for the delivery stream.  https://docs.aws.amazon.com/firehose/latest/APIReference/API_StopDeliveryStreamEncryption.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream for which you want to disable server-side encryption (SSE).

**Type:** STRING

</details>

## tag_delivery_stream

Adds or updates tags for the specified delivery stream. A tag is a key-value pair that you can define and assign to AWS resources. If you specify a tag that already exists, the tag value is replaced with the value that you specify in the request. Tags are metadata. For example, you can add friendly names and descriptions or other types of information that can help you distinguish the delivery stream. For more information about tags, see Using Cost Allocation Tags in the AWS Billing and Cost Management User Guide.  https://docs.aws.amazon.com/firehose/latest/APIReference/API_TagDeliveryStream.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream to which you want to add the tags.

**Type:** STRING

#### Tags (required)

A set of key-value pairs to use to create the tags.

**Type:** ARRAY

</details>

## untag_delivery_stream

Removes tags from the specified delivery stream. Removed tags are deleted, and you can't recover them after this operation successfully completes.  https://docs.aws.amazon.com/firehose/latest/APIReference/API_UntagDeliveryStream.html

<details><summary>Parameters</summary>

#### DeliveryStreamName (required)

The name of the delivery stream.

**Type:** STRING

#### TagKeys (required)

A list of tag keys. Each corresponding tag is removed from the delivery stream.

**Type:** ARRAY

</details>

## update_destination

Updates the specified destination of the specified delivery stream. https://docs.aws.amazon.com/firehose/latest/APIReference/API_UpdateDestination.html

<details><summary>Parameters</summary>

#### CurrentDeliveryStreamVersionId (required)

Obtain this value from the VersionId result of DeliveryStreamDescription. This value is required, and helps the service perform conditional operations. For example, if there is an interleaving update and this value is null, then the update destination fails. After the update is successful, the VersionId value is updated. The service then performs a merge of the old configuration with the new configuration.

**Type:** STRING

#### DeliveryStreamName (required)

The name of the delivery stream.

**Type:** STRING

#### DestinationId (required)

The ID of the destination.

**Type:** STRING

#### ElasticsearchDestinationUpdate

Describes an update for a destination in Amazon ES.

**Type:** OBJECT

#### ExtendedS3DestinationUpdate

Describes an update for a destination in Amazon S3.

**Type:** OBJECT

#### RedshiftDestinationUpdate

Describes an update for a destination in Amazon Redshift.

**Type:** OBJECT

#### S3DestinationUpdate

[Deprecated] Describes an update for a destination in Amazon S3.

**Type:** OBJECT

#### SplunkDestinationUpdate

Describes an update for a destination in Splunk.

**Type:** OBJECT

</details>

