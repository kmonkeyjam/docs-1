---
id: hubspot-documentation
title: Hubspot (version v1.*.*)
sidebar_label: Hubspot
---

## add_contact_to_list

Add contact records that have already been created in the system to a contact list. You can add multiple records at once, either by vid or by email address. Up to 500 records can be added to a list in a single request, including records specified by ID and by email. Please note that you cannot manually add contacts to dynamic lists. To determine whether a list is dynamic or static, when you get a list, you will see a flag called dynamic that equates to true or false.

<details><summary>Parameters</summary>

#### list_id (required)

Unique identifier for the list that you're looking for.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/lists/add_contact_to_list

**Type:** object

</details>

## batch_create_or_update_events



<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/timeline/batch-create-or-update-events

**Type:** object

</details>

## create_batch_contacts

Create a group of contacts or update them if they already exist. Particularly useful for periodic syncs from another contacts database to HubSpot.

<details><summary>Parameters</summary>

#### $body

For formatting, see https://developers.hubspot.com/docs/methods/contacts/batch_create_or_update

**Type:** object

#### auditId

A string that allows you to represent these change sources however you'd like.

**Type:** string

</details>

## create_contact

Create a new contact in HubSpot with a simple HTTP POST to the Contacts API. The contact will be created instantly inside of HubSpot, and will be assigned a unique ID (vid) that can be used to look up the contact inside of HubSpot later.

<details><summary>Parameters</summary>

#### $body

Properties for the contact to be added. While we recommend that all contact records include an email address, it is possible to create contacts without an email address by leaving out the email property.

**Type:** object

</details>

## create_contact_list

Create a new list in a given HubSpot account to populate with contacts. Creating this list show in the user interface, so beware that users will be able to edit and even delete lists that are programatically created in HubSpot.

<details><summary>Parameters</summary>

#### $body

See https://developers.hubspot.com/docs/methods/lists/create_list for format

**Type:** object

</details>

## create_event_type

Create Timeline Event Type for a particular application

<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

#### userId (required)

The ID of the user you're creating the event type for.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/timeline/create-event-type

**Type:** object

</details>

## create_or_update_contact

Create a contact if it doesn't exist in an account already, or update it with the latest property values if it does. If successful, your request will return the unique identifier (VID) of the contact and whether or not the request was a create or an update.

<details><summary>Parameters</summary>

#### contact_email (required)

**Type:** string

#### $body

Properties for the contact to be created or updated. While we recommend that all contact records include an email address, it is possible to create contacts without an email address by leaving out the email property.

**Type:** object

</details>

## create_smtp_api_token

This endpoint is used to create an SMTP API Token. An API token provides both a username and password which can then be used to send email through the HubSpot SMTP API.

<details><summary>Parameters</summary>

#### $body

See format details at https://developers.hubspot.com/docs/methods/email/transactional_email/smtpapi_overview/list/create

**Type:** object

</details>

## create_timeline_event_type_property

Create a new property for a specified timeline event type.

<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

#### event_type_id (required)

The ID of the event type you want to update.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/timeline/create-event-type-property

**Type:** object

</details>

## create_update_event

Create a new event, or update an existing event.

<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/timeline/create-or-update-event

**Type:** object

</details>

## delete_contact

Delete an existing contact from a particular HubSpot portal. If a contact with the same email address interacts with the portal again (via a form submission for example) the contact will be added back into the user interface.

<details><summary>Parameters</summary>

#### contact_id (required)

You must pass the Contact's ID that you're deleting in the request URL.

**Type:** string

</details>

## delete_contact_list

Delete a list in a given HubSpot account, identified by its unique ID. Note that lists can be used by users to trigger marketing automation campaigns, so a good best practice is to only delete the lists that your integration with HubSpot has created.

<details><summary>Parameters</summary>

#### list_id (required)

Unique identifier for the list that you're looking for.

**Type:** string

</details>

## delete_event_type

Delete an existing Timeline event type.

