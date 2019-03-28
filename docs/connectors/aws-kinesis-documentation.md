---
id: aws-kinesis-documentation
title: AWS Kinesis (version v1.*.*)
sidebar_label: AWS Kinesis
---

## add_tags_to_stream

Adds or updates tags for the specified Kinesis data stream. Each time you invoke this operation, you can specify up to 10 tags. If you want to add more than 10 tags to your stream, you can invoke this operation multiple times. In total, each stream can have up to 50 tags.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_AddTagsToStream.html

<details><summary>Parameters</summary>

#### StreamName (required)

The name of the stream.

**Type:** STRING

#### Tags (required)

A set of up to 10 key-value pairs to use to create the tags.

**Type:** OBJECT

</details>

## create_stream

Creates a Kinesis data stream. A stream captures and transports data records that are continuously emitted from different data sources or producers. Scale-out within a stream is explicitly supported by means of shards, which are uniquely identified groups of data records in a stream.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_CreateStream.html

<details><summary>Parameters</summary>

#### ShardCount (required)

The number of shards that the stream will use. The throughput of the stream is a function of the number of shards; more shards are required for greater provisioned throughput. DefaultShardLimit;

**Type:** INTEGER

#### StreamName (required)

A name to identify the stream. The stream name is scoped to the AWS account used by the application that creates the stream. It is also scoped by AWS Region. That is, two streams in two different AWS accounts can have the same name. Two streams in the same AWS account but in two different Regions can also have the same name.

**Type:** STRING

</details>

## decrease_stream_retention_period

Decreases the Kinesis data stream's retention period, which is the length of time data records are accessible after they are added to the stream. The minimum value of a stream's retention period is 24 hours.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_DecreaseStreamRetentionPeriod.html

<details><summary>Parameters</summary>

#### RetentionPeriodHours (required)

The new retention period of the stream, in hours. Must be less than the current retention period.

**Type:** INTEGER

#### StreamName (required)

The name of the stream to modify.

**Type:** STRING

</details>

## delete_stream

Deletes a Kinesis data stream and all its shards and data. You must shut down any applications that are operating on the stream before you delete the stream. If an application attempts to operate on a deleted stream, it receives the exception ResourceNotFoundException.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_DeleteStream.html

<details><summary>Parameters</summary>

#### StreamName (required)

The name of the stream to delete.

**Type:** STRING

#### EnforceConsumerDeletion

If this parameter is unset (null) or if you set it to false, and the stream has registered consumers, the call to DeleteStream fails with a ResourceInUseException.

**Type:** BOOLEAN

</details>

## deregister_stream_consumer

To deregister a consumer, provide its ARN. Alternatively, you can provide the ARN of the data stream and the name you gave the consumer when you registered it. You may also provide all three parameters, as long as they don't conflict with each other. If you don't know the name or ARN of the consumer that you want to deregister, you can use the ListStreamConsumers operation to get a list of the descriptions of all the consumers that are currently registered with a given data stream. The description of a consumer contains its name and ARN.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_DeregisterStreamConsumer.html

<details><summary>Parameters</summary>

#### ConsumerARN

The ARN returned by Kinesis Data Streams when you registered the consumer. If you don't know the ARN of the consumer that you want to deregister, you can use the ListStreamConsumers operation to get a list of the descriptions of all the consumers that are currently registered with a given data stream. The description of a consumer contains its ARN.

**Type:** STRING

#### ConsumerName

The name that you gave to the consumer.

**Type:** STRING

#### StreamARN

The ARN of the Kinesis data stream that the consumer is registered with. For more information, see Amazon Resource Names (ARNs) and AWS Service Namespaces.

**Type:** STRING

</details>

## describe_limits



*This operation has no parameters*

## describe_stream

Describes the specified Kinesis data stream. https://docs.aws.amazon.com/kinesis/latest/APIReference/API_DescribeStream.html

<details><summary>Parameters</summary>

#### StreamName (required)

The name of the stream to describe.

**Type:** STRING

#### ExclusiveStartShardId

The shard ID of the shard to start with.

