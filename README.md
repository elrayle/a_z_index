Jekyll Plugin: a-z.md Generator
====================================

a-z.md Generator is a Jekyll plugin that generates an a-z.md index file by traversing all of the available posts and pages.

How To Use:
-----------
1. Copy file into your _plugins folder within your Jekyll project.
2. Ensure url is set in your config file (for example `url: http://danielgroves.net`)
3. In your config file, change `a-z: filename:` if you want your a-z index to be called something other than a-z.md.
4. Change the `a-z: exclude:` list to exclude any pages that you don't want in the a-z index. 
5. Change the `a-z: include_posts:` list to include any pages that are looping through your posts (e.g. "/index.html", "/notebook/index.md", etc.). This will ensure that right after you make a new post, the last modified date will be updated to reflect the new post.
6. Run Jekyll: `jekyll build` to re-generate your site.
7. An `a-z.md` should be included in your _site folder.

Configuration defaults:

```yaml
a-z:
    filename: "/a-z.md"
    exclude:
        - "/atom.xml"
        - "/feed.xml"
        - "/feed/index.xml"
    include_posts:
        - "/index.html"
    index_title: false
```

Customizations:
---------------
If you want to include the optional changefreq and priority attributes, simply include custom variables in the YAML Front Matter of those files. The names of these custom variables are defined in the config file as `a-z: change_frequency_name:` and `a-z: priority_name:`.

Notes:
------
1. The last modified date is determined by the latest date of the following: system modified date of the page or post, system modified date of included layout, system modified date of included layout within that layout, ...

Author: E. Lynette Rayle

Acknowlegements
---------------
Thanks to the developers of the sitemap plugin which was used as the base code for the a-z plugin.
Sitemap Author: Michael Levin ([http://www.kinnetica.com](http://www.kinnetica.com))
Sitemap Configuration Update: Daniel Groves ([http://danielgroves.net](http://danielgroves.net))

Distributed Under A [Creative Commons](http://creativecommons.org/licenses/by/3.0/) License
