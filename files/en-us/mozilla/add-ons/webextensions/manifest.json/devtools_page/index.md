---
title: devtools_page
slug: Mozilla/Add-ons/WebExtensions/manifest.json/devtools_page
page-type: webextension-manifest-key
browser-compat: webextensions.manifest.devtools_page
sidebar: addonsidebar
---

<table class="fullwidth-table standard-table">
  <tbody>
    <tr>
      <th scope="row">Type</th>
      <td><code>String</code></td>
    </tr>
    <tr>
      <th scope="row">Mandatory</th>
      <td>No</td>
    </tr>
    <tr>
      <th scope="row">Manifest version</th>
      <td>2 or higher</td>
    </tr>
    <tr>
      <th scope="row">Example</th>
      <td>
        <pre class="brush: json">"devtools_page": "devtools/my-page.html"</pre>
      </td>
    </tr>
  </tbody>
</table>

Use this key to enable your extension to extend the browser's built-in devtools.

This key is defined as a URL to an HTML file. The HTML file must be bundled with the extension, and the URL is relative to the extension's root.

The use of this manifest key triggers [an install-time permission warning about devtools](https://support.mozilla.org/en-US/kb/permission-request-messages-firefox-extensions#w_extend-developer-tools-to-access-your-data-in-open-tabs). To avoid an install-time permission warning, mark the feature as optional by listing the `"devtools"` permission in the [`optional_permissions`](/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/optional_permissions) manifest key.

See [Extending the developer tools](/en-US/docs/Mozilla/Add-ons/WebExtensions/Extending_the_developer_tools) to learn more.

## Example

```json
"devtools_page": "devtools/my-page.html"
```

## Browser compatibility

{{Compat}}