**Type:** STRING

#### Limit

The maximum number of shards to return in a single call. The default value is 100. If you specify a value greater than 100, at most 100 shards are returned.

**Type:** INTEGER

</details>

## describe_stream_consumer

To get the description of a registered consumer, provide the ARN of the consumer. Alternatively, you can provide the ARN of the data stream and the name you gave the consumer when you registered it. You may also provide all three parameters, as long as they don't conflict with each other. If you don't know the name or ARN of the consumer that you want to describe, you can use the ListStreamConsumers operation to get a list of the descriptions of all the consumers that are currently registered with a given data stream.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_DescribeStreamConsumer.html

<details><summary>Parameters</summary>

#### ConsumerARN

The ARN returned by Kinesis Data Streams when you registered the consumer.

**Type:** STRING

#### ConsumerName

The name that you gave to the consumer.

**Type:** STRING

#### StreamARN

The ARN of the Kinesis data stream that the consumer is registered with. For more information, see Amazon Resource Names (ARNs) and AWS Service Namespaces.

**Type:** STRING

</details>

## describe_stream_summary

Provides a summarized description of the specified Kinesis data stream without the shard list.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_DescribeStreamSummary.html

<details><summary>Parameters</summary>

#### StreamName (required)

The name of the stream to describe.

**Type:** STRING

</details>

## disable_enhanced_monitoring

Disables enhanced monitoring. https://docs.aws.amazon.com/kinesis/latest/APIReference/API_DisableEnhancedMonitoring.html

<details><summary>Parameters</summary>

#### ShardLevelMetrics (required)

List of shard-level metrics to disable. The following are the valid shard-level metrics. The value "ALL" disables every metric. IncomingBytes IncomingRecords OutgoingBytes OutgoingRecords WriteProvisionedThroughputExceeded ReadProvisionedThroughputExceeded IteratorAgeMilliseconds ALL For more information, see Monitoring the Amazon Kinesis Data Streams Service with Amazon CloudWatch in the Amazon Kinesis Data Streams Developer Guide.

**Type:** ARRAY

#### StreamName (required)

The name of the Kinesis data stream for which to disable enhanced monitoring.

**Type:** STRING

</details>

## enable_enhanced_monitoring

Enables enhanced Kinesis data stream monitoring for shard-level metrics. https://docs.aws.amazon.com/kinesis/latest/APIReference/API_EnableEnhancedMonitoring.html

<details><summary>Parameters</summary>

#### ShardLevelMetrics (required)

List of shard-level metrics to enable. The following are the valid shard-level metrics. The value "ALL" enables every metric. IncomingBytes IncomingRecords OutgoingBytes OutgoingRecords WriteProvisionedThroughputExceeded ReadProvisionedThroughputExceeded IteratorAgeMilliseconds ALL For more information, see Monitoring the Amazon Kinesis Data Streams Service with Amazon CloudWatch in the Amazon Kinesis Data Streams Developer Guide.

**Type:** ARRAY

#### StreamName (required)

The name of the stream for which to enable enhanced monitoring.

**Type:** STRING

</details>

## get_records

Gets data records from a Kinesis data stream's shard. https://docs.aws.amazon.com/kinesis/latest/APIReference/API_GetRecords.html

<details><summary>Parameters</summary>

#### ShardIterator (required)

The position in the shard from which you want to start sequentially reading data records. A shard iterator specifies this position using the sequence number of a data record in the shard.

**Type:** STRING

#### Limit

The maximum number of records to return. Specify a value of up to 10,000. If you specify a value that is greater than 10,000, GetRecords throws InvalidArgumentException. The default value is 10,000.

**Type:** INTEGER

</details>

## get_shard_iterator

Gets an Amazon Kinesis shard iterator. A shard iterator expires 5 minutes after it is returned to the requester.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_GetShardIterator.html

<details><summary>Parameters</summary>

#### ShardId (required)

The shard ID of the Kinesis Data Streams shard to get the iterator for.

**Type:** STRING

#### ShardIteratorType (required)

