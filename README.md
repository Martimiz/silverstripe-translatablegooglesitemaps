# TranslatableGoogleSitemap module for SilverStripe CMS #

**Note:** 
This module is considered beta: working, but not thorougly tested. 
Comments/issues welcome!

## Introduction ##

Provide multilanguage support in GoogleSitemaps, including alternatives, for
sites using the Translatable module. It follows the Google requiremnts explained here:

[Sitemaps: rel="alternate" hreflang="x"](https://support.google.com/webmasters/answer/2620865?hl=en&ref_topic=2370587)

## Usage

Copy to your Website root, using any name you want, then do a ?flush=1 to
renew your YAML files and templates (If the proper template doesn't seem to be 
used, try a flush=1 on sitemap.xml as well).

## Locales

by default the pages' `Locale` property ('en_US', 'nl_NL') will be used to generate the alternatives 
for each page in the sitemap. You can define some locales as generic for a given language, so that for instance `en` is presented to english spoken users, instead of `en_US`.
  
In your _config/translatablegooglesitemaps.yml: 

    ---
    Name: translatablegooglesitemaps
    ---
    TranslatableGoogleSitemap:
      generic_locales:
        en_US: en
        nl_NL: nl

## Sitemap size ##
By default in GoogleSitemaps, the max number of pages in a single sitemap is set to 1000. Since the language alternatives for translated pages add substantially to the sitemap source, you might want to turn that down a bit for large sites:

In your GoogleSitemaps module, in _config/googlesitemaps.yml:

    ---
    Name: googlesitemaps
    ---
      ...
      objects_per_sitemap: 1000
  

## Requirements ##

 * SilverStripe Framework 3.0+ and CMS 3.0+
 * SilverStripe Translatable module
 * Silverstripe GoogleSitemaps module
 
 **Note:** works with the SilverStripe LanguagePrefix module

## Maintainers ##

 * Martine Bloem (Martimiz) <martimiz@gmail.com>

Please report any bugs or issues you may find