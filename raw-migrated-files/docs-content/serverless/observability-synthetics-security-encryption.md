# Synthetics Encryption and Security [observability-synthetics-security-encryption]

Elastic Synthetics was designed with security in mind encrypting both persisted and transmitted data. This page catalogs the points within Elastic Synthetics where data is either stored or transmitted in an encrypted fashion.


## Synthetics UI [observability-synthetics-security-encryption-synthetics-ui] 

Data is stored in [Kibana Secure Saved Objects](../../../deploy-manage/security/secure-saved-objects.md), with sensitive fields encrypted. These fields include your script source, params, and global params.


## Synthetics Service [synthetics_service] 

The Global Elastic Synthetics Service performs all communication of sensitive data (both internally, and with Kibana) over encrypted connections and encrypts all data persisted to disk as well.


## Synthetics Private Locations [synthetics_private_locations] 

In Kibana configuration for private locations is stored in two places, Synthetics saved objects which always encrypt sensitive fields using [Kibana Secure Saved Objects](../../../deploy-manage/security/secure-saved-objects.md) and also in Fleet, which uses unencrypted saved objects restricted by user permissions. For Elastic Cloud customers all data is secured on disk regardless of whether additional saved object encryption is present. See our [Cloud Security Statement](https://www.elastic.co/cloud/security) for more information. We recommend that self-managed customers encrypt disks for their Elasticsearch instances if this is a concern.

All data is encrypted in transit. See [Elastic Agent configuration encryption](https://www.elastic.co/guide/en/fleet/current/_elastic_agent_configuration_encryption.html) for more details.

