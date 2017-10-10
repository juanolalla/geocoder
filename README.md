
Geocoder
========

Geocoder is a Backdrop module that will extract geographical data (geocode) from just about anything you throw at it such as addresses, GPX files, Geotags from EXIF data in photos, and KML files.

Geocoder uses the external geocoding services from Google, Yahoo and Yandex.

Geocoder has been ported to Backdrop from Drupal 7 (https://www.drupal.org/project/geocoder). Here you will find more documentation: http://drupal.org/node/1355780.
Geocoder also provides integration with the Drupal Geofield module, although it has not been ported to Backdrop yet.

Installation
------------

- Install this module using the official Backdrop CMS instructions at https://backdropcms.org/guide/modules

- Install and enable the Geocoder its required module geoPHP (https://backdropcms.org/project/geophp).

- Assign the necessary permissions at /admin/config/people/permissions#module-geocoder.

- Configure the desired settings at /admin/config/content/geocoder.

Geocoder API
------------

Geocoder provides a nice general API for doing geocoding. Here's an example:

```php
// Geocode an address
$address = '4925 Gair Ave, Terrace, BC';
$point = geocoder('google',$address);
$geoJSON = $point->out('json');
```
```php
// List all available handlers
$handlers = geocoder_handler_info();
dpm($handlers);
```

New geocoder handlers as easy to define. Simply create a new plugin file in the folder: plugins/geocoder_handler.

License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for complete text.

Current Maintainers
-------------------

- Juan Olalla (https://github.com/juanolalla)
- Seeking additional maintainers.

Credits
-------

- Originally written for Drupal by cspiker, phayes, henryblyth, jeff h, Les Lim, mikeytown2, fago, patrickavella & michaelfavia
- Ported to Backdrop CMS by Juan Olalla (https://github.com/juanolalla)
