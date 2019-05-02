---
id: mailchimp-documentation
title: Mailchimp (version v1.*.*)
sidebar_label: Mailchimp
---

## add_cart_to_store

Add a new cart to a store.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific cart.

**Type:** object

</details>

## add_customer_to_store

Add a new customer to a store.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific customer. Orders for existing customers should include only the `id` parameter in the `customer` object body.

**Type:** object

</details>

## add_feedback_to_campaign

Add feedback on a specific campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### $body

A specific feedback message from a specific campaign.

**Type:** object

</details>

## add_interest_to_interest_category

Create a new interest or 'group name' for a specific category.

<details><summary>Parameters</summary>

#### interest_category_id (required)

The unique id for the interest category.

**Type:** string

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Assign subscribers to interests to group them together. Interests are referred to as 'group names' in the MailChimp application.

**Type:** object

</details>

## add_line_item_to_cart

Add a new line item to an existing cart.

<details><summary>Parameters</summary>

#### cart_id (required)

The id for the cart.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific cart line item.

**Type:** object

</details>

## add_line_item_to_order_in_store

Add a new line item to an existing order.

<details><summary>Parameters</summary>

#### order_id (required)

The id for the order in a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific order line.

**Type:** object

</details>

## add_member_to_list

Add a new member to the list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Individuals who are currently or have been previously subscribed to this list, including members who have bounced or unsubscribed.

**Type:** object

</details>

## add_member_to_segment

Add a member to a static segment.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### segment_id (required)

The unique id for the segment.

**Type:** string

#### $body

**Type:** object

</details>

## add_merge_field_to_list

Add a new merge field for a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

A merge field (formerly merge vars) for a specific list. These correspond to merge fields in MailChimp's lists and subscriber profiles.

**Type:** object

</details>

## add_order_in_store

Add a new order to a store.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific order.

**Type:** object

</details>

## add_product_to_store

Add a new product to a store.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific product.

**Type:** object

</details>

## add_subscriber_to_email_workflow

