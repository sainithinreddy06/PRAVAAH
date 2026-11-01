# Security, Evidence Integrity, and Audit Boundaries

## Access control

PRAVAAH includes authentication and role-oriented authorization in its supported API workflows, including regional scoping where applicable. Deployments should use least-privilege accounts and review access before exposing sensitive data.

## Evidence integrity

Evidence uploads store a SHA-256 digest. On download, the service recalculates the digest and compares it with the stored value; a mismatch is rejected rather than served as unchanged evidence. This is an integrity check, not a substitute for malware scanning, protected backups, object-store versioning, or retention controls.

## Audit hash chain

Audit records include a previous hash and an event hash derived from canonical event data. The chain verification endpoint recalculates the links and compares the calculated head with the stored chain head.

The mechanism is **tamper-evident, not independently immutable**. A sufficiently privileged operator who can rewrite both audit records and chain state may be able to reconstruct a valid chain. Stronger assurance requires signed checkpoints stored outside the application database under separately controlled access.

## Notifications and background processing

The supported notification channel is in-app. Email and SMS adapters are not implemented. The notification worker must be deployed and configured separately if continuous background processing is required; API-triggered escalation and a running worker are different execution paths.

## Production-readiness considerations

Before any real institutional deployment, operators should independently verify:

- TLS and secret management.
- Database least privilege, backups, restore procedures, and retention.
- Upload size/type validation, storage access controls, and malware scanning.
- Authentication, authorization, and session settings.
- Logging that excludes credentials and unnecessary personal data.
- Monitoring, failure recovery, and worker supervision.
- Audit checkpoint export to separately controlled storage.
- Applicable privacy, security, and regulatory obligations.

## Regulatory boundary

PRAVAAH is an academic/hackathon prototype. It is not an official AICTE service, does not grant or revoke approvals, and must not be treated as a substitute for applicable regulations or authorized human review. Any official-system integration requires authorization and approved interfaces.
