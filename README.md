# Pronamic ↔️ SiteGround

In this repository we keep track of the collaboration between Pronamic and SiteGround.

## CLI `site-tools-client`

### List all domains

```
site-tools-client -j domain-all list
```

### Disable SiteGround dynamic cache for specific domain

```
site-tools-client -j domain update id=1 settings.dynamic_cache=0
```

## Disable SiteGround captcha

SiteGround support staff can disable the anti-bot AI captcha for you, using the following command:

```
sc api do example.com domain-all update settings.protect_captcha_auto=0
```

We had hoped that we could do this ourselves with `site-tools-client`, unfortunately this does not work:

```
site-tools-client -j domain update id=1 settings.protect_captcha_auto=0
```