<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

</details>

## get_batch_by_email

For a given account, return information about a group of contacts by their email addresses. This method will also return you much of the HubSpot lead "intelligence" for each requested contact record. The endpoint accepts many query parameters that allow for customization based on a variety of integration use cases.

<details><summary>Parameters</summary>

#### email (required)

The email of the contact that you want to get the data for. You can include this parameter multiple times to request multiple records. Any email address that doesn't belong to an existing contact record will be ignored. Requests should be limited to 100 or fewer emails.

**Type:** string

#### formSubmissionMode

One of “all”, “none”, “newest”, “oldest” to specify which form submissions should be fetched. Default is “newest”.

**Type:** string

#### includeDeletes

Boolean "true" or "false" to indicate whether the return of deleted contacts is desired. Default is false.

**Type:** boolean

#### property

Specify the properties that should be returned for each ID. By default, the endpoint returns all valued properties for a contact.

**Type:** string

#### propertyMode

One of “value_only” or “value_and_history” to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is “value_only”.

**Type:** string

#### showListMemberships

Boolean "true" or "false" to indicate whether current list memberships should be fetched for the contact. Default is false.

**Type:** boolean

</details>

## get_batch_by_user_token

For a given account, return information about a group of contacts by their user tokens. A visitor's user token is stored in the hubspotutk cookie. This cookie is created automatically by the HubSpot tracking code. The endpoint accepts many query parameters that allow for customization based on a variety of integration use cases. By default, this endpoint will not return the history for properties, only the current value of any populated properties, but you can include the history using the parameters listed below.

<details><summary>Parameters</summary>

#### utk (required)

Each user token requires it's own query parameter (utk=xxx&amp;utk=yyy). Requests should be limited to 100 or fewer user tokens. Any user tokens that are provided that are not associated with a contact record will be ignored.

**Type:** string

#### formSubmissionMode

One of “all”, “none”, “newest”, “oldest” to specify which form submissions should be fetched. Default is “newest”.

**Type:** string

#### includeDeletes

Boolean true or false to indicate whether the return of deleted contacts is desired. Default is false.

**Type:** boolean

#### property

Specify the properties that should be returned for each ID. By default, the endpoint returns all valued properties for a contact. If this parameter is used, only the specified property or properties will be included.

**Type:** string

#### propertyMode

One of “value_only” or “value_and_history” to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is “value_only”.

**Type:** string

#### showListMemberships

Boolean "true" or "false" to indicate whether current list memberships should be fetched for the contact. Default is false.

**Type:** boolean

</details>

## get_batch_by_vid

For a given account, return information about a group of contacts by their unique IDs. A contact's unique ID is stored in a field called 'vid' which stands for 'visitor ID'. The endpoint accepts many query parameters that allow for customization based on a variety of integration use cases. By default, this endpoint will not return the history for properties, only the current value of any populated properties, but you can include the history using the parameters listed below.

<details><summary>Parameters</summary>

#### vid (required)

Each vid requires it's own query parameter (vid=10&amp;vid=11). Requests should be limited to 100 or fewer vids. Any vids that are provided that are invalid will be ignored.

**Type:** string

#### formSubmissionMode

One of “all”, “none”, “newest”, “oldest” to specify which form submissions should be fetched. Default is “newest”.

**Type:** string

#### includeDeletes

Boolean true or false to indicate whether the return of deleted contacts is desired. Default is false.

**Type:** boolean

#### property

Specify the properties that should be returned for each ID. By default, the endpoint returns all valued properties for a contact. If this parameter is used, only the specified property or properties will be included.

**Type:** string

#### propertyMode

One of “value_only” or “value_and_history” to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is “value_only”.

**Type:** string

#### showListMemberships

Boolean "true" or "false" to indicate whether current list memberships should be fetched for the contact. Default is false.

**Type:** boolean

</details>

## get_batch_contact_lists

