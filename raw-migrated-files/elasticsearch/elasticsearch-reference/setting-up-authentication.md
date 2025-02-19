# User authentication [setting-up-authentication]

Authentication identifies an individual. To gain access to restricted resources, a user must prove their identity, via passwords, credentials, or some other means (typically referred to as authentication tokens).

The {{stack}} authenticates users by identifying the users behind the requests that hit the cluster and verifying that they are who they claim to be. The authentication process is handled by one or more authentication services called [*realms*](../../../deploy-manage/users-roles/cluster-or-deployment-auth/authentication-realms.md).

You can use the native support for managing and authenticating users, or integrate with external user management systems such as LDAP and Active Directory.

The {{stack-security-features}} provide built-in realms such as `native`,`ldap`, `active_directory`, `pki`, `file`, `saml`, `kerberos`, `oidc`, and `jwt`. If none of the built-in realms meet your needs, you can also build your own custom realm and plug it into the {{stack}}.

When {{security-features}} are enabled, depending on the realms you’ve configured, you must attach your user credentials to the requests sent to {{es}}. For example, when using realms that support usernames and passwords you can simply attach [basic auth](https://en.wikipedia.org/wiki/Basic_access_authentication) header to the requests.

The {{security-features}} provide two services: the token service and the API key service. You can use these services to exchange the current authentication for a token or key. This token or key can then be used as credentials for authenticating new requests. The API key service is enabled by default. The token service is enabled by default when TLS/SSL is enabled for HTTP.
























