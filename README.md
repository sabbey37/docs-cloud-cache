# docs-cloud-cache

## Staging

The staging docs are on PWS using the pcf-gemfire@pivotal.io account

## Pushing docs to CF

These docs are served as an app in CF

```
cd book
bundle install
bookbinder bind local
cd final_app
cf push p-cloudcache-docs-staging -b https://github.com/cloudfoundry/ruby-buildpack#v1.6.28
```