Manually add a subscriber to a workflow, bypassing the default trigger settings. You can also use this endpoint to trigger a series of automated emails in an [API 3.0 workflow type](http://kb.mailchimp.com/automation/about-automation-workflow-types?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs#Using-the-API) or add subscribers to an automated email queue that uses the [API request delay type](http://kb.mailchimp.com/automation/about-automation-workflow-types?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs#Using-the-API).

<details><summary>Parameters</summary>

#### workflow_email_id (required)

The unique id for the Automation workflow email.

**Type:** string

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

#### $body

Information about subscribers in an Automation email queue.

**Type:** object

</details>

## add_variant_to_product_in_store

Add a new variant to the product.

<details><summary>Parameters</summary>

#### product_id (required)

The id for the product of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific product variant.

**Type:** object

</details>

## batch_update_members_in_list

Batch subscribe or unsubscribe list members.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Members to subscribe to or unsubscribe from a list.

**Type:** object

</details>

## batch_update_members_in_segment

Batch add/remove list members to static segment

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### segment_id (required)

The unique id for the segment.

**Type:** string

#### $body

Members to add/remove to/from a static segment

**Type:** object

</details>

## cancel_campaign

Cancel a Regular or Plain-Text Campaign after you send, before all of your recipients receive it. This feature is included with [MailChimp Pro](http://mailchimp.com/pro?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs).

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

</details>

## create_campaign

Create a new MailChimp campaign.

<details><summary>Parameters</summary>

#### $body

A summary of an individual campaign's settings and content.

**Type:** object

</details>

## create_campaign_folder

Create a new campaign folder.

<details><summary>Parameters</summary>

#### $body

A folder used to organize campaigns.

**Type:** object

</details>

## create_interest_category_for_list

Create a new interest category.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Interest categories organize interests, which are used to group subscribers based on their preferences. These correspond to Group Titles the application.

**Type:** object

</details>

## create_list

Create a new list in your MailChimp account.

<details><summary>Parameters</summary>

#### $body

Information about a specific list.

**Type:** object

</details>

## create_note_for_member_of_list

Add a new note for a specific subscriber.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### $body

A specific note for a specific member.

**Type:** object

</details>

## create_segment_for_list

Create a new segment in a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Information about a specific list segment.

**Type:** object

</details>

## create_store

Add a new store to your MailChimp account.

<details><summary>Parameters</summary>

#### $body

An individual store in an account.

**Type:** object

</details>

## create_template

Create a new template for the account. Only [Classic templates](http://kb.mailchimp.com/templates/basic-and-themes/types-of-templates?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs) are supported.

<details><summary>Parameters</summary>

#### $body

Information about a specific template.

**Type:** object

</details>

## create_template_folder

Create a new template folder.

<details><summary>Parameters</summary>

#### $body

A folder used to organize templates.

**Type:** object

</details>

## create_twitter_lead_gen_card_for_list

Create a new Twitter Lead Generation Card for a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Twitter Lead Generation Card.

**Type:** object

</details>

## create_webhook_in_list

Create a new webhook for a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Configure a webhook for the given list.

**Type:** object

</details>

## customize_signup_form_for_list

Customize a list's default signup form.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

List signup form.

**Type:** object

</details>

## delete_batch_request

Stops a batch request from running. Since only one batch request is run at a time, this can be used to cancel a long running request. The results of any completed operations will not be available after this call.

<details><summary>Parameters</summary>

#### batch_id (required)

The unique id for the batch operation.

**Type:** string

</details>

## delete_campaign

Remove a campaign from your MailChimp account.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

</details>

## delete_campaign_folder

Delete a specific campaign folder, and mark all the campaigns in the folder as 'unfiled'.

<details><summary>Parameters</summary>

#### folder_id (required)

The unique folder id.

**Type:** string

</details>

## delete_cart_in_store

Delete a cart.

<details><summary>Parameters</summary>

#### cart_id (required)

The id for the cart.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

</details>

## delete_customer_from_store

Delete a customer from a store.

<details><summary>Parameters</summary>

#### customer_id (required)

The id for the customer of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

</details>

## delete_feedback_from_campaign

Remove a specific feedback message for a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### feedback_id (required)

The unique id for the feedback message.

**Type:** string

</details>

## delete_file_from_file_manager

Remove a specific file from the File Manager.

<details><summary>Parameters</summary>

#### file_id (required)

The unique id for the File Manager file.

**Type:** string

</details>

## delete_folder_from_file_manager

Delete a specific folder in the File Manager.

<details><summary>Parameters</summary>

#### folder_id (required)

The unique folder id.

**Type:** string

</details>

## delete_interest_category_from_list

Delete a specific interest category.

<details><summary>Parameters</summary>

#### interest_category_id (required)

The unique id for the interest category.

**Type:** string

#### list_id (required)

The unique id for the list.

**Type:** string

</details>

## delete_interests_in_category_of_list

Delete interests or group names in a specific category.

<details><summary>Parameters</summary>

#### interest_category_id (required)

The unique id for the interest category.

**Type:** string

#### interest_id (required)

The specific interest or 'group name'.

**Type:** string

#### list_id (required)

The unique id for the list.

**Type:** string

</details>

## delete_line_item_from_cart_in_store

Delete a specific cart line item.

<details><summary>Parameters</summary>

#### cart_id (required)

The id for the cart.

**Type:** string

#### line_id (required)

The id for the line item.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

</details>

## delete_line_item_from_order_in_store

Delete a specific order line item.

<details><summary>Parameters</summary>

#### line_id (required)

The id for the line item.

**Type:** string

#### order_id (required)

The id for the order in a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

</details>

## delete_list

Delete a list from your MailChimp account. If you delete a list, you'll lose the list history—including subscriber activity, unsubscribes, complaints, and bounces. You’ll also lose subscribers’ email addresses, unless you [exported and backed up your list](http://kb.mailchimp.com/lists/managing-subscribers/view-or-export-a-list?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs#View-or-Export-a-List).

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

</details>

## delete_member_from_list

Delete a member from a list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

</details>

## delete_member_from_segment

Remove a member from the specified static segment.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### segment_id (required)

The unique id for the segment.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

</details>

## delete_merge_field_from_list

Delete a specific merge field in a list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### merge_id (required)

The id for the merge field.

**Type:** string

</details>

## delete_note_for_member_of_list

Delete a specific note for a specific list member.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### note_id (required)

The id for the note.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

</details>

## delete_order_from_store

Delete an order.

<details><summary>Parameters</summary>

#### order_id (required)

The id for the order in a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

</details>

## delete_product_from_store

Delete a product.

<details><summary>Parameters</summary>

#### product_id (required)

The id for the product of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

</details>

## delete_segment_from_list

Delete a specific segment in a list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### segment_id (required)

The unique id for the segment.

**Type:** string

</details>

## delete_store

Delete a store. Deleting a store will also delete any associated subresources, including Customers, Orders, Products, and Carts.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

</details>

## delete_subscriber_from_workflow

[Remove a subscriber](http://kb.mailchimp.com/automation/add-or-remove-subscribers-from-automation-workflow?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs) from a specific Automation workflow. You can remove a subscriber at any point in an Automation workflow, regardless of how many emails they've been sent from that workflow. Once they're removed, they can never be added back to the same workflow.

<details><summary>Parameters</summary>

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

#### $body

Information about subscribers in an Automation email queue.

**Type:** object

</details>

## delete_template

Delete a specific template.

<details><summary>Parameters</summary>

#### template_id (required)

The unique id for the template.

**Type:** string

</details>

## delete_template_folder

Delete a specific template folder, and mark all the templates in the folder as 'unfiled'.

<details><summary>Parameters</summary>

#### folder_id (required)

The unique folder id.

**Type:** string

</details>

## delete_variant_for_product_in_store

Delete a product variant.

<details><summary>Parameters</summary>

#### product_id (required)

The id for the product of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### variant_id (required)

The id for the product variant.

**Type:** string

</details>

## delete_webhook_from_list

Delete a specific webhook in a list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### webhook_id (required)

The unique ID for the webhook.

**Type:** string

</details>

## get_abuse_report_from_campaign

Get information about a specific abuse report for a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### report_id (required)

The id for the abuse report.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_abuse_report_from_list

Get details about a specific abuse report.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### report_id (required)

The id for the abuse report.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_audiences_dashboard

Get all the audiences info for the mobile dashboard

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_authorized_app

Get information about a specific authorized application.

<details><summary>Parameters</summary>

#### app_id (required)

The unique id for the connected authorized application.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_batch_status

Get the status of a batch request.

<details><summary>Parameters</summary>

#### batch_id (required)

The unique id for the batch operation.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_campaign

Get information about a specific campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_campaign_folder

Get information about a specific folder used to organize campaigns.

<details><summary>Parameters</summary>

#### folder_id (required)

The unique folder id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_cart_for_store

Get information about a specific cart.

<details><summary>Parameters</summary>

#### cart_id (required)

The id for the cart.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_click_details_for_campaign

Get information about [clicks](http://kb.mailchimp.com/reports/about-click-tracking?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs) on specific links in your MailChimp campaigns.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_click_details_for_link_in_campaign

Get click details for a specific link in a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### link_id (required)

The id for the link.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_content_from_campaign

Get the the HTML and plain-text content for a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_conversation

Get details about an individual conversation.

<details><summary>Parameters</summary>

#### conversation_id (required)

The unique id for the conversation.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_customer_information

Get information about a specific customer.

<details><summary>Parameters</summary>

#### customer_id (required)

The id for the customer of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_default_content_for_template

Get the sections that you can edit in a template, including each section's default content.

<details><summary>Parameters</summary>

#### template_id (required)

The unique id for the template.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_domain_performance_stats

Get statistics for the top-performing email domains in a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_ecommerce_dashboard

Get all the ecommerce info for the mobile dashboard

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_ecommerce_endpoint



*This operation has no parameters*

## get_eepurl_activity

Get a summary of social activity for the campaign, tracked by EepURL.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_email_activity_for_member_in_campaign

Get a specific list member's activity in a campaign including opens, clicks, and bounces.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_email_from_workflow

Get information about an individual Automation workflow email.

<details><summary>Parameters</summary>

#### workflow_email_id (required)

The unique id for the Automation workflow email.

**Type:** string

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## get_engagement_dashboard

Get all the engagement info for the mobile dashboard

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_feedback_from_campaign

Get a specific feedback message from a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### feedback_id (required)

The unique id for the feedback message.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_feedback_report_for_campaign

Get feedback based on a campaign's statistics. Advice feedback is based on campaign stats like opens, clicks, unsubscribes, bounces, and more.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_file_from_file_manager

Get information about a specific file in the File Manager.

<details><summary>Parameters</summary>

#### file_id (required)

The unique id for the File Manager file.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_file_manager_endpoint



*This operation has no parameters*

## get_folder_in_file_manager

Get information about a specific folder in the File Manager.

<details><summary>Parameters</summary>

#### folder_id (required)

The unique folder id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_growth_history_by_month_for_list

Get a summary of a specific list's growth activity for a specific month and year.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### month (required)

A specific month of list growth history.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_growth_history_data_for_list

Get a month-by-month summary of a specific list's growth activity.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_interest_category_from_list

Get information about a specific interest category.

<details><summary>Parameters</summary>

#### interest_category_id (required)

The unique id for the interest category.

**Type:** string

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_interest_in_interest_category

Get interests or 'group names' for a specific category.

<details><summary>Parameters</summary>

#### interest_category_id (required)

The unique id for the interest category.

**Type:** string

#### interest_id (required)

The specific interest or 'group name'.

**Type:** string

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_line_item_for_cart_in_store

Get information about a specific cart line item.

<details><summary>Parameters</summary>

#### cart_id (required)

The id for the cart.

**Type:** string

#### line_id (required)

The id for the line item.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_line_item_in_order_in_store

Get information about a specific order line item.

<details><summary>Parameters</summary>

#### line_id (required)

The id for the line item.

**Type:** string

#### order_id (required)

The id for the order in a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_list

Get information about a specific list in your MailChimp account. Results include list members who have signed up but haven't confirmed their subscription yet and [unsubscribed or cleaned](http://kb.mailchimp.com/lists/managing-subscribers/view-unsubscribed-and-cleaned-addresses?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs).

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_lists_id_members_id_goals

Get the last 50 Goal events for a member on a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_member_from_click_details

Get information about a specific subscriber who clicked a link in a specific campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### link_id (required)

The id for the link.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_member_from_list

Get information about a specific list member, including a currently subscribed, unsubscribed, or bounced member.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_merge_field_from_list

Get information about a specific merge field in a list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### merge_id (required)

The id for the merge field.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_message_in_conversation

Get an individual message in a conversation.

<details><summary>Parameters</summary>

#### conversation_id (required)

The unique id for the conversation.

**Type:** string

#### message_id (required)

The unique id for the conversation message.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_note_for_member_of_list

Get a specific note for a specific list member.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### note_id (required)

The id for the note.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_onboarding_ads_dashboard

Get all the onboarding ads info for the mobile dashboard

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### num

Restrict results to this number of ads (if we have that many. Default is 3.

**Type:** integer

#### platform

Restrict results to ads compatible with the given platform. Default is ios

**Type:** string

</details>

## get_order_for_store

Get information about a specific order.

<details><summary>Parameters</summary>

#### order_id (required)

The id for the order in a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_product_in_store

Get information about a specific product.

<details><summary>Parameters</summary>

#### product_id (required)

The id for the product of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_recipient_from_campaign

Get information about a specific campaign recipient.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_removed_subscriber_from_workflow

Get information about a specific subscriber who was [removed from an Automation workflow](http://kb.mailchimp.com/automation/add-or-remove-subscribers-from-automation-workflow?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs).

<details><summary>Parameters</summary>

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## get_report_for_campaign

Get report details for a specific sent campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_segment_of_list

Get information about a specific segment.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### segment_id (required)

The unique id for the segment.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_send_checklist_for_campaign

Review the send checklist for a campaign, and resolve any issues before sending.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_store

Get information about a specific store.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_subscriber_in_email_queue

Get information about a specific subscriber in an Automation email queue.

<details><summary>Parameters</summary>

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### workflow_email_id (required)

The unique id for the Automation workflow email.

**Type:** string

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## get_template

Get information about a specific template.

<details><summary>Parameters</summary>

#### template_id (required)

The unique id for the template.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_template_folder

Get information about a specific folder used to organize templates.

<details><summary>Parameters</summary>

#### folder_id (required)

The unique folder id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_twitter_lead_gen_card_for_list

Get information about a specific Twitter Lead Generation Card.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### twitter_card_id (required)

The unique ID for the Twitter Lead Generation Card.

**Type:** string

</details>

## get_unsubscribed_member_from_list

Get information about a specific list member who unsubscribed from a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_variant_for_product_in_store

Get information about a specific product variant.

<details><summary>Parameters</summary>

#### product_id (required)

The id for the product of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### variant_id (required)

The id for the product variant.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## get_webhook_for_list

Get information about a specific webhook.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### webhook_id (required)

The unique ID for the webhook.

**Type:** string

</details>

## get_workflow

Get a summary of an individual Automation workflow's settings and content. The `trigger_settings` object returns information for the first email in the workflow.

<details><summary>Parameters</summary>

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## link_authorized_app

Retrieve OAuth2-based credentials to associate API calls with your application.

<details><summary>Parameters</summary>

#### $body

Use this endpoint to link your application and retrieve OAuth2-based credentials. This is useful if you can't implement the OAuth2 flow but still want to associate calls with your application.

**Type:** object

</details>

## list_abuse_reports_for_campaign

Get a list of [abuse complaints](http://kb.mailchimp.com/accounts/compliance-tips/about-abuse-complaints?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs) for a specific campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_abuse_reports_for_list

Get all abuse reports for a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_activity_for_list

Get up to the previous 180 days of daily detailed aggregated activity stats for a list, not including Automation activity.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_activity_for_member_in_list

Get the last 50 events of a member's activity on a specific list, including opens, clicks, and unsubscribes.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_api_resources

Get links to all other resources available in the API.

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_authorized_apps

Get a list of an account's registered, connected applications.

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_automations

Get a summary of an account's Automations.

<details><summary>Parameters</summary>

#### before_create_time

Restrict the response to automations created before the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### before_send_time

Restrict the response to automations sent before the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### since_create_time

Restrict the response to automations created after the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### since_send_time

Restrict the response to automations sent after the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### status

Restrict the results to automations with the specified status.

**Type:** string

**Potential values:** save, paused, sending

</details>

## list_batches

Get a summary of batch requests that have been made.

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_campaign_folders

Get all folders used to organize campaigns.

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_campaigns

Get all campaigns in an account.

<details><summary>Parameters</summary>

#### before_create_time

Restrict the response to campaigns created before the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### before_send_time

Restrict the response to campaigns sent before the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### folder_id

The unique folder id.

**Type:** string

#### list_id

The unique id for the list.

**Type:** string

#### since_create_time

Restrict the response to campaigns created after the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### since_send_time

Restrict the response to campaigns sent after the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### status

The status of the campaign.

**Type:** string

**Potential values:** save, paused, schedule, sending, sent

#### type

The campaign type.

**Type:** string

**Potential values:** regular, plaintext, absplit, rss, variate

</details>

## list_carts_for_store

Get information about a store's carts.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_conversations

Get a list of conversations for the account.

<details><summary>Parameters</summary>

#### campaign_id

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### has_unread_messages

Whether the conversation has any unread messages.

**Type:** string

**Potential values:** true, false

#### list_id

The unique id for the list.

**Type:** string

</details>

## list_customers_for_store

Get information about a store's customers.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### email_address

Restrict the response to customers with the email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_dashboard_charts

Get info about which dashboard charts to show for this user

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_email_activity

Get a list of member's subscriber activity in a specific campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_emails_in_email_workflow

Get a summary of the emails in an Automation workflow.

<details><summary>Parameters</summary>

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## list_feedback_for_campaign

Get team feedback while you're [working together on a MailChimp campaign](http://kb.mailchimp.com/campaigns/design/collaborate-on-campaigns?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs).

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_files_in_file_manager

Get a list of available images and files stored in the File Manager for the account.

<details><summary>Parameters</summary>

#### before_created_at

Restrict the response to files created before the set date.

**Type:** string

#### created_by

The MailChimp account user who created the File Manager file.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### since_created_at

Restrict the response to files created after the set date.

**Type:** string

#### sort_dir

Determines the order direction for sorted results.

**Type:** string

**Potential values:** ASC, DESC

#### sort_field

Returns files sorted by the specified field.

**Type:** string

**Potential values:** added_date

#### type

The file type for the File Manager file.

**Type:** string

</details>

## list_folders_in_file_manager

Get a list of all folders in the File Manager.

<details><summary>Parameters</summary>

#### before_created_at

Restrict the response to files created before the set date.

**Type:** string

#### created_by

The MailChimp account user who created the File Manager file.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### since_created_at

Restrict the response to files created after the set date.

**Type:** string

</details>

## list_interest_categories_for_list

Get information about a list's interest categories.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### type

Restrict results a type of interest group

**Type:** string

</details>

## list_interests_in_interest_category

Get a list of this category's interests.

<details><summary>Parameters</summary>

#### interest_category_id (required)

The unique id for the interest category.

**Type:** string

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_line_items_for_cart

Get information about a cart's line items.

<details><summary>Parameters</summary>

#### cart_id (required)

The id for the cart.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_line_items_from_order_in_store

Get information about an order's line items.

<details><summary>Parameters</summary>

#### order_id (required)

The id for the order in a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_lists

Get information about all lists in the account.

<details><summary>Parameters</summary>

#### before_campaign_last_sent

Restrict results to lists created before the last campaign send date.

**Type:** string

#### before_date_created

Restrict response to lists created before the set date.

**Type:** string

#### email

Restrict results to lists that include a specific subscriber's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### since_campaign_last_sent

Restrict results to lists created after the last campaign send date.

**Type:** string

#### since_date_created

Restrict results to lists created after the set date.

**Type:** string

</details>

## list_members_click_details_for_campaign

Get information about list members who clicked on a specific link in a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### link_id (required)

The id for the link.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_members_in_list

Get information about members in a specific MailChimp list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### before_last_changed

Restrict results to subscribers whose information changed before the set timeframe.

**Type:** string

#### before_timestamp_opt

Restrict results to subscribers who opted-in before the set timeframe.

**Type:** string

#### email_type

The email type.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### interest_category_id

The unique id for the interest category.

**Type:** string

#### interest_ids

Used to filter list members by interests. Must be accompanied by interest_category_id and interest_match. The value must be a comma separated list of interest ids present for the given interest category.

**Type:** string

#### interest_match

Used to filter list members by interests. Must be accompanied by interest_category_id and interest_ids. "any" will match a member with any of the interest supplied, "all" will only match members with every interest supplied, and "none" will match members without any of the interest supplied.

**Type:** string

**Potential values:** any, all, none

#### since_last_changed

Restrict results to subscribers whose information changed after the set timeframe.

**Type:** string

#### since_timestamp_opt

Restrict results to subscribers who opted-in after the set timeframe.

**Type:** string

#### status

The subscriber's status.

**Type:** string

#### unique_email_id

A unique identifier for the email address across all MailChimp lists. This parameter can be found in any links with [Ecommerce Tracking](http://kb.mailchimp.com/integrations/e-commerce/how-to-use-mailchimp-for-e-commerce?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs) enabled.

**Type:** string

#### vip_only

A filter to return only the list's VIP members. Passing `true` will restrict results to VIP list members, passing `false` will return all list members.

**Type:** boolean

</details>

## list_members_in_segment_of_list

Get information about members in a [saved segment](http://kb.mailchimp.com/segments/how-to-use-saved-segments?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs).

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### segment_id (required)

The unique id for the segment.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_merge_fields_for_list

Get a list of all merge fields (formerly merge vars) for a list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### required

The boolean value if the merge field is required.

**Type:** boolean

#### type

The merge field type.

**Type:** string

</details>

## list_messages_in_conversation

Get messages from a specific conversation.

<details><summary>Parameters</summary>

#### conversation_id (required)

The unique id for the conversation.

**Type:** string

#### before_timestamp

Restrict the response to messages created before the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### is_read

Whether a conversation message has been marked as read.

**Type:** string

**Potential values:** true, false

#### since_timestamp

Restrict the response to messages created after the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

</details>

## list_notes_for_member_in_list

Get recent notes for a specific list member.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_orders_for_store

Get information about a store's orders.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### campaign_id

Restrict results to orders with a specific `campaign_id` value.

**Type:** string

#### customer_id

Restrict results to orders made by a specific customer.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_products_for_store

Get information about a store's products.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_queued_subscribers_for_email_workflow

Get information about an Automation email queue.

<details><summary>Parameters</summary>

#### workflow_email_id (required)

The unique id for the Automation workflow email.

**Type:** string

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## list_recipients_of_campaign

Get information about campaign recipients.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_removed_subscribers_from_workflow

Get information about subscribers who were [removed from an Automation workflow](http://kb.mailchimp.com/automation/add-or-remove-subscribers-from-automation-workflow?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs).

<details><summary>Parameters</summary>

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## list_reports_for_campaign

Get campaign reports.

<details><summary>Parameters</summary>

#### before_send_time

Restrict the response to campaigns sent before the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### since_send_time

Restrict the response to campaigns sent after the set time. We recommend [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) time format: 2015-10-21T15:41:36+00:00.

**Type:** date-time

#### type

The campaign type.

**Type:** string

**Potential values:** regular, plaintext, absplit, rss, variate

</details>

## list_segments_for_list

Get information about all available segments for a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### before_created_at

Restrict results to segments created before the set time.

**Type:** string

#### before_updated_at

Restrict results to segments update before the set time.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### since_created_at

Restrict results to segments created after the set time.

**Type:** string

#### since_updated_at

Restrict results to segments update after the set time.

**Type:** string

#### type

Limit results based on segment type.

**Type:** string

</details>

## list_signup_forms_for_list

Get signup forms for a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

</details>

## list_stores

Get information about all stores in the account.

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_subreports_for_campaign

Get a list of reports with child campaigns for a specific parent campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_template_folders

Get all folders used to organize templates.

<details><summary>Parameters</summary>

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_templates

Get a list of an account's available templates.

<details><summary>Parameters</summary>

#### before_created_at

Restrict the response to templates created before the set date.

**Type:** string

#### created_by

The MailChimp account user who created the template.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### folder_id

The unique folder id.

**Type:** string

#### since_created_at

Restrict the response to templates created after the set date.

**Type:** string

#### type

Limit results based on template type.

**Type:** string

</details>

## list_top_email_clients

Get a list of the top email clients based on user-agent strings.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_top_open_locations_for_campaign

Get top open locations for a specific campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_twitter_lead_gen_cards_for_list

Get information about all Twitter Lead Generation Cards for a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

</details>

## list_unsubscribed_members_from_list

Get information about members who have unsubscribed from a specific campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_variants_for_product_in_store

Get information about a product's variants.

<details><summary>Parameters</summary>

#### product_id (required)

The id for the product of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## list_webhooks_for_list

Get information about all webhooks for a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

</details>

## patch_customer_in_store

Update a customer.

<details><summary>Parameters</summary>

#### customer_id (required)

The id for the customer of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific customer. Orders for existing customers should include only the `id` parameter in the `customer` object body.

**Type:** object

</details>

## patch_member_in_list

Update information for a specific list member.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### $body

Individuals who are currently or have been previously subscribed to this list, including members who have bounced or unsubscribed.

**Type:** object

</details>

## patch_variant_for_product_in_store

Update a product variant.

<details><summary>Parameters</summary>

#### product_id (required)

The id for the product of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### variant_id (required)

The id for the product variant.

**Type:** string

#### $body

Information about a specific product variant.

**Type:** object

</details>

## pause_automated_email

Pause an automated email.

<details><summary>Parameters</summary>

#### workflow_email_id (required)

The unique id for the Automation workflow email.

**Type:** string

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## pause_emails_in_email_workflow

Pause all emails in a specific Automation workflow.

<details><summary>Parameters</summary>

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## post_campaigns_id_actions_resume

[Resume an RSS-Driven campaign](http://kb.mailchimp.com/campaigns/rss-in-campaigns/pause-or-reactivate-an-rss-driven-campaign?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs).

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

</details>

## post_file_manager_folders

Create a new folder in the File Manager.

<details><summary>Parameters</summary>

#### $body

An individual folder listed in the File Manager.

**Type:** object

</details>

## post_message_to_conversation

Post a new message to a conversation.

<details><summary>Parameters</summary>

#### conversation_id (required)

The unique id for the conversation.

**Type:** string

#### $body

An individual message in a conversation. Conversation tracking is a feature available to paid accounts that lets you view replies to your campaigns in your MailChimp account.

**Type:** object

</details>

## puase_campaign

[Pause an RSS-Driven campaign](http://kb.mailchimp.com/campaigns/rss-in-campaigns/pause-or-reactivate-an-rss-driven-campaign?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs).

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

</details>

## replicate_campaign

[Replicate a campaign](http://kb.mailchimp.com/campaigns/ways-to-build/replicate-a-campaign-or-automation-workflow?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs) in saved or send status.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

</details>

## schedule_campaign

[Schedule a campaign](http://kb.mailchimp.com/campaigns/confirmation-and-sending/schedule-pause-or-send-a-campaign?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs) for delivery. If you're using [Multivariate Campaigns](http://kb.mailchimp.com/campaigns/multivariate/about-multivariate-campaigns?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs) to test send times or sending [RSS Campaigns](http://kb.mailchimp.com/campaigns/rss-in-campaigns/create-an-rss-campaign?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs), use the [send](http://developer.mailchimp.com/documentation/mailchimp/reference/campaigns/#action-post_campaigns_campaign_id_actions_send) action instead.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### $body

**Type:** object

</details>

## search_campaigns

Search all campaigns for the specified query terms.

<details><summary>Parameters</summary>

#### query (required)

The search query used to filter results.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

</details>

## search_members_in_list

Search for list members. This search can be restricted to a specific list, or can be used to search across all lists in an account.

<details><summary>Parameters</summary>

#### query (required)

The search query used to filter results.

**Type:** string

#### exclude_fields

A comma-separated list of fields to exclude. Reference parameters of sub-objects with dot notation.

**Type:** array

#### fields

A comma-separated list of fields to return. Reference parameters of sub-objects with dot notation.

**Type:** array

#### list_id

The unique id for the list.

**Type:** string

</details>

## send_campaign

Send a MailChimp campaign. For [RSS Campaigns](http://kb.mailchimp.com/campaigns/rss-in-campaigns/create-an-rss-campaign?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs), the campaign will send according to its schedule. All other campaigns will send immediately.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

</details>

## send_test_email_for_campaign

Send a [test email](http://kb.mailchimp.com/campaigns/previews-and-tests/preview-and-test-your-campaign?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs).

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### $body

**Type:** object

</details>

## set_content_for_campaign

Set the content for a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### $body

The HTML and plain-text content for a campaign

**Type:** object

</details>

## start_all_emails_in_email_workflow

Start all emails in an Automation workflow.

<details><summary>Parameters</summary>

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## start_batch_operation

Begin processing a batch operations request.

<details><summary>Parameters</summary>

#### $body

**Type:** object

</details>

## start_email_workflow

Start an automated email.

<details><summary>Parameters</summary>

#### workflow_email_id (required)

The unique id for the Automation workflow email.

**Type:** string

#### workflow_id (required)

The unique id for the Automation workflow.

**Type:** string

</details>

## unschedule_campaign

[Unschedule](http://kb.mailchimp.com/campaigns/confirmation-and-sending/schedule-pause-or-send-a-campaign?utm_source=mc-api&utm_medium=docs&utm_campaign=apidocs#Pause-a-Scheduled-Campaign) a scheduled campaign that hasn't started sending.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

</details>

## update_campaign

Update some or all of the settings for a specific campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### $body

A summary of an individual campaign's settings and content.

**Type:** object

</details>

## update_campaign_folder

Update a specific folder used to organize campaigns.

<details><summary>Parameters</summary>

#### folder_id (required)

The unique folder id.

**Type:** string

#### $body

A folder used to organize campaigns.

**Type:** object

</details>

## update_cart_in_store

Update a specific cart.

<details><summary>Parameters</summary>

#### cart_id (required)

The id for the cart.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific cart.

**Type:** object

</details>

## update_customer_in_store

Add or update a customer.

<details><summary>Parameters</summary>

#### customer_id (required)

The id for the customer of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific customer. Orders for existing customers should include only the `id` parameter in the `customer` object body.

**Type:** object

</details>

## update_feedback_message_for_campaign

Update a specific feedback message for a campaign.

<details><summary>Parameters</summary>

#### campaign_id (required)

The unique id for the campaign.

**Type:** string

#### feedback_id (required)

The unique id for the feedback message.

**Type:** string

#### $body

A specific feedback message from a specific campaign.

**Type:** object

</details>

## update_file_in_file_manager

Update a file in the File Manager.

<details><summary>Parameters</summary>

#### file_id (required)

The unique id for the File Manager file.

**Type:** string

#### $body

An individual file listed in the File Manager.

**Type:** object

</details>

## update_folder_in_file_manager

Update a specific File Manager folder.

<details><summary>Parameters</summary>

#### folder_id (required)

The unique folder id.

**Type:** string

#### $body

An individual folder listed in the File Manager.

**Type:** object

</details>

## update_interest_category_for_list

Update a specific interest category.

<details><summary>Parameters</summary>

#### interest_category_id (required)

The unique id for the interest category.

**Type:** string

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Interest categories organize interests, which are used to group subscribers based on their preferences. These correspond to Group Titles the application.

**Type:** object

</details>

## update_interests_for_interest_category_in_list

Update interests or 'group names' for a specific category.

<details><summary>Parameters</summary>

#### interest_category_id (required)

The unique id for the interest category.

**Type:** string

#### interest_id (required)

The specific interest or 'group name'.

**Type:** string

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Assign subscribers to interests to group them together. Interests are referred to as 'group names' in the MailChimp application.

**Type:** object

</details>

## update_line_item_for_order_in_store

Update a specific order line item.

<details><summary>Parameters</summary>

#### line_id (required)

The id for the line item.

**Type:** string

#### order_id (required)

The id for the order in a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific order line.

**Type:** object

</details>

## update_line_item_in_cart

Update a specific cart line item.

<details><summary>Parameters</summary>

#### cart_id (required)

The id for the cart.

**Type:** string

#### line_id (required)

The id for the line item.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific cart line item.

**Type:** object

</details>

## update_list

Update the settings for a specific list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### $body

Information about a specific list.

**Type:** object

</details>

## update_member_in_list

Add or update a list member.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### $body

Individuals who are currently or have been previously subscribed to this list, including members who have bounced or unsubscribed.

**Type:** object

</details>

## update_merge_field_in_list

Update a specific merge field in a list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### merge_id (required)

The id for the merge field.

**Type:** string

#### $body

A merge field (formerly merge vars) for a specific list. These correspond to merge fields in MailChimp's lists and subscriber profiles.

**Type:** object

</details>

## update_note_for_member_in_list

Update a specific note for a specific list member.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### note_id (required)

The id for the note.

**Type:** string

#### subscriber_hash (required)

The MD5 hash of the lowercase version of the list member's email address.

**Type:** string

#### $body

A specific note for a specific member.

**Type:** object

</details>

## update_order_in_store

Update a specific order.

<details><summary>Parameters</summary>

#### order_id (required)

The id for the order in a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific order.

**Type:** object

</details>

## update_product_in_store

Update a specific product.

<details><summary>Parameters</summary>

#### product_id (required)

The id for the product of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### $body

Information about a specific product.

**Type:** object

</details>

## update_segment_for_list

Update a specific segment in a list.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### segment_id (required)

The unique id for the segment.

**Type:** string

#### $body

Information about a specific list segment.

**Type:** object

</details>

## update_store

Update a store.

<details><summary>Parameters</summary>

#### store_id (required)

The store id.

**Type:** string

#### $body

An individual store in an account.

**Type:** object

</details>

## update_template

Update the name, HTML, or `folder_id` of an existing template.

<details><summary>Parameters</summary>

#### template_id (required)

The unique id for the template.

**Type:** string

#### $body

Information about a specific template.

**Type:** object

</details>

## update_template_folder

Update a specific folder used to organize templates.

<details><summary>Parameters</summary>

#### folder_id (required)

The unique folder id.

**Type:** string

#### $body

A folder used to organize templates.

**Type:** object

</details>

## update_variant_for_product_in_store

Add or update a product variant.

<details><summary>Parameters</summary>

#### product_id (required)

The id for the product of a store.

**Type:** string

#### store_id (required)

The store id.

**Type:** string

#### variant_id (required)

The id for the product variant.

**Type:** string

#### $body

Information about a specific product variant.

**Type:** object

</details>

## update_webhook_for_list

Update the settings for an existing webhook.

<details><summary>Parameters</summary>

#### list_id (required)

The unique id for the list.

**Type:** string

#### webhook_id (required)

The unique ID for the webhook.

**Type:** string

#### $body

Configure a webhook for the given list.

**Type:** object

</details>

## upload_file_to_file_manager

 Upload a new image or file to the File Manager.

<details><summary>Parameters</summary>

#### $body

An individual file listed in the File Manager.

**Type:** object

</details>

