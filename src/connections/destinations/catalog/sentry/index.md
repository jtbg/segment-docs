---
rewrite: true
title: Sentry Destination
id: 54521fda25e721e32a72eef0
---
[Sentry](https://sentry.io) is open-source error tracking that helps developers monitor and fix crashes in real time. Iterate continuously. Boost efficiency. Improve user experience. The `analytics.js` Sentry Destination is open-source. You can browse the code [on GitHub](https://github.com/segmentio/analytics.js-integrations/tree/master/integrations/sentry).

## Getting Started

{% include content/connection-modes.md %}

1. From the Segment web app, click **Catalog**.
2. Search for "Sentry" in the Catalog, select it, and choose which of your sources to connect the destination to.
3. In the destination settings, enter your "Public DSN".
4. Segment automatically initializes Sentry with your "Public DSN" upon loading analytics.js.
5. Sentry will automatically start tracking errors in your app's JavaScript.

## Identify

If you're not familiar with the Segment Specs, take a look to understand what the [Identify method](/docs/connections/spec/identify/) does. An example call would look like:

```javascript
analytics.identify('userId123');
```

When you call `identify` we call `Sentry.setUser` by passing in the `traits` you provided. We will map the `userId` you provide as `traits.id`.

## Troubleshoot Sentry

Since Sentry is an error tracking application, Segment needs to send something broken from the website to see the event appear in the Sentry dashboard. For example, firing the following error event from the web console, `Sentry.captureException(new Error("Some error"))`; Segment can see the relevant event payload with the `event_id` information.
 
 ![image](https://user-images.githubusercontent.com/96406241/226262825-d038a0c6-acbc-4b20-87bb-558c622a2be5.png)
 
 This error will appear in Sentry with the same event_id we saw on the web console. This helps verify that we have the correct implementation of the destination.


