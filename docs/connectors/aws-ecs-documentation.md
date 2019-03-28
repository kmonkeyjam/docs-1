---
id: aws-ecs-documentation
title: AWS ECS (version v3.*.*)
sidebar_label: AWS ECS
---

## create_cluster

Creates a new Amazon ECS cluster. By default, your account receives a default cluster when you launch your first container instance. However, you can create your own cluster with a unique name with the CreateCluster action.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_CreateCluster.html

<details><summary>Parameters</summary>

#### clusterName

The name of your cluster. If you do not specify a name for your cluster, you create a cluster named default. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. 

**Type:** STRING

#### tags

The metadata that you apply to the cluster to help you categorize and organize them. Each tag consists of a key and an optional value, both of which you define. Tag keys can have a maximum character length of 128 characters, and tag values can have a maximum length of 256 characters. 

**Type:** ARRAY

</details>

## create_service

Runs and maintains a desired number of tasks from a specified task definition. If the number of tasks running in a service drops below desiredCount, Amazon ECS spawns another copy of the task in the specified cluster. To update an existing service, see UpdateService.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_CreateService.html

<details><summary>Parameters</summary>

#### serviceName (required)

The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a Region or across multiple Regions. 

**Type:** STRING

#### taskDefinition (required)

The family and revision (family:revision) or full ARN of the task definition to run in your service. If a revision is not specified, the latest ACTIVE revision is used. 

**Type:** STRING

#### clientToken

Unique, case-sensitive identifier that you provide to ensure the idempotency of the request. Up to 32 ASCII characters are allowed. 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster on which to run your service. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### deploymentConfiguration

Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks. 

**Type:** OBJECT

#### deploymentController

The deployment controller to use for the service. 

**Type:** OBJECT

#### desiredCount

The number of instantiations of the specified task definition to place and keep running on your cluster. 

**Type:** INTEGER

#### enableECSManagedTags

Specifies whether to enable Amazon ECS managed tags for the tasks within the service. For more information, see Tagging Your Amazon ECS Resources in the Amazon Elastic Container Service Developer Guide. 

**Type:** BOOLEAN

#### healthCheckGracePeriodSeconds

The period of time, in seconds, that the Amazon ECS service scheduler should ignore unhealthy Elastic Load Balancing target health checks after a task has first started. This is only valid if your service is configured to use a load balancer. If your service's tasks take a while to start and respond to Elastic Load Balancing health checks, you can specify a health check grace period of up to 2,147,483,647 seconds. During that time, the ECS service scheduler ignores health check status. This grace period can prevent the ECS service scheduler from marking tasks as unhealthy and stopping them before they have time to come up. 

**Type:** INTEGER

#### launchType

The launch type on which to run your service. For more information, see Amazon ECS Launch Types in the Amazon Elastic Container Service Developer Guide. 

**Type:** STRING

#### loadBalancers

A load balancer object representing the load balancer to use with your service. If the service is using the ECS deployment controller, you are limited to one load balancer or target group. If the service is using the CODE_DEPLOY deployment controller, the service is required to use either an Application Load Balancer or Network Load Balancer. When creating an AWS CodeDeploy deployment group, you specify two target groups (referred to as a targetGroupPair). During a deployment, AWS CodeDeploy determines which task set in your service has the status PRIMARY and associates one target group with it, and then associates the other target group with the replacement task set. The load balancer can also have up to two listeners: a required listener for production traffic and an optional listener that allows you perform validation tests with Lambda functions before routing production traffic to it. After you create a service using the ECS deployment controller, the load balancer name or target group ARN, container name, and container port specified in the service definition are immutable. If you are using the CODE_DEPLOY deployment controller, these values can be changed when updating the service. For Classic Load Balancers, this object must contain the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer. When a task from this service is placed on a container instance, the container instance is registered with the load balancer specified here. For Application Load Balancers and Network Load Balancers, this object must contain the load balancer target group ARN, the container name (as it appears in a container definition), and the container port to access from the load balancer. When a task from this service is placed on a container instance, the container instance and port combination is registered as a target in the target group specified here. Services with tasks that use the awsvpc network mode (for example, those with the Fargate launch type) only support Application Load Balancers and Network Load Balancers. Classic Load Balancers are not supported. Also, when you create any target groups for these services, you must choose ip as the target type, not instance, because tasks that use the awsvpc network mode are associated with an elastic network interface, not an Amazon EC2 instance. 

**Type:** ARRAY

#### networkConfiguration

The network configuration for the service. This parameter is required for task definitions that use the awsvpc network mode to receive their own elastic network interface, and it is not supported for other network modes. For more information, see Task Networking in the Amazon Elastic Container Service Developer Guide. 

**Type:** OBJECT

#### placementConstraints

An array of placement constraint objects to use for tasks in your service. You can specify a maximum of 10 constraints per task (this limit includes constraints in the task definition and those specified at runtime).  

**Type:** ARRAY

#### placementStrategy

The placement strategy objects to use for tasks in your service. You can specify a maximum of five strategy rules per service. 

**Type:** ARRAY

#### platformVersion

The platform version on which your tasks in the service are running. A platform version is only specified for tasks using the Fargate launch type. If one is not specified, the LATEST platform version is used by default. For more information, see AWS Fargate Platform Versions in the Amazon Elastic Container Service Developer Guide. 

**Type:** STRING

#### propagateTags

Specifies whether to propagate the tags from the task definition or the service to the tasks in the service. If no value is specified, the tags are not propagated. Tags can only be propagated to the tasks within the service during service creation. To add tags to a task after service creation, use the TagResource API action. 

**Type:** STRING

#### role

The name or full Amazon Resource Name (ARN) of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is only permitted if you are using a load balancer with your service and your task definition does not use the awsvpc network mode. If you specify the role parameter, you must also specify a load balancer object with the loadBalancers parameter. Important If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here. The service-linked role is required if your task definition uses the awsvpc network mode, in which case you should not specify a role here. For more information, see Using Service-Linked Roles for Amazon ECS in the Amazon Elastic Container Service Developer Guide. If your specified role has a path other than /, then you must either specify the full role ARN (this is recommended) or prefix the role name with the path. For example, if a role with the name bar has a path of /foo/ then you would specify /foo/bar as the role name. For more information, see Friendly Names and Paths in the IAM User Guide. 

