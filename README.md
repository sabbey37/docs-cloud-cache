# docs-cloud-cache

## About Product Name

The name of the product is Pivotal Cloud Cache. 
The name can be abbreviated after first use in body text on the page.
For example: first use in body text is "Pivotal Cloud Cache (PCC)". 
In titles and headings and in subsequent use on the page, use "PCC".

## About Branches 

Currently, **v1.2-branch**, **v1.1-branch** and **v1.0-branch** are your branches for (already released) v1.2, v1.1, and v1.0 documentation.

Use the **master** branch for unreleased, v1.3, documentation; you can make changes or PRs relevant to v1.2 on that branch.

Other branches are sometimes created to PR corrections/edits back into live docs.

The above info about branches comes from Megan Moore and Jane Day and is correct as of November 22, 2017.

## Staging

The staging docs are on PWS using https://docs-pcf-staging.cfapps.io/.

Staging docs for the v1.3 release are on https://docs-pcf-staging.cfapps.io/p-cloud-cache/1-3/index.html . 
Ask in the pcf-docs Slack channel if you need access.

## Developing docs locally

This will make the book available at localhost:4567 and automatically update when you write changes to disk

```
cd docs-book-cloud-cache
bundle install
bundle exec bookbinder watch

```

## Building Docs as part of docs-book-pcfservices

1. Clone `pivotal-cf/docs-book-pcfservices` into `~/workspace` directory
2. Clone this repo into `~/workspace` directory as well.
3. Edit the `docs-book-pcfservices/config.yml` to add:
 
    ```
    - repository:
        name: pivotal-cf/docs-cloud-cache     # name of our docs repo
        at_path: content                      # subfolder in our repo containing our erbs and images
      directory: p-cloud-cache                # url for our docs to live in, in html site
      subnav_template: cloudcache_subnav.erb  # name of file containing our navigation (appears to left of docs)
    ```
4. Edit the `docs-book-pcfservices/master-middleman/source/index.html.erb` to add, at the top of the `Pivotal Software` section:

    ```
    <li class="panel span3">
      <a class="configure" href="/p-cloud-cache/index.html" id="cloudcache">
        <div class="prodname">
          Pivotal <br>Cloud Cache
        </div>
      </a>
    </li>
    ```
5. Copy the `docs-cloud-cache/master-middleman/source/subnavs/cloudcache_subnav.erb` to `docs-book-pcfservices/master-middleman/source/subnavs/`
6. In `docs-book-pcfservices`, run `bookbinder watch` (after getting ruby/rbenv/bundle/etc installed).


