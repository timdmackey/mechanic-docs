# Introduction

{% embed url="https://www.youtube.com/watch?v=QitSqzfBovg" caption="" %}

I'm glad you're here. :\) I'm Isaac, and I built Mechanic. My intent is to make Shopify better for everyone. We do this, here, in two parts: \(1\) by making it as easy as possible for developers to solve merchant problems, and \(2\) by making it as easy as possible to use \(and re-use\) those solutions. Mechanic is very, very good at both.

Mechanic is a powerful platform, and I made it to empower everyone who uses it. You are invited. :\)

{% hint style="info" %}
Got a question you need answered now? [Join our Slack workspace.](https://join.slack.com/t/usemechanic/shared_invite/zt-cq84nrs7-ggYbYTbf~CrCjTg8nmHP2A) 💬
{% endhint %}

## What is Mechanic?

Mechanic is an automation and development platform, for Shopify. :\) Mechanic is a replacement for custom apps, allowing developers to solve a similar set of problems without having to host the infrastructure, or think about scaffolding. Developers can get more projects completed faster and more sustainably, by leveraging Mechanic's toolkit.

Mechanic is accompanied by an open-source library, with 280+ automation tasks ready to pull off the shelf, offering an accessible starting point for developers of all skill levels.

As a project of Lightward Inc, Mechanic is offered under a pay-what-feels-good pricing policy. Learn more about this at [lightward.com/pricing](https://lightward.com/pricing).

## How Mechanic works

### Tasks, events, and actions

A developer writes [**tasks**](core-concepts/tasks/) – Mechanic's term for a piece of automation. These tasks can respond to many different [**events**](core-concepts/events/), like a Shopify webhook, a manual trigger, a regular interval \(e.g. hourly, daily\), or an incoming email.

When a task responds to an incoming event, it can choose to generate an [**action**](core-concepts/actions/) – an operation that has an effect.

* The [Shopify](platform/events/topics/shopify.md) action makes changes to a Shopify store, like tagging, publishing, creating or deleting resource. It provides direct and complete access to Shopify's admin API, with support for both REST and GraphQL.
* The [Email](core-concepts/actions/action-types/email.md) action action is for sending email. It supports custom templates, and attachments.
* The [FTP](core-concepts/actions/action-types/ftp.md) action is for uploading files to an FTP or SFTP server. These files may be generated by the task, or can be fetched from external locations.
* The [HTTP](core-concepts/actions/action-types/http.md) action performs any request, to any HTTP endpoint. This facilitates integration with third-party APIs.
* The [Files](core-concepts/actions/action-types/files.md) action generates a variety of file formats, including PDF, CSV, ZIP, and anything retrieved from a public URL. Files generated this way receive a temporary URL of their own, and can be fed into other tasks for further processing.

### Liquid

Mechanic makes heavy use of [**Liquid**](platform/liquid/basics/) – a template language created by Shopify. Its primary use is in [**task code**](core-concepts/tasks/code/). In the same way that a Liquid theme receives browser requests and renders HTML, Mechanic tasks receive events, and render actions \(defined using JSON\).

[**Mechanic-flavored Liquid**]() includes additional support for constructing arrays and hashes, and includes many useful filters, making data processing more efficient.

### Run queues

Mechanic performs work using queues, with no limit on how large each queue can become. If there is a sudden surge of incoming events for a Shopify store, the store's dedicated Mechanic queue could become delayed. This is an important difference between Mechanic and many other systems: in a high-traffic period, Mechanic will never refuse incoming events for a store; instead, it will process each one as soon as possible, by putting them into a run queue.