Determines how the shard iterator is used to start reading data records from the shard. The following are the valid Amazon Kinesis shard iterator types: AT_SEQUENCE_NUMBER - Start reading from the position denoted by a specific sequence number, provided in the value StartingSequenceNumber. AFTER_SEQUENCE_NUMBER - Start reading right after the position denoted by a specific sequence number, provided in the value StartingSequenceNumber. AT_TIMESTAMP - Start reading from the position denoted by a specific time stamp, provided in the value Timestamp. TRIM_HORIZON - Start reading at the last untrimmed record in the shard in the system, which is the oldest data record in the shard. LATEST - Start reading just after the most recent record in the shard, so that you always read the most recent data in the shard.

**Type:** STRING

#### StreamName (required)

The name of the Amazon Kinesis data stream.

**Type:** STRING

#### StartingSequenceNumber

The sequence number of the data record in the shard from which to start reading. Used with shard iterator type AT_SEQUENCE_NUMBER and AFTER_SEQUENCE_NUMBER.

**Type:** STRING

#### Timestamp

The time stamp of the data record from which to start reading. Used with shard iterator type AT_TIMESTAMP. A time stamp is the Unix epoch date with precision in milliseconds. For example, 2016-04-04T19:58:46.480-00:00 or 1459799926.480. If a record with this exact time stamp does not exist, the iterator returned is for the next (later) record. If the time stamp is older than the current trim horizon, the iterator returned is for the oldest untrimmed data record (TRIM_HORIZON).

**Type:** OBJECT

</details>

## increase_stream_retention_period

Increases the Kinesis data stream's retention period, which is the length of time data records are accessible after they are added to the stream. The maximum value of a stream's retention period is 168 hours (7 days).  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_IncreaseStreamRetentionPeriod.html

<details><summary>Parameters</summary>

#### RetentionPeriodHours (required)

The new retention period of the stream, in hours. Must be more than the current retention period.

**Type:** INTEGER

#### StreamName (required)

The name of the stream to modify.

**Type:** STRING

</details>

## list_shards

Lists the shards in a stream and provides information about each shard. This operation has a limit of 100 transactions per second per data stream.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_ListShards.html

<details><summary>Parameters</summary>

#### ExclusiveStartShardId

Specify this parameter to indicate that you want to list the shards starting with the shard whose ID immediately follows ExclusiveStartShardId. If you don't specify this parameter, the default behavior is for ListShards to list the shards starting with the first one in the stream. You cannot specify this parameter if you specify NextToken.

**Type:** STRING

#### StreamCreationTimestamp

Specify this input parameter to distinguish data streams that have the same name. For example, if you create a data stream and then delete it, and you later create another data stream with the same name, you can use this input parameter to specify which of the two streams you want to list the shards for. You cannot specify this parameter if you specify the NextToken parameter.

**Type:** OBJECT

#### StreamName

The name of the data stream whose shards you want to list.  You cannot specify this parameter if you specify the NextToken parameter.

**Type:** STRING

</details>

## list_stream_consumers

Lists the consumers registered to receive data from a stream using enhanced fan-out, and provides information about each consumer.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_ListStreamConsumers.html

<details><summary>Parameters</summary>

#### StreamARN (required)

The ARN of the Kinesis data stream for which you want to list the registered consumers. For more information, see Amazon Resource Names (ARNs) and AWS Service Namespaces.

**Type:** STRING

#### StreamCreationTimestamp

Specify this input parameter to distinguish data streams that have the same name. For example, if you create a data stream and then delete it, and you later create another data stream with the same name, you can use this input parameter to specify which of the two streams you want to list the consumers for.  You can't specify this parameter if you specify the NextToken parameter.

**Type:** OBJECT

</details>

## list_streams



*This operation has no parameters*

## list_tags_for_stream

Lists the tags for the specified Kinesis data stream. This operation has a limit of five transactions per second per account.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_ListTagsForStream.html

<details><summary>Parameters</summary>

#### StreamName (required)

The name of the stream.

**Type:** STRING

</details>

## merge_shards

