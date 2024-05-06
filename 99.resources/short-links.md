---
title: "Short Links"
---

## Introduction

All links that MikroCloud may embed in emails or notifications are signed with a signature to ensure that the link is
not tampered with. This signature is verified when the user clicks on the link.
Because of this, links are long and challenging to read. To make the links more user-friendly, MikroCloud uses a URL
shortening service to create short links that redirect to the long links.

## Short Link Format

MikroCloud owns the domain `mkcld.link` for creating short links.
The format of a short link is as follows:

```
https://mkcld.link/{short-code}
```

The short code is a unique identifier generated for each long link. The short code is used to look up the long link in
the MikroCloud database and redirect the user to the long link.

## Short Link Rate Limits

The upper limit when accessing short links is 60 requests per minute, per IP address. This limit is enforced on the
Short Link service.
Despite this limit, the target link will often have its own rate limits, which may be lower than the Short Link service
rate limit.

## Short Link Expiry

The Short Link service does not expire short links. The lifetime of a short link is the same as the lifetime of the long
link it redirects to.
