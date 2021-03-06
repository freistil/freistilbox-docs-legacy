---
title: Configuration snippets
status: published
zendesk-id: 201084635
tags:
- configuration
---

# Ready-made configuration snippets

In the `current` directory, you'll find a subdirectory named `config` with
CMS-specific configuration snippets. You can include these snippets into your
web application settings to have important services configured automatically.

Using these snippets is easy; you simply integrate them into your website
configuration like this:

```php
require_once('../config/$CMS/$CONF');
```

<span class="label warning">WARNING</span> If you put the includes at the
beginning of your configuration file, their settings can be overridden by
configuration changes coming further below. This can either be useful or
confusing, depending on your approach. We recommend appending the `require_once`
at the end of your configuration file.

## Drupal configuration snippets

Drupal-specific configuration snippets are stored in the directory
`../config/drupal/`. 

Example: `settings.php` for a Drupal 8 site

```php
<?php
...
require_once('../config/drupal/settings-d8-site.php');
require_once('../config/drupal/settings-d8-db123.php');
?>
```

The following configuration files are available:

* `settings-<version>-site.php` -- General website settings, for example Reverse Proxy
  settings.
* `settings-<version>-dbXXX.php` -- Database configuration. Replace "dbXXX" with the
  database name of your site instance. 
* `settings-<version>-memcache.php` -- Memcache configuration.
  See "[How do I enable memcached?](/tech_faq/memcache.html)".

Simply replace `<version>` with a Drupal version shortcut. freistilbox supports
the shortcuts "d6", "d7" and "d8".
