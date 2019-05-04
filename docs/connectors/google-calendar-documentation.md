---
id: google-calendar-documentation
title: Google Calendar (version v1.*.*)
sidebar_label: Google Calendar
---

## clear_calendar

Clears a primary calendar. This operation deletes all events associated with the primary calendar of an account.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## create_acl_rule

Creates an access control rule.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### $body

**Type:** object

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### sendNotifications

Deprecated. Use sendUpdates instead

**Type:** boolean

</details>

## create_calendar

Creates a secondary calendar.

<details><summary>Parameters</summary>

#### $body

**Type:** object

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## create_calendar_event

Creates an event.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### $body

**Type:** object

#### conferenceDataVersion

Version number of conference data supported by the API client. Version 0 assumes no conference data support and ignores conference data in the event's body. Version 1 enables support for copying of ConferenceData as well as for creating new conferences using the createRequest field of conferenceData. The default is 0.

**Type:** integer

#### maxAttendees

The maximum number of attendees to include in the response. If there are more than the specified number of attendees, only the participant is returned. Optional.

**Type:** integer

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### sendNotifications

Deprecated. Use sendUpdates instead

**Type:** boolean

#### supportsAttachments

Whether API client performing operation supports event attachments. Optional. The default is False.

**Type:** boolean

</details>

## create_calendarlist_entry

Adds an entry to the user's calendar list.

<details><summary>Parameters</summary>

#### $body

**Type:** object

#### colorRgbFormat

Whether to use the foregroundColor and backgroundColor fields to write the calendar colors (RGB). If this feature is used, the index-based colorId field will be set to the best matching option automatically. Optional. The default is False.

**Type:** boolean

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## delete_acl_rule

Deletes an access control rule.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### ruleId (required)

ACL rule identifier.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## delete_calendar

Deletes a secondary calendar. Use calendars.clear for clearing all events on primary calendars.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## delete_calendar_event

Deletes an event.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### eventId (required)

Event identifier.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### sendNotifications

Deprecated. Use sendUpdates instead

**Type:** boolean

</details>

## delete_calendarlist_entry

Deletes an entry on the user's calendar list.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## get_acl_rule

Returns an access control rule.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### ruleId (required)

ACL rule identifier.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## get_acl_rules

Returns the rules in the access control list for the calendar.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### showDeleted

Whether to include deleted ACLs in the result. Deleted ACLs are represented by role equal to "none". Deleted ACLs will always be included if syncToken is provided. Optional. The default is False.

**Type:** boolean

#### syncToken

Token obtained from the nextSyncToken field returned on the last page of results from the previous list request. It makes the result of this list request contain only entries that have changed since then. All entries deleted since the previous list request will always be in the result set and it is not allowed to set showDeleted to False.
If the syncToken expires, the server will respond with a 410 GONE response code and the client should clear its storage and perform a full synchronization without any syncToken.
Learn more about incremental synchronization.
Optional. The default is to return all entries.

**Type:** string

</details>

## get_calendar

Returns metadata for a calendar.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## get_calendar_colors

Returns the color definitions for calendars and events.

<details><summary>Parameters</summary>

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## get_calendar_event

Returns an event.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### eventId (required)

Event identifier.

**Type:** string

#### alwaysIncludeEmail

Whether to always include a value in the email field for the organizer, creator and attendees, even if no real email is available (i.e. a generated, non-working value will be provided). The use of this option is discouraged and should only be used by clients which cannot handle the absence of an email address value in the mentioned places. Optional. The default is False.

**Type:** boolean

#### maxAttendees

The maximum number of attendees to include in the response. If there are more than the specified number of attendees, only the participant is returned. Optional.

**Type:** integer

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### timeZone

Time zone used in the response. Optional. The default is the time zone of the calendar.

**Type:** string

</details>

## get_calendar_event_instances

Returns instances of the specified recurring event.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### eventId (required)

Recurring event identifier.

**Type:** string

#### alwaysIncludeEmail

Whether to always include a value in the email field for the organizer, creator and attendees, even if no real email is available (i.e. a generated, non-working value will be provided). The use of this option is discouraged and should only be used by clients which cannot handle the absence of an email address value in the mentioned places. Optional. The default is False.