Merges two adjacent shards in a Kinesis data stream and combines them into a single shard to reduce the stream's capacity to ingest and transport data. Two shards are considered adjacent if the union of the hash key ranges for the two shards form a contiguous set with no gaps. For example, if you have two shards, one with a hash key range of 276...381 and the other with a hash key range of 382...454, then you could merge these two shards into a single shard that would have a hash key range of 276...454. After the merge, the single child shard receives data for all hash key values covered by the two parent shards.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_MergeShards.html

<details><summary>Parameters</summary>

#### AdjacentShardToMerge (required)

The shard ID of the adjacent shard for the merge.

**Type:** STRING

#### ShardToMerge (required)

The shard ID of the shard to combine with the adjacent shard for the merge.

**Type:** STRING

#### StreamName (required)

The name of the stream for the merge.

**Type:** STRING

</details>

## put_record

Writes a single data record into an Amazon Kinesis data stream. Call PutRecord to send data into the stream for real-time ingestion and subsequent processing, one record at a time. Each shard can support writes up to 1,000 records per second, up to a maximum data write total of 1 MiB per second.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_PutRecord.html

<details><summary>Parameters</summary>

#### Data (required)

The data blob to put into the record, which is base64-encoded when the blob is serialized. When the data blob (the payload before base64-encoding) is added to the partition key size, the total size must not exceed the maximum record size (1 MiB).

**Type:** STRING

#### PartitionKey (required)

Determines which shard in the stream the data record is assigned to. Partition keys are Unicode strings with a maximum length limit of 256 characters for each key. Amazon Kinesis Data Streams uses the partition key as input to a hash function that maps the partition key and associated data to a specific shard. Specifically, an MD5 hash function is used to map partition keys to 128-bit integer values and to map associated data records to shards. As a result of this hashing mechanism, all data records with the same partition key map to the same shard within the stream.

**Type:** STRING

#### StreamName (required)

The name of the stream to put the data record into.

**Type:** STRING

#### ExplicitHashKey

The hash value used to explicitly determine the shard the data record is assigned to by overriding the partition key hash.

**Type:** STRING

#### SequenceNumberForOrdering

Guarantees strictly increasing sequence numbers, for puts from the same client and to the same partition key. Usage: set the SequenceNumberForOrdering of record n to the sequence number of record n-1 (as returned in the result when putting record n-1). If this parameter is not set, records are coarsely ordered based on arrival time.

**Type:** STRING

</details>

## put_records

Writes multiple data records into a Kinesis data stream in a single call (also referred to as a PutRecords request). Use this operation to send data into the stream for data ingestion and processing.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_PutRecords.html

<details><summary>Parameters</summary>

#### Records (required)

The records associated with the request.

**Type:** ARRAY

#### StreamName (required)

The stream name associated with the request.

**Type:** STRING

</details>

## register_stream_consumer

Registers a consumer with a Kinesis data stream. When you use this operation, the consumer you register can then call SubscribeToShard to receive data from the stream using enhanced fan-out, at a rate of up to 2 MiB per second for every shard you subscribe to. This rate is unaffected by the total number of consumers that read from the same stream.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_RegisterStreamConsumer.html

<details><summary>Parameters</summary>

#### ConsumerName (required)

For a given Kinesis data stream, each consumer must have a unique name. However, consumer names don't have to be unique across data streams.

**Type:** STRING

#### StreamARN (required)

The ARN of the Kinesis data stream that you want to register the consumer with.  For more info, see Amazon Resource Names (ARNs) and AWS Service Namespaces.

**Type:** STRING

</details>

## remove_tags_from_stream

Removes tags from the specified Kinesis data stream. Removed tags are deleted and cannot be recovered after this operation successfully completes.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_RemoveTagsFromStream.html

<details><summary>Parameters</summary>

#### StreamName (required)

The name of the stream.

**Type:** STRING

#### TagKeys (required)

A list of tag keys. Each corresponding tag is removed from the stream.

**Type:** ARRAY

</details>

## split_shard

