# Dropbox Sign (dropbox-sign)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
