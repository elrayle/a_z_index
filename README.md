Jekyll Plugin: a-z.md Generator
====================================

a-z.md Generator is a Jekyll plugin that generates an a-z.md index file by traversing all of the available posts and pages.

How To Use:
-----------
1. Copy file into your _plugins folder within your Jekyll project.
2. Ensure url is set in your config file (for example `url: http://example.io.github`)
3. In your config file, change `a-z: filename:` **IF** you want your a-z index to be called something other than a-z.md.
4. Change the `a-z: exclude:` list to exclude any pages that you don't want in the a-z index. 
5. Change the `a-z: include_posts:` list to include any pages that are looping through your posts (e.g. "/index.html", "/notebook/index.md", etc.). This will ensure that right after you make a new post, the last modified date will be updated to reflect the new post.
6. Run Jekyll: `jekyll build` to re-generate your site.
7. An `a-z.md` should be included in your _site folder.

Configuration defaults:

```yaml
a-z:
    filename: '/a-z.html'
    relative_path: ''
    alternate_dest: site.dest
    exclude:
        - '/atom.xml'
        - '/feed.xml'
        - '/feed/index.xml'
        - '/a-z.html'
        - '/a-z.md'
    include_posts:
        - '/index.html'
    index_titles: false
    front_matter_ext : []
```
where,
* **filename** [String] - The name of the file that will hold the a-z index (e.g. `'/a-z.md'`)  This filename should have extension `.html` or `.md`.  Any other extension, and the output type will default to `html`.
* **relative_path** [String] - Path to prepend to page names (e.g. `'/my/path'`)  This is the path portion of the URL (e.g. `http://example.io.github/my/path/a_page_on_my_site.html`)
* **alternate_dest** [String] - By default, the generated file goes into _site.  You may want to generate elsewhere (e.g. `'/generated'`).  It is not recommended that you generate md files directly into `'/pages'` as this will cause `jekyll server` to loop through... `a-z.md` file has changed which causes `jekyll builder` to run which creates `a-z.html` AND runs plugins, which regenerates the `a-z.md` file, repeats.  See more notes below related to using this plugin with io.github sites. 
* **exclude** [Array<String>] - Array of page names that should NOT be indexed.
* **include_posts** [Array<Strings>] - Array of pages that have posts that will be indexed individually.
* **index_titles** [ture | false] - The title of the page being indexed will be one of the index terms **IF** true
* **front_matter_ext** [Array<String>] - Additional front matter to add the the a-z index when generating a mark down file.  (e.g. `['sidebar: home_sidebar']`


Custom Terms:
---------------
By default, titles are indexed in the A-Z Index.  To add additional terms for a page, specify a-z front matter on each page.

```
a-z: ['Alternate Index Term', 'Another Index Term', 'And Another']
``` 


Credits and Acknowlegements
---------------
Author: E. Lynette Rayle

Thanks to the developers of the sitemap plugin which was used as the base code for the a-z plugin.
Sitemap Author: Michael Levin ([http://www.kinnetica.com](http://www.kinnetica.com))
Sitemap Configuration Update: Daniel Groves ([http://danielgroves.net](http://danielgroves.net))

Distributed Under A [Creative Commons](http://creativecommons.org/licenses/by/3.0/) License
