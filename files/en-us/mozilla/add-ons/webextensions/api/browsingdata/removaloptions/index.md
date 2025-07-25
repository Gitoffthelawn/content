---
title: browsingData.RemovalOptions
slug: Mozilla/Add-ons/WebExtensions/API/browsingData/RemovalOptions
page-type: webextension-api-type
browser-compat: webextensions.api.browsingData.RemovalOptions
sidebar: addonsidebar
---

The **`browsingData.RemovalOptions`** type contains options to control certain aspects of browsing data removal.

## Type

Values of this type are objects. They contain the following properties:

- `cookieStoreId` {{optional_inline}}
  - : `string`. This property only applies to cookies and indexedDB items. The removal is limited to items belonging to a specific [cookie store](/en-US/docs/Mozilla/Add-ons/WebExtensions/API/cookies/CookieStore) as specified by the ID. See [Work with contextual identities](/en-US/docs/Mozilla/Add-ons/WebExtensions/Work_with_contextual_identities) for more information.

    > [!NOTE]
    > On Firefox Nightly removal of localStorage items by `cookieStoreId` is also supported.

- `excludeOrigin` {{optional_inline}}
  - : `array` of `string`. List of origins to exclude from the removal process. Can't be used together with `origins`. Only supported for cookies, storage, and cache. Cookies are excluded for the entire registrable domain.

- `hostnames` {{optional_inline}}
  - : `array` of `string`. This property applies to cookie, indexedDB, local storage, and service worker registration items. Remove only cookie, indexedDB, local storage, and service worker registration items associated with these hostnames.

    You must pass in just a hostname here, without protocol (for example, `"google.com"` not `"https://google.com"`). You can use the [`URL`](/en-US/docs/Web/API/URL) interface to parse a raw URL and retrieve the hostname. Items associated with subdomains of a given hostname are _not_ removed: you must explicitly list subdomains.

- `origin` {{optional_inline}}
  - : `array` of `string`. List of origins to remove data for. Can't be used together with `excludeOrigins`. Only supported for cookies, storage, and cache. Cookies are cleared for the entire registrable domain.

- `originTypes` {{optional_inline}}
  - : `object`. Used to control whether to remove data only from normal web pages, or also from hosted web apps and extensions. If this option is omitted, only data from normal web pages (`unprotectedWeb`) is removed. Before removing data from web apps or extensions, be very careful to ensure that this is really what the user wants.

    This object may contain any of the following properties:
    - `unprotectedWeb` {{optional_inline}}
      - : `boolean`. If present and `true`, remove data from normal web pages.
    - `protectedWeb` {{optional_inline}}
      - : `boolean`. If present and `true`, remove data from websites that have been installed as hosted apps.
    - `extension` {{optional_inline}}
      - : `boolean`. If present and `true`, remove data from extensions.

- `since` {{optional_inline}}
  - : `number`. How far back in time to remove data, given in [milliseconds since the UNIX epoch](https://en.wikipedia.org/wiki/Unix_time). Note that when removing the browser cache, the entire cache is always removed and this option is ignored. If the `since` property is omitted, it defaults to 0, which means "forever".

## Browser compatibility

{{Compat}}

> [!NOTE]
> This API is based on Chromium's [`chrome.browsingData`](https://developer.chrome.com/docs/extensions/reference/api/browsingData) API.

<!--
// Copyright 2015 The Chromium Authors. All rights reserved.
//
// Redistribution and use in source and binary forms, with or without
// modification, are permitted provided that the following conditions are
// met:
//
//    * Redistributions of source code must retain the above copyright
// notice, this list of conditions and the following disclaimer.
//    * Redistributions in binary form must reproduce the above
// copyright notice, this list of conditions and the following disclaimer
// in the documentation and/or other materials provided with the
// distribution.
//    * Neither the name of Google Inc. nor the names of its
// contributors may be used to endorse or promote products derived from
// this software without specific prior written permission.
//
// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
// "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
// LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
// A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
// OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
// SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
// LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
// DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
// THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
// (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
// OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
-->
