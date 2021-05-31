---
title: "How to Config Netlify Custom Domain in Route53"
date: 2021-05-31T07:59:38+08:00
tags:
  - Howtos
  - Netlify
  - Route53
---
You can config Netlify custom domain
in **two** simple steps.

# Step 1 - Config Custom Domain in Netlify
Select your site in Netlify and
enter your custom domain.
Go to

```txt
(Your site) > Site settings > Domain management > Add custom domain > Enter whs.hk > Verify
```

![Netlify custom domains](/netlify-custom-domains.png)

# Step 2 - Config DNS Records in Route53
Create two DNS records in AWS Route53, one for root domain and another for prefix `www.`
as table below

| Record name | Record type | Value |
|---|---|---|
| `whs.hk` | A | [`75.2.60.5`][1] |
| `www.whs.hk` | CNAME | `naughty-newton-7aceed.netlify.app.` |

![Route53](/route53.png)

# See Also
- [Configure an apex domain][1]

[1]: https://docs.netlify.com/domains-https/custom-domains/configure-external-dns/#configure-an-apex-domain
