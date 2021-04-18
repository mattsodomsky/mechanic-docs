# Code

A task's code is a Liquid template.

In the same way that a Shopify storefront might use a Liquid template to receive requests and render HTML, a task uses its Liquid code to receive events, and render a series of JSON objects. These JSON objects define [**actions**](action-objects.md), [**logs**](logging.md), and [**errors**](error-objects.md). \(The work defined by these JSON objects does not begin until after the task has fully completed its rendering.\)

Task code always has access to a set of [**environment variables**](environment-variables.md), which can be used to make decisions about what JSON objects to render.

A task must purposefully consider its [**preview**](../previews/), so as to accurately communicate its intent to users and to the Mechanic platform.