**Type:** boolean

#### maxAttendees

The maximum number of attendees to include in the response. If there are more than the specified number of attendees, only the participant is returned. Optional.

**Type:** integer

#### originalStart

The original start time of the instance in the result. Optional.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### showDeleted

Whether to include deleted events (with status equals "cancelled") in the result. Cancelled instances of recurring events will still be included if singleEvents is False. Optional. The default is False.

**Type:** boolean

#### timeMax

Upper bound (exclusive) for an event's start time to filter by. Optional. The default is not to filter by start time. Must be an RFC3339 timestamp with mandatory time zone offset.

**Type:** string

#### timeMin

Lower bound (inclusive) for an event's end time to filter by. Optional. The default is not to filter by end time. Must be an RFC3339 timestamp with mandatory time zone offset.

**Type:** string

#### timeZone

Time zone used in the response. Optional. The default is the time zone of the calendar.

**Type:** string

</details>

## get_calendar_events

Returns events on the specified calendar.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### alwaysIncludeEmail

Whether to always include a value in the email field for the organizer, creator and attendees, even if no real email is available (i.e. a generated, non-working value will be provided). The use of this option is discouraged and should only be used by clients which cannot handle the absence of an email address value in the mentioned places. Optional. The default is False.

**Type:** boolean

#### iCalUID

Specifies event ID in the iCalendar format to be included in the response. Optional.

**Type:** string

#### maxAttendees

The maximum number of attendees to include in the response. If there are more than the specified number of attendees, only the participant is returned. Optional.

**Type:** integer

#### orderBy

The order of the events returned in the result. Optional. The default is an unspecified, stable order.

**Type:** string

**Potential values:** startTime, updated

#### privateExtendedProperty

Extended properties constraint specified as propertyName=value. Matches only private properties. This parameter might be repeated multiple times to return events that match all given constraints.

**Type:** array

#### q

Free text search terms to find events that match these terms in any field, except for extended properties. Optional.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### sharedExtendedProperty

Extended properties constraint specified as propertyName=value. Matches only shared properties. This parameter might be repeated multiple times to return events that match all given constraints.

**Type:** array

#### showDeleted

Whether to include deleted events (with status equals "cancelled") in the result. Cancelled instances of recurring events (but not the underlying recurring event) will still be included if showDeleted and singleEvents are both False. If showDeleted and singleEvents are both True, only single instances of deleted events (but not the underlying recurring events) are returned. Optional. The default is False.

**Type:** boolean

#### showHiddenInvitations

Whether to include hidden invitations in the result. Optional. The default is False.

**Type:** boolean

#### singleEvents

Whether to expand recurring events into instances and only return single one-off events and instances of recurring events, but not the underlying recurring events themselves. Optional. The default is False.

**Type:** boolean

#### syncToken

Token obtained from the nextSyncToken field returned on the last page of results from the previous list request. It makes the result of this list request contain only entries that have changed since then. All events deleted since the previous list request will always be in the result set and it is not allowed to set showDeleted to False.
There are several query parameters that cannot be specified together with nextSyncToken to ensure consistency of the client state.

These are: 
- iCalUID 
- orderBy 
- privateExtendedProperty 
- q 
- sharedExtendedProperty 
- timeMin 
- timeMax 
- updatedMin If the syncToken expires, the server will respond with a 410 GONE response code and the client should clear its storage and perform a full synchronization without any syncToken.
Learn more about incremental synchronization.
Optional. The default is to return all entries.

**Type:** string

#### timeMax

Upper bound (exclusive) for an event's start time to filter by. Optional. The default is not to filter by start time. Must be an RFC3339 timestamp with mandatory time zone offset, e.g., 2011-06-03T10:00:00-07:00, 2011-06-03T10:00:00Z. Milliseconds may be provided but will be ignored. If timeMin is set, timeMax must be greater than timeMin.

**Type:** string

#### timeMin