Splits a shard into two new shards in the Kinesis data stream, to increase the stream's capacity to ingest and transport data. SplitShard is called when there is a need to increase the overall capacity of a stream because of an expected increase in the volume of data records being ingested.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_SplitShard.html

<details><summary>Parameters</summary>

#### NewStartingHashKey (required)

A hash key value for the starting hash key of one of the child shards created by the split. The hash key range for a given shard constitutes a set of ordered contiguous positive integers. The value for NewStartingHashKey must be in the range of hash keys being mapped into the shard. The NewStartingHashKey hash key value and all higher hash key values in hash key range are distributed to one of the child shards. All the lower hash key values in the range are distributed to the other child shard.

**Type:** STRING

#### ShardToSplit (required)

The shard ID of the shard to split.

**Type:** STRING

#### StreamName (required)

The name of the stream for the shard split.

**Type:** STRING

</details>

## start_stream_encryption

Enables or updates server-side encryption using an AWS KMS key for a specified stream.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_StartStreamEncryption.html

<details><summary>Parameters</summary>

#### EncryptionType (required)

The encryption type to use. The only valid value is KMS.

**Type:** STRING

#### KeyId (required)

The GUID for the customer-managed AWS KMS key to use for encryption. This value can be a globally unique identifier, a fully specified Amazon Resource Name (ARN) to either an alias or a key, or an alias name prefixed by "alias/".You can also use a master key owned by Kinesis Data Streams by specifying the alias aws/kinesis. Key ARN example: arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 Alias ARN example: arn:aws:kms:us-east-1:123456789012:alias/MyAliasName Globally unique key ID example: 12345678-1234-1234-1234-123456789012 Alias name example: alias/MyAliasName Master key owned by Kinesis Data Streams: alias/aws/kinesis

**Type:** STRING

#### StreamName (required)

The name of the stream for which to start encrypting records.

**Type:** STRING

</details>

## stop_stream_encryption

Disables server-side encryption for a specified stream.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_StopStreamEncryption.html

<details><summary>Parameters</summary>

#### EncryptionType (required)

The encryption type. The only valid value is KMS.

**Type:** STRING

#### KeyId (required)

The GUID for the customer-managed AWS KMS key to use for encryption. This value can be a globally unique identifier, a fully specified Amazon Resource Name (ARN) to either an alias or a key, or an alias name prefixed by "alias/".You can also use a master key owned by Kinesis Data Streams by specifying the alias aws/kinesis. Key ARN example: arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 Alias ARN example: arn:aws:kms:us-east-1:123456789012:alias/MyAliasName Globally unique key ID example: 12345678-1234-1234-1234-123456789012 Alias name example: alias/MyAliasName Master key owned by Kinesis Data Streams: alias/aws/kinesis

**Type:** STRING

#### StreamName (required)

The name of the stream on which to stop encrypting records.

**Type:** STRING

</details>

## subscribe_to_shard

This operation establishes an HTTP/2 connection between the consumer you specify in the ConsumerARN parameter and the shard you specify in the ShardId parameter. After the connection is successfully established, Kinesis Data Streams pushes records from the shard to the consumer over this connection. Before you call this operation, call RegisterStreamConsumer to register the consumer with Kinesis Data Streams.  https://docs.aws.amazon.com/kinesis/latest/APIReference/API_SubscribeToShard.html

<details><summary>Parameters</summary>

#### ConsumerARN (required)

For this parameter, use the value you obtained when you called RegisterStreamConsumer.

**Type:** STRING

#### ShardId (required)

The ID of the shard you want to subscribe to. To see a list of all the shards for a given stream, use ListShards.

**Type:** STRING

</details>

## update_shard_count

Updates the shard count of the specified stream to the specified number of shards. https://docs.aws.amazon.com/kinesis/latest/APIReference/API_UpdateShardCount.html

<details><summary>Parameters</summary>

#### ScalingType (required)

The scaling type. Uniform scaling creates shards of equal size.

**Type:** STRING

#### StreamName (required)

The name of the stream.

**Type:** STRING

#### TargetShardCount (required)

The new number of shards.

**Type:** INTEGER

</details>