**Type:** STRING

#### schedulingStrategy

The scheduling strategy to use for the service. For more information, see Services. There are two service scheduler strategies available: REPLICA-The replica scheduling strategy places and maintains the desired number of tasks across your cluster. By default, the service scheduler spreads tasks across Availability Zones. You can use task placement strategies and constraints to customize task placement decisions. This scheduler strategy is required if using the CODE_DEPLOY deployment controller. DAEMON-The daemon scheduling strategy deploys exactly one task on each active container instance that meets all of the task placement constraints that you specify in your cluster. When you are using this strategy, there is no need to specify a desired number of tasks, a task placement strategy, or use Service Auto Scaling policies. Note Tasks using the Fargate launch type or the CODE_DEPLOY deploymenet controller do not support the DAEMON scheduling strategy. 

**Type:** STRING

#### serviceRegistries

The details of the service discovery registries to assign to this service. For more information, see Service Discovery. Note Service discovery is supported for Fargate tasks if you are using platform version v1.1.0 or later. For more information, see AWS Fargate Platform Versions. 

**Type:** ARRAY

#### tags

The metadata that you apply to the service to help you categorize and organize them. Each tag consists of a key and an optional value, both of which you define. When a service is deleted, the tags are deleted as well. Tag keys can have a maximum character length of 128 characters, and tag values can have a maximum length of 256 characters. 

**Type:** ARRAY

</details>

## delete_account_setting

Modifies the ARN and resource ID format of a resource for a specified IAM user, IAM role, or the root user for an account. You can specify whether the new ARN and resource ID format are disabled for new resources that are created.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DeleteAccountSetting.html

<details><summary>Parameters</summary>

#### name (required)

The resource name for which to disable the new format. If serviceLongArnFormat is specified, the ARN for your Amazon ECS services is affected. If taskLongArnFormat is specified, the ARN and resource ID for your Amazon ECS tasks is affected. If containerInstanceLongArnFormat is specified, the ARN and resource ID for your Amazon ECS container instances is affected. 

**Type:** STRING

#### principalArn

The ARN of the principal, which can be an IAM user, IAM role, or the root user. If you specify the root user, it modifies the ARN and resource ID format for all IAM users, IAM roles, and the root user of the account unless an IAM user or role explicitly overrides these settings for themselves. If this field is omitted, the setting are changed only for the authenticated user. 

**Type:** STRING

</details>

## delete_attributes

Deletes one or more custom attributes from an Amazon ECS resource. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DeleteAttributes.html

<details><summary>Parameters</summary>

#### attributes (required)

The attributes to delete from your resource. You can specify up to 10 attributes per request. For custom attributes, specify the attribute name and target ID, but do not specify the value. If you specify the target ID using the short form, you must also specify the target type. 

**Type:** ARRAY

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that contains the resource to delete attributes. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

</details>

## delete_cluster

Deletes the specified cluster. You must deregister all container instances from this cluster before you may delete it. You can list the container instances in a cluster with ListContainerInstances and deregister them with DeregisterContainerInstance.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DeleteCluster.html

<details><summary>Parameters</summary>

#### cluster (required)

The short name or full Amazon Resource Name (ARN) of the cluster to delete. 

**Type:** STRING

</details>

## delete_service

Deletes a specified service within a cluster. You can delete a service if you have no running tasks in it and the desired task count is zero. If the service is actively maintaining tasks, you cannot delete it, and you must update the service to a desired task count of zero. For more information, see UpdateService.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DeleteService.html

<details><summary>Parameters</summary>

#### service (required)

The name of the service to delete. 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the service to delete. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### force

If true, allows you to delete a service even if it has not been scaled down to zero tasks. It is only necessary to use this if the service is using the REPLICA scheduling strategy. 

**Type:** BOOLEAN

</details>

## deregister_container_instance

Deregisters an Amazon ECS container instance from the specified cluster. This instance is no longer available to run tasks.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DeregisterContainerInstance.html

<details><summary>Parameters</summary>

#### containerInstance (required)

The container instance ID or full ARN of the container instance to deregister. The ARN contains the arn:aws:ecs namespace, followed by the Region of the container instance, the AWS account ID of the container instance owner, the container-instance namespace, and then the container instance ID. For example, arn:aws:ecs:region:aws_account_id:container-instance/container_instance_ID . 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instance to deregister. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### force

Forces the deregistration of the container instance. If you have tasks running on the container instance when you deregister it with the force option, these tasks remain running until you terminate the instance or the tasks stop through some other means, but they are orphaned (no longer monitored or accounted for by Amazon ECS). If an orphaned task on your container instance is part of an Amazon ECS service, then the service scheduler starts another copy of that task, on a different container instance if possible.  Any containers in orphaned service tasks that are registered with a Classic Load Balancer or an Application Load Balancer target group are deregistered. They begin connection draining according to the settings on the load balancer or target group. 

**Type:** BOOLEAN

</details>

## deregister_task_definition

Deregisters the specified task definition by family and revision. Upon deregistration, the task definition is marked as INACTIVE. Existing tasks and services that reference an INACTIVE task definition continue to run without disruption. Existing services that reference an INACTIVE task definition can still scale up or down by modifying the service's desired count.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DeregisterTaskDefinition.html

<details><summary>Parameters</summary>

#### taskDefinition (required)

The family and revision (family:revision) or full Amazon Resource Name (ARN) of the task definition to deregister. You must specify a revision. 

**Type:** STRING

</details>

## describe_clusters

Describes one or more of your clusters. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DescribeClusters.html

<details><summary>Parameters</summary>

#### clusters

A list of up to 100 cluster names or full cluster Amazon Resource Name (ARN) entries. If you do not specify a cluster, the default cluster is assumed. 

