---
title: Pluggable Integrations
sidebar_order: 11
---

Pluggable integrations are integrations that can be additionally enabled, to provide some very specific features. Sentry documents them so you can see what they do and that they can be enabled. To enable pluggable integrations, provide a new instance with your config to `integrations` option, for example, `integrations: [new Sentry.Integrations.ReportingObserver()]`.


## Core

### Debug

_Import name: `Sentry.Integrations.Debug`_

This integration allows you to inspect the content of the processed event,
that will be passed to `beforeSend` and effectively send to Sentry.

Available options:

```js
{
  debugger: boolean; // trigger DevTools debugger instead of using console.log
  stringify: boolean; // stringify event before passing it to console.log
}
```

### RewriteFrames

_Import name: `Sentry.Integrations.RewriteFrames`_

This integration allows you to apply a transformation to each frame of the stack trace.
In the simple scenario, it can be used to change the name of the file frame it originates from, or it can be fed with an iterated function, to apply any arbitrary transformation.

Available options:

```js
{
  root: string; // root path that will be appended to the basename of the current frame's URL
  iteratee: (frame) => frame); // function that takes the frame, applys any transformation on it and returns it back
}
```

## Browser specific

### ReportingObserver

_Import name: `Sentry.Integrations.ReportingObserver`_

This integration hooks into ReportingObserver API and sends captured events through to Sentry.
Can be configured to handle only specific issue types.

Available options:

```js
{
  types: <'crash'|'deprecation'|'intervention'>[];
}
```