---
title: Open Source Sitemap Generator
categories: SEO
tags: [seo,python,sitemap]
comments: true
share: true

link: http://toncar.cz/opensource/sitemap_gen.html

image:
  feature: abstract-5.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
layout: post
---
> This software is a platform-independent site map generator. It crawls a web site starting from a given URL and outputs XML sitemap file that you can use for Google (via [Google Webmaster Tools](https://www.google.com/webmasters/tools/docs/en/about.html)) or other search engines. Site maps are useful for SEO — you can give the search engine hints about what pages it can index at web your site. The site map generator program is published under GNU General Public License.

J'avais un petit site a indexer, pas grand chose : une dizaine de pages et quelques fichiers pdf. Franchement ecrire un xml fait un peu trop de copier-coller pour moi, mais un petit tour sur google et je trouve ce petit crawler !  
Ne reste plus qu'a faire un petit tour sur la [doc sitemaps](http://www.sitemaps.org/protocol.html) pour ajouter quelques metas, ajuster les priorites et zou.

```
sitemap_gen.py version 1.1.0 (2009-09-05)

This script crawls a web site from a given starting URL and generates
a Sitemap file in the format that is accepted by Google. The crawler
does not follow links to other web sites. It also respects the 'nofollow'
tags and will not crawl into directories disallowed in the robots.txt file.

Command line syntax:

python sitemap_gen.py <options> <starting URL>

Available options:
-h         --help                Print this text and exit

-b <ext>   --block <ext>         Exclude URLs with the given extension;
                                 <ext> must be without the leading dot.
                                 The comparison is case insensitive, so
                                 for example DOC and doc are treated
                                 the same. You can use this option several
                                 times to block several extensions.

-c <value> --changefreq <value>  Set the change frequency. The given value
                                 is used in all sitemap entries (maybe a
                                 future version of this script will change
                                 that). The allowed values are: always,
                                 hourly, daily, weekly, monthly, yearly,
                                 never.

-p <prio>  --priority <prio>     Set the priority. The value must be from
                                 the interval between 0.0 and 1.0. The value
                                 will be used in all sitemap entries.

-m <value> --max-urls <value>    Set the maximum number of URLs to be crawled.
                                 The default value is 1000 and the largest
                                 value that you can set is 50000 (the script
                                 generates only a single sitemap file).

-o <file>  --output-file <file>  Set the name of the geneated sitemap file.
                                 The default file name is sitemap.xml.

Usage example:
python sitemap_gen.py -b doc -b bmp -o test_sitemap.xml http://www.your-site-name.com/index.html

For more information, visit http://toncar.cz/opensource/sitemap_gen.html
```