**Type:** ARRAY

#### include

Additional information about your clusters to be separated by launch type, including: runningEC2TasksCount runningFargateTasksCount pendingEC2TasksCount pendingFargateTasksCount activeEC2ServiceCount activeFargateServiceCount drainingEC2ServiceCount drainingFargateServiceCount 

**Type:** ARRAY

</details>

## describe_container_instances

Describes Amazon Elastic Container Service container instances. Returns metadata about registered and remaining resources on each container instance requested.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DescribeContainerInstances.html

<details><summary>Parameters</summary>

#### containerInstances (required)

A list of up to 100 container instance IDs or full Amazon Resource Name (ARN) entries. 

**Type:** ARRAY

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instances to describe. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### include

Specifies whether you want to see the resource tags for the container instance. If TAGS is specified, the tags are included in the response. If this field is omitted, tags are not included in the response. 

**Type:** ARRAY

</details>

## describe_services

Describes the specified services running in your cluster. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DescribeServices.html

<details><summary>Parameters</summary>

#### services (required)

A list of services to describe. You may specify up to 10 services to describe in a single operation. 

**Type:** ARRAY

#### cluster

The short name or full Amazon Resource Name (ARN)the cluster that hosts the service to describe. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### include

Specifies whether you want to see the resource tags for the service. If TAGS is specified, the tags are included in the response. If this field is omitted, tags are not included in the response. 

**Type:** ARRAY

</details>

## describe_task_definition

Describes a task definition. You can specify a family and revision to find information about a specific task definition, or you can simply specify the family to find the latest ACTIVE revision in that family.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DescribeTaskDefinition.html

<details><summary>Parameters</summary>

#### taskDefinition (required)

The family for the latest ACTIVE revision, family and revision (family:revision) for a specific revision in the family, or full Amazon Resource Name (ARN) of the task definition to describe. 

**Type:** STRING

#### include

Specifies whether to see the resource tags for the task definition. If TAGS is specified, the tags are included in the response. If this field is omitted, tags are not included in the response. 

**Type:** ARRAY

</details>

## describe_tasks

Describes a specified task or tasks. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DescribeTasks.html

<details><summary>Parameters</summary>

#### tasks (required)

A list of up to 100 task IDs or full ARN entries. 

**Type:** ARRAY

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task to describe. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### include

Specifies whether you want to see the resource tags for the task. If TAGS is specified, the tags are included in the response. If this field is omitted, tags are not included in the response. 

**Type:** ARRAY

</details>

## discover_poll_endpoint

 Note This action is only used by the Amazon ECS agent, and it is not intended for use outside of the agent.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DiscoverPollEndpoint.html

<details><summary>Parameters</summary>

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster to which the container instance belongs. 

**Type:** STRING

#### containerInstance

The container instance ID or full ARN of the container instance. The ARN contains the arn:aws:ecs namespace, followed by the Region of the container instance, the AWS account ID of the container instance owner, the container-instance namespace, and then the container instance ID. For example, arn:aws:ecs:region:aws_account_id:container-instance/container_instance_ID . 

**Type:** STRING

</details>

## list_account_settings

Lists the account settings for an Amazon ECS resource for a specified principal. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ListAccountSettings.html

<details><summary>Parameters</summary>

#### effectiveSettings

Specifies whether to return the effective settings. If true, the account settings for the root user or the default setting for the principalArn. If false, the account settings for the principalArn are returned if they are set. Otherwise, no account settings are returned. 

**Type:** BOOLEAN

#### maxResults

The maximum number of account setting results returned by ListAccountSettings in paginated output. When this parameter is used, ListAccountSettings only returns maxResults results in a single page along with a nextToken response element. The remaining results of the initial request can be seen by sending another ListAccountSettings request with the returned nextToken value. This value can be between 1 and 10. If this parameter is not used, then ListAccountSettings returns up to 10 results and a nextToken value if applicable. 

**Type:** INTEGER

#### name

The resource name you want to list the account settings for. 

**Type:** STRING

#### nextToken

The nextToken value returned from a previous paginated ListAccountSettings request where maxResults was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the nextToken value. Note This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes. 

**Type:** STRING

#### principalArn

The ARN of the principal, which can be an IAM user, IAM role, or the root user. If this field is omitted, the account settings are listed only for the authenticated user. 

**Type:** STRING

#### value

The value of the account settings with which to filter results. You must also specify an account setting name to use this parameter. 

**Type:** STRING

</details>

## list_attributes

Lists the attributes for Amazon ECS resources within a specified target type and cluster. When you specify a target type and cluster, ListAttributes returns a list of attribute objects, one for each attribute on each resource. You can filter the list of results to a single attribute name to only return results that have that name. You can also filter the results by attribute name and value, for example, to see which container instances in a cluster are running a Linux AMI (ecs.os-type=linux).  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ListAttributes.html

<details><summary>Parameters</summary>

#### targetType (required)

The type of the target with which to list attributes. 

**Type:** STRING

#### attributeName

The name of the attribute with which to filter the results.  

**Type:** STRING

#### attributeValue

The value of the attribute with which to filter results. You must also specify an attribute name to use this parameter. 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster to list attributes. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### maxResults

The maximum number of cluster results returned by ListAttributes in paginated output. When this parameter is used, ListAttributes only returns maxResults results in a single page along with a nextToken response element. The remaining results of the initial request can be seen by sending another ListAttributes request with the returned nextToken value. This value can be between 1 and 100. If this parameter is not used, then ListAttributes returns up to 100 results and a nextToken value if applicable. 

**Type:** INTEGER

#### nextToken

The nextToken value returned from a previous paginated ListAttributes request where maxResults was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the nextToken value. Note This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes. 

**Type:** STRING

</details>

## list_clusters



*This operation has no parameters*

## list_container_instances

Returns a list of container instances in a specified cluster. You can filter the results of a ListContainerInstances operation with cluster query language statements inside the filter parameter. For more information, see Cluster Query Language in the Amazon Elastic Container Service Developer Guide.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ListContainerInstances.html