Lower bound (inclusive) for an event's end time to filter by. Optional. The default is not to filter by end time. Must be an RFC3339 timestamp with mandatory time zone offset, e.g., 2011-06-03T10:00:00-07:00, 2011-06-03T10:00:00Z. Milliseconds may be provided but will be ignored. If timeMax is set, timeMin must be smaller than timeMax.

**Type:** string

#### timeZone

Time zone used in the response. Optional. The default is the time zone of the calendar.

**Type:** string

#### updatedMin

Lower bound for an event's last modification time (as a RFC3339 timestamp) to filter by. When specified, entries deleted since this time will always be included regardless of showDeleted. Optional. The default is not to filter by last modification time.

**Type:** string

</details>

## get_calendarlist

Returns entries on the user's calendar list. The CalendarList is a collection of all calendar entries that a user has added to their list (shown in the left panel of the web UI). You can use it to add and remove existing calendars to/from the users’ list. You also use it to retrieve and set the values of user-specific calendar properties, such as default reminders. Another example is foreground color, since different users can have different colors set for the same calendar.

<details><summary>Parameters</summary>

#### minAccessRole

The minimum access role for the user in the returned entries. Optional. The default is no restriction.

**Type:** string

**Potential values:** freeBusyReader, owner, reader, writer

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### showDeleted

Whether to include deleted calendar list entries in the result. Optional. The default is False.

**Type:** boolean

#### showHidden

Whether to show hidden entries. Optional. The default is False.

**Type:** boolean

#### syncToken

Token obtained from the nextSyncToken field returned on the last page of results from the previous list request. It makes the result of this list request contain only entries that have changed since then. If only read-only fields such as calendar properties or ACLs have changed, the entry won't be returned. All entries deleted and hidden since the previous list request will always be in the result set and it is not allowed to set showDeleted neither showHidden to False.
To ensure client state consistency minAccessRole query parameter cannot be specified together with nextSyncToken.
If the syncToken expires, the server will respond with a 410 GONE response code and the client should clear its storage and perform a full synchronization without any syncToken.
Learn more about incremental synchronization.
Optional. The default is to return all entries.

**Type:** string

</details>

## get_calendarlist_entry

Returns an entry on the user's calendar list.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## get_calendars_freebusy

Returns free/busy information for a set of calendars.

<details><summary>Parameters</summary>

#### $body

**Type:** object

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## get_my_settings

Returns all user settings for the authenticated user.

<details><summary>Parameters</summary>

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### syncToken

Token obtained from the nextSyncToken field returned on the last page of results from the previous list request. It makes the result of this list request contain only entries that have changed since then.
If the syncToken expires, the server will respond with a 410 GONE response code and the client should clear its storage and perform a full synchronization without any syncToken.
Learn more about incremental synchronization.
Optional. The default is to return all entries.

**Type:** string

</details>

## get_setting

Returns a single user setting.

<details><summary>Parameters</summary>

#### setting (required)

The id of the user setting.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## import_calendar_event

Imports an event. This operation is used to add a private copy of an existing event to a calendar.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### $body

**Type:** object

#### conferenceDataVersion

Version number of conference data supported by the API client. Version 0 assumes no conference data support and ignores conference data in the event's body. Version 1 enables support for copying of ConferenceData as well as for creating new conferences using the createRequest field of conferenceData. The default is 0.

**Type:** integer

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### supportsAttachments

Whether API client performing operation supports event attachments. Optional. The default is False.

**Type:** boolean

</details>

## move_calendar_event

Moves an event to another calendar, i.e. changes an event's organizer.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier of the source calendar where the event currently is on.

**Type:** string

#### destination (required)

Calendar identifier of the target calendar where the event is to be moved to.

**Type:** string

#### eventId (required)

Event identifier.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### sendNotifications

Deprecated. Use sendUpdates instead

**Type:** boolean

</details>

## quick_add_calendar_event

Creates an event based on a simple text string.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### text (required)

The text describing the event to be created.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### sendNotifications

Deprecated. Use sendUpdates instead

**Type:** boolean

</details>

## stop_channel

Stop watching resources through this channel

<details><summary>Parameters</summary>

#### $body

**Type:** object

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## update_acl_rule

Updates an access control rule with patch semantics.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### ruleId (required)

