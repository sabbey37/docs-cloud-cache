# docs-cloud-cache

## About Branches 

Currently, **v1.1-branch** and **v1.0-branch** are your branches for (already released) v1.1 and v1.0 documentation. A branch for 1.2 (unreleased) documentation exists; you can make changes or PRs relevant to 1.2 on that branch. Version 1.2 is scheduled for GA on 9/30/17.

Your branch for changes on future releases (later than v1.2) is **master branch**.

Other branches are sometimes created to PR corrections/edits back into live docs.

The **master branch** is in use for versions after 1.2.

The above info about branches comes from Megan Moore and is correct as of September 26, 2017.

## Staging

The staging docs are on PWS using https://docs-pcf-staging.cfapps.io/.

Staging docs for the upcoming v1.2 release are on https://docs-pcf-staging.cfapps.io/p-cloud-cache/1-2/index.html.

## Developing docs locally

This will make the book available at localhost:4567 and automatically update when you write changes to disk

```
cd docs-book-cloud-cache
bundle install
bundle exec ookbinder watch

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