For a given account, return a set of contact lists that you specify with multiple listId parameters. This will return only the metadata on these lists and not all of the contacts in the list. See this page for details on getting contact records in individual lists.

<details><summary>Parameters</summary>

#### listId (required)

An integer that represents the list IDs that you want returned to your call. As you can see in the example URL below, you can specify as many "listId" parameters as you wish on the URL to return multiple lists at once. Any list IDs that are invalid will be ignored.

**Type:** string

</details>

## get_campaign_data

For a given campaign, return data associated with the campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The ID of the campaign you want to update.

**Type:** string

</details>

## get_contact_by_email

For a given account, return information about a single contact by its email address. Since all contacts in HubSpot are de-duplicated off of an email address, you will only ever receive a single contact back from the API.

<details><summary>Parameters</summary>

#### contact-email (required)

**Type:** string

#### formSubmissionMode

One of “all”, “none”, “newest”, “oldest” to specify which form submissions should be fetched. Default is “all”.

**Type:** string

#### property

By default, all valued properties will be included. If you include the "property" parameter, then the returned data will only include the property or properties that you request.

**Type:** string

#### propertyMode

One of “value_only” or “value_and_history” to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is “value_and_history”.

**Type:** string

#### showListMemberships

Boolean "true" or "false" to indicate whether current list memberships should be fetched for the contact. Default is true.

**Type:** boolean

</details>

## get_contact_by_utk

For a given account, return information about a single contact by its user token, stored in the hubspotutk cookie. This cookie is created automatically by the HubSpot tracking code.
This method will also return you much of the HubSpot lead "intelligence" for each requested contact record. The endpoint accepts many query parameters that allow for customization based on a variety of integration use cases.

<details><summary>Parameters</summary>

#### contact_utk (required)

The user token (HubSpot cookie) for the contact that you're searching for.

**Type:** string

#### formSubmissionMode

One of “all”, “none”, “newest”, “oldest” to specify which form submissions should be fetched. Default is “all”.

**Type:** string

#### property

By default, all valued properties will be included. If you include the "property" parameter, then the returned data will only include the property or properties that you request.

**Type:** string

#### propertyMode

One of “value_only” or “value_and_history” to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is “value_and_history”.

**Type:** string

#### showListMemberships

Boolean "true" or "false" to indicate whether current list memberships should be fetched for the contact. Default is true.

**Type:** boolean

</details>

## get_contact_by_vid

Update an existing contact in HubSpot. This method lets you update the properties of a contact in HubSpot.

<details><summary>Parameters</summary>

#### vid (required)

**Type:** string

#### formSubmissionMode

One of 'all', 'none', 'newest', 'oldest' to specify which form submissions should be fetched. Default is 'all'.

**Type:** string

#### property

By default, you will get all properties that the contact has values for. If you include the "property" parameter, then the returned data will only include the property or properties that you request. You can include this parameter multiple times to specify multiple properties. The lastmodifieddate and associatedcompanyid will always be included, even if not specified. Keep in mind that only properties that have a value will be included in the response, even if specified in the URL.

**Type:** string

#### propertyMode

One of 'value_only' or 'value_and_history' to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is 'value_and_history'.

**Type:** string

#### showListMemberships

Boolean 'true' or 'false' to indicate whether current list memberships should be fetched for the contact. Default is true.

**Type:** string

</details>

## get_contact_list

For a given portal, return a contact list by its unique ID. This returns only the metadata for the list; see this page for getting the contact records in the list. If you are not storing the list ids inside of your application, you'll need to first find the list id by using the get all lists endpoint.

<details><summary>Parameters</summary>

#### list_id (required)

Unique identifier for the list that you're looking for.

**Type:** string

</details>

## get_contact_property

Returns a JSON object representing the definition for a given contact property.

<details><summary>Parameters</summary>

#### list_id (required)

Unique identifier for the list that you're looking for.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/companies/get_contact_property

**Type:** object

</details>

## get_event

Get the data for a specific timeline event. All data that the event has will be returned, including the optional fields that were set for you.

