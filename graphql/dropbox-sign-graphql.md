# Dropbox Sign (HelloSign) GraphQL Schema

## Overview

This conceptual GraphQL schema represents the Dropbox Sign (formerly HelloSign) eSignature REST API v3. Dropbox Sign provides legally binding electronic signature workflows including embedded signing, reusable templates, signer fields, branded flows, audit trails, and tamper-proof document delivery. The schema is derived from the official REST API reference at https://developers.hellosign.com/api/reference/ and the OpenAPI specification at https://github.com/hellosign/hellosign-openapi.

## Schema Source

- **API Reference**: https://developers.hellosign.com/api/reference/
- **OpenAPI Specification**: https://github.com/hellosign/hellosign-openapi/blob/main/openapi.yaml
- **Base URL**: https://api.hellosign.com/v3
- **Authentication**: HTTP Basic Auth (API key) or OAuth 2.0 Bearer tokens

## Type Summary

The schema defines 67 named GraphQL types covering the full surface area of the Dropbox Sign API:

### Enumerations (10 types)

| Type | Description |
|------|-------------|
| `SignatureRequestStatus` | Lifecycle states for a signature request (AWAITING_SIGNATURE, SIGNED, DECLINED, EXPIRED, CANCELLED, ERROR, DRAFT) |
| `SignatureRequestType` | How a request was initiated (REQUEST, EMBEDDED, TEMPLATE, BULK) |
| `SignatureStatus` | Per-signer signature states (AWAITING_SIGNATURE, SIGNED, DECLINED, ERROR) |
| `SignatureDate` | Date dimension enum for filtering/sorting (CREATED_AT, UPDATED_AT, EXPIRES_AT, SIGNED_AT) |
| `DocumentType` | Supported document formats (PDF, WORD_DOC, DOCX, IMAGE) |
| `FormFieldType` | Types of form fields placed on documents (SIGNATURE, DATE_SIGNED, INITIALS, TEXT, CHECKBOX, RADIO, DROPDOWN, HYPERLINK, ATTACHMENT) |
| `TemplateRole` | Role types in a template (SIGNER, CC, APPROVER) |
| `UnclaimedDraftType` | Unclaimed draft creation modes (SEND_DOCUMENT, REQUEST_SIGNATURE) |
| `UserType` | User membership types (PRIMARY, MEMBER, INVITEE) |
| `AccountPlan` | Subscription tiers (FREE, ESSENTIALS, DROPBOX_PROFESSIONAL, STANDARD, PREMIUM) |
| `EventType` | All webhook/callback event types emitted by the platform |
| `BulkSendJobStatus` | States of a bulk send job (QUEUED, PROCESSING, COMPLETE, FAILED, CANCELLED) |
| `SignerOrder` | Signing order modes (SEQUENTIAL, PARALLEL) |

### Signature Request Types (7 types)

| Type | Description |
|------|-------------|
| `SignatureRequest` | Core object representing a signature request with status, signers, documents, and metadata |
| `SignatureRequestDetails` | Extended detail view with custom fields, template IDs, and full signer list |
| `Signer` | A recipient who is asked to sign, with optional PIN and SMS auth |
| `SignerDetails` | Full signer record with timestamps, reassignment info, and authentication flags |
| `SignerRole` | Named role definition used in templates |
| `SignerAccessCode` | PIN access code presence indicator per signer |
| `SignerOrder` | Enum for sequential vs parallel signing flows |

### Signature Types (2 types)

| Type | Description |
|------|-------------|
| `Signature` | A signer's signature record with status and timestamps |
| `SignatureDetails` | Extended signature record with error info and reassignment tracking |

### Document and Field Types (7 types)

| Type | Description |
|------|-------------|
| `Document` | Reference to a document attached to a request |
| `DocumentDetails` | Full document record with URL and association IDs |
| `TemplateField` | Positioned field definition on a template |
| `FieldGroup` | Logical grouping of related fields with a rule |
| `FormField` | Positioned field placed on a document with validation |
| `FormFieldGroup` | Grouped form fields with a label and rule |
| `FormFieldValue` | Key-value pair representing a filled-in custom field |

### CC Types (2 types)