ACL rule identifier.

**Type:** string

#### $body

**Type:** object

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### sendNotifications

Deprecated. Use sendUpdates instead

**Type:** boolean

</details>

## update_calendar

Updates some metadata for a calendar, using patch semantics.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### $body

**Type:** object

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## update_calendar_event

Updates an event with patch semantics.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### eventId (required)

Event identifier.

**Type:** string

#### $body

**Type:** object

#### alwaysIncludeEmail

Whether to always include a value in the email field for the organizer, creator and attendees, even if no real email is available (i.e. a generated, non-working value will be provided). The use of this option is discouraged and should only be used by clients which cannot handle the absence of an email address value in the mentioned places. Optional. The default is False.

**Type:** boolean

#### conferenceDataVersion

Version number of conference data supported by the API client. Version 0 assumes no conference data support and ignores conference data in the event's body. Version 1 enables support for copying of ConferenceData as well as for creating new conferences using the createRequest field of conferenceData. The default is 0.

**Type:** integer

#### maxAttendees

The maximum number of attendees to include in the response. If there are more than the specified number of attendees, only the participant is returned. Optional.

**Type:** integer

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### sendNotifications

Deprecated. Use sendUpdates instead

**Type:** boolean

#### supportsAttachments

Whether API client performing operation supports event attachments. Optional. The default is False.

**Type:** boolean

</details>

## update_calendarlist_entry

Updates an entry on the user's calendar list, with patch semantics.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### $body

**Type:** object

#### colorRgbFormat

Whether to use the foregroundColor and backgroundColor fields to write the calendar colors (RGB). If this feature is used, the index-based colorId field will be set to the best matching option automatically. Optional. The default is False.

**Type:** boolean

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

</details>

## watch_acl

Watch for changes to ACL resources.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### $body

**Type:** object

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### showDeleted

Whether to include deleted ACLs in the result. Deleted ACLs are represented by role equal to "none". Deleted ACLs will always be included if syncToken is provided. Optional. The default is False.

**Type:** boolean

#### syncToken

Token obtained from the nextSyncToken field returned on the last page of results from the previous list request. It makes the result of this list request contain only entries that have changed since then. All entries deleted since the previous list request will always be in the result set and it is not allowed to set showDeleted to False.
If the syncToken expires, the server will respond with a 410 GONE response code and the client should clear its storage and perform a full synchronization without any syncToken.
Learn more about incremental synchronization.
Optional. The default is to return all entries.

**Type:** string

</details>

## watch_calendar_events

Watch for changes to Events resources.

<details><summary>Parameters</summary>

#### calendarId (required)

Calendar identifier. To retrieve calendar IDs call the get_calendarlist method. If you want to access the primary calendar of the currently logged in user, use the "primary" keyword.

**Type:** string

#### $body

**Type:** object

#### alwaysIncludeEmail

Whether to always include a value in the email field for the organizer, creator and attendees, even if no real email is available (i.e. a generated, non-working value will be provided). The use of this option is discouraged and should only be used by clients which cannot handle the absence of an email address value in the mentioned places. Optional. The default is False.

**Type:** boolean

#### iCalUID

Specifies event ID in the iCalendar format to be included in the response. Optional.

**Type:** string

#### maxAttendees

The maximum number of attendees to include in the response. If there are more than the specified number of attendees, only the participant is returned. Optional.

**Type:** integer

#### orderBy

The order of the events returned in the result. Optional. The default is an unspecified, stable order.

**Type:** string

**Potential values:** startTime, updated

#### privateExtendedProperty

Extended properties constraint specified as propertyName=value. Matches only private properties. This parameter might be repeated multiple times to return events that match all given constraints.

**Type:** array

#### q

Free text search terms to find events that match these terms in any field, except for extended properties. Optional.

**Type:** string

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### sharedExtendedProperty

Extended properties constraint specified as propertyName=value. Matches only shared properties. This parameter might be repeated multiple times to return events that match all given constraints.

**Type:** array

#### showDeleted