<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

#### event_id (required)

The ID of the event you want to retrieve.

**Type:** string

#### event_type_id (required)

The ID of the event type you want to update.

**Type:** string

</details>

## get_event_by_id

Query the event log for a specific event and get results for that email event.

<details><summary>Parameters</summary>

#### created (required)

The creation timestamp (in milliseconds since epoch) of the event to return.

**Type:** string

#### id (required)

The unique ID of the event to return.

**Type:** string

</details>

## get_lifecyclestages_for_contacts

Returns the number of contacts that entered the individual lifecycle stages during the provided time period. The time period may be up to a two year window. Additionally supports aggregating the results by a second property. This property must be an enumerated property (such as a multiple checkbox or dropdown property) with 20 or fewer option. This would support custom enumerated properties.

<details><summary>Parameters</summary>

#### fromTimestamp (required)

A millisecond timestamp representing the start of the time period that you want the stats for.

**Type:** integer

#### toTimestamp (required)

A millisecond timestamp representing the end of the time period that you want the stats for.

**Type:** integer

#### aggregationProperty

A second optional property to further breakdown the lifecycle stage buckets. This must be an enumerated property with 20 or fewer options.

**Type:** string

</details>

## get_subscription_status

For a given portal, return the email subscription information for the given email address and portal. For specific email subscription types, if the value is true or false, the definition will be returned. If the value is null for a specific type, nothing will be returned.

<details><summary>Parameters</summary>

#### email_address (required)

The email address for which you are requesting subscription status.

**Type:** string

#### portalId (required)

The HubSpot Portal ID for the portal that you're making the call for.

**Type:** string

</details>

## get_timeline_event_type_properties

Get the custom properties for a specified event type.

<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

#### event_type_id (required)

The ID of the event type you want to update.

**Type:** string

</details>

## list_all_contact_lists



*This operation has no parameters*

## list_all_contacts

For a given portal, return all contacts that have been created in the portal. A paginated list of contacts will be returned to you, with a maximum of 100 contacts per page.

<details><summary>Parameters</summary>

#### formSubmissionMode

One of 'all', 'none', 'newest', 'oldest' to specify which form submissions should be fetched. Default is 'newest'.

**Type:** string

#### property

If you include the 'property' parameter, then you will get the specified property in the response. This parameter may be included multiple times to specify multiple properties.

**Type:** string

#### propertyMode

One of 'value_only' or 'value_and_history' to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is 'value_only'.

**Type:** string

#### showListMemberships

Boolean 'true' or 'false' to indicate whether current list memberships should be fetched for the contact. Default is false.

**Type:** string

</details>

## list_campaigns



*This operation has no parameters*

## list_campaigns_by_id



*This operation has no parameters*

## list_contact_lists_dynamic



*This operation has no parameters*

## list_contact_lists_static



*This operation has no parameters*

## list_contacts_in_list

For a given portal and a given list, identified by its unique ID, return a list of contacts that are in that list.

<details><summary>Parameters</summary>

#### list_id (required)

Unique identifier for the list that you're looking for.

**Type:** string

#### formSubmissionMode

One of “all”, “none”, “newest”, “oldest” to specify which form submissions should be fetched. Default is “newest”.

**Type:** string

#### property

If you include the "property" parameter, then the properties in the "contact" object in the returned data will only include the property or properties that you request.

**Type:** string

#### propertyMode

One of “value_only” or “value_and_history” to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is “value_only”.

**Type:** string

#### showListMemberships

Boolean "true" or "false" to indicate whether current list memberships should be fetched for the contact. Default is false.

**Type:** boolean

</details>

## list_email_events

Query the event log for events matching specified parameters. Note that events will be returned in reverse-chronological order.

<details><summary>Parameters</summary>

#### appId

Only return events which correspond to the given HubSpot Application ID.

**Type:** string

#### campaignId

Only return events from the given HubSpot Campaign ID.

**Type:** string

