---
id: faq
title: FAQ
---

Below we've covered common questions and technical scenarios you might encounter while building with Transposit. If there is a question you have that isn't covered here or elsewhere in our documentation, reach out for help by emailing us at [support@transposit.com](mailto:support@transposit.com).

## What applications should use Transposit?

* Anything that connects with multiple data sources and APIs
* Bots and utilities for interacting with/integrating multiple applications
* Automating custom workflows as applications
  * Not just event-based&mdash;on-demand (calling out to other sources of data)
  * standalone
* Applications that require access management (eg, to business data)
  * Useful in big organizations
  * Sharing data with customers or partners
  * With security concerns
* Aggregating data from multiple sources into a custom interfaces that also allow you to modify data in the source applications.

## How is Transposit different from Zapier/IFTTT/Workato/etc.?

* Applications, not workflows
* No wiki required
* Error-proof, share, and customize your presentation

## Automatic pagination

It is common for APIs that return a long list of results to paginate those results, often relying on the caller to keep track of a cursor or page number. Transposit takes care of iterating through these paginated APIs for you and returns a single list of all of the results.

Paginated operations are denoted by a green "paginated" tag in the documentation for the data connection.

> Transposit will continue paginating such APIs until it reaches the `limit` specified in your query, or the API has no more results. For this reason, it is important to always provide a `limit` when using a paginated operation.

## Licensing applications

You may want to include a LICENSE file with your application because Transposit users who can view your application can also create a fork of your application. This is especially true of public applications that all Transposit users can view.

To add a LICENSE to your application:

* Clone your application's git repository
* Add a LICENSE file in the root directory of your git repository
* Commit and push the LICENSE back upstream to Transposit

Henceforth, all forks of your application will include your LICENSE file.

## Hosted apps require third-party cookies

To use a hosted app, you must enable third-party cookies in your browser. Third-party cookies are enabled by default in Chrome, Firefox and Edge. Third-party cookies are disabled by default in Safari. To enable third-party cookies in Safari, navigate to **Preferences** > **Privacy** and uncheck **Prevent cross-site tracking**.