Whether to include deleted events (with status equals "cancelled") in the result. Cancelled instances of recurring events (but not the underlying recurring event) will still be included if showDeleted and singleEvents are both False. If showDeleted and singleEvents are both True, only single instances of deleted events (but not the underlying recurring events) are returned. Optional. The default is False.

**Type:** boolean

#### showHiddenInvitations

Whether to include hidden invitations in the result. Optional. The default is False.

**Type:** boolean

#### singleEvents

Whether to expand recurring events into instances and only return single one-off events and instances of recurring events, but not the underlying recurring events themselves. Optional. The default is False.

**Type:** boolean

#### syncToken

Token obtained from the nextSyncToken field returned on the last page of results from the previous list request. It makes the result of this list request contain only entries that have changed since then. All events deleted since the previous list request will always be in the result set and it is not allowed to set showDeleted to False.
There are several query parameters that cannot be specified together with nextSyncToken to ensure consistency of the client state.

These are:
- iCalUID
- orderBy
- privateExtendedProperty
- q
- sharedExtendedProperty
- timeMin
- timeMax
- updatedMin If the syncToken expires, the server will respond with a 410 GONE response code and the client should clear its storage and perform a full synchronization without any syncToken.
Learn more about incremental synchronization.
Optional. The default is to return all entries.

**Type:** string

#### timeMax

Upper bound (exclusive) for an event's start time to filter by. Optional. The default is not to filter by start time. Must be an RFC3339 timestamp with mandatory time zone offset, e.g., 2011-06-03T10:00:00-07:00, 2011-06-03T10:00:00Z. Milliseconds may be provided but will be ignored. If timeMin is set, timeMax must be greater than timeMin.

**Type:** string

#### timeMin

Lower bound (inclusive) for an event's end time to filter by. Optional. The default is not to filter by end time. Must be an RFC3339 timestamp with mandatory time zone offset, e.g., 2011-06-03T10:00:00-07:00, 2011-06-03T10:00:00Z. Milliseconds may be provided but will be ignored. If timeMax is set, timeMin must be smaller than timeMax.

**Type:** string

#### timeZone

Time zone used in the response. Optional. The default is the time zone of the calendar.

**Type:** string

#### updatedMin

Lower bound for an event's last modification time (as a RFC3339 timestamp) to filter by. When specified, entries deleted since this time will always be included regardless of showDeleted. Optional. The default is not to filter by last modification time.

**Type:** string

</details>

## watch_calendarlist

Watch for changes to CalendarList resources.

<details><summary>Parameters</summary>

#### $body

**Type:** object

#### minAccessRole

The minimum access role for the user in the returned entries. Optional. The default is no restriction.

**Type:** string

**Potential values:** freeBusyReader, owner, reader, writer

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### showDeleted

Whether to include deleted calendar list entries in the result. Optional. The default is False.

**Type:** boolean

#### showHidden

Whether to show hidden entries. Optional. The default is False.

**Type:** boolean

#### syncToken

Token obtained from the nextSyncToken field returned on the last page of results from the previous list request. It makes the result of this list request contain only entries that have changed since then. If only read-only fields such as calendar properties or ACLs have changed, the entry won't be returned. All entries deleted and hidden since the previous list request will always be in the result set and it is not allowed to set showDeleted neither showHidden to False.
To ensure client state consistency minAccessRole query parameter cannot be specified together with nextSyncToken.
If the syncToken expires, the server will respond with a 410 GONE response code and the client should clear its storage and perform a full synchronization without any syncToken.
Learn more about incremental synchronization.
Optional. The default is to return all entries.

**Type:** string

</details>

## watch_settings

Watch for changes to Settings resources.

<details><summary>Parameters</summary>

#### $body

**Type:** object

#### quotaUser

An opaque string that represents a user for quota purposes. Must not exceed 40 characters.

**Type:** string

#### syncToken

Token obtained from the nextSyncToken field returned on the last page of results from the previous list request. It makes the result of this list request contain only entries that have changed since then.
If the syncToken expires, the server will respond with a 410 GONE response code and the client should clear its storage and perform a full synchronization without any syncToken.
Learn more about incremental synchronization.
Optional. The default is to return all entries.

**Type:** string

</details>

