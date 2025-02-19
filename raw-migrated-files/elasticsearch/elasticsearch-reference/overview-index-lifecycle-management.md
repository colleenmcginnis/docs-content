---
navigation_title: "Overview"
---

# {{ilm-init}} overview [overview-index-lifecycle-management]


You can create and apply {{ilm-cap}} ({{ilm-init}}) policies to automatically manage your indices according to your performance, resiliency, and retention requirements.

Index lifecycle policies can trigger actions such as:

* **Rollover**: Creates a new write index when the current one reaches a certain size, number of docs, or age.
* **Shrink**: Reduces the number of primary shards in an index.
* **Force merge**: Triggers a [force merge](https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-forcemerge.html) to reduce the number of segments in an index’s shards.
* **Delete**: Permanently remove an index, including all of its data and metadata.

{{ilm-init}} makes it easier to manage indices in hot-warm-cold architectures, which are common when you’re working with time series data such as logs and metrics.

You can specify:

* The maximum shard size, number of documents, or age at which you want to roll over to a new index.
* The point at which the index is no longer being updated and the number of primary shards can be reduced.
* When to force a merge to permanently remove documents marked for deletion.
* The point at which the index can be moved to less performant hardware.
* The point at which the availability is not as critical and the number of replicas can be reduced.
* When the index can be safely deleted.

For example, if you are indexing metrics data from a fleet of ATMs into Elasticsearch, you might define a policy that says:

1. When the total size of the index’s primary shards reaches 50GB, roll over to a new index.
2. Move the old index into the warm phase, mark it read only, and shrink it down to a single shard.
3. After 7 days, move the index into the cold phase and move it to less expensive hardware.
4. Delete the index once the required 30 day retention period is reached.

::::{important}
To use {{ilm-init}}, all nodes in a cluster must run the same version. Although it might be possible to create and apply policies in a mixed-version cluster, there is no guarantee they will work as intended. Attempting to use a policy that contains actions that aren’t supported on all nodes in a cluster will cause errors.

::::