<details><summary>Parameters</summary>

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instances to list. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### filter

You can filter the results of a ListContainerInstances operation with cluster query language statements. For more information, see Cluster Query Language in the Amazon Elastic Container Service Developer Guide. 

**Type:** STRING

#### maxResults

The maximum number of container instance results returned by ListContainerInstances in paginated output. When this parameter is used, ListContainerInstances only returns maxResults results in a single page along with a nextToken response element. The remaining results of the initial request can be seen by sending another ListContainerInstances request with the returned nextToken value. This value can be between 1 and 100. If this parameter is not used, then ListContainerInstances returns up to 100 results and a nextToken value if applicable. 

**Type:** INTEGER

#### nextToken

The nextToken value returned from a previous paginated ListContainerInstances request where maxResults was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the nextToken value. Note This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes. 

**Type:** STRING

#### status

Filters the container instances by status. For example, if you specify the DRAINING status, the results include only container instances that have been set to DRAINING using UpdateContainerInstancesState. If you do not specify this parameter, the default is to include container instances set to ACTIVE and DRAINING. 

**Type:** STRING

</details>

## list_services

Lists the services that are running in a specified cluster. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ListServices.html

<details><summary>Parameters</summary>

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the services to list. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### launchType

The launch type for the services to list. 

**Type:** STRING

#### schedulingStrategy

The scheduling strategy for services to list. 

**Type:** STRING

</details>

## list_tags_for_resource

List the tags for an Amazon ECS resource. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ListTagsForResource.html

<details><summary>Parameters</summary>

#### resourceArn (required)

The Amazon Resource Name (ARN) that identifies the resource for which to list the tags. Currently, the supported resources are Amazon ECS tasks, services, task definitions, clusters, and container instances. 

**Type:** STRING

</details>

## list_task_definition_families

Returns a list of task definition families that are registered to your account (which may include task definition families that no longer have any ACTIVE task definition revisions).  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ListTaskDefinitionFamilies.html

<details><summary>Parameters</summary>

#### familyPrefix

The familyPrefix is a string that is used to filter the results of ListTaskDefinitionFamilies. If you specify a familyPrefix, only task definition family names that begin with the familyPrefix string are returned. 

**Type:** STRING

#### maxResults

The maximum number of task definition family results returned by ListTaskDefinitionFamilies in paginated output. When this parameter is used, ListTaskDefinitions only returns maxResults results in a single page along with a nextToken response element. The remaining results of the initial request can be seen by sending another ListTaskDefinitionFamilies request with the returned nextToken value. This value can be between 1 and 100. If this parameter is not used, then ListTaskDefinitionFamilies returns up to 100 results and a nextToken value if applicable. 

**Type:** INTEGER

#### nextToken

The nextToken value returned from a previous paginated ListTaskDefinitionFamilies request where maxResults was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the nextToken value. Note This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes. 

**Type:** STRING

#### status

The task definition family status with which to filter the ListTaskDefinitionFamilies results. By default, both ACTIVE and INACTIVE task definition families are listed. If this parameter is set to ACTIVE, only task definition families that have an ACTIVE task definition revision are returned. If this parameter is set to INACTIVE, only task definition families that do not have any ACTIVE task definition revisions are returned. If you paginate the resulting output, be sure to keep the status value constant in each subsequent request. 

**Type:** STRING

</details>

## list_task_definitions

Returns a list of task definitions that are registered to your account. You can filter the results by family name with the familyPrefix parameter or by status with the status parameter.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ListTaskDefinitions.html

<details><summary>Parameters</summary>

#### familyPrefix

The full family name with which to filter the ListTaskDefinitions results. Specifying a familyPrefix limits the listed task definitions to task definition revisions that belong to that family. 

**Type:** STRING

#### sort

The order in which to sort the results. Valid values are ASC and DESC. By default (ASC), task definitions are listed lexicographically by family name and in ascending numerical order by revision so that the newest task definitions in a family are listed last. Setting this parameter to DESC reverses the sort order on family name and revision so that the newest task definitions in a family are listed first. 

**Type:** STRING

#### status

The task definition status with which to filter the ListTaskDefinitions results. By default, only ACTIVE task definitions are listed. By setting this parameter to INACTIVE, you can view task definitions that are INACTIVE as long as an active task or service still references them. If you paginate the resulting output, be sure to keep the status value constant in each subsequent request. 

**Type:** STRING

</details>

## list_tasks

Returns a list of tasks for a specified cluster. You can filter the results by family name, by a particular container instance, or by the desired status of the task with the family, containerInstance, and desiredStatus parameters.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ListTasks.html

<details><summary>Parameters</summary>

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the tasks to list. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### containerInstance

The container instance ID or full ARN of the container instance with which to filter the ListTasks results. Specifying a containerInstance limits the results to tasks that belong to that container instance. 

**Type:** STRING

#### desiredStatus

