﻿---
title: Inedo SDK Versions & Release notes
subtitle: Inedo SDK Versions & Release notes
sequence: 40
keywords: inedo, inedo sdk, versions, release notes
show-headings-in-nav: true
---

The Inedo SDK is used to build extensions to Inedo's core products (BuildMaster, ProGet, Hedgehog, Otter) that implement core capabilities or add functionality. As new features are introduced into the core products, new components will be added to the SDK.

To keep track of which version of the SDK is compatible with which version of each product:

{.docs}
- the Inedo SDK is independently versioned using a three-part version number
- extensions are built against a specific version the Inedo SDK
- each product version specifies a *version compatibility range* that determines which versions of the Inedo SDK extensions can be built against

This [version compatibility range](#compatibility-ranges) effectively establishes a *minimum product version* that each version of the SDK will work with.

:::attention {.best-practice}
![](/resources/images/icons/best-practices.png)

Best practice: When building extensions, target the lowest version possible. This will ensure widest compatibility of your extension.
:::

## Version Compatibility Ranges {#compatibility-ranges data-title="Version Compatibility Ranges"}

The below table shows which version of the Inedo SDK is compatible with which version of each product.

SDK Version           | Minimum Product Version
----------------------|----------------------------
**1.0.4**             | BuildMaster 6.0+<br/>ProGet 5.0+<br/>Hedgehog 1.0+<br/>Otter 2.0+
**1.0.7**             | Otter 2.1+

The table will be expanded as new SDK versions are released.

Note that new maintenance versions (such as 1.0.2) will displace versions in the same minor line (such as 1.0.0 and 1.0.1), These displaced versions will be unlisted from NuGet.org, and should not be targeted.

### Understanding Version Compatibility Ranges {#understanding data-title="Understanding Version Compatibility Ranges"}

The version compatibility range is generally specified as a one-part version number followed by a two-part version number, such as "1 to 1.4".  That means extensions targeting all versions of the Inedo SDK between 1.0.0 and 1.4.x will load, but an extension targeting Inedo SDK 1.5.0 or greater would not load.

Version Compatibility Ranges are "hard coded" in each product which means that, once a product version ships, the range cannot be changed. This can get a bit inconvenient when extensions are designed to work with multiple products with different ranges.

For example, let's say you have an extension with various components that are shared across your ProGet, Otter, and Hedgehog installations. If a new version of ProGet were to come out that introduces a new feature you wanted to extend, you would need to target a newer version of the Inedo SDK to access that new component. This would then mean you would have to upgrade Otter and Hedgehog (both which, presumably would be compatible with the new Inedo SDK), just so that extension can load.

To work around this, you can override the version number used for compatibility verification with the [ProductVersionCompatibilityAttribute](/support/sdk-reference/inedosdk/Inedo.Extensibility/ProductVersionCompatibilityAttribute).   
