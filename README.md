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

## Partials

Cross-product partials for **Pivotal Cloud Cache** are single sourced from the [Services Partials](https://github.com/pivotal-cf/docs-services-partials) repo.

Previously, these partials were sourced from the v018.x branch of the [On Demand Service Broker SDK](https://github.com/pivotal-cf/docs-on-demand-service-broker/tree/v0.18.x) content repo.

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

