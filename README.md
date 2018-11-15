# docs-cloud-cache

## About Product Name

The name of the product is Pivotal Cloud Cache. 
The name can be abbreviated after first use in body text on the page.
For example: first use in body text is "Pivotal Cloud Cache (PCC)". 
In titles and headings and in subsequent use on the page, use "PCC".

## Branches in this Content Repo 

**master** - use for unreleased documentation, currently available on http://docs-pcf-staging.cfapps.io/p-cloud-cache/1-6.
The master branch is the tree-trunk, so ALWAYS make changes you want carried forward in this branch. This includes:

Unreleased features
Doc bug fixes
Doc reorganization or enhancement
Then, if necessary, immediately cherry-pick/copy any changes that you want to push immediately to production into the appropriate "-live" branch below:

**1.5-branch** - current branch for documentation that is assumed/expected to be live on http://docs.pivotal.io/p-cloud-cache/1-5.
**1.4-branch** - current branch for documentation that is assumed/expected to be live on http://docs.pivotal.io/p-cloud-cache/1-4.
**1.3-branch** - current branch for documentation that is assumed/expected to be live on http://docs.pivotal.io/p-cloud-cache/1-3.
**1.2-branch** - not in use because the docs are no longer live. PDF available at http://docs.pivotal.io/archives/p-cloud-cache-1.2.2.pdf
**1.1-branch** - not in use because the docs are no longer live. PDF available at http://docs.pivotal.io/archives/p-cloud-cache-1.1.5.pdf
**1.0-branch** - not in use because the docs are no longer live. PDF available at http://docs.pivotal.io/archives/p-cloud-cache-1.0.8.pdf

Other branches are sometimes created to PR corrections/edits back into live docs.
The above info about branches comes from Samia Nneji and Chris Wong and is correct as of November 15, 2018.

## Partials

Cross-product partials for **Pivotal Cloud Cache** are single sourced from the [Services Partials](https://github.com/pivotal-cf/docs-services-partials) repo.

Previously, these partials were sourced from the v018.x branch of the [On Demand Service Broker SDK](https://github.com/pivotal-cf/docs-on-demand-service-broker/tree/v0.18.x) content repo.

## Staging

The staging docs are on PWS using https://docs-pcf-staging.cfapps.io/.

Staging docs for the v1.6 release are on https://docs-pcf-staging.cfapps.io/p-cloud-cache/1-6/index.html . 
Ask in the pcf-docs Slack channel if you need access.

## Developing docs locally

This will make the book available at localhost:4567 and automatically update when you write changes to disk

```
cd docs-book-cloud-cache
bundle install
bundle exec bookbinder watch

```