#### endTimestamp

Only return events which occurred at or before the given timestamp (in milliseconds since epoch).

**Type:** string

#### eventType

Only return events of the specified type (case-sensitive). The possible types are described in the <a href="/docs/methods/email/email_events_overview">Email Events Bible .

**Type:** string

#### excludeFilteredEvents

Only return events that have not been filtered out due to customer filtering settings. The default value is false.

**Type:** boolean

#### recipient

Only return events related to the given recipient.

**Type:** string

#### startTimestamp

Only return events which occurred at or after the given timestamp (in milliseconds since epoch).

**Type:** string

</details>

## list_event_types

Get Timeline Event Types for a particular application

<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

#### userId (required)

The ID of the user you're creating the event type for.

**Type:** string

</details>

## list_recently_added_contacts_in_list

For a given HubID and a given list, return contacts that have been recently added to that list, starting with the most recently added contact and pageing backwards. A paginated list of contacts will be returned to you, with a maximum of 100 contacts per page, as specified by the "count" parameter.

<details><summary>Parameters</summary>

#### list_id (required)

Unique identifier for the list that you're looking for.

**Type:** string

#### formSubmissionMode

One of “all”, “none”, “newest”, “oldest” to specify which form submissions should be fetched. Default is “newest”.

**Type:** string

#### property

If you include the "property" parameter, then the properties in the "contact" object in the returned data will only include the property or properties that you request.

**Type:** string

#### propertyMode

One of “value_only” or “value_and_history” to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is “value_only”.

**Type:** string

#### showListMemberships

Boolean "true" or "false" to indicate whether current list memberships should be fetched for the contact. Default is false.

**Type:** boolean

</details>

## list_recently_created_contacts

For a given account, return all contacts that have been recently created. A paginated list of contacts will be returned to you, with a maximum of 100 contacts per page, as specified by the "count" parameter.

<details><summary>Parameters</summary>

#### formSubmissionMode

One of “all”, “none”, “newest”, “oldest” to specify which form submissions should be fetched. Default is “newest”.

**Type:** string

#### property

If you include the "property" parameter, then the properties in the "contact" object in the returned data will only include the property or properties that you request.

**Type:** string

#### propertyMode

One of “value_only” or “value_and_history” to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is “value_only”.

**Type:** string

#### showListMemberships

Boolean "true" or "false" to indicate whether current list memberships should be fetched for the contact. Default is false.

**Type:** boolean

</details>

## list_recently_updated_contacts

For a given portal, return all contacts that have been recently updated or created. A paginated list of contacts will be returned to you, with a maximum of 100 contacts per page, as specified by the "count" parameter. The endpoint only scrolls back in time 30 days.

<details><summary>Parameters</summary>

#### formSubmissionMode

One of “all”, “none”, “newest”, “oldest” to specify which form submissions should be fetched. Default is “newest”.

**Type:** string

#### property

If you include the "property" parameter, then the properties in the "contact" object in the returned data will only include the property or properties that you request.

**Type:** string

#### propertyMode

One of “value_only” or “value_and_history” to specify if the current value for a property should be fetched, or the value and all the historical values for that property. Default is “value_only”.

**Type:** string

#### showListMemberships

Boolean "true" or "false" to indicate whether current list memberships should be fetched for the contact. Default is false.

**Type:** boolean

</details>

## list_smtp_api_tokens



*This operation has no parameters*

## list_subscriptions

Returns all email subscription types that have been created in the given Hub ID.

<details><summary>Parameters</summary>

#### portalId (required)

The HubSpot Portal ID for the portal that you're making the call for.

**Type:** string

</details>

## list_subscriptions_timeline

For a given portal, return a time-ordered list of subscription changes.

<details><summary>Parameters</summary>

#### changeType

Only return timeline changes of the specified type (case-sensitive). The possible types are described in the <a href="/docs/methods/email/email_subscriptions_overview">Email Subscriptions Bible .

**Type:** string

