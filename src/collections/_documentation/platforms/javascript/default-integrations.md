---
title: Default Integrations
sidebar_order: 10
---

System integrations are integrations enabled by default that integrate into the
standard library or the interpreter itself. Sentry documents them so you can see
what they do and that they can be disabled if they cause issues. To disable
system integrations set `defaultIntegrations: false` when calling `init()`.
To override their settings, provide a new instance with your config
to `integrations` option, for example, to turn off browser capturing console calls
`integrations: [new Sentry.Integrations.Breadcrumbs({ console: false })]`.

## Core

### Dedupe

_Import name: `Sentry.Integrations.Dedupe`_

This integration deduplicates certain events. The Sentry JavaScript SDK enables this by default, and it should not be disabled except in rare circumstances. Disabling this integration, for instance, will cause duplicate error logging.

### InboundFilters

_Import name: `Sentry.Integrations.InboundFilter`_

This integration allows developers to ignore specific errors based on the type or message. It also allows the ability to blacklist/whitelist URLs from which an exception originates.

To configure it, use `ignoreErrors`, `blacklistUrls`, and `whitelistUrls` SDK options directly.

### FunctionToString

_Import name: `Sentry.Integrations.FunctionToString`_

This integration allows the Sentry JavaScript SDK to provide original functions and method names, even when the Sentry error and breadcrumbs handlers wrap the function and method names.


### ExtraErrorData

_Import name: `Sentry.Integrations.ExtraErrorData`_

This integration extracts all non-native attributes from the Error object and attaches them to the event as the `extra` data.

## Browser specific

### TryCatch

_Import name: `Sentry.Integrations.TryCatch`_

This integration wraps native time and events APIs (`setTimeout`, `setInterval`, `requestAnimationFrame`, `addEventListener/removeEventListener`) in `try/catch` blocks to handle async exceptions.

### Breadcrumbs

_Import name: `Sentry.Integrations.Breadcrumbs`_

This integration wraps native APIs to capture breadcrumbs. By default, the Sentry JavaScript SDK wraps all APIs.

Available options:

```js
{
  beacon: boolean;  // Log HTTP requests done with the Beacon API
  console: boolean; // Log calls to `console.log`, `console.debug`, etc
  dom: boolean;     // Log all click and keypress events
  fetch: boolean;   // Log HTTP requests done with the Fetch API
  history: boolean; // Log calls to `history.pushState` and friends
  sentry: boolean;  // Log whenever we send an event to the server
  xhr: boolean;     // Log HTTP requests done with the XHR API
}
```

### GlobalHandlers

_Import name: `Sentry.Integrations.GlobalHandlers`_

This integration attaches global handlers to capture uncaught exceptions and unhandled rejections.

Available options:

```js
{
  onerror: boolean;
  onunhandledrejection: boolean;
}
```

### LinkedErrors

_Import name: `Sentry.Integrations.LinkedErrors`_

This integration allows you to configure linked errors. They'll be recursively read up to a specified limit and lookup will be performed by a specific key. By default, the Sentry JavaScript SDK sets the limit to 5 and the key used is `cause`.

Available options:

```js
{
  key: string;
  limit: number;
}
```

### UserAgent

_Import name: `Sentry.Integrations.UserAgent`_

This integration attaches user-agent information to the event, which allows us to correctly catalog and tag them with specific OS, Browser and version information.
