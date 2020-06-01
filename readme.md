### OCI API Signing Postman Collection

This Postman collection uses pre-request scripts to assemble the signatures required to invoke the OCI APIs. It is intended to allow for Postman to be used for ad-hoc API testing as part of the development of management and monitoring scripts and infrastructure automation.

The script requires several variable to be populated to facilitate the signing process:

* `private-key` - the signing key in PEM format
* `key-fingerprint` - the fingerprint of the uploaded public cert matching the private key
* `tenancy-id` - the OCID of the tenancy being accessed via the API
* `user-id` - the OCID of the user with which the key is associated

Requests in the collection are provided as samples, and may require additional variables, such as `region`, `compartment-id`, etc. to be set.

In addition, the script sets the following environment variables during invocation for each request, so be careful not to override them or rely on them in your own environment:

* `auth-signature`
* `hostname`
* `request-date`
* `request-target`
* `content-sha256`
* `content-length`

A full writeup is available on [redthunder.blog](https://redthunder.blog/2019/07/10/calling-oci-apis-from-postman/)