#### endTimestamp

Only return timeline items which occurred at or before the given timestamp (in milliseconds since epoch).

**Type:** string

#### includeSnapshots

Include the user's full subscription snapshot with each timeline item. This snapshot is equivalent to what <a href="/docs/methods/email/get_status">this endpoint would have returned at that time.

**Type:** string

#### startTimestamp

Only return timeline items which occurred at or after the given timestamp (in milliseconds since epoch).

**Type:** string

</details>

## merge_contacts

Merge two contact records. The contact ID in the URL will be treated as the primary contact, and the contact ID in the request body will be treated as the secondary contact.

<details><summary>Parameters</summary>

#### contact_id (required)

Unique identifier for a particular contact. In HubSpot's contact system, contact ID's are called "vid".

**Type:** string

#### $body

properties for the contact to be updated

**Type:** object

</details>

## reset_password

Once you have an SMTP API, the List SMTP API Tokens endpoint can be used to list all SMTP API Tokens in the portal. However, for security reasons the password is only provided during the time of the token creation. This endpoint allows for the creation of a replacement password for a given Token, keyed by the userName field.

<details><summary>Parameters</summary>

#### userName (required)

The userName field of the SMTP API Token needing a password reset.

**Type:** string

</details>

## search_contacts

For a given account, return contacts and some data associated with those contacts by the contact's email address, first and last name, phone number, and company name.

<details><summary>Parameters</summary>

#### q (required)

The search term for what you're searching for. You can use all of a word or just parts of a word as well. For example, if you we're searching for contacts with "hubspot" in their name or email, searching for "hub" would also return contacts with "hubspot" in their email address.

**Type:** string

#### property

If you include the "property" parameter, then the properties in the "contact" object in the returned data will only include the property or properties that you request.

**Type:** string

</details>

## send_single_email

Send an email designed and maintained in the HubSpot marketing Email Tool.

<details><summary>Parameters</summary>

#### $body

See format details at https://developers.hubspot.com/docs/methods/email/transactional_email/single-send-overview

**Type:** object

</details>

## update_contact_by_email

Update an existing contact in HubSpot. This method lets you update the properties of a contact in HubSpot.

<details><summary>Parameters</summary>

#### contact-email (required)

**Type:** string

#### $body

properties for the contact to be updated

**Type:** object

</details>

## update_contact_by_vid



<details><summary>Parameters</summary>

#### vid (required)

**Type:** string

#### $body

properties for the contact to be updated

**Type:** object

</details>

## update_event_type

Update an existing event type.

<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

#### event_type_id (required)

The ID of the event type you want to update.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/timeline/update-event-type

**Type:** object

</details>

## update_list

Update a list in a given HubSpot account. Note that like creating a list, users will be able to edit and even delete these lists inside of the HubSpot user interface.

<details><summary>Parameters</summary>

#### list_id (required)

Unique identifier for the list that you're looking for.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/lists/update_list

**Type:** object

</details>

## update_subscription_status

For a given email address, update the email type subscription status, or permanently unsubscribe an email address from all email.

<details><summary>Parameters</summary>

#### email_address (required)

The email address for which you are requesting subscription status.

**Type:** string

#### portalId (required)

The HubSpot Portal ID for the portal that you're making the call for.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/email/update_status

**Type:** object

</details>

## update_timeline_event_type_property

Update an existing property for a specified timeline event type. The id passed in the JSON body needs to match the id of an existing property or this will return a 404 error.  Properties cannot be moved from one event type to another, so the eventTypeId included in the JSON body must match the event-type-id in the URL. Please note that the name cannot be updated.

<details><summary>Parameters</summary>

#### application_id (required)

The ID of the OAuth app you're creating the event type for.

**Type:** string

#### event_type_id (required)

The ID of the event type you want to update.

**Type:** string

#### $body

See format details at https://developers.hubspot.com/docs/methods/timeline/udpate-timeline-event-type-property

**Type:** object

</details>