| Type | Description |
|------|-------------|
| `CC` | CC recipient with email and optional role |
| `CCDetails` | Extended CC record |

### Metadata Type (1 type)

| Type | Description |
|------|-------------|
| `Metadata` | Arbitrary key-value metadata attached to a signature request |

### Template Types (4 types)

| Type | Description |
|------|-------------|
| `Template` | Reusable template with signer roles, documents, and custom fields |
| `TemplateDetails` | Extended template with named form fields and account access |
| `TemplateDocument` | Document associated with a template |
| `TemplateForm` | Form field and group structure of a template |

### Unclaimed Draft Types (2 types)

| Type | Description |
|------|-------------|
| `UnclaimedDraft` | A draft signature request with a claim URL for embedded flows |
| `UnclaimedDraftDetails` | Extended unclaimed draft with type information |

### Embedded Types (2 types)

| Type | Description |
|------|-------------|
| `EmbeddedURL` | Short-lived URL used for embedded signing or requesting |
| `EmbeddedDetails` | Extended embedded URL with request token and ID |

### Team Types (3 types)

| Type | Description |
|------|-------------|
| `Team` | The team associated with an account, including members and invitees |
| `TeamDetails` | Extended team record with role codes |
| `TeamInvite` | A pending team invitation with expiration state |

### User and Account Types (4 types)

| Type | Description |
|------|-------------|
| `User` | Account user with quotas and callback configuration |
| `UserDetails` | Extended user record with locale |
| `Account` | Authenticated account record |
| `AccountDetails` | Quota details for documents, templates, and SMS verifications |

### API App Types (4 types)

| Type | Description |
|------|-------------|
| `App` | OAuth API application registered on the platform |
| `AppDetails` | Redirect URL and test mode configuration for an app |
| `APIKey` | An API key record with creation and expiration dates |
| `OauthToken` | OAuth 2.0 access and refresh token response |

### Webhook and Event Types (5 types)

| Type | Description |
|------|-------------|
| `Webhook` | Webhook subscription configuration |
| `WebhookEvent` | Top-level webhook payload envelope |
| `CallbackDetails` | Callback configuration and HMAC hash details |
| `Event` | Event body with type, time, and HMAC hash |
| `EventDetails` | Event metadata including related signature and app IDs |

### Bulk Send Types (2 types)

| Type | Description |
|------|-------------|
| `BulkSendJob` | Summary of a bulk signature request job |
| `BulkSendJobDetails` | Extended bulk send job with per-request status |

### List Wrappers (6 types)

| Type | Description |
|------|-------------|
| `ListInfo` | Pagination metadata (page count, current page, page size, total) |
| `SignatureRequestList` | Paginated list of signature requests |
| `TemplateList` | Paginated list of templates |
| `TeamList` | Paginated list of teams |
| `BulkSendJobList` | Paginated list of bulk send jobs |
| `AppList` | Paginated list of API apps |

### Root Types (2 types)

| Type | Description |
|------|-------------|
| `Query` | Read operations: fetch signature requests, templates, embedded URLs, account, team, apps, bulk jobs |
| `Mutation` | Write operations: create/cancel/remind signature requests, manage templates, teams, apps, bulk jobs |

## Key API Capabilities Modeled

- **Signature Requests**: Send, retrieve, list, cancel, and remind on signature requests with support for multiple signers, ordering, PIN access codes, and SMS authentication.
- **Templates**: Create and manage reusable templates with named signer roles, CC roles, and placed form fields.
- **Embedded Flows**: Generate short-lived embedded URLs for in-app signing and requesting without leaving the host application.
- **Unclaimed Drafts**: Pre-populate signature requests and hand them off to a requester via a claim URL.
- **Bulk Send**: Send a single template to many recipients simultaneously and track progress via bulk send jobs.
- **API Apps**: Register and configure OAuth applications with custom branding, redirect URLs, and white-labeling options.
- **Teams**: Manage multi-user team memberships and invitations.
- **Events/Webhooks**: Subscribe to and receive webhook callbacks for all lifecycle events on signature requests, templates, and accounts.

## Schema File

See `dropbox-sign-schema.graphql` in this directory for the full GraphQL SDL definition.
