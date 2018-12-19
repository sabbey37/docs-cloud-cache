---
title: Viewing All Plans Available for Pivotal Cloud Cache
---

Run `cf marketplace -s p-cloudcache` to view all plans available for PCC. The plan names displayed are configured by the operator on tile installation.

<pre class='terminal'>
$ cf marketplace -s p-cloudcache

Getting service plan information for service p-cloudcache as admin...
OK

service plan   description      free or paid
extra-small    Caching Plan 1   free
small          Caching Plan 2   free
medium         Caching Plan 3   free
large          Caching Plan 4   free
extra-large    Caching Plan 5   free
</pre>

