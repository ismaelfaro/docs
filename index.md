---
layout: default
---

## Welcome

<p class="lead">
{{site.project_title}} is a new type of library for the web, built on top of Web Components,
and designed to leverage the evolving web platform on modern browsers.
</p>

The {{site.project_title}} project comprises two primary efforts:

- A set of core platform features, including [Shadow DOM](/platform/shadow-dom-shim.html),
[Custom Elements](/platform/custom-elements.html) and [Model Driven Views](/platform/mdv.html).
Initially, these core features will be enabled with a set of polyfills and shims.
- next-generation web application framework built upon these core technologies called the **_Toolkit_**.
</ul>

As browsers begin to implement these features natively, this polyfill platform
layer will become smaller and smaller.

<figure id="architecture-diagram">
  <!-- <img src="/images/architecture-diagram.svg" alt="Architecture Diagram" titld="Architecture Diagram"> -->
  <iframe src="/images/architecture-diagram.svg" seamless></iframe>
  <figcaption>Architectural Diagram</figcaption>
</figure>

## Guiding principles

The overall aim of the toolkit is to manage complexity. It does this through two main principles:

**Everything is a component** — Encapsulation is the key to creating scalable, maintainable applications. All Toolkit resources are components, even ones that are non-visual. To construct an app, a developer creates new components, or uses ones the Toolkit provides, and assembles them together. Focusing on individual, composable building blocks allows developers to "think locally" about their application, reducing complexity. With this divide-and-conquer approach, applications can simultaneously be simple and arbitrarily complicated.

**Extreme pragmatism** — Developers should write the **minimum** amount of code possible to create their application. Anything repetitive should be re-factored into a component, handled by the Toolkit itself, or added into the browser platform itself. The Toolkit provides simple syntax without reducing features, and avoids boilerplate wherever possible.

### Component scripts

Toolkit platform shims the <a href="https://dvcs.w3.org/hg/webcomponents/raw-file/tip/explainer/index.html#external-custom-elements-and-decorators">Custom DOM Element Loader</a> . In order for component code to be debuggable at run-time, scripts embedded in components are injected into <code>&lt;head&gt;</code> in the main document. Tools that support <a href="http://www.html5rocks.com/en/tutorials/developertools/sourcemaps/">source maps</a> (such as <a href="https://www.google.com/intl/en/chrome/browser/canary.html">Chrome Canary</a>) will identify these scripts as belonging to their source components.

### Toolkit and g-component

All Toolkit components depend on `src/g-component.html` which provides the [sugaring layer](/toolkit-kernel-explainer.html). However, an application can load `platform.js` and take advantage of the Custom Element and Shadow DOM support directly. For examples of this, see the [/toolkitchen/projects/CustomElementPlayground/](https://github.com/toolkitchen/projects/tree/master/CustomElementsPlayground) folder for examples.
