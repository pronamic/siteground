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

## Run WP-CLI via specific PHP version

Currently, WP-CLI at SiteGround still runs via PHP 7.4, regardless of which PHP version you set via the SiteTools.
Through SiteGround support we learned that WP-CLI can also be run via other PHP versions:

```
php56 /usr/local/bin/wp-cli.phar
```

```
php70 /usr/local/bin/wp-cli.phar
```

```
php71 /usr/local/bin/wp-cli.phar
```

```
php72 /usr/local/bin/wp-cli.phar
```

```
php73 /usr/local/bin/wp-cli.phar
```

```
php74 /usr/local/bin/wp-cli.phar
```

```
php80 /usr/local/bin/wp-cli.phar
```

```
php81 /usr/local/bin/wp-cli.phar
```

```
php82 /usr/local/bin/wp-cli.phar
```

```
php83 /usr/local/bin/wp-cli.phar
```

Via the `--info` parameter you can view the PHP version that WP-CLI uses:

```
/usr/local/bin/wp-cli.phar --info
OS:	Linux ams44.siteground.eu 5.15.126-MCIclouder399 #399 SMP PREEMPT Wed Aug 16 16:53:17 EEST 2023 x86_64
Shell:	/bin/bash
PHP binary:	/usr/local/php56/bin/php-cli
PHP version:	5.6.40
php.ini used:	/usr/local/php56/lib/php.ini
```