The task desired status with which to filter the ListTasks results. Specifying a desiredStatus of STOPPED limits the results to tasks that Amazon ECS has set the desired status to STOPPED. This can be useful for debugging tasks that are not starting properly or have died or finished. The default status filter is RUNNING, which shows tasks that Amazon ECS has set the desired status to RUNNING. Note Although you can filter results based on a desired status of PENDING, this does not return any results. Amazon ECS never sets the desired status of a task to that value (only a task's lastStatus may have a value of PENDING). 

**Type:** STRING

#### family

The name of the family with which to filter the ListTasks results. Specifying a family limits the results to tasks that belong to that family. 

**Type:** STRING

#### launchType

The launch type for services to list. 

**Type:** STRING

#### maxResults

The maximum number of task results returned by ListTasks in paginated output. When this parameter is used, ListTasks only returns maxResults results in a single page along with a nextToken response element. The remaining results of the initial request can be seen by sending another ListTasks request with the returned nextToken value. This value can be between 1 and 100. If this parameter is not used, then ListTasks returns up to 100 results and a nextToken value if applicable. 

**Type:** INTEGER

#### nextToken

The nextToken value returned from a previous paginated ListTasks request where maxResults was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the nextToken value. Note This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes. 

**Type:** STRING

#### serviceName

The name of the service with which to filter the ListTasks results. Specifying a serviceName limits the results to tasks that belong to that service. 

**Type:** STRING

#### startedBy

The startedBy value with which to filter the task results. Specifying a startedBy value limits the results to tasks that were started with that value. 

**Type:** STRING

</details>

## put_account_setting

Modifies the ARN and resource ID format of a resource type for a specified IAM user, IAM role, or the root user for an account. If the account setting for the root user is changed, it sets the default setting for all of the IAM users and roles for which no individual account setting has been set. The opt-in and opt-out account setting can be set for each Amazon ECS resource separately. The ARN and resource ID format of a resource will be defined by the opt-in status of the IAM user or role that created the resource. Enabling this setting is required to use new Amazon ECS features such as resource tagging. For more information, see Amazon Resource Names (ARNs) and IDs in the Amazon Elastic Container Service Developer Guide.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_PutAccountSetting.html

<details><summary>Parameters</summary>

#### name (required)

The resource name for which to enable the new format. If serviceLongArnFormat is specified, the ARN for your Amazon ECS services is affected. If taskLongArnFormat is specified, the ARN and resource ID for your Amazon ECS tasks is affected. If containerInstanceLongArnFormat is specified, the ARN and resource ID for your Amazon ECS container instances is affected. 

**Type:** STRING

#### value (required)

The account setting value for the specified principal ARN. Accepted values are enabled and disabled. 

**Type:** STRING

#### principalArn

The ARN of the principal, which can be an IAM user, IAM role, or the root user. If you specify the root user, it modifies the ARN and resource ID format for all IAM users, IAM roles, and the root user of the account unless an IAM user or role explicitly overrides these settings for themselves. If this field is omitted, the settings are changed only for the authenticated user. 

**Type:** STRING

</details>

## put_account_setting_default

Modifies the ARN and resource ID format of a resource type for all IAM users on an account for which no individual account setting has been set. Enabling this setting is required to use new Amazon ECS features such as resource tagging.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_PutAccountSettingDefault.html

<details><summary>Parameters</summary>

#### name (required)

The resource type to enable the new format for. If serviceLongArnFormat is specified, the ARN for your Amazon ECS services is affected. If taskLongArnFormat is specified, the ARN and resource ID for your Amazon ECS tasks are affected. If containerInstanceLongArnFormat is specified, the ARN and resource ID for your Amazon ECS container instances are affected. 

**Type:** STRING

#### value (required)

The account setting value for the specified principal ARN. Accepted values are enabled and disabled. 

**Type:** STRING

</details>

## put_attributes

Create or update an attribute on an Amazon ECS resource. If the attribute does not exist, it is created. If the attribute exists, its value is replaced with the specified value. To delete an attribute, use DeleteAttributes. For more information, see Attributes in the Amazon Elastic Container Service Developer Guide.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_PutAttributes.html

<details><summary>Parameters</summary>

#### attributes (required)

The attributes to apply to your resource. You can specify up to 10 custom attributes per resource. You can specify up to 10 attributes in a single call. 

**Type:** ARRAY

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that contains the resource to apply attributes. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

</details>

## register_container_instance

 Note This action is only used by the Amazon ECS agent, and it is not intended for use outside of the agent.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_RegisterContainerInstance.html

<details><summary>Parameters</summary>

#### attributes

The container instance attributes that this container instance supports. 

**Type:** ARRAY

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster with which to register your container instance. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### containerInstanceArn

The ARN of the container instance (if it was previously registered). 

**Type:** STRING

#### instanceIdentityDocument

The instance identity document for the EC2 instance to register. This document can be found by running the following command from the instance: curl http://169.254.169.254/latest/dynamic/instance-identity/document/ 

**Type:** STRING

#### instanceIdentityDocumentSignature

The instance identity document signature for the EC2 instance to register. This signature can be found by running the following command from the instance: curl http://169.254.169.254/latest/dynamic/instance-identity/signature/ 

**Type:** STRING

#### platformDevices

The devices that are available on the container instance. The only supported device type is a GPU. 

**Type:** ARRAY

#### tags

The metadata that you apply to the container instance to help you categorize and organize them. Each tag consists of a key and an optional value, both of which you define. Tag keys can have a maximum character length of 128 characters, and tag values can have a maximum length of 256 characters. 

**Type:** ARRAY

#### totalResources

The resources available on the instance. 

**Type:** ARRAY

#### versionInfo

The version information for the Amazon ECS container agent and Docker daemon running on the container instance. 

**Type:** OBJECT

</details>

## register_task_definition

Registers a new task definition from the supplied family and containerDefinitions. Optionally, you can add data volumes to your containers with the volumes parameter. For more information about task definition parameters and defaults, see Amazon ECS Task Definitions in the Amazon Elastic Container Service Developer Guide.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_RegisterTaskDefinition.html

<details><summary>Parameters</summary>

#### containerDefinitions (required)

A list of container definitions in JSON format that describe the different containers that make up your task. 

**Type:** ARRAY

#### family (required)

You must specify a family for a task definition, which allows you to track multiple versions of the same task definition. The family is used as a name for your task definition. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. 

**Type:** STRING

#### cpu

The number of CPU units used by the task. It can be expressed as an integer using CPU units, for example 1024, or as a string using vCPUs, for example 1 vCPU or 1 vcpu, in a task definition. String values are converted to an integer indicating the CPU units when the task definition is registered. Note Task-level CPU and memory parameters are ignored for Windows containers. We recommend specifying container-level resources for Windows containers. If you are using the EC2 launch type, this field is optional. Supported values are between 128 CPU units (0.125 vCPUs) and 10240 CPU units (10 vCPUs). If you are using the Fargate launch type, this field is required and you must use one of the following values, which determines your range of supported values for the memory parameter: 256 (.25 vCPU) - Available memory values: 512 (0.5 GB), 1024 (1 GB), 2048 (2 GB) 512 (.5 vCPU) - Available memory values: 1024 (1 GB), 2048 (2 GB), 3072 (3 GB), 4096 (4 GB) 1024 (1 vCPU) - Available memory values: 2048 (2 GB), 3072 (3 GB), 4096 (4 GB), 5120 (5 GB), 6144 (6 GB), 7168 (7 GB), 8192 (8 GB) 2048 (2 vCPU) - Available memory values: Between 4096 (4 GB) and 16384 (16 GB) in increments of 1024 (1 GB) 4096 (4 vCPU) - Available memory values: Between 8192 (8 GB) and 30720 (30 GB) in increments of 1024 (1 GB) 

**Type:** STRING

#### executionRoleArn

The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume. 

**Type:** STRING

#### ipcMode

The IPC resource namespace to use for the containers in the task. The valid values are host, task, or none. If host is specified, then all containers within the tasks that specified the host IPC mode on the same container instance share the same IPC resources with the host Amazon EC2 instance. If task is specified, all containers within the specified task share the same IPC resources. If none is specified, then IPC resources within the containers of a task are private and not shared with other containers in a task or on the container instance. If no value is specified, then the IPC resource namespace sharing depends on the Docker daemon setting on the container instance. For more information, see IPC settings in the Docker run reference. If the host IPC mode is used, be aware that there is a heightened risk of undesired IPC namespace expose. For more information, see Docker security. If you are setting namespaced kernel parameters using systemControls for the containers in the task, the following will apply to your IPC resource namespace. For more information, see System Controls in the Amazon Elastic Container Service Developer Guide. For tasks that use the host IPC mode, IPC namespace related systemControls are not supported. For tasks that use the task IPC mode, IPC namespace related systemControls will apply to all containers within a task. Note This parameter is not supported for Windows containers or tasks using the Fargate launch type. 

**Type:** STRING

#### memory

The amount of memory (in MiB) used by the task. It can be expressed as an integer using MiB, for example 1024, or as a string using GB, for example 1GB or 1 GB, in a task definition. String values are converted to an integer indicating the MiB when the task definition is registered. Note Task-level CPU and memory parameters are ignored for Windows containers. We recommend specifying container-level resources for Windows containers. If using the EC2 launch type, this field is optional. If using the Fargate launch type, this field is required and you must use one of the following values, which determines your range of supported values for the cpu parameter: 512 (0.5 GB), 1024 (1 GB), 2048 (2 GB) - Available cpu values: 256 (.25 vCPU) 1024 (1 GB), 2048 (2 GB), 3072 (3 GB), 4096 (4 GB) - Available cpu values: 512 (.5 vCPU) 2048 (2 GB), 3072 (3 GB), 4096 (4 GB), 5120 (5 GB), 6144 (6 GB), 7168 (7 GB), 8192 (8 GB) - Available cpu values: 1024 (1 vCPU) Between 4096 (4 GB) and 16384 (16 GB) in increments of 1024 (1 GB) - Available cpu values: 2048 (2 vCPU) Between 8192 (8 GB) and 30720 (30 GB) in increments of 1024 (1 GB) - Available cpu values: 4096 (4 vCPU) 

**Type:** STRING

#### networkMode

The Docker networking mode to use for the containers in the task. The valid values are none, bridge, awsvpc, and host. The default Docker network mode is bridge. If you are using the Fargate launch type, the awsvpc network mode is required. If you are using the EC2 launch type, any network mode can be used. If the network mode is set to none, you cannot specify port mappings in your container definitions, and the tasks containers do not have external connectivity. The host and awsvpc network modes offer the highest networking performance for containers because they use the EC2 network stack instead of the virtualized network stack provided by the bridge mode. With the host and awsvpc network modes, exposed container ports are mapped directly to the corresponding host port (for the host network mode) or the attached elastic network interface port (for the awsvpc network mode), so you cannot take advantage of dynamic host port mappings.  If the network mode is awsvpc, the task is allocated an elastic network interface, and you must specify a NetworkConfiguration value when you create a service or run a task with the task definition. For more information, see Task Networking in the Amazon Elastic Container Service Developer Guide. Note Currently, only Amazon ECS-optimized AMIs, other Amazon Linux variants with the ecs-init package, or AWS Fargate infrastructure support the awsvpc network mode.  If the network mode is host, you cannot run multiple instantiations of the same task on a single container instance when port mappings are used. Docker for Windows uses different network modes than Docker for Linux. When you register a task definition with Windows containers, you must not specify a network mode. If you use the console to register a task definition with Windows containers, you must choose the <default> network mode object.  For more information, see Network settings in the Docker run reference. 

**Type:** STRING

#### pidMode

The process namespace to use for the containers in the task. The valid values are host or task. If host is specified, then all containers within the tasks that specified the host PID mode on the same container instance share the same IPC resources with the host Amazon EC2 instance. If task is specified, all containers within the specified task share the same process namespace. If no value is specified, the default is a private namespace. For more information, see PID settings in the Docker run reference. If the host PID mode is used, be aware that there is a heightened risk of undesired process namespace expose. For more information, see Docker security. Note This parameter is not supported for Windows containers or tasks using the Fargate launch type. 

**Type:** STRING

#### placementConstraints

An array of placement constraint objects to use for the task. You can specify a maximum of 10 constraints per task (this limit includes constraints in the task definition and those specified at runtime). 

**Type:** ARRAY

#### requiresCompatibilities

The launch type required by the task. If no value is specified, it defaults to EC2. 

**Type:** ARRAY

#### tags

The metadata that you apply to the task definition to help you categorize and organize them. Each tag consists of a key and an optional value, both of which you define. Tag keys can have a maximum character length of 128 characters, and tag values can have a maximum length of 256 characters. 

**Type:** ARRAY

#### taskRoleArn

The short name or full Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role. For more information, see IAM Roles for Tasks in the Amazon Elastic Container Service Developer Guide. 

**Type:** STRING

#### volumes

A list of volume definitions in JSON format that containers in your task may use. 

**Type:** ARRAY

</details>

## run_task

Starts a new task using the specified task definition. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_RunTask.html

<details><summary>Parameters</summary>

#### taskDefinition (required)

The family and revision (family:revision) or full ARN of the task definition to run. If a revision is not specified, the latest ACTIVE revision is used. 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster on which to run your task. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### count

The number of instantiations of the specified task to place on your cluster. You can specify up to 10 tasks per call. 

**Type:** INTEGER

#### enableECSManagedTags

Specifies whether to enable Amazon ECS managed tags for the task. For more information, see Tagging Your Amazon ECS Resources in the Amazon Elastic Container Service Developer Guide. 

**Type:** BOOLEAN

#### group

The name of the task group to associate with the task. The default value is the family name of the task definition (for example, family:my-family-name). 

**Type:** STRING

#### launchType

The launch type on which to run your task. For more information, see Amazon ECS Launch Types in the Amazon Elastic Container Service Developer Guide. 

**Type:** STRING

#### networkConfiguration

The network configuration for the task. This parameter is required for task definitions that use the awsvpc network mode to receive their own elastic network interface, and it is not supported for other network modes. For more information, see Task Networking in the Amazon Elastic Container Service Developer Guide. 

**Type:** OBJECT

#### overrides

A list of container overrides in JSON format that specify the name of a container in the specified task definition and the overrides it should receive. You can override the default command for a container (that is specified in the task definition or Docker image) with a command override. You can also override existing environment variables (that are specified in the task definition or Docker image) on a container or add new environment variables to it with an environment override. Note A total of 8192 characters are allowed for overrides. This limit includes the JSON formatting characters of the override structure. 

**Type:** OBJECT

#### placementConstraints

An array of placement constraint objects to use for the task. You can specify up to 10 constraints per task (including constraints in the task definition and those specified at runtime). 

**Type:** ARRAY

#### placementStrategy

The placement strategy objects to use for the task. You can specify a maximum of five strategy rules per task. 

**Type:** ARRAY

#### platformVersion

The platform version the task should run. A platform version is only specified for tasks using the Fargate launch type. If one is not specified, the LATEST platform version is used by default. For more information, see AWS Fargate Platform Versions in the Amazon Elastic Container Service Developer Guide. 

**Type:** STRING

#### propagateTags

Specifies whether to propagate the tags from the task definition to the task. If no value is specified, the tags are not propagated. Tags can only be propagated to the task during task creation. To add tags to a task after task creation, use the TagResource API action. Note An error will be received if you specify the SERVICE option when running a task. 

**Type:** STRING

#### startedBy

An optional tag specified when a task is started. For example, if you automatically trigger a task to run a batch process job, you could apply a unique identifier for that job to your task with the startedBy parameter. You can then identify which tasks belong to that job by filtering the results of a ListTasks call with the startedBy value. Up to 36 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. If a task is started by an Amazon ECS service, then the startedBy parameter contains the deployment ID of the service that starts it. 

**Type:** STRING

#### tags

The metadata that you apply to the task to help you categorize and organize them. Each tag consists of a key and an optional value, both of which you define. Tag keys can have a maximum character length of 128 characters, and tag values can have a maximum length of 256 characters. 

**Type:** ARRAY

</details>

## start_task

Starts a new task from the specified task definition on the specified container instance or instances.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_StartTask.html

<details><summary>Parameters</summary>

#### containerInstances (required)

The container instance IDs or full ARN entries for the container instances on which you would like to place your task. You can specify up to 10 container instances. 

**Type:** ARRAY

#### taskDefinition (required)

The family and revision (family:revision) or full ARN of the task definition to start. If a revision is not specified, the latest ACTIVE revision is used. 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster on which to start your task. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### enableECSManagedTags

Specifies whether to enable Amazon ECS managed tags for the task. For more information, see Tagging Your Amazon ECS Resources in the Amazon Elastic Container Service Developer Guide. 

**Type:** BOOLEAN

#### group

The name of the task group to associate with the task. The default value is the family name of the task definition (for example, family:my-family-name). 

**Type:** STRING

#### networkConfiguration

The VPC subnet and security group configuration for tasks that receive their own elastic network interface by using the awsvpc networking mode. 

**Type:** OBJECT

#### overrides

A list of container overrides in JSON format that specify the name of a container in the specified task definition and the overrides it should receive. You can override the default command for a container (that is specified in the task definition or Docker image) with a command override. You can also override existing environment variables (that are specified in the task definition or Docker image) on a container or add new environment variables to it with an environment override. Note A total of 8192 characters are allowed for overrides. This limit includes the JSON formatting characters of the override structure. 

**Type:** OBJECT

#### propagateTags

Specifies whether to propagate the tags from the task definition or the service to the task. If no value is specified, the tags are not propagated. 

**Type:** STRING

#### startedBy

An optional tag specified when a task is started. For example, if you automatically trigger a task to run a batch process job, you could apply a unique identifier for that job to your task with the startedBy parameter. You can then identify which tasks belong to that job by filtering the results of a ListTasks call with the startedBy value. Up to 36 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. If a task is started by an Amazon ECS service, then the startedBy parameter contains the deployment ID of the service that starts it. 

**Type:** STRING

#### tags

The metadata that you apply to the task to help you categorize and organize them. Each tag consists of a key and an optional value, both of which you define. Tag keys can have a maximum character length of 128 characters, and tag values can have a maximum length of 256 characters. 

**Type:** ARRAY

</details>

## stop_task

Stops a running task. Any tags associated with the task will be deleted. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_StopTask.html

<details><summary>Parameters</summary>

#### task (required)

The task ID or full ARN entry of the task to stop. 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task to stop. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### reason

An optional message specified when a task is stopped. For example, if you are using a custom scheduler, you can use this parameter to specify the reason for stopping the task here, and the message appears in subsequent DescribeTasks API operations on this task. Up to 255 characters are allowed in this message. 

**Type:** STRING

</details>

## submit_container_state_change

 Note This action is only used by the Amazon ECS agent, and it is not intended for use outside of the agent.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_SubmitContainerStateChange.html

<details><summary>Parameters</summary>

#### cluster

The short name or full ARN of the cluster that hosts the container. 

**Type:** STRING

#### containerName

The name of the container. 

**Type:** STRING

#### exitCode

The exit code returned for the state change request. 

**Type:** INTEGER

#### networkBindings

The network bindings of the container. 

**Type:** ARRAY

#### reason

The reason for the state change request. 

**Type:** STRING

#### status

The status of the state change request. 

**Type:** STRING

#### task

The task ID or full Amazon Resource Name (ARN) of the task that hosts the container. 

**Type:** STRING

</details>

## submit_task_state_change

 Note This action is only used by the Amazon ECS agent, and it is not intended for use outside of the agent.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_SubmitTaskStateChange.html

<details><summary>Parameters</summary>

#### attachments

Any attachments associated with the state change request. 

**Type:** ARRAY

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task. 

**Type:** STRING

#### containers

Any containers associated with the state change request. 

**Type:** ARRAY

#### executionStoppedAt

The Unix timestamp for when the task execution stopped. 

**Type:** OBJECT

#### pullStartedAt

The Unix timestamp for when the container image pull began. 

**Type:** OBJECT

#### pullStoppedAt

The Unix timestamp for when the container image pull completed. 

**Type:** OBJECT

#### reason

The reason for the state change request. 

**Type:** STRING

#### status

The status of the state change request. 

**Type:** STRING

#### task

The task ID or full ARN of the task in the state change request. 

**Type:** STRING

</details>

## tag_resource

Associates the specified tags to a resource with the specified resourceArn. If existing tags on a resource are not specified in the request parameters, they are not changed. When a resource is deleted, the tags associated with that resource are deleted as well.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_TagResource.html

<details><summary>Parameters</summary>

#### resourceArn (required)

The Amazon Resource Name (ARN) of the resource to which to add tags. Currently, the supported resources are Amazon ECS tasks, services, task definitions, clusters, and container instances. 

**Type:** STRING

#### tags (required)

The tags to add to the resource. A tag is an array of key-value pairs. Tag keys can have a maximum character length of 128 characters, and tag values can have a maximum length of 256 characters. 

**Type:** ARRAY

</details>

## untag_resource

Deletes specified tags from a resource. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_UntagResource.html

<details><summary>Parameters</summary>

#### resourceArn (required)

The Amazon Resource Name (ARN) of the resource from which to delete tags. Currently, the supported resources are Amazon ECS tasks, services, task definitions, clusters, and container instances. 

**Type:** STRING

#### tagKeys (required)

The keys of the tags to be removed. 

**Type:** ARRAY

</details>

## update_container_agent

Updates the Amazon ECS container agent on a specified container instance. Updating the Amazon ECS container agent does not interrupt running tasks or services on the container instance. The process for updating the agent differs depending on whether your container instance was launched with the Amazon ECS-optimized AMI or another operating system.  https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_UpdateContainerAgent.html

<details><summary>Parameters</summary>

#### containerInstance (required)

The container instance ID or full ARN entries for the container instance on which you would like to update the Amazon ECS container agent. 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that your container instance is running on. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

</details>

## update_container_instances_state

Modifies the status of an Amazon ECS container instance. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_UpdateContainerInstancesState.html

<details><summary>Parameters</summary>

#### containerInstances (required)

A list of container instance IDs or full ARN entries. 

**Type:** ARRAY

#### status (required)

The container instance state with which to update the container instance. 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instance to update. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

</details>

## update_service

Modifies the parameters of a service. https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_UpdateService.html

<details><summary>Parameters</summary>

#### service (required)

The name of the service to update. 

**Type:** STRING

#### cluster

The short name or full Amazon Resource Name (ARN) of the cluster that your service is running on. If you do not specify a cluster, the default cluster is assumed. 

**Type:** STRING

#### deploymentConfiguration

Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks. 

**Type:** OBJECT

#### desiredCount

The number of instantiations of the task to place and keep running in your service. 

**Type:** INTEGER

#### forceNewDeployment

Whether to force a new deployment of the service. Deployments are not forced by default. You can use this option to trigger a new deployment with no service definition changes. For example, you can update a service's tasks to use a newer Docker image with the same image/tag combination (my_image:latest) or to roll Fargate tasks onto a newer platform version. 

**Type:** BOOLEAN

#### healthCheckGracePeriodSeconds

The period of time, in seconds, that the Amazon ECS service scheduler should ignore unhealthy Elastic Load Balancing target health checks after a task has first started. This is only valid if your service is configured to use a load balancer. If your service's tasks take a while to start and respond to Elastic Load Balancing health checks, you can specify a health check grace period of up to 1,800 seconds. During that time, the ECS service scheduler ignores the Elastic Load Balancing health check status. This grace period can prevent the ECS service scheduler from marking tasks as unhealthy and stopping them before they have time to come up. 

**Type:** INTEGER

#### networkConfiguration

The network configuration for the service. This parameter is required for task definitions that use the awsvpc network mode to receive their own elastic network interface, and it is not supported for other network modes. For more information, see Task Networking in the Amazon Elastic Container Service Developer Guide. Note Updating a service to add a subnet to a list of existing subnets does not trigger a service deployment. For example, if your network configuration change is to keep the existing subnets and simply add another subnet to the network configuration, this does not trigger a new service deployment. 

**Type:** OBJECT

#### platformVersion

The platform version on which your tasks in the service are running. A platform version is only specified for tasks using the Fargate launch type. If one is not specified, the LATEST platform version is used by default. For more information, see AWS Fargate Platform Versions in the Amazon Elastic Container Service Developer Guide. 

**Type:** STRING

#### taskDefinition

The family and revision (family:revision) or full ARN of the task definition to run in your service. If a revision is not specified, the latest ACTIVE revision is used. If you modify the task definition with UpdateService, Amazon ECS spawns a task with the new version of the task definition and then stops an old task after the new version is running. 

**Type:** STRING

</details>

