---
title: Speculation-Rules header
short-title: Speculation-Rules
slug: Web/HTTP/Reference/Headers/Speculation-Rules
page-type: http-header
status:
  - experimental
browser-compat: http.headers.Speculation-Rules
sidebar: http
---

{{SeeCompatTable}}

The HTTP **`Speculation-Rules`** {{Glossary("response header")}} provides one or more URLs pointing to text resources containing speculation rule JSON definitions. When the response is an HTML document, these rules will be added to the document's speculation rule set. See the [Speculation Rules API](/en-US/docs/Web/API/Speculation_Rules_API) for more information.

The resource file containing the speculation rules JSON can have any valid name and extension, but it will be requested with a [`destination`](/en-US/docs/Web/API/Request/destination) type of [`speculationrules`](/en-US/docs/Web/API/Request/destination#speculationrules), and must be served with an `application/speculationrules+json` MIME type.

> [!NOTE]
> This mechanism provides an alternative to specifying the JSON definition inside an inline [`<script type="speculationrules">`](/en-US/docs/Web/HTML/Reference/Elements/script/type/speculationrules) element. Specifying an HTTP header is useful in cases where developers are not able to directly modify the document itself.

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Header type</th>
      <td>{{Glossary("Response header")}}</td>
    </tr>
    <tr>
      <th scope="row">{{Glossary("Forbidden request header")}}</th>
      <td>No</td>
    </tr>
  </tbody>
</table>

## Syntax

```http
Speculation-Rules: <url-list>
```

## Directives

- `<url-list>`
  - : A comma-separated list of URLs pointing to text resources containing speculation rule JSON definitions. The JSON contained in the text files must follow the same rules as that contained inside inline `<script type="speculationrules">` elements. See [Speculation rules JSON representation](/en-US/docs/Web/HTML/Reference/Elements/script/type/speculationrules#speculation_rules_json_representation) for the syntax reference.

## Examples

### Speculation-Rules field with a single file

The following response contains one file reference:

```http
Speculation-Rules: "/rules/prefetch.json"
```

### Speculation-Rules field with multiple files

The following response contains multiple file reference as a comma-separated list:

```http
Speculation-Rules: "/rules/prefetch.json","/rules/prerender.json"
```

> [!NOTE]
> The URL values must be contained in quotes.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Speculation Rules API](/en-US/docs/Web/API/Speculation_Rules_API)
- [`<script type="speculationrules">`](/en-US/docs/Web/HTML/Reference/Elements/script/type/speculationrules)
