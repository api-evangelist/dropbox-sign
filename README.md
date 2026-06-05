# Dropbox Sign (dropbox-sign)

Dropbox Sign (formerly HelloSign) is an eSignature platform that lets developers and businesses embed legally binding electronic signature workflows into their applications and websites. The product supports embedded signing and requesting, reusable templates, custom signer fields, branded signing flows, audit trails, and tamper-proof document delivery. The Dropbox Sign API is documented with an official OpenAPI specification and authenticated via HTTP Basic Auth with an API key or OAuth 2.0 Bearer tokens.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/dropbox-sign/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/dropbox-sign/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- eSignature
- Electronic Signature
- Document Signing
- Workflow Automation
- Documents

## Timestamps

- **Created:** 2026-05-11
- **Modified:** 2026-05-30

## APIs

### Dropbox Sign REST API

Versioned REST API (v3) for sending signature requests, managing templates, teams, accounts, embedded signing/requesting flows, OAuth apps, and reports. Authentication is HTTP Basic Auth with an API key or OAuth 2.0 Bearer tokens; the API ships with an officially maintained OpenAPI specification used to generate SDKs and reference docs.

- **Human URL:** [https://developers.hellosign.com/api/api-reference-welcome](https://developers.hellosign.com/api/api-reference-welcome)
- **Base URL:** `https://api.hellosign.com/v3`

#### Tags

- eSignature
- Electronic Signature
- Document Signing
- Documents

#### Properties

- [Documentation](https://developers.hellosign.com/api/api-reference-welcome)
- [OpenAPI](https://github.com/hellosign/hellosign-openapi/blob/main/openapi.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Git Hub  Open A P I  Repo](https://github.com/hellosign/hellosign-openapi)
- [Getting Started](https://developers.hellosign.com/api/reference)
- [Postman Collection](collections/dropbox-sign.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/dropbox-sign.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Dropbox Sign Events and Callbacks API

Outbound event / callback surface for Dropbox Sign. The platform POSTs JSON event payloads (wrapped in a `multipart/form-data` `json` field) to a subscriber-configured URL whenever signature requests, templates, and account-level activity change state. Two callback scopes are supported: account callbacks (configured on the authenticated account) and app callbacks (configured per API app and routed by `client_id`). Authenticity is verified via the `event.event_hash` field, computed as HMAC-SHA256 of `event_time + event_type` keyed by the receiving account's API key.

- **Human URL:** [https://developers.hellosign.com/docs/events/overview/](https://developers.hellosign.com/docs/events/overview/)

#### Tags

- eSignature
- Webhooks
- Events
- Callbacks
- Event-Driven

#### Properties

- [Documentation](https://developers.hellosign.com/docs/events/overview/)
- [Walkthrough](https://developers.hellosign.com/docs/events/walkthrough/)
- [Account Callbacks](https://developers.hellosign.com/api/reference/operation/accountUpdateEventCallback/)
- [App Callbacks](https://developers.hellosign.com/api/reference/operation/apiAppCreateEventCallback/)
- [AsyncAPI](https://raw.githubusercontent.com/api-evangelist/dropbox-sign/refs/heads/main/asyncapi/dropbox-sign-events-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Postman Collection](collections/dropbox-sign.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/dropbox-sign.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/dropboxsign)
- [Website](https://sign.dropbox.com)
- [Documentation](https://developers.hellosign.com)
- [A P I  Documentation](https://developers.hellosign.com/api/api-reference-welcome)
- [Pricing](https://sign.dropbox.com/pricing)
- [Sign Up](https://sign.dropbox.com/signup)
- [GitHub Organization](https://github.com/hellosign)
- [L L Ms Txt](https://developers.hellosign.com/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
